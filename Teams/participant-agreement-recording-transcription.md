---
layout: Conceptual
title: Manage participant agreement for recording and transcription - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/participant-agreement-recording-transcription
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Manage participant agreement for recording and transcription
author: dj1298
manager: adam
ms.author: djball
ms.service: msteams
ms.topic: article
ms.date: 2026-05-05T00:00:00.0000000Z
locale: en-us
document_id: 09df1b58-170b-1686-9325-9350e6b0d208
document_version_independent_id: 09df1b58-170b-1686-9325-9350e6b0d208
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/participant-agreement-recording-transcription.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: participant-agreement-recording-transcription
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/participant-agreement-recording-transcription.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 06bb1c15-c2d6-7806-f5c7-9ce2e4210e71
---

# Manage participant agreement for recording and transcription - Microsoft Teams | Microsoft Learn

You can use the Teams admin center or PowerShell to manage whether meetings created by organizers with this assigned policy can require participants to provide explicit consent to be recorded and transcribed. This policy also applies to channel meetings.

When the recording agreement policy is turned on, in meetings that aren't set to auto-record, once a user either starts the meeting recording, transcription, or both, all other participants are muted, with their cameras and content-share off. The user who initiates recording or transcription is considered to have given consent and remains unmuted. In auto-recorded meetings, everyone who joins is muted with their cameras off. When a participant decides to un-mute, turn on their camera, or share content, they’re asked to respond **'Yes'** or **'No'** to consent to be included in the meeting recording and transcription. If a participant responds **'No'** to the question, they have a view-only meeting experience. View-only participants can't start recording or transcription for any meetings that require explicit consent.

The consent choice for each participant is included in the attendance report. Participants who aren't in the attendance report—due to the admin policy or opting out—are required to provide consent. When the attendance report is disabled or participants aren't in the attendance report, organizers and co-organizers don't see consent data. However, as an admin, you can still see consent data in the audit logs.

### Manage recording consent

You can use the Teams admin center or the **`-ExplicitRecordingConsent`** parameter in the [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet to manage recording consent. This parameter also manages recording consent for Audio Conferencing. To learn about recording consent for Audio Conferencing, see [Explicit recording consent for Audio Conferencing](conferencing-recording-consent).

To manage this feature using PowerShell, see the [PowerShell section](meeting-recording#manage-whether-meetings-require-participant-agreement-for-recording-and-transcription) in this article.

The following table shows the behaviors of the settings for explicit consent:

| Teams admin center value | PowerShell value | Behavior |
| --- | --- | --- |
| On | Enabled | For organizers with this policy, all their meetings require participants to provide consent to be recorded and transcribed. |
| Off | Disabled | **This setting is the default value.** For organizers with this policy, participants aren't asked for consent to be recorded and transcribed. All participants are included in recordings and transcripts from these organizers' meetings. |

To manage recording consent for your organization in the Teams admin center, follow these steps:

1. Open the Teams admin center.
2. Expand **Meetings** from the navigation pane.
3. Under **Meetings**, select **Meeting Policies**.
4. Either select an existing policy or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the **Global policy**. To exclude certain users from the global policy, create and assign a custom meeting policy.
5. Within your chosen policy, navigate to the **Recording & Transcription** section.
6. Toggle the **Require participant agreement for recording and transcription** setting **On** or **Off**.
7. Select **Save**.
8. To assign the policy:
    - **To specific users**: Select your policy &gt; select **Manage users** &gt; **Assign users** &gt; enter in the search bar the names of specific users and select **Add** &gt; select **Apply**.
    - **To groups**: Select **Group policy assignment** &gt; select **Add** &gt; enter the group's name and enter the policy's name &gt; select **Apply**.

### View consent data

There are two ways for you to view consent data. The first way is in the [Teams meeting attendance and engagement report](/en-us/microsoftteams/teams-analytics-and-reports/meeting-attendance-report). The second is with the **Added information about meeting participants** filter in the Teams meeting audit logs in Purview. Consent data is in the audit logs regardless of your policy that manages the attendance and engagement report or your users' option for tracking attendance. To learn more about audit logs in Purview, see [Audit log activities](/en-us/purview/audit-log-activities#microsoft-teams-activities).

[![Screenshot of Teams meeting audit logs in Purview that show consent data.](media/audit-rec-small.png)](media/audit-rec-expand.png#lightbox)

### Supported and unsupported endpoints and platforms

#### Auto consent endpoints and platforms

The following user types are auto consented for recording and transcription without any participant interaction. They get a consent notification, and their consent data is logged as 'not applicable' or 'auto consent':

- Teams Rooms on Android
- Teams Rooms on Windows
- Third party video conferencing devices via Cloud Video Interop (CVI)
- Third party video conferencing devices connecting via Direct Guest Join (DGJ)
- PSTN endpoints in 1:1 calls

#### Supported endpoints and platforms

Explicit consent is supported on the following endpoints:

- Mobile Teams (Android and iOS)
- Meeting participants dialing in using [Audio Conferencing](conferencing-recording-consent)
- PSTN endpoints in meetings and group calls
- Shared devices
- Teams native Mac
- Teams native Windows
- Teams Phone devices (including audio conferencing phone devices) **Note that** for 1:1 calls, device must be updated to the latest application version. For details, refer to MC1216032 in the Message Center.
- Teams Web
- VDI

#### Unsupported endpoints and platforms

In meetings requiring explicit consent, users joining from unsupported endpoints have the view-only experience. Explicit consent isn’t supported on the following endpoints, along with any endpoints not listed under supported endpoints:

- CarPlay
- Old version native clients
- Teams Displays