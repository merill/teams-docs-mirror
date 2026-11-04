---
layout: Conceptual
title: Configure external meetings and chat with Skype for Business Server - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/external-meetings-skype-for-business-server-hybrid
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: jtremper
author: jacktremper
manager: pamgreen
ms.reviewer: nas, pbafna
ms.date: 2024-06-28T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
- Tier2
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- chat-teams-channels-revamp
ms.localizationpriority: Medium
description: Learn how to configure Skype for Business Server for external chat and meetings with other Microsoft 365 organizations and external chat and calls with Skype users.
locale: en-us
document_id: f15e2650-bbcc-4ae2-5b37-1063d1cde47b
document_version_independent_id: f15e2650-bbcc-4ae2-5b37-1063d1cde47b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/external-meetings-skype-for-business-server-hybrid.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: external-meetings-skype-for-business-server-hybrid
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/external-meetings-skype-for-business-server-hybrid.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 676f59f6-e916-feb9-49a4-440167965ae9
---

# Configure external meetings and chat with Skype for Business Server - Microsoft Teams | Microsoft Learn

If you're using Skype for Business Server by itself or in a hybrid configuration with Teams in Microsoft 365, you can configure chat and meetings with people in other Microsoft 365 organizations and chat and calling with Skype users.

Note

Chat with unmanaged Teams users (those not connected to an organization) is not supported for on-premises only organizations. To configure this for Teams in Microsoft 365, see [Manage external meetings and chat with people and organizations using Microsoft identities](trusted-organizations-external-meetings-chat).

## Configure external meetings and chat with other Microsoft 365 organizations

To allow chatting and meetings with other Microsoft 365 organizations, configure your Skype for Business Server environment as follows:

- Ensure federation is enabled in `CsAccessEdgeConfiguration`.
- Ensure federation for the user is enabled through `ExternalAccessPolicy` (either through the global policy, site policy, or user assigned policy).
- If you are not using open federation, ensure the target domain is listed in `AllowedDomains`.

If you are using Microsoft 365 with Skype for Business Server in a hybrid configuration, configure external meetings and chat in Microsoft 365 as described in [Manage external meetings and chat with people and organizations using Microsoft identities](trusted-organizations-external-meetings-chat). Note that organizations that you're communicating with must also trust your organization.

## Configure external chat and calling with Skype users

To allow chatting and calls with Skype users, configure your Skype for Business Server environment as follows:

- Ensure Skype is enabled as a federated partner.
- Ensure `EnablePublicCloudAccess=true` for the user through `ExternalAccessPolicy` (either via global policy, site policy, or user assigned policy).

If you are using Microsoft 365 with Skype for Business Server in a hybrid configuration, configure external chat and calling with Skype users in Microsoft 365 as described in [Manage external meetings and chat with people and organizations using Microsoft identities](/en-us/microsoftteams/trusted-organizations-external-meetings-chat#manage-chat-and-calls-with-skype-users).