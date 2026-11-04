---
layout: Conceptual
title: Network roaming policy - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/network-roaming-policy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-03-30T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.localizationpriority: High
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Learn how to manage settings for the Teams network roaming policy.
locale: en-us
document_id: 7379a119-c897-7808-5fe7-8e67ee43ba88
document_version_independent_id: 7379a119-c897-7808-5fe7-8e67ee43ba88
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/network-roaming-policy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: network-roaming-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/network-roaming-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ac425207-d407-defc-7f4a-e75aa5f64cf8
---

# Network roaming policy - Microsoft Teams | Microsoft Learn

In addition to managing video and media settings with meeting policies, you can dynamically control the use of the following attributes used by the Microsoft Teams client:

- IP video
- Media bit rate

The **TeamsNetworkRoamingPolicy** policy enables you to assign settings to network sites. The Teams client dynamically picks up the settings based on which network site it connects to. When the Teams client signs in from a network site with a roaming policy assigned, that policy is used. If there's no policy assigned, the values set in the meeting policy are used.

For more information about meeting policy audio and video settings, see [Meeting policy settings for audio and video](meeting-policies-audio-and-video).

## Configure TeamsNetworkRoamingPolicy

To configure **TeamsNetworkRoamingPolicy**, use the following PowerShell cmdlets:

- [Get-CsTeamsNetworkRoamingPolicy](/en-us/powershell/module/teams/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/en-us/powershell/module/teams/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/en-us/powershell/module/teams/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/en-us/powershell/module/teams/remove-csteamsnetworkroamingpolicy)

**TeamsNetworkRoamingPolicy** contains the following parameters:

- `AllowIPVideo` - This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 and group calls started by a user.
- `MediaBitRateKb` - This setting determines the total average media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.

After you configure the policy, assign it to one or more network sites by using the [Set-CsTenantNetworkSite](/en-us/powershell/module/teams/set-cstenantnetworksite) cmdlet as follows:

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

To remove a policy from a network site, use the following cmdlet:

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
```

To enable the network roaming policy for users who aren't enterprise voice enabled, you must also enable the AllowNetworkConfigurationSettingsLookup setting in [Teams Meeting Policy](/en-us/powershell/module/teams/Set-csteamsmeetingpolicy). This setting is off by default.

For more information about creating network sites, see [Network settings for cloud voice features](cloud-voice-network-settings).

## Examples

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## Supported clients

- Windows
- macOS desktop