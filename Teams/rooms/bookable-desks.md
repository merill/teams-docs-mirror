---
layout: Conceptual
title: Setting up Bookable Desks in Microsoft Teams  - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/bookable-desks
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: altonk
ms.date: 2026-09-03T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.localizationpriority: medium
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Rooms
- Tier1
ms.custom: QuickDraft
search.appverid: MET150
f1.keywords:
- NOCSH
description: Helps admins set up Bookable Desks for their Microsoft Teams organization.
locale: en-us
document_id: ed3355d3-8715-ecd6-fd77-fdf68a750442
document_version_independent_id: ed3355d3-8715-ecd6-fd77-fdf68a750442
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/bookable-desks.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/bookable-desks
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/bookable-desks.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ae4d2473-4d01-d233-15ad-ffcb8e7c14c1
---

# Setting up Bookable Desks in Microsoft Teams  - Microsoft Teams | Microsoft Learn

Unlock the full potential of your desks with Microsoft Teams. Bookable desks in Microsoft Teams are designed to enhance the efficiency of your organization by enabling users to seamlessly reserve desks upon plug-in to peripherals. Bookable desks also provides you with the tools to understand and manage those spaces.

## Overview of steps

To set up and use Bookable Desks in your organization, you must perform these tasks:

- Step 1: Review the prerequisites.
- Step 2: Create resource accounts.
- Step 3: Collect information on peripheral devices on each desk such as a monitor.
- Step 4: Enable additional features for users.
- Step 5: Verify the user experience.
- Step 6: Review data in usage reports.

## Step 1 - Review the prerequisites

- Confirm you have access to the Microsoft Teams Pro Management portal.
- Ensure your users have access to the new version of Microsoft Teams desktop app on Windows or Mac.
- Ensure your users have the **Bookable desks** app installed in Microsoft Teams. The app should be installed by default. You can check for it being listed in Teams desktop client under **Settings** &gt; **App permissions**.
- If you're planning to use individual desks, make sure your M365 Billing Administrator has acquired the [Microsoft Teams Shared Space and Shared Space - Single Space licenses](/en-us/microsoftteams/teams-add-on-licensing/teams-shared-device-license) that will be required for the desk accounts.

## Step 2 - Create Desk Pool or Individual Desk Accounts

Desk pool accounts, known as **'workspaces'** in Exchange, are slightly different from room accounts. The capacity of a desk pool represents the number of seats in that pool and the admin sets this capacity. Multiple users can reserve the pool at the same time until all seats (the capacity) are taken. For example, the capacity on a desk pool is set to 2. User A and User B are both able to reserve it from 8am to 5pm, and the remaining capacity is 0. This setting means that a third user can't reserve it between 8am and 5pm.

On the other hand, individual desks, known as **'desk'** in Exchange, represents a specific seat in the office. If a user reserves the individual desk, that specific seat is theirs. Microsoft recommends setting up individual desks over desk pools for a better bookable desk user experience, more detailed utilization analytics, and more management capabilities.

To create a desk pool or an individual desk account, you need to set up the resource account in Exchange. We recommend following the steps outlined in [Configure desk booking](/en-us/microsoft-365/places/configure-desk-booking?branch=main#configure-desk-pools).

After you create the account, allow 24 to 48 hours for the account to appear in Outlook, Teams, and Teams Rooms Pro Management Portal.

## Step 3 - Collect information on peripheral devices

Next, to ensure a seamless user experience, peripherals such as the monitors on the physical desks need to be associated or linked to the desk pool or individual desk account you created earlier. The peripherals need to be identified based on their unique information such as product ID, vendor ID, and serial number. There are two approaches for this identification.

One approach is to manually collect the peripheral information. You can use a free PowerShell script to fetch the details of a peripheral and ensure they're mapped to the corresponding desk pool or individual desk accounts in the Teams Rooms Pro Management portal. The PowerShell script is located [here](https://www.microsoft.com/download/details.aspx?id=106063)to download, and for detailed step-by-step instructions, see [Add peripherals to inventory](/en-us/microsoftteams/rooms/get-peripheral-information). This approach is supported for both desk pools and individual desks.

The other approach is to wait for Teams Rooms Pro Management portal to associate the peripheral automatically. This automation is done by using signals provided by the Teams desktop client application when the users reserve the desk and plug the peripherals into their computer. The blue sparkle iconography denotes an auto associated desk or peripheral, as shown in the following graphic. This approach is only supported for individual desks at this time.

[![Screenshot that shows automatic association.](media/bookable-desks/automatic-association-image.png)](media/bookable-desks/automatic-association-image.png#lightbox)

Microsoft neither requires nor recommends manual verification of auto associations. However, we provided a tracking functionality for your organization if you need it. Selecting the blue sparkle symbol marks a desk or peripheral as verified, turning the symbol's blue fill solid. Selecting it again removes the verification. If a desk is marked as verified, all of its associated peripherals are also marked as verified.

Auto association requires that multiple unique users provide these signals in order to ensure accuracy. The threshold for how many signals it requires before associating is configurable on Teams Rooms Pro Management portal at **Settings** &gt; **General**. You can decide the right balance of association speed and accuracy for your organization, with a minimum of two unique signals and no maximum.

Important

Bookable desks only support peripheral devices that correctly report a unique device serial number to Teams. You can use the [PowerShell script](https://www.microsoft.com/download/details.aspx?id=106063) to verify whether a device reports its serial number correctly. A peripheral device is not supported if its serial number cannot be collected, is not unique, or contains special characters.

## Step 4 - Enable additional features for users

You can [enable the automatic work location update policy](/en-us/powershell/module/teams/new-csteamsworklocationdetectionpolicy) for your organization or for a group of users. Automatic work location updates are designed to enhance the end user experience by making it easier to keep their work location up-to-date and connect with others when they are in the office. With the policy enabled, users can enable automatic work location updates. They can do so in Teams desktop client under **Settings** &gt; **Privacy** &gt; **Manage my work location**.

After users have opted-in, their work location automatically updates to **In the office** when they connect to a bookable desk, provided their work location was previously set to unknown or remote. If the desk pool or individual desk is parented to a building, their work location can also change to a specific building when they connect to a bookable desk. This automatic change happens if their work location was previously set to *Unknown*, *Remote*, or *In the office* and have not been manually changed during the work day.

The detected location lasts until the end of their working hours. If they plug in after work hours, the location is set until 11:59 PM that day. This feature allows for a seamless transition between remote and in-office work, which enhances collaboration and communication within your team and other users.

## Step 5 - Test the end user experience

Wait 24 hours after associating to test this experience. After that point, ensure that you're signed into Teams on a Windows or Mac laptop. Plug the laptop into a peripheral you associated to a desk pool or individual desk account. If there's availability to book, you should then receive an activity feed notification that 'The [space or desk] is reserved and ready for you' along with a booking in your calendar. You can also reserve the desk for a future time slot. To learn more on the end user experience, see [First things to know about bookable desks in Microsoft Teams](https://support.microsoft.com/office/first-things-to-know-about-bookable-desks-in-microsoft-teams-5d10c217-1205-48a1-a883-ff4533f4ae71?preview=true).

## Step 6 - Review data in usage reports

Once the end-user experience is working, you can start to review usage reports to see how your individual desks or desk pools are being used. Desk usage reports are located in the **Teams Rooms Pro Management portal** &gt; **Analytics & Reports** &gt; **Reports** &gt; **Desks usage**.

On the report page you can:

- Change the date range to view usage metrics for different time periods.
- Search for specific desks by display name or resource account.
- Export desk usage details metrics as a csv file.

### Summary metrics

The following summary metrics are available. Metrics only measure usage between 8:00 AM to 5:00 PM on weekdays.

| Metrics | Definition |
| --- | --- |
| Total unused desk pools | The total number of desk pools with 0% utilization. |
| Total unused desks | The total number of individual desks with 0% utilization. |
| Unplanned reservations | The percentage of reservations across desk pools and individual desks that weren't reserved in advance and were automatically booked when users connected to desk peripherals. |

### Desk usage details

Below the summary metrics, a table provides a breakdown of usage for each desk and desk pool. Again, metrics only measure usage between 8:00 AM to 5:00 PM on weekdays.

| Column | Description |
| --- | --- |
| Display name | The name of the individual desk or desk pool. |
| Type | Indicates whether the item is an individual desk or desk pool. |
| Utilization | The percentage of time that the individual desk or desk pool was reserved by users in the specified date range. |
| Reservations | The number of reservations for the individual desk or desk pool during the specified date range. |
| Unplanned reservations | The percentage of reservations that weren't made in advance and were instead created automatically by Teams when users connected to desk peripherals. |
| Reservation occupancy | The percentage of reserved time that users spent connected to the bookable desk. A lower value indicates that users spent less of their reserved time connected to the desk. |

### View detailed usage for a desk

Select a desk or desk-pool row to open its detailed usage report.

| Metrics | Description |
| --- | --- |
| Usage summary | Displays summary usage metrics for the selected individual desk or desk pool. |
| Peak utilization | A table that shows utilization percentages break down by day and hour. |
| Total meetings | The total number of Teams meetings in which the desk was used during the specified date range. |
| Average daily usage | The average amount of time per day that the desk was used for Teams meetings during the specified date range. |
| Meeting performance | The percentage of Teams meetings conducted at the desk that received a Good quality rating. Each meeting is evaluated as Good, Poor, or Unknown. |

## Settings

### Turning off automatic discovery and usage data collection in the Teams client

Bookable desks in Microsoft Teams use peripheral data crowdsourced from the Teams desktop client running on the users' laptops to discover peripherals. This data also helps you understand when those associated desk pools or individual desks are used. No personally identifiable data is collected. If you feel this data collection is inappropriate for your tenant or a group of users in your tenant, use the following PowerShell cmdlets to configure the policy appropriately.

Note

For government clouds, this policy is off by default.

First, ensure that your Microsoft Teams module is on version 6.5.0 or higher. To confirm the version, run the following command:

```powershell
Import-Module MicrosoftTeams
Get-Module -Name MicrosoftTeams
```

If you don't have the Microsoft Teams module installed, run the following command and then rerun the prior command to check the version:

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
Import-Module MicrosoftTeams
```

If your version is lower than 6.5.0, follow [these instructions](/en-us/microsoftteams/teams-powershell-install) to update it.

Use the following commands to create, set, grant, or remove a configuration in the TeamsBYODAndDesks policy:

```powershell
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
Get-CSTeamsBYODAndDesksPolicy
Set-CSTeamsBYODAndDesksPolicy -Identity Test -DeviceDataCollection Enabled
Grant-CSTeamsBYODAndDesksPolicy -PolicyName Test -Identity testuser@test.onmicrosoft.com
Grant-CSTeamsBYODAndDesksPolicy -Group 
Grant-CSTeamsBYODAndDesksPolicy -Global -PolicyName Test
Remove-CSTeamsBYODAndDesksPolicy -Identity Test
```

### Configuring cloud data

**Delete device data**

This setting enables admins to delete all device management data for a specific user.

**Inventory management permission**

The inventory management permission in Teams Rooms Pro Management portal allows others to view and manage the inventory. You can create roles under **Settings** &gt; **Roles** in Teams Room Pro Management portal and grant permissions to access inventory and associate peripherals to desks.

## Frequently asked questions

**Question: What are Desk Pools?**

**Answer:** Desk pools are a group of seats in the office that are close to one other and in the same area. When an employee books a desk in the desk pool, they're reserving a seat in the desk pool.

**Question: What is the difference between individual desks** **and desk pools?**

**Answer**: Individual desks are a new type of resource account in Exchange. This resource account allows a user to book a specific seat instead of booking one of the seats in a desk pool. Support for individual desks for Bookable desks in Teams released in April 2025. Microsoft recommends setting up individual desks over desk pools for a better bookable desk user experience, more detailed utilization analytics, and more management capabilities.

**Question: Is the bookable desks feature available in VDI?**

**Answer:** Yes, this feature set is supported in the [New VDI solution for Teams](/en-us/MicrosoftTeams/vdi-2).

**Question: Does Bookable** **desks work with Microsoft Places?**

**Answer**: Yes. If a user automatically reserves in a desk pool or at an individual desk, the booking also appears as the user's desk booking for the day in Places. If a user books a seat in a desk pool or individual desk in advance through Places, upon plug-in to a bookable desk, the user sees a confirmation message that they're all set for their reservation.

**Question: How can I be sure that it works with my devices? Do I need to buy new hardware?**

**Answer**: That's one of the benefits of Bookable desks. You don't need new hardware. We designed this solution with the goal of working with all models and manufacturers, and we expect each device has unique properties. We currently support monitor and devices with both audio and video capabilities. Support for docking stations and webcams is coming soon.

**Question: Is there another way I can associate my devices other than the PowerShell script or automatic association?**

**Answer**: Yes. You can also associate the device manually through the Pro Management portal. Navigate to **Planning &gt; Inventory &gt; Devices &gt;** select an unassociated device (one with a **Needs action** tag). Select **Add device to a room or desk** and search for the desired desk pool you want to assign the device to. To make it easier to discover devices, they're automatically discovered using your users' Teams app. Once two unique users have plugged into a device on a desk, it automatically surfaces in the **Devices** tab for association.

**Question: Which approach is better for association of individual desks?**

**Answer:** There's not one right way. It depends on how quickly you'd like to set up the association and how much manual effort you'd like to do. The PowerShell approach is a more manual method, but it's faster for spinning up your desks. The automatic approach is a less manual effort, but it can take longer depending on how often your users reserve desks.

**Question: What do I need to access usage reports?**

**Answer:** These reports are currently in preview and don't require a license to access.

**Question: Why is the individual desk I configured not appearing in Teams Rooms Pro Management Portal?**

**Answer:** First, make sure you followed the steps in [Configure desk booking](/en-us/microsoft-365/places/configure-desk-booking?branch=main#configure-desk-pools). If so, also make sure that enableBuildings is enabled for your tenant. If it isn't enabled, the desks don't show in the Pro Management portal. To check this setting, see [Get-PlacesSettings](/en-us/microsoft-365/places/powershell/get-placessettings). To change the value, see [Set-PlacesSettings](/en-us/microsoft-365/places/powershell/set-placessettings).

## Related links

- [First things to know about bookable desks for end users](https://support.microsoft.com/office/first-things-to-know-about-bookable-desks-5d10c217-1205-48a1-a883-ff4533f4ae71).