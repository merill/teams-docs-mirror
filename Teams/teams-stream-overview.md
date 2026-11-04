---
layout: Conceptual
title: Live events in Microsoft Teams overview - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-stream-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
ms.reviewer: christi.balaki,cmunden
ms.date: 2026-06-11T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
description: This article gives an overview of encoder-based RTMP configuration for Microsoft Teams streaming events.
ms.localizationpriority: Medium
ms.custom: 
locale: en-us
document_id: c236d9c5-e50e-a62b-1719-824b4299c3d9
document_version_independent_id: c236d9c5-e50e-a62b-1719-824b4299c3d9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-stream-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-stream-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-stream-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e47aa476-0700-472c-b409-dad2b2bba649
---

# Live events in Microsoft Teams overview - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

Users in your organization can create live events using Microsoft Teams. Your users can schedule, produce, and deliver live events for various scenarios such as company-wide events, leadership updates, and more. Live streaming events allow producers to curate and control the content that is broadcast to an audience.

Your users can create, schedule, and run live events using a single bitrate RTMP or RTMPS stream from an encoder – we take care of all the transcoding for adaptive bitrate delivery to your viewers.

Just like any other video in Teams, as an admin, you decide who can join live events in your organization. Managing the event access type provides an end-to-end creation and viewing experience inside of Teams.

After the event, the video is available on demand with intelligent features including:

- Speech-to-text and closed captions.
- Transcript search and time codes to quickly find moments that matter in a video.

## Live events in Microsoft 365

Your users can create live events in Teams or Viva Engage, wherever your audience, team, or community resides. Attendees can watch the event in high-definition (HD) video and submit questions through a moderated Q&A experience. Seamless integration across Microsoft 365 means that you can use Teams to deliver highly produced, studio-quality events.

## Get started

Ensure that users you want to create live events have the permissions required to create a live event. By default, everyone in your organization can create a live event, however you can restrict access.

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Live events policies** &gt; the **Manage Policies** tab.
2. If you want to:
    1. Edit the existing default policy, choose **Global (Org-wide default)**.
    2. Create a new custom policy, choose **+Add**.
    3. Edit a custom policy, select the policy, and then choose **Edit**.

## Monitor your event

Producers can use the Teams client to see the audience feed (visible on the right side) and the number of attendees currently viewing the event.

## Capabilities

The following are capabilities of live streaming events:

| Operation | Limits |
| --- | --- |
| Create live events in Teams (with external encoder) | Enterprise (E1, E3, E5), Education (A3, A5) |
| Watch live event | Viewers with permissions to view the event and a valid Teams license (unless the event is public, then a license to view isn't required) |
| Maximum resolution | 720p |
| Maximum concurrent live events (in prelive or live) | 15^1^ |
| Active concurrent viewers | 10000^1^ |
| Maximum length of live event | 4 hours ^1^ |
| Partner networks caching support | Hive, Kollective, Ramp, Microsoft |
| Other network caching support | Might work, but isn't supported |
| Attendee DVR controls | Pause, playback speed (2x catch up, 1x at live), seek |
| Real-time captions | 708 caption pass-through from encoder |
| Automatic speech-to-text and captions | Processed after the event |
| Interactive discussions | Supported via Viva Engage when the event is created from Viva Engage |
| Teams comments | Available after the event ends |
| On-demand viewing on live event (after event) | Automatic transition for live to on-demand for immediate viewing and indexing in Teams |
| Downloadable recording | Processed and available after the live event by owners |

^1^ The limits that are set might be changed. Check [Limits and specifications for Teams](limits-specifications-teams).

Teams live events is a highly available service and you can expect good performance at scale. In the unlikely scenario that results in failover being required, live events using external encoding don't have redundancy and aren't recoverable.