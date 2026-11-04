---
layout: Conceptual
title: Setup - Authorized Users - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-authorized-users
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
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.date: 2026-08-31T00:00:00.0000000Z
ms.collection:
- M365-voice
- m365initiative-voice
- tier1
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.voiceapplications.overview
ms.localizationpriority: medium
search.appverid: MET150
customer-intent: As a Teams Administrator, I want to setup authorized users so I can allow users to make changes to teams phone agent, auto attendant, or call queue configurations without having access to Teams Admin Center.
description: Setup - Authorized Users
locale: en-us
document_id: bdc17ac9-a82b-8705-fc77-5d0ecdcb2b56
document_version_independent_id: bdc17ac9-a82b-8705-fc77-5d0ecdcb2b56
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-authorized-users.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-authorized-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-authorized-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d910b3a9-867d-960f-0df4-e608ef17cd84
---

# Setup - Authorized Users - Microsoft Teams | Microsoft Learn

Caution

**Daylight Savings Time changes – Manual changes to auto attendant time zones required by some customers.**

On November 1, 2026, Daylight Savings Time will end in North America.

In Canada, the provinces of Alberta, British Columbia, and Manitoba will remain on Daylight Savings Time and will not move the clocks back one hour.

Customers with auto attendants serving these provinces that have time zone configurations that reference **(UTC-7:00) Mountain Time (US & Canada)**, **(UTC-8:00) Pacific Time (US & Canada)**, or **(UTC-05:00) Eastern Time (US & Canada)** must be updated as follows:

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

Customers with auto attendants serving these areas that have time zone configurations that reference **(UTC-05:00) Eastern Time (US & Canada)** should change the time zone selection to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

This article is for IT Pros and administrators who want to delegate Teams Phone Agent, Auto attendant, and Call queue change capabilities to users in their organization. This article describes the necessary steps to create an Authorized user.

Before you read this article, read [Plan for authorized users](aa-cq-plan-authorized-users) to understand the licensing and prerequisites for Auto Attendant and Call Queue authorized users.

An **authorized user** is a Teams user that a Teams admin center administrator authorizes to make configuration changes to Teams Phone Agents, auto attendants, and call queues. The user doesn't need to have access to the Teams admin center portal nor be assigned any administrative roles.

With the Queues App in Teams, you can give authorized users more control. They can set call routing for business hours, after hours, and holidays, and view real-time and historical metrics. For more information, see Set up Queues app for authorized users.

The authorized user can access these change configuration items through their Teams desktop client or Queues. For end user documentation, see [Manage your Call queue and Auto attendant greetings in Microsoft Teams](https://support.microsoft.com/office/52c741c6-8577-4faf-aa5a-c7853e0ab8f8).

For information on creating a Call queue or Auto attendant, see [Create a Call queue in Microsoft Teams](aa-cq-setup-call-queue) and [Set up a Microsoft Teams Auto attendant](aa-cq-setup-auto-attendant).

## Steps for setting up authorized users

To create an authorized user, you must complete the following steps:

- Step 1 - Assign licenses and enable users for voice
- Step 2 - Assign phone numbers to your users
- Step 3 - Create a Teams voice applications policy
- Step 4 - Assign the voice applications policy to the user
- Step 5 - Create an Auto attendant or Call queue and assign licensed resource accounts
- Step 6 - Assign authorized users to the relevant Auto attendant or Call queue
- Step 7 – Set up Queues app for authorized users (optional)

## Step 1: Assign licenses and enable users for voice

Note

In order for your users to use the Microsoft Teams Queues app, they need to have a Teams Phone and Teams Premium license assigned to them. For a complete list of authorized user settings that require a Teams Premium license, see [Manage Teams voice applications policies](aa-cq-manage-voice-applications-policies).

To assign a Teams Phone and Teams Premium license, do the following steps:

1. Use the Microsoft 365 admin center and go to **Billing** &gt; **Licenses**.
2. Select your Teams Phone license. On the product details page, select **Assign licenses** and assign the license to your users.
3. Select **Assign** once you're finished.
4. Repeat Steps 2 and 3 for a Teams Premium license.

Before you can enable voice for your users, you must assign a license to them first. To enable voice for your users, you can use the Teams admin center or PowerShell.

- In the Teams admin center, go to a **Users** &gt; **Manage users** and select the user you want to edit. Under the **Account** tab &gt; **Assigned phone number**, turn **Enterprise Voice** to **On** and select **Save**.
- For PowerShell, use the [Set-CsPhoneNumberAssignment](/en-us/powershell/module/teams/set-csphonenumberassignment) cmdlet and set the `-EnterpriseVoiceEnabled` parameter to `$true`.

## Step 2: Assign phone numbers to your users

If you haven't already done so, assign user phone numbers to your users. For more information, see [Manage phone numbers for users](assign-change-or-remove-a-phone-number-for-a-user).

## Step 3: Create a Teams voice applications policy

After assigning phone numbers to your users, you need to create a [Teams voice applications policy](aa-cq-manage-voice-applications-policies) that turns on the change functionality that the user needs and to assign that policy to the user.

## Step 4: Assign the voice applications policy to the user

Once you create your Teams voice applications policy, you need to individually assign it to users. To do this, you can use the Teams admin center or [Grant-CsTeamsVoiceApplicationsPolicy](/en-us/powershell/module/teams/grant-csteamsvoiceapplicationspolicy) cmdlet.

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

## Step 5: Create an Auto attendant or Call queue and assign licensed resource accounts

After assigning the voice applications policy to your users, if you haven't already done so, you need to create Auto attendants or Call queues that the user will be authorized to manage.

For more information, see [Set up Auto attendants](aa-cq-setup-auto-attendant) and [Set up Call queues](aa-cq-setup-call-queue).

## Step 6: Assign authorized users to the relevant Auto attendant or Call queue

The next step is assigning the user as an Authorized user to at least one Auto attendant or Call queue. There's a maximum of 15 authorized users per each Auto attendant or Call queue.

## Step 7: Set up Queues app for Authorized users (optional)

With Queues app, authorized users can access more configuration features and reports for Auto attendants and Call queues, such as call flow configuration for business hours, after hours, holidays, and real-time call queue and agent metrics. Queues app is available to authorized users with a Teams Premium and Teams Phone license.

For a complete list of features and licensing required for each, see [Manage voice applications policies](aa-cq-manage-voice-applications-policies).

For information on how to manage the Queues app, see [Manage the Queues app in Microsoft Teams](manage-queues-app).

## Authorized user examples

User 1 needs to be able to change Auto attendant business hours greetings and Call queue timeout shared voicemail greetings for *Auto attendant 1* and *Call queue 1*.

User 2 needs to be able to change Auto attendant after hours greetings for *Auto attendant 1*.

1. Create a *Teams voice applications policy* that enables the Auto attendant **Business Hours Greeting** and the Call queue **Timeout shared voicemail greeting**.
2. Assign this policy to User 1.
3. Create another *Teams voice applications policy* that enables the Auto attendant **After Hours Greeting**.
4. Assign this policy to User 2.
5. Assign both User 1 and User 2 as *Authorized users* for *Auto attendant 1*.
6. Assign User 1 as an *Authorized User* for *Call queue 1*.

Both User 1 and User 2 are now fully authorized users and have new configuration options available to them in their Teams desktop client once they sign out and sign back in.