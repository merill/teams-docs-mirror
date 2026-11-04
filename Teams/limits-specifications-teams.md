---
layout: Conceptual
title: Limits and specifications for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/limits-specifications-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: reference
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: siunies
ms.date: 2026-07-16T00:00:00.0000000Z
description: This article describes the limits, specifications, and other requirements that apply to Microsoft Teams.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 905e2c09-ef3e-07cc-0809-6ff171157c47
document_version_independent_id: c0d33162-183d-fff8-32e9-a999f391ea51
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/limits-specifications-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: limits-specifications-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/limits-specifications-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 8b184768-29c4-38d4-6110-90f7b8cd5a80
---

# Limits and specifications for Microsoft Teams - Microsoft Teams | Microsoft Learn

This article describes some of the limits, specifications, and other requirements that apply to Teams.

## Teams and channels

| Feature | Maximum limit |
| --- | --- |
| Number of teams a user can create | Subject to a 250 object limit¹ |
| Number of teams a user can be a member of | 1,000² |
| Number of members in a team | 25,000^7^ |
| Number of owners per team | 100 |
| Number of org-wide teams allowed in a tenant | 5² |
| Number of members in an [org-wide team](/en-us/microsoftteams/create-an-org-wide-team) | 10,000 |
| Number of teams a global admin can create | 500,000 |
| Number of teams a Microsoft 365 or Office 365 organization can have | 500,000³ |
| Number of channels per team | 1,000 (includes deleted channels)^4,8^ |
| Number of Private channels per team | Included into the overall support limit of 1,000 (includes deleted channels)^4^ |
| Number of members in a Private channel | 5000 |
| Maximum size of distribution list, security group, or Microsoft 365 group that can be imported in to a team | 3,500 |
| Maximum number of members in a Microsoft 365 group that can be converted to a team | 10,000^7^ |
| Channel conversation post size | Approximately 100 KB per post^5,6^ |

^1^ Any directory object in Microsoft Entra ID counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/en-us/graph/permissions-reference).

^2^ This limit includes archived teams.

^3^ To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Microsoft Entra objects in your tenant. Increase is only made for real-life production scenarios.

^4^ Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 1,000 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts toward the per-team limit.

^5^ 100 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.

^6^ 100 KB size limitation doesn't include base64 encoded image.

^7^ Shared channels members from outside the team count toward this limit. Further note that teams/channel mentions are blocked in teams with over 10,000 members.

^8^ Any combination of standard, private and shared channels for a total of 1,000 channels per team.

### Limits for shared channels

The following table describes the maximum number of channels and members.

| Maximum... | Value | Notes |
| --- | --- | --- |
| Members in a team | 25,000 | Includes all users in the team and direct members in shared channels. |
| Shared channels per team | up to 1,000 | Hosted and shared with the team. (Includes deleted channels during their 30-day recovery window.) |
| Teams a channel can be shared with | 50 | Excluding parent team |
| Members in a shared channel | 5,000 direct members, including up to 50 teams. (Each team the channel is shared with counts as one member for purposes of this limit.) | Real time updates are only available to 25,000 users at a time and only 25,000 users appear in the channel list. |

The following limitations also apply:

- Only Microsoft Entra work or school accounts are supported for external participants.
- Shared channels support tabs except for Stream, Planner, and Forms.
- Bots, connectors, and message extensions aren't supported.
- Org-wide teams aren't supported to be added as members of a shared channel.
- When you create a team from an existing team, any shared channels in the existing team aren't copied over.
- Notifications from shared channels aren't included in missed activity emails.
- Shared channels aren't supported in class teams.

## Messaging

### Chat

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin can't search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](/en-us/microsoftteams/exchange-teams-interact).)

| Feature | Maximum limit |
| --- | --- |
| Number of people in a private chat^1^ | 250^2^ |
| Number of people in a video or audio call from chat | 20 |
| Number of file attachments^3^ | 10 |
| File size limitation | 100 MB |
| Chat size | Approximately 100 KB per post^4,5,6^ |

^1^ If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

^2^ Only 200 members can be added to a group chat at the same time.

^3^ If the number of attachments exceeds this limit, you see an error message.

^4^ 100 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.

^5^ 100 KB size limitation doesn't include base64 encoded image.

^6^ During implementation, it's recommended to ensure that the size of the message itself is within 80 KB to guarantee successful message delivery.

#### External messaging limits

Tenants on trial subscriptions are subject to stricter outbound external messaging limits to help prevent abuse. Limits may be adjusted without notice.

Organizations that use only the default Microsoft Online Email Routing Address (MOERA) domain (for example, contoso.onmicrosoft.com) are also subject to outbound external messaging limits. These limits help protect Teams users from spam, phishing, and other abusive activity. When a limit is reached, users might be temporarily unable to send messages to external users. Internal messaging isn't affected, and external messaging automatically resumes when activity falls below the applicable limit. For production use, Microsoft recommends adding and configuring a custom domain for your organization. For more information, see [Add a custom domain to Microsoft 365](/en-us/microsoft-365/admin/setup/add-domain).

### External access

Administrators allowing only trusted domains for external access are limited to adding a maximum of 4,000 trusted domains. For more information, see [Manage external meetings and chat with people and organizations using Microsoft identities](/en-us/microsoftteams/trusted-organizations-external-meetings-chat).

### Emailing a channel

If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

| Feature | Maximum limit |
| --- | --- |
| Message size^1^ | 24 KB |
| Number of file attachments^2^ | 20 |
| Size of each file attachment | Less than 10 MB |
| Number of inline images^2^ | 50 |

Note

There's a throttling limit on how many emails you can send to a channel. The limit is 6 emails per 10 seconds per channel per user and 8 emails per 10 seconds per tenant per user. Additionally, rate limits for Teams connectors are applied, for more information see [Rate limiting for connectors](/en-us/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-using?tabs=cURL%2Ctext1#rate-limiting-for-connectors).

^1^ If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.^2^ If the number of attachments or images exceeds this limit, you see an error message.

For more information, see [Exchange Online limits](/en-us/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

Note

Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel isn't available in Teams for Office GCC/GCCH/DOD organizations.

## Channel names

Channel names can't contain the following characters or words:

| Type | Example |
| --- | --- |
| Characters | ~ # % & \* { } + / \ : &lt; &gt; ? | ' " , .. |
| Characters in these ranges | 0 to 1F80 to 9F |
| Words | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini, \_vti\_ |

Channel names also can't start with an underscore (\_) or period (.), or end with a period (.).

## Meetings and calls

| Feature | Maximum limit |
| --- | --- |
| Number of people in a meeting (can chat and call in) | With Microsoft 365 Business Basic, Microsoft 365 Business Standard, Microsoft 365 Business Premium, Microsoft Teams Essentials, and Microsoft 365 A1 plans, you can host online meetings and video calls for up to 300 people using Microsoft Teams. With Microsoft 365 F1/F3/E3/E5/A3/A5/G3/G5, Office 365 E1/E3/E5/A3/A5/G1/G3/G5, and Microsoft Teams EEA plans, this limit increases up to 1,000 people. |
| Number of people in a video or audio call from chat | 20 |
| Max PowerPoint File Size | 2 GB |
| Teams keeps [meeting recordings](/en-us/microsoftteams/meeting-recording) that don't get uploaded to Microsoft Stream, available for local download | 20 days |
| Meeting recording maximum length | 4 hours or 1.5 GB. When this limit is reached, the recording ends and automatically restarts. |

For more information, see [Overview of meetings and events in Microsoft Teams](overview-meetings-events).

Note

Breakout rooms can only be created in meetings or events with up to 1,000 attendees. Breakout rooms aren't supported in events [optimized for large audiences](plan-events). Additionally, creating breakout rooms in a meeting or event automatically limits the number of attendees to 1,000. For more information about large Teams meetings and events, share the [Tips for setting up large meetings and events in Microsoft Teams](https://support.microsoft.com/teams/meetings/tips-for-setting-up-large-meetings-and-events-in-microsoft-teams) guidance with your end users.

### Meeting expiration

The expiration applies to PSTN dial-in numbers, CVI coordinates, and underlying meeting policies and settings.

When a meeting is joined or updated before its expiration limit, an extra 60 days are added to the expiration limit (except for Meet now meetings).

(**Public preview**) Newly created links and meetings expire according to the conditions outlined in the following table. When these meetings expire, users can't join using the link.

| Meeting type | Time until meeting expiration |
| --- | --- |
| Scheduled meeting (one time) | 60 days after meeting scheduled time |
| Meet now (scheduled via calendar or channels) | 60 days after the link was created |
| Meet now (scheduled via group chats) | N/A |
| Recurrent meetings with end date | 60 days from end date or 60 days from last occurrence, whichever is longer |
| Recurrent meeting with no end date | 1 year after the last access, joined, or meeting updated |

Note

Microsoft Teams meetings and events (such as webinars and town halls) have a time limit of 30 hours.

## Live events

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

[Live events](/en-us/microsoftteams/teams-live-events/what-are-teams-live-events) are structured meetings that enable your organization to schedule and produce events that stream to large online audiences—up to 10,000 people. With live events, the audience interaction is a managed Q&A experience.

| Feature | Maximum limit |
| --- | --- |
| Audience size | Up to 10,000 attendees |
| Duration of event | 4 hours |
| Concurrent live events running in a Microsoft 365 or Office 365 organization ^1^ | 15 |

^1^ You can schedule as many live events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.

For more information about live events, go to [Teams live events](/en-us/microsoftteams/teams-live-events/plan-for-teams-live-events#teams-live-events). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-live-event-in-microsoft-teams-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

## Presence in Outlook

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](/en-us/microsoftteams/presence-admins).

## Storage

Each team in Microsoft Teams has a team site in SharePoint, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

Note

Each [private channel](/en-us/microsoftteams/private-channels) has its own SharePoint site (previously called "site collection").

If you don't have SharePoint enabled in your tenant, Microsoft Teams users can't always share files in teams. Users in private chat also can't share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint document library and OneDrive for Business, all compliance rules configured at the tenant level are followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](/en-us/sharepoint/teams-connected-sites).)

Because Teams runs on a SharePoint backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint.

| Feature | Microsoft 365 Business Basic | Microsoft 365 Business Standard | Office 365 Enterprise E1 | Office 365 Enterprise E3 | Office 365 Enterprise E5 | Office 365 Enterprise F1 |
| --- | --- | --- | --- | --- | --- | --- |
| Storage | 1 TB per organization plus 10 GB per license purchased | 1 TB per organization plus 10 GB per license purchased | 1 TB per organization plus 10 GB per license purchased | 1 TB per organization plus 10 GB per license purchased | 1 TB per organization plus 10 GB per license purchased | 1 TB per organization |
| Storage for Teams Files | Up to 25 TB per site or group | Up to 25 TB per site or group | Up to 25 TB per site or group | Up to 25 TB per site or group | Up to 25 TB per site or group | Up to 25 TB per site or group |
| File upload limit (per file) | 250 GB | 250 GB | 250 GB | 250 GB | 250 GB | 250 GB |

Channels are backed by folders within the SharePoint site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.

For more information, see [SharePoint limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## Class teams

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

A class team is a template type with more apps included, and with limits separate to the number of team members.

Note

Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).

Limits for class teams are listed in the following table:

| Feature | Maximum limit |
| --- | --- |
| Number of members in a team | See the Teams and channels section of this article |
| Number of members to use Assignments in a class team | 1000 |
| Number of members to use a OneNote Class Notebook in a class team | 300 |

A class team can support more members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you need to keep the number of members below the maximum limits above.

## Tags

| Feature | Maximum limit |
| --- | --- |
| Number of tags per team | 200 |
| Number of suggested default tags per team | 25 |
| Number of team members assigned to a tag | 200 |
| Number of tags assigned to a user per team | 25 |

## Contacts

Teams uses these contacts:

- Contacts in your organization's Active Directory
- Contacts added to the user's Outlook default folder

Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** &gt; **Contacts** or **Calls** &gt; **Contacts**.

Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** &gt; **Contacts**.

## Browsers

Teams fully supports the following Internet browsers, with noted exceptions for calling and meetings. This table applies to operating systems running on desktop computers.

| Browser | Calling - audio, video, and sharing | Meetings - audio, video, and sharing^1^^2^ |
| --- | --- | --- |
| Internet Explorer 11 | Not supported | Meetings are supported only if the meeting includes PSTN coordinates. To attend a meeting on IE11 without PSTN coordinates, users must download the Teams desktop client.Video: Not supported.Sharing: Incoming sharing only (no outgoing).  Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting November 30, 2020). [Learn more](https://www.microsoft.com/edge/business). Please note that Internet Explorer 11 will remain a supported browser. Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/en-us/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is installed. |
| Microsoft Edge, RS2 or later | Fully supported, except no outgoing sharing.^3^ | Fully supported, except no outgoing sharing. |
| Microsoft Edge (Chromium-based), the latest version plus two previous versions | Fully supported. | Fully supported. |
| Google Chrome, the latest version plus two previous versions | Fully supported. | Fully supported. Sharing is supported without any plug-ins or extensions on Chrome version 72 or later. |
| Safari 15+ | 1:1 calls fully supported. | Classic Teams may experience issues in some circumstances.^4^ |
| Safari 14+ | 1:1 calls not supported. Group calls fully supported.Video: Fully supported.Sharing: Fully supported. | Meetings: Fully supported.Video: Fully supported.Sharing: Fully supported.Classic Teams may experience issues in some circumstances.^4^ |
| Safari 13.1+ | 1:1 calls not supported. Group calls supported with full audio support.Video: Incoming only.Sharing: Fully supported. | Meetings are supported with full audio support.Video: Incoming only.Sharing: Fully supported.Classic Teams may experience issues in some circumstances.^4^ |
| Firefox, the latest version plus two previous versions | Not supported. | Meetings: Fully supported.Video: Fully supported.Sharing: Fully supported.Note that users are required to have the OpenH264 plugin in Firefox for full support. Browsers without this plugin may see disruptions in the meeting, including in screen sharing activity. Learn more at [Mozilla Firefox Support](https://support.mozilla.org/kb/open-h264-plugin-firefox). |
| Safari versions before 13 | Not supported. | Meetings are supported only if the meeting includes PSTN coordinates. To attend a meeting on Safari without PSTN coordinates, users must download the Teams desktop client.Video: Not supported.Sharing: Incoming sharing only (no outgoing).Safari is enabled on versions higher than 11.1 in preview. While in preview, there are [known issues](https://support.office.com/article/safari-browser-support-1aac0a7c-35a8-42c1-a7df-f674afe234df) with Safari's Intelligent Tracking Prevention. |

^1^ To [give and take control of shared content during sharing](meeting-who-present-request-control), both parties must be using the Teams desktop client. Control isn't supported when either party is running Teams in a browser. This is due to a technical limitation that we're planning to fix.

^2^ Teams meetings on browsers are limited to a single stream; either incoming video feed of the current speaker or screen sharing.

^3^ Edge RS2 or later doesn't support sending real-time audio and video traffic through HTTP proxies.

^4^ Classic Teams users may experience delayed chat messages, including one-on-one chats, group chats, or channel posts while using Safari Browser.

Note

Running Teams in a browser is supported on PCs and Macs that meet the minimum [Teams client system requirements](teams-client-system-requirements). For example, running Firefox on the Linux operating system is an option for using Teams.

On mobile devices we recommend that you use the Teams app. The Teams app is available from the Android and iOS stores.

## Operating systems

For information about operating system requirements, see [Teams client system requirements](/en-us/microsoftteams/teams-client-system-requirements).