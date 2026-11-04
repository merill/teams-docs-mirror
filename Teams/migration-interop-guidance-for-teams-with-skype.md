---
layout: Conceptual
title: Migration and interoperability - Skype for Business - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype
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
ms.reviewer: bjwhalen
ms.date: 2018-05-24T00:00:00.0000000Z
description: Understand the fundamental concepts for managing your organization's transition to Teams from Skype for Business.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
locale: en-us
document_id: 49921e8a-55ac-f547-d4e2-d329f5089c2e
document_version_independent_id: 91c3433a-3684-95cd-3426-4a5877b33106
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/migration-interop-guidance-for-teams-with-skype.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: migration-interop-guidance-for-teams-with-skype
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/migration-interop-guidance-for-teams-with-skype.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 8745c1e5-6d0b-382d-7f36-3b696f3db134
---

# Migration and interoperability - Skype for Business - Microsoft Teams | Microsoft Learn

Important

- After retirement of Skype for Business Online on July 31, 2021, it is no longer possible to assign a coexistence mode other than TeamsOnly to a user homed in the cloud. As was the case prior to retirement, users homed in Skype for Business Server on-premises can be assigned any mode *other than* TeamsOnly.

Coexistence modes provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams. For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any mode) at the same time. Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren't yet.

From a technical perspective, a user's mode governs several aspects of the user's experience:

- *Incoming routing*: In which client (Teams or Skype for Business) do incoming chats and calls land?
- *Presence publishing*: Is the user's presence that is shown to other users based on their activity in Teams or Skype for Business?
- *Meeting scheduling*: Which service is used for scheduling new meetings and ensuring that the proper add-in is present in Outlook? TeamsUpgradePolicy doesn't govern meeting join. Users can always *join* any meeting, whether it be a Skype for Business meeting or a Teams meeting.
- *Client experience*: What functionality is available in Teams and/or Skype for Business client? Can users initiate calls and chats in Teams, Skype for Business, or both? Is Teams & Channels experience available?

For more information on routing and presence behavior based on mode, see [Coexistence with Skype for Business](coexistence-chat-calls-presence).

However, from an experience perspective, mode can be described as defining the experience for:

- *Chat and Calling*: Which client does a user use?
- *Meeting Scheduling*: Do users schedule new meetings as Teams or Skype for Business meetings?
- *Availability of collaboration functionality in Teams client*. Is Teams & Channels and Files functionality available while users still have Skype for Business?

The modes are listed below. Cloud users must be TeamsOnly, and users homed on-premises must be any mode other than TeamsOnly. 

| Mode | Calling and Chat | Meeting Scheduling^1^ | Teams & Channels | Use Case |
| --- | --- | --- | --- | --- |
| **TeamsOnly^2^***Only possible if the user doesn't have an on-premises account in Skype for Business Server* | Teams | Teams | Yes | The final state of being upgraded. The default for new tenants, unless a hybrid configuration is detected. |
| Islands | Either | Either | Yes | Default configuration for hybrid organizations. Allows a single user to evaluate both clients' side by side. Chats and calls can land in either client, so users must always run both clients. To avoid a confusing or regressed Skype for Business experience, external (federated) communications, PSTN voice services and voice applications, Office integration, and several other integrations continue to be handled by Skype for Business. |
| SfBWithTeamsCollabAndMeetings^2^ | Skype for Business | Teams | Yes | "Meetings First." Primarily for on-premises organizations to benefit from Teams meeting functionality, if they aren't yet ready to move calling to the cloud. |
| SfBWithTeamsCollab | Skype for Business | Skype for Business | Yes | Alternate starting point for complex organizations that need tighter administrative control. |
| SfBOnly | Skype for Business | Skype for Business | No^3^ | Specialized scenario for organizations with strict requirements around data control. Teams is used only to join meetings scheduled by others. |
|  |  |  |  |  |

**Notes:**

^1^ The ability to join an existing meeting (whether scheduled in Teams or in Skype for Business) isn't governed by mode. By default, users can always join any meeting they are invited to.

^2^ By default, when assigning either TeamsOnly or SfbWithTeamsCollabAndMeetings to an individual user, any existing Skype for Business meetings scheduled by that user for the future are converted to Teams meetings. If desired, you can leave these meetings as Skype for Business meetings either by specifying `-MigrateMeetingsToTeams $false` when granting TeamsUpgradePolicy, or by unselecting the checkbox in the Teams Admin portal. The ability to convert meetings from Skype for Business to Teams is not available when granting TeamsUpgradePolicy on a tenant-wide basis.

^3^ Currently, Teams doesn't have the ability to disable the Teams and Channels functionality so this remains enabled for now.

## Using TeamsUpgradePolicy

TeamsUpgradePolicy exposes two key properties: Mode and NotifySfbUsers. 

| Parameter | Type | Allowed values(default in italics) | Description |
| --- | --- | --- | --- |
| Mode | Enum | *Islands*TeamsOnlySfBOnlySfBWithTeamsCollabSfBWithTeamsCollabAndMeetings | Indicates the mode the client should run in. |
| NotifySfbUsers | Bool | *False* or true | Indicates whether to show a banner in the Skype for Business client informing the user that Teams will soon replace Skype for Business. This can't be true if Mode=TeamsOnly. |
|  |  |  |  |

Teams provides all relevant instances of TeamsUpgradePolicy via built-in, read-only policies. Therefore, only Get and Grant cmdlets are available. The built-in instances are listed below. 

| Identity | Mode | NotifySfbUsers |
| --- | --- | --- |
| Islands | Islands | False |
| IslandsWithNotify | Islands | True |
| SfBOnly | SfBOnly | False |
| SfBOnlyWithNotify | SfBOnly | True |
| SfBWithTeamsCollab | SfBWithTeamsCollab | False |
| SfBWithTeamsCollabWithNotify | SfBWithTeamsCollab | True |
| SfBWithTeamsCollabAndMeetings | SfBWithTeamsCollabAndMeetings | False |
| SfBWithTeamsCollabAndMeetingsWithNotify | SfBWithTeamsCollabAndMeetings | True |
| UpgradeToTeams | TeamsOnly | False |
| Global*Default* | Islands | False |
|  |  |  |

These policy instances can be granted either to individual users or on a tenant-wide basis. For example:

- To upgrade a user ($SipAddress) to Teams, grant the "UpgradeToTeams" instance:`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- To upgrade the entire tenant, omit the identity parameter from the grant command:`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## The Teams client user experience when using Skype for Business modes

When a user is in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), all incoming chats and calls are routed to the user's Skype for Business client. To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is automatically disabled when a user is in any of the Skype for Business modes. Similarly, meeting scheduling in Teams is automatically disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and automatically enabled when a user is in the SfBWithTeamsCollabAndMeetings mode. For details, see [Teams client experience and conformance to coexistence modes](teams-client-experience-and-conformance-to-coexistence-modes).

Note

- Prior to delivery of the automatic enforcement of Teams and Channels, the SfbOnly and SfBWithTeamsCollab modes behave the same.

## Detailed mode descriptions

| Mode | Explanation |
| --- | --- |
| **Islands**(on-premises only) | A user runs both Skype for Business and Teams side by side. This user:<br>- Can initiate chats and VoIP calls in either Skype for Business or Teams client. Note: Users with Skype for Business homed on-premises can't initiate from Teams to reach another Skype for Business user, regardless of the recipient's mode.<br>- Receives chats & VoIP calls initiated in Skype for Business by another user in their Skype for Business client.<br>- Receives chats & VoIP calls initiated in Teams by another user in their Teams client if they are in the *same tenant*.<br>- Receives chats & VoIP calls initiated in Teams by another user in their Skype for Business client if they are in a *federated tenant*.<br>- Has PSTN functionality as noted below:<br>    - When the user is homed in Skype for Business on-premises and has Enterprise Voice, PSTN calls are always initiated and received in Skype for Business.<br>    - When the user is homed on Skype for Business Online and has Microsoft Phone System, the user always initiates and receives PSTN calls in Skype for Business:<br>        - This happens whether the user has a Microsoft Calling Plan, or connects to the PSTN network through either Skype for Business Cloud Connector Edition or an on-premises deployment of Skype for Business Server (hybrid voice).<br>        - **Note: Phone System Direct Routing is not supported in Islands mode.**<br>- Receives Microsoft Call Queues and Auto-Attendant calls in Skype for Business:<br>    - Phone numbers assigned to Call Queues and Auto-Attendants **cannot** be Phone System Direct Routing numbers in Islands mode.<br><br>- Can schedule meetings in Teams or Skype for Business (and will see both plug-ins by default).<br>- Can join any Skype for Business or Teams meeting; the meeting will open in the respective client. |
| **SfBOnly**(on-premises only) | A user runs only Skype for Business. This user:<br>- Can initiate chats and calls from Skype for Business only.<br>- Receives any chat/call in their Skype for Business client, regardless of where initiated, unless the initiator is a Teams user with Skype for Business homed on-premises.\*<br>- Can schedule only Skype for Business meetings, but can join Skype for Business or Teams meetings.\**Using Islands mode with on-premises users isn't recommended in combination with other users in SfBOnly mode. If a Teams user with Skype for Business homed on-premises initiates a call or chat to a SfBOnly user, the SfBOnly user isn't reachable and receives a missed chat or call email.* |
| **SfBWithTeamsCollab**(on-premises only) | A user runs both Skype for Business and Teams side by side. This user:<br>- Has the functionality of a user in SfBOnly mode.<br>- Has Teams enabled only for group collaboration (Channels); chat/calling/meeting scheduling are disabled. |
| **SfBWithTeamsCollabAndMeetings**(on-premises only) | A user runs both Skype for Business and Teams side by side. This user:<br>- Has the chat and calling functionality of user in SfBOnly mode.<br>- Has Teams enabled for group collaboration (channels - includes channel conversations); chat and calling are disabled.<br>- Can schedule only Teams meetings, but can join Skype for Business or Teams meetings. |
| **TeamsOnly**(cloud users only) | A user runs only Teams. This user:<br>- Receives any chats and calls in their Teams client, regardless of where initiated.<br>- Can initiate chats and calls from Teams only.<br>- Can schedule meetings in Teams only, but can join Skype for Business or Teams meetings.<br>- Can continue to use Skype for Business IP phones.*Using TeamsOnly mode in combination with other users in Islands mode isn't recommended until Teams adoption is saturated; that is, all Islands mode users actively use and monitor both the Teams and Skype for Business clients. If a TeamsOnly user initiates a call or chat to an Islands user, that call or chat lands in the Islands user's Teams client; if the Islands user doesn't use or monitor Teams, that user appears offline and will not be reachable by the TeamsOnly user.*<br>- In some cases, participants in TeamsOnly mode will only be able to join Skype for Business meetings using Skype for Business Web App or Skype Meetings App as an anonymous user. Eventually, this case will be true for all users in TeamsOnly mode. For more information, see [Skype for Business Online retirement](skype-for-business-online-retirement#what-to-expect-post-retirement). |
|  |  |