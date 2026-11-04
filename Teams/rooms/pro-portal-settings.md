---
layout: Conceptual
title: Managing settings for Teams devices - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/pro-portal-settings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: kimmatlock
ms.date: 2026-09-30T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: This article provides guidance on how to manage your Teams device settings. It outlines the application settings that can be applied directly on the device and synchronized with the Teams Rooms Pro management portal, or alternatively, configured from the Teams Rooms Pro management portal to the device.
locale: en-us
document_id: cd7afc53-5593-2c57-4432-8ece01731e18
document_version_independent_id: cd7afc53-5593-2c57-4432-8ece01731e18
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/pro-portal-settings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/pro-portal-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/pro-portal-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5ed26301-9ef8-c49e-2239-67eb0f9423e5
---

# Managing settings for Teams devices - Microsoft Teams | Microsoft Learn

In the Microsoft Teams Rooms Pro Management portal, you can configure settings for Microsoft Teams devices (Teams Rooms on Windows, Teams Rooms on Android, Teams Panels and Teams Phones), provided you have the necessary role-based access control permissions for Rooms Management. For more information, see [role-based access control in the Microsoft Teams Rooms Pro Management portal](/en-us/microsoftteams/rooms/rooms-pro-rbac).

You can change settings on a single device, or for many devices at once using **Device setting jobs**. You can also maintain a reusable library of configurations with **settings templates**.

## Configuring Settings for a single device

To change settings on an individual device:

1. Go to **Rooms/ Phones in the left navigation** and click the device you want to configure.
2. Select the **Settings** tab in the device panel.
3. Use the left navigation in the device panels to browse settings categories (About, Account, Meetings, Device, Network, etc.).
4. Modify the desired settings using the form fields.
5. Click **Apply** (or **Save**). A schedule dialog appears with two options:

    1. **Apply Now** - Queues a job to apply the setting and restarts the device as soon as possible to apply the setting changes. This process can take several minutes. A banner is displayed to indicate that a settings change has been initiated, along with the number of settings changes jobs that are queued.
    2. **Schedule Later** - Schedules the settings change to be applied during the nightly maintenance window to avoid disrupting scheduled meetings during business hours.
6. Choose when to apply the changes.

Any setting changes made directly on the device are synchronized back to the Teams Rooms Pro Management portal and reflected in the Settings tab of the device panel, providing visibility into the device's current configuration.

Note

**Settings management is available only for signed-in devices.** Ensure that the device is signed in for settings changes from the Teams Rooms Pro management portal to be applied successfully.

## Settings job history

Since setting changes from the Teams Rooms Pro management portal to the Teams device aren't in real-time, there will be a delay. An indicator is visible next to any setting that is pending a change or pending verification of a change as a visual cue that a job is in progress for that device.

To provide visibility to the Teams Rooms Pro management technician, there's a **Settings Job History** activity under the **Activity** tab on the Rooms detail panel. This indicates the stage of settings change.

An entry is made for every setting change initiated by a user or by the Teams Rooms Pro management service.

| **Field name** | **Description** |
| --- | --- |
| Status | Indicates the status of the settings job. |
| Submitted on | Indicates the timestamp of the status of the job. |
| Submitted by | Indicates the individual who initiated the settings change or the Teams Rooms Pro Managed Rooms Service |
| Completed on | Indicates the timestamp when the job completed. |

### Device settings job history detail

By selecting the **Settings Job history** row in the table, a **Device settings** job panel is displayed with details about the specific device setting changes.

| **Field name** | **Description** |
| --- | --- |
| Job ID | A unique ID assigned to the settings job. |
| Status | Contains one of the following values: Submitted, Running, Completed, Completed with errors, Canceled, or Failed. |
| Submitted on | Date and Time when the job was submitted. |
| Submitted by | Indicates the individual who initiated the settings change or the Teams Rooms Pro Managed Rooms Service. |
| Settings | Shows the name of the settings that was changed. |
| Reason | See the table below for details. |

### Settings job reasons

Use this table to understand the **Settings Job** reasons.

| **Status** | **Reason** | **Reason** | **Description** | **Action** |
| --- | --- | --- | --- | --- |
| Submitted | PENDING CONNECTION | Device is disconnected, will execute the job after the device reconnects. | Ensure that the device is connected. |  |
| Submitted | SCHEDULED | Job was successfully created. | None. The job is scheduled and will run when the device is available or in the nightly maintenance window. |  |
| Running | IN PROGRESS | Job was sent down to the agent, and is pending a response back. |  |  |
| Completed | SUCCESS | Job successfully completed on the agent, and verification of settings application was done. | Settings validation can take up to 15 minutes to reflect in the Teams Rooms Pro management portal. |  |
| Canceled | CANCELED | User canceled the Job. |  |  |
| Completed With Errors | APP RESTART FAILED | New settings have been written to the correct location, but an issue occurred in the app restart process. To complete the process, the device was rebooted. | Reapply the settings. |  |
| Completed With Errors | VERIFICATION FAILED | New settings have been written, and the app was successfully restarted, but the settings weren't applied correctly or the settings change couldn't be verified. | Check that the settings changed. A retry will be scheduled by the Managed room service for the nightly maintenance window. |  |
| Failed | EXISTING XML FOUND | For a Windows device, an existing XML was found on the device and the agent was unable to create a new XML due to conflicts. | Restart the device to apply the existing SkypeSettings.XML on the device or remove it. See [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](/en-us/microsoftteams/rooms/xml-config-file). |  |
| Failed | FAILED TO WRITE XML | The agent failed to write an XML to a Windows device in the correct location. | Reapply the settings change. |  |
| Failed | FAILED | General failures outside of the specified error codes. | Reapply the settings change. |  |
| Failed | SETTINGS FETCH FAILED | Unable to fetch the new settings from the service. | Reapply the settings change. |  |
| Failed | DEVICE IN MEETING | Device is currently in a meeting. | Try again later. |  |
| Failed | DEVICE DISCONNECTED | Device was disconnected when we attempted to execute the settings change, so no changes occurred. | Reapply the settings change. |  |

Note

**Only one command or action can be processed for a device at a time.** If a device is currently in use or already has a command queued, any new command will remain in the **Queued** state until the device is available. If the command remains in the Queued state for more than **3 days**, its job status will be reported as **Failed**. If needed, a queued command can be canceled from the Activity page.

## Setting Templates

Settings templates let you define a named, reusable configuration that is assigned to specific devices or device groups. When you update a template, you can re-apply it to push the new configuration to all assigned devices.

**Navigate to:** Settings &gt; **Device settings** page &gt; **Templates (Preview)** tab

#### Create a Template

Click **Create Template** to open the wizard:

1. **Template name -** enter a name (required) and optional description.
2. **Room assignments** - select devices and/or device groups; or leave empty to save the template without assignments.
3. **Settings** - configure settings per device type.
4. **Schedule** - choose:

    - **Save only** - save the template for later use without applying it now.
    - **Apply now -** save and apply immediately to the assigned devices.
    - **Apply during maintenance window** - save and apply during the configured maintenance window for the assigned devices.
5. **Review and finish** - review all settings and assignments, then click **Save Template** (save only) or **Save and Apply** (apply immediately/ during Maintenance window).

#### Managing Templates

From the **Templates** tab, you can:

1. View template details: Click on the template to open the detail panel.
2. Edit: Click Edit Template from the table toolbar or detail panel.
3. Clone: Duplicate a template to create a similar configuration.
4. Apply: Push the current template settings to all assigned devices.
5. Delete: Remove one or more templates.

## Configure ultrasound settings in bulk

Use **settings templates** or **device settings jobs** to configure ultrasound settings across multiple supported devices. Go to **Settings** &gt; **Device settings**, create a template or job, and select the Teams Rooms on Windows devices to update. Under **Device**, turn on **Ultrasound beaconing** and, if needed, **Automatically accept proximity-based meeting invitations**. Under **Peripherals**, set **Ultrasound speaker volume**, and then review and apply the changes.

Note

Bulk ultrasound settings are supported on Teams Rooms on Windows and All-in-One Touchboard devices. **Ultrasound speaker** selection remains a per-device setting because speaker identifiers differ between rooms. For the complete list of remotely managed settings, see [Device settings available for remote management](device-settings-available?tabs=WindowsSettings).

## Import configuration profiles from Teams admin center as Setting templates in Teams Rooms Pro Management portal

If your organization already uses configuration profiles in Teams Admin Center (TAC) for Teams Rooms on Android devices, IP phones, or Teams Panels, you can import those profiles as settings templates in Teams Room Pro Management portal.

**Navigate to:** Settings &gt; **Device settings** &gt; **Templates (Preview)** tab &gt; **Import Configuration Profiles** (toolbar button)

**Import wizard steps**

1. **Select profile** - the wizard loads all available TAC configuration profiles. Each profile shows its name, device type, and Import status.
2. Select either a single profile or multiple profiles to import. Your selection determines the subsequent steps in the wizard.
3. When you select a single profile, you can review and configure the following details before importing:

    1. **Template name** - the profile name is pre-filled; adjust if needed.
    2. **Settings** - review the settings mapped from the TAC profile.
    3. **Room assignments** - devices from the TAC profile that are enrolled in PMP are pre-selected; devices not enrolled in PMP are excluded.
    4. **Schedule** - choose when to apply.
    5. **Review and finish** - click **Save Template** or **Save and Apply**.
4. When you select multiple profiles, the wizard skips the intermediate configuration steps and takes you directly to the **Review and Finish** step, where you can review your selections and complete the import.

## Device Settings Jobs for bulk changes

For Teams Rooms Pro management administrators, a job can be created to apply one or more settings to one or more Teams devices through the Teams Rooms Pro management portal. The device setting job acts as a parent container for each of the individual jobs that execute for the selected setting changes across the devices selected. In this way, you'll have an overall status of the completion of the parent job, along with the status for each individual device settings job. A filter has been added to easily sort on a parent job status (Submitted, Running, Completed, Completed with errors, Cancelled, and Failed).

When selecting either the **Apply Now** or **Schedule during Nightly Maintenance window**, the parent job creates individual jobs for each room device selected. At the individual device level, you can see the job under the **Room &gt; Activity** pane. If the device is in a call or unmonitored, the individual job can fail or be rescheduled for another attempt to apply the settings change. If one of the individual jobs fails, the parent job is reflected as **Completed with Errors**. An export button has been provided to download the entire job details along with statuses of each individual job.

### Create a Job

1. In the left navigation of the Microsoft Teams Rooms Pro Management portal, go to **Settings** &gt; **Device Settings**.
2. Select the **Jobs** tab.
3. Add **devices** or **groups of devices** where the setting changes are to be applied.
4. Select **Settings** changes to be applied to devices.
5. **Schedule** whether the settings changes should **apply now** or **schedule in the nightly maintenance window**.
6. Give the job a **name** for reference in the Device Settings Job dashboard.
7. Review the job details. When you're ready, select **Create job**. The job will be queued to execute.

### Device Settings Job Detail (for bulk changes)

Details of the job created are available by selecting the job from list on the Device settings job dashboard. A Setting jobs detail pane is presents with three tabs: **General, Settings and Devices**, along with an Export button. Filters are also available to sort through devices for quick reference of individual job statuses.