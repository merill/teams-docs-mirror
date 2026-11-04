---
layout: Conceptual
title: Bring Your Own Device Rooms in Pro Management Portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/bring-your-own-device
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: eshanmathur
ms.date: 2026-06-23T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: itpro-rooms
audience: Admin
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use Bring Your Own Device rooms feature in the Pro Management Portal
f1keywords: 
locale: en-us
document_id: 6e2f90a7-234b-862a-d9ca-15797a25b383
document_version_independent_id: 6e2f90a7-234b-862a-d9ca-15797a25b383
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/bring-your-own-device.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/bring-your-own-device
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/bring-your-own-device.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 360e3940-975b-dba1-5d12-a0fbf13cd89b
---

# Bring Your Own Device Rooms in Pro Management Portal - Microsoft Teams | Microsoft Learn

Bring Your Own Device rooms are identified as rooms with no Microsoft Teams Rooms. As an admin, you'll be able to:

1. View the inventory of BYOD rooms and peripherals in your tenant.
2. Associate BYOD rooms and peripherals together, or view auto-associated rooms and peripherals. *Users who plug-in room associated peripherals will have [BYOD end user experiences automatically activated](https://support.microsoft.com/office/use-shared-display-mode-in-meeting-rooms-a59c6886-9028-44da-a3cc-5563be40a214) for the best meeting room experience.*
3. View usage, quality, and peripheral status reports for BYOD rooms.

Note

To have access to the portal, you'll need at least one pro, premium, or Teams Shared Device (TSD) license.

## A Critical Concept: Peripheral Association

The BYOD rooms management solution uses the core concept of **association** between room peripherals and room resource accounts to create manageability and drive value for your organization.

A BYOD peripheral may be associated to a BYOD room in Pro Management portal. It can't be associated to more than one room. This association is anchored around a peripheral ID, which is a combination of the peripheral's product ID, vendor ID, and serial number.

When a peripheral is associated to a BYOD room, the Teams client application on your users' computer will send device signals required to construct this peripheral ID along with usage, quality, and peripheral status information. This usage, quality, and status information is then treated as the same for the peripheral's associated BYOD room, if there's one.

In addition, this association proves to the system that the peripheral is in a meeting room, allowing Teams to automatically activate BYOD end user experience features that optimize the client application for meeting room scenarios. [Learn more.](https://support.microsoft.com/en-us/office/use-shared-display-mode-in-meeting-rooms-a59c6886-9028-44da-a3cc-5563be40a214)

There are two ways in which this association can happen, discussed later in the article:

1. Manually associate peripherals to rooms individually
2. Let Pro management portal automatically associate peripherals for you (recommended)

Warning

In order for a BYOD peripheral to be manageable in Pro Management portal, the serial number must be unique. Check with your peripheral manufacturer to see if the peripherals used in your organization satisfy this requirement. You may find that some are unique and some aren't, varying by manufacturer and even device model or firmware version.

## Auto association

In order to reduce manual work required to build and maintain your BYOD inventory, Pro Management portal is capable of automatically associating peripherals to BYOD rooms by using signals provided by the Teams client application when users plug those peripherals into their computers and take meetings that have room bookings.

An auto associated room or peripheral is denoted by the blue sparkle iconography as shown below.

![Auto Association L1.](media/bring-your-own-device/auto-association-l1.png)

While Microsoft doesn't require nor recommend manual verification of auto associations, we have provided a tracking functionality for your organization should that be useful. Clicking on the blue sparkle symbol marks a room or peripheral as verified, turning the symbol's blue fill solid. Clicking on it again unverifies it. If a room is marked as verified, all of its associated peripherals are also marked as verified.

Auto association requires that multiple unique users provide these signals in order to ensure accuracy. The threshold for how many signals it requires before associating is configurable, so you can decide the right balance of association speed and accuracy for your organization, with a minimum of five unique signals and no maximum.

Microsoft encourages all organizations to make their BYOD rooms bookable in Exchange instead of using third party booking solutions to ensure maximum compatibility with auto association and BYOD management. Admins may also wish to encourage their users to book rooms when taking meetings to provide more signals for auto association.

Warning

Auto association only works for rooms that have a room account, are bookable via Exchange and visible in the GAL, and has audio, video, display, or dock peripherals with unique serial numbers.

## Viewing your BYOD Inventory

1. Open Pro Management Portal on https://portal.rooms.microsoft.com/
2. In the left navigation menu, select **Planning** and then the **Inventory** option.

In the **Inventory** page, you'll find all the BYOD rooms and peripherals within your organization. There are two main tabs under **Inventory**: **Rooms** and **Devices**. The **Rooms** tab allows you to explore all of your rooms (including BYOD rooms, Microsoft Teams Rooms, and other). The **Devices** tab is a flat list of all your BYOD Room and Bookable Desk peripherals.

### Rooms view

[![Screenshot of Inventory rooms tab.](../media/byod/inventory-rooms-tab.png)](../media/byod/inventory-rooms-tab.png#lightbox)

The summary metrics show how many rooms of each type you have in your organization.

Important

A BYOD room is defined as any room that doesn't have a meeting enabled compute. In the Pro Management portal specifically, that means **any room that does not have a Microsoft Teams Room** or Surface Hub. These rooms may or may not have peripherals associated to them. Room accounts are pulled from the Microsoft Admin Center and Exchange. A BYOD room that is hidden in the GAL won't appear in this view, nor is it manageable via the Pro Management portal.

- The following table describes the columns in the **Rooms** view of the Inventory. The Monitored and Planned columns aren't relevant for BYOD rooms.

    | Column | Description |
    | --- | --- |
    | Display name | Name of the room |
    | Capacity | Illustrate the room's capacity number |
    | Room type | Type of the room either Teams Rooms or Bring Your Own Device |
    | Monitored | Not relevant for BYOD rooms |
    | Planned | Not Relevant for BYOD rooms |
    | License Type | Type of license assigned to the room (e.g., Pro, Premium, Basic, Standard, Shared Device License, or Unlicensed) |

When you click on a room, you'll see the Room detail view.

#### Room detail view:

When you select a specific room, you'll see a new pane with two different pages, **General** and **Inventory** page.

- **The General tab** provides the following room information:

| Field | Description |
| --- | --- |
| Name | The name of the room |
| Seating Capacity | The room's capacity |
| Device type | Not relevant for BYOD rooms |
| OEM name | Not relevant for BYOD rooms |
| Account | The room resource account associated with the room in Exchange |
| Address | The physical address of the room (street, city, zip code, building, floor) |

- **The Inventory tab** displays detailed information about the room's devices. "Manage assets" isn't relevant for BYOD rooms.

| Column | Description |
| --- | --- |
| Name | Name of the device |
| Type | Type of device (for example, Microsoft Teams Rooms, TeamsPanel, camera.) |
| Make | Manufacturer name |
| SerialNumber | The device's serial number |

### Devices view

[![Screenshot of Device view.](../media/byod/device-view-latest.png)](../media/byod/device-view-latest.png#lightbox)

The Device page offers a flat, searchable list of both BYOD and Bookable desk peripherals.

The peripherals are grouped by plug-in, which means if they're plugged in together, they're displayed as a group with the first device name as the primary device shown in the main table. When a peripheral is manually associated with a room, all of the other peripherals in its group also associate to that room. The **Number of devices** column shows the number of peripherals in the group.

Select the device to either view more details about peripherals in that group, or manually associate that group to a BYOD room or bookable desk.

#### Device detailed view:

When you select a specific peripheral group associated with a room, a new page opens up displaying the following two tabs:

- **Configuration**: This page displays information about the devices in the group including device serial number, product and vendor ID. Under the device information, the button "**Add room or desk**" can be used to associate the peripheral to a BYOD room or bookable desk. Once the devices get added to the specific room, the room's information will also be displayed such as the room's name, capacity, location and license type.
- **Usage details**: This page shows the room's usage report data for the selected period and is accessible with a Teams Shared Device license assigned to the room resource account.

-[![Screenshot of device room association.](../media/byod/device-discovery.png)](../media/byod/device-discovery.png#lightbox)

#### Peripheral Auto Discovery and the Personal Device Filter

Peripherals are automatically discovered using your users' Teams client to send device data to Pro Management portal. When a user enters the prejoin screen of a meeting, any connected displays and USB audio/video peripherals are scanned and transmitted to the cloud. These peripherals populate your Devices tab within the Inventory navigation.

In order to ensure no personal peripherals get discovered or shown to admins, Pro Management portal uses a **personal device filter**. This filter requires that each peripheral be used by at least **five** unique users internal to the same organization before making the peripheral available for management.

Warning

Be aware that Microsoft can't guarantee that peripherals provide unique data like serial numbers, and this may cause errors or overcounting of usage. We recommend working with your OEM partners to ensure that your peripherals are providing unique serial numbers to the operating system via the USB descriptor or EDID. For composite audio video peripherals like AV bars, Teams looks at the audio component for peripheral information.

## Enabling automatic work location updates

You have the option to [enable the automatic work location update policy](/en-us/powershell/module/teams/new-csteamsworklocationdetectionpolicy) for your organization or for a group of users. Automatic work location updates are designed to enhance the end user experience by making it easier to keep their work location up-to-date and connect with others when they are in the office. With the policy enabled, users will have the option to enable automatic work location updates. They can do so in Teams desktop client under **Settings** &gt; **Privacy** &gt; **Sharing your work location**. After users have opted-in, their work location will automatically update to **In the office** when they connect to a BYOD room, provided their work location was previously set to unknown or remote. The detected location will last until the end of their working hours. If they plug in after work hours, the location will be set until 11:59pm that day. This feature allows for a seamless transition between remote and in-office work, which enhances collaboration and communication within your team and other users.

## Usage, Quality, and Peripheral Status Reports

Important

A Teams Shared Device license is required to unlock the Bring Your Own Device room usage report. For more information about the Teams Shared Device, see [Microsoft Teams Shared Devices licensing - Microsoft Teams | Microsoft Learn](../teams-add-on-licensing/teams-shared-device-license).

To view the report for your Bring Your Own Device rooms:

1. In the left navigation menu, select **Reports**.
2. In the Reports page, select the **BYOD** tab.

    [![Screenshot of Usage Report.](../media/byod/usage-report.png)](../media/byod/usage-report.png#lightbox)

    The headlines provide few rooms’ insights described in the following table:

    | Metrics | Description |
    | --- | --- |
    | **BYOD rooms** | Total number of Bring Your Own Device rooms |
    | **Unused rooms** | Number of Bring Your Own Device rooms with no calls |
    | **Utilization** | Percentage of utilization of all Bring Your Own Device rooms across the tenant.  Utilization = Total call duration (all rooms) / (Workdays \* workday hour \* Bring Your Own Device rooms)  For example: If the tenant has 15 Bring Your Own Device Rooms, total call duration for all rooms is 300 h, work days = 10, work day hour = 8 h; then Utilization = 300/(10\*8\*15)= 25% |

    Below the headline metrics, there's a table that provides a granular breakdown of individual Bring Your Own Device rooms, accompanied by specific metrics that illuminate each room’s usage, performance, and peripheral status during the period selected.

    | Column | Description |
    | --- | --- |
    | **Display name** | The designated name of the Bring Your Own Device room |
    | **Utilization** | The percentage of total meeting duration spent in a Bring Your Own Device room during business hours in the selected period.  For example, for a time period set to 10 Work days for room A, total meeting duration for room A is 12 h and Work Day Hour = 8 h; then room utilization = Total Meeting Duration in Room / (Work Days \* Work Day Hour) = 12/(10\*8) = 15% |
    | **Meeting performance** | Percentage of meetings rated as “Good” out of the total meetings in the room. Each meeting is evaluated and receives a Good, poor, Unknown rating. |
    | **Total meetings** | Total count of meetings conducted in the room during the specified timeframe |
    | **Peripheral Status** | Tells you if a peripheral that is usually seen in the room is offline or has been moved to another room so you can proactively react to issues |

### Peripheral State Detection (Offline, Moved)

BYOD reports now run a best effort detection algorithm designed to help you understand when peripherals in your rooms are offline or have moved to a different room.

In a nutshell, the system looks for a break in typical patterns, e.g. if peripherals A, B, and C are seen consistently alongside each other and are associated to Room 123, if peripheral B were to suddenly stop sending signals during usage, the report would flag peripheral B as being potentially offline.

The system also looks for a peripheral that moved from one room to another via auto-association. In this case, the peripheral will be marked as moved.

### Bring Your Own Device utilization detailed view

To see the utilization view for each room, select the specific Bring Your Own Device room from the table. There will be a new pane, which gives a detailed view of device utilization based on the selected period.

Note

Only rooms with Teams Shared Devices or Pro licenses are shown in the Bring Your Own Device usage report. Additionally, for any usage to be captured, rooms must have their peripherals associated to them (see above) for the system to garner signals about room usage.

## Settings

## Access Control & Configuration

### Turning off automatic discovery & usage data collection in the Teams client

The Teams BYOD solution uses peripheral data crowdsourced from the Teams client application running on user's computers to discover peripherals as well as understand when those peripherals (and the rooms they're associated to) are used. No personally identifiable data is collected, but should you feel that this data collection is inappropriate for certain users or groups in your organization, you may use the following PowerShell commands to configure this policy.

First, ensure that your TPM version is &gt; 6.5.0 by running the following commands:

```powershell
Import-Module MicrosoftTeams
Get-Module -Name MicrosoftTeams
```

If your version is older than 6.5.0, [follow the instructions here](/en-us/microsoftteams/teams-powershell-install) to update.

Use the following commands to create, set, or remove a setting in `CsTeamsBYODAndDesksPolicy`. The following example configures the `DeviceDataCollection` setting.

```powershell
Import-Module MicrosoftTeams
Get-CsTeamsBYODAndDesksPolicy
New-CsTeamsBYODAndDesksPolicy -Identity "Test"
Set-CsTeamsBYODAndDesksPolicy -Identity "Test" -DeviceDataCollection Disabled
Set-CsTeamsBYODAndDesksPolicy -Identity "Test" -DeviceDataCollection Enabled
Remove-CsTeamsBYODAndDesksPolicy -Identity "Test"
```

#### Device Data Collection

You can enable or disable BYOD data collection via a Teams policy setting. The setting name is `DeviceDataCollection`.

Warning

Disabling this setting for certain users will cause BYOD and desk information to cease flowing to the service. The Teams BYOD and Desk solution requires peripheral data sent from users to automatically activate [BYOD end user experiences](https://support.microsoft.com/en-us/office/use-shared-display-mode-in-meeting-rooms-a59c6886-9028-44da-a3cc-5563be40a214) and generate reports for BYOD peripherals, BYOD rooms, and Bookable Desks.

### Configuring Cloud Data

**BYOD Rooms and Desk management**

This setting option is located under the **General** tab in Teams Pro Management portal and controls if peripheral data is ingested into the cloud service. This feature is currently enabled by default, but admins have the option to disable it with this function. Disabling this setting will stop showing any reports for BYOD rooms or Desks, and also remove the display of any devices in the **Inventory** section, though those devices will continue to exist in the database.

**Delete Device Data**

This setting option enables admins to delete all device management data for a specific user.

### Inventory management permission

The inventory management permission in Teams Pro Management portal allows other users to view and manage the inventory management. You can create roles and grant other users permission to access inventory management and associate peripherals to rooms or desks.

### Configuring Auto Association

Auto association can be turned off for your organization in Pro Management portal's settings. In addition, the threshold for how many signals it requires before associating is configurable, so you can decide the right balance of association speed and accuracy for your organization, with a minimum of five unique signals and no maximum.