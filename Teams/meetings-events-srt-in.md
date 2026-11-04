---
layout: Conceptual
title: Manage SRT-In for Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meetings-events-srt-in
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
ms.reviewer: cmunden
ms.date: 2026-09-17T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
description: Learn how to set up SRT-In for Teams meetings and events.
locale: en-us
document_id: 51a5b5d1-47e7-a002-277e-f1808fad3332
document_version_independent_id: 51a5b5d1-47e7-a002-277e-f1808fad3332
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meetings-events-srt-in.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meetings-events-srt-in
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meetings-events-srt-in.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 06aa21eb-e825-3d93-067e-41d69ec7481c
---

# Manage SRT-In for Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

SRT-In enables meeting and event organizers to produce their meetings and events directly from an external hardware or software-based encoder using the Secure Reliable Transport (SRT) protocol. To learn more about how organizers use SRT-In, see [Use SRT-In in Microsoft Teams](https://support.microsoft.com/teams/meetings/use-srt-teams).

As an admin, you can use meeting policies to turn on SRT-In for meeting and event organizers. Organizers with this policy can access the SRT link that they need to start streaming from the encoder through their **Meeting options**. To learn more about encoders, see [Use an encoder for streaming with Microsoft Teams](teams-encoder-setup).

The incoming SRT feed must deliver:

- H.264 Advanced Video Coding (AVC) and H.265 High Efficiency Video Coding (HEVC)
- Constant Bitrate (CBR) and Variable Bitrate (VBR) for 1080p
- Frame rate of least 29.97 fps or 30 fps or higher
- Square Pixel Aspect Ratio (PAR)

## SRT ingest endpoints

As part of the network connectivity principles, make sure that the Microsoft 365 endpoints are reachable as defined in [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges).

Verify that you also have the following domain and port:

**Domain**: \*.rtmpingest.mcr.teams.cloud.microsoft**Port**: 49891 (SRT)

## Use the Teams admin center to manage whether organizers can use SRT-In

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one.
3. Go to the **Audio & video** section.
4. For **Allowed streaming media input**, select or clear the **SRT** checkbox from the dropdown.
5. Select **Save**.

## Use PowerShell to manage whether organizers can use SRT-In

To manage whether organizers can use SRT-In, use the **`-AllowedStreamingMediaInput`** parameter within the [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) PowerShell cmdlet.

### Turn on SRT-In

To turn on SRT-In for organizers with this policy, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowedStreamingMediaInput "SRT"  
```

To turn on RTMP-In and SRT-In for organizers with this policy, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowedStreamingMediaInput "RTMP,SRT"  
```

### Turn off SRT-In

To turn off SRT-In for organizers with this policy, use a null value with the `-AllowedStreamingMediaInput` parameter. For example:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowedStreamingMediaInput ""
```

### View the SRT-In status for a policy

To view the current status of SRT-In for a meeting policy, run the following command:

```PowerShell
Get-CsTeamsMeetingPolicy -Identity <policy name>|fl AllowedStreamingMediaInput
```