---
layout: Conceptual
title: Device settings available for remote management - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/device-settings-available
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: 'This article provides guidance on what device settings are available for remote management from the Teams Rooms Pro Management portal.   '
author: obahidika
manager: srpall@microsoft.com
ms.author: obahidika
ms.service: microsoft-365-admin
ms.topic: article
ms.date: 2026-10-08T00:00:00.0000000Z
locale: en-us
document_id: b9ad7ef2-7410-be90-55ee-5132fd55929f
document_version_independent_id: b9ad7ef2-7410-be90-55ee-5132fd55929f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/device-settings-available.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/device-settings-available
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/device-settings-available.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b13452e4-214d-381a-c569-ceab9a30b466
---

# [Teams Rooms on Windows](#tab/WindowsSettings)
Teams Rooms devices have settings that can either be applied on the device and synchronized with the Teams Rooms Pro management portal or from the Teams Rooms Pro management portal to the device. Here are the settings that are visible in the portal.

Note

Some settings available within the Pro Management Portal are only available for specific device types, ensure the setting is supported if a deployment doesn't work as expected.

### About

| **Field** | **Input** | **Description** | **Note** |
| --- | --- | --- | --- |
| Device ID | Number | Unique device identifier | Information only |
| Agent version | Number | Current Teams Rooms Pro Management agent version number. | Information only |
| Last agent activity | Date/Time | Last known time the Teams Rooms Pro Management agent connected with the Service. | Information only |
| OS version | Number | Current Windows operating system build | Information only |
| IP address | Number | Device IP address detected | Information only |
| BIOS manufacturer | Text | Name of BIOS manufacturer | Information only |
| BIOS name | Text | BIOS update name | Information only |
| SMBIOSBIOSVersion | Number |  |  |
| Latitude | Number | Coordinates of the device derived by Windows location settings on device. | Information only |
| Longitude | Number | Coordinates of the device derived by Windows location settings on device. | Information only |
| Time zone | Text | Provided by Microsoft for use with Windows and the .NET TimeZoneInfo class. | Information only |
| Time zone (IANA) | Text | Time zones provided by IANA. | Information only |

### Account

| **Field** | **Input** | **Description** | **Note** |
| --- | --- | --- | --- |
| Exchange sign in address | Text | Device's resource account sign-in address. | Information only |
| Supported meeting mode | Text | Teams only are displayed. | Information only |
| Public Preview | Text | Enrolls the device into Teams Ring 3.6 Public Preview. | Enabling this setting enables Public Preview features on your Teams Rooms device. Use caution as devices in early preview rings aren't supported by Microsoft Support. Available for Individual or bulk changes. |

### Meetings

| **Field** | **Input** | **Description** | **Note** |
| --- | --- | --- | --- |
| Default content layout in single display mode | Radio buttons | Focus on Content and People OR Focus on Content only | Set the default content layout for single display mode. Meeting participants can change the default content layout during meetings. Available for Individual or bulk changes. |
| Show Meeting Chat | Toggle | Enabled by default. | If disabled, meeting chat functionality (including chat bubbles and chat selection) isn't available in any meeting layout on the Teams Rooms device. Available for Individual or bulk changes. |
| Open Chat by Default | Checkbox | Enabled by default. | Checkbox won't be visible if Show Meeting Chat is disabled. If disabled, chat panel won't show by default in meetings using Gallery view. Available for Individual or bulk changes. |
| Front Row Experience | Toggle | Enabled by default. | If false, Front row is disabled. For more information, see [Remotely configure Front Row on Teams Rooms](/en-us/microsoftteams/rooms/manage-front-row). Available for Individual or bulk changes. |
| Default Layout Experience | Radio button | Front row default | Select the default meeting join layout as Gallery or Front Row. Available for Individual or bulk changes. Available for Individual or bulk changes. |
| Front Row Video Size | Dropdown | Medium (default), Small, Large | Sets the size of Front row to provide more or less space for remote participant video and shared content. Available for Individual or bulk changes. |
| Right front row panel | Dropdown | Show raised hand list, Show meeting chat, Hide the panel | Configure the position of the raised hand and chat components in the meeting panels to the left and right of meeting content on front-of-room displays. Available for Individual or bulk changes. |
| Left front row panel | Dropdown | Show raised hand list, Show meeting chat, Hide the panel | Configure the position of the raised hand and chat components in the meeting panels to the left and right of meeting content on front-of-room displays. Available for Individual or bulk changes. |
| Automatic Screen sharing | Toggle | Disabled by default. | If true, a connected HDMI ingest will be automatically shared on the Front of Room display and when in a Teams Meeting it's automatically shared to remote participants. If false, a connected HDMI ingest will be automatically shared on the Front of Room display in and out of a Teams meeting but it will not be shared to remote participants in the meeting automatically, users need to select the share icon to shared content to remote participants. Available for Individual or bulk changes. |
| Show meeting name | Toggle | Enabled by default. | If disabled, the meeting name is hidden from the console and Front of Room calendar displays. Available for Individual or bulk changes. |
| Autoleave if everyone else left the meeting | Toggle | Disabled by default. | If true, device will automatically leave the meeting if it's the only participant in the meeting for more than 5 minutes before or after the scheduled meeting time. Available for Individual or bulk changes. |
| HDMI ingest audio sharing | Toggle | Disabled by default. | When disabled, audio from a connected HDMI ingest isn't shared to Teams Meeting participants. Available for Individual or bulk changes. |
| Enable room capacity notifications | Toggle | Enabled by default. | Enabled by default to provide warnings to in room participants that the room has reached capacity (this requires the room capacity be set in Exchange and a camera capable of people counting). Set to false if you wish to disable these warnings. Available for Individual or bulk changes. |
| Show Captions | Toggle | Disabled by default. | When enabled, captions will be displayed. |
| Filter Profane words in captions and transcripts | Toggle | Enabled by default. | When captions are on, use of profane words are redacted. |
| Enable People Count | Toggle | Enabled by default. | If true, people count will be enabled for Teams Rooms. Available for Individual or bulk changes. |
| Require passcode for all Teams meetings | Toggle | Disabled by default. If true, users are required to enter the correct meeting ID and passcode to join all Teams meetings scheduled in the room with a Microsoft Teams Room Pro license. | Available for Individual or bulk changes. |
| Require passcode for all Private Teams meetings | Toggle | Disabled by default. | If true, users are required to enter the correct meeting ID and passcode to join all private Teams meetings scheduled in the room with a Microsoft Teams Room Pro license. Available for Individual or bulk changes. |
| Join third-party meetings | Checkbox | Cisco Webex, Zoom, GotoMeetings, RingCentral Meetings, Amazon Chime | May require calling plan to enable. For more information, see [Join third-party meetings](/en-us/microsoftteams/rooms/third-party-join?tabs=MTRW). Available for Individual or bulk changes. |
| Join with room info | Radio button | Uses conference room account info to join third party meetings. | Available for Individual or bulk changes. |
| Join with custom info | Radio button | Disabled by default. | If this value is set to true, you must specify both *CustomDisplayNameForThirdPartyMeetings* and *CustomDisplayEmailForThirdPartyMeetings* must be specified. Available for Individual or bulk changes. |
| Show Room Facilitator QR code | Toggle | Disabled by default. | Available for Individual or bulk changes. |

### Device

| **Field** | **Input** | **Description** | **Note** |
| --- | --- | --- | --- |
| Dual Monitor mode | Toggle | Disabled by default. | Dual screen mode is enabled. Otherwise, the device uses single screen mode. Available for Individual or bulk changes. |
| Allow content duplication | Checkbox | Disabled by default. | When checkbox is selected, content is shown on both screens in dual screen mode, when out of meeting. Available for Individual or bulk changes. |
| Enable Resolution and Scaling: | Toggle | Disabled by default. | If true, the display resolution and scale setting will be applied. This setting affects both the main front-of-room display and extended front-of-room display once this setting is enabled. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](/en-us/microsoftteams/rooms/manage-front-room-scale-res). Available for Individual or bulk changes. |
| Main Front of Room Display Resolution (Width) | Number | Enter a value. | The width entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Available for Individual or bulk changes. **Note**: *Changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message This is normal.* |
| Main Front of Room Display (Height) | Number | Enter a value. | The height entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Available for Individual or bulk changes. **Note**: *Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message. This is normal.* |
| Main Front of Room scaling | Slider | Input numeric value of scaling. | Valid values are 100 (recommended), 125, 150, 175, 200, 225, 250, and 300. If you input greater than 300 and your front-of-room display only supports up to 300, it's set to 300. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](/en-us/microsoftteams/rooms/manage-front-room-scale-res). Available for Individual or bulk changes. |
| Extended Front of Room Display Resolution (width) | Number | Enter a value. | The width entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Note: Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message. This is normal. Available for Individual or bulk changes. |
| Extended Front of Room Display Resolution (height) | Number | Enter a value. | The height entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Available for Individual or bulk changes. **Note**: *Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message.* |
| Extended Front of Room scaling | Slider | Input numeric value of scaling. | Valid values are 100 (recommended), 125, 150, 175, 200, 225, 250, and 300. If you input greater than 300 and your front-of-room display only supports up to 300, it's set to 300. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](/en-us/microsoftteams/rooms/manage-front-room-scale-res). Available for Individual or bulk changes. **Note**: *Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message.* |
| Disable Split video gallery | Toggle | Default is false. | This setting is only applicable to dual-display rooms. Specify true to disable splitting video gallery across both screens. This will also disable Front row layout, and any settings associated with Front row layout. Available for Individual or bulk changes. |
| Remove Front of room calendar | Toggle | Disabled by default. | Remove the calendar on front-of-room displays. Available for Individual or bulk changes. |
| Allow Bluetooth beaconing | Toggle | Enabled by default. | When checked, proximity-based meeting invitations using Bluetooth are automatically accepted. Available for Individual or bulk changes. |
| Remote control from personal devices | Checkbox | Enabled by default. | Allow Bluetooth beaconing must be true. When checked, room remote connections are allowed. Room Remote won't work if only ultrasound is turned on. Available for Individual or bulk changes. |
| Ultrasound beaconing | Toggle | Enabled by default. | Enables ultrasound-based proximity detection. Available for individual or bulk changes. For more information, see [Proximity Join using Bluetooth and ultrasound](/en-us/microsoftteams/rooms/proximity-join?tabs=portal). |
| Automatically accept proximity-based meeting invitations | Checkbox | Enabled by default. | When selected, supported proximity-based meeting invitations are automatically accepted. This setting appears when **Ultrasound beaconing** is enabled. Available for individual or bulk changes. |
| Show Room QR Code | Toggle | Enabled by default. | When toggled on, Proximity-based meeting invitations via QR code are automatically accepted. For more information, see [Join meetings with QR codes](/en-us/microsoftteams/rooms/teams-rooms-qr-codes). Available for Individual or bulk changes. |
| Send feedback to the Teams Rooms Pro Management portal | Toggle | Enabled by default. | Allows logs to be sent with feedback submitted using Report a problem. To ensure logs and feedback with larger sizes are delivered, adjust the message size restriction for your mailboxes on the Exchange admin center. Available for Individual or bulk changes. |
| Enhanced diagnostics | Toggle | Enabled by default. | During nightly maintenance reboots, enhanced diagnostics runs additional checks to identify complex room issues, including audio output quality, black or empty camera output, and Teams application display resolution or scaling problems. When detected, Teams Rooms Pro Management can automatically remediate these issues through configuration updates or device resets. |

### Coordinated meetings

| **Field** | **Input** | **Description** | **Note** |
| --- | --- | --- | --- |
| Coordinated Meetings | Toggle | Container for the configuration elements for Coordinated Meetings. | Determines whether Teams is configured to participate in Coordinated Meetings with other devices. Available for Individual or bulk changes. |
| Turn on this device’s microphone | Toggle | Disabled by default. | To avoid causing an echo effect, make sure only one device's microphone is enabled. Available for Individual or bulk changes when coordinated meetings toggle is on. |
| Let people enable when joining a meeting | Checkbox | Disabled by default. | Available for Individual or bulk changes when coordinated meetings toggle is on. |
| Turn on this device’s camera | Toggle | Disabled by default. | Available for Individual or bulk changes when coordinated meetings toggle is on. |
| Let people enable when joining a meeting | Toggle | Disabled by default. | Available for Individual or bulk changes when coordinated meetings toggle is on. |
| Turn on whiteboarding for this device | Toggle | Disabled by default. | Available for Individual or bulk changes when coordinated meetings toggle is on. |
| Let people enable when joining a meeting | Checkbox | Disabled by default. | Available for Individual or bulk changes when coordinated meetings toggle is on. |
| Trusted device accounts | String | Separate with commas. | This is a comma-separated list of UPNs for each Teams Rooms device or Surface Hub that the device should accept meeting join requests from, or to which meeting join requests should be sent. |

### Peripherals

| **Field** | **Input** | **Description** | **Note** |
| --- | --- | --- | --- |
| Conference Microphone | Dropdown | Select option | Set the microphone used as the recording device in a conference. Available for Individual setting changes. Not available for bulk setting changes. |
| Conference audio speaker | Dropdown | Select option | Set the device to be used as speaker for the conference. This setting is used to set the speaker device used in a call. Available for Individual setting changes. Not available for bulk setting changes. |
| Conference audio speaker default volume | Slider |  | Adjusts the conference audio speaker volume. Available for Individual or bulk changes. |
| Default Speaker | Dropdown |  | Set the device to be used to play the audio from an HDMI ingest source. Available for Individual setting changes. Not available for bulk setting changes. |
| Default Speaker volume | Slider |  | Adjusts the default speaker volume. Available for Individual or bulk changes. |
| Ultrasound speaker | Dropdown |  | Select the speaker used for ultrasound signals. This field appears only when a supported ultrasound device is discovered. Available for individual setting changes. Not available for bulk setting changes. |
| Ultrasound speaker volume | Slider | 0–100 | Adjusts the volume of the configured ultrasound speaker. Available for individual or bulk changes. |
| Default Camera | Dropdown |  | Set the default camera. Available for Individual setting changes. Not available for bulk setting changes. |
| Enable Cloud intelliframe | Toggle | Disabled by default. | Allows Teams Rooms to break up the single video feed of the room into a composite view made up of focused and framed video tiles that feature in-room attendees. Available for Individual or bulk changes. |
| Multiple Camera views | Toggle | Disabled by default. | Enable to set up multiple cameras. For more information, see [Multi Camera](/en-us/microsoftteams/rooms/multicamera-view). Available for Individual setting changes. Not available for bulk setting changes. |
| Additional Camera(s) | Dropdown |  | Add up to three cameras. Available for Individual setting changes. Not available for bulk setting changes. |
| Local camera PTZ control | Toggle | Disabled by default. | Allows room participants to manually pan, tilt, and zoom supported cameras. Available for individual or bulk changes on Teams Rooms on Windows and Windows-based all-in-one touchboards. |
| Content camera | Dropdown |  | Select the camera configured in room to share analog whiteboard content in a meeting. Available for Individual setting changes. Not available for bulk setting changes. |
| Allow content enhancement | Checkbox |  | When set to true (the default), the content camera image is digitally enhanced: the whiteboard edge is detected and an appropriate zoom is selected, ink lines are enhanced, and the person writing on the whiteboard is made transparent. Set to false if you intend to send a raw video feed to meeting participants for spaces where a whiteboard isn't drawn on with a pen and instead the camera is used to show sticky notes, posters, or other media. Available for Individual setting changes. Not available for bulk setting changes. |
| Content camera inverted | Checkbox |  | Specify if the content camera is physically installed upside down. For content cameras that support automatic rotation, specify false. Available for Individual setting changes. Not available for bulk setting changes. |
| Enable noise suppression | Toggle | Disabled by default. | Controls noise suppression levels in Teams. **Off** Use OEM-provided noise suppression only. **On** Suppresses all background noises (stationary and nonstationary) that aren't speech. Available for Individual or bulk changes. |

### Theming

| **Field** | **Input** | **Description** |
| --- | --- | --- |
| Theming | Dropdown | Select a default background. Available for Individual or bulk changes. |

Note

Currently, managing custom backgrounds isn't supported in the Teams Rooms Pro management portal.

### Digital Signage

The ability to change specific digital settings is permission based. If you don't have access to change these settings, please check with your Teams Rooms Pro manager administrator. Learn more by seeing [Digital Signage](/en-us/microsoftteams/rooms/digital-signage).

| **Field** | **Input** | **Description** |
| --- | --- | --- |
| Digital Signage | Toggle | Whether the toggle is enabled or editable will be determined by the Digital Signage tenant level settings. When enabled, it determines whether digital signage will be displayed in the room. |
| Reset Digital Signage | Checkbox | Resetting digital signage reverts the digital signage settings of this room to system defaults, including disabling digital signage and unregistering the room from trusted third-party signage sources where the room is enrolled in, if applicable. This action is irreversible. |
| Show Teams Rooms banner | Toggle | Enable to display date, time, room name, and calendar preview while digital signage is active. Disable to hide room information. |
| Display Period | Header |  |
| Activate signage when device has been idle for X minutes | Number | Set the activation time in range of 1 to 100 minutes. |
| Deactivate signage with meeting is starting in X minutes | Number | Set the deactivation time in range of 1 to 100 minutes. |
| Allow screen time out when device is idle | Toggle | Enable to respect OS screen time out settings. Disable to keep signage active on idle devices. |
| Signage source | Selection | Reflects the trusted third-party signage sources where the room is enrolled in. |

# [Teams Android Devices](#tab/Android)
The full settings list documentation is coming soon.

### Peripherals

| **Field** | **Input** | **Description** | **Note** |
| --- | --- | --- | --- |
| Local PTZ camera control | Toggle | Disabled by default. | Allows room participants to manually pan, tilt, and zoom supported cameras. Available for individual or bulk changes on Teams Rooms on Android and paired touch consoles. |

---