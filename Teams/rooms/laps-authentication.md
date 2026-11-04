---
layout: Conceptual
title: LAPS authentication on Teams Rooms on Windows - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/laps-authentication
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: anwoodru
ms.date: 2025-01-27T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-rooms
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: This article provides an overview of LAPS, its architecture, and the steps to configure LAPS for Teams Rooms on Windows.
locale: en-us
document_id: 20328951-3741-ddd8-5667-e1adbc35c58a
document_version_independent_id: 20328951-3741-ddd8-5667-e1adbc35c58a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/laps-authentication.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/laps-authentication
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/laps-authentication.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 392ef692-5b08-1dc8-9cc7-ef6398bee1bd
---

# LAPS authentication on Teams Rooms on Windows - Microsoft Teams | Microsoft Learn

This article provides an overview of LAPS, its architecture, and the steps to configure LAPS for Teams Rooms on Windows.

Windows Local Administrator Password Solution (LAPS) is a Windows feature that manages and backs up the password of the local administrator account to Microsoft Entra joined (Entra Joined) or Active Directory (AD). It provides enhanced protection against local administrator account password attacks and meets key customer requirements for deploying Teams Rooms on Windows devices.

## What is LAPS?

LAPS is a solution that automatically generates a random and complex password for the local administrator account on each Windows device and stores it securely in Entra or Active Directory. The password is periodically changed according to the configured policy and can be retrieved by authorized users when access is required. LAPS reduces the risk of lateral movement and privilege escalation attacks that exploit the same local administrator password on multiple devices. It simplifies the management of local administrator passwords and eliminates the need for manual or scripted solutions.

## Windows LAPS architecture

LAPS consists of the following components:

- A periodic background task runs on each Windows device and performs the password change and backup operations.
- A PowerShell module that provides cmdlets for administering and retrieving the passwords.
- Enable Microsoft Entra Local Administrator Password Solution (LAPS) schema extension for AD that adds an attribute for storing the password and related information.

**LAPS architecture and workflow**:

![Windows LAPS architecture with a managed device, Azure Active Directory, and Windows Server ActiveDirectory.](/en-us/windows-server/identity/laps/media/laps-concepts-overview/laps-concepts-overview-architecture-diagram.png)

## LAPS deployment

Before deploying on Teams Rooms on Windows, you should consider:

- LAPS should be deployed using Entra ID where possible as it provides better security and scalability than Active Directory.
- The devices **must** be Entra joined or Hybrid Entra Joined and **managed** by Intune before proceeding with LAPS deployment.
- Any peripherals or endpoints that connect to the Teams Rooms on Windows device using the local administrator credentials will lose connection upon reboot or password change. Some OEM implementations use this method for connecting room controllers. The OEM should be consulted for compatibility and alternative solutions.
- That all guidance in this document has been configured and tested against OEM builds and excludes any custom images.
- That you have a dedicated device group for Teams Rooms on Windows devices for policy management and assignment. If this isn't available, create one before proceeding further.

Note

Some OEMs like Crestron require the local username and password to connect peripherals like touch controllers. For more information on the impacts of changing the local account password, contact Crestron before implementing.

The deployment of LAPS for Teams Rooms on Windows devices requires:

- Configuring the Entra ID settings to enable LAPS.
- Creating and assigning the LAPS policy in Intune.
- Verifying the password change and backup on the devices.

### Entra Configuration

To enable LAPS in Entra ID:

1. Go to https://entra.microsoft.com.
2. Click **Identity** &gt; **Devices** &gt; **All Devices**.
3. Select **Device Settings**.
4. Toggle **Enable Microsoft Entra Local Administrator Password Solutions** to **Yes**.
5. Click **Save**.

### Intune Configuration

To create and assign the LAPS policy in Intune, the following steps should be followed:

1. Go to **Intune Admin Center** at https://intune.microsoft.com.
2. Select **Endpoint security** in the left navigation.
3. Select **Account protection**.
4. Select **Create Policy**.
5. For **Platform**, select **Windows 10 and later and profile Local admin password solution (Windows LAPS)**.
6. Click **Create**.

To configure the policy settings:

1. Enter a policy name such as *Teams Rooms on Windows LAPS Policy*.
2. Enter a description if required, then click **Next**.
3. Select **Backup Directory** to be **Backup the password to Azure AD only.**
4. Toggle **Password Age Days to configured** and enter the desired value.
5. Toggle **Administrator Account Name** to configured and enter **Admin** to match the pre-defined username of the local admin account on the Teams Rooms on Windows console.
6. Select the desired **Password Complexity** method desired.
7. Toggle **Password Length** to configured and enter the desired password length with 8 minimum and 64 maximum.
8. Click **Next** twice if you don't use scope tags.

To assign the policy to a group of Intune-managed Teams Rooms on Windows devices:

1. Select **Assignments**.
2. Select the group that contains the Teams Rooms on Windows devices and scope the policy correctly. The select **Next**.
3. After you confirm the policy and scope is correct, select **Create** to apply the policy to the in-scope devices.
4. Wait for up to an hour for the policy to apply and the password to be changed.

## LAPS management

To retrieve the local administrator password from the Entra Admin Center:

1. Go to https://entra.microsoft.com.
2. Click **Identity** &gt; **Devices** &gt; **All Devices**.
3. Select **Local Administrator Password Recovery**.
4. Search for an enabled device or select from the prepopulated list.
5. Click **Show local administrator password**.
6. Click **Show to reveal the password**. Take note of the last and next rotation timestamps.

To review the audit logs in Entra:

1. Go to https://entra.microsoft.com.
2. Click **Identity** &gt; **Devices** &gt; **All Devices** &gt; **Audit logs**.
3. Select **Activity** to filter against **Update device local administrator password** or R**ecover device local administrator password** to review the events.

## Summary

LAPS is a Windows feature that enhances the security and management of local administrator passwords for Teams Rooms on Windows devices. It automatically generates and backs up the passwords to Entra and allows authorized users to retrieve them when needed. LAPS also prevents password reuse and simplifies password rotation. This document provides the steps to deploy and service LAPS for Teams Rooms on Windows devices using Entra and Intune.

## Related LAPS documentation

- [Windows LAPS documentation](/en-us/windows-server/identity/laps/laps-overview)
- [Manage Windows LAPS with Microsoft Intune policies](/en-us/mem/intune/protect/windows-laps-overview)
- [Windows Local Administrator Password Solution in Microsoft Entra ID](/en-us/entra/identity/devices/howto-manage-local-admin-passwords)
- [LAPS CSP](/en-us/windows/client-management/mdm/laps-csp)