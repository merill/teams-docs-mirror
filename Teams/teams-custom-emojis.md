---
layout: Conceptual
title: Custom emojis in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-custom-emojis
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: article
ms.date: 2026-10-01T00:00:00.0000000Z
ms.service: msteams
ms.subservice: teams-chat
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: 
ms.custom: teams-chat-and-channels
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about adding custom emojis to Microsoft Teams chats.
ms.localizationpriority: medium
locale: en-us
document_id: 474da111-913f-634a-c7bd-7d32caa9a09f
document_version_independent_id: 474da111-913f-634a-c7bd-7d32caa9a09f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-custom-emojis.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-custom-emojis
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-custom-emojis.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 847405c3-c1fa-81c1-f821-55ad8f73f1f3
---

# Custom emojis in Microsoft Teams - Microsoft Teams | Microsoft Learn

Microsoft Teams now allows users to add their own custom emojis and reactions by uploading an image or GIF file. These emojis and reactions are also accessible to all users in the tenant alongside the standard Teams emojis and reactions. Up to 5,000 custom emojis can be added per tenant. This feature is currently not available for EDU tenants.

The new custom emojis and reactions feature will be turned on by default. Users in the tenant will be able to upload emojis. You can preemptively turn this feature off or restrict which users can create new emojis via the Teams Admin Center controls described in this article.

Note

Custom emojis are available in cross-tenant and federated scenarios. Users outside of your tenant can't see your tenant's custom emojis in their own emoji menu, however, they can view any custom emojis that are sent to them. Furthermore, any AAD-authenticated user can access or download an emoji asset if they've obtained the content URL and image ID.

## How to use this feature

Custom emojis and reactions are found in the emoji and reaction menus in the **Custom** category. Users with upload abilities can add new content through the **Plus** (**+**) button. Users with delete abilities can select any custom emoji to delete.

Note

Deleted emojis may take up to 24 hours to reflect for all users in the tenant. Users may clear the cache on their own devices to see the removal sooner.

## How to manage this feature

This feature can be managed through the Teams admin center. Admins have access to the following controls:

- Turn the feature on/off for the whole tenant via the Messaging Settings page (on by default).
- Set which users can create new emojis via the Messaging Policy groups (on for all users by default).
- Set which users can delete emojis via the Messaging Policy groups (off for all users except admins by default).

In the Teams Admin Center controls, go to **Messaging Settings** section and toggle the **use custom emojis** option, found under the **Custom emojis** section, on or off.

The **Messaging policies** section of the Teams admin center will allow you to turn the **Upload custom emojis** and **Delete custom emojis** settings on or off.

Note

Uploading custom emojis is enabled for all users by default, and the deletion of custom emojis is enabled for Admins by default.