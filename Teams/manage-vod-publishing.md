---
layout: Conceptual
title: Manage VOD publishing for Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-vod-publishing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: sachung
ms.date: 2026-07-06T00:00:00.0000000Z
ms.author: v-lanchin
author: LanaChin8
ms.topic: how-to
manager: v-jesserowe
ms.service: msteams
ms.subservice: teams-events
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to manage Video on Demand (VOD) publishing for events in Microsoft Teams.
locale: en-us
document_id: 68a48ea8-979b-8506-5a15-d7f15643aa40
document_version_independent_id: 68a48ea8-979b-8506-5a15-d7f15643aa40
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-vod-publishing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-vod-publishing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-vod-publishing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 9b33758f-435e-7fd2-daff-3ad834ca0acf
---

# Manage VOD publishing for Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Video on Demand (VOD) for Microsoft Teams events enables event organizers to quickly publish and share event recordings. When organizers record these events, the recordings are uploaded to [OneDrive](tmr-meeting-recording-change#meetings-and-events). When published, recordings are stored in SharePoint Embedded Containers and all attendees automatically receive an email with a link to view the recording.

As an admin, you can manage whether organizers can publish recordings for:

- Events up to 1,000 attendees
- Events optimized for large audiences

## Delete VOD recordings

To learn how to delete VOD recordings, see [Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change#video-on-demand-vod).

## Manage VOD publishing for events up to 1,000 attendees

You can use the Teams admin center or PowerShell to manage VOD publishing permissions for events with up to 1,000 attendees, such as webinars.

The following table lists the values that you can set for publishing permissions for events with up to 1,000 attendees, along with the corresponding behaviors.

| Teams admin center value | PowerShell value | Behavior |
| --- | --- | --- |
| Not allowed | None | Organizers with this policy can't publish any event recordings. |
| Invite only | InviteOnly | Organizers with this policy can only publish recordings for invite-only events. These organizers can't publish any recordings of public events. |
| Your organization | EveryoneInCompanyIncludingGuests | Organizers with this policy can only publish recordings for private and invite-only events. These organizers can't publish any recordings for public events. |
| Public | Everyone | **This is the default.** Organizers with this policy can publish any event recordings. |

Note

Guests can't view recordings of private events.

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. In the **Allowed webinar types for recordings**dropdown list, choose one of the following values:
    - **Not allowed**
    - **Invite only**
    - **Your organization**
    - **Public**
4. Select **Save**.

### Using PowerShell

Use the **`-AllowedWebinarTypesForRecordingPublish`** parameter within the [CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy) PowerShell cmdlet.

To prevent organizers from publishing any event recordings, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedWebinarTypesForRecordingPublish None
```

To only allow organizers to publish private event recordings, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedWebinarTypesForRecordingPublish EveryoneInCompanyIncludingGuests
```

## Manage VOD publishing for events optimized for large audiences

You can use the Teams admin center or PowerShell to manage VOD publishing permissions for events [optimized for large audiences](plan-events), such as town halls.

The following table lists the values that you can set for publishing permissions for events optimized for large audiences, along with the corresponding behaviors.

| Teams admin center value | PowerShell value | Behavior |
| --- | --- | --- |
| Not allowed | None | Organizers with this policy can't publish any event recordings. |
| Invite only | InviteOnly | Organizers with this policy can only publish recordings for invite-only events. These organizers can't publish any recordings of public events. |
| Your organization | EveryoneInCompanyIncludingGuests | Organizers with this policy can only publish recordings for private and invite-only events. These organizers can't publish any recordings for public events. |
| Public | Everyone | **This is the default.** Organizers with this policy can publish any event recordings. |

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. In the **Allowed town hall types for recordings**dropdown list, choose one of the following values:
    - **Not allowed**
    - **Invite only**
    - **Your organization**
    - **Public**
4. Select **Save**.

### Using PowerShell

Use the **`-AllowedTownhallTypesForRecordingPublish`** parameter within the [CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy) PowerShell cmdlet.

To only allow organizers to publish recordings of invite-only events, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedTownhallTypesForRecordingPublish InviteOnly
```

To prevent organizers from publishing any event recordings, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedTownhallTypesForRecordingPublish None
```

To only allow organizers to publish recordings of private and invite-only events, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedTownhallTypesForRecordingPublish EveryoneInCompanyIncludingGuests
```