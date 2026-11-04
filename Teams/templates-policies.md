---
layout: Conceptual
title: Manage team templates in the admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/templates-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: yinchang
ms.date: 2025-03-13T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.custom:
- chat-teams-channels-revamp
- admindeeplinkTEAMS
- teams-chat-and-channels
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to manage team templates in the admin center
locale: en-us
document_id: 35520227-9576-9bc7-7b3c-a7065a7a601b
document_version_independent_id: ebdc0a1a-a879-8c99-2584-ffe79a2f224a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/templates-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: templates-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/templates-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: cb88405d-cab7-cfec-3bf7-84912836dddf
---

# Manage team templates in the admin center - Microsoft Teams | Microsoft Learn

Manage the team templates that your end users see by creating templates policies in the admin center. Within each templates policy, you can designate which templates are shown or hidden.

Assign different users to different templates policies so that your users view only the subset of team templates specified.

## Create templates policies and assign available templates

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Go to **Teams** &gt; **Templates policies**.
3. Choose **Add**.
4. Give the policy a name and add a short description.
5. In the **Viewable templates** list, select the templates you want to hide, and then select **Hide**.

    You can see the templates you chose to hide in the **Hidden templates** list.
6. To unhide certain templates, go the **Hidden templates** list.
7. Select the templates to unhide, and then select **Show**.

    The selected templates appear in the **Viewable templates** list.
8. Choose **Save**.

    Your new templates policy is displayed in the **Templates policies** list.

## Assign templates policies to users

You can assign a templates policy directly to users, either individually or at scale through a batch assignment. Keep in mind that it might take up to 24 hours for your new policy to take effect for your users.

Note

Assigning templates policies to users based on group membership, such as to all users in a security group, isn't supported.

For an overview of the ways to assign policies in Teams, see [Assign policies in Teams](policy-assignment-overview).

### Assign a templates policy to individual users

You can use the Teams admin center or PowerShell to assign a templates policy to an individual user or to a few users at a time. To learn more, see [Assign a policy to individual users](assign-policies-users-and-groups#assign-a-policy-to-individual-users).

### Assign a templates policy to a batch of users

You can use PowerShell to assign a templates policy to large sets of users at a time. To do this, use the [New-CsBatchPolicyAssignmentOperation](/en-us/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet together with TeamsTemplatePermissionPolicy as the `PolicyType` to submit a batch of users and the templates policy that you want to assign. For example:

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

The assignments are processed as a background operation and an operation ID is generated for each batch. You can then use the [Get-CsBatchPolicyAssignmentOperation](/en-us/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.

To learn more, see [Assign a policy to a batch of users using PowerShell](assign-policies-users-and-groups#use-powershell-method).

## Size limits for templates policies

You can hide a max of 100 templates per policy. The **Hide** button is disabled if the given policy already has 100 templates hidden.

## Frequently asked questions

**Q: If a new template is created, will the template be included in my policies?**

A: Any new templates are visible by default. You can choose to hide the template in the Teams admin center in the **Templates policies** section.

**Q: What happens if a template is deleted?**

A: Any deleted templates are no longer present in any templates policies.

**Q: Can I assign multiple users to a templates policy in the Teams admin center?**

A: Yes.

1. In the Teams admin center, go to **Users** &gt; **Manage users**.
2. In the list of users, select the users you want to assign to the templates policy.
3. Select **Edit settings**, and then under **Templates policy**, choose the policy you want to assign.
4. Select **Apply**.

To learn more, see [Assign a policy to individual users](assign-policies-users-and-groups#assign-a-policy-to-individual-users).

**Q: How do I view all users assigned to a specific policy?**

A: In the Teams admin center:

1. Go to **Users** &gt; **Manage users**.
2. Select **Filter**, set a filter for the templates policy, and then choose **Apply**.

    ![The selected templates policy and view users.](media/template-policies-5.png)

**Q: Can I manage templates policies via PowerShell?**

A: No, managing templates policies in PowerShell isn't supported. However, you can use PowerShell to assign templates policies to users.