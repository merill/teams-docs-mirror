---
layout: Conceptual
title: Microsoft Teams Rooms Deployment Overview - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-deploy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: altsou
ms.date: 2026-01-21T00:00:00.0000000Z
ms.topic: install-set-up-deploy
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Read this article to learn about how to deploy Microsoft Teams Rooms and Teams panels, including the deployment phases.
locale: en-us
document_id: 99951587-c6ee-feb3-ab39-8d6b6969e939
document_version_independent_id: 1cb9d2e6-d4c1-628a-79bf-6ae405263f1d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-deploy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-deploy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-deploy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 04916566-2358-5b06-238b-a1a4ea27d551
---

# Microsoft Teams Rooms Deployment Overview - Microsoft Teams | Microsoft Learn

After completing planning for Teams Rooms (see [Planning for Teams Rooms](rooms-plan)), the next phase is deployment. Deploying Teams Rooms is broken down into a few phases:

1. Ordering equipment and confirming that your deployment locations (spaces) meet the deployment dependencies
2. Preparing your network environment and configuration steps to ensure your devices work on your corporate network
3. Creating resource accounts for your Microsoft Teams devices (see [Create and configure resource accounts for Teams devices](rooms-configure-accounts))
4. Enabling the Teams Rooms Pro Management Portal and assigning administrative roles (see [Accessing the Pro Management Portal](enrolling-mtrp-managed-service))
5. Configuring Intune for your Teams Rooms
6. Physically deploying your Teams Rooms devices and completing the initial setup steps

Tip

As a companion to this article, we recommend using the [Microsoft Teams Rooms automated setup guide](https://go.microsoft.com/fwlink/?linkid=2224463) when signed in to the Microsoft 365 admin center. This guide will customize your experience based on your environment. To review best practices without signing in and activating automated setup features, go to the [Microsoft 365 setup portal](https://go.microsoft.com/fwlink/?linkid=2222974).

## Ordering equipment and site readiness for a Teams Rooms deployment

Before ordering Teams Rooms equipment, review your physical meeting room spaces to determine the style of meetings that occur in the space and the equipment that fits the need. For more information, see [meeting room guidance](room-planning-guidance). Then, order your desired equipment from the [Teams devices store](/en-us/microsoftteams/devices/device-store) or from your reseller partner.

Work with your network, facilities, and audio-video (AV) teams to make sure that deployment dependencies are met. Ensure each site and space is ready in terms of power, networking, and furniture. In addition, make sure the physical installation requirements are met. For physical installation considerations, consult with your vendor and use the experience of your AV team when installing and mounting screens and running cabling.

| - | - |
| --- | --- |
| ![confirm sites.](../media/audio_conferencing_image7.png)Decision points | - Select and order your Microsoft Teams Rooms equipment.<br>- Confirm that your sites meet the physical installation requirements for Microsoft Teams Rooms. |
| ![plan device deployment.](../media/audio_conferencing_image9.png)Next steps | - Prepare your network for Teams Rooms. |

## Preparing your corporate network for Teams Rooms

Teams Rooms devices have specific network requirements which may require adjustments to your corporate network from bandwidth, firewall & proxy, or installing certificates. All of these requirements are things you want to consider as you deploy Teams Rooms. For more information on the networking requirements, see these links:

- [Prepare your network](rooms-prep)
- [Enable Teams Rooms QoS](/en-us/microsoftteams/devices/qos-on-teams-devices)
- [Review Teams Rooms IPs and URLs](security?tabs=Windows#network-security)
- [Enable 802.1x for Teams Rooms](security?tabs=Windows#network-security)

## Creating resource accounts for your Microsoft Teams Rooms

Teams Rooms devices need resource accounts to be able to successfully sign into Teams and allow end users to book and ensure join buttons appear on the rooms calendar. Each physical meeting room needs its own Teams Rooms resource account. Teams devices dedicated for that space can share the same resource account, meaning a Teams Room with two Teams panels at different doors can all share the same Teams Rooms resource account. This sharing ensures they're all in sync from a calendar perspective and automatic check-in/booking for meetings works correctly.

For each resource account, there are features an IT admin can enable for different business needs. You want to consider the features outlined here as you create your Teams Rooms resource accounts following this guide: [How to create and configure resource accounts for Teams devices](create-resource-account).

| Scenario | Description | Microsoft Teams Rooms service account feature |
| --- | --- | --- |
| Bookable for meetings | Using voice, video, and screen sharing; making the Microsoft Teams Rooms a bookable resource | Enabled for Microsoft Teams; enabled for Exchange calendaring |
| Meet Now | Allowing a "Meet Now" from the Teams Rooms device | Configure a Teams Meeting policy allowing Meet Now |
| Outbound/inbound Calling | Enable the Microsoft Teams Rooms console to make and receive Public Switched Telephone Network (PSTN) calls | Enabled for Phone System |

| - | - |
| --- | --- |
| ![scenario support.](../media/audio_conferencing_image7.png)Decision points | - Decide which Teams Rooms scenarios you support.<br>- Identify licensing requirements for your Microsoft Teams Rooms resource accounts. |
| ![prepare host machine.](../media/audio_conferencing_image9.png)Next steps | - Prepare the Pro Management Portal. |

## Enabling the Pro Management Portal

Teams Rooms devices are best managed in the Teams Rooms Pro Management Portal. Once you have a Teams Rooms Pro license available in your Microsoft 365 tenant, you can enable the Teams Rooms Pro Management Portal following the guidance here: [Accessing the Pro Management Portal](enrolling-mtrp-managed-service).

While in the Pro Management Portal it's important to define various administrative roles for your meeting room admins. The Pro Management Portal supports granular role-based access control (RBAC), you can follow the steps here for how to configure RBAC: [Role-based access control in the Microsoft Teams Rooms Pro Management Portal](rooms-pro-rbac).

| - | - |
| --- | --- |
| ![scenario support.](../media/audio_conferencing_image7.png)Decision points | - Activate the Pro Management Portal.<br>- Define RBAC inside of the Pro Management Portal |
| ![prepare host machine.](../media/audio_conferencing_image9.png)Next steps | - Configuring Intune for your Teams Devices. |

## Configuring Intune for your Teams Devices

Teams Rooms on Windows devices can be managed in Intune to expand device management capabilities and for Intune compliance checks to ensure Teams Rooms on Windows devices are compliant with organizational requirements. Teams Rooms on Android and Teams panels devices automatically enroll into Intune when they're logged in for the first time providing more controls and Intune compliance checks as well.

For Teams Rooms on Windows devices, Intune enrollment can be completed using [AutoPilot + AutoLogin](autopilot-autologin) or in one of several other manually [enrollment methods offered by Intune](/en-us/mem/intune/fundamentals/deployment-guide-enrollment-windows).

For Teams Rooms on Android and Teams panel devices, Intune enrollment is requirement for a successful sign in. Teams Android devices use Android Device Administrator today as their enrollment method, for information on enabling Intune enrollment see these instructions: [Configure Intune to enroll Teams Android-based devices](/en-us/microsoftteams/devices/phones-panels-deploy#configure-intune-to-enroll-teams-android-based-devices).

| - | - |
| --- | --- |
| ![scenario support.](../media/audio_conferencing_image7.png)Decision points | - Enabling Teams Rooms on Windows devices to enroll in Intune<br>- Enabling Teams Rooms on Android and Teams panels to enroll in Intune |
| ![prepare host machine.](../media/audio_conferencing_image9.png)Next steps | - Physically deploying your Teams Rooms devices and completing the initial setup |

## Physically deploying and configuring your Teams Rooms devices

### Device deployment

After creating your resource accounts and enabling the management portal, it's time to ship devices. Create your plan to ship the devices and their assigned peripherals to your rooms, and then proceed to installation and configuration.

| - | - |
| --- | --- |
| ![manage site-by-site deployment.](../media/audio_conferencing_image7.png)Decision points | - Decide who manages the site-by-site deployment.<br>- Identify the resources to install Microsoft Teams Rooms on site and undertake the configuration and testing. |
| ![start device testing.](../media/audio_conferencing_image9.png)Next steps | - Start device testing. |

*Sample deployment table*

| Site | Room name | Room type | Microsoft Teams Rooms system | Peripheral devices | Microsoft Teams Rooms computer name | Microsoft Teams Rooms resource account |
| --- | --- | --- | --- | --- | --- | --- |
| London HQ | Curie | Medium |  |  |  |  |
| Sydney HQ | Hill | Large |  |  |  |  |

### Microsoft Teams Rooms application and peripheral device configuration

At initial power on of your Teams Rooms device, you need to configure the Microsoft Teams Rooms application to use the matching Microsoft Teams Rooms resource account and password to sign in to Microsoft Teams.

Once signed in, you can configure settings each Microsoft Teams Rooms system. For a Teams Rooms on Windows device, you can use a centrally stored, XML configuration file to manage the application settings. For more information about how to use the XML configuration file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file).

| - | - |
| --- | --- |
| ![decision point configure.](../media/audio_conferencing_image7.png)Decision points | - Decide whether to manually configure each Microsoft Teams Rooms system or use a central XML file. |
| ![next steps remote approach.](../media/audio_conferencing_image9.png)Next steps | - Test your new Teams Rooms devices. |

### Testing

After Teams Rooms is deployed, you should test it. Check that the capabilities listed in [Microsoft Teams Rooms help](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&amp;rs=en-us&amp;ad=us) are working on the deployed device. We recommend that the deployment team check that Microsoft Teams Rooms is appearing in Teams Admin Center and in Teams Rooms Pro Management Portal. It's also important that you make several test calls and meetings to check quality.

### Asset management

As part of the deployment, you may want to update your asset register with the room name, Microsoft Teams Rooms name, Microsoft Teams Rooms resource account, and assigned peripheral devices.

*Sample asset table*

| Site | Room name | Room type | Microsoft Teams Rooms serial no. | Peripheral devices/ Serial nos./ Ports | Microsoft Teams Rooms computer name | Microsoft Teams Rooms service account | Date deployed |
| --- | --- | --- | --- | --- | --- | --- | --- |
| London HQ | Curie | Medium |  |  |  |  |  |
| Sydney HQ | Hill | Large |  |  |  |  |  |