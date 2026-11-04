---
layout: Conceptual
title: Configure Operator Connect - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/operator-connect-configure
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.date: 2026-04-23T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
ms.reviewer: hranapour
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Learn more about how to configure Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
locale: en-us
document_id: 709c5bb1-843a-c243-16b6-86bd9f114d37
document_version_independent_id: e5e9415f-bd40-4084-e280-59be5cc186a6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/operator-connect-configure.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: operator-connect-configure
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/operator-connect-configure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: babf22c6-138c-ac18-5dde-570d4fc1db1d
---

# Configure Operator Connect - Microsoft Teams | Microsoft Learn

This article describes how to configure Operator Connect. Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan) for information about prerequisites and licensing. For a list of operators participating in the Microsoft Operator Connect Program and the countries or regions where their service is available, see the [Microsoft 365 Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/).

## Enable an operator

You can enable, edit, and remove operators in the Teams admin center. In the left navigation pane, go to **Voice &gt; Operator Connect**.

To enable an operator:

1. **Choose an operator.** In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs. Then select the operator you want to enable.
2. **Select countries.** Under **Operator settings**, select the countries/regions you want to enable with your selected operator.
3. **Provide contact information.** Your contact information, including your full name and email address, will be shared automatically with your operator. You can change this information later. Additionally, you'll need to provide company size, and you'll have the option to provide your phone number. Operators will use this information to contact you with more details about Operator Connect.
4. Accept the data transfer notice.
5. **Add your operator.** Select **Add as my operator** to save.

## Set up phone numbers

How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.

- If you need to acquire phone numbers for new users, see Acquire numbers for new Teams users.
- If you want to move existing numbers from Calling Plans to Operator Connect, see Move numbers from Calling Plans to Operator Connect.
- If you want to move existing numbers from Direct Routing to Operator Connect, see Move numbers from Direct Routing to Operator Connect.

### Assign numbers to emergency addresses

The emergency address is a static location associated with a number. Once you create emergency addresses in the Teams admin center, how you assign the addresses, or change them later, will depend on your operator.

To assign numbers to emergency addresses, your operator will implement one of three scenarios:

- The operator assigns emergency addresses to the phone numbers and allows you to change them later in the Teams admin center.
- The operator doesn't assign addresses and allows you to assign emergency addresses to the phone numbers in the Teams admin center.
- The operator assigns emergency addresses to the phone numbers, and doesn't allow you to change them. In this scenario, you'll need to contact your operator to make changes to phone numbers and their assigned emergency address.

For more information on emergency calling, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling).

### Acquire numbers for new Teams users

To acquire numbers for new Teams users, follow these steps:

1. **Assign a Phone System license.** You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell. For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
2. Users that will be assigned phone numbers acquired with Operator Connect need to be in TeamsOnly mode. If your organization is in TeamsOnly mode, then all your users are in TeamsOnly mode. To check this, in the Teams admin center, go to **Teams &gt; Teams upgrade settings**. If your organization is in Islands mode, check if specific users are in TeamsOnly mode. Go to **Users** and select a user account. In the **Account** tab, under **Teams upgrade settings,** the coexistence mode should be set to 'TeamsOnly.'
3. **Acquire numbers.** Go to your operator's website to order and acquire phone numbers. For a list of operators participating in the Microsoft Operator Connect Program and the countries or regions where their service is available, see the [Microsoft 365 Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/). You'll need to provide your tenant ID. If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/en-us/onedrive/find-your-office-365-tenant-id) for more information.
4. **Assign numbers.** Once your operator completes the order, they'll upload numbers to your tenant. You can view the numbers and the provider in the Teams admin center by going to **Voice &gt; Phone numbers**. Assign numbers to users from the Teams admin center or by using PowerShell. For more information, see Assign numbers.

Note

In addition to getting phone numbers for your users, you can get toll or toll-free phone numbers for services such as Audio Conferencing (for conference bridges), Auto Attendants, and Call Queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously. To get service numbers, contact your operator.

### Move numbers from Calling Plans to Operator Connect

1. Contact your operator to port your numbers to Operator Connect. See [Microsoft 365 Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/) to find your operator's website.
2. After your operator completes the porting order, your operator will upload the numbers to your tenant.
3. Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell. For more information, see Assign numbers.

### Move numbers from Direct Routing to Operator Connect

To move from Direct Routing to Operator Connect with on-premises or online phone numbers, follow the steps below:

#### Step 1 - Identify if the existing Direct Routing numbers are assigned online or on-premises and remove/unassign the phone number from a user.

Check that the user is assigned a Direct Routing number by running the Teams PowerShell Module command:

```PowerShell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
```

Check that `NumberType` is DirectRouting.

How you remove your existing Direct Routing numbers depends whether the number is assigned on-premises or online. To check, run the following Teams PowerShell Module command:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

If `OnPremLineUri` is populated with an E.164 phone number, the phone number was assigned on-premises and synchronized to Microsoft 365.

**To migrate existing Direct Routing numbers assigned online to Operator Connect**, contact your operator. To find your operator's website, see [Microsoft 365 Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/). On the agreed date and time, your operator will migrate your numbers from Direct Routing to Operator Connect.

**To migrate Direct Routing numbers assigned on-premises to Operator Connect**, run the following Skype for Business Server PowerShell command:

Important

The phone number will be out of service during the migration, so coordinate with your Operator Connect operator before you begin.

```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

The amount of time it takes for the removal to take effect depends on your configuration. To check if the on-premises number was removed and the changes have been synced from on-premises to Microsoft 365, run the following Teams PowerShell Module command:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

After the changes have synced to Microsoft 365 online directory, the expected output is:

```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 			
```

Once you have verified that the changes have been synced to Microsoft 365 online directory, you can remove/unassign the phone number from the user. To do this, run the following Teams PowerShell Module command:

```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

Removing the phone number may take up to 10 minutes. In rare cases, it can take up to 24 hours. To check if the phone number was removed, run the following Teams PowerShell Module command:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### Step 2 - Remove the online voice routing policy associated with your user

Once the number is unassigned, remove the online voice routing policy associated with your user by running the following Teams PowerShell Module command:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### Step 3 - Acquire phone numbers

Go to your operator's website to order and acquire phone numbers. To find your operators website, see the [Microsoft 365 Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/). You'll need to provide your tenant ID. If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/en-us/onedrive/find-your-office-365-tenant-id) for more information.

#### Step 4 - Assign phone numbers

Once your operator completes the order, they'll upload numbers to your tenant. You can view the numbers and the provider in the Teams admin center by going to **Voice &gt; Phone numbers**. Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell. For more information, see Assign numbers.

### Assign numbers

For information on how to assign phone numbers to your users, see [Manage phone numbers for users](assign-change-or-remove-a-phone-number-for-a-user).

## Manage your operators

If you shared your contact information with an operator through the Teams admin center, from the **My operators** tab, you can view your operators and their status and make the following changes to your selections:

- Manage operator services by country/region
- Suspend an operator
- Remove an operator

Note

Before removing an operator from your organization or from a country/region, you must remove all phone numbers assigned to users in the organization or country/region and contact the operator to release the numbers.

## Release numbers

To release phone numbers from the Teams admin center, go to the **Phone numbers** page and select a number.

- If the phone number isn't assigned to a user, select **Release**.
- If the phone number is assigned to a user, you'll need to unassign the number. Select **Edit**, then **Remove the user to whom the number is assigned** and **click Apply** and confirm **unassigning** the number to save your changes\*\*.\*\* After your changes are saved, select the number again from the phone numbers page and select **Release**.