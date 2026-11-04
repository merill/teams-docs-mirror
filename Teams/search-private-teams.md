---
layout: Conceptual
title: Allow users to search for private teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/search-private-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: shubjain
ms.date: 2025-04-15T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-chat
audience: Admin
ms.custom:
- admindeeplinkTEAMS
- teams-chat-and-channels
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to allow users to search for private teams.
locale: en-us
document_id: ed9cd556-8328-6fd9-e5b8-1d9013604b74
document_version_independent_id: ed9cd556-8328-6fd9-e5b8-1d9013604b74
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/search-private-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: search-private-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/search-private-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 81e4f4aa-cff6-1d0a-5d95-4d77f2ddc9fb
---

# Allow users to search for private teams - Microsoft Teams | Microsoft Learn

By default, users can't search for and find private teams. You can allow users to find private teams by turning on **Private team discovery** in a Teams policy. Users for whom the policy is turned on can search for and find private teams and request to join them. Team owners can approve or deny the request.

## Manage private team discovery

You can allow or prevent private team discovery for users or groups in your organization by using a Teams policy.

To manage if users can search for private teams, complete the following steps:

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), select **Settings & policies**.
2. Select **Teams** and set **Discover private teams** to **On** or **Off**.

Policy changes may take several hours to take effect.

## Restrict private team discovery by using sensitivity labels

If you want to enable private team discovery but restrict the discovery of certain teams, such as those containing sensitive information, you can prevent private team discovery by using a sensitivity label. For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/en-us/purview/sensitivity-labels-teams-groups-sites#how-to-configure-groups-and-site-settings).