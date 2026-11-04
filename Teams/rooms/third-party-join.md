---
layout: Conceptual
title: Third-party meetings on Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/third-party-join
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: mattslomka
ms.date: 2026-09-28T00:00:00.0000000Z
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
description: This article discusses how to configure your organization and Teams Rooms devices to support third-party meeting joining to Cisco Webex and Zoom.
locale: en-us
document_id: 9c62081e-2421-80b9-8ba9-aaf8fd55e432
document_version_independent_id: 5df3c5e5-978f-cfa7-9e5c-3cd7f65fa8ff
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/third-party-join.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/third-party-join
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/third-party-join.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b5a613f4-34b0-61fd-fda3-b18ea1780d1d
---

# Third-party meetings on Teams Rooms - Microsoft Teams | Microsoft Learn

Microsoft Teams Rooms devices support a one-touch and join by ID experiences for connecting to third-party online meetings. This capability comes in two forms: Direct Guest Join (DGJ) or Cross-Platform meetings via SIP (Session Initiation Protocol) join. When third-party join is enabled, you can use Teams Rooms to join meetings hosted on other meeting platforms as easily as you can join meetings hosted on Microsoft Teams. Third-party meeting providers drive the experience of their platform on the Teams Room device.

Before you can join third-party meetings from Teams Rooms, you need to do the following steps:

1. Understand which third-party meeting join solution is right for your organization.
2. Configure the Teams Rooms' resource accounts Exchange mailbox to process invites for third-party and externally scheduled meetings.
3. Ensure no tenant policies are blocking devices from connecting to third-party meeting services.
4. Configure Teams Rooms devices to allow third-party meetings.

## Step 1: Determine which third-party meeting join solution is right for your Teams Rooms

Teams Rooms offer two ways for connecting to third-party meetings: a SIP video-based solution known as cross-platform meeting via SIP join and a WebRTC based solution known as Direct Guest Join. These solutions have different requirements and capabilities which are noted in the table. Review the table and determine which is right for your organization.

| Supported Functionality | Cross-Platform Meetings via SIP | Direct Guest Join |
| --- | --- | --- |
| Join Button | Amazon Chime Cisco Webex Google Meet GoToMeeting RingCentral Zoom Other SIP services | Cisco Webex Zoom Google Meet |
| Join by ID | Amazon Chime Cisco Webex Google Meet GoToMeeting RingCentral Zoom Other SIP services via SIP URI | Zoom Google Meet |
| Events | Cisco Webex\* Zoom\* | Not available |
| Receive video quality | Up to 1080p / 30 fps | Up to 720p / 30 fps |
| Send video quality | Up to 1080p / 30 fps | Up to 720p / 30 fps |
| Receive content | Available | Available |
| Send content with HDMI | Available | Not available |
| Send content with content camera | Available | Not available |
| Camera PTZ controls | Not available | Not available |
| Maximum front of room displays | Two displays | One display |
| Layout controls | Available\* | Available\* |
| List participant | Available\* | Available\* |
| View chat | Available\* | Available\* |
| Breakout rooms | Available\* | Available\* |
| View reactions | Available\* | Available\* |
| Send reactions | Not available | Not available |
| View content annotations | Not available | Not available |
| View transcript | Not available | Not available |
| Recording notification | Available | Available |
| Whiteboard view | Available\* | Available\* |
| Whiteboard interaction | Not available | Not available |
| Lobby control | Available\* | Not available |
| Lobby authentication / bypass | Not available | Not available |
| Microphone mute sync | Not available | Not available |
| Teams Rooms coordinated join | Not available | Not available |
| SIP paid dialing plan required | Yes | No |
| Direct internet access required | No | Yes |
| Teams Rooms license | Teams Rooms Pro | Teams Rooms Basic Teams Rooms Pro |

Note

\*Third party platform features listed were available at the time this article was last updated and may vary from platform to platform. Microsoft periodically reviews these features to keep this document current but other platforms may make changes which can impact these features.

## Step 2: Allow Exchange to process third-party meetings and externally created invites

When a Teams Room joins a Teams Meeting, it utilizes hidden properties in the Outlook meeting invite to know the meeting link to join. But when joining third-party meetings, Teams Rooms read the calendar invite message body so you need to retain the meeting invite body to ensure a join button can be generated for third-party meeting platforms. Similarly, a typical use case for third-party meeting join is for meetings created outside of your organization, in which case, you want users to be able to forward the externally scheduled meeting invite to their preferred meeting space and have the room accept the invite.

To enable these scenarios, you need to modify the Exchange calendar processing rules on the room resource account. To set these room mailbox options using the [Set-CalendarProcessing](/en-us/powershell/module/exchange/set-calendarprocessing) cmdlet, do the following steps:

1. Connect to Exchange Online PowerShell. For more information, [Connect to Exchange Online PowerShell](/en-us/powershell/exchange/mfa-connect-to-exchange-online-powershell).
2. Using the resource account mailbox's user principal name (UPN), run the following command. Replace `<UserPrincipalName>` with the room mailbox's UPN:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False
    ```

## Step 3A: Configure URL rewrite policies to not modify third party meeting links

To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite by the Teams Room device. If your organization uses [Microsoft Defender for Office 365](/en-us/microsoft-365/security/office-365-security/safe-links) safe links, no additional steps are required. However, if your organization uses a third-party solution that scans all URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device. To ensure invites work, you need to add the third-party meeting service's URLs to the [Defender for Office 365 Safe Links](/en-us/microsoft-365/security/office-365-security/safe-links)**[Don't rewrite](/en-us/microsoft-365/security/office-365-security/safe-links)**[list](/en-us/microsoft-365/security/office-365-security/safe-links), or the third-party URL rewrite exception list. If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.

Here are some example entries that you may need to add to a rewrite exception list:

- **Cisco Webex**`*.webex.com/*`
- **Zoom**`*.zoom.us/*`, `*.zoom.com/*`, `*.zoomgov.com/*`
- **Google**`*.meet.google.com/*`

Caution

Only add URLs that you trust to your *don't rewrite* exception list.

## Step 3B: If you're utilizing Direct Guest Join, ensure your network connections are optimized to connect to your desired platform

When using Direct Guest Join, Teams Rooms devices connect directly to the website of that third-party platform. Because of this direct connection, your Teams Rooms devices need to be able to connect to that third party website. Ensure your organization’s firewalls or web filters allow the traffic without authentication and that the web traffic is in an appropriate QoS class (if applicable). Refer to the third-party meeting platforms documentation for the correct URLs and IPs to allow.

## Step 4: Enable third-party meetings on your Teams Rooms devices

The last step you need to take is to allow Teams Rooms to join third-party meetings with Teams Rooms device settings. If the username and email address that you wish to use to join meetings is different than the device's resource account, you can configure that while enabling third-party meeting join.

# [Teams Rooms on Windows](#tab/MTRW)
If you wish to utilize the cross-platform SIP join capability, you need to enable SIP video calling on your Teams Rooms following these instructions: [SIP and H.323 Dialing](meetings-with-sip-h323-devices). Once SIP calling is enabled, the Teams Room automatically uses SIP instead of WebRTC to join the enabled third-party meetings. To ensure SIP calling enabled Teams Rooms can always join a meeting, Teams Rooms will automatically use Direct Guest Join over WebRTC if the third party meeting invite doesn't contain a SIP dial string. Lastly, if SIP calling isn't enabled, Teams Rooms on Windows devices will only utilize Direct Guest Join over WebRTC for third-party meetings.

Note

Automatic fallback to WebRTC DGJ works for meetings using the calendar join button. If users attempt to use join by ID and the meeting does not have SIP capabilities, the call will fail. Only enable SIP dialing in your organization if third-party meetings you join have SIP capabilities or educate your users on the fall back options with the calendar join buttons.

#### Using the Pro Management Portal

1. Log in to the [Teams Pro Management Portal](enrolling-mtrp-managed-service).
2. Select **Rooms**.
3. Select your desired room.
4. Select **Settings**.
5. Select **Meetings**.
6. Toggle your desired meeting platforms (for example, Cisco Webex, Zoom, Google Meet, etc.).
7. Select **Apply**.

Tip

Settings can also be managed in bulk, learn more in [Pro Management Portal Settings.](/en-us/microsoftteams/rooms/pro-portal-settings)

#### Using the local device settings

To configure Teams Rooms on Windows using the touchscreen console, do the following steps:

1. On the Microsoft Teams Rooms console, select **More**.
2. Select **Settings**, and then enter the device administrator username and password.
3. Go to the **Meetings** tab and select a third-party meeting provider you wish to enable (for example, Cisco Webex, Zoom, Google Meet, etc.).
4. If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.
5. If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.
6. Select **Save and exit**. Your device restarts.

# [Teams Rooms on Android](#tab/MTRA)
If you wish to utilize the cross-platform SIP join capability, you need to enable SIP video calling on your Teams Rooms following these instructions: [SIP and H.323 Dialing](meetings-with-sip-h323-devices). Once SIP calling is enabled, the Teams Room automatically uses SIP instead of WebRTC to join the enabled third-party meetings. To ensure SIP calling enabled Teams Rooms can always join a meeting, Teams Rooms will automatically use Direct Guest Join over WebRTC if the third party meeting invite doesn't contain a SIP dial string. Lastly, if SIP calling isn't enabled, Teams Rooms on Android devices will only utilize Direct Guest Join over WebRTC for third-party meetings.

Note

Automatic fallback to WebRTC DGJ works for meetings using the calendar join button. If users attempt to use join by ID and the meeting does not have SIP capabilities, the call will fail. Only enable SIP dialing in your organization if third-party meetings you join have SIP capabilities or educate your users on the fall back options with the calendar join buttons.

#### Using the Pro Management Portal

1. Log in to the [Teams Pro Management Portal](enrolling-mtrp-managed-service).
2. Select **Rooms**.
3. Select your desired room.
4. Select **Settings**.
5. Select **Meetings**.
6. Toggle your desired meeting platforms (for example, Cisco Webex, Zoom, Google Meet, etc.).
7. Select **Apply**.

Tip

Settings can also be managed in bulk, learn more in [Pro Management Portal Settings.](/en-us/microsoftteams/rooms/pro-portal-settings)

#### Using the local device settings

To configure Teams Rooms on Android locally on the device, do the following steps:

1. On the Microsoft Teams Rooms device, select **More**.
2. Select **Settings**.
3. Open **Teams admin settings**. Enter the device administrative credentials.
4. Select **Meetings**.
5. Select the toggle next to the third-party meeting providers you want to enable.
6. If you want to join meetings with a custom username and email address, select **Join with custom name and email**. To update custom personal info, press **Edit custom info** and input your preferred name and email address.

---