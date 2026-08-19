---
name: pavoot-resolve-unknown-faces
description: >-
  Turn unnamed people detected in Pavoot event media into named persons — run the
  Rekognition match scans, review the resulting suggestions, and approve, reject
  or ignore each merge safely.
api: Pavoot Application API
generated: '2026-08-13'
method: generated
source: openapi/_original/pavoot-openapi.json
operations:
  - scan_unknown_faces_for_matches_endpoint_scanUnknownFacesForMatches_post
  - scan_existing_faces_for_person_endpoint_scanExistingFacesForPerson_post
  - get_face_match_suggestions_endpoint_getFaceMatchSuggestions_get
  - approve_face_match_suggestion_endpoint_approveFaceMatchSuggestion_post
  - reject_face_match_suggestion_endpoint_rejectFaceMatchSuggestion_post
  - ignore_face_match_suggestion_endpoint_ignoreFaceMatchSuggestion_post
  - get_project_persons_endpoint_getProjectPersons_get
  - find_duplicate_persons_findDuplicatePersons_get
  - merge_persons_endpoint_mergePersons_post
---

# Resolve unknown faces into named people in Pavoot

Pavoot's tagging pipeline detects faces and groups them into persons, but a person
it cannot name is stored with the literal name `?`. This flow proposes merges of
those unknowns into known people and puts each proposal in front of a human.

**This is identity resolution over biometric data. Every merge is destructive and
every merge should be reviewed by a person.** Approving a wrong suggestion
attributes one guest's photos to another guest — and the follow-up email flow then
sends them out.

## 1. See where you stand

`GET /getProjectPersons?projectId=<id>` lists the project's persons. Unknowns
carry the name `?`.

## 2. Run a match scan

Pick the scan that matches your intent:

- `POST /scanUnknownFacesForMatches` — scans all persons named `?` and finds
  Rekognition matches to **named** persons. Creates `face_match_suggestions` so a
  user can approve merging the unknown into the known one, giving the unknown a
  name. **Runs in the background and returns immediately.**
- `POST /scanExistingFacesForPerson` — the narrower scan, for one person.

Because these return before the work is done, there is no completion signal. Poll
step 3 until the suggestion count stops changing.

## 3. Review the suggestions

`GET /getFaceMatchSuggestions?projectId=<id>` returns the suggestions for
review/approve/reject. Optional `status_filter` narrows the list.

Present these to a human. Do not auto-approve.

## 4. Act on each suggestion

**Approve** — `POST /approveFaceMatchSuggestion` merges the candidate person into
the reference person. Concretely, per Pavoot's own description:

1. In one DB transaction: reassign all `image_faces` from candidate to reference,
   delete the suggestion, delete the candidate person, and update name/folder.
2. In Rekognition: delete the candidate's face from the collection.
3. Emit `person.folders`, `persons.updated` and `face_match_suggestions.updated`
   in a background task so the response returns immediately.

Optional `chosen_name` sets the reference person's name after the merge — use it
when the human picked a name rather than accepting the existing one.

**This deletes the candidate person and their Rekognition face. There is no undo
operation in the API.**

**Reject** — `POST /rejectFaceMatchSuggestion` records that these are not the same
person.

**Ignore** — `POST /ignoreFaceMatchSuggestion` sets it aside without asserting
either way.

## 5. Clean up duplicates among named people

Separately from unknown-face resolution, `GET /findDuplicatePersons` surfaces
likely duplicate named persons, and `POST /mergePersons` merges them. Organization
-wide equivalents exist (`/getOrgOrphanedPersons`, `/getOrgPotentialDuplicates`,
`/scanOrgFacesForMatches`, `/getOrgFaceMatchSuggestions`) when the same guest
appears across several events.

## Agent guardrails

- **Never approve a suggestion without human confirmation.** Approval is an
  irreversible biometric identity assertion with no undo endpoint.
- **Scans are safe; merges are not.** Running `/scanUnknownFacesForMatches` costs
  compute but changes no identities. Approving does.
- **Order matters.** Resolve identities *before* running
  `pavoot-send-attendee-galleries` — otherwise attendees are emailed galleries
  built from a wrong identity graph.
- **No idempotency key.** A retried approve on an already-merged suggestion has no
  defined behaviour; re-read `GET /getFaceMatchSuggestions` instead of retrying.

## Failure handling

- **401 / 403** — missing Clerk session, or no permission on this project.
  `/faces` is one of the routes explicitly gated by permissions; check with
  `GET /checkRouteAccess?path=/faces`.
- **422** — `detail` is an array of `{loc, msg, type}`; other statuses return a
  string.
- The scan endpoints accept a free-form object body (`additionalProperties: true`)
  and the spec types neither their input nor their output, so validate what you
  send against the described behaviour rather than against the schema.
