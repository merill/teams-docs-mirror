---
layout: Conceptual
title: Microsoft Teams Rooms licenses - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-licensing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: sohailta
ms.date: 2026-08-14T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Learn about and compare the available licenses for different types of calling and meeting features in Microsoft Teams Rooms.
locale: en-us
document_id: a2070d20-21d1-c8bb-bbb4-697083efcd20
document_version_independent_id: f4998e3c-74ed-4a2b-fe7c-c55044b9a6b4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-licensing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-licensing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-licensing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ed76c8d8-94bc-5e2c-1334-674b077e7754
---

# Microsoft Teams Rooms licenses - Microsoft Teams | Microsoft Learn

Microsoft offers two licenses for Teams Rooms systems that participate in Teams meetings and calls:

- **Microsoft Teams Rooms Pro** delivers enhanced in-room meeting experiences like intelligent audio and video, front row and large galleries, and dual screen support. The Teams Rooms Pro license also provides advanced management features like remote device management, conditional access policies, and detailed device analytics.

    Teams Rooms Pro is a great fit for medium and enterprise organizations, as well as smaller organizations with larger room counts or more advanced needs. Teams Rooms Pro licenses can be used to license both certified Teams Rooms systems and Teams Panels.
- **Microsoft Teams Rooms Basic** provides core meeting experiences to organizations that purchase a certified Microsoft Teams Rooms system, at no additional cost. The Teams Rooms Basic license includes scheduling, joining meetings, content sharing, and collaborative white boarding, as well as basic security and management capabilities out-of-the-box.
- A Teams Rooms Basic license can be used to license a single certified Teams Rooms system in a room. If you want to log into more than one Teams Rooms system in a room using the same resource account, you need to use a Teams Rooms Pro license.
- You can assign up to 25 Microsoft Teams Rooms Basic licenses to Teams Rooms systems in your organization. If you need to license more than 25 Teams Rooms systems, those additional licenses need to be Teams Rooms Pro licenses. Teams Rooms Basic licenses can be used to license Teams Rooms systems only and not Teams Panels.

A Teams Rooms system can be one of the following:

- A Teams Rooms on Windows compute module and attached touch console
- A Teams Rooms on Android device and touch console connected via either an IP-based or USB connection
- A Surface Hub

The remote administration tasks you perform on a Teams Rooms system or device in the Teams admin center depend on the license that's assigned the system or device. For more information, see [Microsoft Teams Rooms license overview in Teams admin center](admin-center-license-overview).

Important

A shared meeting device is a device used by users in a shared location to participate in Microsoft Teams meetings. A device used as a shared meeting device requires a Teams Rooms license whether it participates by signing in to a Microsoft Teams client, by anonymous join, or by authenticating a Microsoft 365 identity (such as a resource account) through Azure Communication Services or another integration framework. Enterprise per user Microsoft 365 suite licenses aren't authorized for use on shared meeting devices in any of these configurations. Direct Guest Join (DGJ) and Cloud Video Interoperability (CVI) are designed to enable shared meeting devices to join Teams meetings without requiring a separate Teams meeting license for the joining device or endpoint when implemented through Microsoft-supported interoperability experiences and configurations.

Also, Microsoft Teams Shared Space licenses aren't supported on and won't work with Teams Rooms devices. Teams Rooms devices should only be assigned Teams Rooms Basic or Teams Rooms Pro licenses (Teams Rooms legacy licenses are also valid).

## Teams Rooms license service plan comparison

The following table shows the services included in each Teams Rooms license.

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Maximum number of licenses** | 25 | Unlimited |
| **Microsoft Teams** | ✔ | ✔ |
| **Microsoft Teams Rooms Pro Management** |  | ✔ |
| **Audio Conferencing^1^** | ✔ | ✔ |
| **Whiteboard** | ✔ | ✔ |
| **Teams Phone** **Standard** |  | ✔ |
| **Microsoft Intune^2^** |  | ✔ |
| **Microsoft Entra ID P1** |  | ✔ |
| **Microsoft Defender for Endpoint Plan 2** |  | ✔ |
| **Skype for Business Plan 2^3^** |  | ✔ |
| **Geographic availability** | Worldwide | Worldwide |
| **Segment availability** | Commercial, Education, Non-Pro | Commercial, Education, Non-Profit, GCC, GCC-High, DoD |
| **Channel availability** | Web Direct | EA, EAS, EES, CSP, Web Direct, NCE - Customer led, NCE - Partner led |

^1^ To verify service availability, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). [Communication Credits](../what-are-communications-credits) may apply for additional services, such as toll-free, international minutes for domestic plans, and so on. You can disable these features to avoid additional billing. [Conference Phones with Meeting Interface](/en-us/microsoftteams/devices/teams-android-devices-user-interface) requires Microsoft Teams Rooms Pro License.

^2^ Microsoft Intune Plan 1 and Plan 2.

^3^ Included to enable certain legacy authentication methods. As of October 1, 2023 Microsoft Teams Rooms will no longer supports connections to Skype for Business server.

^4^ You need to add and assign a free Teams Rooms Basic license for each device via the Microsoft 365 admin center. You need to provide payment details, although no charge will be made for Teams Rooms Basic licenses. see [subscriptions and billing documentation](/en-us/microsoft-365/commerce) for details.

## Switching from Teams Rooms Standard and Teams Rooms Premium

If your organization has meeting devices that use the Teams Rooms Standard or Teams Rooms Premium legacy licenses, you can continue using those licenses until their expiration date. Upon the expiration date of your existing legacy licenses, we recommend that you transition to the Teams Rooms Pro license. The meeting and management features^\*^ available in both of the legacy licenses have been combined in the Teams Rooms Pro license.

When transitioning between license types, we recommend having overlap with your new license and your old licenses. This will allow you to assign the new license to your existing resource accounts, allow 24 hours, and then remove the legacy license from the accounts. Following this staggered process ensures no interruption in service.

Important

Legacy licenses won't automatically transition to the new licenses. Upon expiration of a legacy license, you'll need to purchase a new Teams Rooms Pro (recommended) or Teams Rooms Basic license. Teams Rooms Pro licenses can be purchased through the Microsoft 365 admin center or your preferred sales channel. Teams Rooms Basic licenses can only be purchased through the Microsoft 365 admin center.

If your organization has an Enterprise Agreement, you can continue using your existing legacy licenses until your next renewal period. You can also continue to reserve additional legacy licenses until your next renewal period. For more information, contact your Microsoft representative.

For information about legacy licenses, see [Microsoft Teams Rooms legacy licenses](rooms-legacy-licensing).

^\*^Microsoft Service engineers no longer serve as intermediaries to incident response as of October 1, 2022.

Tip

As a companion to this article, we recommend using the [Microsoft Teams Rooms automated setup guide](https://go.microsoft.com/fwlink/?linkid=2224463) when signed in to the Microsoft 365 admin center. This guide will customize your experience based on your environment. To review best practices without signing in and activating automated setup features, go to the [Microsoft 365 setup portal](https://go.microsoft.com/fwlink/?linkid=2223356).

## Teams Rooms Basic and Teams Rooms Pro feature comparison

The following tables compare the Teams Rooms Basic and Teams Rooms Pro licenses and show what features are available with each. If a feature isn't available for a license, that feature can't be used on Teams Rooms devices that have been assigned that license. To use a feature on a Teams Rooms device, assign the license in which that feature is available to that device.

### Meeting join

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Join Teams meetings with 1-touch, proximity, and meeting ID** | ✔ | ✔ |
| **Start ad hoc meetings from the room** | ✔ | ✔ |
| **Direct Guest Join for Zoom and Webex meetings** | ✔ | ✔ |
| **Join meetings across Teams clouds** |  | ✔ |
| **Room check-in with Teams Panel** |  | ✔ |
| **Coordinated meeting** |  | ✔ |

### Share and collaborate

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Share and view all Teams content types** | ✔ | ✔ |
| **Share whiteboard with Content Capture Camera** |  | ✔ |

### Meeting engagement

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Teams video gallery with multiple layout options** | ✔ | ✔ |
| **Meeting chat** |  | ✔ |
| **Front row** |  | ✔ |
| **Large gallery (up to 50 videos)** |  | ✔ |
| **Dual screen support** |  | ✔ |
| **Show meeting names** |  | ✔ |

### Calling

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Make and receive peer to peer and group calls** | ✔ | ✔ |
| **Microsoft 365 Phone System** |  | ✔ |
| **End-to-end call encryption** |  | ✔ |

### Intelligent audio and video

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Support for speaker identification** |  | ✔ |
| **Multi-camera support** |  | ✔ |
| **Panoramic room view** |  | ✔ |
| **AI noise suppression** |  | ✔ |
| **People counting** |  | ✔ |

### Security and compliance

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Secure operating system** | ✔ | ✔ |
| **System level security (Secure boot, Assigned Access mode, etc.)** | ✔ | ✔ |
| **Microsoft Entra Conditional Access policies** |  | ✔ |

### Device management

| - | Microsoft Teams Rooms Basic | Microsoft Teams Rooms Pro |
| --- | --- | --- |
| **Pro Management Portal enrollment and inventory** | ✔ | ✔ |
| **Automatic software updates** | ✔ | ✔ |
| **Detailed system and configuration information** |  | ✔ |
| **Peripheral health management** |  | ✔ |
| **Remote configuration** |  | ✔ |
| **Custom backgrounds set up and management** |  | ✔ |
| **Device history and activity** |  | ✔ |
| **ITSM integration** |  | ✔ |
| **Custom health alerts** |  | ✔ |
| **Device analytics** |  | ✔ |

## Pro Management Portal Licensing

### License Type Overview

The Pro Management Portal's license type offer a clear and comprehensive summary of all devices licensing status. To access the licensing information:

1. Use your credentials to log into the Pro Management Portal.
2. Go to **Rooms** and **Inventory** views.
3. In both views, locate the **License Type** column to see device licensing status.

### Inventory View

In the Inventory view, devices are categorized into:

- **Pro**: Devices with pro licenses.
- **Premium**: Devices with premium licenses.
- **Basic**: Devices with basic licenses.
- **Standard**: Devices with standard licenses.
- **Syncing**: For new devices, the license information will appear 24 hours after room reboot due to syncing.
- **Unlicensed**: Devices lacking Pro, Premium, Basic, or Standard licenses.

### Rooms View

In the Rooms view, you'll find:

- **Pro**: Devices with Pro licenses.
- **Premium**: Devices with Premium licenses.
- **Basic**: Devices with basic licenses.
- **Standard**: Devices with standard licenses.
- **Syncing**: For new devices, the license information will appear 24 hours after room reboot due to syncing.
- **Unlicensed**: Devices lacking Pro, Premium, Basic, or Standard licenses.

Important

- Starting October 2, 2023 all devices without Pro or Premium licenses assigned to them will lose access to the pro management capabilities until valid licenses are assigned to them.
- When changing the account of the device, please ensure that the new account has the valid license to avoid any interruption with the device. The 30 day grace period will not be applying when using an expired account to enroll new devices or changing account on current devices.

### Troubleshooting licensing status:

If you encounter devices showing an incorrect "unlicensed" status even though they possess the proper licenses, this can result from account sign-out or improper sign-in of your devices. To resolve these issues, follow [here](/en-us/microsoftteams/troubleshoot/teams-rooms-and-devices/teams-rooms-resource-account-sign-in-issues) that outline how to sign in properly.

Note

If you switch from a legacy license such as Teams Rooms Standard or Teams Rooms Premium to a new license such as Teams Rooms Basic or Pro, it can take up to 48 hours for those licenses to become active.

## Assigning additional licenses:

Teams Rooms devices managed by central IT should only be assigned the following licenses: Microsoft Teams Rooms Pro, Microsoft Teams Rooms Basic, and any additional licenses required for calling (such as calling plans) or enhanced security. No other licenses should be applied.

In exceptional cases where an executive uses a device to conduct meetings and access their personal calendar, it is permissible—though not recommended—to sign in with the executive’s user account, provided that the account also holds a valid Microsoft Teams Rooms Pro license. The account must meet the device’s authentication requirements appropriate for shared device usage. Note that signing in with a user account does **not** provide a personal device experience on the Teams Rooms device.

IT administrators should carefully evaluate this scenario to ensure compliance with company security policies before granting such exceptions. Because Teams Rooms devices automatically sign in and provide access to meeting and calling functions, we strongly recommend implementing physical security measures to prevent unauthorized use of executive devices.

Teams Rooms Pro and Teams Rooms Basic licenses are intended for a single room only. Using the same account across multiple devices that do not belong to the same room violates the license terms of use.

Important

- Avoid assigning Microsoft OneDrive for Business licenses to a Teams rooms account if the resource account is IT-managed. This can prevent user content, like recordings or transcripts, from being saved on the room's OneDrive, ensuring better content management.