---
layout: Conceptual
title: Troubleshoot connectivity issues with Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/connectivity-issues
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: 
ms.date: 2017-08-10T00:00:00.0000000Z
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: troubleshooting
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Troubleshoot connectivity issues with the Microsoft Teams client, primarily caused by the firewall or proxy connection, and learn how to fix it.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 9777f6b3-740c-170c-3d16-5524fda9b1c6
document_version_independent_id: b80035a2-ea72-4d2c-ccb0-ac047ba8378a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/connectivity-issues.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: connectivity-issues
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/connectivity-issues.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d933932b-2500-f9c8-0500-bb13c461cd09
---

# Troubleshoot connectivity issues with Teams client - Microsoft Teams | Microsoft Learn

Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity. Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting. For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article. The following scenarios require specific URLs and ports to be opened in the firewall.

- Authentication
- Microsoft Teams Client Connectivity
- Collaboration
- Media
- Shared Services
- Third Party Integration
- Skype for Business Interoperability
- Skype for Business Client Interoperability

## When Teams is offline or in low bandwidth conditions

The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions. Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online. If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages. We're working on adding this functionality to new chats and will update this documentation when that's available.