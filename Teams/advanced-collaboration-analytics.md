---
layout: Conceptual
title: Advanced collaboration analytics for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/advanced-collaboration-analytics
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: jtremper
author: jacktremper
manager: pamgreen
ms.reviewer: izzychun, charup
ms.date: 2023-11-10T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.collection: 
f1.keywords:
- NOCSH
ms.custom: 
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about the collaboration activity reports in Microsoft Teams.
locale: en-us
document_id: 017ec31e-d060-ba0f-2463-4383cae6e596
document_version_independent_id: 017ec31e-d060-ba0f-2463-4383cae6e596
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/advanced-collaboration-analytics.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: advanced-collaboration-analytics
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/advanced-collaboration-analytics.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d984177b-a10d-5b06-bbfa-ccd3bcdbddaf
---

# Advanced collaboration analytics for Microsoft Teams - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

Advanced collaboration analytics gives you visibility into your organization’s external collaboration habits. These reports include information about your teams, trusted domains, channels, guests, and internal users. You can use this information to facilitate successful collaboration and mitigate potential risks that come with allowing external collaboration.

Reports only show users and teams owned by your organization, but the counts could include activities in cross-tenant collaborations. Reports include chat events (1:1, group, and meeting) initiated by your users and by people outside your organization. Reports include channel events from Teams channels in your organization, but not channel events that your users participate in that are hosted by other organizations.

Advanced collaboration analytics requires a Teams Premium license for each user you want to receive insights about. Note that it takes 30 days after licenses are purchased for the data to be available.

## View the collaboration activity dashboard

Advanced collaboration analytics can be found in the Teams admin center dashboard on the **Collaboration activity** tab.

[![Screenshot that shows the Collaboration activity reports menu item.](media/collaborative-activity-dashboard.png)](media/collaborative-activity-dashboard.png#lightbox)

## Inactive teams

The **Inactive teams** card shows inactive teams whose connected workloads are also inactive. It shows you how many teams in your organization have been inactive for the last 30 or 60 days. You can hover over each bar to see the exact counts for the specific day.

Note that you can set inactive teams to expire automatically by using [expiration policies for Microsoft 365 groups](/en-us/microsoft-365/solutions/microsoft-365-groups-expiration-policy). You can also [archive or delete a team in the Teams admin center](archive-or-delete-a-team).

![Screenshot that shows details of teams that are inactive.](media/inactive-teams.png)

Select **View details** to see which teams these are. For each team, you can see the privacy type, number of channels, number of users, and the last activity date.

[![Screenshot that shows the detailed report of teams that are inactive.](media/detailed-report-view.png)](media/detailed-report-view.png#lightbox)

To change the time frame, select the range of date from the **Date range** drop-down, and select **Run report**.

The bar chart at the top shows the daily count of inactive teams, where each bar represents the number of teams considered inactive on that specific day. The table below reflects the selected time period (30 or 60 days) and lists the teams that have been inactive for the entire selected duration.

You can also archive the team directly from the report. However, archiving a team has no impact on the connected workloads. Only the team itself will become read-only.

To archive an inactive team, under the **Action** column, select the **bin** icon. In the *Archive team?* dialog box, select **Archive**.

A value for **Last activity date (UTC)** is displayed only if teams activity has taken place after October 2023.

Note

SharePoint Administrators with a [Microsoft Syntex - SharePoint Advanced Management](/en-us/sharepoint/advanced-management) license can use [site lifecycle policies](/en-us/sharepoint/site-lifecycle-management) in the SharePoint admin center to detect inactive sites, including team-connected sites.

## Inactive external domains activity

The **Inactive external domains activity** card shows how many domains are allowed and how many of your allowed domains have been active and inactive for the last 30 or 60 days. You can hover over each part of the pie chart to see exact counts.

This card is only available if you've configured an allowlist in [external access](trusted-organizations-external-meetings-chat).

![Screenshot that shows the total number of allowed domains.](media/inactive-external-domains.png)

Select **View details** to see which domains are inactive, including the last activity date. A value for **Last activity date (UTC)** is displayed only if domain activity has taken place after October 2023.

You can change the time frame by choosing a date range from the **Date range** dropdown and selecting **Run report**.

![Screenshot that shows the detailed report view regarding the external domains activity.](media/detailed-report-view-inactive-external-domains.png)

## Teams by user type

The **Teams by user type** card shows how many active teams have a particular user composition:

- Your users only
- Your users and guests
- Your users and external shared channel users
- All user types

![Screenshot that shows the Teams by user type card.](media/teams-by-user-type.png)

## Channels by user type

The **Channels by user type** card shows you how many active channels have a particular user composition:

Standard and private channels

- Only your users
- Your users and guests

Shared channels

- Only your users
- Your users and external channel participants

![Screenshot showing the Channels by user type card.](media/channels-by-user-type.png)

## Teams with the most external user and guest activity

The **Teams with the most external user and guest activity** card shows you which teams in your organization have the most collaboration with guests and external shared channel users for the last 7 or 30 days.

You can select **View details** to see the team names and the sent message count for each team. An average message count is also displayed.

By default, we show you these details for the last 7 days. You can change the time frame by choosing **30 days** or **60 days** from the **Date range** drop-down and selecting **Run report**.

Note that for privacy reasons the data is hidden by default in this card. To reveal the data, see [Show user details in the reports](/en-us/microsoft-365/admin/activity-reports/activity-reports#show-user-details-in-the-reports).

## Users with the most external user and guest collaboration

The **Users with the most external user and guest collaboration** card shows you which of your users have the most collaboration with guests and external shared channel users for the last 7 or 30 days.

You can select **View details** to see the users' names and the sent message count for each user. An average message count is also displayed.

By default, we show you these details for the last 7 days. You can change the time frame by choosing **30 days** or **60 days** from the **Date range** drop-down list and selecting **Run report**.

Note that for privacy reasons the data is hidden by default in this card. To reveal the data, see [Show user details in the reports](/en-us/microsoft-365/admin/activity-reports/activity-reports#show-user-details-in-the-reports).

## Guests with the most external user and guest collaboration

The **Guest with the most external user and guest collaboration** card shows you which guests have the most collaboration with other guests or external shared channel users over the last 7 or 30 days.

Note that for privacy reasons the data is hidden by default in this card. To reveal the data, see [Show user details in the reports](/en-us/microsoft-365/admin/activity-reports/activity-reports#show-user-details-in-the-reports).

## Known issues

1. Card location customizations on dashboard aren't saved across sessions.
2. CSV download hasn't been enabled.
3. Large events have a small chance of data categorization error. For example, a large team with few guests might not be categorized as "with guest users."