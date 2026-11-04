---
layout: Conceptual
title: Set up an Android mobile phone as a common area phone - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/common-area-mobile-phones
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: prashibadkur
ms.date: 2024-10-21T00:00:00.0000000Z
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- M365-collaboration
- Teams_ITAdmin_Devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
- System.Collections.Generic.Dictionary`2[System.String,System.Object]
description: Learn how to set up common area Android phones
locale: en-us
document_id: 5d8f10c0-f11b-d91f-79c9-a04decfe9b33
document_version_independent_id: 5d8f10c0-f11b-d91f-79c9-a04decfe9b33
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/common-area-mobile-phones.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/common-area-mobile-phones
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/common-area-mobile-phones.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 6b14ac96-7491-c9c4-6f25-24fe489a4f6f
---

# Set up an Android mobile phone as a common area phone - Microsoft Teams | Microsoft Learn

A Teams Android mobile app signed in with an account tied to **Microsoft Teams Shared Device** license is used as a shared device by frontline workers to make and receive calls as part of their daily work using Teams.

Important

To use this feature you must have version 1.0.0.2023143401 (2023143401) or later installed on the Android mobile phone.

## Step 1 - Buy the licenses

First, you need to purchase a **Teams Shared Devices** license.

Note

Chat is not supported with a **Teams Shared Devices** license.

To purchase the license:

1. Sign in to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), and select **Billing &gt; Purchase services**.
2. If the **View by category** section isn't already displayed, go to **Purchase from Microsoft** and select **View products**, and then select **Collaboration and communication**.
3. In the product list, find **Microsoft Teams Shared Devices**, and select **Details**.
4. Enter the number of licenses you need, and select **Buy**.

    Note

    Teams-shared devices can be impacted by conditional access rules and other identity configurations, such as Multi-Factor Authentication. For more information, see [Authentication best practices for Teams phones](authentication-best-practices-phones).

## Step 2 - Create a new user account and assign licenses

### Using the Microsoft 365 admin center

Note

If you're deploying more than one phone at a time, you can use only [PowerShell](../set-up-common-area-phones) to create accounts and assign licenses. You can use Microsoft 365 admin center to create accounts and assign licenses only if you're deploying one device at a time.

1. Sign in to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), and select **Users &gt; Active Users &gt; Add a user**.
2. Enter a username like **Main** for the first name and **Reception** for the second name.
3. Enter a display name if it doesn't autogenerate one, for example, **Main Reception**.
4. Enter a username like **BakeryPhone** or **DutyManager**.
5. Manually set the password for your common area phone. To set the password, clear the **Automatically create a password and require this user to change their password when they first sign in** checkbox.

    Important

    Manually setting a password for common area phones is recommended to prevent sign-in issues for your end users.
6. Select the usage location of the device and assign the **Teams Shared Devices** license to the account. If any other licenses are needed, such as **Callings Plans**, assign those licenses too to the account.

    Note

    When you assign a **Teams Shared Device** license to a device, you don't need to assign an additional Phone System license to get other features. To get inbound and outbound calling minutes with Microsoft Phone System you must add a Calling Plan and set up billing. However, if you are using Operator Connect or Direct Routing, you don't need a Calling Plan. For more information on licenses, see [Microsoft Teams add-on licensing](../teams-add-on-licensing/microsoft-teams-add-on-licensing).

### Using PowerShell

Use PowerShell when you want to create and assign licenses for more than one user account at a time. For more information, see [Create Microsoft 365 user accounts with PowerShell](/en-us/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell) and [Assign Microsoft 365 licenses to user accounts with PowerShell](/en-us/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell).

## Step 3 - Set policies

To set up different policies as required, see:

1. [Calling policies in Teams](../teams-calling-policy)
2. [Configure Call park and retrieve](../call-park-and-retrieve)

## Step 4 - Acquire and assign phone numbers

To acquire and assign phone numbers based on your PSTN connectivity option, see [Manage telephone numbers for your organization](../manage-phone-numbers-landing-page).

## Step 5 - Sign in

Once you create and configure the account, you can sign in to the Teams app on the Android mobile phone using the account tied to **Teams Shared Device** license.

[![Screenshot showing the Teams app on an Android mobile device.](../media/teamsshareddevicelicenseonandroidmobile.png)](../media/teamsshareddevicelicenseonandroidmobile.png#lightbox)