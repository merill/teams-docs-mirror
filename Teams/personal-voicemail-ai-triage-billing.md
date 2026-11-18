---
layout: Conceptual
title: Personal voicemail AI triage billing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/personal-voicemail-ai-triage-billing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Configure usage-based billing and spending policies for personal voicemail AI triage in Microsoft Teams.
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-11-13T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
locale: en-us
document_id: 5c561735-32ac-d18d-42f9-16cd594f7499
document_version_independent_id: 5c561735-32ac-d18d-42f9-16cd594f7499
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/personal-voicemail-ai-triage-billing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: personal-voicemail-ai-triage-billing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/personal-voicemail-ai-triage-billing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: 46af9445-94aa-c7e1-9dd0-e9438bd56fba
---

# Personal voicemail AI triage billing - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to set up usage-based billing for personal voicemail AI triage.

Important

This feature is available only through the Microsoft Frontier Program. General availability (GA) timing hasn't been announced yet.

## Planning and licensing review

### Planning

- [Usage-based billing](/en-us/copilot/implement/usage-based-billing-copilot-credits-setup)
- [Configure billing methods](/en-us/copilot/implement/usage-based-billing-copilot-credits-setup#configure-billing-method)

### Licensing

Personal voicemail AI triage requires:

- A Microsoft 365 Copilot license for each user.
- Usage-based billing.

## Personal voicemail AI triage usage-based billing

Each personal voicemail is charged once per processed voicemail.

If you want to enable personal voicemail AI triage for all eligible users, use the **All users** option in spending policy scope.

If you want to limit which users have personal voicemail AI triage enabled, create a Microsoft 365 security group and use the **Specific groups** option in the spending policy scope. To apply different spending limits to different users, create separate security groups. Limit the number of people who own these security groups.

Configuring a spending policy alone doesn't enable AI triage for users. AI triage must also be enabled in voicemail policy.

### For **Specific groups** option create a Microsoft 365 security group

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Teams & groups** &gt; **Active teams and groups** &gt; **Security groups**.
2. Select **Add a security group**.
3. Complete group setup and create the group.

and Add users to the group

1. Open the security group you created.
2. Add owners.
3. Add users who should be included in this policy.

## Create a spending policy

These steps require the **AI Administrator** role.

### Add spending policy

1. In the Microsoft 365 admin center, go to **Copilot** &gt; **Cost Management**.
2. Select the **Configuration** tab.
3. Select **+ Add spending policy**.

### Agents and services

1. Turn off **Allow new Agents and services as they become available**.
2. Select only **AI Triage for Personal Voicemail**.
3. Clear all other services.
4. Select **Next**.

### Access scope

1. Name the policy.
2. Select one of the following:
    - **Specific groups** to limit applicable users, and then select the Microsoft 365 security groups that contain the users.
    - **All users** to apply the policy to all eligible users.
3. Select **Next**.

### Set limits and alerts

1. Configure monthly spending limits.
2. Optionally configure per-user limits.
3. Optionally configure policy-level and user-level alerts.
4. Select **Next**.

### Billing method

1. Use the default spending policy billing method, or override it if you're a Global admin or Billing admin.
2. Select **Next**.

### Review and add the policy

1. Verify scope, services, billing method, limits, and alerts.
2. Select **Create spending policy**.

## Activation prerequisites and charging behavior

Personal voicemail AI triage runs only when all of the following are true:

- The user has a Microsoft 365 Copilot license.
- A spending policy for **AI Triage for Personal Voicemail** is configured for that user in the Microsoft 365 admin center.
- **Personal voicemail AI triage** is enabled in [Voicemail policies](manage-voicemail-policies) in the Teams admin center.

If any requirement isn't met, AI triage isn't performed and no usage-based billing charges are incurred.