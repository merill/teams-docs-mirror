---
layout: Conceptual
title: Create and manage dial plans - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/create-and-manage-dial-plans
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 2025-04-25T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Learn how to use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans (PSTN Calling dial plans).
locale: en-us
document_id: 451b44cf-961a-5bf5-e4b3-16b96e008dd7
document_version_independent_id: 54e706e1-aaa2-3a03-b8c6-5e96244b85ac
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/create-and-manage-dial-plans.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-and-manage-dial-plans
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/create-and-manage-dial-plans.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8789fc27-a3a8-1585-0e8c-d2652f59cdae
---

# Create and manage dial plans - Microsoft Teams | Microsoft Learn

After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for voice routing, you're ready to create the dial plans. With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.

## Using the Microsoft Teams admin center

### Create a dial plan

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Dial plans**.
2. Select **Add**, and then enter a name and description for the dial plan.
3. Under **Normalization rules**, configure and associate one or more [normalization rules](phone-normalization-rules) for the dial plan. Each dial plan must have at least one normalization rule associated with it. To do this, do one or more of the following:

    - To create a new normalization rule and associate it with the dial plan, select **Add**, and then define the rule.
    - To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then select **Edit**. Make the changes you want, and then select **Save**.
    - To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then select **Delete**.
4. Arrange the normalization rules in the order that you want. Select **Move up** or **Move down** to change the position of rules in the list.

    Note

    Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number. If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones. If you set up a dial plan that normalizes a dialed number without a "+", the calling service will attempt to normalize the number again using Tenant and regional dial plan rules. To avoid double normalization, it's recommended that all normalization rules result in numbers starting with a "+". Direct Routing customers can use [trunk translation](direct-routing-translate-numbers) rules to remove the "+" if required.
5. Select **Save**.
6. If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then select **Test**.

### Edit a dial plan

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Dial plans**.
2. Select the dial plan by clicking to the left of the dial plan name, and then select **Edit**.
3. Make the changes that you want, and then select **Save**.

### Assign a dial plan to users

You assign a dial plan in the same way you assign policies. You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

## Using PowerShell

### Start PowerShell

Open a Windows PowerShell command prompt and run the following commands:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

### Create and manage your dial plans

You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.

#### Using single cmdlets

- To create a new dial plan, run the following script:

    ```PowerShell
    New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -SimpleName "Dial-Plan-for-Redmond"
    ```

    For other examples and parameters, see [New-CsTenantDialPlan](/en-us/powershell/module/teams/new-cstenantdialplan).
- To edit the settings of an existing dial plan, run the following script:

    ```PowerShell
    Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -SimpleName "Dial-Plan-for-Redmond"
    ```

    For other examples and parameters, see [Set-CsTenantDialPlan](/en-us/powershell/module/teams/set-cstenantdialplan).
- To add users to a dial plan, run the following script:

    ```PowerShell
    Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
    ```

    For other examples and parameters, see [Grant-CsTenantDialPlan](/en-us/powershell/module/teams/grant-cstenantdialplan).
- To view the settings on a dial plan, run the following script:

    ```PowerShell
    Get-CsTenantDialPlan -Identity RedmondDialPlan
    ```

    For other examples and parameters, see [Get-CsTenantDialPlan](/en-us/powershell/module/teams/get-cstenantdialplan).
- To delete a dial plan, run the following script:

    ```PowerShell
    Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
    ```

    For other examples and parameters, see [Remove-CsTenantDialPlan](/en-us/powershell/module/teams/remove-cstenantdialplan).
- To see the settings of the effective dial plan, run the following script:

    ```PowerShell
    Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
    ```

    For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/en-us/powershell/module/teams/get-cseffectivetenantdialplan).
- To test the effective settings of a dial plan, run:

    ```PowerShell
    Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
    ```

    For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/en-us/powershell/module/teams/test-cseffectivetenantdialplan).

#### Using a PowerShell script

Run this script to delete a normalization rule that's associated with a tenant dial plan without needing to delete the tenant dial plan first:

```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

Run this script to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan:

```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

Run this script to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan:

```PowerShell
$nr1=New-CsVoiceNormalizationRule -Identity Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Run the following script when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.

```PowerShell
(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Run this script to find all users who have been granted the RedmondDialPlan tenant dial plan.

```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Run this script to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.

```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization. You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.

- Run this script in Skype for Business Server Management Shell on-premises to save the on-premises dial plan to the .xml file.

    ```PowerShell
    $DPName = "OPDP1"
    $DPFileName = "dialplan.xml"
    Get-CsDialplan $DPName | Export-Clixml $DPFileName
    ```
- Run this script in Teams PowerShell Module online to create the new tenant dial plan.

    ```PowerShell
    $DPFileName = "dialplan.xml"
    $dp = Import-Clixml $DPFileName
    $NormRules = @()
    ForEach($nr in $dp.NormalizationRules)
    {
     $id1 = "Global/" + $nr.Name
     $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
     $NormRules += $nr2
    }
    New-CsTenantDialPlan -Identity $dp.SimpleName -Description $dp.Description -SimpleName $dp.SimpleName -NormalizationRules $NormRules
    ```

### Name and simple name

For user dial plans, specify a descriptive name that identifies the users to which the dial plan will be assigned.

The dial plan Simple Name is an attribute of the dial plan that is prepopulated with a string that is derived from the dial plan name. The Simple Name field is editable in PowerShell, which enables you to create a more descriptive naming convention for your dial plans. The Simple Name value can't be empty and must be unique.

A best practice is to develop a naming convention for your entire organization and then uses this convention consistently across all sites and users.

We recommend that you type the common, recognizable name of the ***geographic location*** or ***group of users*** to which the corresponding dial plan applies.