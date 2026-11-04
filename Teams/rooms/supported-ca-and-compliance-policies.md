---
layout: Conceptual
title: Supported Conditional Access and Intune device compliance policies for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/supported-ca-and-compliance-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: dimehta
ms.date: 2026-07-06T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
description: Learn about supported and recommended Conditional Access and Intune device compliance policies for Microsoft Teams Rooms.
locale: en-us
document_id: 3138c11c-ca60-4699-f2c6-af0edc2b89a0
document_version_independent_id: 3138c11c-ca60-4699-f2c6-af0edc2b89a0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/supported-ca-and-compliance-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/supported-ca-and-compliance-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/supported-ca-and-compliance-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: a44aa312-3b9a-bf0a-5964-c5c905a655a9
---

# Supported Conditional Access and Intune device compliance policies for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

This article provides supported Conditional Access and Intune device compliance policies for Microsoft Teams Rooms. For best practices and example policies, see [Conditional Access and Intune compliance best practices for Microsoft Teams Rooms](conditional-access-and-compliance-for-devices).

## Supported Conditional Access policies

The following list includes the supported Conditional Access policies for Teams Rooms on Windows and Android as well as Teams panels and phones.

Important

While configuring certain policies might be supported, they may lead to less than desired experiences on your devices, test, and confirm configurations function as intended before deploying at scale. For instance, using the sign-in frequency policy causes devices to periodically sign out and may not be desired. Likewise, configuring sign-in frequency on individual Microsoft 365 services can interrupt or stop the Teams Device sign in flow and isn't supported. Also, blocking Device Code Flow prevents using microsoft.com/devicelogin to remotely sign-in a Teams Android device.

| Assignment | Teams Rooms on Windows | Teams Rooms on Android / Teams phone / Teams Panels |
| --- | --- | --- |
| Users | Supported | Supported |
| Target Resources | Supported  For functionality, don't block access to: <br>- Office 365<br>- Office 365 SharePoint Online<br>- Microsoft Teams Services<br>- Microsoft Intune Enrollment<br>- Device Registration Service | Supported  For functionality, don't block access to: <br>- Office 365<br>- Office 365 SharePoint Online<br>- Microsoft Teams Services<br>- Microsoft Intune Enrollment<br>- Device Registration Service<br>- Microsoft 365 App Catalog Services<br>- Marketplace Extensions Runtime<br>- Office Voice Front Door |
| Network | Supported | Supported |
| **Conditions** |  |  |
| User risk | Supported | Supported |
| Sign-in risk | Supported | Supported |
| Insider risk | Not supported | Not supported |
| Device platforms | Supported | Supported |
| Locations | Supported | Supported |
| Client apps | Supported | Supported |
| Filter for devices | Supported | Supported |
| Authentication flows | Supported | Not supported *Don't block device code flow.* |
| **Grant** |  |  |
| Block access | Supported | Supported |
| Grant access | Supported | Supported |
| Require multifactor authentication | Not supported | Supported *To enable seamless sign-on, don't enforce this policy, use a different secondary authentication factor.* |
| Require authentication strength | Not supported | Not supported |
| Require device to be marked as compliant | Supported | Supported |
| Require Microsoft Entra hybrid joined device | Not supported | Not supported |
| Require approved client app | Not supported | Not supported |
| Require app protection policy | Not supported | Not supported |
| Require password change | Not supported | Not supported |
| Require risk mitigation | Not supported | Not supported |
| Terms of Use Acceptance | Not supported | Not supported |
| **Sessions** |  |  |
| Use app enforced restrictions | Not supported | Not supported |
| Use Conditional Access App Control | Not supported | Not supported |
| Sign-in frequency | Not supported | Not supported |
| Persistent browser session | Not supported | Not supported |
| Customize continuous access evaluation | Not supported *If you check the box, it must be set to Disable or you'll experience instability* | Not supported *If you check the box, it must be set to Disable or you'll experience instability* |
| Disable resiliency defaults | Not supported | Not supported |
| Require token protection for sign-in sessions (Preview) | Not supported | Not supported |

Note

Authentication strength including but not limited to, FIDO2 Security keys, isn't supported for use with Conditional Access policies that affect all Teams Devices.

## Supported device compliance policies

Microsoft Teams Rooms on Windows and Teams Rooms on Android support different device compliance policies.

# [Teams Rooms on Windows](#tab/mtr-w)
Supported device compliance settings and recommendations for their use with Teams Rooms on Windows.

| Policy | Availability | Notes |
| --- | --- | --- |
| [**Device health**](/en-us/mem/intune/protect/compliance-policy-create-windows#device-health) | -- | -- |
| Require BitLocker | Supported | Only use if BitLocker is enabled first. |
| Require Secure Boot to be enabled on the device | Supported | Secure Boot is a requirement for Teams Rooms. |
| Require code integrity | Supported | Code integrity is already a requirement for Teams Rooms. |
| [**Device Properties**](/en-us/mem/intune/protect/compliance-policy-create-windows#device-properties) -- |  |  |
| Operating System Version (minimum, maximum) | Not supported | Teams Rooms automatically will update to newer versions of Windows and setting values here could prevent successful sign-in after an OS update. |
| OS version for mobile devices (minimum, maximum) | Not supported |  |
| Valid operating system builds | Not supported |  |
| [**Configuration Manager Compliance**](/en-us/mem/intune/protect/compliance-policy-create-windows#device-properties) | -- | -- |
| Require device compliance from Configuration Manager | Supported |  |
| [**System security**](/en-us/mem/intune/protect/compliance-policy-create-windows#system-security) | -- | -- |
| All password policies | Not supported | Password policies can prevent the local Skype account from automatically signing in. |
| Require encryption of data storage on device. | Supported | Only use if BitLocker is enabled first. |
| Firewall | Supported | Firewall is already a requirement for Teams Rooms |
| Trusted Platform Module (TPM) | Supported | Trusted Platform Module (TPM) is already a requirement for Teams Rooms. |
| Antivirus | Supported | Antivirus (Windows Defender) is already a requirement for Teams Rooms. |
| Antispyware | Supported | Antispyware (Windows Defender) is already a requirement for Teams Rooms. |
| Microsoft Defender Anti-malware | Supported | Microsoft Defender Anti-malware is already a requirement for Teams Rooms. |
| Microsoft Defender Anti-malware minimum version | Not supported | Teams Rooms will automatically update this component so there's no need to set compliance policies. |
| Microsoft Defender Anti-malware security intelligence up-to-date | Supported | Validate that Microsoft Defender Anti-malware is already a requirement for Teams Rooms. |
| Real-time protection | Supported | Real-time protections are already a requirement for Teams Rooms. |
| [**Microsoft Defender for Endpoint**](/en-us/mem/intune/protect/compliance-policy-create-windows#microsoft-defender-for-endpoint) | -- | -- |
| Require the device to be at or under the machine risk score. | Supported |  |

# [Teams Rooms on Android](#tab/mtr-a)
Supported device compliance settings for Teams Rooms on Android devices enrolled with AOSP Device Management (AOSP DM).

| Policy | Availability | Notes |
| --- | --- | --- |
| [**Device Health**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#device-health) | -- | -- |
| Rooted devices | Supported |  |
| [**Device properties**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#device-properties) | -- | -- |
| Operating System Version (minimum, maximum) | Supported |  |
| Minimum security patch level | Supported |  |
| [**System security**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#system-security) | -- | -- |
| Require a password to unlock mobile devices | Not supported | Teams Devices don't support a password unlock. |
| Required password type | Not supported | Teams Devices don't support a password unlock. |
| Maximum minutes of inactivity before password is required | Not supported | Teams Devices don't support a password unlock. |
| Require encryption of data storage on device. | Supported |  |

# [Teams phones](#tab/phones)
Supported device compliance settings for Teams phone and displays enrolled with AOSP Device Management (AOSP DM).

| Policy | Availability | Notes |
| --- | --- | --- |
| [**Device Health**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#device-health) | -- | -- |
| Rooted devices | Supported |  |
| [**Device properties**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#device-properties) | -- | -- |
| Operating System Version (minimum, maximum) | Supported |  |
| Minimum security patch level | Supported |  |
| [**System security**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#system-security) | -- | -- |
| Require a password to unlock mobile devices | Not supported | Teams Devices don't support a password unlock. |
| Required password type | Not supported | Teams Devices don't support a password unlock. |
| Maximum minutes of inactivity before password is required | Not supported | Teams Devices don't support a password unlock. |
| Require encryption of data storage on device. | Supported |  |

# [Teams panels](#tab/panels)
Supported device compliance settings for Teams panels enrolled with AOSP Device Management (AOSP DM).

| Policy | Availability | Notes |
| --- | --- | --- |
| [**Device Health**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#device-health) | -- | -- |
| Rooted devices | Supported |  |
| [**Device properties**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#device-properties) | -- | -- |
| Operating System Version (minimum, maximum) | Supported |  |
| Minimum security patch level | Supported |  |
| [**System security**](/en-us/mem/intune/protect/compliance-policy-create-android-aosp#system-security) | -- | -- |
| Require a password to unlock mobile devices | Not supported | Teams Devices don't support a password unlock. |
| Required password type | Not supported | Teams Devices don't support a password unlock. |
| Maximum minutes of inactivity before password is required | Not supported | Teams Devices don't support a password unlock. |
| Require encryption of data storage on device. | Supported |  |

---