---
layout: Conceptual
title: Overview of the Microsoft Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-desktop-admin
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MicrosoftHeidi
ms.author: heidip
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
ms.reviewer: shals
search.appverid: MET150
f1.keywords:
- NOCSH
description: Discover how to install, deploy, and manage the Microsoft Teams client across desktop, web, and mobile platforms. Includes admin deployment options, update behavior, and supported environments.
ms.localizationpriority: medium
locale: en-us
document_id: 0c86f401-cff4-93b3-ff69-b9787a87e644
document_version_independent_id: c0808bd3-cf63-0625-4c3c-65469c26fb3e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-desktop-admin.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-desktop-admin
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-desktop-admin.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ae1a75f7-33d7-af77-ac28-208abffd9549
---

# Overview of the Microsoft Teams client - Microsoft Teams | Microsoft Learn

## What is the Teams desktop client?

The Teams desktop client is designed with performance in mind, providing a fast, simple, and flexible experience. The Teams client installs and loads quickly, letting you launch the app and join meetings quickly, giving you more time to focus on business tasks.

The Teams client ensures efficient use of device resources. You have low memory and disk usage with the Teams client app. Whether you have users on multiple accounts or tenants, Teams client can help eliminate the silos and bring them together in one place, giving them more extensibility and scale.

## Get the Teams client

Microsoft Teams is available as a desktop app, web app, and mobile app. This article helps IT admins understand how to deploy, manage, and support the Teams client across platforms.

### Teams client availability

Teams is available on the following platforms:

| Platform | Availability | Notes |
| --- | --- | --- |
| Windows | ✅ | 64-bit and 32-bit installers available. |
| macOS | ✅ | Universal installer supports Intel and Apple silicon. |
| Linux | ❌ | Teams is no longer supported on Linux. |
| Web | ✅ | Supported in Microsoft Edge, Chrome, Firefox, Safari. |
| iOS and Android | ✅ | Available in the App Store and Google Play. |

For supported operating systems and browser versions, see [Teams client system requirements](teams-client-system-requirements).

You can install Teams in several ways:

- **Microsoft 365 Apps for enterprise**: Teams is included by default.
- **Manual installation**: Download the installer from [this link](https://www.microsoft.com/microsoft-teams/download-app).
- **Web access**: Use Teams at https://teams.microsoft.com.

## IT admin deployment options

Admins can deploy Teams using:

- [Microsoft Intune](/en-us/intune/intune-service/apps/manage-microsoft-teams) or other MDM tools.
- Group Policy and PowerShell scripts.
- Configuration Manager.
- Microsoft 365 Apps deployment tools: [Install Microsoft Teams with Microsoft 365 Apps](teams-client-deploy-with-m365apps).

To get started on deployment, see:

- [Teams client system requirements](teams-client-system-requirements)
- [Preparation checklist for organizations installing the Teams client](teams-client-deployment-checklist).
- [Teams for Mac - Overview and prerequisites](teams-client-mac-install-prerequisites).
- [Install Teams for Virtualized Desktop Infrastructure (VDI)](teams-client-vdi-requirements-deploy).
- [Teams client preinstallation script](teams-client-preinstallation-script).

## Updating the Teams client

Teams updates automatically in the background. Admins can manage update behavior using:

- The [Teams client health dashboard in the Teams admin center](teams-client-health).
- Group Policy settings.
- Microsoft 365 Apps admin center.
- Update rings and policies.

For more information, see [Why it's important to keep Teams updated](teams-client-update) and [Microsoft Teams update monitoring](teams-client-health-update-monitoring).

### Servicing agreement

The Modern Lifecycle Policy governs Teams, with the expectation that users remain on the most up-to-date version of the desktop client. Automatic updates ensure users have the latest capabilities, performance enhancements, security, and service reliability. An in-app alert displays if a user's current version is between one and three months old, and if there's a new version available.

Learn more about the Modern Lifecycle Policy under the [**Servicing agreement**](/en-us/microsoftteams/teams-client-update#servicing-agreement) for Microsoft Teams.

## Diagnostic and support tools

Admins can collect logs and troubleshoot issues using built-in tools:

- [Collect Teams client diagnostic logs](log-files).
- [Diagnostic logs for Teams Client](teams-client-diagnostic-logging).