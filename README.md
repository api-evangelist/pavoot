# Pavoot

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Pavoot is a Y Combinator-backed AI event-management platform that operates as an autonomous AI agent for running events end-to-end. It sources and matches the right attendees, personalizes invitations, captures and checks in guests on-site, automatically follows up with context from each interaction, tags event media (photos, faces, and logos) with AI, and attributes the resulting pipeline and ROI. The product targets field marketers, GTM leaders, sales teams, CMO/VP Marketing roles, and founders who want to turn events into pipeline. Pavoot runs no developer program — it issues no API keys, publishes no developer documentation and ships no SDKs — but its application backend at api.pavoot.com does serve a complete, publicly readable OpenAPI 3.1.0 describing 248 operations across event projects, media upload and AI tagging, face and person identity resolution, sponsor brand and logo recognition, attendee registration and follow-up email, gallery sharing, and organization permissions, together with FastAPI Swagger UI and ReDoc. The API itself is authenticated with Clerk-issued session tokens against Pavoot's own OAuth 2.0 / OpenID Connect authorization server at clerk.pavoot.com, so the contract is observable but not consumable by third parties.

**Areas:** Company · Event · Event Management · Marketing · AI Agents · Attendee Intelligence · Go-To-Market · Field Marketing · Pipelines

## Pavoot on APIs.io

Everything profiled for Pavoot is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/pavoot/](https://apis.io/providers/pavoot/)** — or go straight to one of the APIs or properties below.

### APIs (178)

- [Pavoot Abort Multipart Upload API](https://apis.io/apis/pavoot/pavoot-abortmultipartupload-api/) — The AbortMultipartUpload API from Pavoot — 1 operation(s) for abortmultipartupload.
- [Pavoot Add Brand API](https://apis.io/apis/pavoot/pavoot-addbrand-api/) — The AddBrand API from Pavoot — 1 operation(s) for addbrand.
- [Pavoot Add Brand To Projects API](https://apis.io/apis/pavoot/pavoot-addbrandtoprojects-api/) — The AddBrandToProjects API from Pavoot — 1 operation(s) for addbrandtoprojects.
- [Pavoot Add Images API](https://apis.io/apis/pavoot/pavoot-addimages-api/) — The AddImages API from Pavoot — 1 operation(s) for addimages.
- [Pavoot Add Images To Folder API](https://apis.io/apis/pavoot/pavoot-addimagestofolder-api/) — The AddImagesToFolder API from Pavoot — 1 operation(s) for addimagestofolder.
- [Pavoot Add Images To Share API](https://apis.io/apis/pavoot/pavoot-addimagestoshare-api/) — The AddImagesToShare API from Pavoot — 1 operation(s) for addimagestoshare.
- [Pavoot Add Logo API](https://apis.io/apis/pavoot/pavoot-addlogo-api/) — The AddLogo API from Pavoot — 1 operation(s) for addlogo.
- [Pavoot Add Logo Transcription API](https://apis.io/apis/pavoot/pavoot-addlogotranscription-api/) — The AddLogoTranscription API from Pavoot — 1 operation(s) for addlogotranscription.
- [Pavoot Add Person Face API](https://apis.io/apis/pavoot/pavoot-addpersonface-api/) — The AddPersonFace API from Pavoot — 1 operation(s) for addpersonface.
- [Pavoot Add Photographer API](https://apis.io/apis/pavoot/pavoot-addphotographer-api/) — The AddPhotographer API from Pavoot — 1 operation(s) for addphotographer.
- [Pavoot Add Photographer To Projects API](https://apis.io/apis/pavoot/pavoot-addphotographertoprojects-api/) — The AddPhotographerToProjects API from Pavoot — 1 operation(s) for addphotographertoprojects.
- [Pavoot Add Recipients API](https://apis.io/apis/pavoot/pavoot-addrecipients-api/) — The AddRecipients API from Pavoot — 1 operation(s) for addrecipients.
- [Pavoot Add Recipient To Projects API](https://apis.io/apis/pavoot/pavoot-addrecipienttoprojects-api/) — The AddRecipientToProjects API from Pavoot — 1 operation(s) for addrecipienttoprojects.
- [Pavoot Add Tag API](https://apis.io/apis/pavoot/pavoot-addtag-api/) — The AddTag API from Pavoot — 1 operation(s) for addtag.
- [Pavoot Add Tag Bulk API](https://apis.io/apis/pavoot/pavoot-addtagbulk-api/) — The AddTagBulk API from Pavoot — 1 operation(s) for addtagbulk.
- [Pavoot Admin API](https://apis.io/apis/pavoot/pavoot-admin-api/) — The Admin API from Pavoot — 28 operation(s) for admin.
- [Pavoot Approve Face Match Suggestion API](https://apis.io/apis/pavoot/pavoot-approvefacematchsuggestion-api/) — The ApproveFaceMatchSuggestion API from Pavoot — 1 operation(s) for approvefacematchsuggestion.
- [Pavoot Assign Face API](https://apis.io/apis/pavoot/pavoot-assignface-api/) — The AssignFace API from Pavoot — 1 operation(s) for assignface.
- [Pavoot Attendee Registration Info API](https://apis.io/apis/pavoot/pavoot-attendee-registration-info-api/) — The Attendee Registration Info API from Pavoot — 1 operation(s) for attendee registration info.
- [Pavoot Attendee Registration Presign Face API](https://apis.io/apis/pavoot/pavoot-attendee-registration-presign-face-api/) — The Attendee Registration Presign Face API from Pavoot — 1 operation(s) for attendee registration presign face.
- [Pavoot Brand Deletion Impact API](https://apis.io/apis/pavoot/pavoot-branddeletionimpact-api/) — The BrandDeletionImpact API from Pavoot — 1 operation(s) for branddeletionimpact.
- [Pavoot Bulk Add Brands API](https://apis.io/apis/pavoot/pavoot-bulkaddbrands-api/) — The BulkAddBrands API from Pavoot — 1 operation(s) for bulkaddbrands.
- [Pavoot Bulk Add Person Faces API](https://apis.io/apis/pavoot/pavoot-bulkaddpersonfaces-api/) — The BulkAddPersonFaces API from Pavoot — 1 operation(s) for bulkaddpersonfaces.
- [Pavoot Change Person Category API](https://apis.io/apis/pavoot/pavoot-changepersoncategory-api/) — The ChangePersonCategory API from Pavoot — 1 operation(s) for changepersoncategory.
- [Pavoot Check Route Access API](https://apis.io/apis/pavoot/pavoot-checkrouteaccess-api/) — The CheckRouteAccess API from Pavoot — 1 operation(s) for checkrouteaccess.
- [Pavoot Check Upload Limit API](https://apis.io/apis/pavoot/pavoot-checkuploadlimit-api/) — The CheckUploadLimit API from Pavoot — 1 operation(s) for checkuploadlimit.
- [Pavoot Commit Bulk Face Upload API](https://apis.io/apis/pavoot/pavoot-commitbulkfaceupload-api/) — The CommitBulkFaceUpload API from Pavoot — 1 operation(s) for commitbulkfaceupload.
- [Pavoot Complete Bulk Face Upload API](https://apis.io/apis/pavoot/pavoot-completebulkfaceupload-api/) — The CompleteBulkFaceUpload API from Pavoot — 1 operation(s) for completebulkfaceupload.
- [Pavoot Complete Multipart Upload API](https://apis.io/apis/pavoot/pavoot-completemultipartupload-api/) — The CompleteMultipartUpload API from Pavoot — 1 operation(s) for completemultipartupload.
- [Pavoot Count Images API](https://apis.io/apis/pavoot/pavoot-countimages-api/) — The CountImages API from Pavoot — 1 operation(s) for countimages.
- [Pavoot Count Trash Images API](https://apis.io/apis/pavoot/pavoot-counttrashimages-api/) — The CountTrashImages API from Pavoot — 1 operation(s) for counttrashimages.
- [Pavoot Create Folder API](https://apis.io/apis/pavoot/pavoot-createfolder-api/) — The CreateFolder API from Pavoot — 1 operation(s) for createfolder.
- [Pavoot Create Upload Link API](https://apis.io/apis/pavoot/pavoot-createuploadlink-api/) — The CreateUploadLink API from Pavoot — 1 operation(s) for createuploadlink.
- [Pavoot Delete Face API](https://apis.io/apis/pavoot/pavoot-deleteface-api/) — The DeleteFace API from Pavoot — 1 operation(s) for deleteface.
- [Pavoot Delete Folder API](https://apis.io/apis/pavoot/pavoot-deletefolder-api/) — The DeleteFolder API from Pavoot — 1 operation(s) for deletefolder.
- [Pavoot Delete Folder With Contents API](https://apis.io/apis/pavoot/pavoot-deletefolderwithcontents-api/) — The DeleteFolderWithContents API from Pavoot — 1 operation(s) for deletefolderwithcontents.
- [Pavoot Delete Images API](https://apis.io/apis/pavoot/pavoot-deleteimages-api/) — The DeleteImages API from Pavoot — 1 operation(s) for deleteimages.
- [Pavoot Delete Logo API](https://apis.io/apis/pavoot/pavoot-deletelogo-api/) — The DeleteLogo API from Pavoot — 1 operation(s) for deletelogo.
- [Pavoot Delete Logo Transcription API](https://apis.io/apis/pavoot/pavoot-deletelogotranscription-api/) — The DeleteLogoTranscription API from Pavoot — 1 operation(s) for deletelogotranscription.
- [Pavoot Delete Persons API](https://apis.io/apis/pavoot/pavoot-deletepersons-api/) — The DeletePersons API from Pavoot — 1 operation(s) for deletepersons.
- [Pavoot Delete Photographer API](https://apis.io/apis/pavoot/pavoot-deletephotographer-api/) — The DeletePhotographer API from Pavoot — 1 operation(s) for deletephotographer.
- [Pavoot Delete Recipient API](https://apis.io/apis/pavoot/pavoot-deleterecipient-api/) — The DeleteRecipient API from Pavoot — 1 operation(s) for deleterecipient.
- [Pavoot Delete Share API](https://apis.io/apis/pavoot/pavoot-deleteshare-api/) — The DeleteShare API from Pavoot — 1 operation(s) for deleteshare.
- [Pavoot Delete Tag API](https://apis.io/apis/pavoot/pavoot-deletetag-api/) — The DeleteTag API from Pavoot — 1 operation(s) for deletetag.
- [Pavoot Delete Tag Bulk API](https://apis.io/apis/pavoot/pavoot-deletetagbulk-api/) — The DeleteTagBulk API from Pavoot — 1 operation(s) for deletetagbulk.
- [Pavoot Delete Upload Link API](https://apis.io/apis/pavoot/pavoot-deleteuploadlink-api/) — The DeleteUploadLink API from Pavoot — 1 operation(s) for deleteuploadlink.
- [Pavoot Download Attendee Faces Zip API](https://apis.io/apis/pavoot/pavoot-downloadattendeefaceszip-api/) — The DownloadAttendeeFacesZip API from Pavoot — 1 operation(s) for downloadattendeefaceszip.
- [Pavoot Edit Logo API](https://apis.io/apis/pavoot/pavoot-editlogo-api/) — The EditLogo API from Pavoot — 1 operation(s) for editlogo.
- [Pavoot Edit Person API](https://apis.io/apis/pavoot/pavoot-editperson-api/) — The EditPerson API from Pavoot — 1 operation(s) for editperson.
- [Pavoot Edit Photographer API](https://apis.io/apis/pavoot/pavoot-editphotographer-api/) — The EditPhotographer API from Pavoot — 1 operation(s) for editphotographer.
- [Pavoot Edit Recipient API](https://apis.io/apis/pavoot/pavoot-editrecipient-api/) — The EditRecipient API from Pavoot — 1 operation(s) for editrecipient.
- [Pavoot Emit Counts API](https://apis.io/apis/pavoot/pavoot-emit-counts-api/) — The Emit Counts API from Pavoot — 1 operation(s) for emit counts.
- [Pavoot Emit Person Updated API](https://apis.io/apis/pavoot/pavoot-emit-person-updated-api/) — The Emit Person Updated API from Pavoot — 1 operation(s) for emit person updated.
- [Pavoot Emit Tagging Step API](https://apis.io/apis/pavoot/pavoot-emit-tagging-step-api/) — The Emit Tagging Step API from Pavoot — 1 operation(s) for emit tagging step.
- [Pavoot Fast API](https://apis.io/apis/pavoot/pavoot-fastapi-api/) — The FastAPI API from Pavoot — 1 operation(s) for fastapi.
- [Pavoot Find Duplicate Persons API](https://apis.io/apis/pavoot/pavoot-findduplicatepersons-api/) — The FindDuplicatePersons API from Pavoot — 1 operation(s) for findduplicatepersons.
- [Pavoot Generate Brand Folders API](https://apis.io/apis/pavoot/pavoot-generatebrandfolders-api/) — The GenerateBrandFolders API from Pavoot — 1 operation(s) for generatebrandfolders.
- [Pavoot Generate Presigned URLS API](https://apis.io/apis/pavoot/pavoot-generatepresignedurls-api/) — The GeneratePresignedUrls API from Pavoot — 1 operation(s) for generatepresignedurls.
- [Pavoot Get All Tags API](https://apis.io/apis/pavoot/pavoot-getalltags-api/) — The GetAllTags API from Pavoot — 1 operation(s) for getalltags.
- [Pavoot Get Attendee Registration Link API](https://apis.io/apis/pavoot/pavoot-getattendeeregistrationlink-api/) — The GetAttendeeRegistrationLink API from Pavoot — 1 operation(s) for getattendeeregistrationlink.
- [Pavoot Get Attendee Registration Page Layout API](https://apis.io/apis/pavoot/pavoot-getattendeeregistrationpagelayout-api/) — The GetAttendeeRegistrationPageLayout API from Pavoot — 1 operation(s) for getattendeeregistrationpagelayout.
- [Pavoot Get Effective Org Permissions API](https://apis.io/apis/pavoot/pavoot-geteffectiveorgpermissions-api/) — The GetEffectiveOrgPermissions API from Pavoot — 1 operation(s) for geteffectiveorgpermissions.
- [Pavoot Get Effective Permissions API](https://apis.io/apis/pavoot/pavoot-geteffectivepermissions-api/) — The GetEffectivePermissions API from Pavoot — 1 operation(s) for geteffectivepermissions.
- [Pavoot Get Event Organizer Image Tagging API](https://apis.io/apis/pavoot/pavoot-geteventorganizerimagetagging-api/) — The GetEventOrganizerImageTagging API from Pavoot — 1 operation(s) for geteventorganizerimagetagging.
- [Pavoot Get Event Organizer Name API](https://apis.io/apis/pavoot/pavoot-geteventorganizername-api/) — The GetEventOrganizerName API from Pavoot — 1 operation(s) for geteventorganizername.
- [Pavoot Get Face Match Suggestions API](https://apis.io/apis/pavoot/pavoot-getfacematchsuggestions-api/) — The GetFaceMatchSuggestions API from Pavoot — 1 operation(s) for getfacematchsuggestions.
- [Pavoot Get Faces API](https://apis.io/apis/pavoot/pavoot-getfaces-api/) — The GetFaces API from Pavoot — 1 operation(s) for getfaces.
- [Pavoot Get Images With Unknown Faces API](https://apis.io/apis/pavoot/pavoot-getimageswithunknownfaces-api/) — The GetImagesWithUnknownFaces API from Pavoot — 1 operation(s) for getimageswithunknownfaces.
- [Pavoot Get Organization Limits And Usage API](https://apis.io/apis/pavoot/pavoot-getorganizationlimitsandusage-api/) — The GetOrganizationLimitsAndUsage API from Pavoot — 1 operation(s) for getorganizationlimitsandusage.
- [Pavoot Get Org Brands API](https://apis.io/apis/pavoot/pavoot-getorgbrands-api/) — The GetOrgBrands API from Pavoot — 1 operation(s) for getorgbrands.
- [Pavoot Get Org Face Match Suggestions API](https://apis.io/apis/pavoot/pavoot-getorgfacematchsuggestions-api/) — The GetOrgFaceMatchSuggestions API from Pavoot — 1 operation(s) for getorgfacematchsuggestions.
- [Pavoot Get Org Orphaned Persons API](https://apis.io/apis/pavoot/pavoot-getorgorphanedpersons-api/) — The GetOrgOrphanedPersons API from Pavoot — 1 operation(s) for getorgorphanedpersons.
- [Pavoot Get Org Persons API](https://apis.io/apis/pavoot/pavoot-getorgpersons-api/) — The GetOrgPersons API from Pavoot — 1 operation(s) for getorgpersons.
- [Pavoot Get Org Potential Brand Duplicates API](https://apis.io/apis/pavoot/pavoot-getorgpotentialbrandduplicates-api/) — The GetOrgPotentialBrandDuplicates API from Pavoot — 1 operation(s) for getorgpotentialbrandduplicates.
- [Pavoot Get Org Potential Duplicates API](https://apis.io/apis/pavoot/pavoot-getorgpotentialduplicates-api/) — The GetOrgPotentialDuplicates API from Pavoot — 1 operation(s) for getorgpotentialduplicates.
- [Pavoot Get Orphaned Persons API](https://apis.io/apis/pavoot/pavoot-getorphanedpersons-api/) — The GetOrphanedPersons API from Pavoot — 1 operation(s) for getorphanedpersons.
- [Pavoot Get Person Faces API](https://apis.io/apis/pavoot/pavoot-getpersonfaces-api/) — The GetPersonFaces API from Pavoot — 1 operation(s) for getpersonfaces.
- [Pavoot Get Person Folders API](https://apis.io/apis/pavoot/pavoot-getpersonfolders-api/) — The GetPersonFolders API from Pavoot — 1 operation(s) for getpersonfolders.
- [Pavoot Get Persons API](https://apis.io/apis/pavoot/pavoot-getpersons-api/) — The GetPersons API from Pavoot — 1 operation(s) for getpersons.
- [Pavoot Get Photographers API](https://apis.io/apis/pavoot/pavoot-getphotographers-api/) — The GetPhotographers API from Pavoot — 1 operation(s) for getphotographers.
- [Pavoot Get Potential Duplicates API](https://apis.io/apis/pavoot/pavoot-getpotentialduplicates-api/) — The GetPotentialDuplicates API from Pavoot — 1 operation(s) for getpotentialduplicates.
- [Pavoot Get Project Attendee Email Template API](https://apis.io/apis/pavoot/pavoot-getprojectattendeeemailtemplate-api/) — The GetProjectAttendeeEmailTemplate API from Pavoot — 1 operation(s) for getprojectattendeeemailtemplate.
- [Pavoot Get Project Attendees API](https://apis.io/apis/pavoot/pavoot-getprojectattendees-api/) — The GetProjectAttendees API from Pavoot — 1 operation(s) for getprojectattendees.
- [Pavoot Get Project Attendee Setup API](https://apis.io/apis/pavoot/pavoot-getprojectattendeesetup-api/) — The GetProjectAttendeeSetup API from Pavoot — 1 operation(s) for getprojectattendeesetup.
- [Pavoot Get Project Custom Tag Categories API](https://apis.io/apis/pavoot/pavoot-getprojectcustomtagcategories-api/) — The GetProjectCustomTagCategories API from Pavoot — 1 operation(s) for getprojectcustomtagcategories.
- [Pavoot Get Project Face Categories API](https://apis.io/apis/pavoot/pavoot-getprojectfacecategories-api/) — The GetProjectFaceCategories API from Pavoot — 1 operation(s) for getprojectfacecategories.
- [Pavoot Get Project Filenaming Config API](https://apis.io/apis/pavoot/pavoot-getprojectfilenamingconfig-api/) — The GetProjectFilenamingConfig API from Pavoot — 1 operation(s) for getprojectfilenamingconfig.
- [Pavoot Get Project Folders API](https://apis.io/apis/pavoot/pavoot-getprojectfolders-api/) — The GetProjectFolders API from Pavoot — 1 operation(s) for getprojectfolders.
- [Pavoot Get Project Locked Photographers API](https://apis.io/apis/pavoot/pavoot-getprojectlockedphotographers-api/) — The GetProjectLockedPhotographers API from Pavoot — 1 operation(s) for getprojectlockedphotographers.
- [Pavoot Get Project Locked Tags API](https://apis.io/apis/pavoot/pavoot-getprojectlockedtags-api/) — The GetProjectLockedTags API from Pavoot — 1 operation(s) for getprojectlockedtags.
- [Pavoot Get Project Logos API](https://apis.io/apis/pavoot/pavoot-getprojectlogos-api/) — The GetProjectLogos API from Pavoot — 1 operation(s) for getprojectlogos.
- [Pavoot Get Project Organization Info API](https://apis.io/apis/pavoot/pavoot-getprojectorganizationinfo-api/) — The GetProjectOrganizationInfo API from Pavoot — 1 operation(s) for getprojectorganizationinfo.
- [Pavoot Get Project Personalized Prompt API](https://apis.io/apis/pavoot/pavoot-getprojectpersonalizedprompt-api/) — The GetProjectPersonalizedPrompt API from Pavoot — 1 operation(s) for getprojectpersonalizedprompt.
- [Pavoot Get Project Personalized Tags API](https://apis.io/apis/pavoot/pavoot-getprojectpersonalizedtags-api/) — The GetProjectPersonalizedTags API from Pavoot — 1 operation(s) for getprojectpersonalizedtags.
- [Pavoot Get Project Persons API](https://apis.io/apis/pavoot/pavoot-getprojectpersons-api/) — The GetProjectPersons API from Pavoot — 1 operation(s) for getprojectpersons.
- [Pavoot Get Project Storage API](https://apis.io/apis/pavoot/pavoot-getprojectstorage-api/) — The GetProjectStorage API from Pavoot — 1 operation(s) for getprojectstorage.
- [Pavoot Get Project Upload Link Info API](https://apis.io/apis/pavoot/pavoot-getprojectuploadlinkinfo-api/) — The GetProjectUploadLinkInfo API from Pavoot — 1 operation(s) for getprojectuploadlinkinfo.
- [Pavoot Get Recipient Images API](https://apis.io/apis/pavoot/pavoot-getrecipientimages-api/) — The GetRecipientImages API from Pavoot — 1 operation(s) for getrecipientimages.
- [Pavoot Get Recipient Projects API](https://apis.io/apis/pavoot/pavoot-getrecipientprojects-api/) — The GetRecipientProjects API from Pavoot — 1 operation(s) for getrecipientprojects.
- [Pavoot Get Recipients API](https://apis.io/apis/pavoot/pavoot-getrecipients-api/) — The GetRecipients API from Pavoot — 1 operation(s) for getrecipients.
- [Pavoot Get Share API](https://apis.io/apis/pavoot/pavoot-getshare-api/) — The GetShare API from Pavoot — 1 operation(s) for getshare.
- [Pavoot Get Shares API](https://apis.io/apis/pavoot/pavoot-getshares-api/) — The GetShares API from Pavoot — 1 operation(s) for getshares.
- [Pavoot Get Storage API](https://apis.io/apis/pavoot/pavoot-getstorage-api/) — The GetStorage API from Pavoot — 1 operation(s) for getstorage.
- [Pavoot Get Tags From Prompt API](https://apis.io/apis/pavoot/pavoot-gettagsfromprompt-api/) — The GetTagsFromPrompt API from Pavoot — 1 operation(s) for gettagsfromprompt.
- [Pavoot Get Tags From Prompt AI API](https://apis.io/apis/pavoot/pavoot-gettagsfrompromptai-api/) — The GetTagsFromPromptAI API from Pavoot — 1 operation(s) for gettagsfrompromptai.
- [Pavoot Get Text Extraction API](https://apis.io/apis/pavoot/pavoot-gettextextraction-api/) — The GetTextExtraction API from Pavoot — 1 operation(s) for gettextextraction.
- [Pavoot Get Trash Images API](https://apis.io/apis/pavoot/pavoot-gettrashimages-api/) — The GetTrashImages API from Pavoot — 1 operation(s) for gettrashimages.
- [Pavoot Get Upload Links API](https://apis.io/apis/pavoot/pavoot-getuploadlinks-api/) — The GetUploadLinks API from Pavoot — 1 operation(s) for getuploadlinks.
- [Pavoot Ignore Brand Duplicate Group API](https://apis.io/apis/pavoot/pavoot-ignorebrandduplicategroup-api/) — The IgnoreBrandDuplicateGroup API from Pavoot — 1 operation(s) for ignorebrandduplicategroup.
- [Pavoot Ignore Face Match Suggestion API](https://apis.io/apis/pavoot/pavoot-ignorefacematchsuggestion-api/) — The IgnoreFaceMatchSuggestion API from Pavoot — 1 operation(s) for ignorefacematchsuggestion.
- [Pavoot Ignore Name Duplicate Group API](https://apis.io/apis/pavoot/pavoot-ignorenameduplicategroup-api/) — The IgnoreNameDuplicateGroup API from Pavoot — 1 operation(s) for ignorenameduplicategroup.
- [Pavoot Insert Face API](https://apis.io/apis/pavoot/pavoot-insertface-api/) — The InsertFace API from Pavoot — 1 operation(s) for insertface.
- [Pavoot Internal API](https://apis.io/apis/pavoot/pavoot-internal-api/) — The Internal API from Pavoot — 2 operation(s) for internal.
- [Pavoot Invite Photographer API](https://apis.io/apis/pavoot/pavoot-invitephotographer-api/) — The InvitePhotographer API from Pavoot — 1 operation(s) for invitephotographer.
- [Pavoot Invite Recipient API](https://apis.io/apis/pavoot/pavoot-inviterecipient-api/) — The InviteRecipient API from Pavoot — 1 operation(s) for inviterecipient.
- [Pavoot Is User Active API](https://apis.io/apis/pavoot/pavoot-isuseractive-api/) — The IsUserActive API from Pavoot — 1 operation(s) for isuseractive.
- [Pavoot Match Bulk Face Names API](https://apis.io/apis/pavoot/pavoot-matchbulkfacenames-api/) — The MatchBulkFaceNames API from Pavoot — 1 operation(s) for matchbulkfacenames.
- [Pavoot Me API](https://apis.io/apis/pavoot/pavoot-me-api/) — The Me API from Pavoot — 1 operation(s) for me.
- [Pavoot Merge Brands API](https://apis.io/apis/pavoot/pavoot-mergebrands-api/) — The MergeBrands API from Pavoot — 1 operation(s) for mergebrands.
- [Pavoot Merge Persons API](https://apis.io/apis/pavoot/pavoot-mergepersons-api/) — The MergePersons API from Pavoot — 1 operation(s) for mergepersons.
- [Pavoot Org API](https://apis.io/apis/pavoot/pavoot-org-api/) — The Org API from Pavoot — 23 operation(s) for org.
- [Pavoot Photographers API](https://apis.io/apis/pavoot/pavoot-photographers-api/) — The Photographers API from Pavoot — 5 operation(s) for photographers.
- [Pavoot Project By Upload Token API](https://apis.io/apis/pavoot/pavoot-project-by-upload-token-api/) — The Project By Upload Token API from Pavoot — 1 operation(s) for project by upload token.
- [Pavoot Projects API](https://apis.io/apis/pavoot/pavoot-projects-api/) — The Projects API from Pavoot — 2 operation(s) for projects.
- [Pavoot Push Person To Brand API](https://apis.io/apis/pavoot/pavoot-pushpersontobrand-api/) — The PushPersonToBrand API from Pavoot — 1 operation(s) for pushpersontobrand.
- [Pavoot Regenerate Thumbnails API](https://apis.io/apis/pavoot/pavoot-regeneratethumbnails-api/) — The RegenerateThumbnails API from Pavoot — 1 operation(s) for regeneratethumbnails.
- [Pavoot Register Attendee API](https://apis.io/apis/pavoot/pavoot-register-attendee-api/) — The Register Attendee API from Pavoot — 1 operation(s) for register attendee.
- [Pavoot Reject Brand Duplicate Group API](https://apis.io/apis/pavoot/pavoot-rejectbrandduplicategroup-api/) — The RejectBrandDuplicateGroup API from Pavoot — 1 operation(s) for rejectbrandduplicategroup.
- [Pavoot Reject Face Match Suggestion API](https://apis.io/apis/pavoot/pavoot-rejectfacematchsuggestion-api/) — The RejectFaceMatchSuggestion API from Pavoot — 1 operation(s) for rejectfacematchsuggestion.
- [Pavoot Reject Name Duplicate Group API](https://apis.io/apis/pavoot/pavoot-rejectnameduplicategroup-api/) — The RejectNameDuplicateGroup API from Pavoot — 1 operation(s) for rejectnameduplicategroup.
- [Pavoot Remove Brand From Project API](https://apis.io/apis/pavoot/pavoot-removebrandfromproject-api/) — The RemoveBrandFromProject API from Pavoot — 1 operation(s) for removebrandfromproject.
- [Pavoot Remove Images From Folder API](https://apis.io/apis/pavoot/pavoot-removeimagesfromfolder-api/) — The RemoveImagesFromFolder API from Pavoot — 1 operation(s) for removeimagesfromfolder.
- [Pavoot Rename Custom Tag Option API](https://apis.io/apis/pavoot/pavoot-renamecustomtagoption-api/) — The RenameCustomTagOption API from Pavoot — 1 operation(s) for renamecustomtagoption.
- [Pavoot Restore Images API](https://apis.io/apis/pavoot/pavoot-restoreimages-api/) — The RestoreImages API from Pavoot — 1 operation(s) for restoreimages.
- [Pavoot Reviews API](https://apis.io/apis/pavoot/pavoot-reviews-api/) — The Reviews API from Pavoot — 5 operation(s) for reviews.
- [Pavoot Revoke Photographer Project Access API](https://apis.io/apis/pavoot/pavoot-revokephotographerprojectaccess-api/) — The RevokePhotographerProjectAccess API from Pavoot — 1 operation(s) for revokephotographerprojectaccess.
- [Pavoot Scan All Faces For Matches API](https://apis.io/apis/pavoot/pavoot-scanallfacesformatches-api/) — The ScanAllFacesForMatches API from Pavoot — 1 operation(s) for scanallfacesformatches.
- [Pavoot Scan Existing Faces For Person API](https://apis.io/apis/pavoot/pavoot-scanexistingfacesforperson-api/) — The ScanExistingFacesForPerson API from Pavoot — 1 operation(s) for scanexistingfacesforperson.
- [Pavoot Scan Org Faces For Matches API](https://apis.io/apis/pavoot/pavoot-scanorgfacesformatches-api/) — The ScanOrgFacesForMatches API from Pavoot — 1 operation(s) for scanorgfacesformatches.
- [Pavoot Scan Unknown Faces For Matches API](https://apis.io/apis/pavoot/pavoot-scanunknownfacesformatches-api/) — The ScanUnknownFacesForMatches API from Pavoot — 1 operation(s) for scanunknownfacesformatches.
- [Pavoot Search Images API](https://apis.io/apis/pavoot/pavoot-searchimages-api/) — The SearchImages API from Pavoot — 1 operation(s) for searchimages.
- [Pavoot Send Attendee Emails API](https://apis.io/apis/pavoot/pavoot-sendattendeeemails-api/) — The SendAttendeeEmails API from Pavoot — 1 operation(s) for sendattendeeemails.
- [Pavoot Send To Recipient API](https://apis.io/apis/pavoot/pavoot-sendtorecipient-api/) — The SendToRecipient API from Pavoot — 1 operation(s) for sendtorecipient.
- [Pavoot Set Attendee Email Approval API](https://apis.io/apis/pavoot/pavoot-setattendeeemailapproval-api/) — The SetAttendeeEmailApproval API from Pavoot — 1 operation(s) for setattendeeemailapproval.
- [Pavoot Set Attendee Registration Page Layout API](https://apis.io/apis/pavoot/pavoot-setattendeeregistrationpagelayout-api/) — The SetAttendeeRegistrationPageLayout API from Pavoot — 1 operation(s) for setattendeeregistrationpagelayout.
- [Pavoot Set Photographer Lock API](https://apis.io/apis/pavoot/pavoot-setphotographerlock-api/) — The SetPhotographerLock API from Pavoot — 1 operation(s) for setphotographerlock.
- [Pavoot Set Project Attendee Email Template API](https://apis.io/apis/pavoot/pavoot-setprojectattendeeemailtemplate-api/) — The SetProjectAttendeeEmailTemplate API from Pavoot — 1 operation(s) for setprojectattendeeemailtemplate.
- [Pavoot Set Project Attendee Setup API](https://apis.io/apis/pavoot/pavoot-setprojectattendeesetup-api/) — The SetProjectAttendeeSetup API from Pavoot — 1 operation(s) for setprojectattendeesetup.
- [Pavoot Share Images With Recipient API](https://apis.io/apis/pavoot/pavoot-shareimageswithrecipient-api/) — The ShareImagesWithRecipient API from Pavoot — 1 operation(s) for shareimageswithrecipient.
- [Pavoot Shares API](https://apis.io/apis/pavoot/pavoot-shares-api/) — The Shares API from Pavoot — 5 operation(s) for shares.
- [Pavoot Train Logo API](https://apis.io/apis/pavoot/pavoot-trainlogo-api/) — The TrainLogo API from Pavoot — 1 operation(s) for trainlogo.
- [Pavoot Unshare Images With Recipient API](https://apis.io/apis/pavoot/pavoot-unshareimageswithrecipient-api/) — The UnshareImagesWithRecipient API from Pavoot — 1 operation(s) for unshareimageswithrecipient.
- [Pavoot Update All Projects Filenaming Config API](https://apis.io/apis/pavoot/pavoot-updateallprojectsfilenamingconfig-api/) — The UpdateAllProjectsFilenamingConfig API from Pavoot — 1 operation(s) for updateallprojectsfilenamingconfig.
- [Pavoot Update Folder Name API](https://apis.io/apis/pavoot/pavoot-updatefoldername-api/) — The UpdateFolderName API from Pavoot — 1 operation(s) for updatefoldername.
- [Pavoot Update Images Photographer API](https://apis.io/apis/pavoot/pavoot-updateimagesphotographer-api/) — The UpdateImagesPhotographer API from Pavoot — 1 operation(s) for updateimagesphotographer.
- [Pavoot Update Image Title API](https://apis.io/apis/pavoot/pavoot-updateimagetitle-api/) — The UpdateImageTitle API from Pavoot — 1 operation(s) for updateimagetitle.
- [Pavoot Update Logo Transcription API](https://apis.io/apis/pavoot/pavoot-updatelogotranscription-api/) — The UpdateLogoTranscription API from Pavoot — 1 operation(s) for updatelogotranscription.
- [Pavoot Update Project API](https://apis.io/apis/pavoot/pavoot-updateproject-api/) — The UpdateProject API from Pavoot — 1 operation(s) for updateproject.
- [Pavoot Update Project Custom Tag Categories API](https://apis.io/apis/pavoot/pavoot-updateprojectcustomtagcategories-api/) — The UpdateProjectCustomTagCategories API from Pavoot — 1 operation(s) for updateprojectcustomtagcategories.
- [Pavoot Update Project Filenaming Config API](https://apis.io/apis/pavoot/pavoot-updateprojectfilenamingconfig-api/) — The UpdateProjectFilenamingConfig API from Pavoot — 1 operation(s) for updateprojectfilenamingconfig.
- [Pavoot Update Project Locked Photographers API](https://apis.io/apis/pavoot/pavoot-updateprojectlockedphotographers-api/) — The UpdateProjectLockedPhotographers API from Pavoot — 1 operation(s) for updateprojectlockedphotographers.
- [Pavoot Update Project Locked Tags API](https://apis.io/apis/pavoot/pavoot-updateprojectlockedtags-api/) — The UpdateProjectLockedTags API from Pavoot — 1 operation(s) for updateprojectlockedtags.
- [Pavoot Update Project Personalized Prompt API](https://apis.io/apis/pavoot/pavoot-updateprojectpersonalizedprompt-api/) — The UpdateProjectPersonalizedPrompt API from Pavoot — 1 operation(s) for updateprojectpersonalizedprompt.
- [Pavoot Update Project Personalized Tags API](https://apis.io/apis/pavoot/pavoot-updateprojectpersonalizedtags-api/) — The UpdateProjectPersonalizedTags API from Pavoot — 1 operation(s) for updateprojectpersonalizedtags.
- [Pavoot Update Share API](https://apis.io/apis/pavoot/pavoot-updateshare-api/) — The UpdateShare API from Pavoot — 1 operation(s) for updateshare.
- [Pavoot Update Tag API](https://apis.io/apis/pavoot/pavoot-updatetag-api/) — The UpdateTag API from Pavoot — 1 operation(s) for updatetag.
- [Pavoot Update Tag Bulk API](https://apis.io/apis/pavoot/pavoot-updatetagbulk-api/) — The UpdateTagBulk API from Pavoot — 1 operation(s) for updatetagbulk.
- [Pavoot Update Upload Link API](https://apis.io/apis/pavoot/pavoot-updateuploadlink-api/) — The UpdateUploadLink API from Pavoot — 1 operation(s) for updateuploadlink.
- [Pavoot Upload Link By Token API](https://apis.io/apis/pavoot/pavoot-upload-link-by-token-api/) — The Upload Link By Token API from Pavoot — 1 operation(s) for upload link by token.
- [Pavoot Upsert Project Attendee API](https://apis.io/apis/pavoot/pavoot-upsertprojectattendee-api/) — The UpsertProjectAttendee API from Pavoot — 1 operation(s) for upsertprojectattendee.
- [Pavoot Add Project API](https://apis.io/apis/pavoot/pavoot-add-project-api/) — The Add Project API from Pavoot — 1 operation(s) for add project.
- [Pavoot Create Multipart Upload API](https://apis.io/apis/pavoot/pavoot-create-multipart-upload-api/) — The Create Multipart Upload API from Pavoot — 1 operation(s) for create multipart upload.
- [Pavoot Create Share Link API](https://apis.io/apis/pavoot/pavoot-create-share-link-api/) — The Create Share Link API from Pavoot — 1 operation(s) for create share link.
- [Pavoot Delete Project API](https://apis.io/apis/pavoot/pavoot-delete-project-api/) — The Delete Project API from Pavoot — 1 operation(s) for delete project.
- [Pavoot Generate Download Url API](https://apis.io/apis/pavoot/pavoot-generate-download-url-api/) — The Generate Download Url API from Pavoot — 1 operation(s) for generate download url.
- [Pavoot Generate Thumbnail API](https://apis.io/apis/pavoot/pavoot-generate-thumbnail-api/) — The Generate Thumbnail API from Pavoot — 1 operation(s) for generate thumbnail.
- [Pavoot Get Images API](https://apis.io/apis/pavoot/pavoot-get-images-api/) — The Get Images API from Pavoot — 1 operation(s) for get images.
- [Pavoot Get Projects API](https://apis.io/apis/pavoot/pavoot-get-projects-api/) — The Get Projects API from Pavoot — 1 operation(s) for get projects.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Pavoot MCP server (candidate — not published by Pavoot)](https://apis.io/servers/pavoot/pavoot-mcp-server-candidate-not-published-by-pavoot/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Pavoot Api Overlay](https://apis.io/overlays/pavoot/pavoot-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Pavoot Authentication](https://apis.io/security/pavoot/pavoot-authentication/)
- [Pavoot Domain Security](https://apis.io/security/pavoot/pavoot-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Pavoot Scopes](https://apis.io/scopes/pavoot/pavoot-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Pavoot Plans Pricing](https://apis.io/plans/pavoot/pavoot-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Pavoot Rate Limits](https://apis.io/rate-limits/pavoot/pavoot-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://pavoot.com)
- [Terms of service](https://pavoot.com/client/gtc)
- [Privacy policy](https://pavoot.com/privacy)

## API Evangelist rating

**Kin Score 33.8** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 39.0 |
| Contract governance | 4.5 |
| Operational transparency | 0.0 |
| Developer ergonomics | 25.6 |
| Access clarity | 27.6 |

**Agent readiness 34.6** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 34.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/pavoot/](https://apis.io/providers/pavoot/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Pavoot: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/pavoot/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
