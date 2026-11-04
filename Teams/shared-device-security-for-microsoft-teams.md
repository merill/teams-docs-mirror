---
layout: Conceptual
title: 'Zero-trust security guide for Microsoft Teams: Use Teams securely on shared computers - Microsoft Teams | Microsoft Learn'
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/shared-device-security-for-microsoft-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MicrosoftHeidi
ms.author: heidip
manager: dansimp
ms.topic: reference
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: pawa
ms.date: 2024-10-30T00:00:00.0000000Z
description: Zero Trust guidance for using Microsoft Teams securely from a shared computer in the workplace.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
locale: en-us
document_id: 925d2c84-739d-d669-dd70-f80e52b78efd
document_version_independent_id: 5ed29f12-8c1b-ad9e-9d3f-5d82cb40ad58
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/shared-device-security-for-microsoft-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: shared-device-security-for-microsoft-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/shared-device-security-for-microsoft-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4370e00e-3f35-cd33-c199-40d36bb6b6a9
---

# Zero-trust security guide for Microsoft Teams: Use Teams securely on shared computers - Microsoft Teams | Microsoft Learn

When possible, we *recommend* Enterprises take a Zero Trust approach to client devices using device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.

![Zero Trust picture showing verify explicitly, least privilege, and assume breach--the core Zero Trust principles--in blue circles.](media/tp_zerotrustprinciples.png)

Administrators can create secure conditions by *insisting* on verification, least privilege, and by assuming compromise--standards that lead to actions that minimize risk to both users and data.

Tip

For a deeper examination of Zero Trust principles, see [these videos](/en-us/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## Tips for using Microsoft Teams securely from a shared computer

Recognizing that using Teams securely might not be possible or practical in all scenarios, it's still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.

Plans should be developed to adhere to guidelines as promptly as is possible.

1. Use Operating System platform security capabilities.
    1. Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this configuration can be done with [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).
    2. Ensure that any device encryption capabilities such as [**BitLocker**](/en-us/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured. Most modern [**Windows 10 devices support BitLocker**](/en-us/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).
    3. Use anti-virus capabilities such as those offered by [**Windows Defender**](/en-us/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.
    4. Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.
    5. *Don't* grant, or use, administrator privileges for nonadministrative functions (such as browsing the web, running Teams, et cetera).

If the guidance in step 1 can't be met, we recommend using other browser security best practices:

1. Automatically delete browser data.

    1. Configure your browser to automatically delete the browser history and data regularly, or whenever the browser is closed. This configuration protects privacy without affecting how Microsoft Teams works. You can find instructions on how to set up this configuration in the documentation for [Google Chrome](https://support.google.com/chrome/community-guide/245444314/how-to-automatically-clear-browsing-data-when-closing-google-chrome-window-a-step-by-step-guide), [Microsoft Edge](https://support.microsoft.com/windows/microsoft-edge-browsing-data-and-privacy-bb8174ba-9d73-dcf2-9b4a-c582b4e640dd), [Mozilla Firefox](https://support.mozilla.org/en-US/kb/delete-browsing-search-download-history-firefox), and [Apple Safari](https://support.apple.com/guide/safari/clear-your-browsing-history-sfri47acf5d6/mac).
    2. Private browsing sessions, such as inPrivate browsing in Microsoft Edge or Incognito Mode in Google Chrome, can help minimize the data and history saved to your device. However, using Microsoft Teams on the web in private browsing sessions may lead to performance issues if cookies or services used by Microsoft or third-party apps in Teams are blocked.
2. Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.
3. When you're done using the shared system, you must:

    1. [Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    2. Close all browser tabs and windows.
    3. Sign out of the device.

The items in the previous list aren't a comprehensive list of best practices or security controls covering all cases. There might be extra actions that can be taken in your environment (for instance, security administrators might choose to use Safe Links and Safe Attachments for Teams if you have [Microsoft Defender for Office 365 Plan 1 or Plan 2](/en-us/microsoft-365/security/office-365-security/overview)). However, these steps are a starting point for building guidance for using Teams from shared devices.

## More Information

[BitLocker in Configuration Manager](/en-us/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker for Windows 10 in Intune](/en-us/mem/intune/protect/encrypt-devices)

[Endpoint security in Intune](/en-us/mem/intune/protect/endpoint-security)

[Enable](/en-us/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](/en-us/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Microsoft Defender security center article](/en-us/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Microsoft Teams client](teams-client-desktop-admin)

[Security and Microsoft Teams](teams-security-guide)