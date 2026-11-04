---
layout: Conceptual
title: Enable users for Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-enable-users
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: filippse
ms.date: 2026-08-21T00:00:00.0000000Z
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- NOCSH
description: Learn how to enable users for Microsoft Teams Phone Direct Routing.
locale: en-us
document_id: bb2a9717-6565-8443-8833-f7fdce562781
document_version_independent_id: db88c4d6-5864-a481-86cf-465feb452d75
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-enable-users.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-enable-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-enable-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: 4401d9f6-cd28-8699-3e1d-e42027b828fc
---

# Enable users for Direct Routing - Microsoft Teams | Microsoft Learn

This article describes how to enable users for Direct Routing and represents step 2 in the following steps for configuring Direct Routing:

- Step 1. [Connect the Session Border Controller (SBC) with Phone System and validate the connection](direct-routing-connect-the-sbc) .
- **Step 2. Enable users for Direct Routing** (this article).
- Step 3. [Configure voice routing](direct-routing-voice-routing).
- Step 4. [Translate numbers to an alternate format](direct-routing-translate-numbers).

For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure).

When you're ready to enable users for Direct Routing, follow these steps:

1. Create a user in Microsoft 365 and assign a Teams Phone license.
2. Ensure that the user is homed online.
3. Configure the phone number and enable enterprise voice.
4. Configure sending calls directly to voicemail.
5. Assign Teams Only mode to users.

## Create a user and assign the license

There are two options for creating a new user in Microsoft 365. However, we recommend that your organization chooses only one option to avoid routing issues:

- Create the user in on-premises Active Directory and sync the user to the cloud. For more information, see [Integrate your on-premises directories with Microsoft Entra ID](/en-us/azure/active-directory/connect/active-directory-aadconnect).
- Create the user directly in the Microsoft 365 admin center. For more information, see [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

For information about license requirements, see [Licensing requirements](direct-routing-plan#licensing-requirements) in [Plan Direct Routing](direct-routing-plan).

## Ensure that the user is homed online

This step applies to Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing.

Direct Routing requires the user to be homed online. You can check by looking at the `RegistrarPool` parameter, which needs to have a value in the infra.lync.com domain. Microsoft recommends, but doesn't require, that you change the LineURI from on-premises to online when migrating users to Teams Direct Routing.

1. Connect a Microsoft Teams PowerShell session.
2. Issue the command:

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ```

    If `OnPremLineUri` is populated with a &lt;E.164 phone number&gt;, the phone number was assigned on-premises and synchronized to Microsoft 365. If you want to manage the phone number online, clear the parameter using on-premises Skype for Business Management Shell and synchronize to Microsoft 365 before configuring the phone number using Teams PowerShell.
3. From Skype for Business Management Shell, issue the command:

    ```PowerShell
    Set-CsUser -Identity "<User name>" -LineUri $null
    ```

Note

Don't set `EnterpriseVoiceEnabled` to False as there's no requirement to do so. Setting `EnterpriseVoiceEnabled` to False can lead to dial plan normalization issues if legacy Skype for Business phones are in use and the Tenant hybrid configuration is set with UseOnPremDialPlan $True.

After the changes sync to Microsoft 365, the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri` is:

```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```

Note

All user's phone attributes must be managed online before you [decommission your on-premises Skype for Business environment](/en-us/skypeforbusiness/hybrid/decommission-on-prem-overview).

## Upload Direct Routing numbers to your tenant

Uploading your Direct Routing phone numbers to Microsoft's telephone number management inventory supports future number management enhancements.

For example, if you upload your numbers, you can view them in the Teams admin center under **Phone Numbers** or by using the PowerShell cmdlets [Get-CsPhoneNumberAssignment](/en-us/powershell/module/teams/get-csphonenumberassignment) and [Export-CsAcquiredPhoneNumber](/en-us/powershell/module/teams/export-csacquiredphonenumber).

Uploading your Direct Routing phone numbers to Microsoft's telephone number management inventory is optional. If you don't upload the phone numbers, you can still assign numbers to users. Assigning a number to a user automatically uploads the number to Microsoft's telephone number management inventory if it's not already there.

### Use Teams admin center

1. Go to **Voice** &gt; **Phone numbers**.
2. Under the **Numbers** tab, select **Add**.

    Adding phone numbers to your tenant and to Microsoft's telephone number management inventory is accomplished by creating an order request. By selecting **Add**, you are originating an order request that will create an order ID and launch the process of uploading your direct routing numbers. Follow the remaining steps to complete your order.
3. Give your order a **Name** and **Description**.
4. From the options, choose **From Direct Routing**.
5. Select your preferred method of uploading the numbers by selecting from the drop-down, one of the following options:

#### Add one to many phone numbers

If you select **Add one to many phone numbers**, type or paste the phone numbers you wish to upload in the text field.

If you are adding more than one phone number to this list, separate each number with a comma or a new line.

#### Add phone number range

If you select **Add phone number range**, type or paste the starting and ending numbers of your range in the respective text fields.

#### Upload CSV

Note

CSV uploads that include additional telephone number attributes aren't yet available in the Teams admin center. Use Teams PowerShell to upload numbers with these attributes.

1. If you select **Upload CSV**, select the **Upload CSV** icon and select your CSV file.

    The CSV file format requirements are to have a single column, with the first row populated as **TelephoneNumber** and each subsequent row including one phone number.
2. Download a template by selecting **Download a sample CSV file with Direct Routing Numbers**.
3. Select **Next** and proceed to review the validated numbers to be reserved by Microsoft's telephone number management inventory.
4. Select **Confirm**, then select **Finish**.

### Use PowerShell

To upload Direct Routing telephone numbers to Microsoft's telephone number management inventory, use the [New-CsOnlineDirectRoutingTelephoneNumberUploadOrder](/en-us/powershell/module/microsoftteams/new-csonlinedirectroutingtelephonenumberuploadorder) cmdlet.

Use the `-FileContent` parameter to upload a CSV file containing telephone numbers and optional attributes: `LocationId`, `Tags`, `AcquiredCapabilities`, `NetworkSiteId`, and `ReverseNumberLookup`. Attributes can differ for each number. Each upload request supports up to 10,000 telephone numbers. For CSV format requirements, preparation instructions, and examples, see [Upload Direct Routing numbers from a CSV file](/en-us/powershell/module/microsoftteams/new-csonlinedirectroutingtelephonenumberuploadorder#example-4).

Uploading the numbers is an asynchronous operation.

### Order history

View the status of the numbers you uploaded in TAC by navigating in TAC to **Voice** &gt; **Phone numbers** and selecting the **Order history** tab.

View the order status of numbers you uploaded with PowerShell by using the [Get-CsOnlineTelephoneNumberOrder](/en-us/powershell/module/teams/get-csonlinetelephonenumberorder) PowerShell cmdlet with **OrderType** set to `DirectRoutingNumberCreation`, as shown in the following example:

```PowerShell
 Get-CsOnlineTelephoneNumberOrder -OrderType DirectRoutingNumberCreation -OrderId <orderId>
```

Note

Whenever porting Direct Routing numbers to Teams using another PSTN connectivity option, the numbers must be released from Microsoft's telephone number management inventory. After unassigning the numbers from the users and before your number port event, use the PowerShell cmdlet [New-CsOnlineTelephoneNumberReleaseOrder](/en-us/powershell/module/teams/new-csonlinetelephonenumberreleaseorder) to make the Direct Routing numbers available for porting. A release order can also be used if you don't want to keep your acquired Direct Routing numbers in Microsoft's inventory.

## Configure the phone number and enable enterprise voice

After you create the user and assign a license, you must configure the user's online phone settings. The configuration of Cloud Voicemail for the user is automatic and no other configuration needs to be done.

You can configure the phone number by using the Teams admin center or by using Teams PowerShell.

### Use Teams admin center

1. Go to **Users** &gt; **Manage users**.
2. Select a user.
3. Under **Account** &gt; **General information**, select **Edit**.
4. Under **Assign phone number**, from the **Phone number type** drop-down menu, select **Direct Routing**.
5. Enter an assigned phone number and a phone number extension if applicable.
6. Select **Apply**.

    The account's general information now shows the assigned phone number and displays Direct Routing as the phone number type.

### Use PowerShell

1. Connect to a Microsoft Teams PowerShell session.
2. The next steps depend on whether you're managing the user's phone number on-premises or online. If you're managing the phone number on-premises, you must use the on-premises Skype for Business Management Shell, Control Panel, or one of the methods explained in [Decide how to manage attributes after decommissioning](/en-us/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes).

    - If you're managing the user's phone number on-premises, you need to ensure that the user is Enterprise Voice enabled online by using the following command:

        ```PowerShell
        Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
        ```
    - If you're managing the user's phone number online, you need to assign the phone number to the user by using the following command in Teams PowerShell. The user is automatically Enterprise Voice enabled by the command:

        ```PowerShell
        Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
        ```

        For example, to add a phone number for user "Spencer Low," enter the following command:

        ```PowerShell
        Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
        ```

        If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following command:

        ```PowerShell
        Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
        Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
        ```

    Microsoft recommends, but doesn't require, that the phone number is configured as a full E.164 phone number with country code. You can configure phone numbers with extensions. These extensions are used to look up users when the lookup against the base number returns more than one result. This functionality allows companies to configure phone numbers with the same base number and unique extensions. For lookup to be successful, the invite must include the full number with extension as follows:

    ```PowerShell
    Invite: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```

## Configure sending calls directly to voicemail

Direct Routing allows you to end the call to a user and send it directly to a user's voicemail. If you want to send a call directly to voicemail, attach `opaque=app:voicemail` to the Request URI header (for example, `sip:user@contoso.com;opaque=app:voicemail`). The Teams user doesn't receive the calling notification. Instead, the call directly connects to the voicemail of the user.

## Assign Teams Only mode to users to ensure calls land in Microsoft Teams

Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client. To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy. For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement). If your organization uses Skype for Business Server, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype).