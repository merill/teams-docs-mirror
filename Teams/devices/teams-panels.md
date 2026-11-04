---
layout: Conceptual
title: Plan for Teams panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/teams-panels
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: eviegrimshaw
ms.date: 2026-04-28T00:00:00.0000000Z
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
ms.localizationpriority: medium
description: This article provides the information required when you are planning to deploy and manage Microsoft Teams panels.
locale: en-us
document_id: 6f6d4313-70e2-ac40-0e73-85bdb815c38b
document_version_independent_id: 78f8d192-8018-2988-db5c-44900a60833a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/teams-panels.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/teams-panels
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/teams-panels.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0116e9fe-2a5f-0e8c-28e6-72b28f3453e9
---

# Plan for Teams panels - Microsoft Teams | Microsoft Learn

Microsoft Teams panels are the compact touchscreen devices that are mounted right outside of your meeting spaces, typically next to entrances. Teams panels provide you the ability to view location and meeting details at a glance—and reserve an available meeting space on the spot. With rich, large text and color-coded indicators, you can see the meeting space’s availability from a distance.

Teams panels are dedicated Microsoft Teams devices that display meeting details scheduled via Teams or Outlook 365 calendaring applications. With meeting details prominently displayed, attendees can confirm they’re in the right meeting space, at the right time, and for the right meeting.

This article provides an overview of Teams panels and can help you plan, deliver, and manage Teams panels devices in your organization.

## Features supported by Teams panels

Teams panels support the following features:

- **Dedicated display of meeting space and meeting details.** You get at-a-glance details about a meeting space, including its location and availability. For a reserved meeting space, you can see key meeting details, such as meeting title, meeting schedule, and meeting organizer.
- **Reserve available meeting spaces for ad hoc meetings.** Using the touchscreen panel, you can reserve an available meeting space on the spot for an ad hoc meeting, and *join* that Teams meeting from the in-room Microsoft Teams Rooms or Surface Hub devices.
- **Color-coded indicators for space availability status.** You can see meeting space availability from afar and up close with vibrant LED and Home screen indicators. Green indicates that the meeting space is available, and if necessary, you can reserve it right from the panels itself. Red or purple indicates that the meeting space is reserved.
- **Customize wallpaper and reserved state indicator.** Admins can change the default look of the panels through settings. For example, admins can change the background wallpaper, or change the color of the busy state indicator.
- **Accessibility.** Teams panels have several accessibility features, such as high contrast text, to make it easier for anyone to use them.

To learn more about these features and how to use them, see [Use Microsoft Teams panels](use-teams-panels).

## Partners certified for Teams panels

To learn more about partners certified for Teams panels, see [Certified Teams panels](teams-panels-certified-hardware).

## Teams panels requirements

The hardware, software, and network requirements to deploy panels devices may differ depending on which type of panels devices you're deploying. Refer to the Original Equipment Manufacturer (OEM) documentation to know what's required for your set of devices.

Teams panels are supported in the following Microsoft Cloud environments:

- Worldwide
- GCC
- GCC-H

## License requirement

Each Teams panel needs a [Microsoft Teams Rooms Pro license](../rooms/rooms-licensing) or a [Teams Shared Device license](../teams-add-on-licensing/teams-shared-device-license). The license you use depends on how you're going to use your Teams panel:

- **Teams Rooms Pro** - Use this license if your meeting room has a Teams Rooms system or a Surface Hub. You can share one Teams Rooms Pro license with one Teams Rooms system or Surface Hub and your Teams panel. For more information, see Resource account provisioning.
- **Teams Shared Device** - Use this license if your meeting room doesn't have a Teams Rooms system or Surface Hub.

## Deploy Teams panels devices

If you're involved in planning, deploying, and managing Teams panels devices, then this section is for you. This section isn't intended for the end users of Teams panels.

Deployment of Teams panels devices can be broken down into the following tasks:

- Meeting space inventory and capability planning: Create an inventory of your organization’s sites and meeting spaces for deploying Teams panels devices.
- Procurement: Procure the devices from your selected device partner.
- Site readiness: Confirm that your deployment locations (meeting spaces) meet the deployment requirements.
- Configuration and deployment: Create resource accounts and assign them to the devices.

## Inventory sites and meeting spaces

Take an inventory of the existing bookable meeting spaces in your organization. Identify the sites and meeting spaces that are in scope for deploying Teams panels. Work with your facilities and audio-visual teams to determine where and how to install the Teams panels devices, and if any additional hardware is needed for mounting the panels.

## Procurement

Based on the number of meeting spaces that are in scope for deploying Teams panels, procure the devices from one of the partners certified for Teams panels. Visit the partners’ websites to learn more about the devices and procurement options.

Meeting spaces in your organization may have different hardware requirements for installing or mounting the devices. For example, hardware required for mounting the device on a glass, plaster, drywall, or wood paneling may not be the same. Refer to the device partner's documentation for available mounting options.

## Site readiness

While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and meeting space is ready in terms of power and networking.

Our recommendations for Teams panels sites are:

- Dedicated resource accounts
- Power supply (Panels generally support Power over ethernet plus (PoE+) for power. Refer to the OEM documentation for any device-specific power requirements.)

For physical installation considerations, see the OEM documentation and, if you have one, use the experience of your audio-visual team before you install and mount devices and run cabling.

## Configuration and deployment

Planning for configuration and deployment covers the following key areas:

- Resource account provisioning
- Testing

### Resource account provisioning

Every Teams panels device requires a Microsoft 365 room resource account. You use the resource account credentials to sign in to Microsoft Teams app on the panels device.

To set up a Microsoft 365 resource account for Teams panels, you need to purchase a Microsoft Teams Rooms license. For information on how to create a resource account and assign a license to it, see [Create resource accounts for rooms and shared Teams devices](../rooms/create-resource-account).

Note

- If you already have a room resource account set up for the meeting space where you're installing panels, use the same room resource account to sign in to the panels device. However, make sure that the room resource account has a Microsoft Teams Rooms license assigned to it in order to use it as panels resource account.
- If you already have a Microsoft Teams Rooms deployed in the meeting space where you're installing Teams panels, you don't need to purchase a separate license for deploying panels. The admin signs in to the panels device with the same credentials as the Microsoft Teams Rooms for the same space.
- For large meeting spaces, such as board rooms or conference rooms, with multiple entrances, you can mount one panels device at each entrance. Multiple panels that belong to a single meeting space share the same resource account and sign in with the same credentials. You don't need to create separate resource accounts for each panels for the same space.

Tip

It is recommended to create the resource account well in advance of the actual Teams panels installation. Consider using naming conventions for the Teams panels resource account. Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand. These are the names that users will see when they search meeting spaces while scheduling meetings in Outlook or Teams calendars.

### Testing

After you've deployed panels, you should test them. Check that the features supported by Teams panels are working on the deployed device. Try creating several meetings for various time slots via Teams or Outlook 365 on your computer. Check if the panels correctly display the meeting details and availability for the scheduled meetings. Try using the **Reserve** button to check if you can reserve an available meeting space directly from the device.

## Manage Teams panels in your organization

To manage your Teams panels devices, in the left navigation of the Microsoft Teams admin center, go to **Teams Devices** &gt; **Panels**. From here, you can change the device configuration profile, manage updates, restart devices, add and remove device tags, and more. For more information, see [Manage your devices in Teams](device-management).