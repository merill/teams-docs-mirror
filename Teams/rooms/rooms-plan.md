---
layout: Conceptual
title: Plan for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-plan
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: sohailta
ms.date: 2026-01-20T00:00:00.0000000Z
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
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: This article explains the relevant planning considerations for deploying Microsoft Teams Rooms, the next generation of Skype Room Systems.
locale: en-us
document_id: 78187b02-b08d-5b10-587d-82c81652b675
document_version_independent_id: 78187b02-b08d-5b10-587d-82c81652b675
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-plan.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 61b194c7-4684-393c-df3d-bbd191fd092c
---

# Plan for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

This article introduces an end-to-end approach to planning, delivering, and operating Microsoft Teams Rooms as part of your overall meeting and conference room strategy.

The planning information covers the recommended approach and key decisions that you need to make, with links to supporting technical information. We recommend that you review the Plan, Deploy, and Manage sections even if you're already fully deployed.

## Overview of Microsoft Teams Rooms

Microsoft Teams Rooms provides a complete meeting experience that brings HD video, audio, and content sharing to meetings of all sizes, from small huddle areas to large conference rooms.

![A user taps a Teams Rooms console, with a display in the background.](../media/room-systems-image1.jpg)

[Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) is a great resource to find out more about Microsoft Teams Rooms and how it can add value as part of your deployment.

## Microsoft Teams Rooms components

Microsoft Teams Rooms includes the following key components to deliver a great user experience:

- Touchscreen console
- Compute module
- Microsoft Teams Rooms application
- Peripheral devices (camera, microphone, speaker)
- Front of room screens (maximum of two)
- HDMI input

Check out the certified Teams Rooms systems and peripherals in [Teams Rooms certified systems and peripherals](certified-hardware).

## Teams Rooms licensing

Each meeting room needs a Teams Rooms license, such as a Teams Rooms console, Surface Hub, or Teams panel. Teams provides two licenses for Teams Rooms: Microsoft Teams Rooms Pro and Microsoft Teams Rooms Basic.

Microsoft Teams Rooms Pro is great for organizations that have 25 or more meeting room devices or who want the most comprehensive meeting and device management experiences. Hybrid Teams meetings become more immersive with features like Front row, Content camera, AI-powered noise suppression, and other features available with Microsoft Teams Rooms Pro. Teams Rooms admins can centrally manage all their certified Teams Rooms devices from the Pro Management Portal.

Microsoft Teams Rooms Basic is available for organizations that only have a few meeting room devices and who only need basic meeting and management functionality. Microsoft Teams Rooms Basic lets you join meetings, share content and live video, join Zoom and Webex meetings with Direct Guest Join, and perform basic device inventory and monitoring in the Teams Admin Center.

Before you can use a meeting room device, you need to assign a license to it. For more information, see [Microsoft Teams Rooms licenses](rooms-licensing).

Tip

If your meeting room only has a Teams panel, you can use a Teams Shared Device license for the Teams panel resource account. If you add a Teams Rooms device to the space later, you can upgrade to a Teams Rooms Pro license.

Important

A shared meeting device is a device used by users in a shared location to participate in Microsoft Teams meetings. A device used as a shared meeting device requires a Teams Rooms license whether it participates by signing in to a Microsoft Teams client, by anonymous join, or by authenticating a Microsoft 365 identity (such as a resource account) through Azure Communication Services or another integration framework. Enterprise per user Microsoft 365 suite licenses aren't authorized for use on shared meeting devices in any of these configurations. Direct Guest Join (DGJ) and Cloud Video Interoperability (CVI) are designed to enable shared meeting devices to join Teams meetings without requiring a separate Teams meeting license for the joining device or endpoint when implemented through Microsoft-supported interoperability experiences and configurations.

Also, Microsoft Teams Shared Space licenses aren't supported on and won't work with Teams Rooms devices. Teams Rooms devices should only be assigned Teams Rooms Basic or Teams Rooms Pro licenses (Teams Rooms legacy licenses are also valid).

| - | - |
| --- | --- |
| ![decide deployment.](../media/audio_conferencing_image7.png)Decision points | - Are you deploying Microsoft Teams Rooms in your organization?<br>- How do you plan you procure your Microsoft Teams Rooms systems? |
| ![identify activities.](../media/audio_conferencing_image9.png)Next steps | - Identify who performs the key activities throughout your deployment.<br>- Understand where you want to deploy Microsoft Teams Rooms and the peripheral devices that would be appropriate for the room size. |
|  |  |

## Identify who performs the key activities throughout your deployment

Begin with understanding what conference rooms you have and envisioning what would work best for you in the future, then move through selecting and procuring the equipment you need, readying your sites, configuring and deploying your service, managing change and user adoption, and developing operations and maintenance procedures.

[![Begin with understanding what you have and envisioning what would work best for you, then move through selecting and procuring the equipment you need, readying your sites, configuring and deploying your service, managing change and user adoption, and developing operations and maintenance procedures.](../media/room-systems-image2.png)](../media/room-systems-image2.png#lightbox)

You might need to coordinate these activities across several teams. We provide a high-level view of the main activities that you should cover, and also suggestions for the teams who are typically involved in deploying and managing conference room systems, to help you decide who you need to work with.

| Task | Who might undertake the task | Assigned to | Links to this content |
| --- | --- | --- | --- |
| Inventory rooms | Facilities / AV team / IT Project Team |  | Room inventory and capability planning |
| Plan capabilities | IT Project Team |  | Room inventory and capability planning |
| Device selection | IT Project Team / AV Team |  | Device selection |
| Procurement | IT Project Team / AV Team |  | Procurement |
| Site readiness | Facilities / AV team / IT Project Team |  | [Site readiness](rooms-deploy#ordering-equipment-and-site-readiness-for-a-teams-rooms-deployment) |
| Network readiness | IT Project Team |  | [Network readiness](rooms-deploy#preparing-your-corporate-network-for-teams-rooms) |
| Resource accounts | IT Project Team |  | [Creating resource accounts](rooms-deploy#creating-resource-accounts-for-your-microsoft-teams-rooms) |
| Deployment | Facilities / AV team / IT Project Team |  | [Deployment checklist](console) |
| Adoption | Facilities / AV team / IT Project Team |  | Adoption |
| Maintenance and operations | AV team / IT Project Team |  | [Management overview](rooms-manage) |

## Room inventory and capability planning

The first step is to inventory your organization's existing meeting spaces and conference rooms to understand their environment, room size, layout, and purpose. You can then identify the capabilities you want each room to have such as intelligent cameras, whiteboarding, content camera, etc.

After you create an inventory of the equipment and capabilities in each existing room, your requirements for that room feed into your device selection planning to create a rich conferencing solution. The modalities (audio, video) needed for each room—in addition to room size and purpose—all play an important role in deciding which solution is most appropriate for each room.

As part of your discovery, it's key to consider room acoustics and layout. For example, check that the chairs in the room can't block the camera view. Verify that the room doesn't have excessive echo or noisy air conditioning, and that it does have sufficient power for the screens and Microsoft Teams Rooms. There are many factors to consider that your audio-visual (AV) team or partner can advise on.

| - | - |
| --- | --- |
| ![deplyment rooms.](../media/audio_conferencing_image9.png)Next steps | - Review the rooms in scope, and define Microsoft Teams Rooms configurations for them. |

*Sample meeting/conference room inventory*

| Site | Room name | Room type | Number of people | In scope? | Current room capabilities | Future room capabilities |
| --- | --- | --- | --- | --- | --- | --- |
| London HQ | Curie | Medium | 6–12 | Yes | Speakerphone | Single screen, audio, and video plus presentation |
| Sydney HQ | Hill | Large | 12–16 | Yes | Legacy AV unit, single screen, and camera | Dual screens, audio, and video plus presentation |

## Device selection

Evaluate which Microsoft Teams Rooms solution is the most suitable for each room based on the future capabilities you want for the room. Decide which AV peripheral devices are the best fit, depending on room size and layout.

For guidance for the type of system and peripheral devices by room type and size, see [Teams Rooms devices by space](https://www.microsoft.com/microsoft-teams/across-devices/spaces) and select your room size. For a list of certified Teams Rooms systems and peripherals, see [Teams Rooms certified systems and peripherals](certified-hardware).

Based on the vendor you prefer, use the information provided in the requirements article to define your Microsoft Teams Rooms and supported peripheral device configuration per room type, and use this as a template for your deployment.

Tip

Some room types might not be applicable for your deployment.

| - | - |
| --- | --- |
| ![rooms in scope.](../media/audio_conferencing_image7.png)Decision points | - Which types of rooms are in scope for your deployment?<br>- Which systems will you deploy for each room type? |
| ![gather material.](../media/audio_conferencing_image9.png)Next steps | - Start to gather key operational material for your chosen systems, and engage your procurement team. |

*Sample Microsoft Teams Rooms deployment template for your organization*

| Room type/size | Number of people | Microsoft Teams Rooms system | Peripheral devices | Displays |
| --- | --- | --- | --- | --- |
| Focus 10' by 9' | 2–4 |  |  |  |
| Small 16' by 16' | 4–6 |  |  |  |
| Medium 18' by 20' | 6–12 |  |  |  |
| Large 15' by 32' | 12–16 |  |  |  |

Tip

Now is a great time to start gathering information about the Microsoft Teams Rooms solution you've chosen.

## Procurement

You can procure your chosen system as a bundle or an integrated solution via device partners.

You can acquire Microsoft Teams Rooms from one of the partners are listed in [Teams Rooms certified systems and peripherals](certified-hardware). Visit the partners' websites to learn more about these solutions and procurement options.

Depending on your deployment scale and approach, you might decide to have the Microsoft Teams Rooms and supported peripheral devices shipped to a central location for initial configuration and assignment. A central location might be a good approach for a staged rollout across many sites. Or, you might choose to ship the bundles directly to your sites.

| - | - |
| --- | --- |
| ![ship components.](../media/audio_conferencing_image7.png)Decision points | - Do you ship the components directly to a site or to a staging facility?<br>- Do you know who manages the staging facility (if you decide to use one)? |
| ![plan operations.](../media/audio_conferencing_image9.png)Next steps | - Plan for operations.<br>- Plan for adoption and change management. |

## Plan for operations

Your organization must execute monitoring, administration, and management tasks on an ongoing basis, and it's key to agree who will undertake these tasks early in your deployment.

Many organizations have an AV team or partner who manages their conference rooms and devices. It's important to decide who manages the Microsoft Teams Rooms devices going forward to monitor performance and deploy software updates and hotfixes.

Consider which helpdesk queue you route Microsoft Teams Rooms-related calls to, and provide an FAQ to the helpdesk team so they can better understand how to use Microsoft Teams Rooms and the key troubleshooting steps they can take. A good starting point for this FAQ is the [user help](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) and [Known issues](known-issues).

Note

Microsoft Teams Rooms sign in to Microsoft Teams and allows joining meetings hosted by Microsoft Teams services. Microsoft Teams rooms may also connect to third party meeting services anonymously as guest, depending on your configuration of the device.

Skype for Business Server 2019, Skype for Business Server 2015 or earlier platforms like Lync Server 2013 aren't supported by Microsoft Teams Rooms. Microsoft Teams Rooms is not supported in Microsoft 365 operated by 21Vianet.

If you have an on-prem Exchange server, Microsoft Teams Rooms requirements for connecting to Exchange can be found here: [https://learn.microsoft.com/en-us/microsoftteams/exchange-teams-interact](/en-us/microsoftteams/exchange-teams-interact)

| - | - |
| --- | --- |
| ![choose manager.](../media/audio_conferencing_image7.png)Decision points | - Decide who will manage Microsoft Teams Rooms.<br>- Decide which helpdesk queue to route Microsoft Teams Rooms-related calls to. |
| ![prepare host accounts.](../media/audio_conferencing_image9.png)Next steps | - Prepare to host accounts. |

## Plan for adoption and change management

Microsoft Teams Rooms systems introduce new capabilities to your users. It's important that you recognize that Teams Rooms will be a change for your users, and you should ensure your internal marketing campaign identifies the benefits the new system will have for your users and the key talking points leads can use to discuss with their teams.

To inform your users of the new capabilities, consider scheduling show-and-tell events and poster drops at each site. You might also create in-room "quick start guides." Consider finding a meeting champion at each site who can help others get up to speed and start using the devices.