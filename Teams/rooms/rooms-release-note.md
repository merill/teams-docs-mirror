---
layout: Conceptual
title: Release notes for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-release-note
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: henrikalim
ms.date: 2026-10-13T00:00:00.0000000Z
ms.topic: release-notes
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
description: Admin can read the release notes for Microsoft Teams Rooms, which list cumulative improvements in Microsoft Teams Rooms.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 1365f9b8-001c-daa7-592e-d88b9bb3a10e
document_version_independent_id: ffba1b4d-1f19-4dac-0b55-053d98fe26b7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-release-note.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-release-note
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-release-note.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 183d26ce-b005-a762-a363-d3f556de7de6
---

# Release notes for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

This article discusses cumulative improvements in Microsoft Teams Rooms on Windows and Android devices.

There are two types of updates for Teams Rooms: Teams Rooms app updates and Teams Web client.

For information about Teams Rooms app updates, select the **Teams Rooms on Windows** or **Teams Rooms on Android** tabs.

Teams Web client updates happen via the Teams web app delivery services. The Teams web client is a cloud-based service that doesn't require an update to the local application installed on the device.

For more information on how Teams updates, see [Teams update process](../teams-client-update).

Teams Rooms align to the Modern Lifecycle Policy. For more information, see [Teams update process](../teams-client-update#servicing-agreement).

# [Teams Rooms on Windows](#tab/Windows)
## Teams Rooms on Windows version history

| Release | Published date |
| --- | --- |
| 5.7.112.0 | 9/28/2026 |
| 5.6.301.0 | 10/21/2026 |
| 5.6.210.0 | 8/3/2026 |
| 5.6.137.0 | 6/18/2026 |
| 5.6.135.0 | 5/27/2026 |
| 5.5.129.0 | 1/28/2026 |
| 5.4.210.0 | 9/29/2025 |
| 5.3.205.0 | 8/12/2025 |
| 5.3.111.0 | 4/22/2025 |
| 5.3.69.0 | 3/17/2025 |
| 5.2.115.0 | 9/26/2024 |
| 5.1.28.0 | 8/8/2024 |

## Teams Rooms on Windows feature introduction and issue resolution

Teams Rooms app updates happen using the [Pro Management Portal](/en-us/microsoftteams/rooms/update-management) or [manually](manual-update). Updates are applied to the Teams Room application that is installed locally on the device.

Features with the ![](../media/mtr-pro-icon.png) icon are available only with Teams Rooms Pro license.

### 5.7.112.0 (9/28/2026)

Introduced in this update:

- **App update delivery via Pro management portal**![](../media/mtr-pro-icon.png)**:** Teams Rooms app updates will be distributed exclusively through Pro Management Portal (PMP) and will no longer be available through the Microsoft Store.
- **Local Pan-tilt-zoom (PTZ) controls**: Native PTZ control support for compatible cameras from the in-room console. Feature enablement is complete. [Learn more](/en-us/microsoftteams/rooms/camera-controls).

Note

This feature was added to this release as part of a web client build on 10/29/2026.

- **AI-powered notes for in-person meetings with Facilitator**![](../media/mtr-pro-icon.png)**:** Facilitator captures real-time notes and meeting outcomes during in-person meetings. Simply tap to start taking notes, view them on the front-of-room display or touch board, and enter your name to save them for later access in meeting recap. [Learn more](/en-us/microsoftteams/rooms/facilitator-teams-rooms).

### 5.6.301.0 (10/21/2026)

Introduced in this update:

- Security update for [Autopilot and Autologin](/en-us/microsoftteams/rooms/autopilot-autologin) and [One-Time Passcode](/en-us/microsoftteams/rooms/create-otp) functionality.

Note

This build was released after 5.7.112.0 was already released and only for the [day zero update capability](/en-us/microsoftteams/rooms/zero-daydeviceupdates) on Teams Rooms on Windows devices to ensure new devices can be deployed and successfully signed in using the Autologin or One-Time Passcode features. This update will not be visible in the Pro Management Portal for direct installation.

### 5.6.210.0 (8/3/2026)

Introduced in this update:

- **Support for Windows 25H2:** Once this Teams app update is installed, devices running Windows 11 will automatically update to Windows 11 25H2 within approximately 1 week.

### 5.6.137.0 (6/18/2026)

Note

These features were added to this release as part of a web client build on 7/20/2026.

- **Ad-hoc room reservation**![](../media/mtr-pro-icon.png)**:** Users can quickly book a meeting room for immediate use, helping to avoid scheduling conflicts and ensure uninterrupted spontaneous meetings. A “Reserve” button appears on the calendar when the room is available. IT admins can control this feature using the “Allow ad hoc room reservation” setting on the Pro management portal. [Learn more](/en-us/MicrosoftTeams/rooms/mtr-home-refresh#ad-hoc-room-reservation).
- **Together mode deprecation**: Together Mode view in Teams meetings is deprecated for all Teams clients. [Learn more](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/goodbye-together-mode-hello-simplified-meeting-layouts-in-microsoft-teams/4519312).

Resolved Issue:

- Resolved a script launch regression introduced in 5.6.135.0

### 5.6.135.0 (5/27/2026)

Introduced in this update:

- **Miracast**![](../media/mtr-pro-icon.png)**:** Along with Teams Cast and HDMI ingest, all-in-one touch boards running Windows will support Miracast for wireless screen sharing. Miracast enables cable-free mirroring of your device’s screen to share presentations or other content. (Note: Teams Rooms on Windows devices with a console will support Miracast with a future client release.) [Learn more](/en-us/MicrosoftTeams/rooms/miracast).
- **Room health signals and notifications:** When critical issues impact room functionality, users see a banner notification on both the front-of-room display and console in Teams Rooms on Windows. This cannot be disabled and helps set user expectations by proactively surfacing room health issues and ensure productive meetings. [Learn more](/en-us/microsoftteams/rooms/mtr-home-refresh#room-health-banner).
- **Enhanced issue detection in Teams Rooms on Windows and auto-remediation with Teams Rooms Pro Management**![](../media/mtr-pro-icon.png)**:** Enhanced in-room signal detection capabilities that expand beyond existing peripheral monitoring in Pro Management Portal. Teams Rooms on Windows now intelligently assess room audio output quality, black or empty camera output, and that the Teams application is displayed correctly during the nightly maintenance window. Teams Rooms Pro Management automatically remediates these issues through configuration changes or device resets. This ensures users have reliable, ready-to-use meeting rooms, while IT admins benefit from reduced manual troubleshooting and increased uptime. [Learn more](/en-us/microsoftteams/rooms/signals?tabs=MTRW).
- **Front of room resolution & display scaling default enforcement:** The Teams Rooms application reviews the current front of room display resolution and applies a recommended scaling factor to ensure consistent sized screen elements. A 1920x1080 resolution defaults to 100% scaling and 3840x2160 defaults to 200%, a sliding scale based on those configurations is used for other resolutions. This change will take effect on all devices which have not had the scaling overridden using the Pro Management Portal settings or the XML. Those methods can also be used to override the behavior after this update has been deployed. [Learn more](/en-us/microsoftteams/rooms/manage-front-room-scale-res).
- **Changes to how resolution & scaling are configured:** Configuring resolution and scaling for a Teams Room device should only be done using the Pro Management Portal settings or XML to ensure a custom configuration is not overridden. The configuration script still functions but may be overridden if settings outside expected parameters are configured. [Learn more](/en-us/microsoftteams/rooms/manage-front-room-scale-res).
- **Human interpreter listening mode support**![](../media/mtr-pro-icon.png)**:** Participants in a Teams Rooms on Windows can now have professional interpreters listen in and translate the meeting in their selected language in real-time, without disrupting the speaker's original flow of delivery. Languages, pre-set by the meeting organizer, can be selected and changed by participants. [Learn more](https://support.microsoft.com/teams/meetings/use-language-interpretation-in-microsoft-teams-meetings).

Resolved issues:

- Fixed an issue where Coordinated meeting join’s audio and video settings were not applied correctly in Whiteboard meetings.
- Fixed an issue where the touch console would freeze after entering or leaving a breakout room.

### 5.5.129.0 (1/28/2026)

Introduced in this update:

- **Interpreter agent support during meetings**![](../media/mtr-pro-icon.png)**:** The Interpreter agent, which enables real-time interpretation in up to nine languages so each participant can speak and listen in the language of their choice, is now available in Teams Rooms on Windows with a Teams Rooms Pro license. Meeting participants can also opt-in to have Interpreter simulate their personal voice for a more inclusive experience. 20 hours of interpretation included per room account per month with a Teams Rooms Pro license. Access beyond included hours is subject to available capacity. This is controlled using the [Teams Meeting Policy](/en-us/microsoftteams/interpreter-agent-teams#manage-interpreter-using-powershell).
- **Multi-camera view switching**![](../media/mtr-pro-icon.png)**:** When in a meeting with a Teams Room on Windows configured with multiple cameras, you can switch between the room’s camera views using the participant panel on the console or the video tile controls on a touch board, helping you optimize your view.

Resolved Issues:

- Disabled "Voice Clarity” feature in Windows to resolve and prevent audio processing conflicts. [Learn More.](https://support.microsoft.com/topic/windows-11-version-24h2-update-history-0929c747-1815-4543-8461-0160d16f15e5)
- **Direct Guest Join with Teams Rooms on Windows and Google Meet**: Organizations now have expanded meeting interoperability with two-way Direct Guest Join (DGJ) between Google Meet and Teams meetings. Teams Rooms on Windows devices can join Google Meet meetings and Google Meet devices can join Teams meetings. Users can join with one click through the calendar or by meeting ID. [Learn More.](/en-us/microsoftteams/rooms/third-party-join)

### 5.4.210.0 (9/29/2025)

Introduced in this update:

- **Support for Facilitator agent in scheduled Teams meetings**![](../media/mtr-pro-icon.png)**:** When joining an assigned Teams meeting instance from a Microsoft Teams Room, participants in the Teams Room can experience all of the benefits of having Facilitator, including AI-generated notes, agenda and time tracking, AI queries from the web, etc. These features can be seen on the front-of-room display in the Teams Rooms, and is accessible to individual participants after the meeting instance via desktop and web.
- **Support for certified Touch Consoles connected to Touch board devices:** You can now connect certified Touch consoles to Interactive touch board devices like the Surface Hub 3. Users can control the Teams Rooms experience either on the touchscreen or using the console.
- **Browser support for touch boards**![](../media/mtr-pro-icon.png)**:** Now you can access websites and line-of-business web applications using private browsing mode with Microsoft Edge on Teams Rooms on Windows touch boards, including Surface Hub 3. You can use the browser during meetings or outside of them, and admins can manage browsing policies via Pro Management Portal to ensure a secure and safe browsing experience. [Learn more.](/en-us/microsoftteams/rooms/edge-browser-for-touch-boards)
- **Recognition of in-room participants on meeting roster for Teams Rooms with Cloud IntelliFrame**![](../media/mtr-pro-icon.png)**:** Enrolled in-room participants during scheduled meetings are now recognized and listed in the meeting roster for remote attendees. Available only on Windows-based Teams Rooms using Cloud IntelliFrame. Requires the organization to enable face and voice recognition. Requires in-room participants to enroll with a recognition profile in Teams. Requires a scheduled meeting that lists the participant on the meeting invite.
- **Manage voice and face recognition for rooms via device settings:** To simplify management and reduce configuration friction for voice and face recognition in Microsoft Teams Rooms, we’re introducing new admin-facing settings in the Teams Pro Management Portal. These settings replace PowerShell-based configuration with a more intuitive UI, offering clearer visibility into recognition status across rooms.
- **Multiple camera view shown in preview video and camera settings dialog**![](../media/mtr-pro-icon.png)**:** When multiple camera views are enabled, the preview video on the front-of-room display and the camera settings dialog will show multiple camera views. This feature allows in-room users to be aware of all camera streams that are simultaneously streaming to remote users.
- **Support for multiple camera views and IntelliFrame from Teams Rooms on Windows in Teams webinar and structured meetings:** Multiple camera views and IntelliFrame (Multi-stream and Cloud) from Teams Rooms on Windows are now available in Teams webinar and structured meetings with "Manage what attendees see" enabled. Organizers and presenters of these meetings can access intelligent camera views and bring them on the live stage for attendees.
- **Surface Hub rotation support on 24H2**: Surface Hub 3 devices with older firmware don't support rotation when running Windows 11 24H2. Surface SMC firmware version 3.142.20.0 restores this functionality and was released on October 20, 2025. [Learn more.](/en-us/surface-hub/surface-hub-3-update-history#october-20-release)
- **Front-of-room view control for town hall and webinar**![](../media/mtr-pro-icon.png)**:** When a Teams Rooms on Windows is invited as a presenter in a town hall or webinar, the front-of-room display defaults to the attendee view. Room users always have full control from the console, including green room and off-stage management, and can switch the front-of-room display to presenter view without impacting attendees. [Learn more.](https://support.microsoft.com/office/host-an-event-from-a-microsoft-teams-room-mtr-d7ff15e0-6516-4ebc-ae03-a2bdf58a4478)

### 5.3.205.0 (8/12/2025)

Introduced in this update:

- **Support for Windows 24H2:** Once this Teams app update is installed, devices running Windows 11 will automatically update to Windows 11 24H2 within approximately 1 week.

### 5.3.111.0 (4/22/2025)

Introduced in this update:

- **Live transcription**![](../media/mtr-pro-icon.png)**:** Users can start or stop transcription and view the meeting transcript directly from Teams Rooms devices. Users can also change the meeting spoken language, translate the transcript to their desired language, as well as view the original and translated transcript side by side, ensuring that the transcript is accurate and meaningful for non-English speakers. IT admins can allow or prevent users (including resource accounts) from transcribing meetings using the meeting transcription policy in Teams admin center. [Learn more](/en-us/Microsoftteams/meeting-transcription-captions#transcription).
- **Translated captions**![](../media/mtr-pro-icon.png)**:** Captions on Teams Rooms support additional languages and translation capabilities, enhancing meeting accessibility and inclusivity for non-English speaking users. Users can change the meeting spoken language directly from Teams Rooms devices and translate the spoken language as desired, allowing for real-time translation of captions. IT admins can turn on captions by default for all calls and meetings, as well as turn off the filtering of any profanity in captions and transcripts as necessary. To configure calling and meeting policies in the Teams admin center, see [Enable call captions](/en-us/microsoftteams/call-recording-transcription-captions#enable-call-captions) and [Manage live captions](/en-us/microsoftteams/meeting-transcription-captions#live-captions).
- **Updated Gallery view:** The updated Gallery View in Teams Rooms on Windows arranges all participants in consistent tile sizes, prioritizes video on the meeting stage, offers additional layout options, increases video for single and dual displays, and more. In 1:1 calls/meetings, preview video will be positioned at the bottom right, overlapping the other participant, on the primary display. This provides a unified meeting experience across both Teams Rooms and desktop. [Learn more](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-windows-e667f40e-5aab-40c1-bd68-611fe0002ba2).
- **Real time text (RTT) support:** Users can view real time text (RTT) messages on the front of room display. If users wish to send RTT messages, they'll need to join the meeting with their laptop/mobile as a companion device.

### 5.3.69.0 (3/17/2025)

Note

This update doesn't contain any new features. This update contains driver packages that are intended to enable Teams Rooms on Windows application to run on yet to be released devices. The update is optional, available as a manual update only. It isn't required if your device is running app version 5.2.115.0 [Learn more](/en-us/MicrosoftTeams/rooms/manual-update).

### 5.2.115.0 (9/26/2024)

- **Room can join Events as presenters**![](../media/mtr-pro-icon.png)**:** Teams Rooms on Windows devices can now join events in Teams (webinars and town halls) as presenters. You can present directly from the Teams Room, with features like green room access and stage control for organizers and presenters. [Learn more](/en-us/MicrosoftTeams/meeting-webinar-town-hall-feature-comparison).
- **Multiple camera view**![](../media/mtr-pro-icon.png)**:** Teams Rooms on Windows supports up to four single stream cameras that will be shown to remote meeting participants. With multiple camera view, remote meeting participants will have the ability to follow all the action in the room and manually toggle between views from the room that they want to see. [Learn more](/en-us/microsoftteams/rooms/multicamera-view).
- **Start/stop recording**![](../media/mtr-pro-icon.png)**:** Users can start or stop recording directly from Teams Rooms on Windows devices without having to join the meeting on a companion device. IT admins can allow or prevent users (including resource accounts) from recording meetings using the meeting recording policy on the Teams admin center. When users start recording a Meet now or Whiteboard session initiated from a Teams Rooms device, users must ensure that they invite themselves to the meeting so that they can access the recording file through the meeting chat on their Teams desktop or mobile app after the meeting. To ensure that IT-managed resource accounts don't become owners of the recording files, avoid assigning any Microsoft OneDrive for Business license to your resource accounts. [Learn more](/en-us/microsoftteams/tmr-meeting-recording-change#microsoft-teams-rooms-meetings).
- **Digital signage**![](../media/mtr-pro-icon.png) : Inform, connect, and engage your employees with digital signage. Users can view dynamic content and relevant information on front-of-room displays when devices aren't in use. Admins can configure tenant-wide and room-specific settings from the Teams Rooms Pro Management portal. Native integrations with selected third-party digital signage providers ([Appspace](https://docs.appspace.com/latest/devices-app/advanced-registration-microsoft-meeting-room-devices/), [XOGO](https://www.xogo.io/xogo-for-microsoft-teams-rooms)) are available, along with the use of web URLs as signage sources. [Learn more](digital-signage).
- **Enhanced cross-platform meetings using SIP join**![](../media/mtr-pro-icon.png)**:** Collaboration is seamless and intuitive across all meeting platforms, providing a native Teams Rooms experience when joining SIP-based conferencing services like Google Meet, Zoom, Cisco Webex, Amazon Chime, RingCentral, and others. Users enjoy the familiar Teams Rooms interface with access to certain third-party in-meeting controls, depending on the platform. Features include up to 1080p video quality, dual screen support, various meeting layouts, and HDMI ingest. This capability requires a SIP calling plan from a Cloud Video Interop (CVI) partner, currently available through Pexip. [Learn more](third-party-join).
- **Proximity based join experience improvements**: Proximity based join experience is updated to disable auto accepting all nudges from external or federated tenants. In addition, Teams Rooms on Windows with compatible consoles support proximity join using ultrasound, providing an alternative to Bluetooth. [Learn more](/en-us/microsoftteams/rooms/proximity-join?tabs=portal).
- **Dynamic video tile resizing based on people count**![](../media/mtr-pro-icon.png)**:** The room video tile on Teams desktop client dynamically adjusts size based on the number of people in the room. When one person is in the room, the tile matches the remote participant's size. With two or more people, the room tile expands to be four times larger. Room admins can enable or disable the people count. [Learn more](/en-us/microsoftteams/rooms/xml-config-file).
- **Microsoft Teams Rooms on Windows room preview shows Cloud IntelliFrame**![](../media/mtr-pro-icon.png)**:** The Preview video of room shows IntelliFrame when Cloud IntelliFrame is enabled for the room, to let in room participants be aware of how they appear to those online. [Learn more](/en-us/microsoftteams/devices/cloud-intelliframe).
- **Roster grouping for in-room participants through proximity join:** When joining a meeting in a Microsoft Teams Rooms with a companion device, in-room participants are grouped under the room node. Participants must join through Proximity Join with Microsoft Teams Rooms. [Learn more](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-windows-e667f40e-5aab-40c1-bd68-611fe0002ba2).
- **Breakout rooms support:** With breakout room support, Teams Rooms on Windows can be added to a breakout room as an attendee and moved in and out of the main room making it easy for breakout session coordination. [Learn more](https://support.microsoft.com/en-us/office/use-breakout-rooms-in-microsoft-teams-meetings-7de1f48a-da07-466c-a5ab-4ebace28e461).
- **Native controls for Group Framing, Active Speaker and Edge-composed IntelliFrame:** Allow users to natively toggle certain camera features provided by OEMs, including group framing, active speaker framing, and edge-composed IntelliFrame. [Learn more](https://support.microsoft.com/en-us/office/enhance-hybrid-meetings-with-microsoft-intelliframe-for-teams-rooms-97161377-b746-49dc-992f-97bbf0d590f7). 
    Note

    The camera's OEM firmware is required.

Resolved issues:

- Fixed a known issue where content and gallery were swapped, after reconnecting a screen on dual display will set up.
- Fixed a known issue where the chat panel is empty after a reboot.
- Fixed an issue where sometimes, the on-screen keyboard failed to appear on the console.
- Fixed an issue where the app would restart after the device wakes up or while using meet now.

### 5.1.28.0 (8/8/2024)

- Bug fixes for GCC-High: authentication & Teams Admin Center connectivity

### 5.1.24.0 (7/30/2024)

Introduced in this update:

- **Support for Windows 23H2** - Eligible devices will now be updated to Windows 11 23H2.
- **Text and UI resizing** - IT admins can adjust the size of the text and all other UI elements on the front-of-room display by changing the display scaling settings. Text and UI elements are resized and adjusted for all supported display resolution and scaling combinations (1080p resolution at 100-150% scaling, 4K resolution at 100-300% scaling). This capability is extended to support touch boards.
- Fixes for certain Windowing issues.
- Other bug fixes.

### 5.0.305.0 (6/3/2024)

**This is a manual update only.** This update brings the new features released in updates 5.0.111.0 and 5.0.230.0 to GCC-High customers.

### 5.0.230.0 (5/23/2024)

**This release is available for all Teams environments, however, GCC-High customers with this version installed won't see new features released from the previous update 5.0.111.0.**

This update contains essential bug fixes and performance improvements:

- Fixed an issue where WebView 2 runtime was failing to install after updating to app 5.0.111.0, blocking the new features released in that update.
- Fixed an issue where Teams Rooms app might not fill the display when the display was reconnected and the scaling settings with Console wasn't synced.
- Fixed an issue where a blank screen was displayed upon applying a custom theme.
- Fixed an issue where Screen sharing from a video teleconferencing device to a Teams Rooms for Windows device doesn't work.
- Fixed an issue where some devices failed to setup after a reset by using Zero touch Deployment with Windows Autopilot.
- The ability to change language is now enabled by default. Admins can turn off this feature by setting the Room language setting to 'False'. To learn more, see [Teams Rooms XML configuration](/en-us/microsoftteams/rooms/xml-config-file).

### 5.0.111.0 (4/24/2024)

**This release is available for all Teams environments, however, GCC-High customers with this version installed won't see any of the below mentioned new features.**

Introduced in this update:

- **New Teams on Teams Rooms** - This update brings the New Teams available on Teams Desktop to Microsoft Teams Rooms on Windows. With the new Teams app now a part of Teams Rooms on Windows, all Teams Rooms devices can now utilize available resources to optimize room experience and rendering intelligent audio and video more reliably. The New Teams app has parity of experiences, and in addition all new Teams rooms experiences are built on new Teams app.
- **Zero Touch Deployment with Windows Autopilot and Pro Management Portal**![](../media/mtr-pro-icon.png) . This update includes app support to enable the end-to-end deployment experience.
- **Ability to change language on Microsoft Teams Rooms on Windows**. With this new feature, end users can change the language of the Microsoft Teams Rooms on the Microsoft Windows app. The language choices offered are the same as those that are offered in the Microsoft Teams desktop app. The language is reverted to the default language when it restarts. To enable this, you need to set the Room language setting to 'True'. To learn more, see [Teams Rooms XML configuration](/en-us/microsoftteams/rooms/xml-config-file).
- **Skype for business deprecation**. With the release of app 4.19.57.0, we announced the end of support for Skype for Business (Server and Online) on Microsoft Teams Rooms. With this update, we have retired the XML settings for SfB and ability to sign in or support to Skype for Business meetings.
- **Meeting Chat shown by default in Gallery View for Teams Rooms on Windows**. Meeting Chat is now shown by default when joining a Teams meeting with Teams Rooms on Windows in Gallery View, making it easier to see incoming chat messages on the front of room display. Admins can configure the default chat experience for a room, and users can make in-meeting changes to show or hide the chat using the touch console.
- **Join meetings with a QR code**. Users can quickly join upcoming meetings by scanning a QR code on the Teams Rooms home screen using a mobile camera. Users will then enter the room companion mode experience on Teams mobile and the full meeting experience on Teams Rooms. Users can also scan the QR code to start an ad-hoc meeting or cast content from mobile to the front-of-room display. If the user doesn't have the Teams mobile app, they'll be directed to download it after scanning the QR code. Cross-tenant meetings are supported when the organization setting and user policies allow it. IT admins can control the feature from the XML settings or the Teams admin center. [Learn more](/en-us/microsoftteams/rooms/teams-rooms-qr-codes).
- **4K display UI scaling for Teams Rooms on Windows**. 4K-enabled displays, including front of room displays and touch boards, are natively supported on the Teams Rooms experience. Note: 4K video isn't supported.
- **Improvements to Join with an ID**. Teams meetings continue to be the default option while the option to select joining Zoom meetings with an ID, and others to come, is visually clearer.
- **Meeting ID and passcode to join on Teams Rooms on Windows**. Admins can configure and require a meeting ID and passcode to join a meeting on Teams Rooms on Windows to ensure one more level of security and privacy. This feature is available with Teams Rooms Pro license.
- **End users can switch IntelliFrame on or off using Stage roster**.
- **Intelligent Speakers for All Rooms and Devices:** With this update, users can now enjoy enhanced productivity in any meeting space, regardless of the type of mic connected to Teams Room. Support to identify who said what during meetings, providing live attributed transcriptions. This helps Microsoft Copilot and AI notes to keep track of important information. This feature is now in public preview on Microsoft Teams Rooms on Windows.
- **Integration between Report a Problem and Pro Portal Management:** Admins can configure for easier tracking, via SendFeedbackToPMP XML setting, that when a user sends feedback through Report a Problem from a room with a Microsoft Teams Pro license, each feedback creates an event in the Teams Rooms Pro Management portal.

    Important

    Note that some systems maybe missing the minimum version of the Edge WebView2 runtime. Until Edge Webview2 runtime version 110.0.1587.63 or higher is installed, these devices will be missing some features.

### 4.19.82.0 (1/31/2024)

Introduced in this update:

- **Windows Autopilot and Auto-login preview**![](../media/mtr-pro-icon.png) . This feature is now available for Pro Management Portal customers that were nominated for the preview. To sign up, reach out to your Microsoft Account team. This feature provides a seamless end to end setup experience for Microsoft Teams Rooms on Windows.
- App version information is now shown on the setup screens including One Time Passcode screen.
- Fixed a bug that causes video to freeze temporarily when using Yealink SmartVision 60.
- Other bug fixes and improvements.

### 4.19.57.0 (11/16/2023)

Introduced in this update:

- **End of support for Skype for Business server and legacy home screen UI**. Support for Skype for Business and Skype for Business + Microsoft Teams as meeting modes are no longer available, and settings that were required for this setup are removed. The legacy home screen experience is also no longer officially supported. Learn more at [End of support for connecting to Skype for Business server in Microsoft Teams Rooms on Windows](https://techcommunity.microsoft.com/t5/skype-for-business-blog/end-of-support-for-connecting-to-skype-for-business-server-in/ba-p/3915956).
- **Touch board form factor support**. Teams Rooms on Windows now support certified Touch board form factors like Surface Hub 3. Touch boards run Teams rooms touch experience on single screen. Portrait mode/Rotation on Surface Hub 3 is in preview with more optimizations to follow.
- **One time passcode (OTP) based setup**![](../media/mtr-pro-icon.png) . One-time passcode (OTP) provides a new and simplified way to set up Teams Rooms on Windows. During the first-time setup experience, the installer is presented with an option to enter a One-time passcode instead of resource account credentials, eliminating the need to share room account passwords. OTP is then used to automatically fetch the resource account credentials and sign into Teams Rooms. Teams room admins can provision the OTP from the Teams Rooms Pro Management Portal.
- **Front Row Enhancement - Active video speaker promotion**. Front Row now promotes pinned or spotlighted participants to the center stage when there's no shared content in the single and dual display mode to make the most of empty space. For single display mode, when no one is pinned, spotlighted, or sharing content, the most recent active speaker video is promoted to the center. In dual display mode, when no one is pinned, spotlighted, or sharing content, the two most recent active speaker videos are promoted to the center on each screen. If someone is sharing content, the most recent active video speaker is promoted on the right screen.
- **Support Joining a Teams Live Event as an Attendee**. To join a live event as an attendee and watch the streaming experience, follow the instructions on [Attend a live event in Microsoft Teams](https://support.microsoft.com/office/attend-a-live-event-in-microsoft-teams-a1c7b989-ebb1-4479-b750-c86c9bc98d84).
- **Teams Rooms on Windows content camera enhancements**. Teams rooms on Windows support content cameras that are [certified by Microsoft](content-camera?tabs=Windows) to share analog Whiteboard in rooms. Customers now have the choice to connect any Teams certified or any other camera as a content camera on Teams Rooms on Windows to allow ease of use.
- **Responsive calendar sizing**. The calendar size changes dynamically based on screen width and height to adapt to various front-of-room display sizes. Learn more at [Set up and manage Teams Rooms on Windows custom backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds).

Note

Microsoft can't guarantee that cloud enhancement filters work consistently on content camera not certified by Microsoft, so customers must validate the experience before rolling it out.

### 4.18.44.0 (9/20/2023)

- This update resolves a problem that prevents the room display resolution and scaling setting (configured using XML) from working on version 4.18.35.0 when sometimes Windows resets it to the default display settings.

### 4.18.35.0 (8/21/2023)

Introduced in this update:

- **Cloud IntelliFrame**![](../media/mtr-pro-icon.png) . Cloud IntelliFrame makes non-AI cameras smarter. With Cloud IntelliFrame, participants in the room appear similar to remote attendees, creating an immersive and engaging experience for everyone. Whether working from home or in the office, participants are able to see every facial expression and cue, as if they were there in person.
- **Intelligent camera support**![](../media/mtr-pro-icon.png) . IntelliFrame enables multi-stream video, face recognition of in-room participants, active speaker recognition, attributed voice-based transcription, and panoramic video on front-of-room (180-degree view) and center-of-room (360-degree view) cameras, taking Teams Rooms on Windows cameras to the next level of intelligence.
- **Front Row gallery improvement – video segmentation with a unified background**^1^![](../media/mtr-pro-icon.png) . It removes individual backgrounds, adjusts video participant's size, and applies a unified background for remote participants to make them appear as if they are in the same room. This reduces distractions and provides in-room meeting participants with better connection to remote participants in Teams meetings.
- **Spatial audio in the Front Row experience**^2^![](../media/mtr-pro-icon.png) . Spatial Audio brings next-generation audio to the Front Row experience when connected to stereo speakers. This intelligent audio technology delivers a more natural and inclusive experience for in-room participants by playing audio from channel closer to physical location of remote participants on Front row layout, making it feel like remote people are in the room with them and reducing meeting fatigue.

^1^ The feature is turned on by default. To disable the feature, use the following XML. Learn more at [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file). `<IsFrontRowUnifiedBackgroundEnabled>false</IsFrontRowUnifiedBackgroundEnabled>`

^2^ You can achieve the best spatial audio experience with [Teams-certified stereo speakers](certified-hardware?tabs=Peripherals) and by following guidance on designing a [Signature Teams Room](room-planning-guidance?tabs=emtr#signature-teams-room-1). The feature is turned off by default. To enable the feature, use the following XML. Learn more at [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file). `<IsSpatialAudioEnabled>true</IsSpatialAudioEnabled>`

### 4.17.51.0 (6/28/2023)

Introduced in this update:

- Teams Rooms user interface refresh is applied by default.
- Enhanced custom backgrounds on home screen. For more information, see [Set up and manage Teams Rooms on Windows custom backgrounds](custom-backgrounds?tabs=Enhanced). ![](../media/mtr-pro-icon.png)
- Support for SIP/H323 dialing ^1^![](../media/mtr-pro-icon.png)
- Update to Windows 11 22H2 for eligible devices, and Windows 10 22H2 for all others
- Choose your Together mode scene and select it for everyone ![](../media/mtr-pro-icon.png)
- Net Promoter Score survey at the end of some meetings. [Learn more](/en-us/microsoftteams/manage-feedback-policies-in-teams).
- Simplified Device Registration Process for Microsoft Teams Rooms Pro Management Portal. To learn more, visit [Enrolling a device into Pro Management](enroll-a-device). ![](../media/mtr-pro-icon.png)

^1^ Functionality is available through a CVI provider. Learn more at [Teams Rooms on Windows with SIP and H.323 devices](meetings-with-sip-h323-devices).

### 4.16.40.0 (3/24/2023)

Introduced in this update:

- A revitalized Teams Rooms user interface. For more information, see [Microsoft Teams Rooms home screen design refresh](mtr-home-refresh).
- Enhanced View Switcher ^1^.
- Support for Teams premium meetings protection policies (watermark, end-to-end encryption for meetings, and sensitivity labels) ^2^.
- Increased default font size for the meeting interface.
- Support for joining Blue Jeans meetings. To learn more, visit [Enable Teams Rooms devices to join third-party meetings](third-party-join).

^1^ Functionality in the layout switcher is contingent upon the type of Teams Rooms license. For more information, see [A new look for Microsoft Teams Rooms on Windows](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/a-new-look-for-microsoft-teams-rooms-on-windows/ba-p/3726040).

^2^ Meeting organizers should have a valid license to use these policies. Learn more at [Microsoft Teams Premium licensing](../teams-add-on-licensing/licensing-enhance-teams).

### 4.15.58.0 (1/10/2023)

Introduced in this update:

- In-meeting notification improvement
- Meeting chat in Gallery, Large gallery, and Together mode ^1^![](../media/mtr-pro-icon.png)
- Start whiteboard in Teams meetings
- Fit-to-frame room video roster control
- Overflow meeting support
- Join Zoom meetings by ID via Direct Guest Join. Support for joining Zoom meetings by ID has been added in this release and will be enabled in the coming weeks.
- Quality fixes for third-party meetings (Direct Guest Join)
- Fix for license information in settings showing no license when Teams isn't signed in
- A new default wallpaper (Vivid Flag) and four other new wallpapers

^1^ Administrator configuration for hiding meeting chat from all meeting layouts through XML can be found in [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file).

### 4.14.24.0 (9/2/2022)

Introduced in this update:

- Front row layout experience update
- Pin and hide room video
- Administrator configuration for turning off split gallery in dual-display Teams Rooms ^1^
- Dual-display Teams Rooms can now display up to 18 participant video streams
- Support for Microsoft Teams Rooms Pro and Microsoft Teams Rooms Basic room licenses

^1^ Administrator configuration for turning off split gallery through XML can be found in [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file).

### 4.13.132.0 (8/2/2022)

Introduced in this update:

- Join Teams meeting using meeting ID
- End-to-end encryption for one-to-one Teams calls^1^
- Noise suppression in Teams meetings^2^
- Share tray experience update
- Mute and unmute status on your room video
- Admin setting for content only layout default
- Modern authentication is on by default

^1^ Before you can turn on end-to-end encryption for calls from a Teams Rooms device, you need to configure the policy for the device's user account. You can update the user's policy from the Teams admin center or by using Teams PowerShell. For more information, see [Configure the policy for the Teams Rooms user account.](../teams-end-to-end-encryption)

^2^ Teams Rooms added support for noise suppression in release 4.12 with admin override.

Important

With this update, new Teams Rooms devices now default to using modern authentication when connecting to Microsoft Teams and Exchange Online.

We strongly recommend that you test your Teams Rooms devices prior to end of August by turning on Modern authentication for their room accounts.

This change helps prepare for the upcoming update in Exchange Online to turn off basic authentication starting October 1, 2022. For more information, see [Basic Authentication Deprecation in Exchange Online - May 2022 Update](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-may-2022/ba-p/3301866).

### 4.12.139.0 (7/14/2022)

Introduced in this update:

- Changes the version number to allow systems impacted by Windows [KB5013942](https://support.microsoft.com/topic/may-10-2022-kb5013942-os-builds-19042-1706-19043-1706-and-19044-1706-60b51119-85be-4a34-9e21-8954f6749504) to re-register the app so it can launch. There are no functional changes in this app version from 4.1.2.138.0.

Note

For more information, see "Teams Rooms app fails to start after update" in [Known issues in Teams Rooms and devices](/en-us/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues).

### 4.12.138.0 (5/26/2022)

Introduced in this update:

- Bug fix for multiple simultaneous video streams from Jabra Panacast 50 (meeting video, content camera video)
- Cross-cloud meetings can now use default conferencing audio device
- Quality and reliability fixes

### 4.12.126.0 (4/27/2022)

Introduced in this update:

- IT admins can enroll a Teams rooms device to receive public preview features through XML setting. Once enrolled, the device starts to receive preview features. All features that go to preview are announced at [Microsoft Teams Public Preview - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview)^1,2^
- IT admin can set Front of Room display resolution and scaling remotely through XML settings^2^
- IT admin can disable Microsoft noise suppression through XML setting^3^
- IT admin can override download folder cleanup on the device through registry key setting^4^
- Enabling users to join Teams meeting hosted on another cloud (that is, GCCH customer can join Teams meetings hosted on commercial cloud and vice versa)
- Teams Rooms now block launching Microsoft Edge from URLs in PowerPoint Live as an added security measure for Teams rooms with touch displays
- Meet now experience is improved to add instructions for users to invite users to the room
- Support for Windows 10 21H2 feature release for Teams rooms

^1^ Instructions for enrolling Teams Rooms in public preview can be found [here](../public-preview-doc-updates#enable-public-preview).

^2^ For information about setting Front of Room display resolution and scaling remotely through XML, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res).

^3^ At this time, only admin setting is being released. User control and enablement of the noise suppression will follow post 4.12 release in May 2022.

^4^ Device clean up instructions can be found [here](rooms-operations#collecting-logs-on-microsoft-teams-rooms).

Note

Windows 10 21H2 feature update will be updated after 7 days of installing the application or Admins can use manual update instead to install faster. Microsoft Teams Rooms application version 4.12 with these changes, will start to roll out in April 2022 and complete rollout in 2-3 weeks. The application updates are delivered through Windows store and the application is automatically installed. This is rolling out on Microsoft Teams Rooms on Windows only.

What you need to do to prepare: You might want to notify your users about this updated experience and update your training and documentation as appropriate.

### 4.11.17.0 (3/3/2022)

Introduced in this update:

- Bug fix for camera framing, which will enhance all content in camera view.

### 4.11.12.0 (1/24/2022)

Introduced in this update:

- Front Row layout (Preview) for Teams Rooms on Windows^1^
- Admin setting to set Front row layout as default
- Meet Now and call app update for Teams only, Teams default client modes^1,2^
- Switch between multiple video cameras in Teams meetings^1^
- Default video camera setting
- Azure AD Premium 1 license inclusion in Room Standard and Premium SKUs
- Azure AD conditional access policies support^3^
- Remote PTZ controls support^4^

^1^ These features are rolling out using Teams web client and will complete rollout in next couple of weeks. Read more about [Teams updates](../teams-client-update) for details.

^2^ Teams rooms on Windows running in Microsoft Teams only or Skype for Business and Microsoft Teams (default) are updated with new Meet and Call experiences, however other modes aren't impacted by this update.

^3^ This feature requires that IT admins configure Teams desktop client Remote PTZ controls app.

### Teams Rooms Web client update (December 2021)

Introduced in this update:

- Split video layout across dual Front of Room displays when content isn't being shared

### Teams Rooms Web client update (October 2021)

Introduced in this update:

- Unified roster control with Teams desktop client with structured meetings grouping, meeting options and controls for presenters/ attendees, raise hand sort order and ability to invite users from Chat or meeting invite directly from roster
- Universal bar call controls alignment with desktop client in meeting call controls, Layout button and meeting status information
- Dynamic gallery support for single and dual front of room displays
- Unified layout picker for front of room layout option consolidated
- Spotlight or Pin multiple participants in Teams meetings
- Large meetings support with presenter/ attendees controls accessible by tapping participant from roster
- Ability to lock a meeting for meetings where room is organizer, and awareness of meeting that is locked
- Presenter mode consumption support when a remote user shares content with presenter view option
- Reaction support in Teams meetings

Note

Web client updates are available to all Teams Rooms with application versions 4.10 and 4.9. Admins will be able to enroll in Teams Rooms public preview program to get sneak peek of the web client features soon.

### 4.10.10.0 (10/1/2021)

Introduced in this update:

- Room remote allows users to control basic functionality of the room using Teams on their mobile \*
- Content camera support for BLE button for sharing into meeting
- Chat bubbles provide notifications for in meeting chat to bring attention to what's being said using meeting chat \*
- Large gallery and Together mode support is now available in GCC High

Note

Deprecated 19H1 support. Min OS version supported by 4.10 is 19H2.

\*These features are rolled out using Teams service and will work with all application versions greater than 4.9.

To join the scheduled meeting both from Teams Mobile app and Teams Rooms on Windows find the room account in roster on the Teams Mobile app and press "Control this room" menu and you can control Call controls from the app.

### 4.9.12.0 (7/28/2021)

Introduced in this update:

- Microsoft Teams only mode is now available in application settings, so you don't need to set up a Skype for Business account anymore. In this mode, devices signed in to Teams only mode join Skype for Business meetings as a guest.
- Fix for HDMI audio causing lower call volume. HDMI audio feature is automatically enabled for all devices with application build 4.9.12.0.

Note

With Skype for Business reaching end of life it's recommended to update to Teams only mode.

### 4.8.31.0 (05/12/2021)

Introduced in this update:

- Windows 10 20H2 support

Note

Crestron UC-Engine (BIOS version date containing "KYSKLi") Teams Rooms have compatibility issues and updated drivers will be provided by system OEMs in the near future. Windows 10 20H2 won't be offered to these devices. For more information about Windows version support, see [Windows release support](rooms-lifecycle-support#windows-release-support).

### 4.8.25.0 (04/22/2021)

Introduced in this update:

- Fix for an issue where room information on Teams Rooms consoles doesn't show up for room accounts that are hidden from the global address list (GAL)

Note

GCCH customers can download the upgrade package from [Manually update a Microsoft Teams Rooms device](manual-update)

### 4.8.19.0 (04/06/2021)

Introduced in this update:

- Government Community Cloud High (GCCH) support for Teams Rooms. GCCH customers with existing Teams Rooms devices can download version 4.8.19.0 from [Manually update a Microsoft Teams Rooms device](manual-update)
- Join Zoom meetings with better video quality (720p support) and receive the video gallery of participants
- Skype for Business sign-in failure banner removed for Teams default mode. This change supports organizations removing Skype for Business infrastructure
- Teams meetings join link parsing now handles Microsoft Defender Advanced Threat Protection Safe Links to allow joining external Teams seamlessly
- Fix for shared content scaling issue in Skype for Business meetings when the sharer's PC has a custom DPI set in Windows
- Quality and reliability fixes

### 4.7.19.0 (02/03/2021)

Introduced in this update:

- Quality and reliability fixes

### 4.7.15.0 (12/11/2020)

Introduced in this update:

- Share HDMI audio to meeting participants in Teams meeting
- Prevent unmuting based on audio permissions when Teams Rooms joins as attendee. For more information, see [Manage attendee audio permissions in Teams Meetings](https://support.microsoft.com/office/manage-attendee-audio-permissions-in-teams-meetings-f9db15e1-f46f-46da-95c6-34f9f39e671a).
- Spotlight someone's video from Teams Rooms console and consume spotlighted video on room displays

### 4.6.23.0 (10/19/2020)

Introduced in this update:

- Fix for white half-screen when invoking On-screen keyboard in Teams meeting

### 4.6.20.0 (09/30/2020)

Introduced in this update:

- See more videos with 3x3 video gallery on front of room displays
- Start local live closed captions
- Join Zoom meetings from Teams Rooms with Direct Guest Join (Preview)

Note

3x3 video gallery and local live closed captions are delivered through the Microsoft Teams service. These features are available to all Teams Rooms devices with application version 4.5.37.0 and above.

### 4.5.37.0 (08/14/2020)

Introduced in this update:

- Coordinated Meetings between Microsoft Teams and Surface Hub 2S
- Fix for Skype For Business sign-in failure when [Windows 10 update KB4565351](https://support.microsoft.com/help/4565351/windows-10-update-kb4565351) or [Windows 10 update KB4571709](https://support.microsoft.com/help/4571709/windows-10-update-kb4571709) is installed

### 4.5.35.0 (07/23/2020)

Introduced in this update:

- Join Cisco Webex meetings from Teams Rooms with Direct Guest Join
- Teams Admin Center enablement and auto-enrollment
- Windows 10 1909 release support
- Switch to video gallery layout even when content is present
- Virtual raise hands support for attendee and controls for presenter
- Adjustable default volume setting for conferencing and default speaker
- Search and call federated users (tenant) from Teams Room

Important

Version 4.5 is last release to support Windows 10 version 1803; future releases won't be offered to systems on Windows 10 version 1803. For more information about Windows version support, see [Windows release support](rooms-lifecycle-support#windows-release-support).

### 4.4.63.0 (06/25/2020)

Introduced in this update:

- Quality and reliability fixes
- Fix for "application won't launch after update to 4.4.41.0" issue

### 4.4.41.0 (05/06/2020)

Introduced in this update:

- Reliability fixes for application start in Windows 10 Kiosk

### 4.4.25.0 (03/31/2020)

Introduced in this update:

- Modern authentication support for Exchange and Skype for Business
- Support for dynamic emergency calling for Teams (Service components required and released using Teams client rings)
- Ability to disable duplicate content out of meeting for dual displays rooms using XML
- Application splash screen
- Open Source Software (OSS) notices in device settings

### 4.3.42.0 (03/02/2020)

Introduced in this update:

- Policy updates for "Windows Updates for Business"
- Fix for device events reporting showing error in Azure Monitor

### 4.3.33.0 (1/10/2020)

Introduced in this update:

- A fix for a Window resizing/flickering issue seen in certain configurations
- Calendar processing for third-party meetings removed

### 4.3.23.0 (12/13/2019)

Introduced in this update:

- Auto-answer proximity-based calls and admin setting to control the feature
- Device Admin Settings UI refresh with addition of device configuration under About tab
- Room control back to main screen
- Meeting Room SKU available in GCC
- Content camera support for Surface Pro-based system (Minimum required app build: 4.2.4.0)

### 4.2.4.0 (10/07/2019)

Introduced in this update:

- Windows 10 1903 support. Windows 10 1903 update is offered in a few days after app update
- Fixes for On-screen keyboard not showing up reliably

### 4.1.22.0 (08/15/2019)

Introduced in this update:

- A new content camera feature that enables users to intelligently include a traditional whiteboard into their Teams meeting
- Additional improvements to the Console UI to reduce clutter and moved **Settings** into a new side bar that is accessed via More on the console
- Disabled share tray button if local content cable isn't connected or a content camera isn't connected
- Fixed an issue with the touch keyboard where it failed to appear the first time only after a system restart
- Quality and reliability fixes

### 4.0.105.0 (07/10/2019)

Introduced in this update:

- Skype Room System store app rebrand to "Microsoft Teams Rooms"
- Microsoft Teams Rooms console user interface realigned to Microsoft Teams
- Theme update: only keep custom background image on front of room displays, while making console background a neutral color to ensure console UI controls meet color contrast—accessibility requirements
- Universal bar for in-meeting call controls for Teams calls/ meetings to provide consistent experience with Microsoft Teams PC/ Web/ Mobile clients^1^
- Call quality feedback rating after Teams calls/ meetings^1^
- Receive/render Microsoft Whiteboard on Microsoft Teams Rooms front of room display when shared from PC/ Web/ Mobile Teams client^1^^2^
- Removed support for Windows 10 Version 1809 upgrades due to compatibility issues with Microsoft Teams Rooms client. Windows 10 Version 19H1 support will be added in future releases

^1^ Microsoft Teams service rollout using Teams rings. This feature might be available earlier or later than 4.0.105.0 client update.

^2^ Requires IT admins to turn on Microsoft Whiteboard. Also, if you have a touch-enabled front of room display, you must calibrate multiple touch displays using Windows settings with device administrator sign-in to start using Microsoft Whiteboard for collaboration from a room display shared into a Teams meeting.

### 4.0.85.0 (04/8/2019)

Introduced in this update:

- Fixes an issue with the "give feedback" feature.
- Optimizations in preparation for the forthcoming Microsoft Teams Rooms device upgrade to Windows 10 Version 1809.

### 4.0.78.0 (03/14/2019)

Introduced in this update:

- Fix for "hang at app start-up" bug that affected devices on legacy Windows 10 RS2 build.

### 4.0.76.0 (03/04/2019)

Introduced in this update:

- DTMF keypad for Microsoft Teams P2P meetings and PSTN calls. To make Microsoft Teams your default calling client, admins must set IsTeamsDefaultClient to true.
- Pin a remote participant's incoming video to full screen on front of room display. Use "Pin" command from participant roster on the console.
- Improvements to Lobby notifications with addition of Front of Room notification.
- Front of Room display casting icon removed when Bluetooth beacon isn't enabled on Microsoft Teams Rooms device.
- Fix for volume control issue in Teams meetings.

### 4.0.64.0 (12/14/2018)

Introduced in this update:

- Display content on both Front of Room (FoR) displays on dual screen room systems.
- Theming and Front of Room user interface improvements.
- TLS 1.2 client-side support. For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).

### 4.0.51.0 (11/17/2018)

Introduced in this update:

- Dual display (Front of Room) support for Teams Meetings.

### 4.0.31.0 (10/16/2018)

Introduced in this update:

- Quality and reliability fixes.

### 4.0.27.0 (10/1/2018)

Introduced in this update:

- Code changes necessary to prepare the Microsoft Teams Rooms app for later Windows 10 Version 1803 upgrade.
- Fix formatting issue with localized EULAs (specifically Norwegian) which prevents advancing beyond EULA OOBE setup window.
- Code changes required to make Microsoft Teams Rooms application run on legacy Lync Room Systems. See more [here](lrs-migration).

### 4.0.19.0 (8/31/2018)

Introduced in this update:

- Hotfix for Crestron application not launching which would normally be accessible when the app button on a Crestron SR device is pressed. Microsoft Teams Rooms app restart required after installation of 4.0.19.0.

### 4.0.18.0 (08/27/2018)

Introduced in this update:

- "Report a Problem" feature improvements in Teams mode (equivalent of "Give Feedback" in Skype for Business mode).
- Enable ability to fall back from Teams to Skype for Business mode for SIP calls.
- Accessibility improvements (Narrator, Magnifier).
- Automatically restart app when required after XML provisioning changes are applied.
- Miscellaneous fixes.

### 4.0.8.0 (07/06/2018)

Introduced in this update:

- This update enables both Skype for Business *and* Teams meetings support on Room Systems devices. Teams is turned off by default once the update is applied. Admins can enable Teams locally in device settings or via a remote xml push.

### 3.1.115.0 (06/18/2018)

Introduced in this update:

- Fix to address error observed on some systems during app launch.

### 3.1.113.0 (06/13/2018)

Introduced in this update:

- Changes enabling Microsoft to more flexibly manage Windows Updates.
- No change to end-user experience.

### 3.1.112.0 (06/05/2018)

Introduced in this update:

- Fix to address console responsiveness issues observed on Surface Pro 2017-based devices connected to two front-of-room displays and video ingest
- Automated check to ensure that system is running latest provisioning script

### 3.1.104.0 (04/16/2018)

Introduced in this update:

- Fix to improve OSK (on-screen keyboard) behavior in Window 10 Version 1709-based systems
- Improvements to prepare for future operating system updates

### 3.1.100.0 (03/16/2018)

Introduced in this update:

- Application updated to improve telemetry

### 3.1.99.0 (03/14/2018)

Introduced in this update:

- Fixes an issue where intermittent meeting join issues may occur
- Fixes an issue known to result in a device "hang" experience

### 3.1.98.0 (3/8/2018)

Introduced in this update:

- Bug/Crash fixes to improve stability
- Support for variable-sized console
- Peripheral audio processing offloading (additional media allow list)
- Optimizations that enable IT Pros to build do-it-yourself images with Windows 10 Version 1709 January Update and later.

### 3.0.16.0 (11/27/2017)

Introduced in this update:

- Fixes an issue with the "Give Feedback" feature.

### 3.0.15.0 (10/3/2017)

Introduced in this update:

- Support for [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) dock hardware
- Support for the [Logitech Brio](https://www.logitech.com/product/brio)
- Resolves an issue where displays (console and front-of-room) fail to enter sleep mode when there's no activity in the room

### 3.0.12.0 (9/1/2017)

Introduced in this update:

- Runs on a Surface Pro (2017) tablet
- Supports Windows 10 Enterprise Creator's Update (English language, build 1703)
- Support for Crestron SR dock hardware.
- OEM Support for Environment Controls (Crestron)

The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Microsoft Teams Rooms release 3.0.12.0 (update 3).

### 3.0.8.0 (8/4/2017)

Introduced in this update:

- Resolves issues observed when searching for federated users through the Participants search field. Previous to this fix, search results for external federated users might not have resolved correctly and instead have returned incorrect results.

### 3.0.6.0 (7/7/2017)

Introduced in this update:

- Dual-Screen support (for legacy system parity)
- Themes (built-in themes and the ability to set custom theme)
- Ability to Give Feedback for public builds
- Improved Telemetry around meeting join reliability
- Improved OMS reporting
- Ability for IT Admin to configure devices remotely

### 2.0.2.0 (03/15/2017)

Introduced in this update:

- In-app user selection of meeting room audio and video USB devices
- Integrated room console status reporting for customers using Microsoft Operations Management Suite, now Azure Monitor

### Release to Market (12/7/2016)

**Feature(s):**

**Built for Skype for Business**

- One-touch join of Skype Meetings
- Skype Meeting experience optimized for rooms with screen-filling HD video and HD wide-band audio
- All participants can connect to the Skype Meeting using their device of choice from wherever they may be located
- Invite people from your directory where you can instantly see their availability or via a phone call
- Supports Skype for Business PSTN Conferencing and PSTN Calling to replace the stand-alone conference phone in your room

**Transform Any Meeting Room**

- Dedicated Skype Meeting app optimized for center of table touch controller and large front of room display
- Reuse existing investments in your front of room display or projectors
- Works in all types of meeting spaces from huddle spaces to large conference rooms
- Certified Skype for Business audio and video devices are available for various room sizes
- Built-in wired ingest to project desktop sharing to the room and to the Skype Meeting

**Easy to Deploy, Simple to Manage**

- Always-on appliance that automatically wakes up the displays when it detects people in the room
- Simple deployment and updating of the UWP (Universal Windows Platform) Skype Meeting App
- Windows AppLocker locks down the device to the Skype Meeting app
- Monitored and managed as a Windows 10 Enterprise device via Intune and Configuration Manager (MDM)
- Enterprise-grade reliability
- Low training effort of end-users due to familiar Skype user interface
- Runs on Surface Pro 4 tablet

# [Teams Rooms on Android](#tab/Android)
## Teams Rooms on Android version history

| Release | Release date |
| --- | --- |
| 1449/1.0.96.2026264504 | October 2026 |
| 1449/1.0.96.2026261804 | September 2026 |
| 1449/1.0.96.2026249711 | September 2026 |
| 1449/1.0.96.2026144512 | August 2026 |
| 1449/1.0.96.2026142702 | July 2026 |
| 1449/1.0.96.2026129709 | June 2026 |
| 1449/1.0.96.2026100103 | May 2026 |
| 1449/1.0.96.2026087210 | April 2026 |
| 1449/1.0.96.2026048906 | April 2026 |
| 1449/1.0.96.2025421910 | February 2026 |
| 1449/1.0.96.2025341701 | December 2025 |
| 1449/1.0.96.2025328903 | November 2025 |

## Teams Rooms on Android feature introduction and issue resolution

Note

There can be a delay between when features are released by Microsoft and when they become available on a device make and model. If an update isn't available on your device, check with your device manufacturer for information on when it might become available.

Features with ![](../media/mtr-pro-icon.png) are only available with Teams Rooms Pro license.

### 1449/1.0.96.2026264504 (October 2026)

Resolved Issues:

- Resolved an issue where console is stuck on the connecting screen when joining a meeting
- Resolved an issue where an incoming call fails to show up on the console.

### 1449/1.0.96.2026261804 (September 2026)

Introduced in this update:

- **Google Meet for Direct Guest Join:** Organizations now have expanded meeting interoperability with two-way Direct Guest Join (DGJ) between Google Meet and Microsoft Teams meetings. User can join with one block through the calendar or by meeting ID. [Learn More](/en-us/microsoftteams/rooms/third-party-join).

Resolved Issues:

- Resolved an issue where the secondary display may appear blank during a meeting on dual-screen setups.
- Resolved an issue where mute status may become out of sync.

### 1449/1.0.96.2026249711 (September 2026)

Introduced in this update:

- **Interpreter agent support during meetings**![](../media/mtr-pro-icon.png)**:** The Interpreter agent acts as a translator in Teams meetings, allowing participants to listen to the meeting in their chosen language with real-time translation so speaking different languages isn’t a barrier to effective understanding and collaboration. 20 hours of interpretation included per room account per month with a Teams Rooms Pro license. Access beyond included hours is subject to available capacity. This is controlled using the [Teams Meeting Policy](/en-us/microsoftteams/interpreter-agent-teams#manage-interpreter-using-powershell).
- **Modernized Gallery view:** The updated Gallery view in Teams Rooms on Android prioritizes video on the meeting stage, arranges participants in consistent aspect ratios, and minimizes movement of participant tiles on stage. Users can hide the room self-preview video and choose to see audio and video participants equally on stage, instead of prioritizing video participants. Admins can choose the default behavior using local device settings and the Pro Management portal.
- **Chat for organizers and presenters in town hall**![](../media/mtr-pro-icon.png)**:** When a Teams Rooms on Android device is an organizer, co-organizer or presenter in a town hall, you have access to a private chat for event management known as the Event Group. You can also switch to a separate chat with attendees enabling smooth event experiences for all.
- **SIP/H.323 dialing**![](../media/mtr-pro-icon.png)**:** Make SIP or H.323 video calls if configured through a supported partner. [Learn more](/en-us/microsoftteams/rooms/meetings-with-sip-h323-devices).

Resolved issues:

- Resolved an issue where certain devices may still use EWS (Exchange Web Services) for calendaring. Ensure devices are updated to this build or newer prior to disabling EWS within an environment. Also see [Microsoft Learn | Deprecation of Exchange Web Services in Exchange Online](/en-us/exchange/clients-and-mobile-in-exchange-online/deprecation-of-ews-exchange-online).
- Resolved an issue where certain devices may freeze or crash during HDMI presentation.
- Resolved an issue where meeting transcription panel was shown despite transcription policy being set to disabled.
- Resolved an issue where console meeting join QR code was incorrectly sized.
- Resolved an issue where console was slow to join a meeting when QR code join was used.
- Resolved an issue where certain devices appeared as unhealthy in the Pro Management Portal after entering “sleep mode”.
- Resolved an issue where certain devices with paired consoles were unable to participate in end-to-end encrypted meetings.
- Resolved an issue where certain devices sent low bitrate video in certain meeting scenarios.

### 1449/1.0.96.2026144512 (August 2026)

Resolved issues:

- Resolved an issue where HDMI content sharing could fail on certain devices after updating to Teams Rooms on Android version 1449/1.0.96.2026142702.
- Resolved an issue where certain devices running could be unable to share HDMI presentations directly from the touch console home screen.
- Resolved an issue that could cause devices to enter sleep mode during a Town hall.

### 1449/1.0.96.2026142702 (July 2026)

Resolved issues:

- Resolved an issue affecting the reliability of device log collection from the Teams admin center.
- Improved diagnostic logging to optimize log file management.
- Resolved an issue that could cause the display to turn off during a Town hall or webinar.
- Resolved a crash that could occur when ending a call.

### 1449/1.0.96.2026129709 (June 2026)

Introduced in this update:

- **Front-of-room view control for Webinar and Structured Meetings in Teams Rooms on Android**![](../media/mtr-pro-icon.png)**:** When a Teams Rooms on Android device is invited as a presenter in a Webinar or Structured Meeting, the front-of-room display defaults to the attendee view. Presenters always have full control from the console, including green room and off-stage management, and can switch the front-of-room display to presenter view without impacting attendees. [Learn more](https://support.microsoft.com/office/host-or-attend-an-event-from-a-microsoft-teams-room-mtr-d7ff15e0-6516-4ebc-ae03-a2bdf58a4478).
- **Enhanced cross-platform join via SIP**![](../media/mtr-pro-icon.png)**:** Join third-party meetings via SIP instead of Direct Guest Join, delivering expanded cross-platform interoperability. This capability ensures users can connect to external meeting services directly from Teams Rooms, maintaining a consistent and reliable meeting experience across diverse environments. [Learn more](/en-us/MicrosoftTeams/rooms/third-party-join?tabs=MTRW)
- **Meeting stage improvements:** Multiple enhancements including allowing room users to change remote participants videos from fill frame to fit to frame and vice versa from the contact card, updating the look and feel of the contact card, centering the participants shown on the side tray and bottom tray in Gallery view, showing up to 3 participant avatars in the overflow tile, and other UI polishes.
- **Open chat panel by default on Gallery view:** Chat panel now opens by default with Gallery and Large Gallery. Users can open or close the chat panel with one touch using the chat button which has been moved from the view switcher to the meeting utility bar for ease of discoverability. IT admins can change the chat panel default behavior using a local device setting.
- **Focus on content view optimization:** Content is enlarged and the right pane is closed by default on Focus on content view for an improved content viewing experience. Users can open the chat, notes, or transcript pane on demand.
- **One touch speaker on/off:** Quickly mute or unmute room speakers by tapping the speaker icon.
- **Removal of dial pad in meetings:** Dial pad is removed from the more options in-meeting to align with Teams desktop and Teams Rooms on Windows.
- **Location inference for PSTN users for India deployment:** Location inference enables automatic determination of user location during PSTN calls to support compliance with local telecommunication regulations. This ensures calls are routed and handled in accordance with India-specific requirements. [Learn more](/en-us/MicrosoftTeams/location-based-routing-configure-network-settings-india)
- **Together Mode deprecation:** Together Mode view in Teams meetings is deprecated for all Teams clients. [Learn more](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/goodbye-together-mode-hello-simplified-meeting-layouts-in-microsoft-teams/4519312)
- **Control for Auto-Exit Meetings:** Teams Rooms devices automatically exit a Teams Meeting if the device is the only meeting participant for more than 5 minutes outside of the scheduled meeting time. This is enabled by default but can be disabled within the Pro Management Portal settings on an individual device basis.
- Management of settings related to features in this release and future releases is only available within the Teams Rooms Pro management portal ([Learn more](/en-us/MicrosoftTeams/rooms/pro-portal-settings)). To enable this functionality, ensure devices are running Teams Admin Agent 1.0.0.202606082157 or greater.

Resolved issue:

- Fixed an issue where duplicate video feeds appeared in Large Gallery view.

### 1449/1.0.96.2026100103 (May 2026)

Resolved issue:

- Resolved an issue which caused Teams Rooms on Android devices not being able to join Teams webinar. Webinar join experience is now restored.

### 1449/1.0.96.2026087210 (April 2026)

Introduced in this update:

- **Digital signage**![](../media/mtr-pro-icon.png)**:** As with Teams Rooms on Windows, IT admins can now set up Teams Rooms on Android to show dynamic signage content on front-of-room displays when devices are not in use for meetings or presentation. Configuration is available for tenant-wide and room-specific settings via the Teams Rooms Pro Management portal. Native integrations with selected third-party digital signage providers ([Appspace](https://www.appspace.com/microsoft-teams-rooms/), [XOGO](https://xogo.io/xogo-for-microsoft-teams-rooms)) are supported, along with the use of web URLs as signage source. For more information, including known limitations on how digital signage and device sleep mode interacts in this release. [Learn more](/en-us/microsoftteams/rooms/digital-signage).
- **Ad-hoc room reservation**![](../media/mtr-pro-icon.png)**:** Users can quickly book a meeting room for immediate use, helping to avoid scheduling conflicts and ensure uninterrupted spontaneous meetings. A “Reserve” button appears on the calendar when the room is available. IT admins can control this feature using the “Allow ad hoc room reservation” device setting on the Teams admin center. [Learn more](/en-us/MicrosoftTeams/rooms/mtr-home-refresh#ad-hoc-room-reservation).
- **Live transcription**![](../media/mtr-pro-icon.png)**:** View and control live transcription during a meeting from a Teams Rooms on Android device. The real-time transcript includes speaker names and timestamps. You can adjust settings such as spoken language, translated language, and whether both original and translated transcripts are displayed side by side on the front of room display.

Resolved issues:

- Presenter support for Teams Town Hall and Front-of-room view control for Teams Town Hall are available with direct console connection.
- Resolved an issue which caused low video quality in small video frames.

### 1449/1.0.96.2026048906 (April 2026)

Resolved issue:

- Resolved an issue that caused content sharing to intermittently stop in meetings when Teams Rooms on Android devices were configured with dual displays.

### 1449/1.0.96.2025421910 (February 2026)

Introduced in this update:

- **Presenter support for Teams Town Hall**![](../media/mtr-pro-icon.png)**:** Teams Rooms on Android devices can be invited to Town Hall as a presenter and participate fully in the event.
- **Front-of-room view control for Teams Town Hall**![](../media/mtr-pro-icon.png)**:** When a Teams Rooms on Android is invited as a meeting presenter, the front-of-room display defaults to the attendee view. Presenters always have full control from the console, including green room and off-stage management, and can switch the front-of-room display to presenter view without impacting attendees.
- **Start and stop recording and transcription**![](../media/mtr-pro-icon.png)**:** During a Teams meeting, you can start, stop, and restart recording and transcription from a Teams Rooms on Android device. Spoken language for the meeting can also be changed. IT admins can allow or prevent users (including resource accounts) from recording meetings using the meeting recording policy on the Teams admin center. When users start recording and transcription at a Meet now or Whiteboard session initiated from a Teams Rooms device, users must ensure that they invite themselves to the meeting so that they can access the recording and transcription files through the meeting chat on their Teams desktop or mobile app after the meeting. To ensure that IT-managed resource accounts don't become owners of the recording and transcription files, avoid assigning any Microsoft OneDrive for Business license to your resource accounts. Learn more about [recording](/en-us/microsoftteams/tmr-meeting-recording-change#microsoft-teams-rooms-meetings) and [transcription](/en-us/microsoftteams/meeting-transcription-captions#transcription).
- The video on/off status icon for other meeting participants has been removed from the participant list. To check who has video enabled, users can refer to the front-of-room display.

Resolved issues:

- Resolved an issue which caused meeting reactions to appear twice on front of room displays.
- Resolved an issue which added latency intermittently for hardware mute controls.
- Resolved an issue which caused calendar connection to fall back to the retiring EWS API.

    Important

    With the upcoming deprecation of Exchange Web Services (EWS) in Exchange Online, you must update your Teams Rooms on Android devices to this app version or higher to ensure your room calendar will continue to work. Learn more at [Microsoft Learn | Deprecation of Exchange Web Services in Exchange Online](/en-us/exchange/clients-and-mobile-in-exchange-online/deprecation-of-ews-exchange-online), [Microsoft Tech Community | Retirement of Exchange Web Services in Exchange Online](https://techcommunity.microsoft.com/blog/exchange/retirement-of-exchange-web-services-in-exchange-online/3924440) and [The Way to Control EWS Usage in Exchange Online is Changing | Microsoft Community Hub](https://techcommunity.microsoft.com/blog/Exchange/the-way-to-control-ews-usage-in-exchange-online-is-changing/4383083?WT.mc_id=M365-MVP-9501).

### 1449/1.0.96.2025341701 (December 2025)

Resolved issues:

- Fixed an issue on some devices where mute controls did not function correctly.
- Fixed an issue that occasionally caused storage problems impacting update deployment.

### 1449/1.0.96.2025328903 (November 2025)

Resolved issues:

- Resolved an issue where the background was removed and replaced with a purple background after a device reboot or firmware update.
- Resolved an issue where the touch console shows a blank screen.
- Resolved an issue where the front-of-room display dims and powers off while a call/meeting is in progress.
- Resolved an issue where the join by ID icon may not appear on the home screen.
- Resolved where devices were unable to rejoin cross cloud meetings after a disconnect.

### 1449/1.0.96.2025325609 (October 2025)

Introduced in this update:

- **Support for Facilitator agent in scheduled Teams meetings**![](../media/mtr-pro-icon.png)**:** When joining a scheduled Teams meeting on Microsoft Teams Rooms, participants in the room can experience all of the benefits of having Facilitator, including AI-generated notes, agenda and time tracking, and AI answers from the web which can be seen on the front-of-room display. After the meeting, participants can access the notes from Teams desktop and web app.
- **Cloud IntelliFrame**![](../media/mtr-pro-icon.png)**:** Cloud IntelliFrame, the AI-powered video enhancement feature for Microsoft Teams Rooms, transforms the traditional wide-angle room view into a gallery of individual video tiles to enhance participant visibility. Admins can manage it through console settings. This feature is now available on Teams Rooms for Android with a Teams Rooms Pro license.
- **Dynamic video tile resizing based on people count:** The room video tile on the Teams desktop client meeting experience dynamically adjusts size based on the number of people in the room. When one person is in the room, the tile matches the typical remote participant's size. With two or more people in the room's camera frame, the room tile expands to be four times larger.
- **Manage voice recognition for rooms via device settings:** To simplify management and reduce configuration friction for voice recognition in Microsoft Teams Rooms, we’re introducing new admin-facing settings on Android Teams Rooms devices. These settings replace PowerShell-based configuration with a more intuitive UI, offering clearer visibility into recognition status across rooms.
- **Town hall attendee support**![](../media/mtr-pro-icon.png)**:** Teams Rooms on Android devices can now join Teams town hall as an attendee. [Learn more](/en-us/microsoftteams/plan-town-halls).
- **Translated captions**![](../media/mtr-pro-icon.png)**:** Captions on Teams Rooms on Android support additional languages and translation capabilities, enhancing meeting accessibility and inclusivity for non-English speaking users. Users can change the meeting spoken language directly from Teams Rooms devices and translate the spoken language as desired, allowing for real-time translation of captions. IT admins can turn on captions by default for all calls and meetings, as well as turn off the filtering of any profanity in captions as necessary. To configure calling and meeting policies in the Teams admin center, see [Enable call captions](/en-us/microsoftteams/call-recording-transcription-captions#enable-call-captions) and [Manage live captions](/en-us/microsoftteams/meeting-transcription-captions#live-captions).
- **Cross cloud meeting join:** Teams Rooms on Android devices can now join meetings hosted in another Teams cloud. For example, devices connected to the Commercial instance of Teams can join meetings hosted in GCC-High, and other cross-cloud combinations are also supported.
- **Removal of mic button**: The mic on/off button is removed from the call/meeting connecting screen. Users can mute/unmute the room audio once the room has joined the call/meeting.

Note

**Cross cloud meeting join** feature is available on devices without a console or those with a directly connected console.

### 1449/1.0.96.2025223801 (September 2025)

Resolved issues:

- Resolved an issue where the automatic pairing between the console and room device malfunctioned on some devices.
- Resolved an issue where Government cloud customers were asked to sign in again on device after a remote sign in to the device.
- Resolved an issue where the calendar on the device sometimes failed to refresh.
- General improvements to address unexpected sign outs.

### 1449/1.0.96.2025208203 (July 2025)

Resolved issues:

- Improvements to resiliency when either Front of Room device or console drops from a Teams meeting.
- Addressed an issue where the app was occasionally dropping from meetings due to a Teams process crash.
- Improvements to console performance during XL meetings.
- Addressed an issue where console could take longer to join a meeting.
- Addressed an issue where volume changes don’t reflect on the Front of Room device or the updates are slower.

### 1449/1.0.96.2025205603 (July 2025)

Resolved issues:

- Resolved an issue where the Microsoft Teams Rooms application doesn't start automatically after a reboot.
- Resolved an issue where two parallel sign-ins were canceled by each other.
- Resolved an issue where device enrollment was taking longer than expected.
- Resolved an issue which was causing home screen UI performance to be sluggish.

### 1449/1.0.96.2025203502 (June 2025)

Introduced in this update:

- **Real time text (RTT) support:** Users can view real time text (RTT) messages on the front of room display. If users wish to send RTT messages, they'll need to join the meeting with their laptop/mobile as a companion device.

Resolved issues:

- Resolved an issue where explicit consent for Microsoft Copilot wasn't being displayed on Teams Rooms Android.
- Resolved an issue where layout options weren't being shown when content is being shared.
- Resolved an issue where dual display mode was being set automatically.
- Resolved crashes leading to meeting drops in some situations.

### 1449/1.0.96.2025126202 (May 2025)

Introduced in this update:

- **Preview of Facilitator agent note taking in Rooms for offline/ad hoc discussions.** Power your ad-hoc in-person discussions by inviting the Facilitator agent in your Teams Room. Learn more here: [Facilitator in Teams Rooms - Microsoft Teams | Microsoft Learn](/en-us/microsoftteams/rooms/facilitator-teams-rooms)
- **New Microsoft-managed policy to help further secure your tenants against potential threats to accounts using device code flow (DCF) authentication.**
- **Disabled auto accept for external tenant nudges.** Teams Rooms on Android will now also no longer automatically accept any Proximity joins using an external account for security reasons.
- **Local PTZ controls:** If the camera isn't currently auto-framing the room, in-room users can control the Pan-Tilt-Zoom (PTZ) of the active camera to keep the focus where they want it.
- **Speaker recognition and attribution.** Microsoft Teams Rooms on Android will soon support Intelligent Speakers, providing advanced speaker recognition to clearly identify who said what in meeting transcripts. This feature significantly enhances Microsoft 365 Copilot and AI Recap, enabling accurate, personalized summaries and actionable insights from your meetings. This capability seamlessly integrates with both intelligent speakers and your existing room speakers via the cloud. Each participant is securely recognized through a unique voice profile, ensuring precise attribution in live transcripts and maximizing the effectiveness of your Teams meeting experience.
- **Proximity join performance and reliability improvements.** These enhancements are for standalone consoles where calls used to drop sometimes and then rejoin automatically a few seconds later.
- **Call Join performance improvements.** Multiple improvements to call join performance in standalone consoles. These improvements should significantly reduce the time it takes for the console to join a meeting, especially the ones with more than 50 participants.

### 1449/1.0.96.2025031102 (March 2025)

Resolved issues:

- Fixed an issue where app wasn't functional after pressing back key on paired remote with some Logi devices.
- Resolved an issue where local HDMI ingest sharing indicator status wasn't synced between display and console.
- Fixed an issue where Custom background resets to default.
- Fixed a bug that prevented Teams Rooms Android device from joining a meeting when invited from QR code or Bluetooth proximity.

### 1449/1.0.96.2025020302 (February 2025)

Resolved issues:

- Fixed an issue where pairing loss affected functionality of certain Teams Rooms on Android systems.
- Resolved an issue where the meeting UI (user interface) was misaligned after pressing the back button.
- UI fixes and improvements for dual screen setups.
- Resolved an issue where users weren't able to file feedback using “Report a problem”.

### 1449/1.0.96.2025010301 (January 2025)

Introduced in this update:

- **Required updates coming to the session flows:** Starting in June 2025, Teams app clients more than 5 months old will no longer work.

Resolved issues:

- Resolved an issue where touch screen controls were shown on the Front of Room display after the feature is disabled in settings.
- Resolved an issue where some Logi Rally Bar systems failed to swap screens [PM3.1] after restart.
- Fixed an issue where some backgrounds weren't being applied when set on Teams admin center.
- Resolved an issue where chat bubbles weren't being displayed on some Front of room displays.
- Resolved an issue where chats weren't being refreshed on the display.
- Resolved an issue where content sharing in meetings would stop in a dual display setup.
- Resolved an issue where some meeting participants might be displayed as **Unverified** even when they shouldn't be.

### 1449/1.0.96.2024110701 (November 2024)

Introduced in this update:

- **Dual display mode and swap screens admin control**![](../media/mtr-pro-icon.png) . IT admins can deliberately configure Teams Rooms on Android devices to run in dual display mode. Admins can also switch the screens of dual display rooms using the swap screens setting, easily correcting front-of-room displays that were set up inverted. Both controls are accessible from the device settings and Teams Admin Center.

Note

If you're deploying Teams Rooms on Android devices with dual displays, be aware that dual display mode must be explicitly enabled in the configuration profile. By default, the dual display setting is disabled, which means that using an existing configuration profile (designed for single-display devices by default) may inadvertently disable dual display mode for your existing dual display rooms. To avoid this, you must create and maintain a separate configuration profile for any devices that require dual display support. [Learn more](/en-us/microsoftteams/devices/device-management#best-practices-for-managing-configuration-profiles).

- **3x3 video gallery on dual displays**![](../media/mtr-pro-icon.png) . Dual display rooms can now show up to 18 participant videos (3x3 on each screen) when no content is being shared during meetings.
- **Receive Cloud IntelliFrame**![](../media/mtr-pro-icon.png) . Cloud IntelliFrame enhances non-AI cameras, showing in-room participants in individual frames like remote attendees for a more natural, engaging experience. Teams Rooms on Android can now receive Cloud IntelliFrame video feeds, bringing uniformity across Windows and Android devices. [Learn more](/en-us/microsoftteams/devices/cloud-intelliframe).
- **Whiteboard enhancements**. When using the whiteboard outside of meetings, your content is retained even when a meeting begins. The whiteboard's contents are preserved and shared with remote participants instantly. You can also use the 'Follow me' function to guide participants as you navigate, and collaborative cursors let you see everyone working in real-time.
- **Net Promoter Score (NPS) survey**. Users can rate how likely they're to recommend Microsoft Teams Rooms from 1 to 5 and provide additional comments on NPS surveys delivered on Teams Rooms on Android devices. NPS surveys will show up periodically after meetings end. IT admins can manage policies and allow or prevent room accounts from getting NPS surveys using PowerShell. [Learn more](/en-us/microsoftteams/manage-feedback-policies-in-teams).
- **Admin email support for Report a problem**. IT admins can designate an email address for receiving 'Report a problem' submissions from Teams Rooms on Android devices. The email address can be set from the Teams admin settings on the device or from the Teams Rooms on Android configuration profile on the Teams admin center. Once the email is set up, the 'Report a problem' option shows up on the app for users to submit issues to the organization.

### 1449/1.0.96.2024101004 (October 2024)

Resolved issues:

- Resolved a bug to ensure smooth migration to AOSP Device Management in a future release.
- Improved diagnosability for proximity-based meeting join.
- Fixed app crashes and performance issues.

### 1449/1.0.96.2024091202 (September 2024)

Resolved issues:

- When a secondary external camera is attached, users are unable to switch the room camera in meetings.
- Local HDMI content that is projected outside of a meeting gets automatically shared into a meeting.
- Incorrect Korean translation of calendar time slots.
- The Join button isn't showing up correctly on the calendar for Direct Guest Join meetings.
- Various issues causing meetings to crash.
- Minor improvements and bug fixes.

### 1449/1.0.96.2024080804 (August 2024)

Introduced in this update:

- **Custom backgrounds**![](../media/mtr-pro-icon.png) . IT admins can upload custom background images on the Teams admin center to reinforce their company brand on their Teams Rooms on Android devices. The main room display, extended room display, and touch console can each have their own specific background image. PNG, JPG, and JPEG formats are supported. This feature is only available with the Teams Rooms Pro license. [Learn more](/en-us/microsoftteams/rooms/custom-backgrounds-android).
- **Join Zoom meetings with an ID and passcode**. Users can now join Zoom meetings with an ID and a passcode on Teams Rooms on Android. Rooms must be configured to enable Direct Guest Join meetings. [Learn more](/en-us/microsoftteams/rooms/third-party-join).

Resolved issues:

- Joining meetings on some devices results in meeting drops and returning to the home screen.
- Built-in Teams backgrounds aren't downloading successfully.
- Tapping Meet now on some devices shows a notification that the app doesn't support launching on secondary displays.
- When joining Direct Guest Join meetings while the HDMI ingest cable is connected, the HDMI ingest feed is shown as the room video instead of the local room camera feed.
- Volume is increased and decreased by increments of 30 instead of 10 on some devices..
- Participant video gets reframed from fit-to-frame to fill-frame intermittently on some devices.
- Various meeting and call reliability issues.

### 1449/1.0.96.2024061103 (June 2024)

Introduced in this update:

- Bug fixes and other improvements.

### 1449/1.0.96.2024042606 (April 2024)

Introduced in this update:

- **Home screen refresh**. The Teams Rooms on Android home screen matches the look and feel of Teams Rooms on Windows, enabling users to engage with a consistent Teams Rooms interface. The touch console features six action buttons and shows the room calendar on the right side of the home screen. If the Bluetooth beaconing setting is enabled, a room tip appears at the bottom left corner of the front-of-room display and touch console for user education.
- **Join meetings with a QR code**. Users can quickly join upcoming meetings by scanning a QR code on the Teams Rooms home screen using a mobile camera. Users will then enter the room companion mode experience on Teams mobile and the full meeting experience on Teams Rooms. Users can also scan the QR code to start an ad-hoc meeting or cast content from mobile to the front-of-room display. If the user doesn't have the Teams mobile app, they'll be directed to download it after scanning the QR code. Cross-tenant meetings are supported when the organization setting and user policies allow it. IT admins can control the feature from the device settings or the Teams admin center. [Learn more](/en-us/microsoftteams/rooms/teams-rooms-qr-codes).
- **4K local HDMI content sharing**. Users can consume HDMI content in 4K quality on Teams Rooms on Android devices that support 4K HDMI input when users project content to the front-of-room display without joining an online Teams meeting.
- **Give feedback support**. The Help button includes a Give feedback option that lets users share their opinions and ideas about Teams Rooms on Android with Microsoft, just like users can do so on Teams desktop, web, mobile, and Teams Rooms on Window clients. This feedback is used to improve the Teams experience. IT admins can enable or disable this feature for users and manage other feedback policies using PowerShell. [Learn more](/en-us/microsoftteams/manage-feedback-policies-in-teams).
- Performance improvements in meetings including when users share HDMI content.

### 1449/1.0.96.2024032804 (April 2024)

Introduced in this update:

- Bug fixes for issues with launching whiteboard and meeting join failures.

### 1449/1.0.96.2024030101 (March 2024)

Introduced in this update:

- Bug fixes for app crashes and an issue with the device restart banner that doesn't auto dismiss.

### 1449/1.0.96.2024020802 (February 2024)

Introduced in this update:

- **Meeting ID and passcode**^1^![](../media/mtr-pro-icon.png) . IT admins can configure and require users to enter a meeting ID and passcode for joining meetings to ensure a level of security and privacy.
- **New calendar views**. A new look with expanded functionalities. Users can view the calendar for the current day and the next day. Any available time slots for 11 minutes or more are shown. A visual indicator (green/purple vertical bar) is added to each time slot for users to easily see whether a room is booked or available.
- **Improved view switcher for Front of Room display controls**. The updated interface for the view switcher menu provides users with more control of the front of room displays during a meeting. Users can customize the views to show or hide the meeting chat. For Front Row, users can select which meeting component is displayed on the left and right panel. IT admins can configure the default number of panels and the default component showing on the panel(s) using the local device setting.
- Support for Teams Premium security features including end-to-end encryption for meetings and sensitivity labels.
- Fix for an experience regression in the Call app including support for P2P call and group call.
- Reliability and other improvements.
- Removal of Calling settings from the Teams admin settings on the device, including auto dial and auto answer. The latest device configuration prior to the setting removal still applies. Once a device is reset, the functionality is no longer available, just as it is for new devices.

### 1449/1.0.96.2023120901 (February 2024)

Introduced in this update:

- **Daily maintenance restart window**. By default, the device restarts anytime between 2:00 AM and 3:00 AM based on its local time zone. If the device is in use during this window and the window period ends, the restart is rescheduled the following day. IT admins can turn off this functionality or change the restart window from the device settings. Support for these admin controls is coming soon on the Teams admin center.
- Bug fixes and other improvements.

### 1449/1.0.96.2023120801 (December 2023)

Introduced in this update:

- Bug fixes for app crashes and issues with daily maintenance restart window.

### 1449/1.0.96.2023111001 (December 2023)

Introduced in this update:

- **Daily maintenance restart window**. By default, the device restarts anytime between 2:00 AM and 3:00 AM based on its local time zone. If the device is in use during this window and the window period ends, the restart is rescheduled the following day. IT admins can turn off this functionality or change the restart window from the device settings. Support for these admin controls is coming soon on the Teams admin center.
- Bug fixes for app crashes and devices not showing up on Intune.
- Significant reduction in sign out errors and pairing issues due to Workplace Join failures, timeout issues, and memory leaks.

### 1449/1.0.96.2023090601 (October 2023)

Introduced in this update:

- Improvements to the pairing resiliency of the room system and the touch console.
- Other reliability improvements and bug fixes on authentication, smart camera controls, and proximity join.

### 1449/1.0.96.2023062301 (June 2023)

Introduced in this update:

- GCC-H support ![](../media/mtr-pro-icon.png)
- Smart camera controls ![](../media/mtr-pro-icon.png)
- Content camera ![](../media/mtr-pro-icon.png)
- Primary camera switching
- Default meeting layout controls

### 1449/1.0.96.2023060802 (June 2023)

Introduced in this update:

- Fixes for console pairing issues

### 1449/1.0.96.2023050203 (May 2023)

Introduced in this update:

- Quality and reliability fixes

### 1449/1.0.96.2023041207 (April 2023)

Introduced in this update:

- Performance improvements and fixes for volume controls, meeting join latency, chat loading, and layout switching issues

### 1449/1.0.96.2023031201 (March 2023)

Introduced in this update:

- Join Teams meeting with ID
- Single tap ad hoc meetings
- Room reservation extension ![](../media/mtr-pro-icon.png)
- Front row layout ![](../media/mtr-pro-icon.png)
- Meeting chat in Gallery, Large gallery, and Together mode ![](../media/mtr-pro-icon.png)
- HDMI connect auto share controls
- HDMI audio share
- Collaborative annotations support
- Teams Premium watermark-enabled meetings support

### 1449/1.0.96.2022120503 (December 2022)

Introduced in this update:

- Whenever you want to brainstorm in the office, just walk up and start whiteboarding using the new whiteboard button on the home screen. With just one touch, you can quickly launch Microsoft Whiteboard and start collaborating outside of a Teams meeting. Admins can enable and control this feature with the **Allow initiate Whiteboard** setting on the device.
- Seamlessly switch from local to online collaboration by selecting Start meeting on the local whiteboarding screen. This action kicks off an ad-hoc meeting and automatically presents the existing whiteboard. From there, you can add participants into the meeting and contribute across the same whiteboard in real-time.
- Microsoft Whiteboard can now be viewed side by side with remote meeting participants using the Content + Gallery layout. Whenever content sharing starts, Content + Gallery will now be the default layout regardless of the content type.
- Content sharing in a meeting is more accessible with the redesigned share menu. When you select **Share** in the meeting control bar, you can find all content options that can be shared in one place, including Microsoft Whiteboard. Sharing Microsoft Whiteboard in a meeting is also now supported on resource accounts. [Admins, see instructions on how to manage Microsoft Whiteboard sharing in Teams](/en-us/microsoft-365/whiteboard/manage-sharing-organizations)
- We're also introducing a new touch screen support that allows you to control the room system from both the touch display at the front of the room and the touch console, whichever is more convenient. Admins can enable this feature with the **Enabled touch screen controls** setting on the device. To further enhance the meeting experience on large screen devices, 4K display is also now supported.
- Aside from optimizing touch experiences for local meetings, we're also enriching hybrid meetings through remote camera pan, tilt, and zoom controls support. Remote meeting participants can now control the zoom and orientation of a Teams Rooms camera directly from their desktop during a meeting. [Admins, follow these instructions for enabling this setting](/en-us/microsoftteams/meeting-policies-audio-and-video)
- Joining a meeting on a room device has also become more inclusive. With chat notifications, you can see incoming chat messages on the front-of-room display and participate in the meeting on equal grounds. Admins can enable this setting in the device settings, and you can temporarily disable this setting using the meeting control bar.

### 1449/1.0.96.2022090606 (September 2022)

Introduced in this update:

- Teams crops videos to make them fit your screen better. (Microsoft Teams Rooms are excluded from this cropping by default to give you an uncropped view of meeting rooms.) Learn more at [Adjust your view in a Teams meeting](https://support.microsoft.com/office/adjust-your-view-in-a-teams-meeting-9825091c-0e7d-4c2b-95f5-eba644f19175).
- Fit to frame automatically enabled for incoming videos from other Microsoft Teams Rooms devices.
- Improvements and bug fixes for video-related issues.
- Support for Microsoft Teams Rooms Pro and Microsoft Teams Rooms Basic licenses.
- For known issues and troubleshooting, see [Known issues in Teams Rooms and devices](/en-us/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues).
- Get more details about the latest update at [Microsoft 365 blog](https://www.microsoft.com/microsoft-365/blog/2022/09/06/meet-microsoft-teams-rooms-pro/).

### 1449/1.0.96.2022072103 (August 2022)

In partnership with Cisco, you're able to join Cisco WebEx meetings through Microsoft Teams. After you enable **Direct guest** **join** through settings, schedule a new Cisco WebEx meeting or forward an existing meeting to the Teams Rooms on Android. The meeting appears on the calendar and will be available to join.

For IT admins who want to learn more about known issues and troubleshooting Teams Rooms on Android, see [Known issues in Teams Rooms and devices](/en-us/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues).

### 1449/1.0.96.2022051102 (May 2022)

In partnership with Zoom, we're releasing an ability to join Zoom meetings through Microsoft Teams. After you enable **Direct guest** **join** through settings, schedule a new Zoom meeting or forward to an existing Zoom meeting to the Teams Rooms on Android. The meeting appears on the calendar and will be available to join.

To increase the flexibility of how you view people and content in a meeting, we're providing a way for participants to change the orientation of the videos when content is shared, or participants are spotlighted. If you see a strip of participants on the screen, you can change its location by selecting **Layout**.

For known issues and troubleshooting, read [Known issues in Teams Rooms and devices](/en-us/microsoftteams/troubleshoot/teams-rooms-and-devices/rooms-known-issues)

### 1449/1.0.96.2022011305 (February 2022)

Introduced in this update:

- Meetings now display more attendee videos and provide additional flexibility of what is shown on the Teams Rooms front-of-room displays. Here are a few significant improvements:
- Split gallery views in a dual screen meeting.
- Spotlight multiple attendees at once.
- Docked meeting controls.
- New reactions.
- You can view content in the room or share it into the meeting by plugging in an HDMI cable. Available for all certified devices with HDMI capability.
- Presenters and organizers are able to control camera and microphone access for all attendees.
- Five new wallpapers to choose from to customize your Teams Rooms on Android devices. These wallpapers apply to the front-of-room displays in a single and dual screen configuration.
- Webinar presenters can now join and participate from the Teams Rooms on Android devices.
- To provide a more cohesive experience, all IT admin settings are combined into one group under device settings for easier room configuration.
- These settings are available only on shared room accounts and require a password to access.
- This functionality is available on a select set of devices.
- A warning message will appear on the front-of-room display when the room is over capacity.
- This will initially be available only on these select devices: EPOS EXPAND Vision 3T, Yealink MeetingBar A20, Yealink MeetingBar A30.
- When someone checks in on a Teams panel devices and the previous meeting is running over, a notification appears on the front-of-room display to inform those people in the room that their meeting is over, and that people are waiting for the room. (Must have a Teams panel device paired with the Teams Rooms device).

### 1449/1.0.96.2021070803 (July 2021)

Introduced in this update:

- Calling and meeting video optimizations
- Connectivity improvements between touch console, meeting room bar, and mobile room remote
- Access to the dial pad from a remote controller during calls and meetings
- Ability to send feedback and report a problem from the touch console

### 1449/1.0.96.2021051904 (June 2021)

Introduced in this update:

- Simplified sign-in screen
- IT Admins can do remote provisioning and sign-in of Teams Rooms from the Teams Admin Center
- Use your phone or a secondary Teams device as a remote for the Teams Room. Control mic, camera, volume, live captions, and lay out settings via the secondary device
- Select Teams Rooms devices now support projecting your screen via HDMI cable
- Live captions now available for one-on-one calls
- Presenters and organizers can select to lock a meeting to prevent anyone else from joining the meeting. Go to **More** &gt; **Lock** **meeting**
- Hide meeting titles in the calendar on certain Teams Rooms devices
- IT admins can now enable auto-answer for Teams Rooms when someone starts an instant meeting via **Meet** **now**
- 1080p resolution now supported in outgoing video

### 1449/1.0.96.2021032002 (April 2021)

Most Teams Rooms on Android devices are compatible with a touch console. When paired with a Teams Rooms system, the console allows you to see the room calendar, join meetings, and place calls directly from the console. During meetings or calls, you're able to see current meeting participants, add new ones, switch content layouts, raise hands, and more

A full-day calendar view shows all scheduled meetings on the system and permit you to join meetings directly from the device. All existing calling and meeting functionality will move to the console and will be arranged along side the calendar.

Note

If the touch console is connected, all actionable functionality will move to the console, but the calendar will remain visible on the connected display for quick reference.

The following features are available to you when you sign in with your account (for example, E5 licenses) into the Teams Rooms on Android systems:

- Start Microsoft Whiteboard and share the whiteboard in the meeting from the Teams Rooms device.
- Start recording during meeting or call.
- Enable background effects (blur background or use an image). This functionality is only available when a touch console isn't paired.

### 1449/1.0.94.2020102101 (December 2020)

Introduced in this update:

- Dual screen support. Some select hardware that supports dual display configuration can now have a dual display experience with Teams. It's useful in meetings, where meeting participants are presented on one display and content on the other
- Meeting gallery supports 9 participants. Now Teams Rooms on Android will show up to 9 participants on the meeting stage
- New layouts. Together mode and Large gallery layouts are now available under the existing Layout button during meetings. These additional layouts are made to highlight video participants better
- Spotlight. Teams Rooms on Android will present spotlighted participants as large tiles on the meeting stage similar to content. Only desktop Teams clients are capable of selecting spotlighted participants at this time
- Request to speak. Muted participants can now request to be unmuted by raising their hand during meetings
- Auto-answer. Teams Rooms on Android can answer calls or meeting invites automatically. This setting is available to shared configurations only and is located in Admin settings

---