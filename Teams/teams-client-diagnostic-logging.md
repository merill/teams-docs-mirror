---
layout: Conceptual
title: Teams client diagnostic logging in the Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-diagnostic-logging
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
ms.date: 2025-06-16T00:00:00.0000000Z
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
description: Diagnostic logging for Teams client updates in the Teams admin center to manage client updates and prevent sedimentation.
ms.localizationpriority: medium
locale: en-us
document_id: 136fb401-c7e4-05e3-065f-068c83e9736f
document_version_independent_id: 136fb401-c7e4-05e3-065f-068c83e9736f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-diagnostic-logging.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-diagnostic-logging
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-diagnostic-logging.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 9388ab7d-96b4-185c-7dcb-9f0a4503ae0e
---

# Teams client diagnostic logging in the Teams admin center - Microsoft Teams | Microsoft Learn

This article provides an overview of a tool for Teams admins to collect diagnostic logs from the Microsoft Teams admin center.

Note

This feature is currently supported for Windows (non-VDI) and Mac Applications only.

Diagnostic data from clients is essential for triaging and mitigating problems. To streamline problem resolution, reduce overhead, and avoid end user interruptions, we're giving admins the ability to remotely gather diagnostic logs from Teams clients without end-user interruptions. Admins can now remotely collect diagnostic logs from users’ machines from the users page in the Microsoft Teams admin center.

## Steps to gather diagnostic logs

1. Go to the **Users** tab on the left-hand navigation menu, and then select **Manage users**. Once there, navigate to the specific user page of the user you need diagnostic logs collected from.
2. On the user page, the **Client health** tab provides more information about client health for all client versions that user is running.
3. This page also allows you to gather diagnostic logs from a specific device or multiple devices.
4. Choose the client and version you want to collect diagnostic logs from and select the **Request client logs** option.
5. Once log collection is started, the **Client log status** column on this page will be set to **Pending**.
6. Once log collection is complete, you can download and share the logs with your team or Microsoft, and you can also view the collected logs.
7. You can also view the status for all logs collected within your tenant.

![A screenshot of the log collection page showing the steps to gather diagnostic logs outlined in this section of the article.](media/diagnostic-log-walkthrough-screenshot.png)

Note

This feature is accessible to the following roles: Global Administrator, Teams Administrator, Teams Communications Support Engineer, and Teams Communications Support Specialist.

### Devices that use a government cloud account

Client log collection isn't supported on devices that have both commercial and government cloud accounts added simultaneously to the Teams client.

![A screenshot of the log collection page showing Ineligible under the Client log status column.](media/diagnostic-log-ineligible.png)

## Manage Logs

1. Selecting **View client logs** from the Teams client health page lets you view the status for all logs collected in your tenant.
2. This page shows tabs for in-progress and ready to download log requests.
3. You can also delete one or all logs collected using the **Delete** option.

![A screenshot of logs download page showing logs that are ready for download, and another tab show logs with the request in progress](media/teams-client-diagnostic-logging/007.png)

## Supported Log Types

Remote log collection supports the following log types:

1. Web logs which include diagnostics logs, calling logs, central data layer logs, Web Media log
2. Desktop Logs that include Shell Diagnostics logs, Slimcore logs including media stack logs

Note

We do not collect procmon traces and OS Event Logs that require elevated user access.

## Further Information

- These logs are stored for 30 days.
- Logs are stored in a Microsoft secure and compliant storage location.
- User consent isn't required and no prompt or message is shown to users when logs are collected.
- The types of logs collected are client logs and shell logs (media logs). There are no screenshots or heaps collected.
- Provided Teams client is running, logs may take up to 8 hours before they are fully available for download in Teams Admin center. Please check back after some time to see the log status. Future enhancements are planned to reduce this time.