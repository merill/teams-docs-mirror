---
layout: Conceptual
title: Teams policy packages for government - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/policy-packages-gov
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: aaglick
ms.date: 2026-08-03T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use and manage Teams policy packages for your government organization.
locale: en-us
document_id: 855515be-b6e0-5a9f-19aa-1cd6cdf21a97
document_version_independent_id: c5bb5c47-cec9-6d8e-1cba-6c327165b53b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/policy-packages-gov.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: policy-packages-gov
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/policy-packages-gov.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: cbf6fb17-cb28-9d4a-18b6-ce184ebaaf04
---

# Teams policy packages for government - Microsoft Teams | Microsoft Learn

Note

Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.

## Overview

A [policy package](manage-policy-packages) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization. Policy packages simplify, streamline, and help provide consistency when managing policies. You can customize the settings of the policies in the package to suit the needs of your users. When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings. You can manage policy packages by using the Microsoft Teams admin center or PowerShell.

Policy packages pre-define policies for the following, depending on the package:

- Messaging
- Meetings
- Calling
- App setup
- Live events

Teams currently includes the following policy packages for government.

| Package name in the Microsoft Teams admin center | Best used for | Description |
| --- | --- | --- |
| Public safety officer | Public safety officers in your government organization | Creates a set of policies and policy settings that apply to public safety officers in your organization. |
| Frontline manager | Frontline Managers in your government organization | Creates a set of policies and applies those settings to Frontline Managers in your organization. |
| Frontline worker | Frontline Workers in your government organization | Creates a set of policies and applies those settings to Frontline Workers in your organization. |

![Screenshot of healthcare policy packages.](media/policy-packages-gov.png)

Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package. For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety\_Officer is created for each policy in the package.

![Screenshot of policies in the Healthcare clinical worker package.](media/policy-packages-public-safety-officer.png)

## Manage policy packages

### View

View the settings of each policy in a policy package before you assign a package. In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.

Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.

### Customize

Customize the settings of policies in the policy package, as needed, to fit the needs of your organization. Any changes you make to policy settings are automatically applied to users who are assigned the package. To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.

Keep in mind that you can also change the settings of policies in a package after you assign the policy package. To learn more, see [Customize policies in a policy package](manage-policy-packages#customize-policies-in-a-policy-package).

### Assign

Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.

#### Assign a policy package to one or several users

To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.

![Screenshot of how to assign a policy package in the admin center.](media/policy-packages-healthcare-assign.png)

To learn more, see [Assign a policy package](assign-policy-packages).

If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.

#### Assign a policy package to a group

Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list. The policy assignment is propagated to members of the group according to precedence rules. As members are added to or removed from a group, their inherited policy assignments are updated accordingly. This method is recommended for groups of up to 50,000 users but will also work with larger groups.

To learn more, see [Assign a policy package to a group](assign-policy-packages#assign-a-policy-package-to-a-group).

#### Assign a policy package to a large set (batch) of users

Use batch policy package assignment to assign a policy package to large sets of users at a time. You use the [New-CsBatchPolicyPackageAssignmentOperation](/en-us/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign. The assignments are processed as a background operation and an operation ID is generated for each batch.

A batch can contain up to 5,000 users. You can specify users by their object Id, UPN, SIP address, or email address. To learn more, see [Assign a policy package to a batch of users](assign-policy-packages#assign-a-policy-package-to-a-batch-of-users).