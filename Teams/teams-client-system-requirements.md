---
layout: Conceptual
title: System requirements for the Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-system-requirements
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.topic: article
ms.date: 2026-07-16T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: daro
search.appverid: MET150
f1.keywords:
- NOCSH
description: Information about the system requirements, minimum hardware requirements, for the Teams client, what customers need to be able to install and use the Teams client.
ms.localizationpriority: high
locale: en-us
document_id: 53978403-6544-5ef3-eb91-7586a0a74396
document_version_independent_id: 53978403-6544-5ef3-eb91-7586a0a74396
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-system-requirements.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-system-requirements
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-system-requirements.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 24759465-3c9e-4a3d-a79d-34e944fef046
---

# System requirements for the Teams client - Microsoft Teams | Microsoft Learn

Microsoft Teams can be installed on PCs, Macs, and mobile devices, and can also be accessed via a web browser. Most end users can start using Teams by [installing the client](https://www.microsoft.com/microsoft-teams/download-app). After they install the Teams client, all they need to do is sign in with their username and password.

The Teams client delivers up to two times faster app performance while using 50% less memory than previous Teams versions.

## Teams client for Windows PC desktop

| Component | Requirement |
| --- | --- |
| Computer and processor | Minimum 1.1 GHz or faster, two cores. **NOTE** For Intel processors, the maximum speed achieved using Intel Turbo Boost Technology (Max Turbo Frequency) must be considered. |
| Memory | 4.0 GB RAM. |
| Hard disk | 3.0 GB of available disk space. |
| Display | 1024 x 768 or higher resolution. |
| Graphics hardware | Graphics hardware acceleration requires DirectX 9 or later, with WDDM 2.0 or higher for Windows 10 (or WDDM 1.3 or higher for Windows 10 Fall Creators Update). |
| Operating system | Windows 10 version 10.0.19041 or higher (excluding Windows LTSC versions for Teams desktop app^1^). |
| Webview2 | Update to the most current version. |
| Video | USB 2.0 video camera. |
| Devices | Standard laptop camera, microphone, and speakers. |

^1^ The Teams desktop client doesn't support any version of Windows LTSC.

### Additional information

| Requirement | Version |
| --- | --- |
| Settings | Turn on the "Show Notification Banners" setting in **System &gt; Notifications &gt; Microsoft Teams** to receive Teams Notifications. |
| Delivery optimization (DO) | DO powers Teams automatic updates. [What is Delivery Optimization?](/en-us/windows/deployment/do/waas-delivery-optimization)Recommended settings: [Set up Delivery Optimization](/en-us/windows/deployment/do/waas-delivery-optimization-setup#recommended-delivery-optimization-settings)**Note:** Download Mode 100 (Bypass) isn't supported. |

### Required Microsoft 365 Apps Security Updates

| Channel | Version & Build |
| --- | --- |
| Semi-Annual Enterprise Channel | Version 2302 (Build 16130.20306) Version 2208 (Build 15601.20578) |
| Monthly Enterprise Channel | Version 2301 (Build 16026.20222) Version 2212 (Build 15928.20294) |
| Office LTSB | Version 2018 (Build 10396.20023) Version 2021 (Build 14332.20481) |

Learn more at [**Update History for Microsoft 365 Apps**](/en-us/officeupdates/update-history-microsoft365-apps-by-date#supported-versions).

## Teams client for macOS Desktop

| Component | Requirement |
| --- | --- |
| Computer and processor | Dual core processor. |
| Memory | 4.0 GB RAM. |
| Hard disk | 1.5 GB of available disk space. |
| Display | 1200 x 800 or higher resolution |
| Operating system | One of the three most recent versions of macOS. **NOTE** You can find information about the latest macOS versions, and how to upgrade your version of macOS [here](https://support.apple.com/HT201260). For example, when a new version of macOS is released, the new version and the two versions immediately preceding it become the supported versions. |
| Webview2 | Update to the most current version. |
| Video | Compatible webcam. |
| Voice | Compatible microphone and speakers, headset with microphone, or equivalent device. |

## Teams client for web

Teams for Web shares the same hardware requirements as the underlying operating system (Windows, macOS, and Linux) and is supported on the following desktop browsers:

| Browser | Supported versions | Operating systems |
| --- | --- | --- |
| Microsoft Edge | Latest three versions | Windows, macOS, Linux |
| Chrome | Latest three versions | Windows, macOS, Linux |
| Firefox | Latest three versions | Windows, macOS, Linux |
| Safari | Latest two versions | macOS |

The browser must be configured to allow third-party cookies for some third-party or line-of-business (LOB) apps to function properly.

Note

Teams for Web isn't supported in VDI environments, so performance and reliability may be negatively impacted if used in VDI. Teams for Web isn't supported on mobile browsers.

## Teams client on Linux

Linux users have access to Teams for Web and Teams as a progressive web app (PWA).

## Teams client in a Virtual Desktop Infrastructure (VDI) environment

See [Upgrade to Teams for Virtualized Desktop Infrastructure (VDI)](teams-client-vdi-requirements-deploy) for the requirements for running Teams in a virtualized environment.

## Teams client for mobile devices

You can continue using Teams on these mobile platforms:

- Android: Compatible with Android phones and tablets.

Support is limited to the last four major versions of Android. For example, when a new, major version of Android is released, the Android requirement is the new version and the three most recent versions that precede it.

- iOS: Compatible with iPhone, iPad, and iPod touch.

Support is limited to the two most recent major versions of iOS. For example, when a new, major version of iOS is released, the iOS requirement is the new version and the most recent version that preceded it.

## Additional user scenario hardware recommendations

While you can use Teams with the previously mentioned minimal hardware requirements, we recommend the following hardware system requirements for Teams user scenarios like Avatar, Teams Live Events, and so on.

| Teams user scenario | Hardware systems requirements (equivalent or higher) |
| --- | --- |
| Avatar/Mesh experience | 8 GB Ram or higherFour-core processor from 2018 or higher |
| Large meetings (10+ participants) | Four-core processor from 2018 or higher |
| Teams Live Events | Four-core processor from 2018 or higher |