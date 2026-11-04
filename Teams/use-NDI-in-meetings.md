---
layout: Conceptual
title: Allow broadcast production in Teams meetings with NDI and SDI hardware - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/use-ndi-in-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
ms.reviewer: christi.balaki
ms.date: 2025-05-29T00:00:00.0000000Z
manager: pamgreen
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: meetings
search.appverid: MET150
description: Learn how to use NDI and SDI to broadcast meeting content in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
locale: en-us
document_id: 2465e854-e3b1-6bd0-c834-c696121e857a
document_version_independent_id: 6b225ed2-0cd3-b3c3-0e3a-d7ce98031e16
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/use-NDI-in-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: use-ndi-in-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/use-NDI-in-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 922d16fe-3819-b8a1-3eec-d261632e2504
---

# Allow broadcast production in Teams meetings with NDI and SDI hardware - Microsoft Teams | Microsoft Learn

Teams offers two options for broadcasting Teams meeting content:

- Network Device Interface (NewTek NDI®) is a modern solution for connecting multiple media devices, such as studio cameras and mixers, without physical connections. Instead, NDI® technology enables connectivity over a local intranet, including on a local machine. This technology is a widely adopted industry standard for producing live content for streams, with significant awareness and adoption in the professional broadcast world.
- Serial Digital Interface (SDI), known for its reliable long-distance transmission, is a widely used technology for sending video through cables. It's a go-to choice in professional broadcasting because it carries uncompressed, high-quality video along with audio and other data. Hardware devices from AJA Video Systems and Blackmagic Design provide connectivity to legacy broadcast devices that use SDI.

NDI® and SDI technology is supported in all locales.

As an admin, you can allow your users to use NDI® and SDI for broadcast production in their meetings. For the most secure solution, don't turn on this policy as a global setting.

## 1. Turn on the broadcast production policy

To turn on NDI® and SDI broadcast features for a user, you can use the Teams admin center or PowerShell.

### Manage broadcast production in the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one.
3. Go to the **Audio & video** section.
4. Turn the **Broadcast production with NDI and SDI hardware** toggle **On**.
5. Select **Save**.

### Manage broadcast production in PowerShell

You can use the **`-ContentSharingInExternalMeetings`** parameter in the [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet to enable broadcast production for your users.

To allow users with this policy to use broadcast production, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowNDIStreaming $true
```

## 2. Instruct your users to turn on production capabilities

Users with an enabled **Broadcast production with NDI and SDI hardware** policy must turn on **Production capabilities** from **Settings** &gt; **App Permissions** in their specific client. For details on how your user can turn on production capabilities, see [Broadcasting audio and video from Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).