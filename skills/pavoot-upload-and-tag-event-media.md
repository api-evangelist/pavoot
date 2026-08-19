---
name: pavoot-upload-and-tag-event-media
description: >-
  Upload event photos into a Pavoot project via S3 presigned URLs, register them
  for AI tagging, and detect and recover the tagging steps that fail or get stuck.
api: Pavoot Application API
generated: '2026-08-13'
method: generated
source: openapi/_original/pavoot-openapi.json
operations:
  - generate_presigned_urls_endpoint_generatePresignedUrls_post
  - create_multipart_upload_endpoint_createMultipartUpload_post
  - complete_multipart_upload_endpoint_completeMultipartUpload_post
  - abort_multipart_upload_endpoint_abortMultipartUpload_post
  - add_images_route_addImages_post
  - get_tagging_failures_projects__project_id__images_tagging_failures_get
  - retry_tagging_projects__project_id__images_retry_tagging_post
  - get_project_folders_endpoint_getProjectFolders_get
  - create_folder_endpoint_createFolder_post
---

# Upload and tag event media in Pavoot

Bytes never pass through the Pavoot API. You ask Pavoot for a presigned S3
destination, upload directly to S3, then tell Pavoot which UUIDs landed so it can
queue AI tagging.

## Before you start

- Base URL is `https://api.pavoot.com`.
- Every call needs `Authorization: Bearer <clerk-session-jwt>`. Without it you get
  `401 {"detail":"Unauthorized: Authentication failed"}` with no
  `WWW-Authenticate` header to guide you.
- You need a `projectId` (integer). List projects with `GET /getProjects`.
- Optional: put the upload in a folder. Read existing folders with
  `GET /getProjectFolders?projectId=<id>` or make one with `POST /createFolder`.
- **There is no idempotency key on this API.** Do not blind-retry any POST below;
  see "Failure handling".

## Step 1 — choose the upload path by file size

Pavoot has two, and they are not interchangeable.

**Small files — single PUT.** `POST /generatePresignedUrls` with:

- `files` (list): file info, each with `contentType` (required)
- `projectId` (int, required)
- `folderName` (str, optional)
- `photographerId` (str, optional)

It returns `urls`: a list of objects each carrying the file `id`, S3 `key`, the
presigned `url`, and `contentType`. Its own documented failure modes are 401 (not
authenticated), 403 (lacks permission), 400 (missing required parameters) and 500
(S3 access failed).

**Large files — multipart.** `POST /createMultipartUpload` initiates the S3
multipart upload and returns presigned part URLs so parts can be uploaded in
parallel. This exists specifically so browsers can push big files concurrently.

## Step 2 — upload to S3

PUT each file (or each part) straight to its presigned URL. Use the exact
`contentType` you declared in step 1 — a mismatch invalidates the signature.

For multipart, collect each part's ETag and part number, then finish with
`POST /completeMultipartUpload`. If you abandon the upload, call
`POST /abortMultipartUpload` rather than leaving it — incomplete multipart uploads
accumulate in S3.

## Step 3 — register the images

`POST /addImages` registers the uploaded images by UUID and queues tagging tasks
to SQS.

This handler is deliberately synchronous — Pavoot's own note says a 50-image
upload held the event loop for seconds when it was async, so it now runs in
FastAPI's threadpool. Expect it to be slow in proportion to batch size, and set
your client timeout accordingly rather than retrying.

## Step 4 — let tagging run

Tagging is asynchronous across three steps: `general`, `rekognition` and `bda`.
There is no job resource to poll and no completion callback. You learn the outcome
by reading domain state.

## Step 5 — find what failed or hung

`GET /projects/{project_id}/images/tagging-failures`

Query parameters:

- `steps` — comma-delimited, from `general,rekognition,bda`; defaults to all three
- `operator` — `AND` requires every selected step to match, `OR` matches any
- `statuses` — comma-delimited from `failed,stuck,pending`

Pavoot defines the two states precisely: **failed** is status `failed`; **stuck**
is status `pending` for more than one hour. That one-hour rule is the API's own
definition of a hung pipeline — do not invent a shorter timeout.

## Step 6 — retry the specific steps that broke

`POST /projects/{project_id}/images/retry-tagging` resets the named steps to
`pending` and re-queues them to the appropriate SQS queues. Retry only the steps
that failed, not the whole image, so you do not re-run expensive Rekognition work
that already succeeded.

## Failure handling

- **401** — token missing, expired, or belongs to a different Pavoot app. A valid
  Clerk session does not imply membership here; confirm with `GET /me`.
- **403** — authenticated but not permitted on this project. Check with
  `GET /getEffectivePermissions` or `GET /checkRouteAccess?path=<path>`.
- **422** — validation failure. `detail` is an **array** of `{loc, msg, type}`
  objects here, not a string. Every other status returns `detail` as a string.
  Type it as a union or you will crash on the first validation error.
- **Timeouts on `/addImages`** — no idempotency key exists, so a retry may
  re-register images and re-queue duplicate tagging work. Prefer to verify with
  `GET /getImages` or `GET /countImages` before retrying.
- **No rate-limit headers.** Nothing tells you how hard you may push. Throttle
  yourself conservatively on bulk uploads.
