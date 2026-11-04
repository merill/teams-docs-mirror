---
layout: Conceptual
title: Considerations for Teams Phone Mobile - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/considerations-teams-phone-mobile
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
ms.date: 2024-05-08T00:00:00.0000000Z
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
ms.custom: 
description: Learn about emergency calling considerations for Teams Phone Mobile.
locale: en-us
document_id: 115c3ed7-a914-61ac-b90d-c697ec6761b2
document_version_independent_id: 115c3ed7-a914-61ac-b90d-c697ec6761b2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/considerations-teams-phone-mobile.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: considerations-teams-phone-mobile
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/considerations-teams-phone-mobile.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e7767220-f693-e27f-720a-23aede317f8d
---

# Considerations for Teams Phone Mobile - Microsoft Teams | Microsoft Learn

This article describes considerations for emergency calling for Teams Phone Mobile users. Before reading this article, see emergency calling concepts and definitions in [Plan and manage emergency calling](what-are-emergency-locations-addresses-and-call-routing).

To find out if Teams Phone Mobile is the right solution for your business, see [PSTN connectivity options](pstn-connectivity) and [Plan for Teams Phone Mobile](operator-connect-mobile-plan).

## Emergency call enablement for Teams Phone Mobile

Each Teams Phone Mobile user is automatically enabled for emergency calling. Emergency calls are routed automatically to the Teams Phone Mobile carrier for a given number.

The ability for a tenant admin to set the registered address for a Teams Phone Mobile user depends on the capabilities assigned to the number when the carrier uploads them into a customer's inventory. The tenant administrator may or may not be required--or able--to set, modify, or delete the emergency location of a user.

When calls are made through the native dialer of the SIM-enabled smartphone, your operator may use geographic coordinates or cell tower location to approximate the emergency location for assistance.

## Dynamic emergency calling for Teams Phone Mobile

Dynamic emergency calling for Teams Phone Mobile provides the capability to configure and route emergency calls based on the current location of the Teams client. The ability to automatically route to the appropriate Public Safety Answering Point (PSAP), or to notify security desk personnel, varies depending on the country/region of the Teams user.

Dynamic location for routing emergency calls is supported in the United States as follows.

- If a Teams client for a United States user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call is automatically routed to the PSAP in the serving area of the address.
- If a Teams client for a United States user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call. However, the call is screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.

Dynamic location for routing emergency calls is supported in Canada the same as in the United States with the following exceptions: all emergency calls are screened nationally before being transferred to the PSAP.

For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling).

## Emergency call routing for Teams Phone Mobile

Your Teams Phone Mobile operator manages all emergency calls made through your SIM-enabled Smartphone’s cellular dialer **and** from your Teams app. The mobile operator may use multiple technologies to approximate emergency location for assistance, like geographic coordinates or which cell towers are handling the call.

**Your Teams Phone Mobile operator is responsible for ensuring all emergency calls connect to the correct emergency services based on your location, regardless of whether the call is made from your device's native cellular dialer or made from the Teams app.** Contact your operator for more details.

When a Teams Phone Mobile user dials an emergency number using any Microsoft Teams client other than the Teams app on your SIM-enabled Smartphone, how the call is routed to the PSAP depends on the following:

- Whether the emergency address is dynamically determined by the Teams client
- Whether the emergency address is the registered address associated with the user's phone number
- The emergency calling network of that country/region
- In the United States and Canada, dynamic routing is part of the carrier's service. You don't need to procure this service from another service provider.
- If a Teams client is located at a tenant-defined dynamic emergency location:

    - In the United States, emergency calls from that client are automatically routed to the PSAP serving that geographic location.
    - In Canada, all emergency calls are screened by a national call center before transferring the call to the PSAP serving that geographic location.
- If a Teams client isn't located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.
- If an emergency caller is unable to update their emergency location to the screening center, the call is transferred to the PSAP serving the caller's registered address.