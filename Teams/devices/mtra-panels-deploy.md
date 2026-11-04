---
layout: Conceptual
title: Deploy Teams Rooms on Android and Teams panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/mtra-panels-deploy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.date: 2025-11-25T00:00:00.0000000Z
ms.reviewer: mattslomka
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- teams-rooms-devices
- M365-voice
- Teams_ITAdmin_Devices
- Tier1
search.appverid: MET150
ms.localizationpriority: medium
description: This article gives you an overview of how to deploy Teams panels, and Microsoft Teams Rooms on Android using Conditional Access and Intune.
locale: en-us
document_id: ee8bb423-3bb5-6024-2a1f-b759330039b6
document_version_independent_id: ee8bb423-3bb5-6024-2a1f-b759330039b6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/mtra-panels-deploy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/mtra-panels-deploy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/mtra-panels-deploy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 10f2997f-bac8-9d7b-32e1-d9c4a03a0ce9
---

# Deploy Teams Rooms on Android and Teams panels - Microsoft Teams | Microsoft Learn

This article gives you an overview of how to deploy Teams panels and Microsoft Teams Rooms on Android using Conditional Access and Intune.

Important

Device Administrator has been deprecated for Teams Android devices. Devices running the latest firmware will enroll using AOSP (Android Open Source Project) Device Management, follow the instructions to configure [AOSP Device Management enrollment](/en-us/microsoftteams/devices/teams-aosp-enrollment).

## Conditional Access

Conditional Access is a Microsoft Entra feature that helps you to ensure devices accessing your Office 365 resources are properly managed and secure. If you apply Conditional Access policies to the Teams service, all devices including Teams phones, Teams displays, Teams panels, and Microsoft Teams Rooms on Android need to be enrolled into Intune and their settings need to comply with your organizational policies. If the device isn't enrolled into Intune, or if its enrolled, but its settings don't comply with your policies, Conditional Access prevents a user from signing in or using the Teams app on the device.

Typically, compliance policies defined within Intune are assigned to groups of users. This means that if you assign an Android compliance policy to user@contoso.com, that policy applies equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.

If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:

- **Intune license** The user signing into the Teams device must be licensed for Intune. As long as the Teams device is signed in to a user account that has a valid Intune license, the device is automatically enrolled in Microsoft Intune as part of the sign in process.
- **Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.

Teams Android-based devices including Teams panels and Teams Rooms on Android are managed by Intune using Android Device Administrator (DA) management.

## Configure Intune to enroll Teams Android-based devices

Customers must enroll their devices using Android Device Administrator. Before devices can be enrolled into Intune, there are a few basic steps to perform. If you're already managing devices with Intune today, you probably have already done all these things. If not, here's what to do:

Note

- If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.
- If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.
- If the user account used to sign into a Teams device is licensed for Intune, the Teams device will be automatically enrolled in Intune.

1. Set Intune MDM (mobile device management) Authority.

    If you've never used Intune before, you need to set the MDM authority before you can enroll devices. For more information, see [Set the mobile device management authority](/en-us/mem/intune/fundamentals/mdm-authority-set). This is a one-time step that has to be done upon creating a new Intune tenant.
2. Enable Android device administrator enrollment.

    Android-based Teams devices are managed as device administrator devices with Intune. Device administrator enrollment is off by default for newly created tenants. See [Android device administrator enrollment](/en-us/mem/intune/enrollment/android-enroll-device-administrator).
3. Assign licenses to users.

    Users of Teams devices enrolling to Intune must be assigned a valid Intune license. For more information, see [Assign licenses to users so they can enroll devices in Intune](/en-us/mem/intune/fundamentals/licenses-assign).
4. Assign Device Administrator compliance policies.

    1. Create an Android Device Administrator compliance policy.
    2. Assign it to the Microsoft Entra group that contains the users that are signing into the Teams devices. See [Use compliance policies to set rules for devices you manage with Intune](/en-us/mem/intune/protect/device-compliance-get-started).