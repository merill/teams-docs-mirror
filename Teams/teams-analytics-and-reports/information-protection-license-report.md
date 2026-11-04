---
layout: Conceptual
title: Microsoft Teams information protection license report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/information-protection-license-report
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
ms.reviewer: 
ms.date: 2024-11-12T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: 
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- Licensing
- admindeeplinkMAC
- admindeeplinkTEAMS
description: Learn how to use the Teams Information protection license report in the Microsoft Teams admin center to see how apps in your organization are using change notification events subscription APIs.
locale: en-us
document_id: 48493968-9715-1d4b-c712-72b9eb5bc834
document_version_independent_id: 958f2076-17b4-eb8d-49a3-86d5acb50055
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/information-protection-license-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/information-protection-license-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/information-protection-license-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5da2d879-3558-10f0-1464-526c30ba3a0e
---

# Microsoft Teams information protection license report - Microsoft Teams | Microsoft Learn

Teams information protection license report gives API usage insight of [Microsoft Graph APIs that have license and payment requirements](/en-us/graph/teams-licenses). This report highlights all the apps that are using these APIs in [model=A](/en-us/graph/teams-licenses#modela-requirements). It doesn't show usage when APIs are used in [model=B](/en-us/graph/teams-licenses#modelb-requirements) or [evaluation mode](/en-us/graph/teams-licenses#evaluation-mode-default-requirements).

Important

Starting August 25, 2025, the Teams APIs listed in [Microsoft Graph APIs that have license and payment requirements](/en-us/graph/teams-licenses) is no longer metered. As a result of this, the Information Protection report will not generate new data after Aug 2025. This report will be deprecated on 28 Feb 2026.

## View the information protection license report

You must be a Teams admin to make these changes. See [Use Teams administrator roles to manage Teams](../using-admin-roles) to read about getting admin roles and permissions.

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. In the left navigation menu, select **Analytics & reports** &gt; **Usage reports**.
3. On the **View reports** tab, under **Report**, select **Information Protection License**.
4. Under **Date range**, select a range.
5. Under **Apps**, select an app, and then select **Run report**.
6. For each category, metrics on users with licenses, users without licenses, seeded capacity, and utilized capacity can be viewed.
7. The data can be exported by clicking on the export button. The table data can be switched by clicking on the tabs for Teams change notification API, Teams patch API, Teams export APIs (chat), and Teams export APIs (teams).

## Interpret the report

| Callout | Description |
| --- | --- |
| **1** | The information protection license report can be viewed for trends over the last three months. |
| **2** | App name displays a list of all apps that have used [Microsoft Graph API which has license and payment requirements](/en-us/graph/teams-licenses) during the selected time period. |
| **3** | Number of users who have valid [licenses](/en-us/graph/teams-licenses#required-licenses-for-modela). |
| **4** | Number of users who don't have a valid [license](/en-us/graph/teams-licenses#required-licenses-for-modela). |
| **5** | Total API call volume allowed to an app beyond which a consumption fee per API call will be charged to the app. |
| **6** | Total API call volume used by the app for the given date range. |
| **7** | Export the report to a CSV file for offline analysis. Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready. This export exports the currently selected tab only. |
| **8** | Select any specific label to show or hide it in a chart. |
| **9** | Each tab displays usage of a particular set of APIs, namely [change notification](/en-us/graph/api/resources/change-notifications-api-overview?view=graph-rest-1.0), [export API](/en-us/microsoftteams/export-teams-content), and [update message API](/en-us/graph/api/message-update). Select a tab to view usage details of that API. |
| **10** | **Change Notification API Usage**- **Display Name** - Display name of the user against which a change notification was triggered.<br>- **Required License** - Whether the given user has the required license to successfully send a change notification to the app.<br>- **Attempted Count** - Total number of change notifications that were triggered because of this user.<br>- **Change Notification Sent** - Total number of change notifications that were sent to the app. This is less than the total change notifications triggered if the user doesn't have a valid license. |
| **11** | **Patch API**- **Display Name** - Display name of the user where an attempt to update the message was done.<br>- **Required License** - Whether the given user has the required license for the message to get successfully updated.<br>- **Attempted Count** - Total attempts to update messages.<br>- **Message Patched** - Total messages that were successfully updated. |
| **12** | **Chat Export API Usage**- **Display Name** - Display name of user where an attempt to export the user's chat message was done.<br>- **Required License** - Whether the given user has the required license for the message to get successfully exported.<br>- **Attempted Count** - Total attempts to export chat messages.<br>- **Message Exported** - Total attempts where chat message was successfully exported. |
| **13** | **Team Export API Usage**- **Display Name** - Display name of the team where an attempt to export that team's message was done.<br>- **Attempted Count** - Total attempts to export team messages.<br>- **Message Exported** - Total attempts where team message was successfully exported. |

## Make the user-specific data anonymous

To make the data in the Teams user activity report anonymous, you have to be a Microsoft 365 admin. This hides identifiable information such as display name, email, and Microsoft Entra ID in reports and their exports.

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Go to **Settings** &gt; **Org Settings**.
3. Under the **Services** tab, choose **Reports**.
4. Select **Reports**, and then choose to **Display anonymous identifiers**.
    1. This setting gets applied both to the usage reports in the Microsoft 365 admin center and the Teams admin center.
5. Select the **Save changes** button.