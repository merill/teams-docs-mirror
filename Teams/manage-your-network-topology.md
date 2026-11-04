---
layout: Conceptual
title: Manage your network topology for cloud voice features in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-your-network-topology
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
ms.date: 2026-03-24T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to configure your network topology for cloud voice features in Microsoft Teams.
locale: en-us
document_id: eef19426-f330-e8ea-dd48-571954b23176
document_version_independent_id: d4357caa-b5c6-a034-3b81-f409678f5ee3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-your-network-topology.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-your-network-topology
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-your-network-topology.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 2df10005-2458-f43e-97da-b3b5915a4feb
---

# Manage your network topology for cloud voice features in Microsoft Teams - Microsoft Teams | Microsoft Learn

If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan) or [dynamic emergency calling](configure-dynamic-emergency-calling), you must configure network settings for use with these cloud voice features in Microsoft Teams.

Network settings are used to determine the location of a Teams client. The settings include network regions, network sites, subnets, and trusted IP addresses. Depending on the cloud voice feature and capability that you're deploying, you configure some or all of these settings. To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings).

You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.

Note that it can take some time (up to four hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.

Note

Network configuration data may be used across Microsoft 365 services to provide additional services your organization has subscribed to.

## Configure network settings in the Microsoft Teams admin center

You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.

You can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-Based Routing, and assign emergency policies to the site. You can also add network regions that can be used globally for all sites.

#### Add and configure a network site

1. In the left navigation of the Microsoft Teams admin center, go to **Locations** &gt; **Network topology**, and then select the **Network sites** tab.
2. Select **Add**, and then enter a name and description for the site.
3. To associate the site with a network region, select **Add network region**, select an existing region or select **Add** to add a region, and then select **Link**.
4. To enable Location-Based Routing for the site, turn on **Location based routing**.
5. To assign emergency services policies to the site, do one or both of the following:

    - If your organization uses Calling Plans, Operator Connect, or Direct Routing, under **Emergency calling policy**, select the policy that you want.
    - If your organization deployed Direct Routing, under **Emergency call routing policy**, select the policy that you want.
6. (Optional) If you want to change the behavior for clients in this site, you can use the network roaming policy. Under **Network roaming policy**, select the policy that you want. For more information, see [Manage video and media settings with the network roaming policy](network-roaming-policy).
7. To associate a subnet to the site, under **Subnets**, select **Add subnets**. Specify the IP version, IP address, network range, add a description, and then select **Apply**. Each subnet must be associated with a specific site.
8. Select **Save**.

#### Modify a network site

1. In the left navigation of the Microsoft Teams admin center, go to **Locations** &gt; **Network topology**, and then select the **Network sites** tab.
2. Select the site by clicking to the left of the site name, and then select **Edit**.
3. Make the changes that you want, and then select **Save.**

### Manage external trusted IP addresses

You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center. You can add an unlimited number of external trusted IP addresses.

#### Add a trusted IP address

1. In the left navigation of the Microsoft Teams admin center, go to **Locations** &gt; **Network topology**, and then select the **Trusted IPs** tab.
2. Select **Add**.
3. In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then select **Apply**.

#### Edit a trusted IP address

1. In the left navigation of the Microsoft Teams admin center, go to **Locations** &gt; **Network topology**, and then select the **Trusted IPs** tab.
2. Select the IP address by clicking to the left of it, and then select **Edit**.
3. In the **Edit trusted IP address** pane, make the changes that you want, and then select **Apply**.

## Configure network settings using PowerShell

To complete the steps in this section, you need some familiarity with PowerShell cmdlets. To learn more, see [Teams PowerShell Overview](teams-powershell-overview).

### Define network regions

To define network regions, use the [New-CsTenantNetworkRegion](/en-us/powershell/module/teams/New-CsTenantNetworkRegion) cmdlet. Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions; the CentralSite &lt;site ID&gt; parameter is optional.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

This example creates a network region named India:

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

For more information, see [Set-CsTenantNetworkRegion](/en-us/powershell/module/teams/set-cstenantnetworkregion).

### Define network sites

To define network sites, use the [New-CsTenantNetworkSite](/en-us/powershell/module/teams/new-cstenantnetworksite) cmdlet. Each network site must be associated with a network region.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

The following example creates two new network sites, Delhi and Hyderabad, in the India region:

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

The following table shows the network sites defined in this example:

| - | Site 1 | Site 2 |
| --- | --- | --- |
| Site ID | Site 1 (Delhi) | Site 2 (Hyderabad) |
| Region ID | Region 1 (India) | Region 1 (India) |

For more information, see [Set-CsTenantNetworkSite](/en-us/powershell/module/teams/set-cstenantnetworksite).

### Define network subnets

To define network subnets and associate them to network sites, use the [New-CsTenantNetworkSubnet](/en-us/powershell/module/teams/new-cstenantnetworksubnet) cmdlet. You can associate each network subnet with one site only.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

The following example creates an association between subnet 192.168.0.0 and the Delhi network site, and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site:

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

The following table shows the subnets defined in this example:

| - | Site 1 | Site 2 |
| --- | --- | --- |
| Subnet ID | 192.168.0.0 | 2001:4898:e8:25:844e:926f:85ad:dd8e |
| Mask | 24 | 120 |
| Site ID | Site (Delhi) | Site 2 (Hyderabad) |

For multiple subnets, you can import a CSV file by using a script such as the following:

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

In this example, the CSV file looks like the following:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

For more information, see [Set-CsTenantNetworkSubnet](/en-us/powershell/module/teams/set-cstenantnetworksubnet).

### Define external subnets (external trusted IP addresses)

To define external subnets and assign them to the tenant, use the [New-CsTenantTrustedIPAddress](/en-us/powershell/module/teams/new-cstenanttrustedipaddress) cmdlet. You can define an unlimited number of external subnets for a tenant.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

For example:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

For more information, see [Set-CsTenantTrustedIPAddress](/en-us/powershell/module/teams/set-cstenanttrustedipaddress).

## Enable network roaming policies

Once you configure your network roaming policies, you need to enable **Network configuration lookup**\* within each of your **Meeting Policies** in the Teams admin center under **Meetings &gt; Meeting Policies.**

You can either edit the global policy or create a new policy and assign the policy to specific users.