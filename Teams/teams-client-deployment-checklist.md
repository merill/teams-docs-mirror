---
layout: Conceptual
title: Deployment checklist for the Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-deployment-checklist
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: heidip
author: MicrosoftHeidi
manager: jtremper
ms.topic: checklist
ms.date: 2025-06-30T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: amitsri
search.appverid: MET150
f1.keywords:
- NOCSH
description: A checklist of things you need to do and check in your environment before installing the Teams client. Helpful for medium and large business specifically.
ms.localizationpriority: medium
locale: en-us
document_id: 48fd5509-ec53-b346-c16b-12ad445a74a1
document_version_independent_id: 48fd5509-ec53-b346-c16b-12ad445a74a1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-deployment-checklist.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-deployment-checklist
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-deployment-checklist.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c2fdfa36-df21-a4a2-de03-420b500b88c3
---

# Deployment checklist for the Teams client - Microsoft Teams | Microsoft Learn

As part of the deployment for the Teams client, we have information on the executables, locations, and the installer package of the client. Organizations may have different settings in their environment, such as antivirus, network settings, QoS, and so on.

- Name and location: Teams client uses ms-teams.exe & ms-teamsupdate.exe for installation. These files are located in: "Program Files\WindowsApps\MSTeams\_[appversion]\_[cpu arch]\_\_8wekyb3d8bbwe".
- MSIX Installer technology stays current with the newest OS patches. Customers with installation problems in the past may resolve them with the latest OS updates.

Note

Make sure your third-party software is ready to function with the Teams client.

## Checklist

- **OS/WV2 prerequisites**: Make sure the device has an updated Operating System (OS) and WebView2 (WV2) version. see [Teams client system requirements](teams-client-system-requirements). **NOTE**: The Teams client doesn't work on lower OS versions.
- **Device policies restrictions**: [Policies](/en-us/microsoftteams/troubleshoot/teams-administration/fix-new-teams-installation-issues#policy-settings-prevent-download-and-installation) must not block the Teams installation (MSIX) and the Teams Meeting add-in (MSI) or the [Webview2 updater](/en-us/microsoft-edge/webview2/concepts/enterprise).
- **Network considerations**: For a good meeting experience, review any configuration to make sure the correct Teams file paths or binary name is being used. Some examples include configurations for:
    - **Local Firewalls:** If you use Windows Firewall policies to define inbound/outbound rules specific to the Teams application, you need to update them to reference the Teams executable name and path. With each update, the Teams executable path changes. One approach for creating rules that account for the path change is to use Windows Defender Application Control (WDAC) application tagging policies. For an example, refer to the following guidance: [WDAC Application Tagging for Teams](https://aka.ms/new-teams-WDAC).
    - **Split Tunneling/Proxy:** If you're referencing a [split tunneling](/en-us/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel) and/or [proxy](/en-us/microsoft-365/enterprise/microsoft-365-network-connectivity-principles) configuration, ensure that any references include the Teams client executable and path.
    - **Quality of Service (QoS):**If your organization's set up QoS, refer to the following guidance related to Teams:
        - [Implement Quality of Service metrics in Microsoft Teams](qos-in-teams)
        - [Implement Quality of Service (QoS) in Microsoft Teams clients](qos-in-teams-clients)
        - [Configure QoS settings in the Teams admin center](meetings-real-time-media-traffic)
- **Software blocks**: Any management software including [Antivirus](/en-us/microsoftteams/troubleshoot/teams-administration/include-exclude-teams-from-antivirus-dlp) or [AppLocker](applocker-in-teams) should include the Teams client. For third-party products, refer to the manufacturer's documentation.
- **Machine-wide deployment or multi-user devices**: Use [Microsoft 365 apps](teams-client-deploy-with-m365apps) or [teamsbootstrapper](teams-client-bulk-install) to deploy Teams machine-wide.
- **Make sure all users have Teams installed**: As Teams is deployed, track usage to validate that intended users and systems are updated via the [usage report for Teams client](teams-client-usage-report).

## Learn more

- [Upgrade to new Microsoft Teams with Microsoft 365 Apps](teams-client-deploy-with-m365apps)
- [Teams client for Mac - Overview and prerequisites](teams-client-mac-install-prerequisites)
- [Upgrade to Teams for Virtualized Desktop Infrastructure (VDI)](teams-client-vdi-requirements-deploy)