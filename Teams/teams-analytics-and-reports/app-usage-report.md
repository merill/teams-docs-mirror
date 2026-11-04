---
layout: Conceptual
title: Microsoft Teams app usage report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/app-usage-report
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
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: vapati
ms.date: 2022-09-27T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Learn how to use the Teams app usage report in Teams admin center to know the active teams and users of an app.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: ed4904e2-a072-56fc-bc54-4e7d2582d8fd
document_version_independent_id: c70894ac-67e3-be36-4fa6-a95c78fa736a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/app-usage-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/app-usage-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/app-usage-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d8e5fb0b-8870-739d-6b74-e5aa9967c97f
---

# Microsoft Teams app usage report - Microsoft Teams | Microsoft Learn

The Teams app usage report in the Microsoft Teams admin center provides you with insights about which apps users are using in Teams. You can gain insights into the apps activity in your organization for different microsoft (Viva Learning, Shifts etc.), third-party (Polly, Trello etc.) & Line of Business (LOB) Teams apps.

You can use this report to understand where exactly different apps are getting used and deep dive into per-app utilization data.

The data represented in this report provide answers to the following questions:

- How many installed apps do users in your environment have?
- How many apps have at least one active user in your environment based on type (Microsoft, third-party, and LOB)?
- How many apps are being used per platform (Windows, Mac, web, or mobile)?
- How many active users and active teams are using an app?

Note

Usage for **Side loaded** LOB apps is not included in this report.

This article explains how to access the report and view and interpret the various metrics within the report.

## View the app usage report

You must be either a global admin, global reader, or Teams service admin to view the reports in the Microsoft Teams admin center. See [Use Teams administrator roles to manage Teams](../using-admin-roles) to read about getting admin roles and permissions.

1. In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **Apps usage**.
2. Under **Date range**, select a range and then select **Run report**.

[![Screenshot of the Teams app usage report in the Teams admin center with callouts.](media/app-usage2-report10.png)](media/app-usage2-report10.png#lightbox)

## Interpret the report

| Callout | Description |
| --- | --- |
| **1** | The app usage report can be viewed for trends over the last 7, 30, 90, and 180 days. |
| **2** | Each report has a date for when this report was generated. Reports usually reflect a 24-48 hour latency from the time an app was used. For example, data for January 10th should show up in the report by around January 12th. |
| **3** | - The X axis on the chart is the selected date range for the report.<br>- The Y axis is the count of items.<br><br>Hover over the dot representing an item on a given date to see the number of instances of that item on that given date. |
| **4** | You can filter what you see on the chart by selecting an item in the legend. For example, select **Active Microsoft apps**, **Total installed apps**, and more to see only the info related to each one. Changing this selection doesn’t change the information in the table. <br>- **Active Microsoft apps** is the number of Microsoft apps (for example, Viva learning) used across your organization.<br>- **Active third-party apps** is the number of third-party apps (for example, Polly) used across your organization.<br>- **Active LOB apps** is the number of Line of Business apps used across your organization.<br>- **Total active apps** is the total number of apps used across your organization.<br>- **Total inactive apps** is the number of apps not used in your organization.<br>- **Total installed apps** is the total number of apps installed within your organization. The start date for all install metrics is October 2021. Only apps installed after that date will be counted.<br><br> The chart shows you aggregated metrics across the organization on each day within a selected period. For example, if you select January 28th and metric **Active third-party apps**, the chart will show you the total number of third-party apps used on January 28th within your organization. |
| **5** | The table gives you a breakdown of usage by each app. <br>- **App ID** is the external app identifier present in the app manifest. More information about the app can be found in the [Manage apps section in Teams admin center](/en-us/microsoftteams/manage-apps) by referring to it using this external App ID.<br>- **App name** is the name of this application as present in the app manifest.<br>- **Publisher** is the publisher of this application as present in the app manifest. This is only available for apps published to the global Store.<br>- **Teams using this app** is the number of distinct Teams teams that have at least one user using this app.<br>- **Users using this app** is the number of distinct users in your organization that are using this app.<br>- **Used on Windows** indicates whether that app has been used on Windows by at least one user in your organization.<br>- **Used on Mac** indicates whether that app has been used on MAC by at least one user in your organization.<br>- **Used on Web** indicates whether that app has been used on the web by at least one user in your organization.<br>- **Last used date** is the date when that app was last used by anyone in your organization. |
| **6** | Select **Edit columns** to add or remove columns in the table. |
| **7** | Export the report to a CSV file for offline analysis. Select the **Export to Excel** icon, and the report will be downloaded within your browser. |
| **8** | Time series data represented in the top graph show different usage metrics aggregated for the entire tenant. |
| **9** | Tabular data represented in the bottom half shows different usage metrics aggregated per team. |

## Managing apps in the Microsoft Teams admin center

For more information about how to manage your Teams apps, refer to [About apps in Microsoft Teams](../apps-in-teams).

To link an app in this report to the Manage Apps experience in the Microsoft Teams admin center, you can use the following:

- App Name
- External App ID

External App IDs are equivalent to the ID in the Manage apps page for Store apps. For LOB apps, the **External app ID** column can be enabled in the [Manage apps section in Teams admin center](/en-us/microsoftteams/manage-apps) column settings. You can also view it on the app details page of a custom LOB app.