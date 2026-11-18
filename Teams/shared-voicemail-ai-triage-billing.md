---
layout: Conceptual
title: Shared voicemail AI triage billing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/shared-voicemail-ai-triage-billing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Configure usage-based billing and spending policies for shared voicemail AI triage in Microsoft Teams.
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
document_id: fe965a9a-4664-0369-bc2b-83b713ba4bff
document_version_independent_id: fe965a9a-4664-0369-bc2b-83b713ba4bff
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/shared-voicemail-ai-triage-billing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: shared-voicemail-ai-triage-billing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/shared-voicemail-ai-triage-billing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: 31c50bf5-353c-63c8-91b2-e3c5c4441135
---

# Shared voicemail AI triage billing - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to set up usage-based billing for shared voicemail AI triage.

Important

This feature is available only through the Microsoft Frontier Program. General availability (GA) timing hasn't been announced yet.

## Planning and licensing review

### Planning

- [Usage-based billing](/en-us/copilot/implement/usage-based-billing-copilot-credits-setup)
- [Configure billing methods](/en-us/copilot/implement/usage-based-billing-copilot-credits-setup#configure-billing-method)

### Licensing

- Shared voicemail AI triage requires usage-based billing.
- A Microsoft 365 Copilot license isn't required for shared voicemail triage.
- For Queues app scenarios, the Queues app has separate licensing requirements (Teams Premium).

## Shared voicemail AI triage usage-based billing

Each shared voicemail is charged once per processed voicemail, regardless of how many users receive it.

If you want to enable shared voicemail AI triage for all resource accounts, use the **All users** option in spending policy scope. This approach is recommended when you want to enable AI triage for all shared voicemail in your organization.

If you want to limit which resource accounts have voicemail AI triage enabled, create a Microsoft 365 security group and use the **Specific groups** option in the spending policy scope. To apply different spending limits to different resource accounts, create separate security groups. Limit the number of people who own these security groups.

Configuring a spending policy alone doesn't enable AI triage for resource accounts. AI triage must also be enabled in the specific Call Queue, Auto Attendant, and Teams Phone Agent templates.

### For "Specific groups" option create a Microsoft 365 security group

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Teams & groups** &gt; **Active teams and groups** &gt; **Security groups**.
2. Select **Add a security group**.
3. Complete group setup and create the group.

and add Call Queue, Auto Attendant, and Teams Phone Agent resource accounts to the group

1. Open the security group you created.
2. Add owners.
3. Add the resource accounts used by Auto Attendants, Call Queues, or Teams Phone Agents.

## Create a spending policy

These steps require the **AI Administrator** role.

### Add spending policy

1. In the Microsoft 365 admin center, go to **Copilot** &gt; **Cost Management**.
2. Select the **Configuration** tab.
3. Select **+ Add spending policy**.

### Agents and services

1. Turn off **Allow new Agents and services as they become available**.
2. Select only **AI Triage for Shared Voicemail**.
3. Clear all other services.
4. Select **Next**.

### Access scope

1. Name the policy.
2. Select one of the following:
    - **Specific groups** to limit applicable Call Queue, Auto Attendant, and Teams Phone Agent resource accounts, and then select the Microsoft 365 security groups that contain these resource accounts.
    - **All users** to apply the policy to all resource accounts.
3. Select **Next**.

### Set limits and alerts

1. Configure monthly spending limits.
2. Optionally configure per-resource-account limits.
3. Optionally configure policy-level and user-level alerts.
4. Select **Next**.

### Billing method

1. Use the default spending policy billing method, or override it if you're a Global admin or Billing admin.
2. Select **Next**.

### Review and add the policy

1. Verify scope, services, billing method, limits, and alerts.
2. Select **Create spending policy**.

## Activation prerequisites and charging behavior

Shared voicemail AI triage runs only when both are true:

- A spending policy is configured for **AI Triage for Shared Voicemail** for the applicable resource account in Microsoft 365 admin center.
- An "AI triage for shared voicemails" template is selected under the specific Auto Attendant, Call Queue, or Teams Phone Agent settings in Teams admin center.

If no template is selected, AI triage isn't performed and no usage-based billing charges are incurred, even when a spending policy is configured.

## Billing attribution

Shared voicemail AI triage is billed once per processed voicemail, regardless of how many users receive the voicemail.

The charge is attributed to the resource account associated with the Auto Attendant, Call Queue, or Teams Phone Agent. If an Auto Attendant or Call Queue doesn't have its own resource account, the root resource account associated with the phone number is used for billing.