---
layout: Conceptual
title: More about Calling Line ID and Calling Party Name - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/more-about-calling-line-id-and-calling-party-name
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-09-21T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
ms.subservice: teams-calling
description: Learn about Calling Line ID and Calling Party Name.
locale: en-us
document_id: 460aeaa2-0475-1a17-a9b1-d8e44f7f6e21
document_version_independent_id: 3c47839b-40f4-f94d-0eef-1d9ff7c9402b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/more-about-calling-line-ID-and-calling-party-name.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: more-about-calling-line-id-and-calling-party-name
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/more-about-calling-line-ID-and-calling-party-name.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 44149453-1696-80f1-d413-142cffeb69a1
---

# More about Calling Line ID and Calling Party Name - Microsoft Teams | Microsoft Learn

Caller ID consists of two user-facing pieces of information:

- A phone number - typically referred to as CLID or calling line ID.
- Calling party name - typically referred to as CNAM.

When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier). The CNAM information for the call might or might not be routed with the call because this information depends on how the country/region has implemented CNAM (if at all). The reliability of CNAM delivery with the call varies depending on the country/region and carriers that handle the call - either as an intermediary or a terminating carrier.

CLID and CNAM transmission is the responsibility of the terminating carrier. The terminating carrier must support CLID and CNAM functionality and provide up-to-date records for both values. Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier. If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.

Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases - as in the United States. In countries/regions where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call. Microsoft currently doesn't support originating CNAM information in countries/regions other than the United States.