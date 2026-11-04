---
layout: Conceptual
title: Implementing 802.1x Authentication for Microsoft Teams Rooms on Windows - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/802-1x-authentication
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
ms.date: 2025-09-11T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
ms.custom: QuickDraft
search.appverid: MET150
f1.keywords:
- NOCSH
ai-usage: ai-assisted
description: This article serves as a comprehensive guide to assist you in configuring and implementing 802.1x authentication for Microsoft Teams Rooms.
locale: en-us
document_id: 91eaa517-e61d-405f-764f-0f84667549d2
document_version_independent_id: 91eaa517-e61d-405f-764f-0f84667549d2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/802-1x-authentication.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/802-1x-authentication
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/802-1x-authentication.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 44db2155-8681-e365-63a2-9cb16b8d57b1
---

# Implementing 802.1x Authentication for Microsoft Teams Rooms on Windows - Microsoft Teams | Microsoft Learn

For customers looking to implement 802.1x in network environments especially Zero Trust networks, Microsoft Teams Rooms for Windows offers support similar to that of other Windows devices. This article outlines the necessary steps for setting up and deploying 802.1x authentication.

Important

For Teams Rooms on Android devices consult with your device manufacturer for guidance on support for 802.1x network authentication.

## Prerequisites

Before you begin, ensure that your network devices and AAA/RADIUS server are enabled for 802.1x LAN authentication. Configuration details vary depending upon your chosen vendor for these solutions. 802.1x is currently not supported on Teams Rooms for Android due to the lack of support for LAN profiles in Intune for Android. Refer to your device manufacturer to verify that your device can operate in a 802.1x LAN environment.

## Steps to Configure 802.1x Authentication

The following steps assume a ground up configuration to enable 802.1x for your Teams Rooms devices. Review these steps carefully and only implement those items applicable to your network.

### Step 1: Enable 802.1x LAN Authentication

Ensure that your network devices and AAA/RADIUS server are enabled for 802.1x LAN authentication. Configuration details vary depending on your chosen vendor for these solutions.

### Step 2: Configure Intune for Certification Distribution and Authentication

Use a PKCS certificate profile to provision devices with certificates in Microsoft Intune. For detailed instructions, refer to [Use a PKCS certificate profile to provision devices with certificates in Microsoft Intune](/en-us/mem/intune/protect/certificates-pfx-configure).

### Step 3: Create a Wired Network Profile within Intune

Configure 802.1x wired network settings for macOS and Windows devices in Microsoft Intune. For detailed instructions, refer to [Configure 802.1x wired network settings for macOS and Windows devices in Microsoft Intune](/en-us/mem/intune/configuration/wi-fi-settings-windows).

### Step 4: Enroll Your Teams Rooms Devices to Intune

Ensure your Teams Rooms devices are enrolled in Intune. For detailed instructions, refer to [Enrolling Microsoft Teams Rooms on Windows devices with Microsoft Endpoint Manager](https://techcommunity.microsoft.com/t5/microsoft-teams/enrolling-microsoft-teams-rooms-on-windows-devices-with-microsoft/ba-p/1744120).

### Step 5: Configure EAP on Your Teams Rooms on Windows

Configure Extensible Authentication Protocol (EAP) on your Teams Rooms on Windows. For detailed instructions, refer to [Configure EAP profiles and settings in Windows](/en-us/windows-server/networking/technologies/extensible-authentication-protocol/configure-eap-profiles?tabs=netsh-wifi%2Cpowershell-vpn%2Csettings-wifi%2Cgroup-policy-wifi).

With these steps in place, your 802.1x environment and Teams Rooms on Windows devices will be configured to ensure your Teams Rooms devices are managed and identified on your network.