---
layout: Conceptual
title: How to uninstall the classic Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-classic-client-uninstall
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.topic: install-set-up-deploy
ms.date: 2026-02-23T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Uninstalling classic Teams client from client machines. Take this action if the automatic uninstall doesn't work. This article also helps if an admin needs to do a manual removal after the end of availability for classic Teams client and the upgrade to new Teams client.
ms.localizationpriority: high
locale: en-us
document_id: 92fe55c7-8180-b137-73a7-59f232ef116d
document_version_independent_id: 92fe55c7-8180-b137-73a7-59f232ef116d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-classic-client-uninstall.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-classic-client-uninstall
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-classic-client-uninstall.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fb8b9379-63c4-9a4e-60d4-dc6ad74fc553
---

# How to uninstall the classic Teams client - Microsoft Teams | Microsoft Learn

After you install the new Teams client and setting the **New Teams Only** policy (or reaching the end of life period for classic Teams), there's an attempt to remove classic Teams client application after a period of time. Microsoft attempts this removal, but in some cases, due to permissions or other settings, the removal may fail. This article outlines the steps and considerations for IT administrators to uninstall the classic Teams client manually.

## Understanding Your Deployment Scenario

Before proceeding with the uninstallation, you should try to identify how classic Teams was deployed in your organization. The most common configurations are:

1. **User-Deployed or Per user Admin Deployment**:

    - Users, individually, or admins, on a per-user basis, installed classic Teams. This installation happened typically through the web, Microsoft Store, or admin tools. In **Add or Remove Programs**, you only see an entry for classic Teams.
    - **Action**: No immediate action required. classic Teams attempts to be automatically uninstalled some time after the new Teams installation.
2. **Commercial Version of Microsoft 365 Apps Installed**:

    - In **Start** &gt; **Settings** &gt; **Apps**, classic Teams and the Teams Machine-Wide Installer are both present.
    - **Action**: No immediate action required. The new Teams installation replaces classic Teams, which is removed at a later point. Microsoft 365 Apps attempts to uninstall the Teams Machine-Wide Installer at a later point.
3. **Admin-Deployed Teams Machine-Wide Installer Without Microsoft 365 Apps**:

    - Classic Teams was deployed machine-wide by an admin without using Microsoft 365 Apps (typically by deploying the Teams Machine-Wide Installer directly).
    - **Action**: After new Teams is deployed, an attempt is made to remove classic Teams after a period of time. If Microsoft 365 Apps is present, after new Teams is deployed, an attempt to remove the Teams Machine-Wide Installer is made as well. Otherwise, admins must proactively uninstall the Teams Machine-Wide Installer using their existing deployment tools.

Note

If your organization has the **New Teams as default** setting, which allows users to switch back, the uninstallation of classic Teams removes the switch option.

## Uninstalling classic Teams

Important

For customers who uninstall classic Teams themselves and experience a Teams meeting add-on issue, there are troubleshooting steps available here: [Teams meeting add-in missing from Outlook and new Teams](/en-us/microsoftteams/troubleshoot/meetings/teams-meeting-add-in-missing).

### For User-Deployed or Per-user Admin Deployments

These users don't see the "Teams Machine-Wide Installer" in their system. As the **New Teams Only** policy rolls out, classic Teams is automatically uninstalled some time after the new Teams installation. No further action is required unless users aren't signed in for an extended period. In those cases, make sure that new Teams is deployed machine-wide to prevent users from being left without a Teams installation.

### For Commercial Version of Microsoft 365 Apps

The new Teams installation automatically uninstalls the classic Teams app. Microsoft 365 Apps removes the Teams Machine-Wide Installer in a future update. You should make sure that admin configuration isn't blocking the new Teams installation.

### For Admin-Deployed Teams Machine-Wide Installer Without Microsoft 365 Apps

Caution

Before proceeding, ensure new Teams is deployed machine-wide using the Microsoft 365 apps version or through the [Bulk upgrade to the new Microsoft Teams client](teams-client-bulk-install) option, or users may be left without a Teams client.

Admins should use their existing deployment tools to uninstall the Teams Machine-Wide Installer. This action triggers the uninstallation of classic Teams for each user as they sign in.

### An example uninstall using Intune on Windows

To uninstall an application across all devices using Intune on Windows, you can follow these steps: 

1. Sign in to the Microsoft Endpoint Manager admin center https://endpoint.microsoft.com/.
2. Go to Devices &gt; Windows &gt; Windows Apps.
3. Select the **Add** button and then select **Windows app (Win32)**.
4. In the **Add app** wizard, select **App package file** and upload the .intunewin file for the application you want to uninstall.
5. In the **Detection rules** section, select **Manually configure detection rules**.
6. In the **Detection rules** section, select the **Add** button and select **File**.
7. In the **File** section, enter the path and file name of the uninstaller for the application you want to uninstall.
8. In the **Uninstall command**section, enter the command to run the uninstaller silently. For example, if the uninstaller is "uninstall.exe" and the silent switch is "/quiet", the command would be:
    - 64-bit: "MsiExec.exe -x {731F6BAA-A986-45A4-8936-7C3AAAAA760B} /quiet"
    - 32-bit: "MsiExec.exe -x {39AF0813-FA7B-4860-ADBE-93B9B214B914} /quiet"

You can learn more at [Uninstall an app with Intune for Windows](/en-us/mem/intune/apps/apps-add).

### Special Considerations for VDI Environments

- For **Persistent VDI** configurations, follow the steps for admin-deployed Teams Machine-Wide Installer without Microsoft 365 Apps.
- For **Non-Persistent VDI** configurations, admins must manage the uninstallation process according to their device configuration.

### Removing Classic Teams on macOS

To remove the classic Teams client from a macOS device, execute the following commands in the terminal:

```
# Remove classic Teams
sudo rm -rf /Applications/Microsoft\ Teams\ classic.app
# Remove classic Teams cache
rm -rf ~/Library/Application\ Support/Microsoft/Teams
# Remove Classic Teams preferences
defaults delete com.microsoft.teams
# Unload Classic Teams Updater Daemon
sudo launchctl bootout system /Library/LaunchDaemons/com.microsoft.teams.TeamsUpdaterDaemon.plist
# Remove Classic Teams Updater Daemon
sudo rm -f /Library/LaunchDaemons/com.microsoft.teams.TeamsUpdaterDaemon.plist
# Remove Classic Teams Updater log
sudo rm -rf /Library/Logs/Microsoft/Teams/updater.log
```

Make sure you have the necessary permissions to execute these commands. This process completely removes the classic Teams client and its associated file.

## FAQs

- **How do I know if users still have classic Teams?** Use your tenant dashboard or device management tools to scan for classic Teams and the Teams Machine-Wide Installer.
- **When is classic Teams removed automatically?** Classic Teams is uninstalled some time after the new Teams installation completes, and once users receive the new Teams policy settings. If the Teams Machine-Wide Installer is present, Microsoft 365 Apps can uninstall it for each user as they sign in.
- **How much network bandwidth is required for the new Teams update?** The initial update is approximately 150 MB, with subsequent updates ranging from 120-150 MB. This update is automatically downloaded and installed from the internet once per device (multi-user devices don't download the binaries for each user). An admin can also choose to do an offline installation using the [bulk installer](teams-client-bulk-install). The [MSIX app package updates](/en-us/windows/msix/desktop/managing-your-msix-deployment-update) article has more details.
- **How can I remove all copies of classic Teams from a multi-user device without each user signing in?** Manual deletion is possible but not recommended as it may leave residual files.
- **Are users notified of the uninstallation attempt?** No, the process is designed to be silent to minimize disruptions.
- **Are there any workarounds for the uninstallation timer?** No, this timer isn't configurable. Admins can use device management software, such as Intune, to directly uninstall classic Teams.