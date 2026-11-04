---
layout: Conceptual
title: Proxy servers for Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/proxy-servers-for-skype-for-business-online
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: jastark
ms.date: 2026-05-25T00:00:00.0000000Z
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: This article provides information about using a proxy server with Microsoft Teams.
locale: en-us
document_id: 826084d1-06f7-e837-bcfc-d86d427288f6
document_version_independent_id: 9b36168e-d398-0188-c510-4dc5dd5f9563
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/proxy-servers-for-skype-for-business-online.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: proxy-servers-for-skype-for-business-online
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/proxy-servers-for-skype-for-business-online.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7b373a9e-2215-ac74-3c40-9805c26d19c4
---

# Proxy servers for Teams - Microsoft Teams | Microsoft Learn

This article provides guidance about using a proxy server with Microsoft Teams.

## Microsoft 365 connectivity

High quality, low latency connectivity is key to achieving call quality within Microsoft Teams.

We recommend that the path between the end user’s device and Microsoft 365 is as short and direct as possible and uses local Internet egress that's close to the end user, this enables traffic to quickly reach the closest Microsoft network service front door location.

## Not using a proxy server is recommended

Many organizations utilize proxy servers today within their network. As Microsoft Teams media traffic is already encrypted, passing this traffic through a proxy server doesn't make the traffic any more secure.

Proxies can also cause issues. Performance-related problems can be introduced to the environment through latency and packet loss by attempting to route Teams traffic through a proxy server. These issues can occur if the proxy can't handle the traffic volume or routes traffic to a Microsoft network service front door location that is farther from the end user.

Issues such as these result in a negative experience within Teams.

We recommend that Teams traffic bypasses proxy server infrastructure, including SSL inspection. You can achieve this by placing Teams Phones and Teams Rooms devices on a dedicated VLAN with direct internet access.

## Windows-based Teams devices

Windows-based Teams meeting rooms, and Surface Hubs support some proxy servers, but don't support proxy servers that require authentication.

We recommend that these devices bypass your proxy infrastructure and access Microsoft 365 services via your firewall.

## Android-based Teams devices

Android-based Teams devices, including Teams phones, panels, displays, and boards don't support authenticated proxy servers or tenant restrictions. Contact your OEM partner for details on unauthenticated proxy support.

We recommend that these devices bypass your proxy infrastructure and access Microsoft 365 services via your firewall.

## If you need to use a proxy server

Some organizations have no option to bypass a proxy for Teams traffic. If that's the case for you, the problems mentioned earlier need to be kept in mind.

Note

If you use a privately signed certificate on your proxy infrastructure (commonly used for SSL inspection), you need to install the privately signed certificate and the certificate chain on the Teams meeting room device to allow the device to trust the certificate. Installing privately signed certificates on Teams phones and other Android-based Teams devices isn't supported.

Microsoft also strongly recommends:

- Using local, external DNS resolution (some cloud-based proxy solutions can cause DNS resolution to occur in another location).
- Ensuring the path between the Teams device and our service is as short and direct as possible
- Using direct UDP-based routing rather than relying on TCP-based routing for media
- Allowing UDP traffic for Teams Media (3478-3481) through your firewall
- Allowing all required URLs and IPs, including those for Azure, Office 365, Intune, and Teams Rooms Pro (where used) through your firewall.
- Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network)

Following this guidance helps minimize potential problems.

## Recommendation for Teams events optimized for large audiences and Teams view-only meetings

Attendees in Teams events [optimized for large audiences](plan-events) (such as town halls) and Teams view-only meetings receive the stream via TCP HTTPS. We recommend that you bypass proxy servers and disable SSL inspection for the following URLs:

- Commercial cloud

    - \*.ml.cdn.office.net
    - \*.ml.teams.microsoft.com
    - \*.ml.communications.svc.cloud.microsoft
    - \*.ml.communications.svc.static.microsoft
- Government clouds

    - \*.ml.gcc.teams.microsoft.com
    - \*.ml.dod.teams.microsoft.us
    - \*.ml.gov.teams.microsoft.us