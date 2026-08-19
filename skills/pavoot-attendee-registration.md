---
name: pavoot-attendee-registration
description: >-
  Stand up a Pavoot attendee registration page for an event, share its public
  link, and handle the token-scoped self-registration flow including the mandatory
  face photo upload.
api: Pavoot Application API
generated: '2026-08-13'
method: generated
source: openapi/_original/pavoot-openapi.json
operations:
  - get_attendee_registration_link_endpoint_getAttendeeRegistrationLink_get
  - get_attendee_registration_page_layout_endpoint_getAttendeeRegistrationPageLayout_get
  - set_attendee_registration_page_layout_endpoint_setAttendeeRegistrationPageLayout_put
  - attendee_registration_info_endpoint_attendee_registration_info__token__get
  - attendee_registration_presign_face_endpoint_attendee_registration_presign_face_post
  - register_attendee_endpoint_register_attendee_post
  - get_project_attendees_endpoint_getProjectAttendees_get
  - upsert_project_attendee_endpoint_upsertProjectAttendee_post
---

# Run attendee registration for a Pavoot event

This flow spans two trust zones. Organizer-side setup needs a Clerk session;
attendee-side registration is **token-scoped and public**. Do not mix them up —
the public half must never be called with an organizer token from a browser you
do not control.

## Organizer side (requires a Clerk session)

### 1. Design the registration form

Read the current layout with
`GET /getAttendeeRegistrationPageLayout?projectId=<id>` and write it back with
`PUT /setAttendeeRegistrationPageLayout`. The layout controls what the public form
asks for.

### 2. Get the public link

`GET /getAttendeeRegistrationLink?projectId=<id>` returns the public URL for the
registration form, **creating a token if none exists yet**. Calling it is
therefore a write on first use. It requires the same authorization as managing
attendees.

Treat the returned URL as a credential: anyone holding it can register into this
event.

### 3. Watch registrations arrive

`GET /getProjectAttendees?projectId=<id>` lists attendees and their workflow
status.

To create or correct an attendee yourself, `POST /upsertProjectAttendee` creates
or updates the `project_attendees` row and **creates a share link for the person
if one is missing** — which is what later lets that attendee be emailed their own
photos.

## Attendee side (public, token-scoped)

### 4. Render the form

`GET /attendee-registration-info/{token}` returns the project name and layout for
the form. Pavoot documents this as public: **no auth required**. This is the only
call the attendee's browser should make before submitting.

### 5. Upload the mandatory face photo

`POST /attendee-registration-presign-face` returns a presigned PUT for the
attendee profile photo, using the same S3 layout as the dashboard. PUT the image
straight to that URL.

The face photo is **mandatory** for attendee registration — it is what binds this
person to their photos later via face matching. Registration will not complete
without it.

### 6. Submit the registration

`POST /register-attendee`. Behaviour depends on the token type:

- **Public token** — attendee registration only, and the face photo is mandatory.
- **Member token** — requires the visitor to be signed in with Clerk, and allows
  registering as an attendee, a startup, or both. The face photo is still required
  whenever the attendee role is included.

Check which token type you are holding before building the UI; a member-token flow
that skips the Clerk sign-in will fail.

## What happens next

Registered attendees are matched against faces detected in uploaded event media.
Once photos are tagged, use the follow-up flow
(`pavoot-send-attendee-galleries`) to approve and send each attendee their own
gallery.

## Privacy note — read before deploying this

This flow collects **biometric data**: a face photo, enrolled into an AWS
Rekognition collection, that is used to identify a person across event media.
Pavoot publishes an attendee-facing privacy notice at
`https://pavoot.com/privacy-attendees` and a DPA at
`https://pavoot.com/client/dpa`, but publishes no biometric-specific retention
schedule or consent artifact. If you operate this form under GDPR (face data is
Article 9 special-category data) or a US state biometric statute, satisfy consent
and retention in your own layout and process — the API does not do it for you and
exposes no consent field.

## Failure handling

- **401** on organizer calls — missing or wrong-app Clerk session; verify with
  `GET /me`.
- **403** — session valid but lacking attendee-management permission on this
  project.
- **422** — `detail` is an **array** of `{loc, msg, type}`; every other error
  returns `detail` as a plain string.
- **No idempotency key.** A retried `POST /register-attendee` may create a
  duplicate person. Read `GET /getProjectAttendees` to reconcile rather than
  retrying blind.
