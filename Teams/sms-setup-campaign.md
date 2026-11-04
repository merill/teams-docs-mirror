---
layout: Conceptual
title: Set up a Campaign for SMS in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/sms-setup-campaign
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
description: Learn how to set up a Campaign to enable SMS in Microsoft Teams.
locale: en-us
document_id: a6ef3a08-0692-27ee-569b-5e5287362d71
document_version_independent_id: a6ef3a08-0692-27ee-569b-5e5287362d71
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/sms-setup-campaign.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sms-setup-campaign
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/sms-setup-campaign.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7e2de2eb-59af-e5a9-189a-79c6c3e21636
---

# Set up a Campaign for SMS in Microsoft Teams - Microsoft Teams | Microsoft Learn

Note

Service update: If you receive a Brand or Campaign rejection, our Telephone Number Services team is aware and managing a case with you through the [Phone Number Service Center](https://pstnsd.powerappsportals.com) portal. Due to a high volume of requests for SMS in Teams, processing times to facilitate approvals of rejected Brand and Campaign applications for SMS in Teams may take 4 to 6 weeks. We appreciate your patience as we work diligently to address all requests.

This article is for IT administrators and IT professionals who are enabling Short Message Service (SMS) in Teams and need to register their company's campaign.

Before reading this article, make sure you've read [Plan for SMS in Teams](sms-overview) and [Step 1: Create a brand](sms-setup-brand).

Note

SMS in Teams is only available on Calling Plan phone numbers in the United States (including Puerto Rico) and Canada. Customers must have an approved Brand and Campaign before enabling SMS on Teams Calling Plan numbers.

## Prerequisites

Ensure fundamental understanding of the *purpose* for a Campaign, as described in [Learn about SMS Texting in Teams](sms-overview).

Administrators must have one of the following role-based access control (RBAC) roles assigned:

- Teams Administrator
- Teams Communications Administrator
- Teams Telephony Administrator

## Campaign registration details for SMS in Teams

Once your Brand is verified and its status shows as **Approved** in the Teams admin center, you can begin the **campaign** registration process.

This process includes a detailed description of the SMS services you provide, including:

- The purpose of your SMS service
- Your target audience
- How users opt in and opt out
- Sample messages and compliance details

Important

Your application will be reviewed by **10DLC operators**, who are the **final approvers** of your campaign. They evaluate the nature of your messaging and ensure it complies with industry regulations. The accuracy and completeness of your submission may affect both the **review timeline** and the **approval outcome**.

To register your campaign, you must submit the required information through the **Teams admin center**. The following sections outline details required to register your campaign.

### Campaign Use Case

The use case specifies how the SMS service is used for the given campaign. For SMS in Teams, the use case is Unified Communications as a Service (UCaaS), Low Volume. Microsoft defines the use case and you can't change the use case.

Important

This registration is solely for **SMS-enabled phone numbers assigned to individual employees (users) for 1-to-1 conversations**. It does **not support** marketing, bulk messaging, automated alerts, or API-driven interactions.

### Campaign Description

The description provides a comprehensive explanation of the SMS service utilization, type of messages sent, and your target audience. 

### SMS Privacy Policy

When you register a campaign, you must provide a link to your brand's Privacy Policy related to SMS messaging. It can be a webpage or an online file that's publicly accessible and must clearly describe the following information:

- How consumer data is used and shared (if applicable)
- How consumers can contact the message sender
- A statement that says "mobile opt-in information won't be shared with third parties for marketing purposes"

Note

If your company doesn't have a privacy statement related to SMS, you may use the [SMS privacy statement and terms and conditions template](/en-us/microsoftteams/sms-privacy-terms-template).

### SMS Terms and Conditions

When registering a campaign, you must provide a link to your brand's Terms & Conditions related to SMS. It can be a webpage or an online file that is publicly accessible and must have an SMS disclosure that includes:

- Brand name
- Types of messages the consumer can expect to receive
- Message frequency disclosure (for example, "Msg frequency varies")
- Message and data rates disclosure (for example, "Msg & data rates may apply")
- Support contact information (for example, "send HELP for support," "contact help@contoso.com for support")
- Opt-out information (for example, "Send STOP to unsubscribe")

Note

If your company doesn't have terms and conditions related to SMS, you may use the [SMS privacy statement and terms and conditions template](/en-us/microsoftteams/sms-privacy-terms-template).

### Call to Action

The Call to Action clearly and transparently describes how a recipient opts-in to receive messages from you. It must be **explicit, verifiable, and specific to SMS**. It must not be bundled with other services and must include the following information:

- Brand name
- Types of messages the consumer can expect to receive
- Message frequency disclosure (for example, "Msg frequency varies")
- Message and data rates disclosure (for example, "Msg & data rates may apply")
- Opt-in information (see the following table for examples)
- Help information (for example, "send HELP for help")
- Opt-out information (for example, "send STOP to unsubscribe")
- Privacy Policy link
- Terms and Conditions link

The table below shows examples of how users might opt in:

| Method | Description | Requirement | Examples |
| --- | --- | --- | --- |
| Web Sign-Up | Users enter their phone number on a website and check a box agreeing to receive messages. | Provide a direct link to the submission form or the webpage. | "By submitting this form [**add link to the form here**], user consent to receive [type of text messages] from [Brand Name] at the number provided. Msg & data rates may apply. Msg frequency varies. Unsubscribe by replying STOP or clicking the unsubscribe link. Reply HELP for help. Phone numbers aren't shared with third parties. Privacy Policy [link] & Terms [link]." |
| Text Message Keyword | Users opt-in by texting a keyword (for example, "START") to a specific number. | Explain how users learn about the keyword, such as via a webpage link or screenshot. | "[**Explain how users learn about the keyword / phone number**]. By texting START to [phone number], user consent to receive text messages from [Brand Name]. Msg & data rates may apply. Msg frequency varies. Unsubscribe by replying STOP. Reply HELP for help. Phone numbers won't be shared with third parties. Privacy Policy [link] & Terms [link]." |
| Verbally | Users opt-in verbally at a physical location or over the phone. | Provide a copy of the script used to inform users about the opt-in. | "[Brand name] collects opt-in verbally at their locations or over the phone. [**Add the script here**]. Customers provide their number and are informed that 'Message and data rates may apply', 'Message frequency varies', and they can 'text HELP for support or STOP to unsubscribe.' Phone numbers won't be shared with third parties. Privacy Policy [link] & Terms [link]." |

Note

The provided examples are for illustration purpose only and don't guarantee the approval of your campaign. It's important to be as detailed and accurate as possible in your Call to Action.

### Sample Messages

These sample messages are examples of messages that you send. They must align with the campaign use case and must include the following information:

- Brand name
- Opt-out language in at least one sample message
- An embedded link in at least one sample message if "Yes" is selected for **Embedded Link** under Content Attributes

### Required Automated Messages

#### Opt-In Message

When a Teams user sends the first message in an SMS conversation or when recipient replies START, the **Opt-In Message** is automatically sent to the recipient. The Opt-In Message must include the following information:

- Brand name
- Message frequency disclosure (for example, "Msg frequency varies")
- Message and data rates disclosure (for example, "Msg & data rates may apply")
- Help information (for example, "send HELP for help")
- Opt-out information (for example, "send STOP to unsubscribe")

An example might look like this:

> 
> Thank you for opting in to receive [type of messages] from [Brand Name]. Msg frequency varies. Msg & data rates may apply. Reply HELP for help. Reply STOP to opt out from receiving messages from this number.\*" automated message is sent to the recipient send START to resume a conversation.

##### Opt-Out Message

When recipient replies STOP, the Opt-Out Message is automatically sent to the recipient.

The Opt-Out Message must include the following information:

- Brand name
- Confirmation that the recipient will receive no further messages.

An example might look like this:

> 
> You have successfully opted out of messages from this [Brand Name] number. You'll receive no further messages. Reply START to resume. Msg & data rates may apply.

##### Help Message

When recipient replies HELP, the Help Message is automatically sent to the recipient.

The Help Message must include the following information:

- Brand name
- Support contact information (for example, an email address, phone number, or website)

 An example might look like this:

> 
> Thank you for contacting [Brand Name] support. Please email us at [email address] for support. Reply STOP to opt-out from receiving messages from this number. Msg & data rates may apply.

Important

Only START, HELP, and STOP, QUIT, END, REVOKE, OPT OUT, CANCEL, UNSUBSCRIBE keywords are monitored and enforced for SMS in Teams.

### Content Attributes

The following table provides a detailed description of the content attributes of a campaign:

| Content | Description |
| --- | --- |
| **Direct Lending or Loan Arrangement** | Indicates if the brand engages in lending, even if the campaign isn't related to lending or loan arrangement. |
| **Embedded Link** | Indicates if embedded links are sent in messages. Public URL shorteners (bitly, tinyurl) aren't accepted. If selected, at least one sample message must include an embedded link. |
| **Embedded Phone Number** | Indicates if embedded phone numbers are sent in messages, excluding HELP contact. If selected, at least one sample message must include an embedded phone number. |
| **Age-Gated Content** | Indicates if the content includes age-gated materials. |

## Create or Update an SMS in Teams Campaign in Teams admin center

1. Go to **Teams Admin Center** &gt; **Voice** &gt; **Service Configuration** &gt; **SMS** &gt; **Step 2: Create Campaign**
2. Select **Create / Update / View Campaign**
3. Fill in:
    - Campaign Description
    - Call to Action
    - Sample Messages
    - Privacy Policy & Terms links
    - Opt-In, Opt-Out, Help Messages
    - Content Attributes
4. Accept Microsoft’s terms and conditions.
5. Submit your campaign.

After submission, the Campaign status shows as **Submitted** and the campaign information can't be modified.

If your campaign is approved, your campaign status updates to **Approved** and you can move on to [Step 3: Enable SMS](sms-management).

If your campaign isn't approved and needs updates from you, the status will change to **Pending Customer Update**. You will be able to review the rejection reasons, make the necessary updates, and resubmit your campaign. For details on rejections and recommended actions, visit [Resolve 10DLC campaign rejection errors](/en-us/troubleshoot/microsoftteams/phone-system/sms-calling-errors).

If your campaign isn't approved and requires support intervention, the status will update to **Microsoft Support Engaged**. In this case, our support team may reach out to your brand's support representative for further assistance.

## Submission and Review Process

The following diagram illustrates the campaign submission and review process:

![teams-sms-campaign-submission-review-process](media/sms-setup-campaign/10dlc.jpg)

**Campaign Status Descriptions**

| Status | Description | Owner |
| --- | --- | --- |
| **Draft** | Your campaign isn't submitted yet. You can continue to update and prepare it before submission. | Customer |
| **Submitted** | Your campaign has been submitted for verification. No further actions are allowed. | SMS Partner |
| **Approved** | Your campaign has been approved. You can now activate SMS on your phone numbers. | Customer |
| **Microsoft Support Engaged** | Your campaign is under review by support team. They may contact the support the brand contact. | Microsoft |
| **Pending Customer Update** | Your campaign requires updates from you. Log in to Teams Admin Center, review the reasons, and resubmit. | Customer |
| **Denied** | Your Campaign has been rejected. This may be due to reaching the maximum number of attempts or a final rejection. No further action allowed. | N/A |
| **Cancelled** | Your campaign has been canceled, either at your request or due to inactivity. No further action allowed. | N/A |

Note

You can make updates and submit your campaign while its status is either **Draft** or **Pending Customer Update**, with a maximum of four submissions. After the fourth attempt, the campaign will be permanently denied. Once a campaign is **approved**, you can't make changes to the campaign content or configuration. If your campaign status is **Microsoft Support Engaged**, a support case is automatically opened on your behalf with Microsoft's Telephone Number Services (TNS) - Service Desk. You can view your case by navigating to the [Phone Number Service Center](https://pstnsd.powerappsportals.com), and then selecting the tab for My Company Cases. Open the case, and you can interact with the Telephone Number Services - Service Desk team about the details and status of the case.

## Considerations

### Campaigns with More Than 49 SMS-Enabled Numbers

If your organization requires more than 49 SMS-enabled phone numbers for a campaign, you must request a **number pool**.

You can request a number pool via **Teams admin center** only while the campaign is in **Draft** or **Pending Customer Update**. When requesting a number pool, you must provide:

- The **target number of SMS-enabled phone numbers**
- The **estimated number of SMS messages sent per day**

The number pool request is **only processed after the campaign is approved** and triggers an **additional verification** by 10DLC operators. This process may take up to 20 business days. These timelines are for informational purposes only and may vary.

Important

If your campaign is already **Approved**, you **cannot** request a number pool via the Teams Admin Center. You must contact Microsoft support. Currently, **non-profit brands are not eligible** for number pool expansion due to technical limitations.

### Campaign approval process timeline

Your application will be reviewed by 10DLC operators, who are the final approvers of your campaign. They assess the nature of your business's messaging and ensure compliance with industry regulations. The application content may affect both the lead time and the validation outcome. This process may take up to 20 business days. These timelines are for informational purposes only and may vary.