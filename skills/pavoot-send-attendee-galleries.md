---
name: pavoot-send-attendee-galleries
description: >-
  Approve Pavoot event attendees for their post-event photo email, send the
  emails, and correctly handle the partial-success response that a 200 hides.
api: Pavoot Application API
generated: '2026-08-13'
method: generated
source: openapi/_original/pavoot-openapi.json
operations:
  - get_project_attendee_setup_endpoint_getProjectAttendeeSetup_get
  - set_project_attendee_setup_endpoint_setProjectAttendeeSetup_put
  - get_project_attendee_email_template_endpoint_getProjectAttendeeEmailTemplate_get
  - set_project_attendee_email_template_endpoint_setProjectAttendeeEmailTemplate_put
  - get_project_attendees_endpoint_getProjectAttendees_get
  - set_attendee_email_approval_endpoint_setAttendeeEmailApproval_post
  - send_attendee_emails_endpoint_sendAttendeeEmails_post
  - upsert_project_attendee_endpoint_upsertProjectAttendee_post
---

# Send Pavoot attendees their event photos

This is the highest-consequence flow in the Pavoot API: it sends real email to
real event guests. It has no idempotency key and it returns **200 on partial
failure**. Read the whole skill before calling `/sendAttendeeEmails`.

## 1. Check the project's send configuration

`GET /getProjectAttendeeSetup?projectId=<id>` returns `auto_send_email` and
`send_from_email`.

If `auto_send_email` is on, Pavoot may already be sending — attendees will appear
with status `auto-sent`. Do not layer a manual send on top without checking.
Change configuration with `PUT /setProjectAttendeeSetup`.

## 2. Review the email template

`GET /getProjectAttendeeEmailTemplate?projectId=<id>` and
`PUT /setProjectAttendeeEmailTemplate`. Get the template right before approving
anyone — the template is read at send time, and there is no unsend.

## 3. Approve attendees

`GET /getProjectAttendees?projectId=<id>` lists attendees with their status.

`POST /setAttendeeEmailApproval` sets the workflow status. Valid values:

| Status | Meaning |
|---|---|
| `pending` | Not cleared to send |
| `approved` | Cleared to send |
| `approved-none` | Cleared, with no photos matched |
| `approved-Pavoot` | Cleared via the Pavoot-side approval variant |
| `sent` | Email sent |
| `auto-sent` | Sent by the automatic sender |
| `email-failed` | Send attempted and failed; see `last_email_error` |

Only `approved`, `approved-none` and `approved-Pavoot` are sendable. After a
send, you can move an attendee back to `pending` or an `approved*` value to adjust
the workflow or send again.

## 4. Send

`POST /sendAttendeeEmails` emails each eligible attendee their share link.

Preconditions the API enforces:

- Status must be `approved`, `approved-none` or `approved-Pavoot` — **or**
  `sent`/`auto-sent` when you pass `forceResend=true`.
- For any person with **zero images**, you must supply `zero_images_phrase`.
  Without it that recipient is rejected.

## 5. Reconcile — the step people skip

**A 200 from `/sendAttendeeEmails` does not mean every email was sent.** The
documented behaviour is per-recipient:

- On success, that attendee's status becomes `sent`.
- On failure, that attendee's status becomes `email-failed`, `last_email_error` is
  recorded, and **the loop continues to the next recipient**.

So the operation returns partial success. Always re-read
`GET /getProjectAttendees?projectId=<id>` after sending and count how many landed
on `email-failed`. That is the only way to know what actually happened.

To retry the failures, set them back to an approved status with
`POST /setAttendeeEmailApproval`, then call `/sendAttendeeEmails` again — or use
`forceResend=true` for ones already marked `sent`.

## Guardrails for agents

- **Never call `/sendAttendeeEmails` speculatively or as a retry after a
  timeout.** There is no idempotency key, so a duplicate call can double-send to
  guests. If a call times out, reconcile with `GET /getProjectAttendees` first and
  only re-send the recipients still in an approved state.
- **Confirm the recipient set before sending.** Approval is per attendee, but the
  send is a fan-out; verify the approved count matches what a human expects.
- **`forceResend=true` is a deliberate re-send to people who already got the
  email.** Treat it as requiring explicit human confirmation.

## Failure handling

- **401 / 403** — missing Clerk session, or no attendee-management permission on
  this project.
- **422** — `detail` is an array of `{loc, msg, type}`. A missing
  `zero_images_phrase` surfaces here.
- **No 429 is declared and no rate-limit headers exist**, so pace large sends
  yourself.
