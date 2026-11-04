---
layout: Conceptual
title: Integrate custom collaboration applications with Microsoft 365 - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/collaboration-integration
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: daro
ms.date: 2025-01-09T00:00:00.0000000Z
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: integration
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Learn about how to integrate custom collaboration applications with Microsoft 365.
locale: en-us
document_id: 8f954985-6365-b0d5-aa91-1761916bb57c
document_version_independent_id: 8f954985-6365-b0d5-aa91-1761916bb57c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/collaboration-integration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: collaboration-integration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/collaboration-integration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 83e8e104-b070-b25d-b077-00580582e6c6
---

# Integrate custom collaboration applications with Microsoft 365 - Microsoft Teams | Microsoft Learn

This article provides an overview of collaboration-related integrations in Microsoft 365 services. This topic may be of interest to independent software developers (ISVs) developing applications that integrate with Microsoft 365. Resources to learn how to create these types of integrations in any application are included in the following sections. APIs are also available to export data from Teams for use in such custom applications.

## Collaboration services in Microsoft 365

Microsoft 365 provides standard application programming interfaces (APIs) to all developers to enable integrations, including the functionality relied upon by Microsoft product and services for such integrations. Developers can use these APIs to create many similar experiences in their own applications.

### User account management

Microsoft 365 uses Microsoft Entra ID for authentication and authorization of users, including people outside your organization (B2B guests), and for maintaining user profile information.

Microsoft Entra authentication is used by Microsoft 365 web applications such as SharePoint and OneDrive, and by client applications such as Outlook and Teams. User profile information is viewable by users in various places in Microsoft 365 and its associated applications.

Microsoft documents and makes available the APIs necessary to create these experiences in your custom applications:

- [Person resource type](/en-us/graph/api/resources/person)
- [List directReports](/en-us/graph/api/user-list-directreports)
- [List manager](/en-us/graph/api/user-list-manager)

Microsoft 365 groups are used to give groups of users access to a set of related applications, including SharePoint, Planner, and Teams. Microsoft documents and makes available the APIs necessary to create these experiences in your custom applications:

- [Group resource type](/en-us/graph/api/resources/group)

#### Calendar management

Microsoft 365 uses Exchange Online to manage users’ mailboxes and calendars. Mail and calendar information is made available to users in applications such as Outlook and Teams. Microsoft documents and makes available the APIs necessary to create these experiences in your custom applications:

- [Calendar resource type](/en-us/graph/api/resources/calendar)

#### File management

Microsoft 365 uses SharePoint and OneDrive for all file storage and sharing. The files APIs allow any application to access and modify files.

Microsoft 365 uses insights to provide lists of documents that are trending, or that a user viewed, modified, or shared. For example, OneDrive provides this information to users. These insights are available to any application via the Office Graph Insights API.

Microsoft documents and makes available the APIs necessary to create these experiences in custom applications:

- [Working with files in Microsoft Graph](/en-us/graph/api/resources/onedrive)
- [Permission resource type](/en-us/graph/api/resources/permission)
- [officeGraphInsights resource type](/en-us/graph/api/resources/officegraphinsights)

#### Search

Microsoft 365 uses a unified search engine to cover many different experiences from a single interface. This search can be extended to other applications by using the Microsoft Search API. Microsoft documents and makes available the APIs necessary to create these experiences in your custom applications:

- [Overview of the Microsoft Search API in Microsoft Graph](/en-us/graph/search-concept-overview)

## Exporting Messages and other Media from Microsoft Teams

Once you integrated your custom application with Microsoft 365, you can export direct messages, group messages, channel posts (including their replies), call and meeting transcripts and recordings from Teams by using published APIs.

Note

Some of the following APIs are metered and have costs associated with their use.

### Direct messages, group messages, and meeting messages

Teams includes direct messages (one-to-one chats), group chats, and chats associated with meetings. Messages in Teams may contain plain text, rich HTML, images, links, etc. Microsoft documents and makes available the APIs necessary to export this data out of Microsoft Teams:

- [List Chats](/en-us/graph/api/chat-list)
- [Get Chat](/en-us/graph/api/chat-get)
- [List members of a Chat](/en-us/graph/api/chat-list-members)
- [Get chatMessage in a channel or chat](/en-us/graph/api/chatmessage-get)
- [chats: getAllMessages](/en-us/graph/api/chats-getallmessages)

### Channel posts

Channel posts, also known as threaded conversations, are conversations that occur in a Teams channel. Microsoft documents and makes available the APIs necessary to export this data out of Teams:

- [List joinedTeams](/en-us/graph/api/user-list-joinedteams).
- [List teams](/en-us/graph/api/teams-list).
- [List Channels](/en-us/graph/api/channel-list).
- [List allChannels](/en-us/graph/api/team-list-allchannels).
- [Get Channel](/en-us/graph/api/channel-get).
- [List members of a channel](/en-us/graph/api/channel-list-members).
- [Get chatMessage in a channel or chat](/en-us/graph/api/chatmessage-get).
- [channel: getAllMessages](/en-us/graph/api/channel-getallmessages).

### Meeting recordings and transcripts

Recordings of Teams meetings and calls are stored in OneDrive or SharePoint. Microsoft documents and makes available the APIs necessary to export this data out of Teams:

- [List recordings](/en-us/graph/api/onlinemeeting-list-recordings).
- [Get callRecording](/en-us/graph/api/callrecording-get).
- [onlineMeeting: getAllRecordings](/en-us/graph/api/onlinemeeting-getallrecordings).

Note

The APIs to list and download call/meeting recordings are currently in beta.

Transcripts of Teams meetings and calls are stored in OneDrive and SharePoint. Microsoft documents and makes available the APIs necessary to export this data out of Teams:

- [List callTranscripts](/en-us/microsoftteams/platform/graph-api/meeting-transcripts/api-transcripts#list-calltranscripts).
- [Get callTranscript](/en-us/microsoftteams/platform/graph-api/meeting-transcripts/api-transcripts#get-calltranscript).
- [Get callTranscript content](/en-us/microsoftteams/platform/graph-api/meeting-transcripts/api-transcripts#get-calltranscript-content).

You can use the following APIs to get Teams meeting recordings and transcripts:

- [List available drives](/en-us/onedrive/developer/rest-api/api/drive_list).
- [Get Drive](/en-us/onedrive/developer/rest-api/api/drive_get).
- [List items shared with the signed-in user](/en-us/onedrive/developer/rest-api/api/drive_sharedwithme).
- [Download the contents of a DriveItem](/en-us/onedrive/developer/rest-api/api/driveitem_get_content).

## Support

As you start working with Microsoft Graph, check out these references to get started:

- [Get started with Microsoft Graph Toolkit](/en-us/graph/toolkit/get-started/overview).
- [Best practices for working with Microsoft Graph](/en-us/graph/best-practices-concept).
- [Export options for switching from Microsoft Teams](migration-from-teams).

Developers and admins who are working with and implementing the scenarios described in this article can obtain assistance from Microsoft and its engineers, including managed technical support, by emailing InteropHelp@microsoft.com.