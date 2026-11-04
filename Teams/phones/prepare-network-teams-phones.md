---
layout: Conceptual
title: Prepare your network for Team phones - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/prepare-network-teams-phones
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: prashibadkur
ms.date: 2025-09-11T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
description: Learn about how to prepare your network infrastructure for deploying Microsoft Teams phones so that you can take advantage of all of the available features.
locale: en-us
document_id: 61199959-1863-20d8-7ea4-2e60defdd3a5
document_version_independent_id: 61199959-1863-20d8-7ea4-2e60defdd3a5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/prepare-network-teams-phones.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/prepare-network-teams-phones
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/prepare-network-teams-phones.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: 63ab5172-e414-4f51-929b-7811b05af480
---

# Prepare your network for Team phones - Microsoft Teams | Microsoft Learn

This section contains an overview of the steps required to prepare your network environment so that you can use all of the features of Microsoft Teams phones. This section also includes information on configuring local administrative access to your Teams phones.

## Confirm network configuration

In order to function properly, Microsoft Phone devices must have access to a network that meets these requirements:

- Review access to: Microsoft Teams, Intune, Microsoft Entra ID, & Microsoft Common destinations. Open required ports to the required destinations documented in [Teams Android Device - Network Security](/en-us/microsoftteams/rooms/security?tabs=Android#network-security)
- Review network bandwidth and quality of service (QoS) requirements: [QoS on Teams Phones](qos-on-teams-phones)
- Review if your organization utilizes a proxy, you need the proxy address or proxy autoconfiguration (PAC) file url
- Review if your organization utilizes certificates for network access, you need the certificates for a successful setup

Important

Be sure to use a network connection with enough bandwidth (we recommend 100 kbps up/down per Teams Phone) to ensure your calls perform well.

### Certificates

Your Microsoft Teams Phone device uses certificates for Microsoft Teams, network usage, and authentication. If the related servers use public certificates, which is the case for online, there should be no further action required on the part of the admin to install certificates. If, on the other hand, the certificate authority is a private CA then the device needs to trust that CA. This means having the CA + CA chain certificates installed on the device. Certificates can be installed via OEM tooling.

Note

Trusted Root Certificate deployment through Intune is not supported on Teams phone devices.

### Proxy

Important

Microsoft Teams Phones does not support proxy authentication as it may interfere with regular operations of the room. Ensure that Microsoft Teams Phones have been exempted from proxy authentication before going into production. If your proxy server utilizes internally signed certificates, you must install the internal certificate chain, including the root CA, on the Microsoft Teams Phone.

Proxy settings on Teams Phones vary by device manufacturer. Consult OEM documentation for how to best configure Teams Phone devices for a network with a proxy.

### Wireless network considerations

We strongly recommend that you connect your Teams Rooms devices to a wired network for greater stability and performance, ensuring a seamless meeting experience. If using a wired connection isn't available, you may opt to use a wireless connection.

Important

Wireless networks can be prone to network interference leading to quality degradation. We strongly recommend that you follow your wireless equipment provider's best practices when configuring a wireless connection to improve video and audio quality.

Here are some examples of wireless network configuration best practices recommended by various manufacturers:

- Deploy wireless equipment, such as access points and routers, that can handle and distribute the bandwidth load across all connected devices in the network.
- As much as possible, use access points and routers from a single manufacturer to avoid further congesting the radio-spectrum.
- Ensure wireless equipment is installed in a way that reduces or eliminates interference from objects and other equipment.
- Ensure the wireless network shows strong signal strength (Wi-Fi signal showing full bars is preferred) on Teams Rooms and other device screens.
- Default to prioritizing 5-GHz coverage for devices to optimize for higher bandwidth.
- Enable band steering to ensure that 5 GHz is always given more priority when sharing the same network name as 2.4 GHz.
- Keep wireless channel utilization below 50%.
- Keep access point and router firmware up to date with the latest firmware versions and hot fixes.
- Verify that Teams Rooms devices and at least one access point see each other with a signal strength of -60 dBm or better. A dBm value closer to zero is preferred. Follow your equipment manufacturer's recommendations.
- Implement QoS whenever possible to allow monitoring and resolution of issues in real time.

For more best practices specific to your wireless network hardware, check your manufacturer's documentation.

## Tenant Restrictions

For organizations which utilize [tenant restrictions](/en-us/entra/identity/enterprise-apps/tenant-restrictions) features of Microsoft Entra ID, this is supported on some Teams Devices if your organization utilizes the proxy deployment variant with header injection. However, tenant restrictions aren't supported today on Teams Phone devices. Consult with your Android device OEM for potential workarounds.

## 802.1x Network Authentication

Consult with your Teams Phone manufacturer for guidance on supporting 802.1x network authentication.

## Device administrative access

Local administrative access to Teams Phone devices is controlled by the Teams device equipment manufacturer. Consult the device documentation for default accounts and passwords and instructions for how to change those passwords.