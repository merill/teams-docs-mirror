---
layout: Conceptual
title: Manage channel policies in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: jastark
ms.date: 2026-07-14T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
- chat-teams-channels-revamp
- teams-chat-and-channels
description: Learn how to use and manage teams channel policies in your organization to control what users can do in teams and channels.
locale: en-us
document_id: fd13cd2b-3dca-1b7c-9970-c0f8c2348712
document_version_independent_id: 318c6208-531a-3600-e45b-c43ea845db86
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 411a13c6-62d7-f71a-c86e-34d399159eb9
---

# Manage channel policies in Microsoft Teams - Microsoft Teams | Microsoft Learn

As an admin, you can use policies in Microsoft Teams to control what users in your organization can do in teams and channels. For example, you can set whether users are allowed to create private or shared channels.

You manage teams policies by going to **Teams** &gt; **Teams policies** in the Microsoft Teams admin center. You can use the global (Org-wide default) policy or create and assign custom policies. Users in your organization will automatically get the global policy unless you create and assign a custom policy.

You can edit the global policy or create and assign a custom policy. After you edit the global policy or assign a policy, it may take 24 hours for changes to take effect.

Note

To access this policy in the new experience, navigate to Settings & policies -&gt; Custom Policies for users and groups -&gt; Teams. For more details, refer to [Unified policies and settings management](/en-us/microsoftteams/unified-policies-settings-management-teams-admin-center).

## Channel policies

You can refer to the following document to learn about the policies available for Teams - [Allow users to search for private teams](/en-us/microsoftteams/search-private-teams). The following policies are available for channels in Teams:

| Policy | Description |
| --- | --- |
| **Create private channels** | When **On**, team owners and members can create private channels. (Team owners can control if members can create private channels in each team.) |
| **Create shared channels** | When **On**, team owners can create shared channels. Teams apps that are available for your organization are also available in shared channels. |
| **Invite external users to shared channels** | When **On**, owners and members of shared channels can invite external participants from organizations where a cross-organization trust has been configured. Teams policies for your organization apply to these channels. |
| **Join external shared channels** | When **On**, users can participate in shared channels created by other organizations where a cross-organization trust has been configured. Teams policies for the other organization apply to these channels. |

## Create a custom teams policy

1. In the left navigation of the Microsoft Teams admin center, go to **Teams** &gt; **Teams policies**.
2. Click **Add**.
3. Enter a name and description for the policy.

    ![Screenshot of teams policy settings.](media/teams-policies.png)
4. Turn on or turn off the settings that you want, and then click **Save**.
5. Click **Save**.

## Edit a teams policy

You can edit the global policy or any custom policies that you create.

1. In the left navigation of the Microsoft Teams admin center, go to **Teams** &gt; **Teams policies**.
2. Select the policy by clicking to the left of the policy name, and then click **Edit**.
3. Turn on or turn off the settings that you want, and then click **Save**.

## Assign a custom teams policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](/en-us/microsoftteams/assign-policies-users-and-groups)