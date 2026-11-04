---
layout: Conceptual
title: Android versioning support for Teams devices - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/android-version-support
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: divank
ms.date: 2026-09-28T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-devices
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier2
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: Learn about the versions of the Android operating system and platform that are supported on Teams devices.
locale: en-us
document_id: c18a2b88-5ae0-6c4b-f161-ca92c6eb48f8
document_version_independent_id: c18a2b88-5ae0-6c4b-f161-ca92c6eb48f8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/android-version-support.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/android-version-support
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/android-version-support.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fb31aecf-df1e-071c-545d-934cb4d1fc23
---

# Android versioning support for Teams devices - Microsoft Teams | Microsoft Learn

You can learn about all of the Teams devices including Teams Rooms on Android, Teams panels, and Teams phones that run the Android operating system and which versions of Android are support on those specific devices.

## Certification overview

These are currently the available Certification Programs for Microsoft Teams devices on Android.

- Teams Phones, including conference phones and expansion modules (sidecar)
- Teams Rooms for Android, including touch consoles
- Teams panels

You can learn more about end of certification of Teams devices by visiting [Devices for Teams](/en-us/microsoftteams/devices/teams-ip-phones#end-of-certification-teams-devices) or [Microsoft Teams enabled devices](https://www.microsoft.com/microsoft-teams/across-devices/devices).

This article describes the product lifecycle of Microsoft Teams devices on Android, both Microsoft Teams devices applications and Android OS/OEM firmware support.

Microsoft support applies only to devices certified under one of the currently active Teams devices Certification Programs, from Original Equipment Manufacturer (OEM) accepted into any of the currently active Teams devices Certification Programs.

Original Equipment Manufacturers (OEM) are responsible for maintaining Microsoft Teams Devices certified status for each of their devices. Decision to not recertify, end of sale, or end of life of a specific device is an Original Equipment Manufacturer (OEM) decision. Customers are encouraged to contact the Original Equipment Manufacturer (OEM) for any questions about the lifecycle of a specific device.

You can learn more about end of certification of Teams devices by visiting [Devices for Teams](/en-us/microsoftteams/devices/teams-ip-phones#end-of-certification-teams-devices).

## Microsoft Teams Devices Applications Support

Microsoft Teams applications running on Android Teams devices and other Microsoft applications present on Teams on Android devices (as needed for authentication and device management) are governed by [Modern Lifecycle Policy](/en-us/lifecycle/policies/modern).

Microsoft applications are updated from Microsoft Teams Admin Center (TAC) or Teams Rooms Pro management portal (PMP), where device admins can configure policies for automatic or manual updates of these applications. Microsoft recommends customers to use auto-update setting to ensure Teams on Android devices stays up to date and functional. In cases where customers may need to set up manual updates, customers must make sure to stay current on Microsoft applications. Microsoft tests and supports the latest and latest-1 versions of Microsoft applications on the device. Keeping devices on older versions of the application can leave your Teams devices unstable and unusable.

Teams on Android devices customers should follow Modern Lifecycle Policy guidelines to receive Teams device applications on Android device support from Microsoft. While the latest and latest-1 versions of Microsoft applications on the device, the support structure for Teams Rooms devices applications is dynamic and depends on the availability of the latest version. When you encounter a code defect in a version of the application that's not the latest, you must install the latest version to receive a fix.

All Teams devices applications Android releases are listed at [What's new in Microsoft Teams devices](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2).

Important

If you are installing Teams devices applications from a device Original Equipment Manufacturers (OEM) provided service, make sure to validate that Microsoft applications provided by the device OEMs are listed and supported in Teams Admin Center, Teams Rooms Pro management portal or listed at [Devices for Teams](/en-us/microsoftteams/devices/teams-ip-phones#product-release-information-for-teams-phones) or [Teams Rooms on Android app and firmware versions](/en-us/microsoftteams/rooms/android-app-firmware).

## Android OS and OEM firmware support

Microsoft Teams devices on Android are appliances that come packaged with Android operating system owned and managed by hardware Original Equipment Manufacturers (OEM) partners and is developed using Android Open Source Project. Android operating system and firmware updates are provided by hardware Original Equipment Manufacturers (OEM) to Microsoft for certification. Those updates are then distributed through Microsoft Teams Admin Center (TAC) or Teams Rooms Pro management portal (PMP).

Android operating system and firmware updates installed through device hardware Original Equipment Manufacturers (OEM) services must be certified by Microsoft. They must be available in Teams Admin Center (TAC) or Teams Rooms Pro management portal (PMP) for devices to be eligible for support for defects found with Microsoft applications on the device.

The following Android operating systems versions are supported on Teams devices.

Note

The certification end date for Android 10 and Android 11 based devices has been extended from September 3, 2025, to September 3, 2026. This extension is designed to offer greater flexibility and peace of mind, ensuring you have ample time to manage required firmware and application updates. The Microsoft support end dates will remain as September 3, 2027. For Android 12 and Android 13 based devices, the certification end date has been extended from October 6, 2026, to August 15, 2028, and the Microsoft support end date has been extended to August 15, 2030.

| **Android OS version** | **Microsoft Teams Certification End Date** | **Microsoft Support End Date** |
| --- | --- | --- |
| Android 9 | August 5, 2023 | August 5, 2025 |
| Android 10 | September 3, 2026 | September 3, 2027 |
| Android 11 | September 3, 2026 | September 3, 2027 |
| Android 12 | August 15, 2028 | August 15, 2030 |
| Android 13 | August 15, 2028 | August 15, 2030 |
| Android 14 | October 4, 2028 | October 4, 2030 |
| Android 15 | October 15, 2029 | October 15, 2031 |
| Android 17 | June 16, 2031 | June 16, 2033 |