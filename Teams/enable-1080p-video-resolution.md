---
layout: Conceptual
title: Enable 1080p video resolution for Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/enable-1080p-video-resolution
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Describes how admins can set up 1080p video quality for Teams events.
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: cmunden, gavinhewitt
ms.service: msteams
ms.subservice: teams-events
ms.topic: how-to
ms.date: 2026-10-06T00:00:00.0000000Z
audience: admin
f1.keywords:
- NOCSH
locale: en-us
document_id: 7ebc35ce-8510-8fbd-7b16-2b01aab15941
document_version_independent_id: 7ebc35ce-8510-8fbd-7b16-2b01aab15941
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/enable-1080p-video-resolution.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enable-1080p-video-resolution
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/enable-1080p-video-resolution.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 8d2e79a9-18ca-653d-4df7-3eb2d9c950da
---

# Enable 1080p video resolution for Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

Note

In Teams events, this feature is available only in events [optimized for large audiences](/en-us/microsoftteams/plan-events).

Attendees can experience Teams events in 1080p resolution with up to 30 frames per second, which provides a more engaging and visually stunning experience. 1080p resolution is supported for both [Ultra-Low Latency (ULL)](ultra-low-latency-streaming-events) streaming and HTTPS Live Streaming (HLS).

For resiliency at scale, we recommend using an enterprise content delivery network (eCDN). 1080p resolution with ULL streaming is supported only with Microsoft eCDN. Third-party eCDN solutions will use HLS.

## Set up 1080p resolution

1. In [SetCsTeamsEventsPolicy](/en-us/powershell/module/microsoftteams/set-csteamseventspolicy), set the `-TownhallMaxResolution` parameter to `Max1080p`.
2. Apply the policy tenant-wide or assign it to specific event organizers in your organization.
3. Hold a test event and use [Teams events insights](https://support.microsoft.com/office/town-hall-insights-in-microsoft-teams-def99575-61bf-4ea2-ad0e-c6e75dce7741) to confirm the resolution for attendees.

## FAQ

### Do I need to use a policy to manage 1080p resolution in events?

Yes. In [SetCsTeamsEventsPolicy](/en-us/powershell/module/microsoftteams/set-csteamseventspolicy), set the `-TownhallMaxResolution` parameter to `Max1080p`. Then apply the policy tenant-wide or assign it to specific organizers who need access to 1080p events. Policy changes aren't reflected immediately for users. It might take up to 24 hours for changes to take effect.

### What are the bandwidth requirements for 1080p?

1080p requires about 4 Mbps per stream. 

### What happens if I enable 1080p resolution and my network can't support it?

Teams events use adaptive resolution, which downshifts to 720p or 540p if network conditions can't sustain 1080p. We recommend that you test your network ahead of time to ensure it can support 1080p resolution reliably. Keep in mind that downshifting resolution interrupts the streaming experience for attendees.

### What attendee platforms support 1080p?

The Teams desktop client, macOS, iOS, Android, MTR-A devices, and web browsers support 1080p resolution.

### How does split tunneling in my network affect 1080p resolution?

If your split tunneling is configured according to the guidance in [Special considerations for Teams events in VPN environments](/en-us/microsoft-365/enterprise/microsoft-365-vpn-stream-and-live-events), you're ready for 1080p broadcasts. 

### Where can I confirm that attendees are seeing 1080p resolution?

[Teams events insights](https://support.microsoft.com/office/town-hall-insights-in-microsoft-teams-def99575-61bf-4ea2-ad0e-c6e75dce7741) contain near real-time information that includes attendee resolution.