---
layout: Conceptual
title: Create a Brand for SMS in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/sms-setup-brand
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: nijait, julienp
ms.date: 2026-05-29T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
description: Learn how to set up an SMS Brand to enable SMS in Microsoft Teams.
locale: en-us
document_id: c8b12077-aae5-7d7f-f68d-f6dc8467365c
document_version_independent_id: c8b12077-aae5-7d7f-f68d-f6dc8467365c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/sms-setup-brand.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sms-setup-brand
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/sms-setup-brand.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a9cbef99-af30-7a72-d1c9-3424a4a5d68c
---

# Create a Brand for SMS in Microsoft Teams - Microsoft Teams | Microsoft Learn

Note

Service update: If you receive a Brand or Campaign rejection, our Telephone Number Services team is aware and managing a case with you through the [Phone Number Service Center](https://pstnsd.powerappsportals.com) portal. Due to a high volume of requests for SMS in Teams, processing times to facilitate approvals of rejected Brand and Campaign applications for SMS in Teams might take 4 to 6 weeks. We appreciate your patience as we work diligently to address all requests.

This article is for IT administrators and IT professionals who are enabling Short Message Service (SMS) in Teams.

Use this article while creating a brand in Microsoft's Teams admin center to verify and register your company.

Before reading this article, make sure you've read [Plan for SMS in Teams](sms-overview).

Note

SMS in Teams is only available on Calling Plan phone numbers in the United States (including Puerto Rico) and Canada.

Customers must have an approved Brand and Campaign before enabling SMS on Teams Calling Plan numbers.

## Prerequisites

Ensure fundamental understanding of the *purpose* for your Brand, as described in [Learn about SMS Texting in Teams](sms-overview).

Administrators must have one of the following role-based access control (RBAC) roles assigned:

- Teams Administrator
- Teams Communications Administrator
- Teams Telephony Administrator

## Create a Teams SMS brand in Teams admin center

The 10DLC (10-digit long code) registration process involves verifying your organization's identity. To get your organization verified, you build an organization profile as your "Brand" in the Teams admin center.

1. In the Teams admin center, go to **Voice** &gt; **Service configuration** &gt; **SMS** &gt; **Step 1: Create brand**.
2. Select **Create your brand to start / Update brand / View details** to open a right-side configuration slide-out and populate the fields with your company's information.

The form fields change dynamically depending on your company's country/region and status. For example, if your company is registered in the US and is a *publicly traded* company, more fields are required to disclose your company's stock symbol. However, if you have a private company, a stock symbol isn't required.

Populate your Brand application according to the field headers as follows:

### Description

In the first section of the brand form, provide details of your company, as denoted in its country/region.

| Form field | Description |
| --- | --- |
| Brand legal name | Enter your company's legally registered name in your country/region. Ensure that your company name matches your corporation registration and is spelled correctly. |
| Brand display name | Enter your company's *Doing Business As* name or *Trade* name of your company. |
| Tax ID issuing country | Enter the country/region where your company business ID is issued. |
| Tax ID | Enter the Tax ID of your company, respective to the country/region of your company registration.**United States** - US companies (and companies with a US EIN), enter your Tax ID's nine-digit EIN.**Canada** - For companies based in Canada, enter your nine-digit Canadian Business Number (BN) issued by the Canada Revenue Agency (CRA), Corporation/Incorporation Number, or Registry ID.**Outside the United States and Canada** - Businesses outside US & Canada should enter the numeric part of their VAT ID. |
| Brand legal address | Enter the legal address where your company is registered. If you already defined your legal address as an address in **Locations**, select **Use existing** and search for the address by the city or by the location description. If the address isn't already added, select **Add new** and enter it here.Ensure that your legal address matches your corporation registration and is spelled correctly. |
| Website | Enter your company's website. |

### Brand Information

Within the brand information, provide context about your company's business.

| Form field | Description |
| --- | --- |
| Organization Legal Form | Select the legal structure of your company.**Private company** - A private company is owned by individuals or groups and doesn't sell shares to the public.**Publicly Traded Company** - A publicly traded company sells shares on stock exchanges.**Non-Profit Organization** - A non-profit operates for charitable purposes without distributing profits. Only US-based non-profits or non-profits with a US EIN are accepted. Non-US non-profits should register as private companies. For example, if you're a non-profit organization located in Canada, you register as a **Private company**. |
| Brand segment | From the drop-down, select the industry that best categorizes your company's business. |

Note

Brand registration for US Government entities isn't currently supported. Non-US Government entities should register as private companies. Brand registration for Sole Proprietor entities isn't currently supported.

To register **Publicly Traded** brands, additional information is required:

| Form field | Description |
| --- | --- |
| Brand stock symbol | If your company is a publicly traded company, enter your company's stock symbol. |
| Brand stock exchange | If your company is a publicly traded company, select the exchange where it's listed and traded. |
| Business email contact for Two Factor Authentication (2FA) | Brands with a Public Profit entity type are required to complete a two-factor authentication (2FA) process as part of the verification process. Provide the email that should receive the verification email. This email address can't be a personal email address, free email address, or a distribution list (such as sales or support). |

### Contact Information

If there are issues with the registration of your brand, Microsoft Support will reach out to a point of contact that you designate. Enter your contact information according to the field headers as follows:

| Form field | Description |
| --- | --- |
| First name | Enter the first name of the point of contact for this application process. |
| Last name | Enter last name. |
| Phone number | Enter the phone number in E.164 format of the point of contact for inquiries related to this application process.E.164 is the international phone number format that starts with a plus sign (+) followed by your country code, area code, and local number with no spaces, dashes, or parentheses. For example, a US phone number of (202) 555-0123 should be written as: +12025550123. |
| Email address | Enter the email address of the *point of contact* for inquiries related to this application process. We recommend entering a distribution or group list here over a personal email. |

### Terms and Conditions

Once the fields are accurately filled out, select the box to accept Microsoft's terms and conditions.

The terms as follows relate to Microsoft sharing your brand information with an operator, in this case, The Campaign Registry.

> 
> Teams SMS services involve an integration between Microsoft and the underlying carrier, aggregator, or operator ("Operator"). Microsoft must share application details and/or brand information with the Operator to ensure that the program meets regulatory guidelines and standards set by operators. The Operator is the final reviewer and approver of your service application. If the details you provide on your application change, it's your responsibility to resubmit your application with up-to-date information. By submitting an application, you agree that Microsoft may share the application details as necessary for provisioning the Teams messaging service.

### Brand submission and status

After filling out all the applicable fields, select **Submit**.

After reviewing your brand's details and accepting Microsoft's terms and conditions, select **Submit**.

After submission, your brand's **Status** should now show as **Submitted** and the brand information can't be modified.

The brand review and approval process may take two business days. This timeline is for informational purposes only and might vary. If you submitted incorrect brand information, [contact Microsoft's Telephone Number Services - Service Desk](contact-tns-service-desk).

Important

If you designated your organization's legal form as *Publicly Traded Company*, you're required to complete a two-factor authentication (2FA) process as part of the verification process.

Once you submit your brand, the Business Contact Email will receive an email with a verification link and PIN from **noreply@auth.campaignregistry.com**. They should select the link, enter their first name, last name, job title, and the PIN, and complete the form to verify your brand. If the Business Contact doesn't receive the two-factor authentication (2FA) email, check your junk mail and your company's firewall rules. Alternatively, you can request Microsoft to resend the email.

#### Status updates

After we review your submission, the brand's **Status** updates to one of the following values:

- **Approved** - This status means your brand is approved. You can move on to [Step 2: Create a campaign](sms-setup-campaign).
- **Microsoft Support Engaged** - This status means your brand isn't approved. Our support team will contact the support representative of your brand for further assistance. Microsoft's Telephone Number Services - Service Desk team automatically opens a case on your behalf. You can view your case by navigating to the [Phone Number Service Center](https://pstnsd.powerappsportals.com), and selecting the tab for **My Company Cases**. Open the case, and you can interact with the Telephone Number Services (TNS) - Service Desk team about the details and status of your case.