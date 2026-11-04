---
layout: Conceptual
title: Manage RTMP-In for Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meetings-rtmp-in
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: srajay, cmunden
ms.date: 2026-10-06T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Tier2
- m365initiative-meetings
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
description: Learn how to set up RTMP-In for Teams meetings and events.
locale: en-us
document_id: 5718254f-842e-6954-474f-b92da72b6d7f
document_version_independent_id: 5718254f-842e-6954-474f-b92da72b6d7f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meetings-rtmp-in.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meetings-rtmp-in
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meetings-rtmp-in.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e44fafc7-82dd-1dfa-8035-5c61307e2838
---

# Manage RTMP-In for Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

RTMP-In enables meeting and event organizers to produce their meetings and events directly from an external hardware or software-based encoder using Real-Time Messaging Protocol (RTMP). To learn more about how organizers use RTMP-In, see [Use RTMP-In in Microsoft Teams](https://support.microsoft.com/office/use-rtmp-in-in-microsoft-teams-789d6090-8511-4e2e-add6-52a9f551be7f).

As an admin, you can use meeting policies to turn on RTMP-In for meeting and event organizers. Organizers with this policy can access the RTMP link and key needed to start streaming from the encoder through their **Meeting options**. To learn more about encoders, see [Use an encoder for streaming with Microsoft Teams](teams-encoder-setup).

The incoming RTMP feed must deliver:

- H.264 Advanced Video Coding (AVC)
- Constant Bitrate (CBR) for 720p or Constant Bitrate (CBR) and Variable Bitrate (VBR) for 1080p
- Frame rate of at least 29.97 fps or 30 fps or higher
- Square Pixel Aspect Ratio (PAR)

## RTMP ingest endpoints

As part of the network connectivity principles, make sure that the Microsoft 365 endpoints are reachable as defined in [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges). Verify that you also have the following domains and ports:

**Domains**:

- Single RTMP Stream - \*.rtmpingest.mcr.teams.microsoft.com
- Additional RTMP Stream - \*.rtmpingest.mcr.teams.cloud.microsoft

**Ports**:

- Single RTMP Stream - 1935/1936 (for RTMP/RTMPS)
- Additional RTMP Stream - 50118/50119 (RTMP/RTMPS)

Note

RTMP domain and port will transition to \*.rtmpingest.mcr.teams.cloud.microsoft and 50118/50119 (RTMP/RTMPS) for both Single and Additional RTMP Streams by the end of 2026 so please ensure access to this port and domain.

## Manage whether organizers can use RTMP-In with the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one.
3. Go to the **Audio & video** section.
4. For **Allowed streaming media input**, select or clear the **RTMP** checkbox from the dropdown.
5. Select **Save**.

## Manage whether organizers can use RTMP-In with PowerShell

To manage whether organizers can use RTMP-In, use the **`-AllowedStreamingMediaInput`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

### Turn on RTMP-In

To turn on RTMP-In for organizers with this policy, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowedStreamingMediaInput "RTMP"  
```

### Turn off RTMP-In

To turn off RTMP-In for organizers with this policy, use a null value with `-AllowedStreamingMediaInput`. For example:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowedStreamingMediaInput ""
```

### View the RTMP-In status for a policy

To view the current status of RTMP-In for a meeting policy, use the following script:

```PowerShell
Get-CsTeamsMeetingPolicy -Identity <policy name>|fl AllowedStreamingMediaInput
```