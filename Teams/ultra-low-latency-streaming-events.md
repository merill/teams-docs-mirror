---
layout: Conceptual
title: Ultra-Low Latency (ULL) streaming for Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/ultra-low-latency-streaming-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Describes the Ultra-Low Latency (ULL) feature in Teams events.
author: chbalaki
manager: preethir
ms.author: chbalaki
ms.service: msteams
ms.subservice: teams-events
ms.topic: concept-article
ms.date: 2026-10-06T00:00:00.0000000Z
locale: en-us
document_id: 90c51422-c946-f45a-b1b9-ff88478f241c
document_version_independent_id: 90c51422-c946-f45a-b1b9-ff88478f241c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/ultra-low-latency-streaming-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: ultra-low-latency-streaming-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/ultra-low-latency-streaming-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
platformId: 738677c3-ab00-73c8-85e3-635523933cc7
---

# Ultra-Low Latency (ULL) streaming for Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

Note

In Teams events, this feature is available only in events [optimized for large audiences](/en-us/microsoftteams/plan-events).

Teams events attendees historically viewed the presentation with a 30-second or more delay. With Ultra-Low Latency (ULL), attendees can now watch events at a significantly reduced latency so they can be in sync with the presentation being shared and better engage with the organizers and presenters.

Ultra-Low Latency uses a new streaming protocol for event attendees. Ultra-Low Latency is compatible with the Microsoft Enterprise Content Delivery Network (eCDN). It doesn't support third-party eCDN providers.

All engagement and interactivity features—including reactions, event chat, and more—work regardless of what streaming protocol is used.

No action is required from administrators to enable Ultra-Low Latency in their organization.

Note

Ultra-Low Latency (ULL) might fall back to the HTTPS Live Streaming (HLS) protocol if Microsoft detects a network issue.

## FAQ

### Does it use the same event content delivery networks?

No. Ultra-Low Latency operates its own delivery network within the Microsoft 365 domains and IPs.

### Does Ultra-Low Latency work with Real-Time Messaging Protocol (RTMP)?

Yes, but there's additional inherent latency with the RTMP protocol that isn't reduced by Ultra-Low Latency.

### What determines the location of delivery nodes, and should we expect Ultra-Low Latency in locations such as China?

Delivery nodes are determined by the location of the attendee and are located throughout NOAM, APAC, and EMEA. There are no delivery nodes specifically in China and this traffic would be served from APAC.

### Does Ultra-Low Latency work with events that were scheduled before the rollout to my organization?

Yes, because Ultra-Low Latency usage is decided at runtime rather than during the scheduling process.

### Can Ultra-Low Latency be enabled in meetings options during an event?

Ultra-Low Latency is used by default, and if clients have issues with ULL, there's a fallback to HTTPS Live Streaming (HLS).

### Does Ultra-Low Latency scale to 50,000 and/or 100,000 attendees?

Ultra-Low Latency currently supports up to 20,000 attendees. We're working to scale this support to 50,000 and 100,000 attendees in the future. For now, events with more than 20,000 attendees use HTTPS Live Streaming (HLS) protocol.