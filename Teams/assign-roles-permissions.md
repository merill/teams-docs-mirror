---
layout: Conceptual
title: Assign team owners and members in Microsoft Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/assign-roles-permissions
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: dansteve
ms.date: 2024-06-13T00:00:00.0000000Z
search.appverid: MET150
description: Learn to assign team owner and member roles and permissions in Microsoft Teams including permissions to create teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.collection:
- M365-collaboration
locale: en-us
document_id: 20423b44-629b-1bee-280c-fb55680cd33e
document_version_independent_id: a60f6a48-89d7-98b6-4245-4be171fd06fd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/assign-roles-permissions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: assign-roles-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/assign-roles-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4ef50b96-739a-bfc6-9536-acf71e9bb50c
---

# Assign team owners and members in Microsoft Teams admin center - Microsoft Teams | Microsoft Learn

**Owner** and **member** are the two user roles within Microsoft Teams. The user who creates a new team is granted owner status by default. Owners and members have different types of permissions and capabilities when interacting with a team and its channels. See [Overview of teams and channels in Microsoft Teams](teams-channels-overview) to learn more about roles in Teams.

Note

If a team is created from an existing Microsoft 365 group, permissions are inherited.

## Assign a user role in Teams admin center

1. In the Teams admin center, expand **Teams** and select **Manage teams**.
2. Select the team name under the display name column.
3. In the Members tab, you can add or remove members and assign owner and moderator roles to members.

## Restrict permission to create teams

All users with a mailbox in Exchange Online have permissions to create Microsoft 365 groups and a team within Microsoft Teams. Restrict users from creating new teams and Microsoft 365 groups by delegating group creation and management rights to a set of users. If this restriction is active, neither team owners or members can create new teams. For more information, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## User permissions based on assigned roles

The table below shows the difference in permissions between an owner and a member.

### Teams

| Teams tasks | Team Owner | Team Member |
| --- | --- | --- |
| Create/Delete team | Yes | No |
| Edit team name/description | Yes | No |
| Add members to private team | Yes | No |
| Add members to public team | Yes | Yes |
| Request to add new member | N/A | Yes |
| Promote/Demote user status | Yes | No |
| Leave team | Yes | Yes |
| Add/Remove apps | Yes | Yes, if enabled by team owner |

### Channels

| ***Standard channel tasks*** | **Team Owner** | **Team Member** |
| --- | --- | --- |
| Create/Delete channel | Yes | Yes, if enabled by team owner |
| Edit channel name/description | Yes | Yes, if enabled by team owner |
| ***Private channel tasks*** |  |  |
| Create channel | Yes | Yes, if enabled by team owner |
| Delete channel | Yes | No |
| Edit channel name/description | No | N/A |
| ***Shared channel tasks*** |  |  |
| Create channel | Yes | No |
| Delete channel | Yes | No |
| Edit channel name/description | No | No |