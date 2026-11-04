---
layout: Conceptual
title: View your policy assignments in the Activity log in the Microsoft Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/activity-log
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
ms.reviewer: jastark
ms.date: 2020-05-21T00:00:00.0000000Z
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
search.appverid: MET150
description: Learn how to view your policy assignment activities in the Activity log in the Microsoft Teams admin center.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: 
ms.collection:
- M365-collaboration
locale: en-us
document_id: 22995067-f8fb-45d1-f68b-7e66fc155ec4
document_version_independent_id: 341abea2-00c5-e037-72de-dab0f73d9726
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/activity-log.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: activity-log
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/activity-log.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/86a4b315-a9f1-4577-b985-6fb0e0e67420
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/96ac410d-d052-4707-8007-df31dd0fe041
platformId: 62807112-a611-bf46-452a-7e62b6db8dab
---

# View your policy assignments in the Activity log in the Microsoft Teams admin center - Microsoft Teams | Microsoft Learn

When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log. The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days. Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.

![Screenshot of the Activity log page.](media/activity-log.png)

## View your policy assignment activities in the Activity log

To view your policy assignments in the Activity log:

1. In the left navigation of the Microsoft Teams admin center, go to **Home**, and then under **Activity Log**, select **View details**.
2. You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**. You'll see the following information about each assignment:
    - **Name**: The name of the policy assignment. Click the link to view more details. This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started. You'll also see the list of users in the batch, and the status and result for each user. Here's an example:

        ![Screenshot of the.](media/activity-log-policy-assignment-detail.png)
    - **Submitted**: Date and time the policy assignment was submitted.
    - **Completion time**: Date and time the policy assignment was completed.
    - **Impact on**: Number of users in the batch.
    - **Overall status**: Status of the policy assignment.

Note

You can also get to the Activity log from the **Users** page. After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page. Click the **Activity log** link in the banner.