---
layout: Conceptual
title: Teams updates - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-update
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
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: 
ms.date: 2026-07-20T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
description: This article outlines the process behind updating the Microsoft Teams desktop client.
ms.localizationpriority: Medium
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 442f8c6b-95ba-a09e-639d-b9dd141198f6
document_version_independent_id: 442f8c6b-95ba-a09e-639d-b9dd141198f6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-update.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-update
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-update.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 46ec0059-6d1b-07fb-011f-9d885955fe59
---

# Teams updates - Microsoft Teams | Microsoft Learn

Keeping Microsoft Teams up-to-date is crucial for maximizing productivity and staying connected. Regular updates mean you have access to the latest features, security enhancements, and bug fixes. Updating not only improves the overall performance and reliability of the application, it also helps you and your team collaborate more efficiently. By staying current with updates, you reduce the risk of having issues and ensure compatibility with other tools, making it easier to focus on your work without interruptions.

## Servicing agreement

As part of a modern online service, the Teams client is updated twice a month. The client automatically installs updates when they become available to that client. Because we stagger the availability of updates worldwide using [safe deployment practices](/en-us/devops/operate/safe-deployment-practices), some clients in your organization might receive new updates before others. Because the [Modern Lifecycle Policy](/en-us/lifecycle/policies/modern) governs Teams, users should remain on the most up-to-date version of the desktop client. Auto-updates ensure that users have the latest capabilities, performance enhancements, security, and service reliability.

To identify when desktop clients fall out of date, an in-app alert displays if the user's current version is between one and three months old and if new version's available. This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so. Users on Teams desktop clients that are more than three months old see a blocking page. This page gives the options to update now, reach out to their IT admin, or continue to Teams on the web.

For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** &gt; **What's new** in the client.

## Teams client updates timeline

New updates for the Teams desktop client are released twice a month after thorough internal testing and validation through our Technology Adoption Program (TAP). The desktop client is rolled out to customers gradually.

Important

When there's a critical update, Teams bypasses the regular schedule and releases the update immediately.

Other factors that help your client to stay up-to-date:

- Operating System (OS):
    - Meets the minimum OS requirements for Teams.
    - Your OS version is up-to-date (non-LTSC update channel) and still under support.
    - Your OS has the latest patches installed.
- Webview2:
    - Webview2 updates automatically on Windows, you should make sure it isn't blocked. Teams updates Webview2 on macOS.
    - Webview2 must be a supported version (latest version).

For more information, see [Teams client system requirements](teams-client-system-requirements).

## Updating Teams on Windows devices

- **Update checks**: Teams applications on both Windows and Mac devices check for updates when the application starts up and every few hours in the background, whether the application is running or not. A user must be signed into the machine for updates to happen.
- **Download**: Updates are downloaded based on availability and staged to the user session. By using Windows Delivery Optimization, only the delta that's different from the current installed version (the differential update) is downloaded.
- **Restart**: Restarting the application is required for the update to take effect.
- **Manual**: The update starts automatically when the application is idle on Windows clients. Selecting the **Restart** button next to the ellipsis (...) button in the client allows a user to restart sooner.

### Issues with Teams client updates in Windows and best practices

- Windows delivery optimization service is disabled or configured with unsupported mode (100). This configuration blocks the updater's ability to download the update payload.
    - There's a Windows Delivery Optimization service configuration requirement: [Teams client system requirements](teams-client-system-requirements#additional-information).
    - Enabling the Peer to Peer capability isn't required.
- A user modifies Team's app package. The MSIX packages are installed machine-wide under the Program Files directory. The Windows OS tightly controls and monitors the file ACLs. If a user modifies or changes the file ACLs, the system deems the application to be in a corrupted state. This circumstance leads to unexpected behaviors such as crashing, unexpected app termination, and a failure to update.
    - It's essential to make sure the files under the installation directory (%programfiles%\windowsapps) aren't altered in any way.
- Network settings that block Team's CDN endpoints cause delivery optimization service failures and a failure to update the app.
    - You must allow Microsoft M365 endpoints in network configuration. For more information, see [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges).
    - Avoid SSL inspection on M365 endpoints. SSL inspection is known to cause high update download failure rate and retries.
- A device is running an out of support OS, or a Windows version that doesn't have the latest updates and patches can lower the success of Teams updates.
    - Windows 11 improves the Teams application update success rate and reliability as it has the most current installer.
    - Make sure you install all OS patches before deploying Teams on Windows 10 or Windows 11.

## Updating Teams on Mac devices

- The Teams desktop client updates itself using Microsoft AutoUpdate (MAU), similar to other Microsoft applications. Learn more about MAU at [Configuring Microsoft AutoUpdate (MAU) for Organization Specific Updates](/en-us/microsoft-365-apps/mac/mau-configure-organization-specific-updates).
- Teams uses default MAU Office channels for updates and a custom channel for Teams-specific scenarios. The post-installation script registers the app with MAU's default Office channel (Current, Preview, or Beta) to ensure Mau updates the app without running itself.
- When the update is downloaded while Teams is running, we use MAU's **Install On Clone** feature, to prepare the installation. Once a user quits the application, MAU moves the clone to the /Applications folder to finish updates. Teams for Mac doesn't automatically restart to apply updates. It always waits for user to take the action.
- Users can also select **Check for updates** from the Help menu bar item to manually check for updates. This action opens Microsoft AutoUpdate (MAU).

### How to configure MAU

- No special configuration is required if the MAU preferences are left at default values.
- If your organization employs managed MAU preferences, the Teams app preferences should look like this example:

```xml
<key>/Applications/Microsoft Teams.app</key>
    <dict>
      <key>Application ID</key>
      <string>TEAMS21</string>
    </dict>
```

Note

Your configuration may contain an LCID key with a value set to 1033. This value isn't used any longer, and you can delete it.

### Issues with Mac update and best practices

- Microsoft AutoUpdate (MAU) not being installed or being blocked on your device.
    - MAU is an integral part of Teams and included with the Teams installer. When Teams is first installed, MAU is also installed unless it's already present on the device. However, there are instances where firewalls deliberately remove or block MAU.
    - To see if you have MAU installed, select **Check for Updates** from the Help menu bar item. This selection should open the MAU user interface, but if MAU isn't installed, nothing happens.
    - To make sure that MAU is allowed to function correctly, we need to first check the MAU configuration. If the configuration is correct and MAU is installed, and it still doesn't work, it's likely being blocked. In that case, the user should contact their administrator.
- MAU is outdated.
    - Microsoft Teams needs MAU version 4.52.22101101 at a minimum, but we recommend you use version 4.73.24071426 or higher for crucial security updates. MAU self-updates, and a manual update shouldn't be required under the default settings.
- Your organization uses a custom MAU profile and the Teams portion isn't configured correctly.
    - As previously mentioned, Teams handles MAU registration autonomously within user preferences. There are instances when an organization deploys custom MAU preferences using an MDM management system. In such cases, the managed preferences take precedence. Occasionally, these settings might be incorrectly configured. Common issues include a complete lack of Teams configuration or configurations that reference the old name **Microsoft Teams (work or school).app**.

### How to troubleshoot a MAU configuration

- To troubleshoot MAU configuration issues, you first need to open the Terminal app and execute the following commands:

    - ` defaults read /Library/Managed\ Preferences/com.microsoft.autoupdate2`
    - `defaults read com.microsoft.autoupdate2`
- In the output, locate the "/Applications/Microsoft Teams.app". It should look like:

    - Basic:

```xml
Applications= {
      ...
      "/Applications/Microsoft Teams.app" =     {
        "Application ID" = TEAMS21;
    };
    ...
    }
```

- Custom channel:

```xml
Applications= {
      ...
      "/Applications/Microsoft Teams.app" =         {
      "Application ID" = TEAMS21;
      ChannelName = Custom;
      ManifestServer = "https://statics.teams.cdn.office.net/production-osx/24199.1700.3003.1785/";
      ManifestServerExpiryTime = "2024-08-02T08:40:06Z";
    };
    ...
    }
```

Note

Preferences in /Library/Managed\ Preferences/ take precedence. If you see an "Applications" entry there, focus solely on that output.

- If the "/Application/Microsoft Teams.app" path is absent, it indicates that the Teams registration is missing, and you need to reach out to your administrator to add the basic registration to the managed preferences profile.
- If the "/Application/Microsoft Teams.app" entry appears but is different from the examples, contact your administrator to resolve the managed preferences profile.

#### Common misconfigurations

| Issue | Example |
| --- | --- |
| Teams configuration with old name | "/Applications/Microsoft Teams **(work or school).app**"= {"Application ID" = **TEAMS21**;} |
| Serving multiple configurations of the same path but with different app IDs | "/Applications/**Microsoft Teams.app**" = {"Application ID" = **TEAMS10**;}"/Applications/**Microsoft Teams.app**" = {"Application ID" = **TEAMS21**;} |

#### Update issues caused by name mismatch

A special case might occur when the registration is correct, but your application is still called Microsoft Teams (work or school).app. This issue mostly impacts early adopters and dogfooders. In this situation, you have two options:

1. Manually download and install the [latest version of Teams](https://aka.ms/getteams). If you don't have permission to install software, contact an administrator to perform the installation. After the installation is done, you continue to receive updates automatically.
2. Add an additional registration for MAU preferences. Use the following registration to address the name mismatch:

```xml
/Applications/Microsoft Teams.app = {
    "Application ID" = TEAMS21;
}
/Applications/Microsoft Teams (work or school).app = {
    "Application ID" = TEAMS21;
}
/Applications/Microsoft Teams (work preview).app = {
    "Application ID" = TEAMS21;
}
```

## Updates to Teams on VDI

See [Install Teams on VDI](vdi-2).