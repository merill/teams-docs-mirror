---
layout: Conceptual
title: Configure an Exchange hybrid organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/exchange-hybrid-organization
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.date: 2017-09-25T00:00:00.0000000Z
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
description: Learn how to configure an Exchange hybrid organization for use with Microsoft Teams to ensure Group memberships are synchronized.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 20c0a619-c505-73a3-d815-58b384dc9a61
document_version_independent_id: 78b91880-6d1e-a9dc-6099-7a0a15b96a4a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/Exchange-hybrid-organization.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: exchange-hybrid-organization
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/Exchange-hybrid-organization.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/cf9b82c5-b6dc-45f3-b005-b1bc5fc03bea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0c85d34e-bfd2-4466-957c-f0b61e9692df
platformId: 3c277c63-2ed5-04f2-8904-b7f0b849fd3d
---

# Configure an Exchange hybrid organization - Microsoft Teams | Microsoft Learn

Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Microsoft Entra Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](/en-us/exchange/hybrid-deployment/set-up-microsoft-365-groups).