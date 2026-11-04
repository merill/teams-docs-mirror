---
layout: Conceptual
title: Deploy Teams Phones using Conditional Access and Intune - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/phones-deploy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.date: 2024-10-21T00:00:00.0000000Z
ms.reviewer: prashibadkur
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
description: This article provides an overview of and features supported by Microsoft Teams Phones.
locale: en-us
document_id: df57a9d6-3fd9-4da4-efc1-03e982ab55cb
document_version_independent_id: df57a9d6-3fd9-4da4-efc1-03e982ab55cb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/phones-deploy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/phones-deploy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/phones-deploy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 99cdd742-3bba-aad6-e147-5703f08d674e
---

# Deploy Teams Phones using Conditional Access and Intune - Microsoft Teams | Microsoft Learn

This article gives you an overview of how to deploy and configure Intune and Conditional Access to support Teams Phones.

## Configure Intune to allow enrollment Teams Phones

Customers must enroll their Teams phone devices using Android Device Administrator. Before devices can be enrolled into Intune successfully, there are a few basic steps to perform. If you're managing devices with Intune today, you may be able to skip several steps. If not, here's what to do:

1. Ensure Intune is set as the MDM (mobile device management) authority.

    You need to set the MDM authority to be Intune before you can enroll devices. For more information, see [Set the mobile device management authority](/en-us/mem/intune/fundamentals/mdm-authority-set). Settings the MDM authority is a one-time step that has to be done upon creating a new Intune tenant.
2. Enable Android device administrator.

    Teams Phones are Android-based and without Google Mobile Services (GMS) and therefore are managed in Intune with Android Device Administrator (ADA). Device Administrator enrollment is off by default for newly created tenants. See [Android device administrator enrollment](/en-us/mem/intune/enrollment/android-enroll-device-administrator) for steps on how to enable Android Device Administrator in your environment.

Note

Intune enrollment for Teams Phones will switch to Android Open Source Project (AOSP) Device Management in 2025.

1. Assign Device Administrator compliance policies.

    Android Device Administrator offers Intune compliance policies which can be used to ensure Teams Phones are compliant with various organization security policies. Create an Android Device Administrator compliance policy then assign it to your Teams phone resource accounts. For more information, see [use compliance policies to set rules for devices you manage with Intune](/en-us/mem/intune/protect/device-compliance-get-started).

Note

- If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.
- If the user account used to sign into a Teams device is licensed for Intune, the Teams device will automatically enroll in Intune.

## Conditional Access

Conditional Access is a Microsoft Entra ID feature that helps to ensure devices accessing your Microsoft 365 resources are properly managed and secure. For Teams Phones, we recommend using Conditional Access to secure Teams phone resource accounts since resource accounts don't support user interactive multi-factor authentication (MFA). Conditional Access can be used to enforce a different secondary factor, such as known network location or compliant device to match organization security policies. If you apply a Conditional Access policy requiring Teams Phones to be Intune compliance, the Teams phone must be enrolled into Intune with a compliance policy configured. If the device isn't enrolled into Intune, or if its enrolled, but its settings don't comply with your policies, Conditional Access prevents that Teams phone from signing in successfully.

Typically, compliance policies defined within Intune are assigned to groups of users. This means that if you assign an Android compliance policy to user@contoso.com, that policy applies equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into. For more information, review [Teams phone authentication best practices](authentication-best-practices-phones).

If you use Conditional Access compliance policies, Intune enrollment is required. There are a couple things you need to set up to allow for a successful Intune enrollment:

- **Intune license** The user signing into the Teams phone must be licensed for Intune. As long as the Teams device is signed in to a user account that has a valid Intune license, the device is automatically enrolled in Microsoft Intune as part of the sign in process.
- **Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.