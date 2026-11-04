---
layout: Conceptual
title: Set up Microsoft Calling Plans - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-calling-plans
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: roykuntz, jastark
ms.date: 2026-07-31T00:00:00.0000000Z
ms.topic: install-set-up-deploy
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365solution-voice
- m365solution-scenario
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- LIL_Placement
- seo-marvel-mar2020
description: Learn how to set up Calling Plans, including how to buy & assign licenses, get phone numbers, and add emergency addresses & locations.
locale: en-us
document_id: 8354e80d-02da-7f51-a713-e698322e8ec1
document_version_independent_id: ef42d9af-336a-e014-de0a-b7bf7bb1f87d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-calling-plans.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-calling-plans
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-calling-plans.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 462e5599-16a3-d0c2-6fb9-28d3e09946ec
---

# Set up Microsoft Calling Plans - Microsoft Teams | Microsoft Learn

This article describes how to set up Microsoft Calling Plans with Teams Phone. This solution is the simplest option that connects Teams Phone to the Public Switched Telephone Network (PSTN) for external calling. With this option, **Microsoft acts as your PSTN carrier**.

This article assumes that you already have Teams Phone licenses for your users, which is a requirement for purchasing Calling Plans. If you do not have a Teams Phone license, see [Set up Teams Phone](setting-up-your-phone-system) and [Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).

For more information about all Microsoft Calling Plan options, see [Microsoft Teams Calling Plans](calling-plans-for-office-365).

For more information about Teams Phone, see [What is Teams Phone](what-is-phone-system-in-office-365).

Important

- Verify that Microsoft Calling Plans are available in your country or region.
- Before you acquire or port telephone numbers, verify whether Know Your Customer (KYC) approval is required for the target country or region. KYC review is completed at the tenant level, and most reviews are completed within three business days. Complete KYC early so that number acquisition or porting isn't delayed.
- Ensure you have the required Teams Phone and Calling Plan licenses.

## Step 1: Find out if Calling Plans are available in your country/region

Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country/region to get availability information about Calling Plans.

If Calling Plans aren't available in your country/region, see [PSTN connectivity options](pstn-connectivity) for other available PSTN connectivity options.

## Step 2: Complete Know Your Customer verification, if required

Before you purchase licenses or begin acquiring or transferring phone numbers, determine whether Know Your Customer (KYC) verification is required for your organization.

KYC is required in some countries and regions before your organization can acquire or port telephone numbers. The requirements are established by local regulatory authorities and can vary by country or region.

An authorized representative of your organization must complete the verification. The representative must use an individual company email address associated with the business domain being verified. Distribution lists, personal email addresses, and the default `onmicrosoft.com` tenant domain aren't accepted.

To submit or review your organization's KYC information:

1. In the Teams admin center, go to **Voice** &gt; **Service configuration** &gt; **Know Your Customer**.
2. Select **Add KYC information** and complete the required business, domain, and supporting-document verification.
3. Submit the request and monitor the **KYC Status** from the same page.

Most KYC reviews are completed within three business days. Microsoft sends status notifications to the email address provided during submission. If the status changes to **Action Required**, review the request and provide the additional information or documentation requested.

Wait until the KYC status is **Approved** before proceeding with phone number acquisition or porting.

For complete requirements and status definitions, see [Validate your business identity with PSTN operators using Know Your Customer](teams-phone-know-your-customer).

## Step 3: Buy and assign licenses

1. After you buy and assign **Teams Phone** licenses, you can purchase Calling plans for Teams phone, see [How to buy Calling Plans](/en-us/microsoftteams/calling-plans-for-office-365). For more information, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing).
2. Assign a Calling Plan license to the people in your organization. See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses).

    If you purchase a Pay-As-You-Go Calling Plan, you may need to purchase Communication Credits. To determine if you need to purchase Communication Credits, see [How to fund a Pay-As-You-Go Calling Plan](calling-plans-for-office-365#how-to-fund-a-pay-as-you-go-calling-plan).

## Step 4: Get phone numbers

There are three ways to get new user numbers:

- **Use the Teams admin center.** For some countries/regions, you can get numbers for your users by using the Teams admin center, see [Get Microsoft Teams Calling Plan phone numbers for your tenant](getting-phone-numbers-for-your-users).
- **Port your existing numbers.** You can port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365. After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers. For more information, see [Submitting a port request - Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams).
- **Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new phone numbers using the Teams admin center, or you'll need specific phone numbers or area codes. If so, you can submit a request for "phone number support". To do this, go to **Teams admin center** &gt; **Voice** &gt; **Phone Numbers**, click **Add**, and then click "Get phone number support" at the top right-hand corner of the page. On the resulting page you can create and submit a ticket for our phone number support teams.

## Step 5: Add emergency addresses and locations for your organization

An emergency address must be associated with a phone number. When this association happens can vary among countries/regions. For example, in the United States, you need to associate an emergency address when you assign the phone number to the user. In the United Kingdom, you need to associate an emergency address to the phone number when you're getting the phone numbers from Microsoft 365, or when transferring phone numbers from your current service provider.

For information about emergency calling and managing emergency addresses, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing).

## Step 6: Assign an emergency address and a phone number to a user

You must assign a phone number and an emergency address to each of your users. The emergency address must be created before you can associate it with a phone number. For more information, see [Manage emergency locations](assign-change-emergency-location-user) and [Manage phone numbers for users](assign-change-or-remove-a-phone-number-for-a-user).

Tip

If you add more people to your business right before doing this step, it may take **several hours** for them to appear on the **Voice users** page.

## Step 7: Tell your users about their new phone numbers

Microsoft recommends sending mail or using your business's preferred communication method to tell the people about their new phone numbers.

In **Microsoft Teams**, users can see their phone number by selecting **Calls** in the left navigation. The phone number is shown above the dial pad.

## Run a Self-diagnostics tool

Microsoft 365 admin users have access to diagnostics that can be run within the tenant to verify a user is properly configured to make or receive PSTN calls.

Note

This feature isn't available for Microsoft 365 Government, Microsoft 365 operated by 21Vianet, or Microsoft 365 Germany.

Select Run Tests, as follows. This will populate the diagnostic in the Microsoft 365 Admin Center.

The diagnostic performs a large range of verifications.