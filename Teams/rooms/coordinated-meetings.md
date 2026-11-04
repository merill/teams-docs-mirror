---
layout: Conceptual
title: Set up coordinated meetings between multiple Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/coordinated-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: kramachandra
ms.date: 2026-04-30T00:00:00.0000000Z
audience: Admin
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Configure multiple Teams Rooms devices to join meetings when one device or the other joins a meeting.
locale: en-us
document_id: 94992f4d-eb18-400e-5979-5301f9b4a6d7
document_version_independent_id: 403c8366-9324-cf9e-332a-f55a554375dd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/coordinated-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/coordinated-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/coordinated-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 669fc2f5-ff13-f324-28b7-9d4af619ae24
---

# Set up coordinated meetings between multiple Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

If you have one or more Microsoft Teams Rooms on Windows devices in a meeting room, you can set up Coordinated Meetings. Coordinated Meetings lets you set up your Teams Rooms on Windows devices so that when you join a meeting on one device, the other devices in the room are also joined to the same meeting. Configure your cameras, speakers, and microphones so that the ones that give participants the best experience are enabled to avoid echo and feedback noise participants can experience when adding multiple devices to a meeting.

To set up Coordinated Meetings, you need to make sure your Teams Rooms on Windows devices are already correctly configured to participate in meetings. Most importantly, each device needs to have its own Teams Rooms resource account. For information on how to set up the accounts: [Click Here](rooms-deploy).

The following steps should be completed for each meeting room separately.

## Step 1: Plan your Coordinated Meeting experience

Before you make any configuration changes, you need to decide which devices will do what in each meeting room. That is, for a given meeting room, you need to decide which device will have the active microphone, camera, and whiteboard. How you configure your devices depends on your specific environment, but here are some general recommendations to start with:

- **Microphone:** Primary device that has an audio system capable of covering the full meeting space
- **Camera:** Primary device that has a camera or camera system capable of covering the full meeting space
- **Whiteboard:** Device that has an interactive touch screen

Important

Make sure you enable the microphone only on one device. If you enable it on more than one device, you'll experience audio echo and feedback.

## Step 2: Get your devices' user principal names (UPNs)

When you set up the Coordinated Meeting experience, you need to tell the Teams Rooms on Windows devices in that room which devices to coordinate with. This is done by adding the user principal name (UPN) of the devices it should coordinate with to its configuration. If you don't know the UPNs for each of the devices you want to set up for Coordinated Meetings, you can find them using the [Pro Management Portal](/en-us/microsoftteams/rooms/inventory) inventory.

## Step 3: Create a deployment worksheet

After you've planned your Coordinated Meeting experience and gathered a list of your devices' UPNs, it's a good idea to create a deployment worksheet. A deployment worksheet helps to visualize the configuration you want to set across all of your devices, allowing you to validate your choices and check for errors.

In a spreadsheet app, add rows for the following in the first column:

| Setting | Description |
| --- | --- |
| **Audio default** | Determines on which device the microphone will be active when a meeting starts. Only one device can have this field set to `true` while the rest of the devices must have this field set to `false` to avoid audio echo and feedback. |
| **Audio enabled** | Determines whether participants in a meeting can toggle the microphone on or off. Devices on which **Audio default** is set to `false` should have this setting set to `false` so that participants can't accidentally turn on a microphone and cause audio echo or feedback.<br>If **Audio default** is set to `true`, this setting is ignored and participants can mute or unmute the microphone. |
| **Video default** | Determines on which device the camera will be active when a meeting starts. For the best experience, we recommend that only the primary Teams Rooms device be set to `true` while all other devices are set to `false`. |
| **Video enabled** | Determines whether participants in a meeting can toggle the camera on or off. You can set this to `true` on any other devices in the event participants want to share different video perspectives (such as if a participant is using the whiteboard on a secondary device). If you don't want participants to turn a camera on or off on a device, set this to `false`.<br> If **Video default** is set to `true`, this setting is ignored and participants can turn the camera on or off. |
| **Whiteboard default** | Determines whether the Teams Rooms device will display a whiteboard shared by one of the meeting participants. |
| **Trusted accounts** | This is a comma-separated list of UPNs for each Teams Rooms device or Surface Hub that the device should accept meeting join requests from, or to which meeting join requests should be sent. |

In subsequent columns, add each of your Teams Rooms on Windows devices. In each column, fill out the values that correspond to the experience you want for the meeting room. Here's an example using a Teams Room as the primary device and a Surface Hub 3 as the secondary whiteboarding device:

- Teams Room
    - Audio and video are turned **on** when a meeting starts. Participants **can** toggle audio and video on or off.
    - Displaying a shared whiteboard is turned off.
- Surface Hub 3
    - Audio is turned **off** when a meeting starts. Participants **can't** toggle audio on or off.
    - Video is turned **off** when a meeting starts. Participants **can** toggle video on or off.

| Setting | Teams Room | Surface Hub 3 |
| --- | --- | --- |
| **Audio default** | `true` | `false` |
| **Audio enabled** | `true` | `false` |
| **Video default** | `true` | `false` |
| **Video enabled** | `true` | `true` |
| **Whiteboard default** | `false` | `false` |
| **Trusted accounts** | hub@contoso.com | room@contoso.com |

## Step 4: Configure Teams Rooms on Windows devices

You can either set up Coordinated Meetings on a Teams Rooms device using the device's touch screen or within the [Pro Management Portal](/en-us/microsoftteams/rooms/pro-portal-settings).

Use the worksheet you created in the previous step to help you set up your devices.

### Use the Teams Rooms device's touch screen

To set up Coordinated Meetings on a device, do the following:

1. Select **... More** &gt; **Settings**.
2. Enter the Administrator password and select **Yes**.
3. Select **Coordinated Meetings**.
4. Under **Options**, set **Coordinated Meeting** to *on*.
5. If **Audio default** in your worksheet is `true`, set **Turn on this device's microphone** to on, otherwise leave it *off*.
6. If **Audio enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's microphone**. This option can't be turned off if **Turn on this device's microphone** is set to on.
7. If **Video default** in your worksheet is `true`, set **Turn on this device's camera** to on, otherwise leave it *off*.
8. If **Video enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's camera**. This option can't be turned off if **Turn on this device's camera** is set to *on*.
9. If **Whiteboard default** in your worksheet is `true`, set **Turn on whiteboarding on this device** to *on*, otherwise leave it *off*.
10. Under **Trusted device accounts**, type each UPN listed in **Trusted accounts** in your worksheet. Separate multiple UPNs with commas.
11. On the trusted device, turn off proximity and room remote.
12. Select **Save and exit**.

After you select **Save and exit**, the device will restart and it'll be ready to participate in Coordinated Meetings.

### Use the Teams Rooms Pro Management Portal

1. Log in to the Teams Rooms [Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service) to use [settings management](/en-us/microsoftteams/rooms/pro-portal-settings#coordinated-meetings)
2. Select the **Rooms** tab
3. Select your primary meeting room device
4. Select **Settings**
5. Select **Coordinated Meetings**
6. Configure your desired settings as outlined in your worksheet from step 3
7. Select Apply
8. Select your secondary meeting room device
9. Select **Settings**
10. Select **Coordinated Meetings**
11. Configure your desired settings as outlined in your worksheet from step 3
12. Select Apply

After the settings have been applied to both devices, it'll be ready to participate in Coordinated Meetings.

## Step 5: Test the configuration

Once all of your configuration is complete, schedule a Teams Meeting with the primary device's account and then select the join button on the Teams Room. Your Primary device should bring your secondary device into the meeting, if not, review your configuration and try again.