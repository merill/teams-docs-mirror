---
layout: Conceptual
title: Teams Rooms home screen and admin controls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/mtr-home-refresh
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
ms.date: 2026-11-10T00:00:00.0000000Z
ms.topic: article
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
description: Learn about the Microsoft Teams Rooms home screen design and features.
locale: en-us
document_id: 57a3d302-b586-7147-0ef3-4cd8db136ca5
document_version_independent_id: 57a3d302-b586-7147-0ef3-4cd8db136ca5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/mtr-home-refresh.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/mtr-home-refresh
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/mtr-home-refresh.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d2585b8e-ec1b-afcb-7fc2-f7f5cb8fc066
---

# Teams Rooms home screen and admin controls - Microsoft Teams | Microsoft Learn

Microsoft Teams Rooms includes a modern home screen design that provides a seamless, intuitive, and consistent look and feel with other Teams devices. The touch console (or touch board) offers a clean and straightforward user experience, prominently displaying a room calendar, an easy access to join upcoming scheduled meetings with a single touch, and commonly used actions like starting a meeting, making a call, and sharing content. Additionally, the home screen features customizable background options, allowing you to tailor the interface to your organization's needs. This user-centric design ensures efficient collaboration and communication, enhancing productivity in a modern workplace environment.

This article explains the various features available on a Teams Rooms touch console (or touch board), including the default experience, the ways you can configure a feature (if applicable), and any differences between Teams Rooms on Windows and Teams Rooms on Android. For a more comprehensive overview of the Teams Rooms user features beyond the home screen experience, see [Get started with Teams Rooms](https://support.microsoft.com/office/get-started-with-microsoft-teams-rooms-0e3b47c5-5bc0-4b96-af31-56ac7d4606f9).

## Home screen actions

### Meet now

Room users can instantly start an ad-hoc Teams meeting using Meet now on any **Teams Rooms (Windows and Android)** device. To ensure that you aren't blocking this functionality using policy, see [Manage who can start instant meetings](/en-us/microsoftteams/manage-who-can-schedule-meetings).

### Call

**Teams Rooms (Windows and Android)** devices include Call. By default, Teams Calling is available, allowing room users to make and receive peer to peer and group calls with other user(s) in the organization or with federated Teams user(s).

Additionally, **Teams Rooms (Windows and Android)** devices also support Public Switched Telephone Network (PSTN) calling as the Teams Rooms Pro license includes the M365 Phone System functionality. In addition to having the proper license, you need to add a Calling Plan, Operator Connect, or Direct Routing configuration to your Teams Rooms account for the PSTN functionality to work. Learn more at [Teams PSTN connectivity](/en-us/microsoftteams/pstn-connectivity).

Furthermore, with a Teams Rooms Pro license, **Teams Rooms on Windows** devices support SIP/H.323 calling. For more information, see [Meetings with SIP and H.323 devices](/en-us/microsoftteams/rooms/meetings-with-sip-h323-devices).

### Share content

Room users can share content to any **Teams Rooms (Windows and Android)** device either wirelessly using Teams cast or by connecting their personal device to the room system using an HDMI or USB-C cable.

#### Teams cast

By default, Bluetooth beaconing is enabled on all **Teams Rooms (Windows and Android)** devices so room users can [cast content from desktop](https://support.microsoft.com/office/cast-content-from-your-desktop-to-a-microsoft-teams-room-6d62cdbb-3da2-4bb9-80bd-9cf1098beb3d) or [cast content from mobile](https://support.microsoft.com/office/cast-content-from-a-mobile-device-to-a-microsoft-teams-room-c4e5fb1b-6b94-4d48-88f2-6bcd8e7e339d) to the front-of-room display. To disable Bluetooth beaconing:

- On a **Teams Rooms on Windows** device, open **Settings** &gt; **Device** &gt; toggle **Bluetooth beaconing** to Off as desired. You can also make the configuration change using the [Teams Pro Management Portal](enrolling-mtrp-managed-service).
- On a **Teams Rooms on Android** device, open **Teams Admin Settings** &gt; **General** &gt; toggle **Bluetooth beaconing** to Off as desired. You can also make the configuration change using the [Teams Pro Management Portal](enrolling-mtrp-managed-service).

#### HDMI input

By default, upon plugging in an HDMI device to the room system, all **Teams Rooms (Windows and Android)** devices automatically share the audio and video output of a connected HDMI ingest device. If dual screens are connected to your **Teams Rooms on Windows** device, by default, HDMI content is shared onto both front-of-room displays. On **Teams Rooms on Android** devices with a dual screen deployment, HDMI content is only shared onto the extended front-of-room display.

Warning

We don't recommend having devices which always output a video signal connected to the HDMI ingest. This is known to cause challenges when trying to present content in a Teams meeting and leads to a misreport in usage data due to the system believing it's always in use.

On a **Teams Rooms on Windows** device, you can disable automatic sharing into a Teams meeting but this doesn't disable automatic sharing onto the front-of-room display. To disable automatic sharing into a meeting, open **Settings** &gt; **Meetings** and toggle **Automatic screen sharing** to Off.

On a **Teams Rooms on Android** device, you can disable HDMI ingest audio and automatic HDMI content sharing onto the front-of-room display (which also disables automatic sharing into a Teams meeting). To do so, open **Teams Admin Settings** &gt; select **Meeting** and toggle **Include Audio** and/or **Automatically share to the room display** to Off as desired. Alternatively, you can adjust these settings through the [Teams Pro Management Portal](enrolling-mtrp-managed-service).

### Start Whiteboard

For in person brainstorming sessions, **Teams Rooms (Windows and Android)** devices offer a quick way to start an ad-hoc Microsoft Whiteboard session from the home screen.

If the front-of-room display of your **Teams Rooms on Android** device isn't touch-enabled, you can disable this feature: open **Teams Admin Settings** &gt; **Meetings** and toggle **Allow room to initiate whiteboarding** to Off as desired. You can also update this setting using the Teams Rooms on Android configuration profile in the Teams admin center. Whiteboard is available on all Teams Rooms on Android devices. On Teams Rooms on Windows devices, Whiteboard from the home screen is supported only on touch board deployments.

### Join with a meeting ID

If room users would like to join a meeting that isn't on the room calendar, **Teams Rooms (Windows and Android)** devices allow users to enter the meeting ID and passcode to join a meeting. Entering the meeting ID and passcode to join third-party meetings is also supported if third-party meetings are enabled on the device. To enable third-party meetings, see [Enable Teams Rooms devices to join third-party meetings](/en-us/microsoftteams/rooms/third-party-join).

### Room controls

**Teams Rooms on Windows** devices offer an extensibility option referred to as Room controls, supported by Teams Rooms device manufacturers or Audio Visual (AV) partners. Consult your Teams Rooms device manufacturer or your AV partner if you wish to add extensibility controls for lights/blinds, cameras, or custom video routing.

### Accessibility options

For accessibility, **Teams Rooms on Windows** devices allow room users to switch on/off a high contrast screen mode. Installation of an external keyboard is also supported if desired. Accessibility options on **Teams Rooms on Android** devices are controlled by the Teams Rooms device manufacturer.

### Language settings

By default, **Teams Rooms on Windows** devices allow room users to change the language of the Teams Rooms app using the Language button in the home screen. The language choices offered are the same as the ones available on the Teams desktop app. Once the language has been changed on the device from the home screen, the device continues using that language until a restart occurs (can be triggered by a user or during the device maintenance reboot). Administrators can disable room users from temporarily changing the language of the Teams Rooms app through the [Teams Pro Management Portal](enrolling-mtrp-managed-service).

Language options on **Teams Rooms on Android** devices are controlled by the Teams Rooms device manufacturer.

### Help and feedback

#### Report a problem

Under Help, Report a problem will show if your **Teams Rooms (Windows and Android)** device has a preview app or if your account is in a preview ring.

Outside of the preview experience, **Report a problem** is enabled by default on **Teams Rooms on Windows** devices with a Teams Rooms Pro licensed account.

When a user reports an issue, a feedback event is created in the Teams Rooms Pro Management portal. This event provides the information needed to investigate the issue or open a support case with room logs. Administrators can configure feedback and log collection through the [Teams Rooms Pro Management portal](enrolling-mtrp-managed-service).

On a **Teams Room on Android** device, report a problem can be enabled to send an email notification to IT admins through the [Teams Rooms Pro Management portal](enrolling-mtrp-managed-service).

#### Give feedback

Give feedback is enabled on all **Teams Rooms (Windows and Android)** devices by default. Room users can fill out Give feedback to send any comments or suggestions about Teams Rooms to Microsoft. We'll use this feedback to improve the Teams experience. Data sent through Give feedback is considered as Feedback Data under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered Customer Data or Personal Data. For more information, see [Manage Microsoft feedback for your organization](/en-us/privacy/microsoft-365/feedback/feedback-manage).

## Calendar

The room calendar on **Teams Rooms (Windows and Android)** devices shows the room availability and scheduled meetings in the room which includes third-party meetings (when enabled). By default, room users can join meetings in one touch and view meeting details including the meeting name, organizer, time, and platform. To enable third-party meetings, see [Enable Teams Rooms devices to join third-party meetings](/en-us/microsoftteams/rooms/third-party-join). Administrators can manage calendar privacy settings through the [Teams Pro Management Portal](enrolling-mtrp-managed-service).

For privacy purposes, meeting names can be hidden from **Teams Rooms (Windows and Android)** calendar and replaced with the organizer name if desired:

- On a **Teams Rooms on Windows** device, open **Settings** &gt; **Meetings** and toggle **Show meeting names** to Off to hide meeting names.
- On a **Teams Rooms on Android** device, open **Teams Admin Settings** &gt; **Meetings** and toggle **Show meeting names** to Off to hide meeting names on the Teams Rooms device.

For increased security in the meeting join experience on a shared device, **Teams Rooms (Windows and Android)** devices support requiring room users to enter the meeting credentials (ID and passcode) before joining scheduled Teams meetings. This feature requires the account on the device to have a Teams Rooms Pro license. To enable this functionality:

- On **Teams Rooms on Windows** devices, you can either require the meeting ID and passcode for all scheduled Teams meetings or only for meetings that are marked as private with the following XML settings:
- On **Teams Rooms on Android** devices, open **Teams Admin Settings** &gt; **Meetings** and toggle **Require passcode for all meetings** to On to require room users to enter the meeting credentials to join all scheduled Teams meetings.

The way **Teams Rooms (Windows and Android)** devices communicate with Exchange is aligned with the same method Teams desktop, web, and mobile clients utilize. To ensure that meetings appear correctly on your Teams Rooms clients, see [How Exchange and Microsoft Teams interact](../exchange-teams-interact). You may also want to review your Exchange calendar processing settings for additional customizations on the room calendar, see [Configure mailbox properties](/en-us/microsoftteams/rooms/create-resource-account?tabs=m365-admin-center%2Cgraph-powershell-password#configure-mailbox-properties).

Warning

Only on-premises Exchange servers with Hybrid Configuration and AutoDiscover v2 published externally are supported which is consistent with how other Teams clients connect with Exchange. If you're using Teams Rooms with an on-premises Exchange server, we recommend that you review how on-premises mailboxes work with Teams: [Microsoft Teams and on-premises mailboxes](https://techcommunity.microsoft.com/t5/microsoft-teams-community-blog/microsoft-teams-and-on-premises-mailboxes-part-1-how-do-teams/ba-p/2229851)

### Ad-hoc room reservation

Allow users to quickly book the meeting room for immediate use, helping to avoid scheduling conflicts and ensure uninterrupted spontaneous meetings. A **Reserve** button appears on the calendar when the room is available. IT admins can control this feature: 

- On **Teams Rooms on Windows** devices: open the Pro Management Portal &gt; **Rooms** &gt; select your room &gt; **Settings** &gt; **Meetings** &gt; toggle **Allow ad hoc room reservation** to control this functionality.
- On **Teams Rooms on Android** devices: open **Teams Admin Settings** &gt; **Meetings** and toggle **Allow ad hoc room reservation** to toggle this functionality or use the configuration profile within Teams Admin Center.

## QR code join

**Teams Rooms (Windows and Android)** devices display a QR code on the console and front-of-room display by default to allow users to easily bring their meetings to the room. For more information, see[Join meeting with QR codes](/en-us/microsoftteams/rooms/teams-rooms-qr-codes).

## Background

**Teams Rooms (Windows and Android)** devices include several out of the box backgrounds that can be selected as desired.

If your Teams Rooms device has an account with a Teams Rooms Pro license, you can configure custom backgrounds for your device, see [Teams Rooms on Windows custom backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds) or [Teams Rooms on Android custom backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds-android)

## Release ring indicator

**Teams Rooms (Windows and Android)** indicate with a pill icon below the time if they are in an earlier release ring for Microsoft Teams (no pill is present on a device not in preview). This indicator is intentional to ensure users know the device is running an earlier release of Microsoft Teams. Teams Rooms can be put into a preview state in any of the following ways, if you wish to move the devices out of the preview ring, review the options and undo those changes:

- [Teams Public Preview](/en-us/microsoftteams/public-preview-doc-updates)
- [Microsoft Frontier](/en-us/microsoft-365/admin/manage/get-started-frontier)
- [M365 Targeted Release](/en-us/microsoft-365/admin/manage/release-options-in-office-365)*(retiring January 2027)*
- Participating in a private preview in partnership with Microsoft. Please contact your Microsoft account team for more information.
- On a **Teams Rooms on Windows**, administrators can manage release ring and preview settings through [Teams Pro Management Portal](enrolling-mtrp-managed-service).

## Room health banner

**Teams Rooms on Windows** proactively surfaces critical room health issues through banner notifications displayed on both the front-of-room display and room console. When critical issues impact core meeting functionality, the banner informs users that the room may not support a reliable hybrid meeting experience and recommends moving to another room if needed. This sets user expectations before meeting start, improve meeting readiness, and reduce meeting disruptions. The room health banner is enabled by default and can’t be disabled and can't be controlled through signal suppression in the Pro Management Portal.

Depending on the room health state, banner notifications can appear for the following issues:

- Sign-in failed or room authentication issues
- Network connectivity issues
- Console unavailable, disconnected, or misconfigured
- Display unavailable, disconnected, or misconfigured
- Microphone unavailable, disconnected, or misconfigured
- Speaker unavailable, disconnected, or misconfigured
- Camera unavailable, disconnected, or misconfigured