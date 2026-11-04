---
layout: Conceptual
title: Live events recording policies - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-live-events/live-events-recording-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: article
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: christi.balaki,cmunden
ms.date: 2024-10-03T00:00:00.0000000Z
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Learn about live event recording policies.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: ae14299b-94b7-6dcd-5560-c1dbee13918f
document_version_independent_id: 8e145920-8a41-ed84-e366-797081ea162c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-live-events/live-events-recording-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-live-events/live-events-recording-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-live-events/live-events-recording-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 02c15624-15f6-413b-2bf8-d60885c8ad95
---

# Live events recording policies - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

There are multiple ways for your users to record a Microsoft Teams live event. The recording policies that you, as an admin manage, determine the available recording options for your users. This article explains the different settings.

The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/en-us/powershell/module/teams/set-csteamsmeetingbroadcastpolicy).

## Scheduling and option behaviors

There are two organizer options while scheduling a live event recording:

- **Recording available for producers and presenters**

    - Recording file: Provides a recording file that producers and presenters can download after the event is over.
- **Recording available for attendees**

    - DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event
    - VOD: A video on demand (VOD) allows attendees to watch after the event is over

## Broadcast recording policy setting

As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.

| - | Recording available for producers and presenters | Recording available for attendees |
| --- | --- | --- |
| Always record | Disabled and selected | Enabled and selected |
| Organizer can record or not | Enabled and selected by default | Enabled and selected by default |
| Never record | Disabled and not selected | Disabled and not selected |

## Storage and persistence behavior

| Option | State | DVR | VOD | Recording |
| --- | --- | --- | --- | --- |
| Recording available for attendees | Selected | DVR is available and the Azure Media Services (AMS) asset is stored for 180 days | Attendee can access and watch the event |  |
|  | Not Selected | DVR is available and the AMS asset is stored for 180 days | Attendee won't get access into the event after it's over |  |
|  | Disabled (Not selected) | DVR is available and the AMS asset is deleted after the event | Attendee won't get access into the event after it's over |  |
| Recording available to producers and presenters | Selected |  |  | An MP4 is created and stored for 180 days |
|  | Not Selected |  |  | No file is created |

### Related topics

- [What is Teams live events?](what-are-teams-live-events)
- [Plan for Teams live events](plan-for-teams-live-events)
- [Configure live events settings in Teams](configure-teams-live-events)
- [Teams clouds meeting recording](../meeting-recording)