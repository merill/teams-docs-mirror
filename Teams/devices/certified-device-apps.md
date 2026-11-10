---
layout: Conceptual
title: Release Notes for Teams Android Devices Management Apps - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/certified-device-apps
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: vapati
ms.date: 2026-10-29T00:00:00.0000000Z
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
description: Learn about the versions of Android-based management apps that are supported on Android-based Teams devices including the Teams admin agent app, the Intune app, and the Microsoft Authenticator app.
locale: en-us
document_id: 0831124d-8f14-ac97-1d1f-2ccf9e635322
document_version_independent_id: 0831124d-8f14-ac97-1d1f-2ccf9e635322
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/certified-device-apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/certified-device-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/certified-device-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 116e29d6-848d-5835-c1fe-ceac6e0ef644
---

# Release Notes for Teams Android Devices Management Apps - Microsoft Teams | Microsoft Learn

For Teams Android devices to function, there are several applications required for functionality. All required applications are included in bundled firmware from the original equipment manufacturer (OEM). As an OEM releases a new firmware, new versions of required applications are bundled in if available. The certified firmware list includes the details on the specific application versions bundled into an OEM firmware. Outside of firmware releases the applications can also be updated individually, for more information on updating your Teams devices remotely, see [Update Microsoft Teams devices remotely](/en-us/microsoftteams/devices/remote-update).

This article provides details about the releases of the following apps for Android-based Teams devices:

- Teams Admin Agent app
- Microsoft Intune app
- Authenticator app

For product release information about firmware and the Teams app, refer to the following articles:

- [Release notes for Microsoft Teams Rooms](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Android)
- [Release notes for Microsoft Teams phone and panels](/en-us/microsoftteams/devices/devices-release-notes)
- [Teams Rooms on Android Firmware](/en-us/microsoftteams/devices/certified-hardware-android?tabs=firmware)
- [Teams phone Firmware](/en-us/microsoftteams/devices/teams-phones-certified-hardware?tabs=firmware)
- [Teams panels Firmware](/en-us/microsoftteams/devices/teams-panels-certified-hardware?tabs=firmware)

# [Teams Admin Agent](#tab/Agent)
The following releases are supported versions of the Teams admin agent app:

| **Release date** | **App version** |
| --- | --- |
| Nov 2026 | 1.0.0.202610190119.product |
| October 2026 | 1.0.0.202610260205.product |
| September 2026 | 1.0.0.202609172331.product |
| September 2026 | 1.0.0.202608280411.product |
| July 2026 | 1.0.0.202607160723.product |
| June 2026 | 1.0.0.202606082157.product |
| April 2026 | 1.0.0.202604060507.product |
| December 2025 | 1.0.0.202511230136.product |
| October 2025 | 1.0.0.202507210031.product |
| May 2025 | 1.0.0.202505080136.product |
| February 2025 | 1.0.0.202412110504.product |
| October 2024 | 1.0.0.202407050618.product |

### 1.0.0.202610190119

**This release, also known as Admin Agent 901, is available for all Teams-certified devices in the all clouds. It includes the following updates:**

- Fixes an issue where Android 15 devices could fail to connect to the Pro Management Portal (PMP).
- Preparation for deprecating the device management experience in Teams Admin Center (TAC) which is targeted for deprecation in mid-November.
- Fixes provisioning issues affecting Android devices.
- Includes other miscellaneous bug fixes.

Warning

This update will be rolled out at an accelerated pace as the update includes critical fixes that enable Android 15 devices to establish connectivity with PMP.

Note

Because this update is being rolled out at an accelerated pace, admins may see a package publication date that appears to be backdated. This is a mandatory app update required to manage devices in PMP, therefore this update **cannot be paused**.

### 1.0.0.202610260205

**This hotfix release (also known as Admin Agent 875) is available for all Teams certified devices in Commercial and GCC clouds and contains the following updates:**

- Resolved an issue which impacted connectivity for GCC endpoints

Note

This update will be rolled out at an accelerated release cadence, the publish date may appear backdated to ensure an accelerated deployment. This update is mandatory for managing device in the Teams Pro Management Portal and cannot be paused. Only the devices online and manageable via PMP will get auto-updated with this update.

### 1.0.0.202609172331

**This release (also known as Admin Agent 870) is available for all Teams certified devices in Commercial, GCC, GCC-High, and DoD clouds and contains following updates:**

- Improvements to device health monitoring
- Improvements to on-device logging

Note

This update will be rolled out at an accelerated release cadence, the publish date may appear backdated to ensure an accelerated deployment. This update is mandatory for managing device in the Teams Pro Management Portal and cannot be paused. Only the devices online and manageable via PMP will get auto-updated with this update.

### 1.0.0.202608280411

**This release (also known as Admin Agent 865) is available for all Teams certified devices in the Commercial cloud and contains following updates:**

- Expanded support for Android device management in the Teams Pro Management Portal. Learn more about the transition in [Transitioning Teams Android Device Management](/en-us/microsoftteams/rooms/aboutunifieddevicemanagement-pmp1) and Message Center communication MC1227622.
- Bug fixes for device settings
- Improved health signals
- Critical bug fixes related to devices provisioning
- Other miscellaneous bug fixes

Note

This update **will not be released** to GCC/GCC-H/DoD clouds. For public cloud customers, this update will be rolled out at faster candance and admins may see the actual publish date of package backdated.

### 1.0.0.202607160723

**This release (also known as Admin agent 856) is available for all Teams certified devices in Commercial, GCC, GCC-High, and DoD clouds and contains following updates:**

- Expanded support for Android device management in the Teams Pro Management Portal. Learn more about the transition in [Transitioning Teams Android Device Management](/en-us/microsoftteams/rooms/aboutunifieddevicemanagement-pmp1) and Message Center communication MC1227622.
- Device [provisioning support for Android devices in PMP](/en-us/microsoftteams/rooms/provisionandroiddevicespromanagementportal)
- Support for additional settings for Android devices in PMP (Hotline, line keys etc.)
- Various bug fixes

Note

This update will be rolled out at an accelerated release cadence, the publish date may appear backdated to ensure an accelerated deployment. This update is mandatory for managing device in the Teams Pro Management Portal and cannot be paused.

### 1.0.0.202606082157

**This release (also called as Admin agent 830) is available for all Teams certified devices in the Commercial cloud and contains following updates:**

- Initial support for Android device management in the Teams Pro Management Portal. Learn more about the transition in [Transitioning Teams Android Device Management](/en-us/microsoftteams/rooms/aboutunifieddevicemanagement-pmp1) and Message Center communication MC1227622.
- Various bug fixes

Note

This version **will NOT be released** to Government cloud customers. All Government cloud customers will receive next version 856 (1.0.0.202607160723) as part of their tenant. For public cloud customers, this update will be rolled out at faster candance and admins may see the actual publish date of package backdated. Also, considering its a mandatory app update for managing your devices in PMP, this update can not be paused by customers.

### 1.0.0.202604060507

**This release is currently available for all Teams certified devices and contains following updates:**

- Resolved an issue to retrieve and display the correct device Wi-Fi MAC address for all Teams Android devices.

### 1.0.0.202511230136

**This release is currently available for all Teams certified devices and contains following updates:**

- Added support for zero touch attestation (with tenant) for new MDEP devices (with version MDEP.2025.15.4).
- Added support for application rollback for Android devices.
- Resolved an MDEP issue related to provisioning failures when using MAC ID + OTP.

### 1.0.0.202507210031

**This release is currently available for all Teams certified devices and contains following updates:**

- Added support for zero day updates for firmware and apps for out-of-box devices.
- Resolved an issue for government cloud customers.

### 1.0.0.202505080136

**This release is currently available for all Teams certified devices and contains following updates:**

- Resolved a critical security issue.

### 1.0.0.202412110504

**This release is currently available for all Teams certified devices and contains following updates:**

- Added support for partial configuration changes and two-way sync of settings between device management service and the device.
- Added support for the ability to carry out operations like updates or configuration changes in a nondisruptive manner.
- Added IP address support for some devices.

### 1.0.0.202407050618

**This release is currently available for all Teams certified devices and contains following updates:**

- Improvements to determine device health more appropriately with the help of more signals.
- Improvements for better management of configurations for devices.
- Bug fixes to improve admin agent overall update reliability.

# [Microsoft Intune](#tab/Intune)
The following are supported versions of the Microsoft Intune app:

| **Release date** | **App version** |
| --- | --- |
| October 2026 | 26.6.4 |
| August 2026 | 26.6.3 |
| August 2026 | 26.6.0 |
| June 2026 | 26.03.1 |
| June 2025 | 25.02.1 |

### 26.6.4

**This release is available for** **all Teams certified devices and contains following updates:**

- Telemetry optimizations and improvements to reduce writes.

### 26.6.3

**This release is available for** **all Teams certified devices and contains following updates:**

- Improved root detection for more accurate compliance evaluation.
- Improved diagnosability for better troubleshooting.

### 26.6.0

**This release is currently available for all Teams certified devices and contains following updates:**

**Diagnostics improvements**

- Added device launch telemetry to improve visibility into device health and reliability.
- Improved the readability of the on-device support/incident ID to make it easier to provide when working with support.

**Bug fixes and platform improvements**

- Fixed an issue that could cause devices to be incorrectly detected as rooted.
- Added an app-management permission required for AOSP devices.
- Updated underlying libraries to improve security and performance.
- Updated the app to target Android 16 (API 36.1).

### 26.03.1

**This release is currently available for all Teams certified devices and contains following updates:**

- Improved log upload reliability, along with client logging and service telemetry, for better diagnostics.
- Improved app download handling to reduce potential failures on Teams devices.
- Improved certificate installation behavior to avoid end-user prompts during the Entra WPJ hardware-backed certificate security rollout.
- Updated libraries for security and performance improvements.
- Increased the target SDK version to API 36.

### 25.02.1

**This release is currently available for all Teams certified devices and contains following updates:**

- Telemetry improvements for more efficient investigations.
- Customers using Conditional Access policies should first deploy the updated AOSP Agent to a small group of devices and confirm Conditional Access continues to work as expected, before deploying the updated AOSP Agent to your entire device fleet.

# [Authenticator](#tab/Authenticator)
The following are supported versions of the Authenticator app:

| **Release date** | **App version** |
| --- | --- |
| October 2026 | 6.2609.6407 |
| September 2026 | 6.2607.4685 |
| July 2026 | 6.2606.4246 |
| May 2026 | 6.2605.3066 |
| March 2026 | 6.2601.0189 |
| January 2026 | 6.2512.8111 |
| December 2025 | 6.2509.6046 |
| December 2024 | 6.2410.7268 |

### 6.2609.6407

**This release is available for all Teams certified devices and contains following updates.**

- Telemetry optimizations and improvements to reduce writes

### 6.2607.4685

**This release is available for all Teams certified devices and contains following updates.**

- Reliability and Device Health: Improved stability and reduced storage wear to help extend device life.
- Security Enhancements: Strengthened network protections and minimized sensitive logging.
- Improved diagnostics for better troubleshooting.

### 6.2606.4246

**This release is available for all Teams certified devices and contains following updates.**

- Enhanced resiliency to better handle delays during Resource Account provisioning.
- Latest Authenticator updates with additional improvements.

### 6.2605.3066

**This release is available for all Teams certified devices and contains following updates.**

- Resolved an issue that caused a time-out during Password-less Resource Account migration.

### 6.2601.0189

**This release is available for all Teams certified devices and contains following updates.**

- Added support for password-less resource accounts.

### 6.2512.8111

**This release is available for all Teams certified devices and contains following updates.**

- Added various improvements.

### 6.2509.6046

**This release is available for all Teams certified devices and contains following updates.**

- Support for configuration of user-interactive challenges with DCF authentication.
- Addressed issues around high CPU load and memory consumption.
- Client-side changes to support new security protocol by default.

### 6.2410.7268

**This release is available for all Teams certified devices and contains following updates.**

- Initial release

---