---
layout: Conceptual
title: Enable People Recognition on Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/teams-rooms-people-recognition
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to enable people recognition with voice and face biometric data on Teams Rooms
author: PPAARRIISS
ms.author: parisataheri
manager: kspiess
ms.topic: concept-article
ms.service: msteams
ms.subservice: itpro-rooms
ms.date: 2025-12-12T00:00:00.0000000Z
ms.localizationpriority: medium
locale: en-us
document_id: 65cc87de-7418-e6df-f59b-c57329bd83d6
document_version_independent_id: 65cc87de-7418-e6df-f59b-c57329bd83d6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/teams-rooms-people-recognition.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/teams-rooms-people-recognition
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/teams-rooms-people-recognition.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2624a017-7337-44fa-9494-a407bb0e59fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/a438284e-c3c3-4c36-ab0b-aa7c244b912c
platformId: 5e905d81-4004-8c66-8c32-a36f6502ae3d
---

# Enable People Recognition on Teams Rooms - Microsoft Teams | Microsoft Learn

Teams Rooms support **voice** and **face recognition** to identify who is speaking or appearing on camera in meetings from within the meeting room. When an [enrolled user](/en-us/microsoftteams/rooms/voice-and-face-recognition) joins meetings from a Teams Room, their contributions are accurately attributed in transcriptions, meeting recaps, and Copilot experiences. Recognition enhances collaboration by helping participants easily follow who said what, even when multiple people are in the room. 

## What is People Recognition?

By default, participants in a Teams Room are distinguished from each other as "Speaker 1" or "Participant 1", without any biometric identification. However, to further the meeting experience, Teams Rooms offer People Recognition, which can **recognize enrolled users by their voice or face**.

- **Voice recognition:** Uses an enrolled user’s voice profile to identify who is speaking in the room.
- **Face recognition:** Uses an enrolled user’s face profile to identify them when they appear on camera in a meeting room.

If an in-room participant isn't enrolled, they're still displayed on video as Participant X and in the transcript as Speaker X.

| Device type | Voice recognition | Face recognition | Configuration method |
| --- | --- | --- | --- |
| Teams Rooms on Windows | ✅ Supported | ✅ Supported | Device settings or meeting policy |
| Teams Rooms on Android | ✅ Supported | 🚫 Not supported | Device settings or meeting policy |

Face recognition requires a [supported camera](/en-us/microsoftteams/devices/multistream-intelliframe#supported-cameras) or Teams Rooms on Windows devices with [Cloud IntelliFrame](/en-us/microsoftteams/devices/cloud-intelliframe) enabled.

Important

This feature is exclusive to Microsoft Teams Rooms devices with a Teams Rooms Pro license.

## Step 1: Enable recognition

Recognition in Teams Rooms can be configured through either device-level settings or a Teams Meeting policy. We recommend using device-level settings because meeting policy-based configuration will be retired in the future.

Device settings offer the most flexible configuration for meeting room admins. The table explains the two configuration options.

| Setting | Default Behavior | Description |
| --- | --- | --- |
| Voice Recognition | Off | Users with enrolled voice profile are identified with their voice when using this device. Others are distinguished as meeting participants. |
| Face Recognition | Off | Users with enrolled face profile are identified with their face when using this device. Others are distinguished as meeting participants. |

[![Screenshot of Pro Management Portal user interface showing regnition settings.](media/teams-rooms-people-recognition/rooms-1-0.png)](media/teams-rooms-people-recognition/rooms-1-0.png#lightbox)

## #tab/device-settings

#### Use the Pro Management Portal

1. Log in to the [Teams Pro Management Portal](enrolling-mtrp-managed-service).
2. Select **Rooms**.
3. Select **Settings** followed by the **Recognition** tab
4. Enable **Configure with device settings**
5. Modify to the desired configuration
6. Select **Apply**
7. Choose when to apply the settings change and select **Submit**

Tip

These changes can be completed in bulk within the Pro Management Portal with a /microsoftteams/rooms/pro-portal-settings.

#### Configure locally on the device

1. On the Teams Room console, go to **Settings &gt; Recognition**.
2. Select **Configure with device settings (Recommended)**.
3. Turn on **Voice recognition** and/or **Face recognition** as applicable.

[![Screenshot of Teams Rooms Settings Recognition Tab](media/teams-rooms-people-recognition/peripherals.png)](media/teams-rooms-people-recognition/peripherals.png#lightbox)

## #tab/meeting-policy

Note

Meeting policy–based configuration will be retired in the future.

Admins can also manage recognition through **Teams Meeting policies**.

1. Connect to /microsoftteams/teams-powershell-managing-teams
2. Modify the existing /powershell/module/microsoftteams/set-csteamsmeetingpolicy OR create a unique Teams Meeting policy modifying the attributes in the example

```powershell
Set-CsTeamsMeetingPolicy -Identity PolicyName -roomAttributeUserOverride Attribute -roomPeopleNameUserOverride On
```

| Policy | Description | Values and Behavior |
| --- | --- | --- |
| roomAttributeUserOverride | Control the voice-based user identification in meeting rooms. | **Off**<br>- The room won't send audio for identification.<br>- Meeting room users won't be attributed or distinguished, and their voice signatures won't be retrieved or used.<br>- Meeting room users are unknown.<br><br>**Attribute**<br>- Rooms users who have their voice enrolled will be attributed in the transcription.<br>- Users who aren't enrolled show as Speaker X.<br><br>**Distinguish**<br>- Rooms users will be distinguished and separated as Speaker 1, Speaker 2, .... in the transcription.<br>- Irrespective of enrollment status of the user, their name won't show in the transcription. |
| roomPeopleNameUserOverride | Control the video-based user identification in meeting rooms. | **Off**<br>- The room won't send video for identification.<br><br>**On**<br>- Room users captured by supported cameras will be identified.<br>- Users who aren't enrolled show as Participant X. |

If transcription isn't enabled in the Teams Meeting policy, voice identification won't occur.

## Step 2: Enable user enrollment

Voice and face recognition only works if end users have completed enrollment by creating their biometric profiles in Teams. IT admins can manage enrollment permissions using the **Teams AI Policies**.

Review /microsoftteams/rooms/voice-and-face-recognition#admin-settings for configuration guidance.

## Privacy and compliance

Both **voice** and **face recognition** features follow Microsoft’s enterprise-grade privacy and compliance standards.

- Voice and face profiles are encrypted and stored securely.
- Users can **unenroll** at any time.
- Recognition data is used only for in-meeting identification, transcription, and AI-generated recaps.
- Organizations can disable enrollment or recognition through policy controls.

Learn more at [Overview and configuration of voice and face enrollment](/en-us/microsoftteams/rooms/voice-and-face-recognition) and [aka.ms/privacy](https://www.microsoft.com/privacy).