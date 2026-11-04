---
layout: Conceptual
title: Plan for live events in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-live-events/plan-for-teams-live-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.reviewer: christi.balaki,cmunden
ms.date: 2024-10-03T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: In this article, learn about the factors to consider before you set up live events in Microsoft Teams.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 2b679199-caa5-4cc5-27e5-60a2cf999f69
document_version_independent_id: 6878c954-e248-94c2-7602-47437ec7a2dd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-live-events/plan-for-teams-live-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-live-events/plan-for-teams-live-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-live-events/plan-for-teams-live-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d5864eeb-9112-46cf-118f-d63995020abf
---

# Plan for live events in Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

When you're planning Teams live events to hold large meetings in your organization, there are several factors that you need to consider before starting the setup.

Note

For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network) to learn about bandwidth requirements for Teams live events.

The Teams client doesn't support Teams live events on Surface hub devices. Users can only join the events as viewers using the Edge web browser on their Surface hub devices.

## Who can attend, create, and schedule live events

Anyone can attend a live event without a license. For details, see [Admin quick start - Meetings and live events](../quick-start-meetings-live-events).

## Prerequisites

The following prerequisites are required for users to schedule a Teams live event.

### Licensing

You must assign these licenses to allow users in your org to organize, produce, or present a Teams live event:

- **To organize:** A Microsoft or Office 365 Enterprise E1, E3, or E5 license, **[or]** a Microsoft or Office 365 Education A3 or A5 license.
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3, or A5 license. The exception to this requirement is guests can present without a license if the other criteria for guests in the Allow guests to present section are met.
- A Microsoft Teams license - this license is included in the licenses listed in the first and second bullets.

Note

Currently, Microsoft 365 Small Business plans can't create and hold Teams live events.

To participate in a live event as an authenticated user, a Microsoft 365 or Office 365 license is required. This requirement depends on the production method used:

- **For events produced in Teams or using a Teams Powered Encoder** The user must be assigned a Teams license.

Note

Teams live events is now available for US Government Cloud Community (GCC) organizations.

For more information about licensing, see [Microsoft Teams add-on licensing](../teams-add-on-licensing/microsoft-teams-add-on-licensing).

### Policies

For the full live event experience, users must have:

- Private meeting scheduling in Teams enabled (*The [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy)**`-AllowPrivateMeetingScheduling`** parameter = True*).
- Video sharing enabled in Teams meetings (*The [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy)**`-AllowIPVideo`** parameter = True*).
- Screen sharing enabled in Teams meetings (*The [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy)**`-ScreenSharingMode`** parameter = EntireScreen*).
- Live event scheduling in Teams enabled (*The [**CsTeamsMeetingBroadcastPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingbroadcastpolicy)**`-AllowBroadcastScheduling`** parameter = True*).
- [Coexistence mode](/en-us/microsoftteams/setting-your-coexistence-and-upgrade-settings) configured to be able to schedule Teams meetings (*Islands, Meeting First, or Teams Only*).

Important

Non-authenticated anonymous users can't be invited as producers or presenters in Teams live events.

## Allow guests to present

For a guest to present in a live event, do the following tasks:

1. [Add the user as a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Have the user accept the guest invitation and join the team.
3. [Schedule the live event and add the guest to your event group](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials can't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## Who can watch live events

| Attendee visibility | Teams production | External app or device production | Teams Powered Encoder |
| --- | --- | --- | --- |
| Public (anonymous users) | Yes | No | Yes |
| Guests | Yes^1^ | No | Yes |
| People in external access trusted organizations | Yes^1^ | No | Yes |
| Everyone in the organization | Yes | Yes | Yes |
| Specific groups or people | Yes | Yes | Yes |

^1^ Can only be invited through People & Group. 

## Teams live events

The following table highlights core capabilities and features offered in live events.

| Capability | Events produced in Teams | Events produced in external app or device |
| --- | --- | --- |
| Maximum audience size | 10,000 attendees^1^ | 10,000 attendees^1^ |
| Maximum duration of live event | four hours | four hours |
| Maximum number of presenters and producers in a live event | 10 ^2^ | 10 ^2^ |
| Maximum number of concurrent live events per Microsoft 365 or Office 365 organization | 15 | 15 |
| Live event creation | Teams, Viva Engage via Teams | Teams, Viva Engage via Teams, Stream |
| Audience engagement – Viva Engage | ✔ (integrated experience) | ✔ (integrated experience) |
| Audience engagement – Moderated Q & A | ✔ | ✔ |
| Producer client on Windows | ✔ (Teams) | ✔ (Stream, Teams via Stream Embed) |
| Producer client on Mac | ✔ (Teams) | ✔ (Stream, Teams via Stream Embed) |
| Attendee count in Producer UI | ✔ (Teams) | ✔ (Stream, Teams via Stream Embed) |
| Allows multiple presenters | ✔ (Teams) | N/A |
| Invite a presenter during the meeting | ❌ | N/A |
| Presenter join on Web and Mobile | ❌ | N/A |
| External access & guest presenters/attendees | ✔ (Teams) | N/A |
| Presenter – PSTN access | ✔ (Teams) | N/A |
| Present a screen | ✔ (Teams) | N/A |
| Share system audio on Windows (available only when screen sharing) | ✔ (Teams) | ✔ |
| Present a PowerPoint (PPT sharing) | ❌ (mitigated via screen sharing) | N/A |
| Cloud based meeting recording | ✔ | ✔ |
| Auto publish recording to Stream | ❌ | ✔ |
| Live captions and subtitles | ✔ | ❌ |
| Captions in live event recordings | ✔ | ✔ |
| Attendee DVR controls (pause, rewind) | ✔ | ✔ |
| Microsoft eCDN | ✔ | ✔ |
| Partner eCDN Support | ✔ (Hive, Kollective, Ramp) | ✔ (Hive, Kollective, Ramp) |
| Post-broadcast attendance report for Producers | ✔ | ❌ |
| Audience Sentiment Analysis – Live voting & polls | ❌ | ❌ |

^1^ The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams).^2^ You can have up to 100 presenters and producers in a live event, but only the last 10 who spoke show up in the list.

## Regional availability

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

Important

The region for the event is automatically selected depending on the organizer and the Microsoft 365 tenant location.

### Live events are available in the following regional data centers

- North America
- Asia Pacific
- Europe/Africa

### Data location for the following countries/regions is supported

- Australia
- Canada
- France
- Germany
- India
- Japan
- Norway
- Poland
- Singapore
- Sweden
- Switzerland
- United Kingdom

#### Exclusions and considerations

- **Data location:** Teams data locations, outside of the ones listed, aren't currently supported.