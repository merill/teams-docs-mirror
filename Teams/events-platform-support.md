---
layout: Conceptual
title: Platform support for Teams events features - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/events-platform-support
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: guptaharsh
ms.date: 2026-04-01T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-events
audience: admin
f1.keywords:
- NOCSH
description: Learn about the supported platforms for events features in Microsoft Teams.
locale: en-us
document_id: 88a9769d-52b5-811e-2765-cb8846b54ab7
document_version_independent_id: 88a9769d-52b5-811e-2765-cb8846b54ab7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/events-platform-support.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: events-platform-support
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/events-platform-support.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 88146e09-2a0d-5a36-fe50-dfaef82c275f
---

# Platform support for Teams events features - Microsoft Teams | Microsoft Learn

This article outlines the supported platforms for Teams events features.

## Supported platforms for events optimized for large audiences

The following table describes platform support for features for [events optimized for large audiences](plan-events), such as town halls.

| Feature | Windows | Mac | Mobile | Web | Microsoft Teams Rooms- Windows | Microsoft Teams Rooms- Android | Touch boards for Teams Rooms | Direct guest join | CVI | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Custom emails | Yes | Yes | Yes | No | No | No | No | No | No | No | No | No | Yes | Yes |
| Event chat | Yes | Yes | Yes | Yes | No | No | N/A | N/A | No | N/A | Yes | N/A | No^1^ | Yes |
| Attendee reactions | Yes | Yes | Yes | Yes | No | No | N/A | N/A | No | N/A | Yes | N/A | Partial^1^ | Yes |
| Teams events insights | Yes | Yes | Yes | Yes | No | No | N/A | N/A | No | No | Yes | N/A | Partial^1^ | Yes |
| Microsoft eCDN, analytics, and provider management | Yes | Yes | No | Yes | No | No | No | No | No | No | No | Yes | Partial^1^ | Yes |
| RTMP-In | Yes | Yes | No | Yes | No | No | No | No | N/A | N/A | Yes | No | Yes | Yes |

^1^Your users should join via web.

## Platform support for events up to 1,000 attendees

The following table describes platform support for features for events up to 1,000 attendees, such as webinars.

| Feature | Windows | Mac | Mobile | Web | Microsoft Teams Rooms- Windows | Microsoft Teams Rooms- Android | Touch boards for Teams Rooms | Direct guest join | CVI | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Custom emails and reminders | Yes | Yes | N/A | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | No | Yes | Yes |
| Enable and manage the waitlist beyond capacity | Yes | Yes | N/A | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | No | Yes | Yes |
| Limit registration start and end times | Yes | Yes | N/A | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | No | Yes | Yes |
| Manage what attendees see | Yes | Yes | No | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | Yes | Yes | Yes |
| Manually approve registrants | Yes | Yes | No | Yes | No | No | No | No | No | No | No | No | Yes | Yes |
| RTMP-In | Yes | Yes | No | Yes | No | No | No | No | N/A | N/A | Yes | No | Yes | Yes |

## Platform support for immersive events

The following table describes platform support for immersive events.

| Feature | Windows | Mac | Mobile | Web | Microsoft Teams Rooms- Windows | Microsoft Teams Rooms- Android | Touch boards for Teams Rooms | Direct guest join | CVI | View-only mode | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Immersive events in Teams** | **Yes** | **Yes** | No | No | No | No | No | No | No | No | No | No | No | No | No |