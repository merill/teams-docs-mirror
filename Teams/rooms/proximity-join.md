---
layout: Conceptual
title: Proximity Join using Bluetooth and ultrasound - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/proximity-join
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: leungsam
ms.date: 2026-04-13T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: itpro-rooms
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use the Proximity Join feature using Bluetooth and Ultrasound connectivity to nudge a Microsoft Teams Room console into a meeting you're having for an optimum meeting room experience.
f1keywords: NOCSH
locale: en-us
document_id: 2aadd6d6-7f0e-5043-9e85-eab380368591
document_version_independent_id: 2aadd6d6-7f0e-5043-9e85-eab380368591
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/proximity-join.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/proximity-join
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/proximity-join.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3b26661f-5bb1-a104-7e27-d7d415305cb0
---

# Proximity Join using Bluetooth and ultrasound - Microsoft Teams | Microsoft Learn

Proximity Join is a feature that lets end users use the Teams app on a desktop or mobile device to invite or nudge a Microsoft Teams Room into a Teams meeting. The Teams Room doesn't need to be invited to the meeting to be joined using proximity join. Proximity join is also a requirement to enable [Room Remote](https://support.microsoft.com/office/use-a-room-remote-to-control-a-room-device-in-microsoft-teams-af126a46-4ad5-47b1-a449-e3c63952698e) functionality. This feature uses wireless technologies that can be individually turned on or off based on the requirements of the environment:

- Bluetooth
- Ultrasound (Ultrasonic)

The end user experience is the same using either Bluetooth or ultrasound for Proximity Join. If they're both turned on, they operate together to provide improved accuracy. A Teams Room that is found using ultrasound on is always put at the top of the list of nearby rooms in the meeting's prejoin screen (under the room audio option). Teams Rooms that are found using Bluetooth are listed after the rooms that have ultrasound turned on.

When a user's laptop or mobile device brings a Teams Rooms in using Proximity Join or if Proximity Join detects a user is joining while in a Teams Room which is already in the same meeting, the user's video won't appear on the room's display, and the room's video stream is hidden on the personal device meeting stage. Users can override the automatic hiding behavior by using the pin or spotlight functionality of Teams Meetings.

Proximity Join nudges from a desktop or mobile client must come from a user within the same tenant or from a [trusted external organization](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings#specify-trusted-microsoft-365-organizations). Users not covered by these scenarios won't see the Teams Room available for proximity join. Likewise, if the meeting participant using proximity join from their device is unable to bypass the Teams Meeting lobby, the proximity join will fail as the participant is unable to add an additional device to the meeting from the lobby due to security restrictions.

Proximity join doesn't require a direct network connection between a user personal devices and the Teams Rooms device, all communication takes place through Microsoft Teams.

**Known issue**: In rare cases, the Teams desktop app might become unresponsive when joining a meeting. If this occurs, restart the Teams desktop app and rejoin the meeting.

## Bluetooth

Bluetooth is a short range wireless technology in which compatible devices can use it to communicate. However, this signal can penetrate through walls. Rooms discovered through Bluetooth are sorted by signal strength in descending order, and it includes all Teams Rooms both in use and not in use. This is because the Bluetooth signal isn't paused when Microsoft Teams Room has joined a meeting.

Bluetooth must be enabled on both the Teams Rooms device and on the client desktop/mobile endpoint in order for proximity to function.

For information on the security of Bluetooth Proximity Join see [Teams Rooms Security](/en-us/microsoftteams/rooms/security).

## Ultrasound

Ultrasound signaling is available on Microsoft Teams Rooms on Windows (from compatible consoles) and can be used to along with Bluetooth for more accurate proximity join logic.

The Proximity Join using ultrasound works by emitting an ultrasonic (19.5 kHz - 21.5 kHz) signal from the Teams Room console that isn't audible to humans. It's more accurate than Bluetooth because at reasonable volume, it won't penetrate through walls but the signal is paused when the Microsoft Teams Room is either in a meeting or HDMI ingest is active. For example, you walk into a conference room with ultrasound turned on the Teams Rooms console, and you want to join your meeting to the Teams Room, you see it in the meeting's prejoin screen in the list of available rooms because those rooms are sorted and listed at the top of the screen. This lets someone select the exact Teams Rooms console and conference room they want to use for their meeting.Proximity Join using ultrasound isn't currently available for Teams Rooms on Android.Room Remote doesn't support ultrasound proximity because ultrasound is disabled when in a call.

Caution

People or animals with sensitive hearing may be able to hear the ultrasound tones. In our testing, this sound hasn't been distressing, and is only output prior to a call being initiated but take note if those who may hear the ultrasound tones are present in your environment to decide if this feature should be enabled or not.

### Ultrasound supported devices

| Supported Devices |
| --- |
| Crestron UC-2 |
| Crestron MercuryX |
| Logi Tap |

## Administration and settings

There are multiple ways and tools you can use to manage Proximity Join settings for Microsoft Teams Rooms.

Note

The settings for ultrasound don't apply to Teams Room on Android but the Bluetooth settings are available for those devices.

# [Pro Management Portal](#tab/pmp)
Management of proximity features is available in the Teams Rooms Pro Management portal:

- Allow Bluetooth beaconing

    - Automatically accept proximity-based meeting invitations
    - Remote control from personal devices
- Enable ultrasound beacon

# [Teams Admin Center (Android)](#tab/tac)
Management of proximity features for Teams Rooms on Android is available in Teams Admin Center, Teams Rooms on Android Configuration Profiles:

- Bluetooth beaconing

# [Local device settings](#tab/app-settings)
Management of proximity features is available in settings on the device:

- Allow Bluetooth beaconing

    - Automatically accept proximity-based meeting invitations
    - Remote control from personal devices

Note

Ultrasound controls aren't available yet within the device settings.

---