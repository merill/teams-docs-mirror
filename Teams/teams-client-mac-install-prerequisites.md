---
layout: Conceptual
title: Deploy the Microsoft Teams client for Mac - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-mac-install-prerequisites
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
ms.date: 2025-06-30T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: smylavarapu
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about deploying the Microsoft Teams desktop client for the Mac.
ms.localizationpriority: medium
locale: en-us
document_id: 4a3ddf0e-9cf4-3186-599d-0f1ce15b3eaf
document_version_independent_id: 4a3ddf0e-9cf4-3186-599d-0f1ce15b3eaf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-mac-install-prerequisites.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-mac-install-prerequisites
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-mac-install-prerequisites.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 38e27f8b-95e7-1fea-064d-738daf584d9d
---

# Deploy the Microsoft Teams client for Mac - Microsoft Teams | Microsoft Learn

The Teams for Mac client is designed with performance in mind, providing a fast, simple, and flexible experience. The Teams client installs and loads quickly, letting you launch the app and join meetings with ease, giving you more time to focus on the business tasks.

The Teams client ensures more efficient use of device resources. Whether you have users on multiple accounts or tenants, Teams helps eliminate the silos and bring them together in one place, giving them more extensibility and scale.

## Prerequisites

### Minimum Mac and Teams versions

For information on deploying the Teams client on Mac, see [Teams client system requirements](teams-client-system-requirements).

### Turn on System Notification

After you install the client, if users don't choose to **Allow Notifications** with the initial macOS Alert about notifications settings, then users must turn on the **Allow Notifications** from system settings.

#### System notification for Monterey OS

1. Open macOS System Preferences.
2. Go to **Notifications & Focus** and, under **Notifications**, select Microsoft Teams.
3. Switch the **Allow notifications** toggle to turn on notifications.

![Teams for Mac notifications macOS Monterey.](media/new-teams-mac-notifications-monterey.png)

##### System notification for macOS Ventura and Sonoma

1. Open macOS System Preferences.
2. Go to **Notifications** and, under **App Notifications**, select Microsoft Teams.
3. Switch the **Allow notifications** toggle to turn on notifications.

![Teams for Mac notifications macOS Ventura Sonoma.](media/new-teams-mac-notifications.png)

### Turn on Screen Sharing

Users can enable screen sharing for sharing content on calls and in meetings using the regular in-app flow when they first try to screen share. This action requires that they restart Teams. The user needs to drop from the meeting. Alternatively, users can turn on permissions for screen recording under system settings.

#### Screen sharing for Monterey OS

1. Open macOS System Preferences.
2. Go to Security & Privacy &gt; Privacy tab &gt; Screen Recording.
3. Select the **+** sign to add Microsoft Teams to allow recording content of your screen.

![Teams Mac security page.](media/new-teams-mac-security.png)

##### Screen sharing for macOS Ventura and Sonoma

1. Go to Privacy & Security &gt; Screen Recording.
2. Switch the toggle for Microsoft Teams to Allow recording of the content of your screen.

![Teams Mac screen recording page.](media/new-teams-mac-screen-recording.png)

## How to uninstall the Teams client

You can uninstall the Teams client just like any other Mac app.

### How to clear the cache

1. Command + Space and enter Terminal.
2. rm -rf ~/Library/Group Containers/UBF8T346G9.com.microsoft.teams
3. rm -rf ~/Library/Containers/com.microsoft.teams2