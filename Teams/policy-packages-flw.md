---
layout: Conceptual
title: Teams policy packages for frontline workers - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/policy-packages-flw
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: 
ms.date: 2024-07-25T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
f1.keywords: 
ms.custom: 
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to use and manage Teams policy packages for frontline workers in your organization.
locale: en-us
document_id: 7d5d86f4-f446-26ba-3a05-bb692da3bc8e
document_version_independent_id: 7d5d86f4-f446-26ba-3a05-bb692da3bc8e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/policy-packages-flw.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: policy-packages-flw
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/policy-packages-flw.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a6bfaa48-a578-3f1e-2d0c-390afefa2e9a
---

# Teams policy packages for frontline workers - Microsoft Teams | Microsoft Learn

## Overview

A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization. Policy packages simplify, streamline, and help provide consistency when managing policies. To learn more, see [Managing policy packages in Teams](manage-policy-packages).

You can customize the settings of the policies in a package to suit the needs of your users. When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings. You can manage policy packages by using the Microsoft Teams admin center or PowerShell.

This article gives you an overview of the **Frontline manager** and **Frontline worker** policy packages included in Teams.

| Package name in the Teams admin center | Description |
| --- | --- |
| **Frontline manager** | Creates a set of policies and applies those settings to frontline managers in your organization. |
| **Frontline worker** | Creates a set of policies and applies those settings to frontline workers in your organization. |

[![Screenshot of frontline policy packages.](media/policy-packages-flw.png)](media/policy-packages-flw.png#lightbox)

Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package. For example, when you assign the Frontline manager policy package to store managers in your organization, a policy named Frontline\_Manager is created for each policy in the package.

![Screenshot of policies in the Frontline manager policy package.](media/policy-packages-flw-frontline-manager.png)

## Use policy packages

### View

View the settings of each policy in a policy package before you assign a package. In the left navigation of the Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.

Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.

### Customize

Customize the settings of policies in the policy package, as needed, to fit the needs of your organization. Any changes you make to policy settings are automatically applied to users who are assigned the package.

To edit the settings of a policy in a policy package, in the left navigation of the Teams admin center, go to **Policy packages**, select the policy package, select name of the policy you want to edit, and then select **Edit**.

Note

You can also change the settings of policies in a package after you assign the policy package.

### Assign

You can assign a policy package to an individual user, multiple users, a group of users such as a security group or distribution list, or a large set (batch) of users. To learn more, see [Assign policy packages to users and groups](assign-policy-packages).