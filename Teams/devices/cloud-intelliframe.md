---
layout: Conceptual
title: Cloud IntelliFrame - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/cloud-intelliframe
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: suhailkhalid
ms.date: 2026-01-06T00:00:00.0000000Z
ms.topic: concept-article
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
description: This article describes the Cloud IntelliFrame feature for Teams Rooms.
locale: en-us
document_id: f9d86af0-5d7d-30cb-8bc9-679f22fc8c77
document_version_independent_id: f9d86af0-5d7d-30cb-8bc9-679f22fc8c77
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/cloud-intelliframe.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/cloud-intelliframe
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/cloud-intelliframe.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ce90e4b4-ce16-20c6-989d-5b7ef268821c
---

# Cloud IntelliFrame - Microsoft Teams | Microsoft Learn

Cloud IntelliFrame is a new experience that allows online meeting attendees to see people in Teams Rooms more clearly through the smart video feeds of in-room participants. These smart video feeds are created by zooming into the faces of the in-room participants and by eliminating distractions, thereby enhancing the hybrid meeting experience. You can see the expressions and gestures of the people in the room more easily, which helps improve collaboration in hybrid meetings. It creates equity in hybrid meetings as everyone can be seen and heard.

## How Cloud IntelliFrame works

Important

Install appropriate signage outside any meeting room where you enable Cloud IntelliFrame advising people about the feature.

All Microsoft Teams Rooms on Windows with a Pro license equipped with cameras (see: Cameras enabled by default) automatically opt-in to Cloud IntelliFrame. Online participants on Microsoft Teams Desktop (Windows and Mac) will see the IntelliFrame video feed as a secondary option from rooms with these cameras.

Cloud IntelliFrame shows the smart feed when there are nine or less people in the room. It automatically switches between the standard room view and IntelliFrame view based on in-room activity. For example, if someone enters the meeting room, the view would automatically switch to standard room view until the individual settles down.

![Screenshot that shows CIF with participant identities.](media/cloud-intelliframe/cif-with-identity1.jpg)

People in the room can disable IntelliFrame by using the in-meeting settings on the console. These settings turn off Cloud IntelliFrame and switch back to standard view of the room. All online attendees would then see the standard view of the room.

[![Screenshot that shows how the standard view of a Teams Room looks on a computer.](../media/standard-view-of-teams-room.png)](../media/standard-view-of-teams-room.png#lightbox)

People on Teams Desktop can also toggle IntelliFrame on/off by right-clicking on the room's video tile and selecting **Turn off IntelliFrame**. This option switches off the IntelliFrame view just on their Teams client.

![Screenshot showing option to turn off CIF.](media/cloud-intelliframe/group-632893.png)

### Data Retention

Cloud IntelliFrame runs on Azure and is fully compliant with Microsoft 365 data processing with full separation between organizational boundaries. The infrastructure of Cloud IntelliFrame is no different from the infrastructure we use to record Teams Meetings.

Cloud IntelliFrame doesn't store meeting data or any identifiable information. The only data we log is what is needed to improve the service (for example, how long did it take to switch from room view to gallery, how often does the view layout change during the meeting), and to understand how Cloud IntelliFrame was used (for example, are end-users enabling/disabling it?).

## Cameras enabled by default

The following camera models don't have their own built in intelligence. When deployed in Microsoft Teams Rooms on Windows with a Pro license, Teams Rooms automatically enables Cloud IntelliFrame:

- AVer CAM520 Pro
- AVer CAM520 Pro2
- Crestron P12
- Crestron P20
- Jabra PanaCast
- Lenovo ThinkSmart One
- Logitech BRIO
- Logitech CC3000e
- Logitech MeetUp
- Logitech PTZ Pro
- Logitech PTZ Pro 2
- Logitech Rally
- Logitech Webcam C925e
- Logitech Webcam C920
- Logitech Webcam C930e
- Microsoft LifeCam Studio
- Poly EagleEye CUBE
- Polycom EagleEye IV
- Surface Hub Smart Camera
- Surface Hub 2 Camera
- Yealink UVC30
- Yealink UVC34
- Yealink UVC40
- Yealink UVC50
- Yealink UVC80
- Yealink UVC84

## Configure Cloud IntelliFrame

Cloud IntelliFrame is ideal for focus rooms and medium spaces. It may not be ideal for large spaces as people farthest from the camera may appear blurry after digital zoom. You may also want to switch off Cloud IntelliFrame in rooms with glass walls without any privacy filter. You can configure Cloud IntelliFrame through the [Teams Rooms Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service) or directly from the Teams Rooms device.

### Override Default Settings

Admins have granular control over Cloud IntelliFrame's end-user behavior. These settings can be configured remotely or directly on the console.

The available settings are:

| Setting | Default Setting | Description |
| --- | --- | --- |
| Enable Cloud IntelliFrame | True | Enable or disable Cloud IntelliFrame for this room. |
| Enable By Default | True | Enable Cloud IntelliFrame by default or allow in-room users to manually switch it on. |
| Cloud IntelliFrame on Supported Cameras Only | True | Disable this setting to allow Cloud IntelliFrame on any camera. |

Important

When enabling Cloud IntelliFrame on any camera, ensure that other AI features (for example, Speaker Tracking, Grid View) are turned off, as they can interfere with Cloud IntelliFrame.

#### Pro Management Portal

1. Log in to the [Teams Rooms Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service)
2. Select **Rooms**.
3. Select **Settings** followed by the **Peripherals** tab
4. Modify to the desired configuration for Cloud IntelliFrame
5. Select **Apply**
6. Choose when to apply the settings change and select **Submit**

#### Console Setting

To modify Cloud IntellIFrame settings via the console, navigate to **Settings &gt; Peripherals &gt; Cameras &gt; Cloud intelliFrame** to:

- Enable or disable Cloud IntelliFrame
- Configure whether Cloud IntelliFrame is on by default or if in-room users can manually enable it
- Override the default setting to allow Cloud IntelliFrame to work on any camera

![Console setting: Cloud IntelliFrame is on for this room using supported camera.](media/cloud-intelliframe/on,-supported-cameras-only,-supported-camera-selected.png)

When using an unsupported camera, the console settings appear as below. Even though Cloud IntelliFrame setting is on, the experience isn't enabled for the room because it's using an unsupported camera.

![Cloud IntelliFrame disabled for unsupported camera.](media/cloud-intelliframe/on,-supported-cameras-only,-unsupported-camera-in-use.png)

Uncheck the unsupported cameras only setting to override the supported camera list and enable Cloud IntelliFrame for a room with any camera:

![Cloud intelliFrame enabled for unsupported camera via override.](media/cloud-intelliframe/on,-all-cameras,-unsupported-camera-in-use.png)

When enabling Cloud IntelliFrame on a nonsupported camera, ensure that other AI features (for example, Speaker Tracking, Grid View) are turned off, as they can interfere with Cloud IntelliFrame.

## Recognition of In-Room Participants

Cloud IntelliFrame can identify in-room participants during scheduled meetings, displaying their names in the meeting roster for remote attendees.

![Screenshot showing CIF with identity.](media/cloud-intelliframe/cif-with-identity.jpg) To be identified during a meeting, the following conditions must be met:

- The meeting must be scheduled in Teams (ad-hoc "Meet Now" meetings aren't supported).
- The participant must be listed in the meeting invite.
- The organization must enable [voice and face recognition](/en-us/microsoftteams/rooms/voice-and-face-recognition).
- The participant must have [created a recognition profile in Teams](https://support.microsoft.com/en-us/office/create-recognition-profiles-for-microsoft-intelliframe-f0084478-52a7-4c52-bcdc-9063ed0e0bc0).

When these requirements are met, Cloud IntelliFrame will match in-room participants using facial recognition against the list of invited attendees who have completed enrollment. Recognized individuals appear by name in the roster for all meeting participants. If someone joins the room who isn't on the invite list, even if they’ve enrolled previously and have been recognized in other meetings in the same room, they will **not** be identified in the current meeting.

This capability is available on **Teams Rooms on Windows** with the **Teams Rooms Pro license** using either [supported cameras](/en-us/microsoftteams/devices/cloud-intelliframe) or [cameras enabled via settings](/en-us/microsoftteams/devices/cloud-intelliframe).

Important

You're responsible for compliance with local laws and regulations when you enable Cloud IntelliFrame in a particular jurisdiction, including with respect to obligations around notice, consent, and data retention. These obligations may include installing appropriate signage outside any meeting room where you enable Cloud IntelliFrame advising people about the feature. Due to the uncertainty regarding the scope of "biometrics" in the State of Illinois law; Cloud IntelliFrame isn't intended for use in Illinois.