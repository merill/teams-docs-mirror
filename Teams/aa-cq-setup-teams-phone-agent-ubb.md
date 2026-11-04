---
layout: Conceptual
title: Setup - Teams Phone Agent - Usage-based billing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-teams-phone-agent-ubb
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-10-19T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to set up usage-based billing and spending policies for Teams Phone Agent.
description: Learn how to set up usage-based billing for Teams Phone Agent.
locale: en-us
document_id: b932a764-c3aa-e6e4-a46c-228a8ce4532b
document_version_independent_id: b932a764-c3aa-e6e4-a46c-228a8ce4532b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-teams-phone-agent-ubb.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-teams-phone-agent-ubb
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-teams-phone-agent-ubb.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ef36b0f6-47ff-88da-61dd-d6255dc8d727
---

# Setup - Teams Phone Agent - Usage-based billing - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

Caution

**Daylight Savings Time changes – Manual changes to auto attendant time zones required by some customers.**

On November 1, 2026, Daylight Savings Time will end in North America.

In Canada, the provinces of Alberta, British Columbia, and Manitoba will remain on Daylight Savings Time and will not move the clocks back one hour.

Customers with Teams Phone Agents serving these provinces that have time zone configurations that reference **(UTC-7:00) Mountain Time (US & Canada)**, **(UTC-8:00) Pacific Time (US & Canada)**, or **(UTC-05:00) Eastern Time (US & Canada)** must be updated as follows:

- Alberta: Permanently moves to UTC-6:00.

    - Change the auto attendant time zone selection from **(UTC-7:00) Mountain Time (US & Canada)** to **(UTC-6:00) Saskatchewan** as DST is not observed in Saskatchewan.
- British Columbia: Permanently moves to UTC-7:00.

    - Change the auto attendant time zone selection from **(UTC-8:00) Pacific Time (US & Canada)** to **(UTC-7:00) Arizona** as DST is not observed in Arizona.
- Manitoba: Permanently moves to UTC-5:00.

    - Change the auto attendant time zone selection from **(UTC-05:00) Eastern Time (US & Canada)** to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

In Ontario, the following communities and areas will not turn clocks back and will remain on Central Daylight Time year‑round:

- Kenora
- Dryden
- Fort Frances
- Sioux Lookout
- Red Lake
- Rainy River
- Other communities west of the 90th meridian that currently follow Central Time and change clocks seasonally

Customers with Teams Phone Agents serving these areas that have time zone configurations that reference **(UTC-05:00) Eastern Time (US & Canada)** should change the time zone selection to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

This article is for IT pros and Teams administrators who want to set up usage-based billing for Teams Phone Agent.

## Planning and licensing review

### Planning

- [Usage-based billing](aa-cq-plan-teams-phone-agent-ubb)
- [Copilot Credit Estimator](https://nptnlopcost-ppe-h8b6dtchacfcgqhk.b02.azurefd.net/#/estimator).

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)

## Known issues

None.

## What's new in Teams Phone Agent (last six months)

- October 21, 2026
    - [Spam detection](aa-cq-setup-teams-phone-agent-template-spam-detection) can be configured in Teams admin center.
- October 19, 2026
    - [Copilot Credit Estimator](https://nptnlopcost-ppe-h8b6dtchacfcgqhk.b02.azurefd.net/#/estimator) now supports Teams Phone Agent.
- October 14, 2026
    - Teams Phone Agent now supports 42 voices, including 33 new ones.
- September 30, 2026
    - Teams Phone Agent is now generally available to all customers.
    - [Appointments integration with Microsoft Bookings](aa-cq-setup-teams-phone-agent-tools-appointments) can be configured in Teams admin center.
    - [Automatic Recording for Teams Phone Agent](aa-cq-setup-teams-phone-agent-template-recording-automatic) can be configured in Teams admin center.
    - [Maximum call length with configurable disconnect message](aa-cq-setup-teams-phone-agent#configurable-call-length) can be configured in Teams admin center.
    - Question and Answers URLs are refreshed daily.
- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent updated.
- September 1, 2026
    - Appointments integration with Microsoft Bookings can be configured via PowerShell.
- August 31, 2026
    - [AI disclaimer](aa-cq-setup-teams-phone-agent#ai-disclaimer-customization) can be configured in Teams admin center.
    - [Maximum call length](aa-cq-setup-teams-phone-agent#configurable-call-length) can be configured in Teams admin center.
- August 17, 2026
    - Automatic Recording for Teams Phone Agent can be configured via PowerShell.
- August 12, 2026
    - Spam detection can be configured via PowerShell.
    - AI disclaimer customization can be configured via PowerShell.
    - Maximum call length can be configured in PowerShell.
- July 20, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent is now available.
- June 15, 2026
    - Entered Frontier Public Preview

## Teams Phone Agent usage-based billing

All Teams Phone Agent resource accounts in the same Microsoft 365 security group follow the same spending policy. To apply different spending limits to different Teams Phone Agents, create separate security groups.

Limit the number of people who own these security groups.

## Create a Microsoft 365 security group

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Teams & groups**, **Active teams and groups**, **Security groups**.
2. Select **Add a security group**.
3. On the **Set up the basics** page, add your group name and a description and choose **Next**.
4. On the **Edit settings** page, select whether you want to allow Microsoft Entra roles to be assigned to the group and select **Next**.
    - Teams Phone Agent doesn't require this setting.
5. Review your selections and choose **Create group** and **Close**.

## Add Teams Phone Agent resource accounts

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Teams & groups**, **Active teams and groups**, **Security groups**.
2. Select the security group created.
3. On the **General** tab, select **Add owners** to add group owners.
4. On the **Members** tab, select **View all and manage members**, **+ Add members**, and use the **Search** box to find the resource accounts for the Teams Phone Agent. Select **Add** and then select **Close**.
    - The search returns all matching resource accounts, not only Teams Phone Agent accounts.

For more information, see [Create, edit, or delete a security group](/en-us/microsoft-365/admin/email/create-edit-or-delete-a-security-group).

## Create a spending policy

Note

These steps require the **AI Administrator** role.

### Add spending policy

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Copilot** and **Cost Management**.
2. Select the **Configuration** tab and then select **+ Add spending policy**.

### Agents and services

1. Turn off **Allow new Agents and services as they become available**.
2. Make sure that only the **Teams Phone Agent**service is selected.
    - Clear the checkboxes for all other services.
3. Select **Next**.

### Access scope

1. Give the spending policy a name.
2. Select **Specific groups**.
3. Select the Microsoft 365 security groups that contain your Teams Phone Agent resource accounts that should be part of this spending policy.
4. Select **Next**.

### Set limits and alerts

For the security groups that you selected for this policy, select the credit limits that apply to them.

#### Set the monthly spending limit for this policy

Set spending limits on a per-calendar month basis.

- **Unlimited monthly budget**: No limit is applied.
- **Limited monthly budget**: Limit the number of credits that this policy can spend each month.
    - Any Teams Phone Agent in the security group can consume the entire monthly budget.
    - When the limit is reached, Teams Phone Agent works as an Auto Attendant until credits reset on the first day of the next month.
    - The policy always uses prepaid credits first, whether through capacity packs or through pre-purchase plans, before moving to pay-as-you-go.

#### Select monthly budget limits for users (optional)

Set a monthly limit per resource account in the security group. This limit prevents a single Teams Phone Agent from spending all available credits.

- Specify the maximum credit limit users can spend per month.

#### Define alerts (optional)

Configure policy level alerts:

- Specify the usage threshold for the policy.
- Select the administrators or stakeholders who must receive email notifications when policy usage reaches the threshold.
- Review the prepopulated administrator email address and add other recipients as needed.

If the policy has a monthly per-user limit, configure user-level threshold notifications:

- Turn on user notifications for the policy.
- Specify the threshold percentage at which users receive an email.

User-level notifications alert users as they approach their spending limit. The user-level notifications are separate from notifications sent to administrators or stakeholders about overall policy consumption.

Select **Next**.

### Billing method

By default, the policy uses the billing method from the default spending policy.

If you're a Global administrator or a Billing administrator, you can override this selection and select how this policy should be billed. This feature enables you to do departmental billing and vary billing methods for each group, department, or set of users.

**For Global or Billing administrators**

1. If your tenant has capacity packs, you can choose to use them.
2. Alternatively, you can choose a different Azure subscription to bill against. For more information, see [Configure billing methods](/en-us/microsoft-365/copilot/usage-based-billing-copilot-credits-setup#configure-billing-method).
3. Select **Next**

### Review and add the policy

1. Before you create the spending policy, verify these settings:

    - **Budget scope**.
    - **Agents and services**.
    - **Billing method**.
    - **Spending limit**.
    - **User and group limits**.
    - **Alerts**.
2. Select **Create spending policy** to complete the setup.

A notification confirms that the spending policy is created.

## Related Teams Phone Agent setup and configuration articles

- [Questions and Answers](aa-cq-setup-teams-phone-agent-tools-questions-answers)
- [Appointments](aa-cq-setup-teams-phone-agent-tools-appointments)
- [Third-party voice agents](aa-cq-setup-third-party-voice-agents)
- [Holidays](aa-cq-setup-holidays)
- [Teams Phone Agent](aa-cq-setup-teams-phone-agent)