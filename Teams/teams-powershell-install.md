---
layout: Conceptual
title: Install Microsoft Teams PowerShell - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-powershell-install
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: mattslomka
author: MattSlomka
ms.author: mattslomka
manager: kimmatlock
ms.date: 2026-02-20T00:00:00.0000000Z
ms.topic: install-set-up-deploy
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.collection:
- M365-collaboration
description: Learn to use the PowerShell controls for managing Microsoft Teams.
locale: en-us
document_id: cd283f6e-3865-ed70-d663-cc461ee8ba57
document_version_independent_id: 2450d311-fc04-d8b6-b4a2-b1890ec6fc3e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-powershell-install.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-powershell-install
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-powershell-install.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f1c9203c-f65c-7e41-ff1c-27e76ec2cf97
---

# Install Microsoft Teams PowerShell - Microsoft Teams | Microsoft Learn

This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.

## Requirements

Microsoft Teams PowerShell module requires Windows PowerShell 5.1 or PowerShell 7.2 or later on all platforms. Install the [latest version of PowerShell](/en-us/powershell/scripting/install/installing-powershell) available for your operating system.

To check your PowerShell version, run the following command from within a PowerShell session:

```powershell
$PSVersionTable.PSVersion
```

We recommend that you use the Install-Module cmdlet to install the Microsoft Teams PowerShell module.

If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you see the following message:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Answer **Yes** or **Yes to All** to continue with the installation.

## Installing using the PowerShellGallery

Microsoft Teams PowerShell module is currently supported for use with Windows PowerShell 5.1 or PowerShell 7.2 or later. Follow these steps to install the module with Windows PowerShell 5.1 for example:

1. Update to [Windows PowerShell 5.1](/en-us/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.
2. Install [.NET Framework 4.7.2](/en-us/dotnet/framework/install) or later.
3. Run the following command to install the latest PowerShellGet:

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    ```
4. Install the Teams PowerShell Module.

    ```powershell
    Install-Module -Name MicrosoftTeams -Force -AllowClobber
    ```

## Offline Installation

In some environments, it's not possible to connect to the PowerShell Gallery. In those situations, follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).

## Sign in

To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.

```PowerShell
Connect-MicrosoftTeams
```

## Update Teams PowerShell Module

To update any PowerShell module, you should use the same method used to install the module. For example, if you originally used Install-Module, then you should use [Update-Module](/en-us/powershell/module/powershellget/update-module) to get the latest version.

```powershell
Update-Module MicrosoftTeams
```

Warning

If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail. Close PowerShell and re-open a new elevated PowerShell session.

## Uninstall Teams PowerShell

To uninstall Microsoft Teams PowerShell, open a new PowerShell session and use the below method:

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -AllVersions
```