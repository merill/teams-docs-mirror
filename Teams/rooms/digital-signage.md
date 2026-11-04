---
layout: Conceptual
title: Digital signage with Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/digital-signage
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
ms.date: 2026-08-24T00:00:00.0000000Z
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-consoles
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: Learn more about how
locale: en-us
document_id: 425a16c7-3312-e233-17fa-1d9d22ba515f
document_version_independent_id: 425a16c7-3312-e233-17fa-1d9d22ba515f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/digital-signage.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/digital-signage
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/digital-signage.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1f1ddadc-8aed-db6d-b225-b7affe70bc9b
---

# Digital signage with Teams Rooms - Microsoft Teams | Microsoft Learn

Digital signage on Microsoft Teams Rooms expands organizational communications into your meeting spaces, enabling you to inform, connect, and engage your teams. When your Teams Rooms devices aren't used for meetings or presentations, they can be configured to display dynamic content and relevant information like how to guides, company or organizational news, upcoming events, and more in signage mode. You can adjust when signage mode is activated and deactivated, including whether signage mode will adhere to the operating system's screen time-out setting. When your Teams Rooms devices are in signage mode, signage content appears in full screen on the front-of-room displays. You can show the Teams Rooms banner so that users can see the room information and calendar preview alongside the signage content on the front-of-room displays. Tapping the touch console during signage mode seamlessly returns the user to the home screen. Teams panels outside rooms can also show signage with their own display behaviors.

[![Teams Rooms homescreen.](media/digital-signage/ds-meeting-enlarged-console.jpg)](media/digital-signage/ds-meeting-enlarged-console.jpg#lightbox)

## Prerequisites

Configuring digital signage for your tenant requires the following:

1. Teams Rooms on Windows [version 5.1 or later](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Windows) installed on your Teams Rooms on Windows devices.
2. Teams Rooms on Android [version 1449/1.0.96.2026087210 or later](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Android) installed on your Teams Rooms on Android devices.
3. Teams panels [version 1449/1.0.97.2026286706 or later](/en-us/microsoftteams/devices/devices-release-notes?tabs=panels) installed on your Teams panel devices.
4. Teams Rooms Pro license assigned to resource accounts signed in to your Teams Rooms devices.
5. Teams Rooms Pro Management portal access for device configuration and management.

### Unsupported client and environments

Currently, digital signage isn't yet available on the following clients and environments:

- Multitenant Management portal (MTMA)
- Government Community Cloud (GCC)
- Government Community Cloud High (GCC-H)
- Department of Defense (DoD)

## Setup and management

To enable digital signage for your Teams Rooms devices, you need to follow these steps:

1. Manage permissions for digital signage.
2. Enable digital signage for the tenant.
3. Add signage sources for the tenant, including enabling native third-party integrations as desired.
4. Assign a source and settings to devices, or device groups, which register devices onto supported third-party content management systems (if applicable).

Before enabling digital signage, review your organization's privacy and compliance requirements, particularly when using third-party signage providers or external web content. For more information, see Step 3: Add an external signage source.

The following sections show you how to complete each step.

## Step 1: Managing permissions for digital signage

By default, Microsoft 365 Global Admins and Teams Rooms Pro Managers have the digital signage *tenant* management and digital signage *room* management permissions which grant the ability to perform the following actions respectively:

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

- Digital signage *tenant* management permission

    - Enable, disable, and reset digital signage for the tenant.
    - Add and delete signage sources.
    - Assign signage source and settings to any device or device groups in the tenant.
    - Set default signage source and settings for the tenant.
- Digital signage *room* management permission

    - Enable, disable, and reset digital signage for specific room, device, and/or device group.
    - Select an existing signage source from the list of sources that was added to the tenant.
    - Modify signage settings for a room, device and/or device group.

To delegate digital signage permissions to other administrators, use role-based access control:

1. Sign in to **Teams Rooms Pro Management** portal &gt; go to **Settings** &gt; **Roles** &gt; select **Create** **role** &gt; enter a unique name and description for the role &gt; select **Next**.
2. Under **Role permissions**, select **Digital signage tenant management: View, Modify** and/or **Digital signage room management: Modify** as desired &gt; select **Next** &gt; enter a name and description for the assignment &gt; select **Next**.
3. Under **Assign members**, search and/or select users and/or security groups that are part of this role with the selected permissions &gt; select **Next**.
4. Under **Assign scope**, search and/or select rooms, devices, and/or device groups that this role can manage &gt; select **Next** &gt; **Add new role**.

## Step 2: Enable digital signage

1. In the Teams Pro Management Portal, go to **Settings** &gt; **Digital signage**.
2. Turn on **Digital signage**.

After digital signage is enabled, add one or more signage sources. You can assign different sources to individual rooms or room groups. Supported signage sources include web URLs and integrations with third-party digital signage providers.

The following third-party integrations are supported:

- [AppSpace](https://www.appspace.com/microsoft-teams-rooms/)
- [XOGO](https://www.xogo.io/xogo-for-microsoft-teams-rooms)

Supported third-party providers require a separate subscription. Contact the provider for licensing and pricing information.

## Step 3: Add an external signage source

To enable a third-party digital signage integration:

1. From the **Digital signage tenant management** page, select **Add source**.
2. Enter a unique name and description for the source, then select **Next**.
3. Select the third-party provider you want to use.
4. Enter the integration ID provided by the third-party service.
5. Select **Validate**, then select **Next**.
6. Review and accept the terms of use, then select **Next**.
7. Review the configuration and select **Submit**.

For provider-specific setup instructions, see:

- [Appspace](https://docs.appspace.com/latest/devices-app/advanced-registration-microsoft-meeting-room-devices/)
- [XOGO](https://www.xogo.io/microsoft-teams-rooms-setup)

If you don’t use any of the supported third party providers, you can set web URLs as a signage source. To ensure the web application loads successfully on your Teams Rooms device, the URL must meet the following requirements:

- Has a valid web URL format.
- Begins with "https".
- Accessible within a browser InPrivate window without requiring authentication or permission from the resource account.
- Loads within an iframe that runs in sandbox="allow-scripts allow-same-origin" environment. For more information, see [CSP: frame-ancestors - HTTP | MDN (mozilla.org)](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors).
- Allows iframe embedding. Digital signage renders web content within a sandboxed iframe. Websites that prevent iframe embedding through Content-Security-Policy (CSP) or other restrictions aren't supported.
- Uses content that is optimized for the target display size. Direct image URLs are rendered using their original dimensions and aren't resized or transformed by Teams Rooms.

Important

To use a web URL as a signage source, the website must allow *https://teams.microsoft.com/* in the Content-Security-Policy (CSP) frame-ancestors directive. Otherwise, the content can’t be displayed in digital signage.

### Add a web URL signage source

1. From the **Digital signage tenant management** page, select **Add source**.
2. Enter a unique name and description for the source, then select **Next**.
3. Select **Custom**.
4. Enter a web URL that meets the requirements listed in this article, then select **Next**.
5. Review and accept the terms of use, then select **Next**.
6. Review the configuration and select **Submit**.

SharePoint and OneDrive for Business URLs aren't supported as custom signage sources. When you add a signage source, you're responsible for the content displayed on your devices and for ensuring that the source meets your organization's privacy and compliance requirements. Supported third-party providers receive the room name and room email address for devices assigned to their service to enable the integration.

## Step 4: Assigning signage source and settings

Once you've added signage source(s) for your tenant, you can now assign a signage source and settings to your devices. If you're assigning one of the trusted third-party providers as a signage source to a device, this step automatically registers that specific device onto the third-party content management system. You can assign a signage source and settings for multiple devices or device groups at the tenant level or for individual devices at a device level:

Once you've added signage source(s) for your tenant, you can now assign a signage source and settings to your devices. If you're assigning one of the trusted third party providers as a signage source to a device, this step automatically registers that specific device onto the third-party content management system. You can assign a signage source and settings for multiple devices or device groups at the tenant level or for individual devices at a device level:

- Tenant-level - from the digital signage tenant management page, choose a signage source &gt; select **Assign to devices** &gt; confirm the preselected source that you intend to assign &gt; select **Next** &gt; review or modify signage settings &gt; select **Next** &gt; search or select devices and/or device groups where you'd like to assign your chosen source and settings &gt; select **Next** &gt; choose when the configuration will be applied &gt; review and finish &gt; select **Submit**.
- Room-level - navigate to the specific device's settings. Go to **Rooms** &gt; choose a specific device &gt; select **Settings** &gt; **Digital signage** &gt; toggle ON **Digital signage** &gt; modify signage settings as desired &gt; choose a signage source from any of the sources added to the tenant &gt; select **Apply** &gt; choose when the configuration will be applied &gt; select **Submit**.

Important

Whether you choose to apply the settings now or during the maintenance window, the device must be online, connected, and signed into the Teams Rooms app or Teams panel app for settings to be applied. After a device restarts, it takes about 10-15 minutes for the Teams Rooms Pro Management agent to be connected.

Note

To find the setting application results, go to **Rooms** &gt; select **Export** **all** and filter through the devices and settings in the CSV file. Once settings have been applied, devices are now registered with the third party provider. You can manage and update the content that plays in the device directly from the third party content management system.

Tip

When designing signage content, avoid placing texts or images on the top 15% of the screen height to avoid being obstructed by the Teams info banner.

Tip

Use signage content designed for smaller screens when showing signage on Teams panels. Smaller text on content designed for front-of-room displays may not be legible on a Teams panel screen.

Warning

Make sure that there's signage content assigned to your device from the third party service. If there isn't signage content from the third party service available for your device, signage mode won't activate even when configured to do so to avoid showing blank screens on devices.

When designing content, avoid placing text or images in the top 15% of the display, where Teams information can overlap signage content. Teams panels have smaller displays than front-of-room screens, so content should be optimized for readability on smaller devices.

Signage mode activates only when content is available for the device. If no content is assigned, the device remains on the Teams Rooms home screen instead of displaying a blank screen.

## Modifying default source and settings

While each device or device group can be assigned with a unique configuration, you can set your preferred default signage settings for your tenant, including the default source, signage mode user interface, and display period. To do so:

- **Signage source** - From the digital signage tenant management page, choose a source &gt; select **Set as default**.
- **Signage mode user interface** - From the digital signage tenant management page, select **Preferences** &gt; toggle On or Off **Show Teams info banner** as desired. Turn On to show room information including room name and calendar preview alongside signage content. Turn Off to hide room information in signage mode. Note that on Teams panels, Teams info banner will be shown alongside signage content even when **Show Teams info banner** setting is turned off.
- **Show signage on Teams panels** - From the digital signage tenant management page, select **Preferences** &gt; select a value for **Show signage on Teams panels**. Setting chooses whether digital signage displays on Teams Panel devices: **Yes** to always show signage on panels in addition to Teams Rooms front-of-room displays, **No** (default) to not show signage on panels, or **Show only on Teams panels** to show signage exclusively on panels and not on Teams Rooms front-of-room displays.
- **Display period** - From the digital signage tenant management page, select **Preferences**:
    - **Activation timer** - Enter the number of minutes (between 1 to 100, default 1) that a device has been idle before signage mode activates.
    - **Deactivation timer for front-of-room displays** - Enter the number of minutes (between 0 to 100, default 0) before a scheduled meeting starts when signage mode deactivates and returns to the home screen.
    - **Deactivation timer for Teams panels** - Enter the number of minutes (between 0 to 100, default 5) before a scheduled meeting starts when signage mode deactivates on Teams panels and returns to the home screen.
    - **Screen timeout** - Toggle On or Off **Allow screen timeout when device is idle** as desired. Turn On to adhere to the operating system's screen time out settings (that is, the screen light goes out regardless of when signage mode is activated). Turn Off to bypass the operating system's screen time out settings (that is, the screen remains lit up on idle devices when signage mode is activated). See [section below](/en-us/microsoftteams/rooms/digital-signage#known-issues-and-limitations) on known issues with digital signage interaction with device sleep mode on a number of Teams Room on Android and Teams panel device models.

Video playback can affect how operating systems apply screen-timeout settings. Devices displaying video content might remain active longer than expected. Organizations that want signage to appear as quickly as possible should use shorter activation timers and longer screen-timeout intervals.

## Monitoring and insights

When using a supported third party digital signage provider as the signage source of a room, you can proactively monitor the health of digital signage in the room using the new digital signage health signal when you expand the display signal. To view the digital signage health signal: go to **Rooms** &gt; choose the specific device &gt; select **Status** &gt; toggle On **Show all signals** &gt; expand **Display** &gt; select **Digital signage**. Alternatively, go to **Incidents** &gt; expand **Display** &gt; select **Digital signage**.

When there's an issue with the third party player or signage content, the issue description, and actions you can take to resolve the issue (if applicable) will be visible in the messages. Depending on the nature of the issue, the Teams Rooms experience varies:

- If there's no signage content available to play in a room whether caused by a system error (that is, server error, offline) or human error (that is, no content assigned to the device, no cached content), signage mode will remain deactivated until the issue is resolved at the next device restart. The device remains on the home screen to avoid showing error messages or empty screens. Alerts are provided on the Teams Rooms Pro Management portal and the third party content management system as appropriate.
- If there's signage content available to play on a device (that is, cached content) despite an error, signage mode continues to activate per the activation timer. Any applicable alerts will still be provided on the Teams Rooms Pro Management portal and/or the third party content management system.

Note

The digital signage health signal isn't available for devices with a web URL (custom option) signage source.

## Help and support

For issues with getting a valid integration ID, how your Teams Rooms devices appear on the third party content management system, or specific problems with the signage content displayed on your devices, you must contact your third party provider for assistance. If your digital signage provider determines that the underlying issue requires Microsoft's attention, they can route the issue to Microsoft on your behalf or advise you to open a ticket directly with Microsoft. For other issues with configuring digital signage settings using the Teams Rooms Pro Management portal, you may contact Microsoft support.

## Known issues and limitations

| Issue or limitation | Workaround |
| --- | --- |
| Digital signage is not available on **Cisco devices** for Microsoft Teams Room on Android or Teams panels. | Teams digital signage will be enabled in a future update. |
| When the **Apply now** option for applying settings is selected and the room is in use, the settings won't be applied immediately to avoid disruption to the device. Rather, we retry to apply the settings during the maintenance window. | When settings fail to apply immediately, you can either wait for the maintenance window or push another update when the device is no longer in use to override the settings scheduled to be applied during the maintenance window. |
| There's a 2-hour delay before changes to digital signage settings appear in the **Export all** report. | Navigate to the room's digital signage settings page to view the latest settings of the device. |
| In some instances, assigning an Appspace channel to a device results in a failure to load signage mode on the device. | To troubleshoot, run the **Restart device-Clear cache** action with the **Delete Teams cache** option selected on the Teams Rooms Pro Management portal for the impacted room. If the issue persists, contact Appspace. |
| Rooms with dual displays that use Appspace may see a black screen on one of the displays when the Appspace player loads for the first time. | When a black screen is showing on of one of the dual displays, tap the touch console to exit signage mode. When the room goes back to the home screen, the next time signage mode loads, both screens will properly show signage mode. |
| On Microsoft Teams Room **on Android** and Teams panels, when digital signage is enabled, some device models do not go into sleep mode when expected. | No workaround at this time. Only enable digital signage if the device not entering sleep mode is ok. Issue will be addressed in a future update. |