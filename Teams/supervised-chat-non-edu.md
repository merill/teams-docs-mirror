---
layout: Conceptual
title: Use supervised chats for non-educational tenants - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/supervised-chat-non-edu
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: angch
ms.date: 2025-03-13T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-chat
audience: Admin
ms.custom:
- chat-teams-channels-revamp
- teams-chat-and-channels
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about supervised chats for non-educational tenants in Microsoft Teams meetings.
ms.collection:
- M365-collaboration
locale: en-us
document_id: 82f0c686-160c-100f-6d37-55033048e8d1
document_version_independent_id: 65b5b49b-5881-eb26-bfd0-4abb7eecb899
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/supervised-chat-non-edu.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: supervised-chat-non-edu
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/supervised-chat-non-edu.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3f8dfaf5-e524-8e0b-e240-c781f0878888
---

# Use supervised chats for non-educational tenants - Microsoft Teams | Microsoft Learn

Supervised chat allows designated supervisors to initiate chats with anyone in their organization and blocks restricted users from starting new chats unless an appropriate supervisor is present. When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving restricted users are properly supervised.

These limitations are only applied to new private chats that are created after supervised chat is fully enabled. They don't apply to existing private chats, meetings chats, or channels.

Supervised chat is tailored for educational institution needs, but it's also available to non-educational tenants.

Note

Supervised chat protects new chats created after the feature is enforced. It doesn't protect existing chats.

## Enable supervised chat

Note

Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted restricted user access to unsupervised chats.

### Define chat permission roles for each user in your environment

For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role. There are three roles that a user can have assigned:

- **Full permissions**: This role should be assigned to the chat supervisors in your environment. They can start chats with any user within your environment. Users with full permissions are expected to supervise the chats they participate in. They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.
- **Limited permissions**: This role is ideal for staff members who should only have supervised access to restricted users. They can start chats with any full or limited users but can't start chats with restricted users. If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation. This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.
- **Restricted permissions**: This role is ideal for users who need to be supervised. They can only start chats with users who have full permissions. They can participate in any conversation that a user with full permissions invites them to. In federated chat cases, only a user with full permissions who is from the restricted user's tenant can add restricted users.

To set your users' chat permission role, use the **Chat permissions role** policy found within your Messaging policy options in the Teams admin portal. You can use PowerShell to define roles using the `ChatPermissionRole` policy with the values `Full`, `Limited`, or `Restricted`. This policy is under [CsTeamsMessagingPolicy](/en-us/powershell/module/teams/set-csteamsmessagingpolicy).

Roles can't be assigned to guests in your tenant. Guests are assigned the limited role.

## Allow supervised chat

Supervised chat is disabled by default for your tenant. After you set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Teams** &gt; **Teams Settings** and setting **Role-based chat permissions** policy to **On**. You can also use PowerShell to enable Supervised Chat by setting `AllowRoleBasedChatPermissions` to `true`. This cmdlet is under [CsTeamsClientConfiguration](/en-us/powershell/module/teams/set-csteamsclientconfiguration).

Supervised chat must be enabled for all users in the tenant and can't be enabled for only a portion of your users.

**Enable chat**:

Enable chat for all your users using the existing Chat policy available in Teams admin center.

**Maintain supervised chats**:

After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:

- Assign appropriate roles to any new users that join your tenant. By default, users are assigned a restricted role.
- If a user with full permissions leaves or is removed from a tenant, the chats they were supervising are left unattended. Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised. Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.