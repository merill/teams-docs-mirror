---
layout: Conceptual
title: PowerShell script sample - Create & assign messaging policy - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/scripts/powershell-script-teams-messaging-policy-edu
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: article
ms.reviewer: ritikag
ms.date: 2018-09-11T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
description: Use this PowerShell script to create a messaging policy in Teams and assign it to users in your organization.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 5dfe01e2-b14d-226d-de27-40cb2733a65d
document_version_independent_id: 09477e15-46e1-1a9a-def6-93ef73f24e24
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/scripts/powershell-script-teams-messaging-policy-edu.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: scripts/powershell-script-teams-messaging-policy-edu
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/scripts/powershell-script-teams-messaging-policy-edu.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 43abf41d-c36d-8280-2c0e-6c1ecd1b87de
---

# PowerShell script sample - Create & assign messaging policy - Microsoft Teams | Microsoft Learn

Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.

For more information about using this PowerShell script, see [Quick start - Teams for Education](../teams-quick-start-edu).

This script uses the [Grant-CsTeamsMessagingPolicy](/en-us/powershell/module/teams/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module. See [Teams PowerShell overview](../teams-powershell-overview) to learn more about managing Teams using PowerShell.

## Before you start

Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=54616), and then restart your computer if prompted.

To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## Sample script

```powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
```

Note

You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of. For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu) and [Assign policies to your users in Teams](../policy-assignment-overview).