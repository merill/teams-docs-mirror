---
layout: Conceptual
title: Bulk deploy the Microsoft Teams desktop client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-bulk-install
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
ms.date: 2026-07-16T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: 
search.appverid: MET150
f1.keywords:
- NOCSH
description: Bulk install the Microsoft Teams client.
ms.localizationpriority: medium
locale: en-us
document_id: 9c1f5040-eb93-421b-7437-0d97d3d79424
document_version_independent_id: 9c1f5040-eb93-421b-7437-0d97d3d79424
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-bulk-install.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-bulk-install
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-bulk-install.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: cc9ac01b-edc1-6bf8-ed37-1d7f2df5b29a
---

# Bulk deploy the Microsoft Teams desktop client - Microsoft Teams | Microsoft Learn

Direct or "bulk" deployments are helpful because users don't need to manually download and install the Teams client. Microsoft provides an executable (.exe) file for the Teams client. This executable allows you to deploy the application directly to computers in your organization using your choice of software management tools, such as Intune or Configuration Manager.

The Teams installer installs the Teams MSIX package on a target computer, making sure that Teams can interoperate correctly with Office and other Microsoft software.

Note

**New.** An offline installer option is now available. Learn more: Download and install Teams using an offline installer

## How it works

**TeamsBootstrapper** is a lightweight online installer with a headless command-line interface. It allows admins to provision (install) the app for all users on a given target computer.

When **teamsbootstrapper.exe** is run on a computer:

- The installer downloads the latest Teams MSIX package from Microsoft
- The installer installs the Teams application for all users on the computer, and any users who may be added afterwards.

Important

If users previously installed a different Teams version, that version is replaced with the provisioned version.

- Modifies the registry to allow Teams to work with Office and other computer applications.
- Displays success or failure message on the command line

Important

You must use the latest version of the bootstrapper.exe. If you downloaded the .exe previously, view **Properties &gt; Details &gt; Product version** on your version to confirm you have the latest version. You can compare it to the properties on the latest download.

## Prerequisites for target computers

For Teams to be successfully installed, computers must meet the minimum requirements listed in [Teams client system requirements](teams-client-system-requirements).

Additional requirements:

| Requirement | Version/Description |
| --- | --- |
| Office | Microsoft 365 Apps or Office LTSC 2021 Learn more: [Office versions and connectivity to Microsoft 365 services](/en-us/deployoffice/endofsupport/microsoft-365-services-connectivity) |
| Settings | Turn on the "Show Notification Banners" setting in **System &gt; Notifications &gt; Microsoft Teams** to receive Teams Notifications. |
| Webview2 | Update to the most current version. Learn more: [Enterprise management of WebView2 Runtimes](/en-us/microsoft-edge/webview2/concepts/enterprise) |
| Delivery optimization (DO) | DO powers Teams automatic updates. [What is Delivery Optimization?](/en-us/windows/deployment/do/waas-delivery-optimization)Recommended settings: [Set up Delivery Optimization](/en-us/windows/deployment/do/waas-delivery-optimization-setup#recommended-delivery-optimization-settings)**Note:** Download Mode 100 (Bypass) isn't supported. |

## Install the Teams application

All steps must be completed to successfully deploy Teams.

Important

You must run the latest version of the bootstrapper.exe to avoid any issues that may be fixed. If you downloaded the file previously, check **Properties &gt; Details &gt; Product version** to confirm you have the latest version. You can compare it to the latest download.

### Option 1A: Download and install Teams for a single computer

To install Teams on a single computer with many users, follow these steps:

1. [Download the .exe installer](https://go.microsoft.com/fwlink/?linkid=2243204&amp;clcid=0x409). If you downloaded this file previously, compare the properties on each file to confirm you have the latest version.
2. Open the Command Prompt as an Admin.
3. At the prompt, enter: `.\teamsbootstrapper.exe -p`
4. A success or fail status displays. If you receive an error, learn more at [Common HRESULT values](/en-us/windows/win32/seccrypto/common-hresult-values).

    ![command line prompt feedback](media/new-teams-direct-deploy-cmd-feedback.png)

#### Option 1B: Download and install Teams using an offline installer

Admins can also use a local teams MSIX to provision Teams. This option minimizes the amount of bandwidth used for the initial installation. The MSIX can exist in a local path or UNC.

1. [Download the .exe installer.](https://go.microsoft.com/fwlink/?linkid=2243204&amp;clcid=0x409). If you downloaded this file previously, compare the properties on each file to confirm you have the latest version.
2. Download the MSIX:- [MSIX x86](https://go.microsoft.com/fwlink/?linkid=2196060&amp;clcid=0x409)- [MSIX x64](https://go.microsoft.com/fwlink/?linkid=2196106)- [ARM64](https://go.microsoft.com/fwlink/?linkid=2196207&amp;clcid=0x409)
3. Open the Command Prompt as an Admin.
4. Depending on where your MSIX is located, take the following action:

    **For local path, enter:**`.\teamsbootstrapper.exe -p -o "c:\path\to\teams.msix"`

    *Example:*

    [![Screenshot that shows the local path location for offline installer.](media/new-teams-bulk-offline-localpath.png)](media/new-teams-bulk-offline-localpath.png#lightbox)

    **For UNC, enter:**`.\teamsbootstrapper.exe -p -o "`\`unc\path\to\teams.msix"`

    *Example:*

    [![Screenshot that shows the offline location using unc.](media/new-teams-bulk-offline-unc.png)](media/new-teams-bulk-offline-unc.png#lightbox)

#### Option 2: Install Teams across your organization

To deploy this installer to a group of computers, or your entire organization, follow these steps:

1. [Download the .exe installer](https://go.microsoft.com/fwlink/?linkid=2243204&amp;clcid=0x409). If you downloaded this file previously, compare the properties on each file to confirm you have the latest version.
2. Distribute the installer to your target computers using [Intune](/en-us/mem/intune/apps/apps-add-office365), [Microsoft Endpoint Configuration Manager](/en-us/configmgr/core/understand/introduction), [Group Policy](/en-us/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software), or third-party distribution software.
3. Run the installer on each computer.

### Gov cloud deployments for PC and Mac

#### PC update

If the customer tenant is on the GCCH, DoD, or Gallatin, the customer may need to set the initial cloud endpoint through the following registry key. Setting the endpoint with the registry key restricts Teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams, as shown here:

```console
HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams
Value = CloudType
value type = DWORD
  1 = Commercial, 2 = GCC, 3 = GCCH, 4 = DOD, 7 = Gallatin
```

#### Mac update

If the customer tenant is on the GCCH, DoD, or Gallatin, the customer may need to set the initial cloud endpoint through the following .plist configuration key. Setting the endpoint with the .plist configuration restricts teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams, as shown here:

```console
Domain: com.microsoft.teams2
Key: CloudType
Data Type: Int
Value: {Enter number associated with the cloud}
  1 = Commercial, 2 = GCC, 3 = GCCH, 4 = DOD, 7 = Gallatin
```

The .plist configuration can be propagated to managed devices using Intune as described in [Add preference file settings to macOS devices in Microsoft Intune](/en-us/mem/intune/configuration/preference-file-settings-macos).

## Remove Teams for all users

For more information, see [How to uninstall the Teams client](teams-client-uninstall).