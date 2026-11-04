---
layout: Conceptual
title: Overview and configuration of voice and face enrollment - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/voice-and-face-recognition
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: elaineho
ms.date: 2026-11-04T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: concept-article
audience: admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-consoles
- Tier1
- magic-ai-copilot
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
ms.custom: QuickDraft
description: Learn how admins can manage and control voice and face enrollment in Microsoft Teams to ensure data privacy and a better user experience.
locale: en-us
document_id: 1fc69e68-81e9-cd96-b6b2-a34d54e2b333
document_version_independent_id: 1fc69e68-81e9-cd96-b6b2-a34d54e2b333
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/voice-and-face-recognition.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/voice-and-face-recognition
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/voice-and-face-recognition.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2624a017-7337-44fa-9494-a407bb0e59fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/a438284e-c3c3-4c36-ab0b-aa7c244b912c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 477c5075-7f37-ef8d-366f-0d28a5eebf92
---

# Overview and configuration of voice and face enrollment - Microsoft Teams | Microsoft Learn

Voice and face recognition is a feature in Microsoft Teams Enterprise that allows users to create a voice and face profile that enables them to be identified during certain Teams meetings. Depending on their Enterprise administrator settings, a user can create their voice and face profile by "express enrollment" using their voice and images and videos of their face from Teams meetings or by "active enrollment" of their voice and face via a manual experience in their Recognition settings.

If users opt to expressly enroll their voice and face profile from Teams meetings, that data will be collected on an ongoing basis and will be used to improve the audio quality and user experience of Teams meetings and calls. The recognition feature helps to reduce background noise and secondary speakers and provides speaker attribution and Microsoft Copilot accuracy in meeting rooms equipped with Microsoft Teams Rooms devices. Enterprise administrators and security teams can manage and control the availability of this feature for their users, including which users can choose express enrollment and which users can choose active enrollment.

Users have full control over their voice and face data. Where express enrollment is available to a user, they can still choose to use active enrollment. Users can also opt out of voice and face recognition at any time through their desktop client. If Enterprise administrators disable enrollment after the user enrolled, the user still has the ability to opt out after. See [Create your Microsoft Teams recognition profile](https://support.microsoft.com/teams/calls-devices/create-your-microsoft-teams-recognition-profile).

This article covers:

- Enrollment process: Users can use either the active or express enrollment process to get started.
- Data retention: The duration that Microsoft Teams keeps the voice and face profiles of users.
- Admin settings: Enterprise administrators can turn on or off voice and face enrollment for specific users, groups of users, or the whole organization. They can configure the feature using PowerShell.
- Data export: Data export is managed directly by end users.
- Frequently asked questions: Common questions and answers.

By providing detailed information on how Microsoft Teams stores and handles user data, this article aims to ensure peace of mind and control for IT admins, security teams, and legal teams.

Microsoft doesn't use the voice and face profiles of users to train any models or for any other purposes other than providing the voice and face recognition feature in Microsoft Teams.

## Step 1: Enable voice and face enrollment

If Enterprise administrators have enabled enrollment, users can opt to enroll their voice and face to create their voice and face profile. For users who are already enrolled, they can update their voice and face profile by redoing their express enrollment or using active enrollment (if available) to make their experience even better.

Enrollment starts in the Teams app: users go to **Settings** &gt; **Recognition** and, depending on how their Enterprise administrator has enabled the feature for them, opt in to either express enrollment or active enrollment. For express enrollment, opt-in allows the Teams app to automatically capture users' voice data from Teams meetings and create and update their voice profile via their in-meeting speech. Generating a voice profile using in-meeting speech typically takes a couple of meetings. If the user needs to generate their voice profile more quickly, they always have the option to use express enrollment and manually submit their voice in their Recognition settings.

Users can delete their voice and face profile at any time using the Teams desktop app, even if their Enterprise administrator has turned off enrollment after they enrolled.

### Supported enrollment languages

The language of the installed Teams app determines the available languages that a user can use to enroll their voice. There's no language requirement for face enrollment. The following localized versions are supported:

- en-us
- en-gb
- en-ca
- en-in
- en-au
- en-nz
- ar-sa
- da-dk
- de-de
- es-es
- es-mx
- fi-fi
- fr-ca
- fr-fr
- it-it
- ja-jp
- ko-kr
- nb-no
- nl-nl
- pl-pl
- pt-br
- ru-ru
- sv-se
- zh-cn
- zh-tw

If the language you're looking for isn't supported for enrolling your voice, Microsoft is currently exploring fallback options.

## Data retention

When a user is enrolled in the feature and has an active Teams account, Microsoft, on behalf of the user's organization, retains their voice and face profiles in accordance with the following retention policies. The user’s voice and face profile is removed right away if the user unenrolls from the feature. If users leave their organization, their data is deleted according to the organization's data retention policy. If the organization deletes the user's Teams account, the user's voice and face profile is removed within 90 days of the Teams account being deleted. In addition, a voice and face profile that isn't used for one year is removed automatically. Once a voice or face profile has been removed, the user must enroll again if they want to use the features.

If users enroll their voice or face profile, they can always choose to unenroll it later, even if their organization no longer allows enrollment.

If users enroll via active enrollment, the audio, images, and videos submitted during active enrollment are retained for one year. If users enroll via express enrollment, Teams audio and video used to create voice and face profiles aren't retained after the end of the Teams call.

When a user also uses Voice Isolation on their device, a local copy of the voice profile is stored encrypted. This copy of the voice profile expires after 14 days and is replaced with a new copy of the voice profile. If users leave the organization, the customer data is deleted accordingly with the customer's data retention policy.

## Step 2: Manage enrollment settings

Connect to PowerShell and ensure you're running the latest version. For detailed instructions and the update command, see the [Install Microsoft Teams PowerShell](/en-us/microsoftteams/teams-powershell-install) article.

Enterprise administrators can manage voice and face enrollment by using the `CsTeamsAIPolicy`. You can access this policy only through Microsoft PowerShell. It replaces the previous `EnrollUserOverride` setting in `CsTeamsMeetingPolicy`.

The new policy includes three distinct settings which are enabled by default:

| Parameter | Description |
| --- | --- |
| EnrollVoice | Allows users to manually create and manage their voice profiles via the Recognition settings for speaker identification, transcription, and voice isolation. |
| EnrollFace | Allows users to manually create and manage their face profiles via their Recognition settings for facial identification in meetings using supported cameras. |
| PassiveVoiceEnrollment | Allows users to create their voice profiles via their voice data from Teams meetings for speaker identification, transcription, and voice isolation. |

Enterprise administrators can turn on or off use of voice and face recognition and voice and face enrollment for specific users or groups using the Teams AI Policy. By default, voice and face recognition is available and enrollment is enabled for all users in the organization. Enterprise administrators can change the states of these parameters using PowerShell. Organizations with any of the preceding parameters enabled means the corresponding functionality is made accessible for the user. **Even if the feature is available, users still need to opt in to enroll their voice and face and create their voice and face profile before they can start using voice and face recognition**. See [Set-CsTeamsAIPolicy](/en-us/powershell/module/microsoftteams/set-csteamsaipolicy) and [New-CsTeamsAIPolicy](/en-us/powershell/module/microsoftteams/new-csteamsaipolicy) for specific guidance on policy creation and assignment.

To allow only active enrollment via manual submission of voice and face data from the Recognition settings for all users in your organization:

```Powershell
Set-CsTeamsAIPolicy -Identity Global -EnrollVoice Enabled -EnrollFace Enabled
```

To enable express voice enrollment from the Recognition settings and apply to all users in your organization:

```Powershell
Set-CsTeamsAIPolicy -Identity Global -PassiveVoiceEnrollment Enabled
```

To disable active voice and face enrollment for specific users, Enterprise administrators can create and assign a custom meeting policy to the users:

```Powershell
New-CsTeamsAIPolicy -Identity DisableEnrollment -EnrollVoice Disabled -EnrollFace Disabled
Grant-CsTeamsAIPolicy -Identity DisableEnrollment -Identity testuser@test.onmicrosoft.com 
```

For detailed guidance on how to configure and manage these settings, including more parameters and examples, see the [Set-CsTeamsAIPolicy (MicrosoftTeamsPowerShell)](/en-us/powershell/module/teams/set-csteamsaipolicy) documentation.

The `CsTeamsAIPolicy` also includes the configuration for Voice Isolation `-VoiceIsolation`. Learn more in [Manage voice isolation](/en-us/microsoftteams/voice-isolation).

## Step 3: Enable recognition in Teams Rooms

To provide granular controls for Enterprise administrators, there's a separate configuration to allow Teams Rooms to utilize user voice and face profiles to identify who is in a meeting room. See [Enable People Recognition on Teams Rooms](/en-us/MicrosoftTeams/rooms/teams-rooms-people-recognition) to learn how to enable recognition.

## Export active enrollment data

Data exports are available only to users who have enrolled their voice and face via active enrollment. These users can follow these steps to export their data:

1. Go to **Settings** &gt; **Recognition**.
2. Select **Export** to download your voice or face data. The data is saved directly to your device's Downloads folder.

*Exporting your voice data*

- For users who used active enrollment to submit their voice manually via the Recognition settings, an audio recording is available for exporting after active enrollment is complete.
- For users enrolling their voice using express enrollment, their audio data from Teams calls isn't retained as this data is processed only during the course of the call and not retained after the end of the call. As such, there's no data to export and the **Export** button doesn't appear next to their voice profile.

*Exporting your face profile*

- For users actively enrolling their face profile manually via the Recognition settings, the user's images captured to generate the face profile are available for exporting after active enrollment is complete.

## Manage enrollment data in Teams admin center

Enterprise administrators can now use **Teams admin center** to view end-user **voice and face enrollment status** and manage enrolled data directly from the admin experience.

This new experience helps Enterprise administrators better understand readiness for features that depend on enrollment, such as:

- **Speaker attribution**
- **Voice isolation**
- **Face-based room experiences**

Enterprise administrators can also **delete end-user voice and face profiles and enrollment data directly from the Teams admin center**. If profiles and enrollment data are deleted, the user must complete enrollment again to continue using features that rely on that profile data.

Enterprise administrators **can't export end-user voice or face enrollment data from the Teams admin center**. Export of enrollment data remains under the **end user's control** and within the user experience.

This capability does **not change default feature availability and enrollment behavior**. Existing policies and end-user controls for voice and face recognition and enrollment remain the same.

## Frequently asked questions

**Regarding the user's voice enrollments, where do you store the data?**

> 
> Voice data is stored in the Office 365 trusted compliance store.

**Can both users and Enterprise administrators control the data being saved?**

> 
> Only the end user can export their data. Users can unenroll and remove their profile from the Teams app.

**For how long do you keep the data?**

> 
> Microsoft retains enrollment data for actively used voice and face profiles for one year. Users' data is deleted if not used for one year. Additionally, enrollment data is deleted right away if the user unenrolls from the feature and, if they leave their organization, in accordance with their organization's data retention policy. If the organization deletes the user's Teams account, the user's enrollment data and voice and face profile is removed within 90 days of the Teams account being deleted.

**How is data stored and processed for cross tenants?**

> 
> We don't support getting data cross-tenant. We only retrieve data for their tenant only.

**Are voice and face enrollments available in GCCH and DOD?**

> 
> No, voice and face enrollments are currently available only up to GCC and aren't available in GCCH or DOD environments.

**Can Enterprise administrators download end users' voice and face data?**

> 
> No, data export is managed directly by end users. Admins don't have access to export voice and face data, giving users full control over their face and voice data and profiles.

**Can Enterprise administrators manage voice and face enrollment data in the Teams admin center?**

> 
> Yes. Admins can now use the **Teams admin center** to view enrollment status and delete end-user **voice and face enrollment data and profiles** directly from the Teams admin center. If a profile is deleted, the user must re-enroll to continue using experiences that depend on it.

**Can Enterprise administrators export end-user voice or face profiles or enrollment data from the Teams admin center?**

> 
> No. Admins can't export end-user voice or face profiles or enrollment data from the Teams admin center. Export capability remains with the **end user**.

**Why does voice enrollment fail with errors like “Couldn't capture your voice”?**

> 
> This can be caused by network restrictions blocking required Microsoft speech service endpoints. Ensure the following endpoint is allow-listed:

- `*.speech.microsoft.com`

For more information, see [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges).