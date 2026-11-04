---
layout: Conceptual
title: Overview of teams and channels in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-channels-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: harshc-ms
ms.author: chandraharsh
manager: jtremper
ms.date: 2026-08-07T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Learn about the different teams, channels, and apps available to a wide variety of requirements such as finance, event planning, sales, and more.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
- intro-overview
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.collection:
- M365-collaboration
locale: en-us
document_id: 06059d07-6687-2924-7d0a-3c03220a1650
document_version_independent_id: bb293f92-9394-b156-2e08-0baead5c3bbe
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-channels-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-channels-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-channels-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b5cc235a-225c-7e76-ba07-1014e61099db
---

# Overview of teams and channels in Microsoft Teams - Microsoft Teams | Microsoft Learn

Microsoft Teams allows individual teams to self-organize and collaborate across business scenarios:

- **Teams** are collections of people, content, and tools surrounding different projects and outcomes within an organization.

    - Teams can be created to be private to only invited users.
    - Teams can also be created to be public and open and anyone within the organization can join (up to 10,000 members).

    A team is designed to bring together a group of people who work closely to get things done. Teams can be dynamic for project-based work (for example, launching a product, creating a digital ship room), and ongoing, to reflect the internal structure of your organization (for example, departments and office locations). Conversations, files, and notes across team channels are only visible to members of the team.
- **Channels** are dedicated sections within a team to keep conversations organized by specific topics, projects, disciplines—whatever works for your team. Files that you share in a channel (on the Files tab) are stored in SharePoint. To learn more, read [Overview of Teams and SharePoint integration](/en-us/sharepoint/teams-connected-sites).

    - Channels are places where conversations happen and where the work actually gets done. Channels can be open to all team members (standard channels), selected team members ([private channels](private-channels)), or selected people both inside and outside the team ([shared channels](shared-channels)).
    - Channels are most valuable when extended with apps that include tabs, connectors, and bots that increase their value to the members of the team. To learn more, see [Overview of Teams apps](apps-in-teams).

See [Limits and specifications for Microsoft Teams](/en-us/microsoftteams/limits-specifications-teams) for information on the limits associated with using Teams.

## Membership, roles, and settings

### Team membership

Team owners can invite anyone at your organization to join their team. Depending on your organization's settings people from outside of your organization can be added to your teams as guests or as external participants in shared channels. See [Guest Access in Microsoft Teams](guest-access) for more information.

Team owners can also create a team based on an existing Microsoft 365 group. Any changes made to the group membership are synced with Teams automatically.

### Team roles

There are two main roles in Teams:

- **Team owner**: The person who creates the team. Team owners can make any member of their team a co-owner when they invite them to the team or at any point after they've joined the team. Having multiple team owners lets you share the responsibilities of managing settings and membership, including invitations.
- **Team members**: The people who the owners invite to join their team.

Also, if moderation is set up, team owners and members can have moderator capabilities for a channel. Moderators can start new posts in the channel and control whether team members can reply to existing channel messages. Team owners can assign moderators within a channel. (Team owners have moderator capabilities by default.) Moderators within a channel can add or remove other moderators within that channel. For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams).

Note

When you add a team owner, they're also added as a member, except when the team is created in the Teams admin center or when a team is added to a new or existing Microsoft 365 group.

### Team settings

Team owners can manage team-wide settings directly in Teams. Settings include the ability to add a team picture, set permissions across team members for creating standard, private, and shared channels, adding tabs and connectors, @mentioning the entire team or channel, and the usage of GIFs, stickers, and memes.

If you're a Teams Administrator in Microsoft 365, you have access to system-wide settings in the Teams admin center. These settings can impact the options and defaults team owners see under team settings.

By default, all users have permissions to create a team. To modify this, see [Assign roles and permissions in Teams](assign-roles-permissions).

Note

When you create a new team or a private or shared channel in Teams, a team site in SharePoint gets automatically created. To edit the site description or classification for this team site, go to the corresponding channel's [settings in Microsoft Teams](https://support.microsoft.com/office/bf39798f-90d2-44fb-a750-55fa05a56f1d).

Learn more about managing [Microsoft Teams connected teams sites](/en-us/SharePoint/teams-connected-sites).

This video shows the steps to view and manage a user's team membership.

## Channel feature comparison

The following table shows a comparison of Teams features for each channel type.

| Features | Standard channel | Private channel | Shared channel |
| --- | --- | --- | --- |
| People can be added to the channel without adding them to the team. | No | No | Yes |
| Channel membership can be limited to a subset of the team. | No | Yes | Yes |
| Channel can be shared directly with other teams. | No | No | Yes |
| Channel can be shared directly with its parent team. | N/A | No | Yes |
| Guests can participate in the channel. | Yes | Yes | No |
| External participants (B2B Direct Connect) can participate in the channel. | No | No | Yes |
| Moderation | Yes | No | No |
| Copy link to channel | Yes | No | No |
| Each channel has a dedicated SharePoint site. | No | Yes | Yes |
| Scheduled meetings | Yes | No | Yes |
| Planner | Yes | No | No |
| Bots, connectors, and messaging extensions | Yes | No | No |
| Supported in class teams | Yes | Yes | No |
| Tags | Yes | Yes | Yes |
| Analytics | Yes | Yes | No |

## Org-wide teams

If your organization has no more than 10,000 users, you can create an org-wide team. Org-wide teams provide an automatic way for everyone in an organization to be a part of a single team for collaboration. For more information, including best practices for creating and managing an org-wide team, see [Create an org-wide team in Microsoft Teams](create-an-org-wide-team).