---
layout: Conceptual
title: Manage phone numbers for Teams Phone Mobile - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/operator-connect-mobile-configure-numbers
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.date: 2024-07-08T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
ms.reviewer: odocspr
search.appverid: MET150
description: Learn how to manage phone numbers for Teams Phone Mobile.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
locale: en-us
document_id: e06d5fc6-5e8a-ce36-51f7-9e3e65bd8a3b
document_version_independent_id: e06d5fc6-5e8a-ce36-51f7-9e3e65bd8a3b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/operator-connect-mobile-configure-numbers.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: operator-connect-mobile-configure-numbers
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/operator-connect-mobile-configure-numbers.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 32a1b49f-f599-abd2-e57f-5f3a68cf50a8
---

# Manage phone numbers for Teams Phone Mobile - Microsoft Teams | Microsoft Learn

This is step 3 in how to configure Teams Phone Mobile. Before reading this article, be sure you've read [Configure Teams Phone Mobile](operator-connect-mobile-configure).

How you manage phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from Microsoft Calling Plans, Operator Connect, or Direct Routing. This article describes the following scenarios:

- Acquire numbers for new Teams users.
- Move numbers from Calling Plans to Teams Phone Mobile.
- Move numbers from Operator Connect to Teams Phone Mobile.
- Move numbers from Direct Routing to Teams Phone Mobile.

## Acquire numbers for new Teams users

To acquire numbers for new Teams users, follow these steps:

1. **Assign a Teams Phone license** to users by using the Microsoft 365 admin center or by using PowerShell. For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
2. **Ensure users who are assigned phone numbers acquired with Teams Phone Mobile are in TeamsOnly mode.** If your organization is in TeamsOnly mode, then all your users are in TeamsOnly mode.

    To check, in the Teams admin center, go to **Teams &gt; Teams upgrade settings**. If your organization is in Islands mode, check if specific users are in TeamsOnly mode. Go to **Users** and select a user account. In the **Account** tab, under **Teams upgrade,** the coexistence mode should be set to TeamsOnly.
3. **Acquire numbers.** Go to your operator's website or contact them to order and acquire mobile SIM-enabled phone numbers with the Teams Phone Mobile service enabled.

    After your operator completes the order, they'll upload SIM-enabled mobile numbers to your tenant. You can view the numbers and the provider in the Teams admin center by going to **Voice &gt; Phone numbers**.
4. **Assign numbers** to users by using the Teams admin center or by using PowerShell. For more information, see [Assign numbers](assign-change-or-remove-a-phone-number-for-a-user).

## Move numbers from Calling Plans to Teams Phone Mobile

1. Ensure you have eligible Microsoft 365 subscriptions for Teams Phone Mobile.
2. [Remove the phone number to be moved for respective users](assign-change-or-remove-a-phone-number-for-a-user#use-teams-admin-center-to-remove-a-phone-number-from-a-user).
3. Contact your operator to port your numbers to Teams Phone Mobile on an eligible wireless voice plan which is SIM-enabled.
4. After your operator completes the porting order, your operator will upload the numbers to your tenant. You can view the numbers and the operator in the Teams admin center by going to **Voice &gt; Phone numbers**.
5. **Assign numbers** to users by using the Teams admin center or by using PowerShell. For more information, see [Assign numbers](assign-change-or-remove-a-phone-number-for-a-user).

## Move numbers from Operator Connect to Teams Phone Mobile

1. Ensure you have eligible Microsoft 365 subscriptions for Teams Phone Mobile.
2. [Remove the phone number to be moved for respective users](assign-change-or-remove-a-phone-number-for-a-user#use-teams-admin-center-to-remove-a-phone-number-from-a-user).
3. Contact your existing Operator Connect provider to remove the phone numbers from your tenant.
4. Contact your operator to port your numbers to Teams Phone Mobile on an eligible wireless voice plan which is SIM-enabled.
5. After your operator completes the porting order, your operator will upload the numbers to your tenant. You can view the numbers and the provider in the Teams admin center by going to **Voice &gt; Phone numbers**.
6. You can assign numbers to users by using the Teams admin center or by using PowerShell. For more information, see [Assign numbers](assign-change-or-remove-a-phone-number-for-a-user).

## Move numbers from Direct Routing to Teams Phone Mobile

To move numbers from Direct Routing to Teams Phone Mobile, you'll need to complete the following steps:

1. Determine if the existing Direct Routing numbers are assigned online or on-premises.
2. Migrate the numbers from Direct Routing to Teams Phone Mobile.
3. Remove the Direct Routing online voice routing policy associated with your user.
4. Acquire phone numbers.
5. Assign phone numbers.

These steps are described in greater detail in the following sections.

### Determine if the existing Direct Routing numbers are assigned online or on-premises.

How you remove your existing Direct Routing numbers depends on whether the number is assigned on-premises or online.

1. First, check that the user is assigned a Direct Routing number by running the following Teams PowerShell command. NumberType should be DirectRouting:

    ```PowerShell
    Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
    ```
2. Determine if the number is assigned online or on-premises by running the following Teams PowerShell command:

    ```PowerShell
    Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
    ```

    If OnPremLineUri is populated with an E.164 phone number, the phone number was assigned on-premises and synchronized to Microsoft 365.

### Migrate the numbers from Direct Routing to Teams Phone Mobile

To migrate numbers, follow the steps below.

Important

During migration, the phone number will be out of service. Coordinate with your Teams Phone Mobile operator before you begin the migration.

- **To migrate existing Direct Routing numbers assigned online to Teams Phone Mobile**, contact your operator. To find your operator's website, see [Microsoft 365 Teams Phone Mobile directory](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). On the agreed date and time, your operator will migrate your numbers from Direct Routing to Teams Phone Mobile. This may involve removing the phone number being migrated from your tenant and add it again as a new phone number associated with Teams Phone Mobile.
- **To migrate Direct Routing numbers assigned on-premises to Teams Phone Mobile**, run the following Skype for Business Server PowerShell command:

    ```PowerShell
    Set-CsUser -Identity <user> -LineURI $null 
    ```

    To check if the on-premises number was removed and the changes have been synced from on-premises to Microsoft 365, run the following Teams PowerShell command:

    ```PowerShell
    Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
    ```

After the changes have synced to Microsoft 365 online directory, the expected output is:

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

To check if the phone number was removed, run the following Teams PowerShell command:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

Note

The amount of time it takes for the removal to take effect depends on your configuration. Removing the phone number may take up to 10 minutes, in rare cases, it can take up to 24 hours.

### Remove the Direct Routing online voice routing policy associated with your user

After the number is unassigned, remove the online voice routing policy associated with your user by running the following Teams PowerShell command:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

### Assign Teams Phone Mobile licenses to your users

For more information, see [Assign Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses).

### Acquire phone numbers

Contact your operator to port your numbers to Teams Phone Mobile on an eligible wireless voice plan which is SIM-enabled.

After your operator completes the order, they'll upload numbers to your tenant. You can view the numbers and the provider in the Teams admin center by going to **Voice &gt; Phone numbers**.

### Assign phone numbers

You can assign Teams Phone Mobile numbers to users by using the Teams admin center or by using PowerShell. For more information, see [Assign numbers](assign-change-or-remove-a-phone-number-for-a-user).