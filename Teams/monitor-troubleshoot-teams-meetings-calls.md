---
layout: Conceptual
title: Monitor and troubleshoot Teams meetings and calls from the Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/monitor-troubleshoot-teams-meetings-calls
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.topic: article
ms.service: msteams
ms.subservice: meetings
audience: admin
ms.reviewer: snchatur
ms.date: 2026-08-24T00:00:00.0000000Z
description: Use the meeting troubleshooting experience in the Microsoft Teams admin center to diagnose and resolve meeting and call quality issues.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
- ContentFreshnessFY24
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: d4902dc8-5265-7367-867c-956f0a11239d
document_version_independent_id: d4902dc8-5265-7367-867c-956f0a11239d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/monitor-troubleshoot-teams-meetings-calls.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: monitor-troubleshoot-teams-meetings-calls
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/monitor-troubleshoot-teams-meetings-calls.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: a5597e3d-96dd-8505-a883-1c80075ae4ad
---

# Monitor and troubleshoot Teams meetings and calls from the Teams admin center - Microsoft Teams | Microsoft Learn

This article describes how to use the meeting troubleshooting experience in the Microsoft Teams admin center to diagnose and resolve meeting and call quality issues for individual users and meetings across your organization. You'll learn how to navigate meeting and call details, investigate meeting and participant details, and use telemetry data to identify root causes and take remediation actions.

**Applies to:** Conferences (including Events) and Calls - across Windows, Mac, Android, iOS, and Web

- For events, telemetry is only available for presenters and organizers (if they are participating). Telemetry is not available for other attendees.

**Available in:** Worldwide (Public), GCC

## Prerequisites

Before you begin, ensure the following:

- You have one of the supported admin roles assigned in Microsoft Entra ID. For a full list of supported roles, see [Use Microsoft Teams administrator roles to manage Teams](using-admin-roles).
- If your organization uses Administrative Units (AUs), your AU assignment determines which users' meetings you can access.
- Partner admins using Granular Delegated Admin Privileges (GDAP) must be assigned the Teams Communications Support Specialist (TCSS) or Teams Communications Support Engineer (TCSE) role in the customer tenant.
- Users whose meetings you want to investigate must be using Microsoft Teams.

Note

Meeting troubleshooting data (real-time granular and aggregate) is available for all Teams users regardless of license type. However, the depth and retention period of telemetry data varies by license.

## Overview

The meeting troubleshooting experience in the Teams admin center provides three interconnected views that allow you to move from a broad, cumulative perspective for a user down to the session-level details:

- **User view** - Shows a user's meeting history alongside weekly quality and activity trends. The view includes the **In-progress meetings** list (earlier these meetings showed up as "Recent meetings") and the **Completed meetings** list (earlier these meetings showed up as both "Recent meetings" and "Past meetings" depending on user license and elapsed time). Both the lists include only the meetings in which the user has participated. They do not include the meetings that the user has organized but not participated.
- **Meeting view** - Shows the details of a specific meeting, including participant summaries, issue trends, and suggested root cause analysis.
- **Participant view** - Shows session-level telemetry and diagnostics for a specific participant in a meeting. If a participant joins the meeting from multiple sessions, the experience brings all the sessions within the same view.

You can navigate between these views to progressively narrow your investigation from the meeting level to a specific user session.

## Find a meeting you want to troubleshoot

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com).
2. In the left navigation, select **Manage users**. Select the user whose meetings you want to troubleshoot.

    Note

    If you manage a subset of users through Administrative Units, you'll only be able to find users that are part of your scope.
3. Select the **Meetings & calls** tab, and then select an ongoing meeting from the **In-progress meetings** list or a completed meeting or call from the **Completed meetings** list.

    [![Screenshot of the user view of the meeting troubleshooting experience in the Teams admin center.](media/monitor-troubleshoot-meetings-calls-user-view.png)](media/monitor-troubleshoot-meetings-calls-user-view.png#lightbox)

### In-progress meetings

The In-progress meetings table lists all meetings currently taking place across your tenant. Use this table to identify and respond to active quality issues in real time.

**Supported activity types:** Meetings, Events

Each meeting is represented by a row that shows:

- **Meeting information** - including ID, start time, user join time, activity type, participant count, and user status in the meeting
- **Meeting issues** - count of potential issues related to the audio, video, and screen sharing experience of the user, including those cause by call drops, call failures, or device-related issues.

Note

In-progress meeting data includes all users regardless of license type, while the meeting is live.

### Completed meetings

The Completed meetings table lists meetings that have ended and for which telemetry has been processed. Once the meeting has ended, it might take from 30 minutes to 2 hours for the telemetry to be processed.

**Supported activity types:** Conference (Meetings, Events), Calls (P2P, PSTN)

The following information is available:

- A summary of meetings and calls for the user - The ratio of meetings with and without issues in the last 7 and 30 days
- Weekly activity summary

Each meeting is represented by a row that shows:

- **Meeting information** - including ID, start time, user join time, activity type, participant count, and user status in the meeting
- **Meeting issues** - count of issues related to the audio, video, and screen sharing experience of the user, including issues caused by call drops, call failures, or device-related issues.

Note

Completed meeting data includes all users regardless of license type.

To find specific completed meetings:

- Use **Search** to find meetings by their ID or Meeting Code.
- Use the **Sort** controls to sort the meeting list by any available column.
- Use the **Filter**options to narrow results by one or more of the following:
    - Issues types - Audio, Video, Screenshare
    - Activity type - Call or Conference
    - Date

Select a meeting ID or participant count to navigate to the Meeting details page. Select **View participant telemetry** to navigate to the Participant details page for the user.

To export completed meeting data:

1. Select **Export** from the completed meetings list.
2. The data for all completed meetings in the 30-day period is downloaded as a CSV file.

Important

**What's changed** - Meeting and call quality is no longer categorized as Good or Poor. Instead, you can now check if the user faced any quality or reliability issues in the meeting. Quality is judged using [intelligent media classifiers](cqd-intelligent-media-quality-classifiers), which are a set of machine learning models trained on Teams call telemetry and help pinpoint specific problem areas in stream quality.

## Investigate a meeting

**Use Copilot:** Select any meeting in the Completed meetings table, and then select the **Troubleshoot** table action. Copilot opens in a chat window within the Teams admin center with a prefilled prompt. Just run the prompt and Copilot provides a detailed analysis of the user's experience in the meeting. This option is only available if at least one user in your organization has a Copilot license.

Otherwise, select any meeting for a user to open the Meeting details page. This page provides a detailed breakdown of everything that occurred during the meeting and is organized into three sections.

While the meeting is in progress, the information updates every minute. You can use the graph to move across different time windows in a meeting.

[![Screenshot of the meeting view of the meeting troubleshooting experience in the Teams admin center.](media/monitor-troubleshoot-meetings-calls-meeting-view.png)](media/monitor-troubleshoot-meetings-calls-meeting-view.png#lightbox)

### Meeting information

This section provides general details about the meeting, including:

- Meeting ID and code
- Meeting start time and duration
- Number of participants
- Meeting organizer
- Activity type

### Issues

This section lists all quality and reliability issues occurring/occurred during the meeting. For each issue, you can view:

- **The issue type and description** - The issues are categorized as per the experience they affect - Audio, Video, and Screenshare. Reliability and device issues like call drops, call failures, and system issues are categorized as Other.
- **The participants affected**
- **Possible root cause and recommended actions** to help resolve or mitigate the issue

While the meeting is in progress, the issues are aggregated for the selected 10-minute time window. Issues identified while a meeting is in progress are based on target values for each telemetry metric. Since these values are general targets based on expected performance, the existence of an issue doesn't necessarily mean the user experienced degraded media quality.

Once a meeting is complete and the telemetry is aggregated, media quality is judged using intelligent media classifiers. These classifiers are a set of machine learning models trained on Teams call telemetry to accurately identify if users experienced noticeable media degradation and help pinpoint specific problem areas in stream quality.

Important

Once a meeting ends and telemetry is fully processed, all meeting details use aggregate meeting telemetry (instead of real-time granular telemetry). This ensures consistency in the data shown across all participants, regardless of their individual license type.

[![Screenshot of the meeting view of the meeting troubleshooting experience in the Teams admin center, showing details about meeting issues.](media/monitor-troubleshoot-meetings-calls-meeting-view-issues.png)](media/monitor-troubleshoot-meetings-calls-meeting-view-issues.png#lightbox)

#### Root cause areas

Each issue is categorized into a root cause area that helps identify why the issue occurred and provides recommendations based on the underlying telemetry to help mitigate the problem:

| Root cause area | Description |
| --- | --- |
| Network | Indicates the issue was caused by poor network conditions. |
| Compute | Indicates the issue was caused by a lack of processing/memory resources on the user's device. |
| Device | Indicates the issue was caused by the user's microphone, speaker/headphones, or camera. |
| Media | Indicates high confidence that the user experienced noticably degraded media quality. |

### Participants

This section lists all participants in the meeting. Each participant entry shows a summary of any issues they experienced and details of their meeting. Select a participant to open the Participant details page for more detailed diagnostics.

Note

For federated and external participants, end-user identifiable information (EUII) is obfuscated to protect privacy in accordance with Microsoft data handling policies. For peer-to-peer (P2P) calls, relevant EUII is **not** obfuscated because the shared call session requires participant information to support effective troubleshooting.

## Investigate the meeting quality of a specific participant

The Participant details page gives you diagnostic information for a single participant in a meeting. It's divided into information that applies across all of a participant's sessions and information that's specific to each individual session.

**Use Copilot:** Select any of the available Copilot prompt options to investigate the meeting quality of the participant in the meeting, or analyze the trends across the organization. This option is only available if at least one user in your organization has a Copilot license.

[![Screenshot of the participant view of the meeting troubleshooting experience in the Teams admin center.](media/monitor-troubleshoot-meetings-calls-participant-view.png)](media/monitor-troubleshoot-meetings-calls-participant-view.png#lightbox)

[![Screenshot of the participant view of the meeting troubleshooting experience in the Teams admin center, showing the Real time telemetry and Aggregate values tabs.](media/monitor-troubleshoot-meetings-calls-participant-complete.png)](media/monitor-troubleshoot-meetings-calls-participant-complete.png#lightbox)

### Participant information

The following information is shown at the participant level and reflects aggregated data across all their sessions in the meeting:

- Username and license type
- Device used
- Location based on public IP
- First join time and last leave time
- Total duration in the meeting
- Participant status

### Participant issues

This section lists all quality and reliability issues that the user faced during the meeting. For each issue, you can view:

- **The issue type and description** - The issues are categorized as per the experience they affect - Audio, Video, and Screenshare. Reliability and device issues like call drops, call failures, and system issues are categorized as Other.
- **Possible root cause and recommended actions** to help resolve or mitigate the issue

While the meeting is in progress, the issues are aggregated for the selected 10-minute time window.

### Session-level telemetry

You can view the telemetry for each session that the user has in the meeting. If a participant joined the meeting from multiple devices or reconnected during the meeting, each session is listed separately.

Detailed real-time telemetry is available for meetings in progress. Once the meeting is complete, telemetry is aggregated into average and maximum values.

Note

Real-time telemetry is available for users and accounts with **Teams Premium** and **Teams Rooms Pro** licenses for seven days after the meeting ends. For all other users, the real-time telemetry is retained for the duration of the meeting. Aggregated telemetry is available for all users for 30 days after the meeting ends.

Individual telemetry values are highlighted in red if they are outside the expected range. A value being highlighted doesn't necessarily mean the user experienced poor quality, but can help identify potential risks worth additional investigation.

Each session can contain the following information, but the values will vary depending on the type of media and devices used in the session:

#### Audio (Inbound)

| Name | Description |
| --- | --- |
| Jitter | Jitter is a measure of the variation in packet delay for a data stream. When jitter is too high, audio can become choppy. |
| Local healed ratio | Indicates when the audio healer is being invoked on the local endpoint for the inbound audio stream. High healer usage is experienced by end users as "choppy audio". |
| Packet loss | Packet loss occurs when data packets fail to reach their destination. The percentage of packets lost is based on the total number of packets sent. |
| Speaker (Audio render device) | Name of the audio render device (for example, speakers or headphones) in use. |
| Speaker/Headphone driver | Audio driver version used by the render device (speakers or headphones). |

#### Audio (Outbound)

| Name | Description |
| --- | --- |
| Round-trip time | Round trip time is the time it takes for a single packet to travel from the client to the remote endpoint and back to the client. High round trip time can cause audio latency. |
| Bitrate | Throughput of the audio stream expressed in kilobits per second. |
| Codec | Displays the audio codec being sent and received. A different codec can be received than the one being sent. |
| Microphone (Audio capture device) | Name of the audio capture device in use. |
| Microphone driver | Audio driver version used by the capture device. |

#### Video

| Name | Description |
| --- | --- |
| Round-trip time | Round trip time is the time it takes for a single packet to travel from the client to the remote endpoint and back to the client. High round trip time can cause delays in stream playback. |
| Bitrate | Throughput of the video stream expressed in kilobits per second. |
| Loss recovery attempt rate | Indicates the number of times there was a request to recover from network loss causing video to freeze. This value is typically caused by packet loss on the network. |
| Source freeze count | The number of times the camera didn’t generate a new frame for more than one second. |
| Average allocated bandwidth | Average amount of network bandwidth allocated to video expressed in kilobits per second. |
| Frame rate | Number of frames per second of video the client is sending. Lower than expected values here might suggest system resource constraints, insufficient network bandwidth, or misbehaving video capture devices. |
| Resolution (vertical) | Resolution of the outbound video measured in pixels. |
| Resolution (horizontal) | Resolution of the outbound video measured in pixels. |
| Codec | Displays the video codec and rendering mode of the outbound video stream. |
| Camera (Video capture device) | Name of the video capture device in use. |
| Camera driver | Video driver version used by the capture device. |

#### Screensharing (Inbound)

| Name | Description |
| --- | --- |
| Packet loss | Round trip time is the time it takes for a single packet to travel from the client to the remote endpoint and back to the client. High round trip time can cause delays in stream playback. |
| Bitrate | Throughput of the video stream expressed in kilobits per second. |
| Frame rate | Number of frames per second of video the client is sending. Lower than expected values here might suggest system resource constraints, insufficient network bandwidth, or misbehaving video capture devices. |
| Harmonic frame rate | The harmonic average of the incoming video framerate, which represents the regularity of the incoming frames along with the rate of frames. |
| Normalized freeze duration | Rate of video freezing that is observed on the receiver side and is represented in milliseconds of freeze per minute of active video. |
| Audio/video sync | Indicates the audio / video synchronization in milliseconds. A positive value indicates audio is behind while a negative value indicates video is behind. |
| Screenshare render device | Name of the video capture device in use. |
| Screenshare render device driver | Video driver version used by the capture device. |

#### Screensharing (Outbound)

| Name | Description |
| --- | --- |
| Round-trip time | Round trip time is the time it takes for a single packet to travel from the client to the remote endpoint and back to the client. High round trip time can cause delays in stream playback. |
| Bitrate | Throughput of the video stream expressed in kilobits per second. |
| Loss recovery attempt rate | Indicates the number of times there was a request to recover from network loss causing video to freeze. This value is typically caused by packet loss on the network. |
| Source freeze count | The number of times the camera didn’t generate a new frame for more than one second. |
| Frame rate | Number of frames per second of video the client is sending. Lower than expected values here might suggest system resource constraints, insufficient network bandwidth, or misbehaving video capture devices. |
| Codec | Displays the video codec and rendering mode of the outbound video stream. |
| Screenshare capture device | Name of the video capture device in use. |
| Screenshare capture device driver | Video driver version used by the capture device. |

#### Network

| Name | Description |
| --- | --- |
| Location | User's country or region based on their public IP address. |
| Local IP Address | Local network IP address of the user's endpoint. |
| Local Port | Local network port of the user's endpoint. |
| Remote IP Address | Local network IP address for the opposite endpoint of the media connection. |
| Server Reflexive IP Address | Public egress IP for the user's media connection. |
| Connectivity type | Type of network connection for the user's endpoint, such as Ethernet or WiFi. |
| Local transport bytes sent | Number of media bytes transmitted by the user's endpoint. |
| Local media path | Type of media transport utilized for the media connection. |
| Media network error | Reflects any unexpected errors in the media connection setup. |

#### System

| Name | Description |
| --- | --- |
| VDI platform | Platform used for virtual desktop infrastructure (VDI), such as Azure Virtual Desktop. |
| VDI optimization | Indicates the type and status of media optimization for VDI connections. |
| CPU | Name of the central processing unit (CPU) used for media on the user's endpoint. |
| CPU speed | Speed of the CPU in megahertz. |
| CPU cores | Number of cores in the CPU. |

Note

Some meeting telemetry parameters (like audio device details) may not be supported if the participant session is on Web, VDI, or PSTN.

#### Export

You can additionally download advanced telemetry for a completed meeting for further analysis.

Important

**What's changed** - The **Advanced** and **Debug** sections are no longer available. To simplify troubleshooting, you'll find the most relevant telemetry in the section for **real-time** telemetry and **aggregate** telemetry. If you wish to analyze further, all the telemetry previously available under the **Advanced** and **Debug** sections can be downloaded using **Export**.

## Further reading

- [Call Quality Dashboard](turning-on-and-using-call-quality-dashboard)