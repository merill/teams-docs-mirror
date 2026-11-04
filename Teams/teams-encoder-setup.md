---
layout: Conceptual
title: Use an encoder for streaming with Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-encoder-setup
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
ms.reviewer: chbalaki, cmunden
ms.date: 2026-09-18T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about encoder-based RTMP and SRT setup and supported encoders for Microsoft Teams streaming events.
ms.localizationpriority: medium
ms.custom: 
locale: en-us
document_id: 6b808097-6ba9-b0b7-e48e-0ff395ff1dfb
document_version_independent_id: 6b808097-6ba9-b0b7-e48e-0ff395ff1dfb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-encoder-setup.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-encoder-setup
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-encoder-setup.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
platformId: 6cbcad19-db83-c3d1-fd9c-0dc8cc67682d
---

# Use an encoder for streaming with Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Live events

Video encoders allow users to produce Microsoft Teams meetings and events through external hardware or software-based solutions.

## Overview

An encoder takes audio and video content from various sources you use during a meeting or event, such as a camera, a microphone, or a desktop screen capture. The encoder compresses and converts that media into a suitable digital format, and sends it to Teams for live streaming to your audience. To learn more about how you can use Teams production technologies (such as NDI) with external encoders, see our [Custom Production playbook](https://aka.ms/CustomProductionVEP).

## Prerequisites

Users must have a Teams meeting policy that has RTMP-In or SRT-In enabled. To learn more, see [Manage RTMP-In for Teams meetings and events](meetings-rtmp-in) and [Manage SRT-In for Teams meetings and events](meetings-events-srt-in).

## Production workflow when using an encoder

Here's the workflow for producing a Teams event using an encoder.

The organizer must turn on **RTMP-In** or **SRT-In** in their **Meeting options**.

- **RTMP-In** creates an RTMP endpoint, which is provided with an RTMP(S) URL and corresponding stream key. The encoder uses the URL and stream key to connect to the RTMP endpoint for the scheduled event.
- **SRT-In** creates an SRT endpoint, which is provided with an SRT URL. The encoder uses the URL to connect to the SRT endpoint for the scheduled event.

## Common video encoders used for live streaming

Microsoft validated the following video encoders for live streaming with Teams.

### Supported encoders

| Encoder | Encoder Type | RTMP | SRT |
| --- | --- | --- | --- |
| AJA HELO Plus | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| AWS Elemental Live | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| Blackmagic Web Presenter HD | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| Blackmagic ATEM Mini with streaming engine | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| BrandLive | Service | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| Epiphan video Pearl Nano | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| FFmpeg | Software | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| Haivision | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| Kiloview E3 | Hardware |  | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| Live Arena AI Producer | Service | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| Magewell Ultra Encode AIO | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| Matrox Monarch EDGE Series | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| Newtek TriCaster 2 Elite | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| Open Broadcaster Software (OBS Studio) | Software | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| Socialive | Service | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| StreamYard | Service | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| Telestream Wirecast | Software | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |
| Teradek Prism Flex | Hardware | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| vMix | Software | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |
| XSplit Broadcaster | Software | ![Image of a checkmark for yes.](/en-us/office/media/icons/success-teams.png) |  |