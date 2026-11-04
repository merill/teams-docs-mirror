---
layout: Conceptual
title: Export options for switching from Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/migration-from-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.topic: upgrade-and-migration-article
ms.date: 2025-12-01T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: freda.li
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guidance on exporting data when migrating from Microsoft Teams to a third-party application.
ms.localizationpriority: medium
locale: en-us
document_id: 96b712cf-e660-aae2-eb37-a2347583ca66
document_version_independent_id: 96b712cf-e660-aae2-eb37-a2347583ca66
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/migration-from-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: migration-from-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/migration-from-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 1e132066-3bc6-9f66-6ef1-3aca8aa0d9a1
---

# Export options for switching from Microsoft Teams - Microsoft Teams | Microsoft Learn

Microsoft supports customer choice, including enabling the export of data at no charge when switching from Teams to another provider. For any customer who prefers to use Teams Export APIs, refer to Access the Teams Export APIs.

In addition to the APIs, Teams now offers a brand-new data export tool for small to medium-sized customers to export data when switching. This tool allows for unlimited exports during a 90-day period with just a single action in the Teams admin center. For more information about how to use the tool, see Steps to access the Teams data export tool.

Note

These export options are specifically for switching from Microsoft Teams to another provider. For other scenarios, such as Microsoft tenant migration or backup, refer to [Export content with the Microsoft Teams Export APIs](export-teams-content).

## Steps to access the Teams data export tool

To export your data from Microsoft Teams for switching and access the tool at no charge, select [this link](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRx5b6YlW2R1CjDCOVm7MOXlURFVFWEY5R1lNWjJVQk9BWUlFQzEzQTVXQSQlQCN0PWcu&amp;rbb720c08d48c47a6a40fa4b0e8ebcbe2=%22API%20technical%20documentation%20or%20information%22&amp;r525bf46017dc41db8e35d6f44ef148a2=%22Technical%20documentation%20or%20information%22&amp;r6891e08e7e844b7083ff9059d2d841a6=%22Data%20Export%20Tool%20%28500%20users%20or%20less%29%22) to contact support through the Microsoft Form.

Complete the following fields in the Microsoft Form:

- Contact information: Provide details as requested.
- Select the category: API technical documentation or information.
- Select the question or feedback option: Technical documentation or information.
- Select the API functional area: Data Export Tool (500 users or less).
- Describe the problem: Provide an estimate of the size of your tenant and confirmation that you need to access the tool to switch from Teams.

The tool supports data export for tenants of up to 500 users. Once we receive your request, we begin processing it and notify you when you can access the tool.

### Access the Teams data export tool

Exporting data may involve your confidential, personal, and sensitive data. Note the following considerations:

- **Access role**: As the tool gives access to sensitive Teams data, you need to sign in to the Teams admin center as the global administrator to access it.
- **Duration**: You can use the tool for up to 90 days from the time the access is provided to the tool.
- **Download window**: After the data is prepared, you'll download a ZIP file with a series of JSON files. When the download link becomes available, you have 24 hours to download it.

Note

When you start exporting data or when an export is in progress, any new data created during or after the export isn't included. To capture the new, excluded content, you can do another export within the 90 days.

### Step-by-step: Using the Teams data export tool

1. Locate the **Teams data export tool** in the **Teams admin center**. Sign in to the **Microsoft Teams admin center** as a Global Administrator. On the **Dashboard**, locate the **Teams data export card**.

    [![Screenshot of the Microsoft Teams admin center, showing the Teams data export experience.](media/export/teams-data-export-1.png)](media/export/teams-data-export-1.png#lightbox)
2. Select the export scope and start the export In the **Teams data export card**, select the desired **date range** (for example, *Entire history*), and then select **Export** to begin the data export process.

    [![Screenshot of the Microsoft Teams data export card and date range experience.](media/export/teams-data-export-button-2.png)](media/export/teams-data-export-button-2.png#lightbox)
3. Review the permissions prompt When initiating the export, you will see a **permissions request** screen for the *Teams Data Export Tool*. The tool requests read-only access required to export **Teams** data, such as chats, channels, meetings, and related metadata.

    [![Screenshot of the Microsoft Teams data export card and permissions and accept experience.](media/migration-from-teams/teams-data-export-accept-3.png)](media/migration-from-teams/teams-data-export-accept-3.png#lightbox)
4. Monitor export progress After the export is initiated, the **Teams data export** card shows the current status (for example, *Preparing the data*). Once the export is complete, a download link will be made available for a limited time.

    [![Screenshot of the Microsoft Teams data export status experience.](media/export/teams-data-export-progress-4.png)](media/export/teams-data-export-progress-4.png#lightbox)
5. Download the exported data Once the export is complete, navigate to **Analytics & reports** &gt; **Usage reports**, and select the **Downloads** tab. When the export is ready, a **Download link** appears with the export file (in .zip format). Select **Download** to retrieve the exported data.

    [![Screenshot of the Microsoft Teams data export download link.](media/export/teams-data-export-files-5.png)](media/export/teams-data-export-files-5.png#lightbox)

### What the Teams data export tool supports

The data exported through the tool closely resembles the data exported through the Teams Export APIs. For more information, see [Export content with the Microsoft Teams Export APIs](export-teams-content).

The Teams data export tool allows you to export the following items from Microsoft Teams:

- 1:1 chats
- Group chats
- Meeting chats
- Channel messages

The Teams data export tool also supports the following data:

- **Team and Channel structure**: The Teams data export tool supports the Team and Channels structure. Channels are specific collaboration spaces within a team where members can focus on topics, projects, or departments.
- **User/Roster**: The Teams data export tool supports exporting the list of users who are part of a specific team or channel, including details about each user's roles.
- **Apps**: The Teams data export tool supports exporting the list of installed apps for a channel.

Note

To export meeting transcript links, an administrator must enable Microsoft Graph access to transcripts. This access is turned off by default. For configuration steps, see [Tenant administrator controls for transcript access](/en-us/graph/api/calltranscript-get?tenant-administrator-controls-for-transcript-access).

### What the ZIP file includes

| File name | Note | Public documentation |
| --- | --- | --- |
| /users/usersList.json | List of all users with user details | [List users](/en-us/graph/api/user-list) |
| /users/{userId}/messages\_{userId}.json | List of messages for a user | [chats: getAllMessages](/en-us/graph/api/chats-getallmessages) |
| /users/{userId}/retainedMessages\_{userId}.json | List of edit message history of a user | [chat: getAllRetainedMessages](/en-us/graph/api/chat-getallretainedmessages) |
| /users/{userId}/targetedMessages\_{userId}.json | List of targeted messages for a user | [userTeamwork: getAllTargetedMessages](/en-us/graph/api/userteamwork-getalltargetedmessages) |
| /users/{userId}/retainedTargetedMessages\_{userId}.json | List of edit targeted message history for a user | [userTeamwork: getAllRetainedTargetedMessages](/en-us/graph/api/userteamwork-getallretainedtargetedmessages) |
| /users/{userId}/meetings\_{userId}.json | List of meetings user is part of | [List events](/en-us/graph/api/calendar-list-events) |
| /users/{userId}/meetingRecordings\_{userId}.json | List of meeting recordings links organized by a user | [onlineMeeting: getAllRecordings](/en-us/graph/api/onlinemeeting-getallrecordings) |
| /users/{userId}/meetingTranscripts\_{userId}.json | List of meeting transcript links organized by a user | [onlineMeeting: getAllTranscripts](/en-us/graph/api/onlinemeeting-getalltranscripts) |
| /teams/teamsList | List of teams | [List groups](/en-us/graph/api/group-list) |
| /teams/teamsSettings | Team settings of all teams | [Get team](/en-us/graph/api/team-get) |
| /teams/{teamId}/teamMembers\_{teamId}.json | List of members of a team | [List members of team](/en-us/graph/api/team-list-members) |
| /teams/{teamId}/messages\_{teamId}.json | List of messages for a team | [channel: getAllMessages](/en-us/graph/api/channel-getallmessages) |
| /teams/{teamId}/retainedMessages\_{teamId}.json | Message edit history of a team | [channel: getAllRetainedMessages](/en-us/graph/api/channel-getallretainedmessages) |
| /teams/{teamId}/teamInstalledApps\_{teamId}.json | List of installed apps of a team | [List apps in team](/en-us/graph/api/team-list-installedapps) |
| /teams/{teamId}/groupEvents\_{teamdId}.json | List of meetings for a team | [List calendarView](/en-us/graph/api/calendar-list-calendarview) |
| /teams/{teamId}/channels\_{teamId}.json | List of channels for a team | [List allChannels](/en-us/graph/api/team-list-allchannels) |
| /teams/{teamId}/channels/{channelId}/channelMembers.json | List of members of a channel (Only available for shared and private channels; standard channel members are the same as teams member.) | [List members of a channel](/en-us/graph/api/channel-list-members) |
| /meetings/questionsAndAnswers.json | List of questions, answers, and reactions from meetings | [List Q&A Messages in a Meeting](/en-us/graph/api/resources/onlinemeetingengagementconversation) |

## Access the Teams Export APIs

To learn more about which data we support to export using the Teams Export APIs, see [Export content with the Microsoft Teams Export APIs](export-teams-content).

If you have questions about using the Teams Export APIs for switching from Teams to another provider at no charge, you can reach out to [Microsoft 365 Interoperability and Data Portability Feedback and Questions](https://aka.ms/TeamsAPIInteropFeedback).