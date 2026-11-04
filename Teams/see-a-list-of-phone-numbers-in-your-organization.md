---
layout: Conceptual
title: See a list of telephone numbers in your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/see-a-list-of-phone-numbers-in-your-organization
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
ms.reviewer: davlick, roykuntz, jastark, pavellatif
ms.date: 2026-05-28T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- M365-collaboration
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Learn how to see a list of all telephone numbers in your organization and all numbers that are assigned to users or unassigned.
locale: en-us
document_id: 224b0537-e144-f5ed-6974-6e34733bceb2
document_version_independent_id: 4f1875c6-77ef-f636-669e-5f3af9691f7d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/see-a-list-of-phone-numbers-in-your-organization.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: see-a-list-of-phone-numbers-in-your-organization
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/see-a-list-of-phone-numbers-in-your-organization.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 841ab87c-1bbf-3108-3fb9-0ff89c187f98
---

# See a list of telephone numbers in your organization - Microsoft Teams | Microsoft Learn

This article is for Teams admins who are managing telephone numbers for their organization's tenant.

In Teams, the numbers that you associate with your tenant are stored in Microsoft's telephone number management inventory, reserved only for your tenant's use. You can see these numbers at any time.

You can see telephone numbers acquired through any of the Public Switched Telephone Network [(PSTN) connectivity options](pstn-connectivity) that connected to your tenant. The numbers you can see include numbers assigned to users and unassigned numbers that are reserved for use in your tenant.

To have your unassigned Direct Routing telephone numbers included in this view, you must upload them to Microsoft's telephone number management inventory. For more information, see [Upload Direct Routing numbers to your tenant](direct-routing-enable-users#upload-direct-routing-numbers-to-your-tenant).

To see the telephone numbers in your organization:

1. Go to the **Microsoft Teams admin center**.
2. In the left navigation, go to **Voice** &gt; **Phone numbers**.

    - For you to see the **Voice** option in the left navigation in the Microsoft Teams admin center, you must first buy at least one **Enterprise E5 license (or One Teams Premium license)**, one **Teams Phone** add-on license, or one **Audio Conferencing** add-on license.
3. To view the assignment status of a number, see the **Assignment Status** column, which also shows what type of service the number is assigned to. You can click the filter icon to filter by:

    - **Assigned to user**
    - **Assigned to conference bridge**
    - **Assigned to Voice app (Auto Attendant/Call Queue)**
    - **Unassigned**
4. On the **Filter** pane, you can use the drop-down list to filter your view by several different categories, few examples include:

    - Phone number **activation state**.
    - Phone number **Assigned to**
    - Phone number **Assignment status**
    - Phone numbers with specific **emergency address**, or **location**
    - **Phone number -** where you can search by number range that you set. You can search by lowest number or highest number, or search for Numbers that start with a number that you specify.
    - Phone number **from a specific Partner or Reseller**
    - Phone Number **type**.

## To see the activation status for number assignments

After assigning numbers to users, you might want to see the activation status of the number assignments:

1. Go to the **Microsoft Teams admin center**.
2. In the left navigation, go to **Voice** &gt; **Phone numbers**.
3. Click the filter icon to filter your view by **Activation state**. You can filter by:

    - **Activated**
    - **Assignment pending**
    - **Assignment failed**
    - **Update pending**
    - **Update failed**

## Using the Teams PowerShell module

You can also use the Teams PowerShell module version 1.1.6 or later to see the phone numbers in your organization. For more information about PowerShell, see [Microsoft Teams PowerShell Overview](teams-powershell-overview).

To see a list of all telephone numbers that you have for your organization, use the [Get-CsPhoneNumberAssignment](/en-us/powershell/module/teams/get-csphonenumberassignment) cmdlet. For example, to see each telephone number, its type, and its state, run the following command:

```PowerShell
Get-CsPhoneNumberAssignment | ft TelephoneNumber,ActivationState,NumberType
```

By default, the [Get-CsPhoneNumberAssignment](/en-us/powershell/module/teams/get-csphonenumberassignment) cmdlet returns the first 500 results. Use the "-skip" and "-top" parameters to customize your output.

Another way to get a list of all telephone numbers in your organization is to use the [Export-CsAcquiredPhoneNumber](/en-us/powershell/module/teams/export-csacquiredphonenumber) PowerShell cmdlet.

To see all of the telephone numbers that are assigned to users, use the [Get-CsOnlineUser](/en-us/powershell/module/teams/get-csonlineuser) cmdlet. For example, to see all users with a telephone number assigned, run the following command:

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```