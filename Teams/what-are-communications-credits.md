---
layout: Conceptual
title: What are Communication Credits? - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/what-are-communications-credits
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.reviewer: dachocro
ms.date: 2026-03-24T00:00:00.0000000Z
ms.topic: concept-article
ms.assetid: 524dbea7-117f-493d-8005-6461f7f10059
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- admindeeplinkMAC
- admindeeplinkTEAMS
description: Learn about Communication Credits funding, how to find rates, and which services you receive.
locale: en-us
document_id: d52a9779-b72d-dea0-eac2-6c04a8c282eb
document_version_independent_id: d3c3d968-9e54-ec42-3438-9320e23d68b9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/what-are-communications-credits.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: what-are-communications-credits
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/what-are-communications-credits.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: daf6f235-8643-8aca-3b68-13111db367a4
---

# What are Communication Credits? - Microsoft Teams | Microsoft Learn

Communication Credits are a billing tool to pay for consumed minutes of Audio Conferencing and Microsoft Calling Plan overages. Communication Credits support multiple billing use cases, including:

- All usage of toll-free numbers that support your tenant’s Audio-Conferencing service, Teams Phone auto attendants, and Teams Phone call queues.
- Toll-free calls are billed per minute and require a positive Communication Credits balance.
- Dialing out from a Teams meeting or using Call Me At feature to add an audio conference participant who is in a country or region that is not included in your dial out minute pool minutes (Non zone A country). For more information on Dial out /Call me at minute pool and Zone A countries see [Audio Conferencing subscription "Dial-Out"/"Call Me At" minutes benefit](audio-conferencing-subscription-dial-out).
- Overages related to Teams meeting dial-out calls that exceed the pool of Audio-Conferencing minutes.
- Overages of any calls (domestic or international) beyond the Calling Plan’s included minutes.
- All outgoing calls when using a **Pay-As-You-Go Calling Plan**.

To set up Communication Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization).

## Do I need Communication Credits?

Not all customers need to set up Communication Credits.

Outbound calls to some destinations may already be included in your Audio Conferencing or Calling Plan subscription. Check your subscription information for details before purchasing Communication Credits you don't need.

### Conflicting organization addresses

If your organization is located in a different region than the billing address of your Enterprise Agreement (EA), you might not be able to purchase Communication Credits.

If you're unable to purchase Communication Credits, open a support ticket from the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2166757), and we can work with you to mitigate this issue until a permanent solution is in place.

### Customers without a Microsoft Online Subscription Agreement (MOSA) billing account

Microsoft 365 services are assigned a billing account when they're purchased.

Because of the billing differences between billing account types, these two requirements must be met to purchase Communication Credits:

1. Your Calling and Audio Conferencing subscriptions use a Microsoft Online Subscription Agreement (MOSA) billing account.
2. Your default billing account is set to your MOSA billing account.
    1. For instructions on setting your default billing account, see [Select a default billing account](/en-us/microsoft-365/commerce/manage-billing-accounts#select-a-default-billing-account).

The Microsoft Customer Agreement (MCA) billing account type allows customers to pay for services after the services were consumed, also known as post-usage billing. Because Communication Credits are a prepaid budget to support outgoing minutes, they're not available to purchase for customers with an MCA billing account for their Calling and Audio Conferencing subscriptions or with an MCA billing account as their default billing account.

It's possible for your account to have both MCA and MOSA billing accounts. Make sure that your default billing account and Calling and Audio Conferencing subscriptions are using the MOSA billing account if you want to use communication credits.

To learn how to check if your Calling and Audio Conferencing subscriptions' billing accounts are MCA or MOSA, see [Understand your Microsoft business billing account](/en-us/microsoft-365/commerce/manage-billing-accounts#view-my-billing-accounts).

Warning

MCA customers need to turn off Communication Credits automatic recharge. For instructions on how to turn off Communication Credits auto recharge, see [Turn off Communication Credits auto recharge for Microsoft MCA customers](turn-off-communication-credits-auto-recharge-mca-customers).

### Your Calling Plan or Audio Conferencing plan is through a Cloud Solution Provider (CSP)

If you purchased your Calling or Audio Conferencing plan through a Cloud Solution Provider (CSP), you can't acquire Communication Credits in the Microsoft 365 admin center. Your CSP needs to fund Communication Credits on your behalf.

If you want the ability to fund your Calling or Audio Conferencing plan with Communication Credits on your own, purchase your Calling and Audio Conferencing plans from the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) or the [Microsoft sales page](https://www.microsoft.com/microsoft-teams/microsoft-teams-phone) yourself.

## What are the Communication Credits rates?

See the cost of calls for Teams Calling Plans at [Cloud-Based Phone System for Voice Calling](https://go.microsoft.com/fwlink/p/?LinkId=799523) and scroll to the *See rates for where you want to call* section.

## Determine how many Communication Credits to purchase

If you choose to fund your Communication Credits balance with a one-time amount and then the balance falls to zero, most calling scenarios will no longer work, including toll-free phone numbers.

As such, we recommend that you use the **Auto-recharge** setting to avoid any disruption of service should your Communication Credits balance reach 0 (zero). View your current Communication Credits balance by going to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and selecting **Billing** &gt; **Your products** &gt; **Communications Credits**.

If you're ready to set up Communication Credits, see [Set up Communication Credits for your organization](set-up-communications-credits-for-your-organization).

### View your usage data in the Teams admin center

Each organization has different calling volumes and rates to consider. Retrieve your usage data from your service provider. For organizations using Teams as their service provider, review your data by completing the following steps:

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) with your Teams admin credentials.
2. In the left navigation menu, select **Analytics & reports** &gt; **Usage reports**.
3. On the **Usage reports** page, select **PSTN and SMS (preview) usage** from the **Report** dropdown menu and a date range to review.
4. Select the **Run report** button.

This report lets you export the call data records to Excel and create custom reports.

For more information about Teams usage reports, see [Teams PSTN usage report](teams-analytics-and-reports/pstn-usage-report).

## Who receives notifications about Communication Credits statuses?

Important notifications related to the Communication Credits status of your organization are sent to the following admins:

- Application Administrator
- Authentication Administrator
- Azure AD Joined Device Local Administrator
- Billing Administrator
- Cloud Device Administrator
- Company Administrator
- Device Administrator
- Global Administrator
- Helpdesk Administrator
- License Administrator
- Lync Service Administrator
- Privileged Authentication Administrator
- Service Support Administrator
- Skype for Business Administrator
- Teams Administrator
- Teams Communications Administrator
- Teams Communications Support Engineer
- Teams Communications Support Specialist
- User Account Administrator
- User Administrator

These notifications include when transactions succeed, when recharge transactions fail (such as an expired credit card), and when the Communication Credits balance reaches 0 (zero).

## Want to know about plans and pricing?

You can see the plans and pricing by visiting one of the following links:

- [Calling Plans](https://go.microsoft.com/fwlink/?linkid=799761)
- [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=799762)
- [Phone System](https://go.microsoft.com/fwlink/?linkid=799763)

You can also see information about pricing by [signing in to the Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and going to **Marketplace**.

To see a table with the licenses you need for each feature, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing).