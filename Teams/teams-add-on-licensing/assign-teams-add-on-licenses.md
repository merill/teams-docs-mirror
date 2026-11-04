---
layout: Conceptual
title: Assign Teams add-on licenses to users - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: ITPro
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.custom:
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- tier1
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: alexcerone
ms.date: 2025-02-27T00:00:00.0000000Z
description: Learn how to assign Teams add-on licenses to users for capabilities like Audio Conferencing, Teams Phone, and Calling Plans.
locale: en-us
document_id: ed46e6b1-48c5-5302-2f38-89c315d4bff7
document_version_independent_id: 81053999-79ca-888d-38fa-8978276b6228
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-add-on-licensing/assign-teams-add-on-licenses.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-add-on-licensing/assign-teams-add-on-licenses
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-add-on-licensing/assign-teams-add-on-licenses.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e9efd84e-cb55-4ad0-ca32-41e2504d044d
---

# Assign Teams add-on licenses to users - Microsoft Teams | Microsoft Learn

Add-on licenses are licenses for specific Teams capabilities like Audio Conferencing, Teams Phone, and Calling Plans. This article describes how to assign add-on licenses to individual users and large sets of users in bulk.

Note

See [Teams add-on licensing](microsoft-teams-add-on-licensing) for Teams capabilities that are available with add-on licenses. You'll also find information about which licenses you need to buy and how to buy them, depending on your plan. After you decide which capabilities you want for your users, assign the licenses to them.

You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization. You must be a User management admin to manage licenses.

## What you need to know before you assign Teams Phone, Calling Plan, and Communication Credits licenses

Before you get started, review the following requirements:

- If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for users, you only need to assign a Teams Phone Standard license. Do NOT assign a Calling Plan license.
- After assigning a Microsoft Calling Plan to a user, it can take up to 24 hours before they'll see the dial pad in their Teams client. If the dial pad isn't shown in 24 hours, check your [dial pad configuration](../dial-pad-configuration). If necessary, you can also [contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
- You'll get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose the option to buy more.
- Even if your users are assigned Enterprise E5 licenses, you still need to connect them to the PSTN. You have several [PSTN connectivity options](../pstn-connectivity), including Microsoft Teams Calling Plans, Direct Routing, or Operator Connect.
- After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users. For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans).

## Using the Microsoft 365 admin center

Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.

You assign licenses on the **Billing** &gt; **Licenses** page (for up to 20 users at a time) or the **Users** &gt; **Active users** page (for up to 40 users at a time). The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.

For step-by-step instructions, see [Assign licenses to users](/en-us/microsoft-365/admin/manage/assign-licenses-to-users).

If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use PowerShell or [group-based licensing in Microsoft Entra ID](/en-us/azure/active-directory/users-groups-roles/licensing-groups-assign).

## Using PowerShell

Use PowerShell to assign licenses to users in bulk. To learn more, see [Assign licenses to user accounts with PowerShell](/en-us/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### Example script

Here's an example of how to use a script to assign licenses to your users.

1. [Install the Microsoft Graph PowerShell Module](/en-us/powershell/microsoftgraph/installation).
2. At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where `CompanyName:License` is your organization name and the identifier for the license that you want to assign. For example, `litwareinc:MCOMEETADV`.

    The identifier is different than the friendly name of the license. For example, the identifier for Audio Conferencing is `MCOMEETADV`. To learn more, see Product names and SKU identifiers for licensing.

```powershell
    # Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    # Example of text file:
    # user1@domain.com
    # user2@domain.com
    
    # Import Module
    Import-Module Microsoft.Graph.Users.Actions
    
    # Authenticate to Microsoft Graph
    Connect-MgGraph
    
    # File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
        $OFD = New-Object System.Windows.Forms.OpenFileDialog
        $OFD.filter = "text files (*.*)| *.txt"
        $OFD.ShowDialog() | Out-Null
        $OFD.filename
    
    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }
    
    # Create a variable of all users
    $users = Get-Content $OFD.filename
    
    # License each user in the $users variable
      $EmsSku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq ''
      $addLicenses = @(
      @{SkuId = $EmsSku.SkuId}
      )

      foreach ($user in $users){
      Write-host "Assigning License: $user"
      Set-MgUserLicense -UserId $user -AddLicenses $addLicenses -ErrorAction SilentlyContinue
      }
```

For example, to assign Microsoft 365 Enterprise E1 and Audio Conferencing licenses, use the following syntax in the script:

```powershell
    Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All

    $EmsSku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'ENTERPRISEPACK'
    $FlowSku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'MCOMEETADV'
    $addLicenses = @(
    @{SkuId = $EmsSku.SkuId},
    @{SkuId = $FlowSku.SkuId}
    )

    Set-MgUserLicense -UserId $user -AddLicenses $addLicenses -RemoveLicenses @()
```

To assign a Teams Phone with Calling Plan license, use the following syntax in the script:

```powershell
    Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All

    $EmsSku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'MCOTEAMS_ESSENTIALS'

    Set-MgUserLicense -UserId $user -AddLicenses @() -RemoveLicenses @()
```

## Product names and SKU identifiers for licensing

Important

Starting April 1, 2024, all new Enterprise customers who wish to provide workers with both Microsoft Teams and the value in existing Microsoft 365 or Office 365 Enterprise suites (E1/E3/E5) will need to purchase two SKUs: one E1/E3/E5 (no Teams) suite and one Teams standalone (*Microsoft Teams Enterprise* or *Microsoft Teams EEA*). Microsoft 365 Business suites (up to 300 users) and Frontline worker suites will be available in versions both with and without Teams.

For Enterprise customers in the European Economic Area (EEA) and Switzerland, this change became effective on October 1, 2023.

Enterprise customers already subscribed to Microsoft 365 or Office 365 suites that include Teams prior to April 1, 2024 will continue to be able to use, renew, upgrade, and otherwise adjust their subscriptions that include Teams as before.

For more information on this licensing change in the EEA and Switzerland, see [New subscription structure for Microsoft 365 in Europe](https://www.microsoft.com/licensing/news/Microsoft365-Teams-EEA).

For more information on this licensing change for all other global regions, see [Microsoft Teams licensing announcement](https://aka.ms/MSTeamsLicensingROW).

Here's a partial list of product names and their corresponding SKU part names that you can reference when you use PowerShell to manage licenses in Teams.

To learn more, see [View licenses and services with PowerShell](/en-us/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/en-us/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu).

| Product name | SKU part name |
| --- | --- |
| Microsoft Enterprise E5 (with Teams Phone) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (without Audio Conferencing) | ENTERPRISEPREMIUM\_NOPSTNCONF |
| Microsoft Enterprise E5 (with Audio Conferencing) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365\_BUSINESS\_ESSENTIALS |
| Microsoft 365 Business Standard | O365\_BUSINESS\_PREMIUM |
| Microsoft 365 Business | SPB |
| Audio Conferencing | MCOMEETADV |
| Audio Conferencing Pay Per Minute (pay as you go) Requires Communications Credits to be set up and enabled.\* | MCOMEETACPEA |
| Teams Phone Standard and Teams Phone Standard for Frontline Workers | MCOEV |
| Teams Phone with Calling Plan | MCOTEAMS\_ESSENTIALS |
| International Calling Plan | MCOPSTN2 |
| Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries/regions) | MCOPSTN1 |
| Domestic Calling Plan (120 minutes per user/month for each country/region) *This plan isn't available in the United States.* | MCOPSTN5 |
| Domestic Calling Plan (240 minutes per user/month for each country/region) *This plan isn't available in the United States.* | MCOPSTN6 |
| Communications Credits | MCOPSTNPP |
| Pay-As-You-Go Calling Plans (Zone-1 Countries) | MCOPSTN\_PAYG\_1 |
| Pay-As-You-Go Calling Plans (Zone-2 Countries) | MCOPSTN\_PAYG\_2 |
| Microsoft Teams Rooms Basic | Microsoft\_Teams\_Rooms\_Basic |
| Microsoft Teams Rooms Basic without Audio Conferencing | Microsoft\_Teams\_Rooms\_Basic\_without\_Audio\_Conferencing |
| Microsoft Teams Rooms Pro | Microsoft\_Teams\_Rooms\_Pro |
| Microsoft Teams Rooms Pro without Audio Conferencing | Microsoft\_Teams\_Rooms\_Pro\_without\_Audio\_Conferencing |
| Microsoft Teams Shared Devices | MCOCAP |
| Microsoft Teams Premium | Microsoft\_Teams\_Premium |
| Microsoft Teams Enterprise EEA | Microsoft\_Teams\_EEA |
| Microsoft Teams Enterprise | Microsoft\_Teams\_Enterprise |