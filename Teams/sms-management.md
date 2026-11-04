---
layout: Conceptual
title: Enable and manage SMS in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/sms-management
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
description: Enable and manage SMS in Microsoft Teams
locale: en-us
document_id: 7b8a6074-54d6-a284-89f6-870a842efb93
document_version_independent_id: 7b8a6074-54d6-a284-89f6-870a842efb93
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/sms-management.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sms-management
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/sms-management.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a93b1ff3-8d38-adab-b010-562271205df9
---

# Enable and manage SMS in Microsoft Teams - Microsoft Teams | Microsoft Learn

This article is for IT administrators and IT professionals who are administering the Short Message Service (SMS) usage in Microsoft Teams. You can manage SMS for Teams through the Teams admin center.

Note

SMS in Teams is only available on Calling Plan phone numbers in the United States (including Puerto Rico) and Canada.

## Prerequisites

### Brand and Campaign

To ensure successful enablement of SMS for a Teams Calling Plan phone number, confirm service enablement is configured, as described in the articles [Step 1: Create brand](sms-setup-brand) and [Step 2: Create campaign](sms-setup-campaign).

### Licensing

To enable Teams users with SMS capabilities, you must assign the following licenses to your users:

- Teams
- Teams Phone
- Microsoft Teams Calling Plan

For more information, see [SMS Licensing](sms-overview#licensing).

### Billing mechanism

A tenant **billing mechanism***should* be in place for SMS consumption overages and *must* be in place for Pay-as-you-go Calling Plans.

Funding for usage overages is supported either with prepaid Communication Credits using a Microsoft Online Subscription Agreement (MOSA) or with postpaid invoicing using a Microsoft Customer Agreement (MCA). For more information, see [SMS overview of usage and billing](sms-overview#usage-and-billing).

#### Permissions

As an administrator, you must be assigned one of the following Role-Based Access Control (RBAC) roles:

- Teams Administrator
- Teams Communications Administrator
- Teams Telephony Administrator

For more information about Teams administrator roles, see [Use Microsoft Teams administrator roles to manage Teams](using-admin-roles).

## Manage SMS in Teams for Users

### SMS status for phone numbers

Not all phone numbers support SMS in Teams. In the Teams admin center, under **Voice** &gt; **Phone numbers** &gt; **Numbers**, the **SMS status** shows whether a number can use SMS in Teams and displays the phone number's current SMS in Teams status. The following table lists the **SMS status** values and their descriptions.

| SMS status | Description |
| --- | --- |
| Not available | SMS in Teams isn't available on the phone number. SMS might not be available due to the current phone number's configuration—for example, the phone number is assigned to a Resource Account, or the phone number itself doesn't support SMS. |
| Not Activated | SMS in Teams is available on the phone number, but you haven't activated it yet. You can select **Enable SMS** to activate SMS in Teams for this phone number. |
| In Progress | SMS in Teams activation is in progress and might take up to two hours. |
| Activated | SMS in Teams is activated on the phone number. You can select **Disable SMS** to turn off SMS in Teams for this phone number. |

#### Turn on SMS for a user

To enable SMS in Teams for a user, you must turn on SMS for a user's phone number.

1. In Teams admin center, navigate to the left side rail, select **Voice** &gt; **Phone numbers** &gt; **Numbers**.
2. Find and select the number for the user.
3. In the contextual menu just above the list of phone numbers, select **Enable SMS**.

If the number isn't already assigned to a user, you can assign that number to a user. For more information on number management, see [Manage phone numbers for users](assign-change-or-remove-a-phone-number-for-a-user).

#### Turn off SMS for a user

To turn off SMS for a user, do the following steps:

1. In the Teams admin center, navigate to the left side rail, select **Voice** &gt; **Phone numbers** &gt; **Numbers**.
2. Find and select the number for the user.
3. In the contextual menu just above the list of phone numbers, select **Disable SMS**.

## SMS usage report

To view itemized SMS reporting, do the following steps:

1. In Teams admin center, navigate to the left side rail, select **Reports & analytics** &gt; **Usage reports** &gt; **PSTN and SMS Usage**.
2. Choose a date range.
3. Select **Run report**.

For more information, see [Microsoft Teams PSTN Usage report](teams-analytics-and-reports/pstn-usage-report).