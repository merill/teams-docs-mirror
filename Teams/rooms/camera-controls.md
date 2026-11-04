---
layout: Conceptual
title: Camera controls in Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/camera-controls
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: thofreeman
ms.date: 2026-09-23T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-rooms
audience: Admin
ms.collection:
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: Learn how in-room participants adjust cameras in Microsoft Teams Rooms, including pan, tilt, and zoom controls, which cameras support them, and expected behavior.
locale: en-us
document_id: 92702e4f-bec3-273f-8cbe-64ee54f5d446
document_version_independent_id: 92702e4f-bec3-273f-8cbe-64ee54f5d446
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/camera-controls.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/camera-controls
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/camera-controls.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 31645420-b51c-f46a-c22c-1df20f50b702
---

# Camera controls in Teams Rooms - Microsoft Teams | Microsoft Learn

Microsoft Teams Rooms gives people manual control over the room camera in addition to automatic framing features that run on the camera or in the cloud.

Teams Rooms provides three ways to control and adjust the in-room camera experience:

- **Enhanced Framing** uses supported framing modes to automatically adjust how participants are shown.
- **Local PTZ controls** let people in the room manually pan, tilt, and zoom supported cameras.
- **Camera source selection** lets people in the room manually switch between available cameras.

On Teams Rooms on Windows and Teams Rooms on Android, manual camera controls work alongside **Enhanced framing**. When **Enhanced framing** is on, the camera or the cloud automatically reframes the room using an available framing mode, such as **IntelliFrame**, **Active speaker**, or **Group framing**. The availability and behavior of individual controls can vary by platform, device, camera, and firmware.

To use manual PTZ controls, turn Enhanced framing off. Camera capabilities and other room settings also affect whether controls are available. See Which cameras support local PTZ controls.

## Availability across devices

| Control | Teams Rooms on Windows | Teams Rooms on Android |
| --- | --- | --- |
| Local PTZ controls | Included in app version 5.7.112.0 or later; requires feature enablement and a compatible camera | Available in app version 1449/1.0.96.2025126202 or later on compatible devices |
| Switch between in-room cameras | Available | Available |
| Enhanced framing | Available | Available |

## Prerequisites

- A Teams Rooms device running a supported version of the Teams Rooms app. For local PTZ on Windows, use app version 5.7.112.0 or later and a camera that exposes supported PTZ operations.
- A camera connected to the Teams Rooms device and selected as the room camera.
- Use the latest supported firmware that the manufacturer recommends for the specific Teams Rooms device and camera configuration. Don’t use preview or unsupported firmware.

## Open Camera settings

During a meeting, select the chevron next to the camera icon on the room console to open **Camera settings**.

Selecting the **camera icon** itself turns room video on or off instead of opening the settings dialog.

The appearance and available options can differ by platform, room device, camera, and firmware.

The following example shows Camera settings on **Teams Rooms on Windows**.

![Camera settings on Teams Rooms on Windows.](media/camera-controls/camera-settings-dialog.png)

## Use Enhanced Framing

**Multiple camera view** on Teams Rooms on Windows lets the room send up to four supported single-stream USB camera feeds for remote participants to view simultaneously. This differs from switching the selected camera under **Source**. Multiple camera view requires a Teams Rooms Pro license and a supported configuration. Local PTZ controls aren’t available while it is active. For setup instructions, see [Multiple camera view](multicamera-view).

**Enhanced framing** automatically adjusts the room view by using an available framing mode, such as IntelliFrame, Active speaker, or Group framing. Turn **Enhanced framing** off before using manual local PTZ controls.

## Switch between in-room cameras

- On **Teams Rooms on Windows**, when more than one camera is connected, people in the room can change which camera sends video by selecting a different camera under **Source** in **Camera settings**. Camera selection persists for the remainder of the meeting.
- On **Teams Rooms on Android**, if multiple sources are available, open the camera dropdown and select the desired camera under **Source**.

To send video from multiple cameras at the same time rather than switching between them, see [Multiple camera view](multicamera-view).

## Local pan, tilt, and zoom controls

Local PTZ controls allow people in the room to manually adjust a camera from the Teams Rooms console. When available, people can pan, tilt, and zoom the selected camera to better frame the room or focus on a specific area.

For example, local PTZ controls can be useful when a camera is positioned toward a conference table, but the discussion has moved to a whiteboard or another area of the room.

Teams Rooms on Windows and Android support source selection, enhanced framing, PTZ controls, and reset on supported devices. Windows-specific requirements, management options, and reset behavior are described below. On Android, available controls vary by device and firmware. On Teams Rooms on Android, zoom in before using pan and tilt controls. On Teams Rooms on Windows, if Teams Rooms uses digital PTZ and the view is fully zoomed out, zoom in before using pan and tilt controls; digital pan and tilt move the view within the captured image. Zooming in first isn't an inherent requirement for mechanical pan and tilt.

### Which cameras support local PTZ controls?

**Teams Rooms on Windows:** A camera qualifies for local PTZ when it is on the [Cameras enabled by default](../devices/cloud-intelliframe#cameras-enabled-by-default) list for Cloud IntelliFrame or reports its automatic-framing state to Teams Rooms. This lets Teams Rooms avoid conflicts between manual control and automatic framing. The Cloud IntelliFrame list is used as an eligibility reference; Cloud IntelliFrame doesn't need to be turned on to use local PTZ.

On **Teams Rooms on Windows**, all of the following room and camera conditions must also be met:

- **Enhanced framing** is turned off.
- **Multiple camera view** is turned off.
- Local PTZ controls are enabled for the room.
- The local PTZ feature is enabled on the Teams Rooms device.
- The selected camera exposes supported PTZ controls to Teams Rooms.

On **Teams Rooms on Android**, availability depends on the PTZ capabilities exposed through the device's camera integration and supported firmware. The Windows Cloud IntelliFrame-list eligibility rule isn't an Android requirement.

When local PTZ controls are available, Teams Rooms displays the operations supported by the selected camera. Some cameras support pan, tilt, and zoom, while others support only a subset of those operations.

Both mechanically controlled cameras and cameras that adjust the image digitally can support local PTZ controls.

If a camera doesn't expose supported PTZ controls to Teams Rooms, local PTZ controls won't appear, even if the camera can be controlled through the manufacturer's application, remote control, or other management tools.

Note

Cloud IntelliFrame provides automatic framing in the cloud. On **Teams Rooms on Windows**, turn off **Enhanced framing** before using local PTZ controls.

The following diagram summarizes the camera and room checks for local PTZ on Teams Rooms on Windows. Meeting these conditions determines whether controls can be offered; the operations shown still depend on what the camera exposes.

![Local PTZ eligibility checks for Teams Rooms on Windows.](media/camera-controls/local-pan-tilt-zoom-eligibility-2026-10-15.png)

### Camera PTZ behavior examples

The following examples show how different camera models provide PTZ. They aren't an exhaustive list of cameras that can show local controls and don't guarantee identical Reset behavior. The PTZ method used by Teams Rooms determines the Reset outcome described in Understand Reset behavior.

| Brand | Camera examples | PTZ capability |
| --- | --- | --- |
| **Jabra** | Original PanaCast | Electronic pan, tilt, and zoom (digital PTZ). This entry doesn't include PanaCast 50. |
| **Lenovo** | ThinkSmart One | Electronic pan, tilt, and zoom for its integrated camera. ThinkSmart One is an all-in-one Windows device, not a separately connected ThinkSmart Cam. |
| **Logitech** | Original BRIO/BRIO 4K; Webcam C920; Webcam C930e; original MeetUp | The listed webcams provide digital PTZ. MeetUp instead has motorized pan and tilt with digital zoom. Local directional PTZ can work on MeetUp, but that alone doesn't establish whether Reset restores its physical pan and tilt. Don't apply the original MeetUp description to MeetUp 2. |
| **Microsoft** | LifeCam Studio | Digital pan, tilt, and zoom. |
| **Poly** | Studio E60; Studio E70 | Studio E60 uses hardware PTZ with absolute positioning; Studio E70 uses digital PTZ. |
| **Yealink** | UVC30 Room; UVC34; original UVC40 | Electronic PTZ. These examples don't automatically include other UVC30 variants or UVC40 E2. |

All cameras in this table are subject to the same connection, software, feature-enablement, and room requirements. A digital or absolute PTZ specification in a manufacturer's application doesn't, by itself, establish that Teams Rooms uses the same control method.

A camera not shown in this examples table might still provide local PTZ controls. Conversely, a camera can support directional controls even if Reset doesn't restore physical pan and tilt.

### Evaluate cameras for deployment

Before deploying broadly, confirm the camera's capabilities and manufacturer-recommended firmware, and evaluate pan, tilt, zoom, and Reset separately. Use the Teams Rooms app version and camera firmware planned for deployment.

Choose a camera that provides the pan, tilt, zoom, and Reset behavior needed for the room, and use the latest supported firmware recommended by the manufacturer for the planned Teams Rooms configuration.

If PTZ controls don’t function correctly, work with the Teams device manufacturer to confirm the supported firmware for **local PTZ in Teams Rooms**. If the issue continues on supported firmware, contact Microsoft Support.

**Reset** returns supported camera-view adjustments to their default values. It isn’t a factory reset and doesn’t restore the camera position from the beginning of the meeting. Which adjustments return to their defaults depends on whether Teams Rooms uses digital PTZ, absolute hardware positioning, or relative-only hardware pan and tilt. Motorized movement, digital zoom, a Home button, or stored presets don't, by themselves, identify the positioning method available to Teams Rooms.

### Use local PTZ controls

The options shown in **Camera settings** vary by camera model. Some cameras show more settings than others, and framing modes appear only when the camera or the service supports them.

1. On the room console, select the chevron next to the camera icon to open **Camera settings**. Selecting the camera icon itself turns the room camera on or off instead of opening the dialog.
2. If more than one camera is connected, confirm that the intended camera is selected under **Source**.
3. If **Enhanced framing** is on, turn it off. If local PTZ controls don't appear, see Review expected behavior and known limitations.
4. To adjust the selected camera's pan, tilt, or zoom, use the available controls.
5. To reset camera adjustments, select **Reset**. What resets depends on the control method used by Teams Rooms and the available software updates. See Understand Reset behavior.
6. To close **Camera settings**, select anywhere outside the dialog. The dialog also closes on its own after a short period of inactivity.

Note

Camera-position changes can persist after a meeting. On Teams Rooms on Windows, ending a meeting doesn’t automatically invoke local PTZ Reset. Select **Reset** to return supported adjustments to their default values. Camera-provided return behavior and restoration of automatic framing are separate.

### Understand Reset behavior

**Reset** returns supported camera-view adjustments to their default values. It isn’t a factory reset and doesn’t restore the camera position from the beginning of the meeting. Reset doesn't have the same effect for every PTZ implementation. The following table describes expected Reset behavior on Teams Rooms on Windows when local PTZ and applicable software updates are enabled and **Teams Rooms uses the specified control method**.

| Control method used by Teams Rooms | Expected Reset behavior | What this means |
| --- | --- | --- |
| **Digital pan, tilt, and zoom** | Resets digital pan, tilt, and zoom adjustments | Restores the digitally adjusted view; the physical camera doesn't move. Digital zoom alone doesn't establish digital pan and tilt. |
| **Hardware pan and tilt with absolute positioning** | Resets physical pan and tilt and the zoom adjustment when the applicable Reset support is enabled | Absolute positioning lets software address specific physical pan and tilt positions. Zoom can be optical or digital, provided Teams Rooms can reset that adjustment. |
| **Hardware pan and tilt with relative-only positioning** | Resets zoom; physical pan and tilt remain at their adjusted positions | Directional movement can still work, but this control method doesn't let Reset restore the physical pan and tilt positions. |

“Manual PTZ” describes a person operating the controls. It isn't a separate camera-capability category: digital, absolute hardware, and relative hardware PTZ can all be operated manually.

Note

Absolute positioning means addressing a particular pan or tilt position, rather than only moving from the current position. A camera's stored presets or Home button don't, by themselves, establish that Teams Rooms can address those positions. Absolute hardware PTZ isn't a universal requirement for full Reset because digital PTZ can reset the digitally adjusted view.

The Teams Rooms on Windows 5.7.112.0 release includes local PTZ support. The applicable updated Reset behavior must also be available on the device. Without it, some cameras using absolute positioning can reset zoom without resetting pan or tilt. Updating Teams Rooms doesn't create absolute positioning on a camera that offers relative-only hardware control.

A zoom-only Reset can therefore have different explanations: expected behavior for relative-only hardware pan and tilt, or unavailable or ineffective Reset support on the absolute-positioning path. The symptom alone doesn't identify the camera's capabilities.

Firmware and implementation can also affect results. This table describes expected behavior by control method, not a guarantee for every camera model. If the observed behavior differs, see Troubleshoot when local PTZ controls don't work as expected.

On Teams Rooms on Android, select Reset to return the camera view to the default supported by the device’s camera integration. The adjustments that reset depend on the camera and firmware.

### Manage local PTZ controls

The local PTZ room control is enabled by default on **Teams Rooms on Windows**.

1. Open [Teams Rooms Pro Management](/en-us/microsoftteams/rooms/rooms-pro-management).
2. Select the room.
3. Navigate to **Device settings**.
4. Select the **Peripherals tab.**
5. Enable or disable Local PTZ controls.
6. Save the changes.

## Troubleshoot when local PTZ controls aren't shown

The following checks apply to **Teams Rooms on Windows**. More than one condition can affect whether controls appear.

| What you see | Possible cause | What to check |
| --- | --- | --- |
| No PTZ controls in **Camera settings** | **Enhanced framing** is on | Turn **Enhanced framing** off, then check the remaining camera and room requirements. |
| No PTZ controls for any camera in the room | Local PTZ is disabled, the feature isn't enabled on the device, or the cameras don't meet an eligibility condition | Review Which cameras support local PTZ controls, check that **Enhanced framing** and **Multiple camera view** are turned off and verify that the selected camera supports PTZ operations in Teams Rooms. |
| PTZ controls appear for one camera but not another | Camera capabilities, firmware, or camera selection differ | Confirm the selected camera and review Which cameras support local PTZ controls. If the requirements are met but controls remain unavailable, contact Microsoft Support. |
| No PTZ controls while multiple camera view is on | Local PTZ isn't available in multiple camera view | Turn off multiple camera view. See [Multiple camera view](multicamera-view). |
| PTZ controls disappear after a room-setting change | The change may have affected local PTZ availability or camera configuration | Review the changed settings. Confirm that local PTZ is enabled for the room, the intended camera is selected, and Enhanced framing and multiple camera view are off. |

## Troubleshoot when local PTZ controls don't work as expected

The following guidance applies to **Teams Rooms on Windows**.

| What you see | What to do |
| --- | --- |
| A PTZ control appears, but the camera doesn't respond as expected | Confirm the selected camera, use manufacturer-recommended firmware, and check the Teams Rooms app version and available updates. If the issue persists, contact Microsoft Support. |
| Pan or tilt doesn't change the view | If Teams Rooms uses digital PTZ and the view is fully zoomed out, zoom in first, then pan or tilt. Digital pan and tilt move the view within the captured image. |
| Reset changes zoom but doesn't reset pan or tilt | Review Understand Reset behavior. This is expected for relative-only hardware pan and tilt, but can also indicate that the applicable Reset behavior isn't available or isn't working for a camera using absolute positioning. Confirm the camera's control method and install available supported updates. If the issue persists, contact Microsoft Support. |
| Digital PTZ or absolute hardware PTZ doesn't reset as expected | Confirm the camera configuration, firmware, and applicable Teams Rooms software updates. If the issue persists, contact Microsoft Support with the reproduction details. |
| Reset returns the camera to an inconsistent position | Review the manufacturer's guidance and the Teams Rooms software updates available on the device. If the behavior remains inconsistent, contact Microsoft Support with the affected configuration and reproduction steps. |

When reporting an issue, include the camera model, installed firmware, Teams Rooms app version, affected control, reproduction steps, and relevant diagnostic logs. Distinguish between controls that don't appear and controls that appear but don't work as expected.

## Review expected behavior and known limitations

The following local PTZ behavior applies to **Teams Rooms on Windows**:

**Manual controls and automatic framing are mutually exclusive**. Local PTZ controls are hidden while **Enhanced framing** is on, so manual adjustments don't conflict with automatic framing.

**Multiple camera view takes precedence**. Local PTZ controls aren't offered while multiple camera view is active.

Reset depends on the control method. Digital PTZ and absolute hardware positioning can restore pan, tilt, and zoom through their respective methods, subject to applicable software support. Relative-only hardware pan and tilt remain unchanged when Reset is selected. See Understand Reset behavior.

**Feature enablement is separate from installing the app**. Having a supported Teams Rooms version doesn't by itself establish that local PTZ or the updated Reset behavior is enabled on the device.