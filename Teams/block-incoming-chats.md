---
layout: Conceptual
title: Allow users to block Microsoft Teams chat messages - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/block-incoming-chats
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: degoh
ms.date: 2024-07-29T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-chat
audience: Admin
ms.custom: teams-chat-and-channels
ms.collection: 
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to allow users to block chats from people inside your organization.
locale: en-us
document_id: 2ad175ee-39b3-c33d-5c31-7496d349a24b
document_version_independent_id: 2ad175ee-39b3-c33d-5c31-7496d349a24b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/block-incoming-chats.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: block-incoming-chats
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/block-incoming-chats.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ff25e005-c8b7-3ade-4cb1-41ece9177e09
---

# Allow users to block Microsoft Teams chat messages - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

You can allow users to block new incoming chats from people in your organization. When someone initiates a chat, users who have this policy assigned to them can block that person. That person then can't communicate with the user. Users can also unblock people from their chat history.

This feature only affects 1:1 chats from other people inside your organization. (All users can [block chats from people outside your organization](https://support.microsoft.com/office/5b590992-c938-4ed9-933b-37ee1fb84d32).) This feature doesn't affect channel or meeting chats.

Users must be using the [Teams desktop client](teams-client-desktop-admin) or the web client to use this feature.

This feature requires Teams Premium.

Note

There is a known issue where blocking a user does not currently hide your presence status from the blocked user. While the blocked user cannot send messages, they may still be able to see presence information, such as Available or Away. We are actively working on a fix and will update this documentation as the improvement rolls out.

## Manage who can block new incoming chats

Configuring internal message blocking requires two admin controls:

- The **Priority account chat control** messaging setting determines if message blocking is available in your organization.
- The **Priority account chat control** messaging policy control determines if a user assigned to that policy can block new incoming chats.

To manage internal message blocking for your organization:

1. In the Teams admin center, expand **Messaging** and select **Messaging settings**.
2. Under **Advanced collaboration management**, set **Priority account chat control** to **On** or **Off**.
3. Select **Save**.

To manage internal message blocking for specific users or groups:

1. In the Teams admin center, expand **Messaging** and select **Messaging policies**.
2. Select the policy that you want to update or create a new one.
3. Set **Priority account chat control** to **On** or **Off**.
4. Select **Save**.

The messaging setting and the messaging policy must both be enabled for a user to be able to block new incoming chats.