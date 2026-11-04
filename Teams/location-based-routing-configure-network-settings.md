---
layout: Conceptual
title: Configure network settings - Location-Based Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/location-based-routing-configure-network-settings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
ms.topic: article
ms.reviewer: filippse
ms.date: 2026-09-18T00:00:00.0000000Z
audience: admin
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
description: Learn how to create and set up network settings for Location-Based Routing.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 7c64c973-c329-2cd4-d4c3-258f254fcccd
document_version_independent_id: fb3f5ebd-9bab-0a02-ba1f-d30445450d87
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/location-based-routing-configure-network-settings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: location-based-routing-configure-network-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/location-based-routing-configure-network-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e88940c2-6038-5b84-32a9-3748c08847e6
---

# Configure network settings - Location-Based Routing - Microsoft Teams | Microsoft Learn

This article describes how to configure network settings for Location-Based Routing. This article applies to Direct Routing and Operator Connect for India.

- **If you have Direct Routing,** see [Plan Location-Based Routing for Direct Routing](location-based-routing-plan) to review other steps you need to take before you configure network settings.
- **If you have Operator Connect for India**, see [Plan and configure Location-Based Routing for Operator Connect for India](location-based-routing-india-plan) before configuring your network settings.

## Define network regions

A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas. For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology).

## Define network sites

A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus. You must associate each network site in your topology with a network region. For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology).

- **For Direct Routing**, a best practice for Location-Based Routing is to create a separate site for each location that has unique Public Switched Telephone Network (PSTN) connectivity. You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing. For example, you might want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.
- **For Operator Connect for India**, you will define you network sites, but you do not need to enable sites for Location-Based Routing.

## Define network subnets

Each subnet must be associated with a specific network site. You can associate multiple subnets with the same network site, but you can't associate multiple sites with the same subnet. For steps on how to configure network subnets, see [Manage your network topology for cloud features in Teams](manage-your-network-topology).

For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined site to restrict toll bypass.

This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed. Both IPv6 and IPv4 subnets are supported. When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address. If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.

## Define trusted IP addresses (external subnets)

Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network. For steps on how to configure trusted IP addresses, see [Manage your network topology for cloud features in Teams](manage-your-network-topology).

If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.

If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and the following rules apply:

- **For Direct Routing users**, any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.
- **For Operator Connect for India users**, any PSTN calls to or from a user at an unknown location are blocked.