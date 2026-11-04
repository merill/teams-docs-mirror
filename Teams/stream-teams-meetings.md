---
layout: Conceptual
title: Allow live streaming with RTMP-Out for Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/stream-teams-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.reviewer: chbalaki
ms.date: 2026-07-06T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- Tier2
- m365initiative-meetings
description: Learn how to set up and manage streaming, also known as RTMP-Out, for your Teams meetings and events.
locale: en-us
document_id: fbe1d8aa-42df-e997-e547-5c05526f8398
document_version_independent_id: a426a627-6d8e-004f-25d7-85e53fb3bb18
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/stream-teams-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: stream-teams-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/stream-teams-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d80d0fca-9b34-d74e-2033-c3f5ff999c20
---

# Allow live streaming with RTMP-Out for Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Live streaming allows organizers in your organization to expand their reach and provide a unique experience for meeting and event attendees. As an admin, when you allow live streaming, your organizers can stream meetings and events to external endpoints by providing a Real-Time Messaging Protocol out (RTMP-Out) URL and key to the built-in [Custom Streaming app](https://appsource.microsoft.com/product/office/WA200006865) in Teams.

To learn more about how your organizers can use RTMP to live stream meetings and events, see [Broadcast audio and video from Teams with RTMP](https://support.microsoft.com/office/broadcast-audio-and-video-from-teams-with-rtmp-11d5707b-88bf-411c-aff1-f8d85cab58a0).

Note

Organizers can't stream live events.

## Manage live streaming for your users

You can use the Teams admin center or PowerShell to manage whether organizers with this assigned policy can live stream their meetings and events through RTMP-Out.

### Manage live streaming in the Teams admin center

Follow these steps to manage live streaming in the Teams admin center:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy that you want to edit.
3. Under **Audio & video**, set **Live streaming** to **On** from the dropdown.
4. Select **Save**.

### Manage live streaming with PowerShell

To manage whether organizers with this policy can live stream their meetings and events through RTMP, use the **`-LiveStreamingMode`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

To allow organizers with this policy to stream their meetings through RTMP, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -LiveStreamingMode Enabled
```

For information on how to assign policies with PowerShell, see [Assign policies in Teams](policy-assignment-overview).