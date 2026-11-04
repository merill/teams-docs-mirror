---
layout: Conceptual
title: Manage Teams Premium for your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-premium-dashboard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: wlibebe
ms.author: wlibebe
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: riagrawal
ms.date: 2026-07-01T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
description: Learn how to use the Teams Premium dashboard in the Teams admin center to manage licenses and know how often users are using each Teams Premium feature.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 840cd4d4-8291-9f83-c7fe-f1e4e38d60f2
document_version_independent_id: 840cd4d4-8291-9f83-c7fe-f1e4e38d60f2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-premium-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-premium-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-premium-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7302bea9-e8ac-c067-d252-35e62a4255e3
---

# Manage Teams Premium for your organization - Microsoft Teams | Microsoft Learn

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

As an admin, you can use The Teams Premium dashboard to manage licenses, track features usage, and get suggestions on how to set up and optimize features for your organization. To learn more about Teams Premium, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience).

To access the Teams Premium dashboard, sign-in to the Teams admin center &gt; select **Teams Premium** in the navigation pane.

## Teams Premium discovery trial

Note

The Teams Premium discovery trial isn’t available if you have a paid Teams Premium subscription or already used the trial.

The Teams Premium discovery trial gives you and your organization a 30-day free trial to explore Teams Premium features.

To start a trial for Teams Premium, follow these steps:

1. Go to the Teams admin center.
2. From the navigation pane, select **Teams Premium**.
3. Select **Try for free** to start the 30-day free trial.

During your trial, you can assign 25 licenses to your users.

## Manage Teams Premium

If you have a Teams Premium trial or licenses for your organization, the Teams Premium dashboard has the following four tabs:

- **Overview**- Overview for licenses, license requests, feature advisor, and Teams Premium feature usage.
- **Licenses**- Manage and assign Teams Premium licenses and license requests for users in your organization. You can also view a list of licensed users and users recommended to have a Teams Premium license.
- **Usage reports**- View aggregated usage of Teams Premium features by users in your org.
- **Feature advisor**- Overview of all Teams Premium features that you must configure for your users.

![Screenshot of Teams Premium Overview](media/teams-premium-dashboard/teams-premium-overview.png)

### Licenses

[![Screenshot of the Teams Premium dashboard's licenses tab.](media/t-pre-dash-licenses-small.png)](media/t-pre-dash-licenses-expand.png#lightbox)

To access licensing information, either select the **Licenses** tab or select **View details** in the **Teams Premium licensing widget** on the **Overview** tab.

The Teams Premium Licenses dashboard has the following widgets:

- **Total Premium licenses**- Count of users with assigned and unassigned Teams Premium licenses.
- **License requests**- Count of pending requests for Teams Premium licenses from users in your organization.
- **Available licenses**- Count of remaining available Teams Premium licenses that you can assign to users in your org.

The dashboard’s table has three tabs that provide the following details:

**Licensed users tab**- Display names, usernames, and locations of users in your organization with an active Teams Premium license.

**License requests tab**- Display names, usernames, request dates, business justifications, and locations of users in your organization who requested Teams Premium license. You can approve or reject licenses in this tab.

**Recommendations tab**- Display names, usernames, and reasons for recommendation of users in your organization who would benefit from a Teams Premium license. You can assign licenses to selected users in this table.

### Usage Reports

To access feature usage information, either select the **Usage reports** tab or select **View details** in the **Teams Premium feature usage** widget on the **Overview** tab. You can also access this usage report from **Analytics & reports** &gt; **Usage reports** &gt; On the **View reports tab**, under **Report**, select **Teams Premium feature usage**.

When you access **Teams Premium feature usage** from the **Teams Premium** dashboard, the data reflects the last 30 days.

To learn more about the Teams Premium usage report, see [Teams Premium feature usage report](/en-us/microsoftteams/teams-analytics-and-reports/teams-premium-usage-report).

### Feature advisor

![Screenshot of Teams Premium Feature Advisor](media/teams-premium-dashboard/teams-premium-feature-advisor.png)

To access feature usage information, either select the **Feature advisor** tab or select **View details** in the **Feature advisor widget** on the **Overview** tab.

The **feature advisor** dashboard shows all the Teams Premium features that you must configure for your users and has the following widgets:

- **Status of Teams Premium features**- Percentage of features that you haven’t enabled, enabled for some users, and enabled for all users.
- **Suggested features**- Teams Premium features that you could enable for licensed users in your organization.

The dashboard’s table has three tabs that provide the following details:

- **Premium area**- Name of Teams Premium area that the features belong to.
- **Feature**- Name of the feature.
- **Status**- One of the following statuses is displayed:

    - **Not enabled**- You haven’t configured this feature or assigned it to any Teams Premium users.
    - **Enabled for some Premium users**- You've configured this feature but only assigned it to some Teams Premium users.
    - **Enabled for all Premium users**- You configured this feature and assigned it to all Teams Premium users.
- **Governing policy**- The admin policy that controls the feature.
- **Description**- Description of the feature.