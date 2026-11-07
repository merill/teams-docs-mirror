---
layout: Conceptual
title: Manage Teams recording policies for meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-recording
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
ms.reviewer: ritikag,lisma
ms.date: 2026-07-06T00:00:00.0000000Z
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Learn how to deploy features in Teams meetings to record audio, video, and screen sharing activity.
locale: en-us
document_id: 976b8a9b-5a3e-1f3b-b848-d1dfbfd3389d
document_version_independent_id: 2b13a471-3baf-0086-439a-f94abb162fd6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-recording.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-recording
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-recording.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e4e3f36a-825c-131c-d2b1-b0242d3590c1
---

# Manage Teams recording policies for meetings and events - Microsoft Teams | Microsoft Learn

Note

When organizers turn off Microsoft Copilot in Teams meetings and events, recording and transcription are also turned off. To learn more about Copilot, see [Manage Microsoft Copilot in Teams meetings and events](copilot-teams-transcription).

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Group calls

In Microsoft Teams, your users can record their Teams meetings, 1:1 calls, and events to capture audio, video, and screen sharing activity. There are policies that control recording in each type. Many users use the term "meetings" and "calls" interchangeably.

Use this article to find the policy that controls recording in Teams meetings and events.

1. Confirm the type: meeting, event, or call.
2. Confirm the policy scope: meeting policy, events policy, or calling policy.
3. Confirm who needs recording permission: the organizer, co-organizer, or presenter.

There are two recording features that can be enabled with policy:

**Convenience recording**: An ad-hoc recording of a call or meeting that a user starts and manages. For an overview of convenience recording, see [Overview- Recording and transcription for Teams meetings and calls](/en-us/microsoftteams/recording-transcription-overview).

**Compliance recording**: Calls and meetings that are automatically recorded without user intervention and owned by the company, using a third-party solution.

We recommend that you check your call recording policy settings as well. If the settings are different for meetings and calls, it might cause confusion for your users. To learn about managing recording for Public Switched Telephone Network (PSTN calls), see [Configure call recording, transcription, and captions in Teams](call-recording-transcription-captions).

When a meeting is recorded:

- It gets uploaded to the meeting organizer's OneDrive (private meetings) or SharePoint (channel meetings). To learn more about recordings in OneDrive and SharePoint, see [Teams meeting recording storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change).
- People invited to the meeting have permissions to view the recording (guests and external attendees can view the recording only if the recording is explicitly shared with them).
- Microsoft Purview, OneDrive file storage, and access permissions apply to the meeting recording files the same as with other files.
- It's linked in the chat for the meeting.
- It's displayed in the **Recordings and Transcripts** tab for the meeting in Teams calendar.
- It's added to various file lists across Microsoft 365: Shared with me, office.com, Recommended, Recent, etc.
- Microsoft 365 Search indexes it.

Teams events follow the same process for recording. However, there are a few key differences:

- In events [optimized for large audiences](plan-events), such as town halls, attendees can't access the recording through the chat.
- By default, events are recorded automatically. Your users can stop their events from being automatically recorded by using the **Record and transcribe** setting in their meeting options.
- Events use video on demand (VOD) to publish recordings. To learn more, see [Manage VOD publishing for Teams events](manage-vod-publishing).

There's an option for recordings to have automatic transcription, so users can play back meeting recordings with closed captions and review important discussion items in the transcript. For more information about transcription and captions, see [Configure transcription and captions for Teams meetings](meeting-transcription-captions).

For an overview of recording and transcription policies available for Teams meetings, events, and calls, see [Overview- Recording and transcription for Teams meetings, events, and calls](recording-transcription-overview).

## External participants

External participants can't record meetings except when it's a [Teams third-party compliance recording](teams-recording-policy). If an external Teams user who's enabled for compliance recording joins a meeting or call hosted by your organization, the other organization records that meeting or call for compliance purposes, regardless of the **Meeting recording** setting in your organization. Organizers, co-organizers, and presenters in that meeting are notified and can remove the external participant from the meeting if they don't want the other org to capture recordings.

## Allow or prevent users from recording

You can use the Microsoft Teams admin center or PowerShell to control whether your users can record meetings and events. Meetings and events each have their own recording policies that you can manage. Both the organizer and recording initiator need to have recording permissions to record the meeting or event. Organizers with a Teams Premium license can use their meeting options to control who can record and transcribe.

### Meetings

To allow or prevent meeting recordings, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the Global policy. To exclude certain users from the global policy, create and assign a custom meeting policy.
3. Turn the **Meeting recording** toggle **On** or **Off**.
4. Select **Save**.
5. To assign the policy:
    - **To specific users**: Select your policy, select **Manage users** &gt; **Assign users**, enter the names of specific users in the search bar, select **Add**, and then select **Apply**.
    - **To groups**: Go to the **Group policy assignment** tab, select **Add**, enter the group name, select the policy name, and then select **Apply**.

To manage meeting recording by using PowerShell, use the **`-AllowCloudRecording`** parameter in [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy). For details, see the PowerShell section later in this article. Before you enable meeting recording, review Permissions and storage and make sure the required OneDrive or SharePoint storage is available.

### Events

#### Events up to 1,000 attendees

To allow or prevent recordings for events with up to 1,000 attendees, such as webinars, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the Global policy. To exclude certain users from the Global policy, create and assign a custom events policy.
3. Go to the **Recording & transcription** section.
4. Turn the **Record events up to 1k attendees** toggle **On** or **Off**.
5. Select **Save**.
6. To assign the policy:
    - **To specific users**: Select your policy, select **Manage users** &gt; **Assign users**, enter the names of specific users in the search bar, select **Add**, and then select **Apply**.
    - **To groups**: Go to the **Group policy assignment** tab, select **Add**, enter the group name, select the policy name, and then select **Apply**.

To manage recordings for events with up to 1,000 attendees using PowerShell, use the **`-RecordingForWebinar`** parameter in [Set-CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy). For details, see the PowerShell section later in this article.

#### Events optimized for large audiences

To allow or prevent recordings for events [optimized for large audiences](plan-events), such as town halls, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the Global policy. To exclude certain users from the Global policy, create and assign a custom events policy.
3. Go to the **Recording & transcription** section.
4. Turn the **Record events optimized for a large audience** toggle **On** or **Off**.
5. Select **Save**.
6. To assign the policy:
    - **To specific users**: Select your policy, select **Manage users** &gt; **Assign users**, enter the names of specific users in the search bar, select **Add**, and then select **Apply**.
    - **To groups**: Go to the **Group policy assignment** tab, select **Add**, enter the group name, select the policy name, and then select **Apply**.

To manage recordings for events optimized for large audiences using PowerShell, use the **`-RecordingForTownhall`** parameter in [Set-CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy). For details, see the PowerShell section later in this article.

## Block or allow download of channel meeting recordings

**`-ChannelRecordingDownload`** is an org-wide policy parameter that controls the folder where recordings and transcripts are stored to determine whether users can download channel meeting recordings and transcripts.

The two values for this setting are:

- **Allow** (default value) - Channel meeting recordings and transcripts are saved to a **Recordings** folder in the channel's SharePoint site. The recording and transcript file permissions follow the Channel SharePoint permissions. This is the same as any other file uploaded for the channel.
- **Block** - Channel meeting recordings and transcripts are saved to a **Recordings\View only** folder in the channel's SharePoint site. Channel owners have full access and rights to the recordings and transcripts in this folder, while channel members can only view them without the option to download or edit.

To manage this setting by using PowerShell, use the **`-ChannelRecordingDownload`** parameter in [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy). For more information, see the PowerShell section later in this article.

## Set a custom privacy policy URL

To update the Teams recording and transcription privacy policy URL with a custom link for users in and outside your org, you must use one of the following options:

- The **`-LegalURL`** parameter within the [CsTeamsMeetingConfiguration](/en-us/powershell/module/skype/set-csteamsmeetingconfiguration) PowerShell cmdlet.
- The Teams admin center through **Meeting settings** &gt; **Email invitation** &gt; **Privacy and Security URL**. For detailed instructions, see [Customize meeting invitations (IT admins)](customize-meeting-invitations).

If you don't enter a privacy and security URL in Teams meeting settings or PowerShell, we display Microsoft Entra ID's privacy policy. For more information on Microsoft Entra ID's privacy policy, see [Add your organization's privacy info using Microsoft Entra ID](/en-us/entra/fundamentals/properties-area). If there's no Microsoft Entra ID, we display the Microsoft Privacy policy.

When you add your privacy policy URL, your URL replaces the default Teams meeting recording and transcription privacy statement.

Note

The Microsoft Entra ID's privacy policy isn't shown to external tenant users or anonymous users. If you don't create a privacy and security URL in Teams meeting settings or PowerShell, the Microsoft Privacy policy is shown instead.

## Permissions and storage

Teams meeting recordings are stored in the organizer's OneDrive and SharePoint storage. The location and permissions depend on the type of meeting and the role of the user in the meeting. Users with full edit rights on the video recording file can change the permissions and share it later with others as needed. To understand permissions and storage in OneDrive and SharePoint, see [Use OneDrive and SharePoint for meeting recordings](tmr-meeting-recording-change).

Important

**`-AllowCloudRecording`** controls whether users can record meetings; it doesn't configure or validate recording storage. For non-channel meetings, make sure the applicable OneDrive account is available and has sufficient storage capacity. Channel meeting recordings are stored in SharePoint. If a recording can't be uploaded to OneDrive or SharePoint, it's temporarily stored in async media storage and must be downloaded within 21 days. Otherwise, the recording is deleted.

## eDiscovery search for recordings and transcripts

To find your users' recording and transcript files by using eDiscovery, follow these steps:

1. Go to the [Microsoft Purview portal](https://purview.microsoft.com/).
2. In the search box, enter 'eDiscovery'.
3. Follow the steps in the linked article to create an eDiscovery case: [Create and manage an eDiscovery (Premium) case](/en-us/purview/ediscovery-create-and-manage-cases).
4. Open the case, and then on the **Collections** tab, select **New collection**.
5. Commit the new collection.
6. Open **Review set**, and use the filter to find the recordings and transcripts you're looking for.

## Troubleshooting

If users can't record a meeting, first verify if it was a Teams meeting, 1:1 calls, or event. Then verify the matching policy and recording setting assigned.

To learn about why users can't record meeting, see [I can't record a meeting in Microsoft Teams](https://support.microsoft.com/office/i-can-t-record-a-meeting-in-microsoft-teams-f35329c2-57b1-487f-b5e3-70a7efb0945b). To learn how to use diagnostic tools, see [Issues that affect meeting recordings](/en-us/microsoftteams/troubleshoot/meetings/troubleshoot-meeting-recording-issues).

## PowerShell

Start by connecting to Windows PowerShell.

After you create or update new policies, assign them to users or groups. For more information about assigning policies to users and groups by using PowerShell, see [Assign policies to users and groups](assign-policies-users-and-groups).

### Manage recording for meetings

To allow everyone in your organization to record, except users with an assigned custom meeting policy, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

To allow specific users in your organization to record, run the following commands:

1. Create a new policy.

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity "Your Policy Name" -AllowCloudRecording $true
    ```
2. Assign specific users the policy.

    ```powershell
    Grant-CsTeamsMeetingPolicy -Identity "user@contoso.onmicrosoft.com" -PolicyName "Your Policy Name"
    ```

To allow specific groups in your organization to record, run the following commands:

1. Create a new policy.

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity "Your Policy Name" -AllowCloudRecording $true
    ```
2. Assign specific groups the policy.

    ```powershell
    Grant-CsTeamsMeetingPolicy -Group "Group ID" -PolicyName "Your Policy Name"
    ```

### Manage recording for events up to 1,000 attendees

To allow users with this policy to record events with up to 1,000 attendees, run the following command:

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -RecordingForWebinar Enabled
```

To prevent users with this policy from recording events with up to 1,000 attendees, run the following command:

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -RecordingForWebinar Disabled 
```

### Manage recording for events optimized for large audiences

To allow users with this policy to record events optimized for large audiences, run the following command:

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -RecordingForTownhall Enabled
```

To prevent users with this policy from recording events optimized for large audiences, run the following command:

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -RecordingForTownhall Disabled 
```

### Manage whether meetings require participant agreement for recording and transcription

The **`-ExplicitRecordingConsent`** parameter also controls recording consent for Audio Conferencing. To learn about explicit consent for Audio Conferencing, see [Explicit recording consent for Audio Conferencing](conferencing-recording-consent).

To require participants to give their explicit consent to be recorded or transcribed in any meeting that organizers with this policy create, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -ExplicitRecordingConsent Enabled
```

### Manage download of channel meeting recordings in PowerShell

To prevent users in your organization from downloading channel meeting recordings and transcripts from OneDrive and SharePoint, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

To allow users in your organization to download channel meeting recordings and transcripts from OneDrive and SharePoint, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Allow
```