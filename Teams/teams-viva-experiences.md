---
layout: Conceptual
title: Manage Viva Engage experiences in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-viva-experiences
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: kafkadesign
ms.author: v-lilkafka
manager: v-jesserowe
ms.reviewer: adriennet
ms.topic: how-to
ms.date: 2026-01-26T00:00:00.0000000Z
ms.service: msteams
ms.subservice: teams-chat
audience: admin
ms.collection:
- M365-collaboration
ms.custom:
- admindeeplinkTEAMS
- teams-chat-and-channels
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Learn about how to manage Viva Engage experiences in Microsoft Teams.
locale: en-us
document_id: 78f57061-2a53-d7f8-e73f-97baf430a52e
document_version_independent_id: 78f57061-2a53-d7f8-e73f-97baf430a52e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-viva-experiences.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-viva-experiences
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-viva-experiences.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e4f48d48-dfb7-4973-a019-e504674667cb
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/495840e0-c52f-49d2-a584-185aefeb98c7
platformId: e6cefe67-e675-0af6-77d5-3c5a5338bfb2
---

# Manage Viva Engage experiences in Microsoft Teams - Microsoft Teams | Microsoft Learn

Note

Engage storylines in Teams is generally available. Engage communities in Teams is currently in public preview. Features in public preview might not be complete and could undergo changes before the public GA release. They're provided for evaluation purposes only. For more information about Engage communities in Teams, see [Getting started with Viva Engage Communities in Microsoft Teams](https://support.microsoft.com/en-us/office/getting-started-with-viva-engage-communities-in-microsoft-teams-b9fa52b8-4d1f-4ed4-b285-03e2537d3dbe).

Viva Engage unites your organization, allowing people to connect with leaders, coworkers, and communities. With Viva Engage, your users can generate ideas, share their work and experiences, and find connection at work.

Now, Viva Engage integrates into your users' Teams workflows. This article outlines the technical details of the integration of Viva Engage experiences into Teams and advises IT admins on feature management.

## Admin requirements for Viva Engage experiences in Teams

Before rolling out Viva Engage experiences to Teams, observe the following guidelines to ensure Viva Engage experiences are accessible to your users:

1. Ensure that your tenant doesn't block [Viva Engage's IPs and URLs](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges).
2. Enable sign-ins for the Office 365 Viva Engage service in Microsoft Entra ID:
    1. Sign in to the [Microsoft Entra admin center](https://go.microsoft.com/fwlink/p/?linkid=2067268).
    2. Go to **Identity** &gt; **Applications** &gt; **Enterprise Applications** &gt; **Viva Engage** &gt; **Properties**.
    3. Select **Yes** for the **Enabled for users to sign-in?** option.

### User requirements for Viva Engage experiences in Teams

To access Engage features, Teams users must have the following licenses:

- A Microsoft 365 license
- A Microsoft Teams license
- Access to [Viva Engage either with or without Viva Engage license enforcement](/en-us/viva/engage/setup#set-up-licensing-for-viva-engage).

### Current limitations of Viva Engage experiences in Teams

The following Engage features and activities are usable only in the Viva Engage App or web experience:

- Assign leaders in Viva Engage
- Assign and manage delegates
- Manage campaigns and Topics pages
- Create communities
- Several right rail features, such as community campaigns and events, aren't currently supported.

Engage experiences in Teams aren't available for educational (EDU) tenants, or for tenants that don't support the Engage app, such as special clouds, GCC, and GCC-H.

Engage experiences in Teams aren't usable for organizations that configure and use [segmentation](/en-us/viva/engage/engage-segmentation/engage-segmentation) in their network. For [multi-tenant organizations](/en-us/entra/identity/multi-tenant-organizations/overview) (MTOs), members of hub tenants can see MTO communities in the Teams navigation. Members of spoke tenants can't see MTO communities.

### Data handling of Viva Engage experiences in Teams

Viva Engage content in Teams supports [Engage security and compliance standards](/en-us/viva/engage/manage-security-and-compliance/security-and-compliance).

## How to set Viva Engage experiences in Teams

**Viva Engage experiences in Teams** include communities and storylines. Both are enabled by default across your organization, and each has its own setting so it can be disabled independently in Teams.

Note

**What's happening across your organization** doesn't have a separate setting. To prevent community content from appearing in this section, turn off the **Communities** setting. To prevent storyline content from appearing, turn off the **Storylines** setting.

**Set the communities experience in Teams**

To change the communities setting, complete the following steps: 

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) with your admin credentials.
2. In the left-rail menu, select **Settings & policies**.
3. Select either **Global (Org-wide default) settings** or **Custom policies for users & groups**.
4. Scroll to the **Messaging** section and select **Messaging**.
5. On the **Messaging settings** page, find the **Viva Engage** section.
6. To enable **communities in Teams**, switch on the toggle.
7. Choose **Save**.

**Set the storylines experience in Teams**

To change the storyline setting, complete the following steps: 

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) with your admin credentials.
2. In the left-rail menu, select **Settings & policies**.
3. Select either **Global (Org-wide default) settings** or **Custom policies for users & groups**.
4. Scroll to the **Messaging** section and select **Messaging**.
5. On the **Messaging settings** page, find the **Viva Engage** section.
6. To enable **storylines in Teams**, switch on the toggle.
7. Choose **Save**.

Note

Disabling the Storylines setting only removes the Storylines experience from Microsoft Teams. Storylines will continue to be available in Viva Engage **unless** Storylines are disabled in the Viva Engage admin settings. If Storylines are disabled in the Viva Engage admin center, the experience is disabled in both Viva Engage and Microsoft Teams. If your organization chooses to turn off Viva Engage or the storyline feature, storyline doesn't appear in Teams. Storyline in Teams doesn't grant storyline access or permissions to Engage-unlicensed users.

## User experience of storylines in Teams chats

Storyline content, whether originating from Teams or from Engage, is visible to all eligible users in both Teams and Viva Engage.

Teams chats support storyline pages with the following user features:

- Create new storyline posts directly from Teams
- Follow, view, and comment on others' storylines in Teams
- Receive notifications in Teams for relevant activity in storyline
- Post a storyline or comment on storyline posts on behalf of others as a delegate
- Change the cover photo at the top of their storyline
- A similar look and feel for Storyline conversations to other messaging experiences in Teams.

[Viva Engage Premium](/en-us/viva/engage/setup#set-up-licensing-for-viva-engage) licensed users can use the following features:

- Assigned leaders can send storyline announcements
- Users can view personal analytics about their storyline
- Review analytics to get insights into engagement trends, to measure impact and optimize content strategies.

## User experience of Engage communities in Team chats

The communities in Teams experience includes the following features:

**Unified access in Teams**: Find Communities in the Teams navigation pane (Chat app for unified view or Teams and Channels app for split view), which reduces friction and keeps collaboration in one place. Navigation includes the following options: 

- Show (or hide) communities in the nav that are most important to them
- Create custom sections for tailored organization
- Use a-z or recency-based sort order for the default **Communities** section.

**Discoverability & Personalization**: Users can browse and join communities aligned with interests and organizational priorities.

**Rich Engagement Features:**

- Users can scroll through the community feed, post discussions, questions, praise, or polls, react to posts and see who else reacts, and create announcements (if an admin).
- Delegated posting for designated roles (requires delegate set up in Viva Engage).
- Notifications for announcements, user mentions and other community experiences appear in the Teams Activity feed. Users can deep-link into these new experiences.
- Use community-scoped search to search in communities for specific content, or search across communities with the Teams search bar.
- Join and engage with events in communities: ask questions, upvote, view live, or rewatch events.
- Review analytics for insight into engagement trends (requires premium Viva Engage license).
- Manage community settings, membership, admin, and expert roles seamlessly from the new experience (community admin only).