---
layout: Conceptual
title: Create a building map for Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cqd-building-mapping
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
ms.reviewer: mikedav, siunies, gageames, jamp
ms.date: 2025-09-15T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Learn how to create a building map that you can use to upload tenant and building data in Call Quality Dashboard (CQD).
locale: en-us
document_id: 0adc2a8b-be73-d2f4-a429-89fc1af2f346
document_version_independent_id: ccab7e69-ff8d-bdfe-722a-7b0b1782b290
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/CQD-building-mapping.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cqd-building-mapping
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/CQD-building-mapping.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: 4c662c98-ccc5-d3de-b269-1a328e0f0705
---

# Create a building map for Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn

In a Microsoft Teams or Skype for Business deployment, all clients are external. As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.

When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, with the assumption that you can only improve networks you can manage. By uploading subnet and building information, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network. This distinction is why it's important to create a building map for your organization and [upload it in Teams admin center](cqd-upload-tenant-building-data).

## Building mapping tools

There are many ways to map your organization's subnets. If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools). These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file. These tools can help with the following tasks:

1. Query AD Sites and Services, and create a building file based on the information contained within.
2. Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.
3. Validate an existing building file, checking for duplicates and overlaps.
4. Find unmapped subnets in CQD.