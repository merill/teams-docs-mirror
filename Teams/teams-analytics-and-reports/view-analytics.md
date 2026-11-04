---
layout: Conceptual
title: View analytics in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/view-analytics
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: Admin
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: snchatur
ms.date: 2026-05-26T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about cross-team analytics, per-team analytics, and per-channel analytics in Teams, which let users see usage data for teams or channels that they're part of.
ms.custom:
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.collection:
- M365-collaboration
locale: en-us
document_id: 3c93d512-6e5a-09c7-1c9f-c7eeb94555da
document_version_independent_id: f289f914-6b58-6c29-8997-a2fbd017ffe7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/view-analytics.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/view-analytics
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/view-analytics.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: eae8cd76-8ea7-eade-2a08-8c543b22d2d9
---

# View analytics in Teams - Microsoft Teams | Microsoft Learn

In Microsoft Teams, users can view analytics for teams and channels that they're part of. This information gives users insight into usage patterns and activity on their teams. Users can see data such as the number of active users, posts, replies, and more at three levels.

- **Cross-team analytics** gives users a broad overview of usage data for all teams that they're a member or owner of in a single list view.
- **Per-team analytics** gives users a more granular view, showing usage data for a specific team.
- **Per-channel analytics** gives users an even more granular view, showing usage data for a specific channel.

Users can filter any of these views to see data for a specified time period.

## View cross-team analytics

1. In Teams, at the bottom of the teams list, next to **Join or create a team**, select **Manage teams**.
2. Select the **Analytics** tab.
3. Select a date range to show usage data for all teams that you're a member or owner of.

    ![Screenshot of cross-team analytics view.](../media/view-analytics-cross-team.png)

    | Item | Description |
    | --- | --- |
    | **Name** | Name of the team. |
    | **Active users** | Number of active users on the team and trend line of team activity during the specified time period. |
    | **People** | Total number of people on the team in the specified time period. This includes team owners, team members, and guests. |
    | **Guests** | Number of guests on the team during the specified time period. |
    | **Posts** | Number of new messages posted in team chat during the specified time period. |
    | **Replies** | Number of replies in team chat during the specified time period. |
    | **Type** | Whether the team is a private team or public team. |

## View per-team analytics

1. In Teams, go to the team that you want, select **More options (...)**, and then select **Manage team**.
2. Click the **Analytics** tab.
3. Select a date range to show usage data for the team.

    ![Screenshot of per-team analytics view.](../media/view-analytics-per-team.png)

    | Item | Description |
    | --- | --- |
    | **Summary** | Summary of team activity including the following:<br>    - **Users**: Total number of users in the specified time period. This includes team owners, team members, and guests.<br>    - **Posts**: Number of new messages posted in team chat during the specified time period.<br>    - **Replies**: Number of replies in team chat during the specified time period.<br>    - **Apps**: Number of apps added to the team.<br>    - **Meetings**: Number of Teams meetings organized at the team level. |
    | **Active users** | Number of active and inactive users. |
    | **Role** | Numbers of users by role, including team owners, team members, and guests. |
    | **Active users** chart | Number of daily active. Hover over the dot on a given date to see the number of active users on that date. |
    | **Messages** chart | Total number of messages posted in team chat by date. Hover over the dot on a given date to see the number of new posts and replies posted on that date. |

Tip

You can also view per-team analytics by clicking a team in list in the cross-team analytics view.

## View per-channel analytics

1. In Teams, go to the channel that you want, select **More options (...)**, and then select **Manage channel**.
2. Select the **Analytics** tab.
3. Select a date range to show usage data for the channel.

    ![Screenshot of per-channel analytics view.](../media/view-analytics-per-channel.png)

    | Item | Description |
    | --- | --- |
    | **Summary** | Summary of channel activity including the following:<br>    - **Users**: Total number of users in the specified time period. This includes team owners, team members, and guests.<br>    - **Posts**: Number of new messages posted to the channel during the specified time period.<br>    - **Replies**: Number of replies in the channel during the specified time period.<br>    - **Apps**: Number of apps added to the channel. |
    | **Messages** chart | Total number of messages posted to the channel chat by date. Hover over the dot on a given date to see the number of new posts and replies posted on that date. |

Tip

You can also view per-channel analytics by selecting a channel in the drop-down list box in the per-team analytics view.

Note

We define active users as users who perform an intentional action in the desktop client, mobile client, and web client. Examples of an intentional action include starting a chat, placing a call, sharing a file, editing a document within teams, participating in a meeting, and so on. We strip out passive actions like auto boot, minimizing a screen, or closing the app. We also de-dupe all actions across a single user ID.