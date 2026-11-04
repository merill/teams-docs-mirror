---
layout: Conceptual
title: Walkie Talkie usage and performance report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/walkie-talkie-usage-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: admin
ms.topic: article
ms.service: frontline-worker-solutions
ms.reviewer: yinchang
ms.date: 2024-12-30T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- teams-1p-app-admin
description: Learn how to use the Walkie Talkie usage and performance report in the Microsoft Teams admin center to get an overview of Walkie Talkie usage activity in your organization.
locale: en-us
document_id: db33ff9d-b43d-2f63-01f6-b1ca2aa60787
document_version_independent_id: db33ff9d-b43d-2f63-01f6-b1ca2aa60787
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/walkie-talkie-usage-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/walkie-talkie-usage-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/walkie-talkie-usage-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 63d08381-381d-8036-7476-1b660c3a5aad
---

# Walkie Talkie usage and performance report - Microsoft Teams | Microsoft Learn

The Walkie Talkie usage and performance report in the Microsoft Teams admin center gives you an overview of [Walkie Talkie](../walkie-talkie) activity in your organization. The report provides information such as the number of push-to-talk (PTT) transmissions made and received, channel activity, transmission duration, and device and participant details.

You can choose a predefined date range or set your own custom date and time range (coming soon) for the report. Use this report to gain insight into Walkie Talkie usage trends and performance in your organization.

To access the report, you must be a Teams Administrator, Global Reader, Report Reader, or Global Administrator.

Important

Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use a less-privileged role.

## Download and view the report

1. In the left navigation of the Microsoft Teams admin center, go to **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **Walkie Talkie usage and performance**.
2. Under **Date range**, select a predefined range or set a custom date and time range (coming soon). You can set a range to show data up to 30 days before the current date.
3. Select **Run report**.
4. On the **Downloads** tab, under **Status**, choose **Download** to download the report in CSV format.

## Interpret the report

The report gives you a breakdown of each transmission made during the date range that you selected. Here's the information included in the report.

| Column name | Description |
| --- | --- |
| TenantId | Tenant ID. |
| UserId | User ID. |
| DeviceId | Device ID. |
| ChannelId | The Walkie Talkie channel in which communication happens. |
| ConversationId | ID of each PTT transmission. |
| TeamId | ID of the team that corresponds to the Walkie Talkie channel in which the user connects to. |
| UnreachableParticipantsCount | Number of participants flagged as unreachable and hidden from the roster because they weren't able to receive any of the last five transmissions. |
| TransmissionDuration | Duration of time (in milliseconds) between when the service receives the notification that one participant is about to start a transmission to when the service delivers the last package of that transmission. |
| TotalParticipantsCount | Total number of participants connected to the Walkie Talkie channel. |
| PacketCount | Number of packets used to send the audio transmission. |
| NotifiedParticipants | The participants to which a push notification is sent when a transmission starts. In scenarios where the connection between the device and service is lost, a notification is sent to the device to re-establish the connection as soon as possible because a transmission is coming. |
| AudioDurationMilliseconds | Duration of the transmission in milliseconds. |
| ConnectionId | ID of each connection to a Walkie Talkie channel established by the device. |
| TransmissionStartTime | Date and time, in Coordinated Universal Time (UTC), when the first audio packet is received by the service. The format is YYYY-MM-DDTHH:MM:SS. For example, 2024-10-08T20:49:03. |
| TransmissionEndTime | Date and time, in Coordinated Universal Time (UTC), when the last audio packet is received by the service. The format is YYYY-MM-DDTHH:MM:SS. For example, 2024-10-08T20:49:05. |
| ParticipantList | A semi-colon delimited list of IDs of the devices connected to the channel at the time the transmission ends. |
| CallTimedOut | Whether the transmission exceeded the duration limit. This is a Boolean value. |
| Platform | Device operating system. |
| ParticipantType | Whether the participant was the transmitter or a receiver of the transmission. |
| WebSocketState | Whether the status of the connection between the device and the service was already established when the transmission started. |
| AppVersion | Version of the Teams app installed on the device. |
| ClientCallStatus | Indicates if the device was able to receive the transmission without any issue. |

### Use the report to identify and investigate issues

#### Missing audio transmissions

1. **Locate the ParticipantList column**. Go to the **ParticipantList** column in the report, which lists the participants for each conversation ID. This list contains the device ID for each participant of the conversation.
2. **Count the participants**. Make sure the number of participants in the participant list matches the number of rows for that conversation ID.
3. **Check for mismatches**. If the numbers don’t match, it indicates missing transmissions.
4. **Identify the missing participants**. To find out which participants missed the transmission, compare the participant IDs in the list with the rows present.
5. **Backtrack to the user ID**. Use the participant ID to backtrack and identify the specific user who missed the transmission.

#### Audio quality issues

1. **Identify client call status**. Go to the **ClientCallStatus**column in the report and check the client call status.
    - A status of FAILURE indicates an issue with the transmission. The issue could be due to network glitches, degraded audio quality, or other technical problems.
    - A status of ABANDONED means that the device received the transmission but didn’t reproduce it. This could be because the device was in Do Not Disturb mode or already engaged in another call.
2. **Analyze failure reasons**. Understand that a FAILURE status means the service was able to ping the device, but the device didn’t respond correctly. This could be due to network issues or device problems.
3. **Review specific failures**. Investigate specific failure cases such as network issues, incoming call in progress errors, or mismatched channel IDs. These can provide insights into the nature of the audio quality issues.