---
layout: Conceptual
title: Microsoft Teams Calling Plans - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/calling-plans-for-office-365
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-07-30T00:00:00.0000000Z
ms.topic: article
ms.assetid: f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918
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
- O365E_E5Voiceplandetails
- O365M_E5Voiceplandetails
- O365P_E5Voiceplandetails
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Learn about Microsoft Teams Calling Plans and how to get licenses for your organization.
locale: en-us
document_id: 33bfc660-573d-b57e-8b67-6aa1fbe820ad
document_version_independent_id: 53318fba-10e9-cd4b-f0ee-397cd10e8c0c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/calling-plans-for-office-365.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: calling-plans-for-office-365
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/calling-plans-for-office-365.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4143aa04-f22a-7b10-0c5f-177127f8ec27
---

# Microsoft Teams Calling Plans - Microsoft Teams | Microsoft Learn

Microsoft Teams Calling Plans provide PSTN connectivity for Teams Phone, enabling users to make and receive external phone calls. This article helps you choose the right Calling Plan, understand licensing requirements, and purchase Calling Plans for your organization. This solution is the simplest option that connects Teams Phone to the PSTN for external calling.

To find out if Microsoft Teams Calling Plans are available in your area, see [Country and region availability](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

If Teams Calling Plans aren't available in your area, Microsoft provides other PSTN connectivity options. For more information on all PSTN connectivity options, see [PSTN connectivity options](pstn-connectivity).

After reading this article, see [Set up Microsoft Calling Plans](set-up-calling-plans).

## Calling Plan options

Microsoft offers three Calling Plan options.

| Calling Plan | Domestic calls | International calls | Outgoing call billing | Best for |
| --- | --- | --- | --- | --- |
| **Domestic Calling Plan** | Yes | No | Included minutes | Users who call within their assigned country or region |
| **International Calling Plan** | Yes | Yes | Included domestic and international minutes | Users who regularly make international calls |
| **Pay-As-You-Go Calling Plan** | Yes | Yes | Charged by usage | Users with low or variable outgoing call volume |

To decide which option is right for your organization, ask yourself the following:

- Are Teams Calling Plans available in my area? Which user locations have Calling Plan service?
- Do my users need international calling?
- If some of my users don't make a significant number of outgoing calls, is the Pay-As-You-Go Calling Plan the most economical option for them?

All users in the same country with the same Calling Plan share a pool of minutes. For example, if you have 100 users located in the United States with a Domestic Calling Plan assigned, each user is allocated 3,000 minutes and they all share a pool of 300,000 minutes. All calls exceeding these minutes are billed per minute. **Pooling is only available on identical Calling Plans.**

Note

The country is based on the location of the user's license. You can check the users license in the **Microsoft 365 admin center** &gt; **Active users** and **NOT** the billing address listed in the **Microsoft 365 admin center** under the **Settings &gt; Org Settings &gt; Organization profile &gt; Organization Information.**

For more information about monthly minutes available in each country, see [Country and region availability](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

The following diagram provides a high-level overview of Microsoft Teams Calling Plans and the available plan options.

[![Microsoft Teams Calling Plans overview. This diagram shows how Calling Plans connect Teams Phone to the PSTN for external calling.](media/calling-plans-for-office-365/calling-plans-chart.png)](media/calling-plans-for-office-365/calling-plans-chart.png#lightbox)

### Domestic Calling Plan

With the Domestic Calling Plan, licensed users can call out to numbers located in the country where they're assigned in Microsoft 365. Unlimited incoming minutes are included. Outgoing minutes are included based on the license purchased.

There are two Domestic Calling Plan options to choose from based on your organization's billing location.

- **Microsoft Teams Domestic Calling Plan (customers in US/UK/CA)**: For organizations in the United States, Puerto Rico, United Kingdom, and Canada. Organizations can assign this license to end users in any market where Calling Plans are available.
- **Microsoft Teams Domestic Calling Plan (customers outside US/UK/CA)**: For organizations in Austria, Belgium, Croatia, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hong Kong SAR, Hungary, Ireland, Italy, Latvia, Lithuania, Luxembourg, Netherlands, New Zealand, Norway, Poland, Portugal, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, and Switzerland. Organizations can assign this license to end users in any market where Calling Plans are available.

Once these plans are assigned, the minutes available vary depending on the location of the end user. For more information, see [Country and region availability for Audio Conferencing and Calling Plans](calling-plan-overview).

Note

Mexico has its own Domestic Calling Plan. You must purchase the independent Domestic Calling Plan for Mexico.

### International Calling Plan

The International Calling Plan includes both domestic and international minutes for outbound calls. Domestic minutes allow users to call numbers in the country where their Microsoft 365 license is assigned. International minutes allow users to call international numbers in [196 countries](country-and-region-availability-for-audio-conferencing-and-calling-plans/users-can-make-outbound-calls-to-these-countries-and-regions). Unlimited incoming minutes are included. Outgoing minutes are included based on the license purchased.

For more information, see [Country and region availability for Audio Conferencing and Calling Plans](calling-plan-overview).

### Pay-As-You-Go Calling Plan

With the Pay-As-You-Go Calling Plan, licensed users can call out to numbers located in the country where their Microsoft 365 license is assigned to the user based on the user's location, and to international numbers in [196 countries](country-and-region-availability-for-audio-conferencing-and-calling-plans/users-can-make-outbound-calls-to-these-countries-and-regions).

Unlimited incoming minutes are included. No outgoing minutes are included. All outgoing calls are charged based on the minutes used, either with Communication Credits or post-usage billing (for new commerce experience calling subscriptions only). Licenses are assigned to users based on their location.

To learn how to fund and use minutes for a Pay-As-You-Go Calling Plan, see How to fund a Pay-As-You-Go Calling Plan.

There are three **Pay-As-You-Go Calling Plan** options to choose from:

- **Pay-As-You-Go Calling Plan Zone 1**: For users in the United States and Puerto Rico, United Kingdom, and Canada.
- **Pay-As-You-Go Calling Plan Zone 2**: For users in Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hong Kong SAR, Hungary, Ireland, Italy, Latvia, Lithuania, Luxembourg, Netherlands, New Zealand, Norway, Poland, Portugal, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, and Switzerland.
- **Pay-As-You-Go Calling Plan Mexico**: For users in Mexico.

    Note

    Pay-As-You-Go Calling Plan Mexico can't be purchased by US or PR customers.

## How to buy Calling Plans

Note

Before you acquire or port telephone numbers, verify whether Know Your Customer (KYC) approval is required for the target country or region. KYC review is completed at the tenant level and most reviews are completed within three business days. Complete KYC early so that number acquisition or porting is not delayed.

1. You must first purchase a **Teams Phone add-on license**. To do that, [sign in to the Microsoft 365 admin center and choose](https://go.microsoft.com/fwlink/p/?linkid=868433)**[Billing](https://go.microsoft.com/fwlink/p/?linkid=868433)** &gt; **Your products** &gt; **Add more products** &gt; **Add-ons &gt; Select the add on for Teams phone that you want &gt; Buy**.

    Note

    Depending on your plan, you may need to buy more add-ons before you can buy Teams Phone licenses. To learn more, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing).
2. After you buy Teams Phone licenses, you can buy a Calling Plan by [signing in to the Microsoft 365 admin center and choose](https://go.microsoft.com/fwlink/p/?linkid=868433)**[Billing](https://go.microsoft.com/fwlink/p/?linkid=868433)** &gt; **Your products** &gt; **Add more products** &gt; **Add-ons &gt; Select the add on for Microsoft Teams calling plan that you want &gt; Buy**.
3. Alternately you can also buy Teams phone and Calling plan bundle instead of purchasing Teams phone and calling plan separately, to do that, [signing in to the Microsoft 365 admin center and choose](https://go.microsoft.com/fwlink/p/?linkid=868433)**[Billing](https://go.microsoft.com/fwlink/p/?linkid=868433)** &gt; **Your products** &gt; **Add more products** &gt; **Add-ons &gt; Select the add on for Teams phone with "domestic" or "international" calling plan per your preference &gt; Buy**.

You can buy and assign different Calling Plans to different users, depending on the needs of your organization. After you select the Calling Plan you need, proceed to checkout. You assign a plan to each user in the Microsoft 365 admin center. To learn how, see [Assign Microsoft Teams add-on licenses](/en-us/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## How to fund a Pay-As-You-Go Calling Plan

Pay-As-You-Go Calling Plans don't have a set number of outgoing call minutes like the Domestic or International Calling Plans. Instead, some admins may need to take additional steps to fund their Pay-As-You-Go Calling Plan. Until the Pay-As-You-Go Calling Plan is properly funded, users aren't able to make outgoing calls.

There are two ways you can fund and use minutes with a Pay-As-You-Go Calling Plan:

- **Purchase the Pay-As-You-Go Calling Plan with a Microsoft Customer Agreement (MCA)**

    - Customers who purchased their calling plan with a Microsoft Customer Agreement (MCA) are able to pay for the outgoing call minutes they used in the previous month. This billing is also called post-usage or post-consumption billing.
    - For instructions on purchasing a calling plan with an MCA, see [Enable pay-as-you-go for your subscription](/en-us/microsoft-365/commerce/subscriptions/manage-pay-as-you-go-services) and [New commerce overage for telco pay-as-you-go](/en-us/partner-center/new-commerce-telco-payg).
- **Purchase Communication Credits**

    - This option is for customers who purchased their calling plan with a Microsoft Online Subscription Agreement (MOSA). These customers need to purchase Communication Credits to fund their Pay-As-You-Go Calling Plan.
    - For instructions on how to purchase and assign Communication Credits, see [Set up Communication Credits for your organization](set-up-communications-credits-for-your-organization).

## Pricing information

- [Pricing for Calling Plans and Teams Phone](https://www.microsoft.com/microsoft-365/microsoft-teams/voice-calling).