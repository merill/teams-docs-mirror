---
layout: Conceptual
title: Teams Progressive Web Apps (PWAs) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-progressive-web-apps
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Progressive Web Apps (PWAs) allow sites like Teams on the web to offer more desktop capabilities that are typically unavailable to websites.
author: officedocspr5
ms.author: odocspr
manager: jacktremper
audience: admin
displayType: one-column
ms.date: 2026-03-27T00:00:00.0000000Z
ms.reviewer: 
ms.service: msteams
ms.subservice: teams-apps
ms.topic: tutorial
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- tier2
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-mar2020
locale: en-us
document_id: 24101ab0-2fed-ccc0-6849-893da4041dcc
document_version_independent_id: 24101ab0-2fed-ccc0-6849-893da4041dcc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-progressive-web-apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-progressive-web-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-progressive-web-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/7ebba99b-05c3-4387-8883-f7bbf6632cb8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/006ab567-b18c-4cf1-9a25-c24daa46ede1
platformId: f0c381bd-0f88-fa53-8486-186f264cc7ec
---

# Teams Progressive Web Apps (PWAs) - Microsoft Teams | Microsoft Learn

A Progressive Web App (PWA) is a type of web application that can be installed on a device and provides a user experience similar to a native desktop app. PWAs allow sites like Teams on the web to offer more desktop capabilities that are typically unavailable to websites.

PWAs are hosted by Microsoft Edge and Chrome browsers but look and feel like a native app. At their core, PWAs are still websites and operate within the same browser sandbox environment, offering the security and control many administrators require for their users.

## Microsoft Teams on the web as a PWA

Microsoft Teams on the web can be installed as a PWA on Edge or Chrome browsers. This allows users who can't install the Microsoft Teams desktop client or prefer using web apps to still have a seamless Teams desktop experience.

## Benefits of using Teams PWA

- **Automatic start**: Can automatically start on login for quick access.
- **Easy access**: Can be pinned to the taskbar or dock for easy access.
- **Consistent experience**: Provides a more consistent experience for web users who also use Teams desktop clients on other devices.

## Deploying Teams PWA using group policies

Administrators can deploy Microsoft Teams on the web PWA using group policies in Edge and Chrome browsers. There are two relevant policies:

- **WebAppInstallForceList**: This policy allows administrators to force-install specific web apps, including PWAs. Users are unable to uninstall PWAs in this policy, and removing the policy causes the PWA to be uninstalled.
- **WebAppSettings**: This policy provides more settings for managing web apps.

For detailed instructions on configuring these policies, see the following documentation:

- [Edge group policy documentation](/en-us/deployedge/microsoft-edge-policies)
- [Chrome group policy documentation](https://support.google.com/chrome/a/answer/187202)

## Recommended group policies for PWA users

To ensure a smooth experience for PWA users and to avoid common permission issues, it's also recommended that administrators set the following group policies:

- **SleepingTabsBlockedForUrls**: Prevents tabs with Teams on the web from going to sleep.
- **NotificationsAllowedForURLs**: Automatically allows notifications for Teams on the web.
- **ScreenCaptureAllowedByOrigins**: Allows screen capture for Teams on the web.
- **AudioCaptureAllowedUrls**: Allows audio capture for Teams on the web.
- **VideoCaptureAllowedUrls**: Allows video capture for specified URLs.
- **CookiesAllowedForUrls**: Unblocks specific cookies for Teams on the web, including third-party cookies used in line-of-business (LOB) apps.

Setting these policies helps users avoid repeatedly approving common permissions or accidentally blocking functionalities needed for Teams on the web.