---
layout: Conceptual
title: Network settings for cloud voice features - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cloud-voice-network-settings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.topic: concept-article
ms.reviewer: mshaikh
ms.date: 2026-03-24T00:00:00.0000000Z
ms.service: msteams
ms.subservice: teams-calling
audience: admin
search.appverid: MET150
description: Learn about the network settings that you must configure for Location-Based Routing for Direct Routing and enhanced emergency services.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 664d4214-9f5d-d793-c9a3-9a75bc0e2c9b
document_version_independent_id: f9f04eb1-4a4c-4a60-e42f-ec57dfe0a12a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/cloud-voice-network-settings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cloud-voice-network-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/cloud-voice-network-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
platformId: cd6088be-2091-d3f1-0e7c-9d16a5a2339a
---

# Network settings for cloud voice features - Microsoft Teams | Microsoft Learn

Learn about network regions, network sites, network subnets, and trusted IP addresses.

These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan) and [dynamic emergency calling](configure-dynamic-emergency-calling). If you're deploying these cloud voice features in your organization, you must configure network settings for use with these features in Microsoft Teams.

This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling. Depending on the cloud voice feature and capability that you're deploying, you configure some or all of these settings. For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology).

Note that it can take some time (up to four hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.

Note

Any feature-specific requirements for network settings are documented in the configuration topics for that feature.

## Network region

A network region contains a collection of network sites. It interconnects various parts of a network across multiple geographic areas. For example, if your organization has many sites located in India, you can choose to designate "India" as a network region. Each network site must be associated with a network region.

The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services. If you already created network regions for one feature, you don't have to create new network regions for the other feature.

## Network site

A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus. Network sites are defined as a collection of IP subnets. Each network site must be associated with a network region.

## Network subnet

Each subnet must be associated with a specific network site. A client's location is determined based on the network subnet and the associated network site. You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.

Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated. When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.

For each network site, you should work with your network administrator to determine which IP subnets are assigned to which network site. For example, assume the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Assume Bob, who usually works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer gets an IP address in one of the four ranges that are allocated for New York; for example, 172.29.80.103.

## Trusted IP address

Trusted IP addresses are the internet external IP addresses of the enterprise network. They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.

If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located. A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings. (If the enterprise network has both IPv4 and IPv6 internet accessible external IP addresses, you must add both as trusted IP addresses.)

If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.

Important

Network configuration setting lookups are not supported with cloud proxy service deployments that modify the source IP addresses from Teams clients.