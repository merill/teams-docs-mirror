---
layout: Conceptual
title: Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/tmr-meeting-recording-change
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
ms.reviewer: yudma, yujin1, lisma, ritikag
ms.date: 2026-09-23T00:00:00.0000000Z
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: meetings
search.appverid: MET150
description: Learn about how meeting recordings are stored in OneDrive and SharePoint, and permissions.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
locale: en-us
document_id: 05552174-1baa-6c4f-14fe-42b8ef1ff394
document_version_independent_id: 05552174-1baa-6c4f-14fe-42b8ef1ff394
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/tmr-meeting-recording-change.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: tmr-meeting-recording-change
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/tmr-meeting-recording-change.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 19d1c8af-e1af-cd4b-c635-0e2c9470a635
---

# Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Calls

Note

When organizers turn off Microsoft Copilot in Teams meetings and events, recording and transcription are also turned off. To learn more about Copilot, see [Manage Microsoft Copilot in Teams meetings and events](copilot-teams-transcription).

When users in your organization record and transcribe Teams meetings, the recordings and transcripts are stored in either OneDrive for work or school and SharePoint. Depending on where your users access the file, the recording plays on the video player in OneDrive or SharePoint. This article helps you, as an admin, understand recording and transcript storage and permissions for OneDrive and SharePoint.

To learn about your recording policies, see [Teams meeting recording](meeting-recording). To learn how to block the download of Teams meeting recording files from SharePoint or OneDrive, see [Block the download of Teams meeting recording files from SharePoint or OneDrive](block-download-meeting-recording).

## Recording storage

### Meetings and events

For **meetings and events**, the recording saves to the organizer's OneDrive, even if the organizer didn't attend the meeting or event. All recording files are saved to the organizer's OneDrive **Recordings** folder. Co-organizers have the same editing permissions as organizers for recording files. To understand what happens if an organizer doesn't have a OneDrive account, see the **Recording storage for organizers without OneDrive accounts** section in this article. This behavior applies to the following types of meeting and events:

- Automatically recorded meetings
- Delegate-created meetings
- Manually recorded meetings
- Meet now meetings
- Meetings scheduled in Outlook
- Meetings scheduled in the Teams client
- Recurring meetings
- Teams events

#### Delegate-created meetings

For meetings in which an organizer appoints a **delegate** who has permission to act on the organizer's behalf, all recording files are automatically saved to the organizer's **Recordings** folder in OneDrive. When delegates are added as co-organizers, they have the same editing permissions as organizers for recording files.

### 1:1 and group calls

For 1-1 call and group calls, recording files go to the OneDrive account of the user who selected **Record**.

### Channel meetings

For **Channel meetings**, the recording is stored in the SharePoint Teams site documentation library in a folder named **Recordings**. For example: *Teams name - Channel name*/**Documents**/**Recordings**.

### Shared mailbox scheduled meetings

For **meetings scheduled using a shared mailbox**, the shared mailbox is considered the organizer. If the shared account has a OneDrive, the recording is uploaded there. However, since shared mailboxes typically don't have a OneDrive, the recordings are uploaded to the co-organizer's or recording initiator's OneDrive instead. To understand what happens if an organizer doesn't have a OneDrive account, see the **Recording storage for organizers without OneDrive accounts** section in this article.

For details on shared mailboxes, see [About shared mailboxes - Microsoft 365 admin](/en-us/microsoft-365/admin/email/about-shared-mailboxes).

### Video on Demand (VOD)

When organizers record events, the recordings are stored in OneDrive. When an organizer uses VOD to publish event recordings, the recordings are stored in SharePoint Embedded File Storage Containers.

For events [optimized for large audiences](plan-events) such as town halls, only the event organizer can manage recordings of past events in their calendar.

Note

As an admin, although you can find the event recording in the SharePoint Embedded Container, you can only delete the recording in the Teams admin center.

To learn more about SharePoint Embedded File Storage Containers, see [Overview of SharePoint Embedded](/en-us/sharepoint/dev/embedded/overview).

#### Delete a VOD event recording

1. In the left navigation of the Teams admin center, go to **Analytics and reports** &gt; **Usage reports**.
2. On the **View reports** tab, under **Report**, choose **Teams events usage reports**.
3. In the table, find the event that you want to delete the recording for and select the row. The names of recordings follow this pattern of *'Teams Virtual Event VOD Container evt\_{EventId}rec{RecordingId}'*.
4. Select **Delete event data**.

To learn more about VOD, see [Manage VOD publishing for events](manage-vod-publishing).

### Microsoft Teams Rooms meetings

For **Microsoft Teams Rooms meetings**, when a user creates a meeting using the **Meet now** button in a Teams Room, the Teams Room itself becomes the meeting organizer. By default, the recording is stored in the Teams Room's OneDrive account, if available. However, none of the meeting participants have full permissions to the file. To give meeting participants full permissions to the recording file, avoid assigning a OneDrive license to your Teams Room's resource account.

When a Teams Room's resource account doesn't have a OneDrive license and storage, the recording gets saved to the co-organizer's or recording initiator's OneDrive. For details on what happens if a co-organizer or recording doesn't have a OneDrive account, see the **Recording storage for organizers without OneDrive accounts** section in this article.

To learn more about Microsoft Teams Rooms meetings, see [Microsoft Teams Rooms (Windows)](https://support.microsoft.com/office/microsoft-teams-rooms-windows-e667f40e-5aab-40c1-bd68-611fe0002ba2).

### Recording storage for organizers without OneDrive accounts

When the organizer doesn't have a OneDrive account, here's what happens, in order, to the meeting recording:

1. The recording is saved to the co-organizer's OneDrive, while the meeting or event organizer retains permissions to edit and share the recording. When there are multiple co-organizers, the recording saves to the co-organizers' OneDrive according to order of co-organizers in meeting options.

    For example, if you open meeting option page and see three co-organizers:

    `co-organizer 1`, `co-organizer 2`, `co-organizer 3`

    In this example, the recording is saved to co-organizer 1's OneDrive account. If co-organizer 1 doesn't have a OneDrive account, the recording is saved to co-organizer 2's OneDrive. If co-organizer 2 also doesn't have a OneDrive account, the recording is then saved to co-organizer 3's OneDrive.
2. If none of the co-organizers have OneDrive accounts, the recording is saved to the OneDrive account of the user who initiated the recording.
3. If the user who initiated the recording doesn't have a OneDrive, the recording gets temporarily stored to async media storage.

### Async media storage

If a Teams meeting recording fails to successfully upload to OneDrive because the organizer, co-organizers, and recording initiator don't have OneDrive accounts, or the storage quota is full, an error message appears. The recording is instead temporarily saved to async media storage. Once the recording is in async media storage, no retry attempts are made to automatically upload the recording to OneDrive or SharePoint. During that time, the organizer must download the recording. The organizer can try to upload the recording again if they get a OneDrive or SharePoint license, or clear some space in their storage quota. If not downloaded within 21 days, the recording is deleted.

### Videos

Videos are just like any other file in OneDrive and SharePoint. Handling ownership and retention after someone leaves follows the standard [OneDrive and SharePoint process](/en-us/onedrive/retention-and-deletion).

### Retention labels

To learn how to apply retention labels to Teams meeting recordings, see [How to auto-apply a retention label](/en-us/microsoft-365/compliance/apply-retention-labels-automatically).

### Planning for storage

The size of a one-hour recording is 400 MB. Make sure you understand the capacity required for recorded files and have sufficient storage available in OneDrive and SharePoint. Read [Set the default storage space for OneDrive](/en-us/sharepoint/set-default-storage-space) and [Manage SharePoint site storage limits](/en-us/sharepoint/manage-site-collection-storage-limits) to understand the base storage included in the subscription and how to purchase more storage.

## Viewing permissions

For **non-Channel meetings**:

- All meeting invitees, except for external participants, automatically get a personally shared link. The meeting organizer must add external participants to the shared list.
- If the meeting is forwarded, only participants who are automatically added to the meeting chat thread receive the recording link.
- For optimal performance, the total number of users in a chat shouldn't exceed 1,000.
- If a meeting is forwarded to a group, only some users are added to the chat. If forwarded to an individual user, they're added to the meeting chat unless there are more than 1,000 users in the chat.
- For **large meetings** with more than 2,000 participants, some participants may not automatically receive permissions to the recording file. Participants without access can ask the recording owner to add them to the shared list.

For **Channel meetings**, permissions are inherited from the owners and members list in the channel.

## Recording quotas

Teams meeting recording files live in OneDrive and SharePoint and are included in your quota for those services. To learn more, see [SharePoint quota](/en-us/sharepoint/sites/plan-site-maintenance-and-management#quotas), [Sharepoint limits](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits), and [OneDrive quota](/en-us/onedrive/set-default-storage-space).

## Transcripts and captions

### Transcripts

You can choose to delete Teams meeting recordings along with their accompanying transcripts by using an *auto-apply retention label policy* that identifies these files from OneDrive and SharePoint transcript or OneDrive transcript. For more information, see [Automatically apply a retention label to Microsoft 365 items](/en-us/purview/apply-retention-labels-automatically).

To help you get started, see the following sections:

- [How to create an auto-apply retention label policy](/en-us/purview/apply-retention-labels-automatically#how-to-create-an-auto-apply-retention-label-policy)
- [Auto-apply labels to content with keywords or searchable properties](/en-us/purview/apply-retention-labels-automatically#auto-apply-labels-to-content-with-keywords-or-searchable-properties)
- [Identifying Teams meeting recordings and accompanying transcripts in OneDrive and SharePoint](/en-us/purview/apply-retention-labels-automatically#microsoft-teams-meeting-recordings)
- [How long it takes for retention labels to take effect](/en-us/purview/apply-retention-labels-automatically#how-long-it-takes-for-retention-labels-to-take-effect)

Note

When you create a retention label policy in Microsoft Purview, the minimum retention period is one day. The recordings and accompanying transcripts are deleted after one day.

### Captions

Captions help create inclusive content for viewers of all abilities. Closed captions for Teams meeting recordings are available during playback if transcription was turned on at the time of recording. To allow users to record meetings with transcripts, you must assign a policy with transcription turned on. To learn more about managing transcription for your users, see [Admins- Manage transcription and captions for Teams meetings](meeting-transcription-captions).

Closed captions aren't fully supported if the Teams meeting recording is moved or copied from its original location in OneDrive or SharePoint.

You can use the **Meetings automatically expire** setting in the Teams admin center to control when captions expire. To learn more, see [Manage Teams recording policies for meetings and events](manage-teams-recording-expiration-policy).

## Permissions or role-based access

Note

We recommend that the recipient is required to be a signed-in user when sharing Teams meeting recordings. Select the **People in (Your Organization)** option when you share the file as documented in [Share SharePoint files or folders](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c). External sharing isn't designed for the distribution of large files or a large number of files.

| Meeting type | Who selected Record? | Where does the recording land? | Who has access? R/W, R, or sharing |
| --- | --- | --- | --- |
| 1:1 call with internal parties | Caller | Caller's OneDrive account | Caller is owner and has full permissions. Callee has read-only access, but no sharing or download permissions. |
| 1:1 call with internal parties | Callee | Callee's OneDrive account | Callee is owner and has full permissions. Caller has read-only access, but no sharing or download permissions. |
| 1:1 call with an external call | Caller | Caller's OneDrive account | Caller is owner and has full permissions.Callee has no access. Caller must share it to the Callee. |
| 1:1 call with an external call | Callee | Callee's OneDrive account | Callee is owner and has full permissions.Caller has no access. Callee must share it to the Caller. |
| Group call | Any member of the call | Group member who selected Record's OneDrive account | Member who selected Record has full permissions.  Other group members from the same organization have Read rights.  Other group members from different organization have no permissions to it. |
| Adhoc/Scheduled meeting | Organizer | Organizer's OneDrive account | Organizer has full permissions to the recording. Co-organizers and organizer have edit permissions and can share.  All other members of the meeting from the same organization as the organizer have read access, but no sharing and download permissions. |
| Adhoc/Scheduled meeting | Other meeting member | Organizer's OneDrive account | Organizer has full permissions to the recording. Co-organizers and organizer have edit permissions and can share.  All other members of the meeting from the same organization as the organizer have read access. |
| Adhoc/Scheduled meeting with external participants | Organizer | Organizer's OneDrive account | Organizer has full permissions to the recording. Co-organizers and organizer have edit permissions and can share.  All other members of the meeting from the same organization as the organizer have read access.  All other external participants have no access, and the Organizer must share it to them. |
| Adhoc/Scheduled meeting with external participants | Other meeting member | Organizer's OneDrive account | Organizer has full permissions to the recording. Co-organizers and organizer have edit permissions and can share.  All other members of the meeting from the same organization as the organizer have read access. All other external participants have no access, and the Organizer must share it to them. |
| Channel meeting | Channel Member | Teams SharePoint location for that channel. Channel meeting recording upload to SharePoint isn't supported for IP-based restrictions. We recommend using [Azure conditional access](/en-us/azure/active-directory/conditional-access/overview). | Member who selected on Record has edit permissions to the recording. Every other member's permissions are based on the Channel SharePoint permissions. |