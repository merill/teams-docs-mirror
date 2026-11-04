---
layout: Conceptual
title: Manage the Praise app in the Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-praise-app
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal0201
ms.author: vikasalmal
manager: jtremper
ms.reviewer: rjam
ms.date: 2026-05-22T00:00:00.0000000Z
audience: admin
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
ms.localizationpriority: medium
description: Learn how to manage the Praise app in the Microsoft Teams admin center.
ms.collection:
- M365-collaboration
- m365-frontline
- teams-1p-app-admin
- highpri
locale: en-us
document_id: 4a2033a3-a651-78f3-90c2-ad582e182731
document_version_independent_id: 057e7da2-4e65-7f8d-5843-b15d92ffff02
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-praise-app.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-praise-app
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-praise-app.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: c963ae2a-2500-58b2-5323-d55bf842f12a
---

# Manage the Praise app in the Teams admin center - Microsoft Teams | Microsoft Learn

## Overview of Praise

The Praise app in Microsoft Teams helps users show appreciation to members of your organization or classroom. The badges in Praise are designed to help recognize the effort that goes into the wide range of work that Teams users do, from educators to frontline workers. To learn more, check out [Send Praise to people in Teams](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Admins must have a Teams license to access this feature. If you try to access this feature without a Teams license, you'll get an error message.

Note

The Praise app is available for GCC or GCC High cloud environments, but not for DoD.

## Enable or disable Praise in your organization

Praise is enabled by default for all Teams users in your organization. You can turn off or turn on the app at the org level on the [Manage apps](manage-apps) page in the Microsoft Teams admin center.

![Screenshot of the Praise app details page in the Teams admin center, showing the Status toggle.](media/manage-praise-app-admin-center.png)

1. In the left pane of the Microsoft Teams admin center, go to **Teams apps** &gt; **Manage apps**.
2. In the list of apps, search for the Praise app, select it, and then switch the **Status** toggle to **Blocked** or **Allowed**.

Keep in mind that this setting affects both the Praise app and the Praise feature in the Viva Insights app in Teams.

If you set the status to **Blocked**, the Praise app is blocked within a few minutes for Teams. However, Praise in Viva Insights can take up to 15 days to be blocked.

## Enable or disable Praise for specific users in your organization

To allow or block specific users in your organization from using Praise, make sure Praise is turned on for your organization on the [Manage apps](manage-apps) page. Then create a custom policy for app permissions and assign it to those users. To learn more, see [Use app permission policies to control user access to apps](teams-app-permission-policies).

## Composer

Teams users in your organization can use the praise composer to recognize their peers for going above and beyond with their work. While crafting their message, they can pick from 14 titles—like **Courage**, **Optimism**, **Kind heart**, and **Creative**—to recognize their colleagues’ contributions.

![Screenshot of the praise composer.](media/praise.png)

## User data in Praise

Praise uses Viva Insights to process and store data. See the [Personal insights FAQ](/en-us/viva/insights/personal/overview/mya-faq) to learn more about how Viva Insights processes and stores user data.

## Give feedback or report an issue

To send feedback or report an issue, select **Settings and more** (**…**) in Teams, and then choose **Help** &gt; **Give feedback**. Enter your feedback or details about the issue you're experiencing. Indicate at the beginning of your feedback report that you're sending feedback about Praise so we can easily identify Praise issues.