---
layout: Conceptual
title: The Teams client health dashboard in the Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-health
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.topic: article
ms.date: 2025-02-26T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: shals
search.appverid: MET150
f1.keywords:
- NOCSH
description: How to configure and use the health page in the Teams admin center to manage clients using monitoring and informational advice specific to situations.
ms.localizationpriority: medium
locale: en-us
document_id: 279ca732-bf36-7d6e-f4a0-ae55f205db73
document_version_independent_id: 279ca732-bf36-7d6e-f4a0-ae55f205db73
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-health.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-health
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-health.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7adce7e5-4505-69e4-89bb-a44bba73c76b
---

# The Teams client health dashboard in the Teams admin center - Microsoft Teams | Microsoft Learn

Teams client health is an all-new page with a set of data, insights, and tools to help administrators troubleshoot and resolve issues. When a Teams application experiences an issue, end-users typically reach out to their admins. As an admin, you may have many requests from end-users. These requests can leave you in a reactive position with limited information to diagnose and resolve problems effectively.

You may need to proactively monitor for issues. You may also need to perform remediation actions to manage and fix issues before they impact your end user productivity or cause further escalations.

## Access the Teams client health dashboard

To access the Teams client health dashboard, follow these steps:

1. Go to the Teams admin center.
2. Select **Teams client health** from the navigation pane.

The Teams client health page displays an overview of Teams client health along with more information when you go into the details.

![A screenshot of the client health page with four callout boxes marked. Box 1 is at the top of the page next to Client health. Box 2 is on the top right next to Top issues. Box 3 is on the lower middle above the issues list. Box 4 is on the lower right next to the search, settings, and export options.](media/teams-client-health-main-page.png)

The **Client health** widget displays key health metrics like device crashes and launch failure trends for the last 28 days for all devices in your tenant.

Note

This widget only surfaces health markers that are end-user impacting and actionable by administrators.

Here are more details on each metric:

| Callout number | Details |
| --- | --- |
| Callout 1 | This widget shows Client health trends across the health metric:- **Crashes**: The number of devices experiencing Teams app crashes per day within the last 28 days. Supported for Windows (non-VDI) and Mac Applications.- **Launch failures**: The number of devices experiencing Teams app launch failures per day within the last 28 days.Supported for Windows (non-VDI) and Mac applications. |
| Callout 2 | This widget shows the top issues experienced by users in the organization:- Device reported crashes: The number of devices that experienced crashes in the last seven days. The number of devices that experienced crashes in last 28 days.- Device reported launch failures: The number of devices that experienced launch failures in the last seven days. The number of devices that experienced launch failures in the last 28 days.- Device reported update failures: The number of devices that experienced update failures in last seven days. The number of devices that experienced update failures in last 28 days. |
| Callout 3 | This table provides the following data:- Issue: Problems impacting devices and users in the tenant.- Insights: Insights on potential reasons behind these problems.- Impacted Devices in the last seven days (%): The number of devices that experienced the issue in the last seven days and the percentage of the device base impacted in the organization.- Affected users in the last seven days (%): The number of users who experienced the issue in the last seven days and the percentage of the user base impacted in the organization.- Impacted Devices in the last 28 days (%): The number of devices that experienced the issue in the last 28 days and the percentage of the device base impacted in the organization.- Affected users in the last 28 days (%): The number of users who experienced the issue in the last 28 days and the percentage of the user base impacted in the organization.- Suggested Actions: Recommended mitigation guidance to troubleshoot and fix the issue. |
| Callout 4 | You can use these buttons to:- Export the table to a CSV file.- Filter by issue or insight.- Access settings for the columns in the table. |

![A screenshot of a details page, with callouts marked. The first callout is next to the title for the page, and says Crash. The second callout is below the title and indicates what's behind this issue. The third callout is next to a link to help fix the issue. The fourth callout is at the top of the list of users experiencing the issue with details about them. The fifth callout is on the upper right-hand side of the page, with the filter, settings, and export options.](media/teams-client-issue-details-page.png)

| Callout number | Details |
| --- | --- |
| Callout 1 | Issue type - The category of issue impacting users and devices. |
| Callout 2 | Insight - The insight or reason leading users and devices to experience the issue. |
| Callout 3 | Mitigation link - This link points to Microsoft recommended mitigation and guidance to resolving the issue. |
| Callout 4 | The table provides the following data- Client version - The Teams client version the user is currently on.- Version status - The client version status of the Teams client the user is running on.- Ring - The ring the user is a part of.- Device - Details about the device the user is currently using.- Device crashes - The number of devices that experienced crashes in last seven days.- Device launch failures - The number of devices that experienced launch failures in the last seven days.- Updated on (UTC) - The time stamp when this information was last refreshed. |
| Callout 5 | You can use these buttons to:- Export the table to a CSV file.- Filter and search by versions.- Manage settings for columns in the table. |