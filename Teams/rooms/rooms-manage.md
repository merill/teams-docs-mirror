---
layout: Conceptual
title: Managing Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-manage
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: ayerragangu
ms.date: 2026-07-15T00:00:00.0000000Z
ms.topic: how-to
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
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Learn about how to develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 5ad37b23-8b85-a502-f176-d90586c0a1c1
document_version_independent_id: dcc4aba8-e341-4f19-cd0a-4c99cd5ef3bf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-manage.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-manage
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-manage.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 79af67a1-a9ee-b1e0-9390-1931225a317f
---

# Managing Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

Important

Monitoring, managing, and updating Teams devices is moving to the Pro Management Portal. Review the transition guide [here](/en-us/microsoftteams/rooms/aboutunifieddevicemanagement-pmp1) to learn more and begin using the Pro Management Portal.

If you have Microsoft Teams Rooms device you can manage the devices in Microsoft Teams Rooms Pro Management Portal or Teams admin center.

- To manage Teams Rooms devices in Teams Rooms Pro Management, see [Microsoft Teams Rooms Pro Management Portal](rooms-pro-management). To manage devices using Teams Rooms Pro management, see the permissions required in: [Role-based access control in the Microsoft Teams Rooms Pro Management Portal](/en-us/microsoftteams/rooms/rooms-pro-rbac).
- To manage Teams Rooms devices in Teams Admin Center, open the [Microsoft Teams admin center](https://admin.teams.microsoft.com) and go to **Teams Devices**. To manage devices using the Teams admin center, you need to be assigned Teams Administrator or Teams Devices Administrator roles.

![Teams Rooms summary page in Teams admin center.](../media/teams-rooms-summary2.png)

## Management options in Teams Admin Center

### Device restart options

Changes to device settings will only take effect after the device has been restarted. When you make changes that need a restart, you can choose whether to restart immediately or schedule a restart. Here are the available restart options:

- **Immediate restart** If you choose this option, all of the devices you're making changes to will restart as soon as you select this option.
- **Scheduled restart**If you choose this option, you can restart the devices you're making changes to at a time that's less disruptive to your organization.
    - **Select date and time** - Choose the specific date and time to restart the device. The date and time you choose is local to the device being restarted.
    - **Leave update for nightly reboot** Devices are restarted nightly to perform maintenance. Changes you make to devices will be applied during this restart.

Caution

Teams Rooms and Surface Hubs that are in use at the time of a restart will become unavailable for the duration of the restart process. They'll be disconnected from in-progress meetings and won't be available to join new meetings while the device is restarting.

### Remove device

When you remove a device, the device is removed from your organization and no longer appears in your list of Teams Rooms on Windows or Surface Hubs in the Teams admin center.

If you remove a device and it's still configured with a valid username and password, it will be automatically re-added to your list of Teams Rooms or Surface Hubs if it connects to Microsoft 365 again.

To remove one or more devices, do the following:

1. Go to **Teams Devices** and select the devices you want to remove.
2. Select **Remove**.

### Download device logs

You can download a copy of a device's diagnostic log files if requested to do so by Microsoft support. Log files are compressed into a zip file that can be downloaded from the Teams admin center.

To download logs from a Teams Rooms device to your computer, do the following:

1. Go to **Teams Devices** and select the name of the device you want to download logs from.
2. Select **Download device logs**. It can take several minutes for device logs to become available.
3. Select the **History** tab and then select log file link under **Diagnostics file**. A zip file containing your device's diagnostic log files will be downloaded to your browser's default Downloads folder.

### Manage in-product surveys and call quality feedback

Teams Rooms devices may display in-product surveys, including call quality feedback prompts, to signed-in room accounts. To disable these surveys, use the Cloud Policy service for Microsoft 365. For more information, see [Manage user feedback in Microsoft Teams](../manage-feedback-policies-in-teams).

### View device information

From Teams admin center, you can view the overall status of all devices in your organization and view details of each device individually.

### Teams Rooms system dashboard

The Teams Rooms system dashboard shows you the status and health of all of your devices at a glance.

### Device details view

To view detailed information about a device, select its name from the device list. When in details view, you can see the following information about your device:

- **Health status** Shows the overall health of the Teams Rooms or Surface Hub device. Health status can be either **Healthy**, **Non-urgent**, **Critical**, or **Offline**.
- **Offline since** Shows the last time Microsoft 365 was able to communicate with the device.
- **Usage status** Shows the current state of the device: **Idle**, **Busy**, or **Unavailable**. Only for Teams Rooms on Windows.
- **Peripherals** Shows the peripherals connected to your Teams Rooms device and their health status. Health status can be either **Connected** or **Disconnected**. Only for Teams Rooms on Windows.
- **Health** Shows detailed information about the peripherals connected to your Teams Rooms device, network connectivity, sign in status to required services, and software version information.
- **Details** Shows manufacturer information, network IP address, and Teams Rooms device serial/MAC address.
- **Activity** Shows past meeting details including date and time of the meeting, number of participants, duration, and audio quality. For more information about meeting details, see the Meeting activity details section later in this article.
- **History** Shows a history of management activity on the Teams Rooms or Surface Hub device, including configuration updates, device restarts, and device log download links.

#### Meeting activity details

The **Activity** tab in device details shows high-level and detailed information about all of the meetings the device has participated in over time. In the **Activity** tab, you can see when a meeting was held, how many participants attended the meeting, and the quality of audio during the meeting.

![Teams Rooms device activity summary list.](../media/teams-rooms-meeting-activity-summary.png)

To see the detail information about a specific meeting, select the date and time of the meeting you want more information about. If a meeting has only two participants, you'll see the participant details page, otherwise you'll see a participant summary page.

##### Participant summary

The participant summary page shows all of the participants that attended the meeting. You can see when each participant joined the meeting, their name, audio quality, and what features were used during their session. To view the details of a participant's session, select the session start time for that participant.

![Teams Rooms device conference details.](../media/teams-rooms-meeting-activity-participant-summary.png)

##### Participant details

The participant details page shows end-to-end diagnostic information for that participant's session. As shown in the following graphic, **Device**, **System**, and **Connectivity** information is provided for the participant and for the Teams Rooms device. **Network** diagnostic information between the participant and the Teams Rooms device is also provided. Select the icon for the context you want more information about. For additional diagnostic information, select the **Advanced** tab.

![Teams Rooms device call details.](../media/teams-rooms-meeting-activity-participant-details.png)