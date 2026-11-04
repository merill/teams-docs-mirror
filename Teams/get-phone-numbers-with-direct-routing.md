---
layout: Conceptual
title: Get Direct Routing phone numbers in your Teams tenant - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/get-phone-numbers-with-direct-routing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: pavellatif
ms.date: 2025-05-05T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
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
- Calling Plans
description: Learn how to upload Direct Routing telephone numbers to your Teams admin center.
locale: en-us
document_id: 02709975-2966-7770-6909-3c0c8c73b10e
document_version_independent_id: 02709975-2966-7770-6909-3c0c8c73b10e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/get-phone-numbers-with-direct-routing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: get-phone-numbers-with-direct-routing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/get-phone-numbers-with-direct-routing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/b1cfdec6-b0c3-4209-818c-736879856e0e
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/37da4cc9-0cfc-42a9-ba5e-805706b01ef8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d0723c1-cf38-4c30-ab3d-5df787b33270
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3661fb96-d414-4a4e-b7ad-9370637790dd
platformId: 289afec2-3a16-c6ff-4c00-95bbcbdf30e3
---

# Get Direct Routing phone numbers in your Teams tenant - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Direct Routing

This article provides considerations and guidance for IT pros and admins who are acquiring new telephone numbers from a Direct Routing partner.

Direct Routing is one of several methods available to integrate your tenant with the Public Switched Telephone Network (PSTN).

To learn more about Direct Routing as a PSTN solution, see [Plan for Direct Routing](direct-routing-plan).

In a Direct Routing solution, the phone number services agreement is between your organization and your PSTN operator. You may fulfill other requirements with your Direct Routing PSTN operator, like assigning number usage types, Emergency Calling services, and more.

To reserve and acquire new Direct telephone numbers or to port existing numbers to your Direct Routing partner, work with your Direct Routing PSTN partner directly.

Once you acquire numbers from your partner, use the following guidance to upload those numbers so that you can manage your Direct Routing numbers in Teams.

One your numbers are uploaded to Teams, you can use Teams to assign Direct Routing numbers to users. To learn more, see [Manage phone numbers for users](assign-change-or-remove-a-phone-number-for-a-user).

## Considerations for getting Direct Routing numbers in your tenant

Direct Routing phone numbers can be managed in on-premises Active Directory or in Microsoft 365. Managing numbers in Microsoft 365 is recommended.

### Direct Routing numbers managed in an on-premises Active Directory

If you have or had a Skype for Business Server hybrid deployment, your on-premises Active Directory is most likely synchronizing with Microsoft 365. This means that directory attributes on user and resource accounts are managed in the on-premises Active Directory and synchronized into Microsoft 365.

If the Direct Routing phone number is managed on the user or resource account in the on-premises Active Directory, the msRTCSIP-Line parameter on the account contains a value. You can use a tool such as ADSI Edit to view the msRTCSIP-Line parameter for a user or resource account that has a Direct Routing phone number assigned in on-premises Active Directory.

Through the directory synchronization process (Microsoft Entra Connect), this parameter is automatically synchronized to the user or resource account in Microsoft 365. After the synchronization is complete, view the phone number by looking at the OnPremLineURi parameter in the output from the [Get-CsOnlineUser](/en-us/powershell/module/teams/get-csonlineuser) cmdlet.

| Where | Parameter | Value |
| --- | --- | --- |
| On-premises AD | msRTCSIP-Line | +14255551234 |
| Microsoft 365 | OnPremLineURi | +14255551234 |

### Direct Routing numbers managed in Microsoft 365

If you're not managing Direct Routing phone numbers in the on-premises Active Directory, then they're only managed in Microsoft 365. When numbers are managed in Microsoft 365 and you run the Get-CsOnlineUser cmdlet for a user or resource account, there's no visible value in the OnPremLineUri parameter.

You can manage Direct Routing numbers in Microsoft 365 with Teams PowerShell, using the [Set-CsPhoneNumberAssignment](/en-us/powershell/module/teams/set-csphonenumberassignment) and [Get-CsPhoneNumberAssignment](/en-us/powershell/module/teams/get-csphonenumberassignment) cmdlets.

### Direct Routing numbers managed in both an on-premises Active Directory and Microsoft 365

It's possible to manage Direct Routing phone numbers of some user and resource accounts in on-premises Active Directory while managing others in Microsoft 365. This capability depends on whether the attribute msRTCSIP-Line is set on the user or resource account in the on-premises Active Directory.

### Change where Direct Routing phone numbers are managed

To move management of Direct Routing phone numbers from on-premises Active Directory to Microsoft 365, in the on-premises Active Directory user or resource account, remove the phone number from the msRTCSIP-Line attribute.

The phone number needs to be reassigned to the user or resource account in Microsoft 365.

After the removal is synchronized to Microsoft 365, the OnPremLineUri attribute in the output from Get-CsOnlineUser on the user or resource account will be empty.

For more information, see [Clear Skype for Business attributes for all on-premises users in Active Directory](/en-us/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md).

## Upload Direct Routing numbers to your tenant

Uploading your Direct Routing phone numbers to Microsoft's telephone number management inventory supports future number management enhancements.

For example, if you upload your numbers, you can view them in the Teams admin center under **Phone Numbers** or by using the PowerShell cmdlets [Get-CsPhoneNumberAssignment](/en-us/powershell/module/teams/get-csphonenumberassignment) and [Export-CsAcquiredPhoneNumber](/en-us/powershell/module/teams/export-csacquiredphonenumber).

Uploading your Direct Routing phone numbers to Microsoft's telephone number management inventory is optional. If you don't upload the phone numbers, you can still assign numbers to users. Assigning a number to a user automatically uploads the number to Microsoft's telephone number management inventory if it's not already there.

### Use Teams admin center

1. Go to **Voice** &gt; **Phone numbers**.
2. Under the **Numbers** tab, select **Add**.

    Adding phone numbers to your tenant and to Microsoft's telephone number management inventory is accomplished by creating an order request. By selecting **Add**, you're originating an order request that creates an order ID and launch the process of uploading your Direct Routing numbers. To complete your order, follow the remaining steps.
3. Give your order a **Name** and **Description**.
4. From the options, choose **From Direct Routing**.
5. Select your preferred method of uploading the numbers by selecting from the drop-down, one of the following options:

#### Add one to many phone numbers

If you select **Add one to many phone numbers**, type or paste the phone numbers you wish to upload in the text field.

If you're adding more than one phone number to this list, separate each number with a comma or a new line.

#### Add phone number range

If you select **Add phone number range**, type or paste the starting and ending numbers of your range in the respective text fields.

#### Upload CSV

Note

CSV uploads that include additional telephone number attributes aren't yet available in the Teams admin center. Use Teams PowerShell to upload numbers with these attributes.

If you select **Upload CSV**, select the **Upload CSV** icon and select your CSV file.

The CSV file format requirements are to have a single column, with the first row populated as **TelephoneNumber** and each subsequent row including one phone number.

Download a template by selecting **Download a sample CSV file with Direct Routing Numbers**.

1. Select **Next** and proceed to review the validated numbers to be reserved by Microsoft's telephone number management inventory.
2. Select **Confirm**, then select **Finish**

### Use PowerShell

To upload Direct Routing telephone numbers to Microsoft's telephone number management inventory, use the [New-CsOnlineDirectRoutingTelephoneNumberUploadOrder](/en-us/powershell/module/microsoftteams/new-csonlinedirectroutingtelephonenumberuploadorder) cmdlet.

Use the `-FileContent` parameter to upload a CSV file containing telephone numbers and optional attributes: `LocationId`, `Tags`, `AcquiredCapabilities`, `NetworkSiteId`, and `ReverseNumberLookup`. Attributes can differ for each number. Each upload request supports up to 10,000 telephone numbers. For CSV format requirements, preparation instructions, and examples, see [Upload Direct Routing numbers from a CSV file](/en-us/powershell/module/microsoftteams/new-csonlinedirectroutingtelephonenumberuploadorder#example-4).

Uploading the numbers is an asynchronous operation.

### Order history

View the status of the numbers you uploaded in Teams admin center by navigating to **Voice** &gt; **Phone numbers** and selecting the **Order history** tab.

View the order status of numbers you uploaded with PowerShell by using the [Get-CsOnlineTelephoneNumberOrder](/en-us/powershell/module/teams/get-csonlinetelephonenumberorder) PowerShell cmdlet with **OrderType** set to `DirectRoutingNumberCreation`, as shown in the following example:

```PowerShell
 Get-CsOnlineTelephoneNumberOrder -OrderType DirectRoutingNumberCreation -OrderId <orderId>
```

Note

Whenever porting Direct Routing numbers to Teams using another PSTN connectivity option, the numbers must be released from Microsoft's telephone number management inventory. After unassigning the numbers from the users and before your number port event, use the PowerShell cmdlet [New-CsOnlineTelephoneNumberReleaseOrder](/en-us/powershell/module/teams/new-csonlinetelephonenumberreleaseorder) to make the Direct Routing numbers available for porting. A release order can also be used if you don't want to keep your acquired Direct Routing numbers in Microsoft's inventory.