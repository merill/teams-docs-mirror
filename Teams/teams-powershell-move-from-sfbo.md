---
layout: Conceptual
title: Migrating from Skype for Business Online Connector to the Teams PowerShell module - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-powershell-move-from-sfbo
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
ms.date: 2020-10-14T00:00:00.0000000Z
manager: sshastri
ms.topic: upgrade-and-migration-article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.collection:
- M365-collaboration
description: Learn how to move from Skype for Business Online Connector to the Teams PowerShell module to manage Teams.
locale: en-us
document_id: 09f27c0e-15db-920c-dee9-824bcab166cc
document_version_independent_id: c0bd47ae-da8c-b466-4e05-5c97b055ee9b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-powershell-move-from-sfbo.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-powershell-move-from-sfbo
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-powershell-move-from-sfbo.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: 3e607939-dbc0-063c-fc2c-4c2ee11e328b
---

# Migrating from Skype for Business Online Connector to the Teams PowerShell module - Microsoft Teams | Microsoft Learn

Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line. Administrators don't require Skype For Business Online Connector for their Teams administration.

Note

Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.

## How to Migrate

Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple. The below steps explain how to do this migration.

1. Install the latest Teams PowerShell module. For steps, see [Install Microsoft Teams PowerShell](teams-powershell-install).
2. Uninstall Skype For Business Online Connector. To uninstall, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.
3. In your PowerShell scripts, change the module name that's referenced in `Import-Module` from

    `SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.

    For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.
4. When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`. `Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session.

    ```powershell
       # When using the Skype for Business online connector
    
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
    
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
    
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
    
         # Example getting tenant details
         Get-csTenant
    
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```