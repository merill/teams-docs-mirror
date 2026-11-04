---
layout: Conceptual
title: Plan for Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/plan-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.date: 2026-07-10T00:00:00.0000000Z
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.reviewer: absri,chbalaki,preethir
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-events
audience: admin
f1.keywords:
- NOCSH
search.appverid: MET150
description: Admin guidance for Teams events. Get an overview of Teams events, including planning considerations, policy controls, and guidance to help prepare for events in your organization..
locale: en-us
document_id: 01169806-ed52-75a5-78b2-de3d0fd10cc3
document_version_independent_id: 01169806-ed52-75a5-78b2-de3d0fd10cc3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/plan-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: plan-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/plan-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c4b91c59-4609-b040-09cb-f3ee4bbd71da
---

# Plan for Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

## Overview

Teams events support a range of structured communication experiences, from interactive sessions to broadcast-style events for large audiences.

This article provides admins with an overview of Teams events, including planning considerations, policy controls, and guidance to help prepare for events in your organization.

## Understanding Teams events

### Licensing and capacity for Teams events

With Teams Enterprise, organizers can:

- Host events for up to 1,000 attendees with the following engagement capabilities: attendee microphone and camera, interactive chat, reactions, raise hand, polls, and Q&A.
- Host events for up to 3,000 attendees with the following engagement capabilities: meeting chat for large events, reactions, raise hand, polls, and Q&A.
- Host events for up to 10,000 attendees in a view-only experience, with Q&A.

With an [Attendee Capacity Pack](teams-add-on-licensing/attendee-capacity-pack) add-on license, organizers can scale events up to 100,000 attendees. To learn more about licensing for Teams events, see [Teams events licensing overview](events-licensing).

The availability of some features depends on event capacity. For more information, see [Event features at scale](meetings-events-feature-comparison#event-features-at-scale).

Note

We recommend using [Teams Events Services](https://adoption.microsoft.com/virtual-event-guidance/assistance) for events with more than 20,000 attendees.

### The Events app

The Events app (formerly the Meet app) in Teams provides a centralized way for users in your organization to create, discover, and manage digital and hybrid events. The app is preinstalled for all Teams users.

Organizers use a unified creation flow to configure event settings—such as registration and attendee interaction—based on event capacity and scenario, rather than selecting a fixed event type. This approach replaces preset configurations tied to specific event types and provides a consistent, flexible experience that enables organizers to tailor events to their audience and goals. To learn more, see [Get started with the Microsoft Teams Events app](https://support.microsoft.com/teams/meetings-events/get-started-with-events-app).

[![Screenshot of the Create page in the Events app in Teams](media/plan-events-create-event.png)](media/plan-events-create-event.png#lightbox)

Existing Teams webinar and town hall policies continue to apply, so admins can control who can create events and which capabilities organizers can use without adopting a new policy model. When allowed by policy, organizers can create events from scratch and configure options for their scenario or use prebuilt webinar or town hall templates. Interactive events up to 1,000 attendees use webinar policy settings, while events optimized for large audiences use town hall policy settings.

### Optimize for large audience in Teams events

The event scheduling form and templates in the Events app include the **Optimize for large audience** option. This option optimizes an event for broadcast-style delivery to support large audiences.

When **Optimize for large audience** is on, the event respects all town hall settings in Teams events policy ([CsTeamsEventsPolicy](/en-us/powershell/module/microsoftteams/set-csteamseventspolicy)).

[![Screenshot of the Set up experience and options section of the event scheduling form, showing the Optimize for large audience option.](media/plan-events-scheduling-form.png)](media/plan-events-scheduling-form.png#lightbox)

Organizers have the following experience when they create events:

- For events with *up to* 1,000 attendees, **Optimize for large audience** is off, and organizers can choose to turn it on.
- For events with *more than* 1,000 attendees, **Optimize for large audience** is on and can't be turned off.

For more information about how policy settings work with **Optimize for large audience**, see [Manage who can schedule and attend events in Microsoft Teams](set-up-events).

#### Event experience based on Optimize for large audience

When **Optimize for large audience** is on, the event uses town hall policy settings. Some attendee features are limited or adjusted and settings are applied to support large-scale delivery. For example, attendees can't turn on their microphones and cameras on demand, and attendees view the event at a slight delay and can pause and rewind the live video. Attendees also use an enterprise content delivery network (eCDN), if applicable.

When **Optimize for large audience** is off, the event uses webinar policy settings and supports a more interactive experience. Attendees can use features such as microphone, camera, and interactive chat.

Keep in mind that the town hall template uses town hall policy settings unless **Optimize for large audience** is turned off, and the webinar template uses webinar policy settings, unless **Optimize for large audience** is turned on.

For a list of features available in events with up to 1,000 attendees and in events optimized for large audiences, see [Meetings and events feature comparison](meetings-events-feature-comparison).

Note

Customers in China currently can't create Teams events optimized for large audiences, such as town halls. They can join events optimized for large audiences hosted in a tenant outside of China if they're added as a guest account (the recommended approach for authenticated participation) or anonymously if the organizer enables anonymous access.

### Understand your policies

Teams events are managed through a combination of Teams meeting policies ([CsTeamsMeetingPolicy](/en-us/powershell/module/microsoftteams/set-csteamsmeetingpolicy)), Teams events policies ([CsTeamsEventsPolicy](/en-us/powershell/module/microsoftteams/set-csteamseventspolicy)), and organizer and attendee settings. Meeting policies control core capabilities that apply across meetings and events, while events policies control event-specific capabilities. Organizer settings further define the experience for events within the boundaries set by admin policies.

- For a high-level overview of policy management for Teams meetings and events, see [Manage meeting and event policies in Microsoft Teams](meeting-policies-overview).
- For a list of admin policies and organizer settings for events, see Admin and organizer policy and setting controls later in this article.

## Plan and configure

### Decide who can attend events that organizers create

You control whether organizers can schedule public events that everyone can attend or in-org events that only people in your organization can attend.

Some key differences exist between in-org events and public events. Consider the following information when you [manage who can attend events](set-up-events#manage-who-can-attend-events).

# [Events up to 1,000 attendees](#tab/events-up-to-1000-attendees)
| Capability | In-org event | Public event |
| --- | --- | --- |
| Includes guests | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Members of the organization that created the event can join | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Anyone with a registration link can join | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Anonymous users can register | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees type their name on the registration form when registering | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees must reenter their information after selecting the join link | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees have unique join links | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Organizers can decide whether attendees with a registration link can bypass the lobby | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Organizers can decide whether anyone who can't bypass the lobby is automatically rejected | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees can dial in to join | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) |
| Includes external presenters | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |

# [Events optimized for large audiences](#tab/events-optimized-for-large-audiences)
| Capability | In-org event | Public event |
| --- | --- | --- |
| Includes guests | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Members of the organization that created the event can join | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Anyone with a registration link can join | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Anonymous users can register | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees type their name on the registration form when registering | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees must reenter their information after selecting the join link | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees have unique join links | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |
| Attendees can dial in to join | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) | ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) |
| Includes external presenters | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) | ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) |

---

### Get your network ready for events optimized for large audiences

Follow these steps to ensure your network is set up to support events optimized for large audiences.

1. **Ensure your Teams environment is set up to connect to our services** Ensure that your network connectivity to Microsoft 365 follows the network connectivity principles outlined in [Microsoft 365 network connectivity principles](/en-us/microsoft-365/enterprise/microsoft-365-network-connectivity-principles). The network connectivity principles are standard principles to follow for all Microsoft 365 services, and not just specific to Teams events.
2. **Ensure your devices are optimized to connect to our services** As part of the network connectivity principles, ensure that the Microsoft 365 endpoints are reachable as defined in [Microsoft 365 endpoints](/en-us/microsoft-365/enterprise/microsoft-365-endpoints).
3. **Understand special considerations for events in VPN environments** If your organization uses VPN connectivity for remote participants, review the guidance in [Special considerations for Teams events in VPN environments](/en-us/microsoft-365/enterprise/microsoft-365-vpn-stream-and-live-events). This article details how to optimize the attendee traffic for direct connectivity (also known as split tunneling) to the service.
4. **Plan for bandwidth considerations for events** Follow the bandwidth requirements documented in [Prepare your organization's network for Teams](/en-us/MicrosoftTeams/prepare-network#bandwidth-requirements) for your organizers, co-organizers, and presenters. Without an enterprise content delivery Network (eCDN), bandwidth requirements can be approximated at 2 Mbps per viewer at each location. (Update to 3 Mbps for 1080p). For physical locations with a high number of attendees or dense network environments, we recommend implementing an eCDN solution to optimize bandwidth usage and ensure a smooth streaming experience.
5. **Optimize your internal network via eCDN** An eCDN takes the video content from the internet and distributes the content throughout your enterprise without affecting network performance.By default, Microsoft eCDN is enabled for organizers of events optimized for large audiences. You can also select from one of the following certified eCDN partner solutions to optimize your network for events held within your organization:
    - [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
    - [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
    - [Ramp](https://rampecdn.com/) To turn off Microsoft eCDN for organizers and to learn more about our partner solutions, see [Enterprise content delivery networks for streaming Microsoft Teams events](streaming-ecdn-enterprise-content-delivery-network). For more information about Microsoft eCDN, see [Introduction to Microsoft eCDN](/en-us/ecdn/intro).
6. **Perform a silent test** Before large-scale events, we recommend performing a silent test to evaluate network performance and identify potential bottlenecks. If you’re using Microsoft eCDN, see [Teams Silent Testing](teams-silent-testing) for steps on validating network readiness. If you're using an eCDN partner solution, work directly with your provider to schedule and execute a silent test in advance of your event.
7. **Plan for a dry run** Always schedule a dry run ahead of your event to ensure readiness. This includes conducting an eCDN silent test (if applicable) to validate network performance and proactively surface any gaps before going live.

### Teams for Virtualized Desktop Infrastructure (VDI)

Users in your organization might use VDI. To learn which event capabilities are supported in VDI environments, see:

- [New VDI solution for Teams](vdi-2#feature-list-with-the-new-optimization)
- [Deploy Teams for Virtualized Desktop Infrastructure (VDI)](teams-client-vdi-requirements-deploy#features-not-supported-in-vdi)

## Operate and monitor

### Monitor events in your organizations

#### Real-time monitoring

You can use real-time data telemetry to monitor events and troubleshoot technical issues.

- **Real-time monitoring of the presenter and organizer experience**

    You can view scheduled events and see audio, video, content sharing, and network-related issues. As an admin, you can use this telemetry to investigate any issues presenters and organizers experience during the event and troubleshoot in real time. To learn more, see [Use real-time telemetry to troubleshoot poor meeting quality](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality).

    For more information, see [Monitor and troubleshoot Teams meetings and calls from the Teams admin center](monitor-troubleshoot-teams-meetings-calls).
- **Real-time monitoring of the attendee experience**

    You can use the Microsoft eCDN analytics dashboard for performance analysis and network troubleshooting of the attendee experience during events.

    For more information about real-time monitoring of attendees, see [Microsoft eCDN real time analytics](/en-us/ecdn/technical-documentation/analytics).

#### Call Quality Dashboard

Use the Call Quality Dashboard (CQD) to monitor event quality at the org-wide level and optimize your network to drive performance quality.

For more information about using CQD for events in your org, see [What is Call Quality Dashboard (CQD)](cqd-what-is-call-quality-dashboard). You can use the Microsoft Call Quality connector to view specialized **'Teams Events Overview'** and **'Event Health Details'** reports in Power BI Desktop.

To get started, download the latest [CQD Quality of Experience (QER) report template](cqd-power-bi-query-templates).

For more information about the dimensions and measurements visible through CQD for events, search for the word "events" in [Dimensions and measurements available in Call Quality Dashboard (CQD)](dimensions-and-measures-available-in-call-quality-dashboard).

#### Teams event insights for organizers

During an event, organizers and co-organizers can see real-time event analytics like viewer count, attendee country or region, and more. The analytics consist of several data widgets, including charts and graphs, breakdowns tables, and a viewing experience timeline.

For more information, see [Teams event insights](https://support.microsoft.com/office/town-hall-insights-in-microsoft-teams-def99575-61bf-4ea2-ad0e-c6e75dce7741).

## Reference

### Admin and organizer policy and setting controls

Admins and organizers have different policies and settings to control the event experience. The following table lists event features and how admin and organizer policies and settings interact.

# [Events up to 1,000 attendees](#tab/policy-events-up-to-1000-attendees)
| Feature | Admins | Organizers |
| --- | --- | --- |
| [Announce when callers join or leave](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams) | Control whether an entry and exit announcement plays when attendees who dialed in to the event join or leave. | No control. |
| [Anonymous participants](anonymous-users-in-meetings) | Manage how anonymous attendees access Teams meetings in your org. | Can prevent anonymous users from joining specific events if admin allows. |
| [Attendance and engagement reports](/en-us/microsoftteams/teams-analytics-and-reports/meeting-attendance-report) | Can enforce on or off or allow organizer to choose. | Can turn on or off if allowed by admin. Organizers can also see engagement information that captures how attendees reacted and interacted during the meeting or event. |
| [Audio and video](meeting-policies-audio-and-video) | Can set audio and video modes and network settings. | Can allow or prevent attendee microphones and cameras. |
| [Cameras](meeting-policies-audio-and-video) | Can use the **IP Mode for Video** policy to control both outgoing and incoming video for the events users organize or attend. | Can use the **Allow camera for attendees** setting when creating the event to manage whether attendees can turn on cameras. |
| [Chat](manage-meeting-chat) | Can manage whether organizers, presenters, co-organizers, and attendees can read and write chat messages. | Can manage whether chat is available for their events. |
| [Choose co-organizers](https://support.microsoft.com/office/schedule-a-meeting-in-microsoft-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | No control | Can assign different roles in an event to give users specific permissions. |
| [Collaboration features](meeting-policies-content-sharing) | Can control the availability of PowerPoint Live, whiteboard, and shared notes. | No control. |
| [Compliance recording](teams-recording-policy) | Can implement an admin policy for automatic recording. | No control |
| [Content sharing](meeting-who-present-request-control) | Can control sharing mode and who can request control and can set a default for who can present. | Can control who can present. |
| [Convenience recording](meeting-recording) | Can allow or prevent recording and set recording expiration time. | If the admin allows recording, organizers can manage who can record (Teams Premium) and automatic recording. |
| [Custom backgrounds (Teams Premium)](custom-meeting-backgrounds) | Can upload images for your users to display in the background of their video feed during meetings. | Can use the backgrounds you upload. |
| [Decorate my background (Teams Premium)](https://support.microsoft.com/office/change-your-background-in-microsoft-teams-meetings-f77a2381-443a-499d-825e-509a140f4780) | No control | Teams Premium licensed organizers, co-organizers, presenters, and participants can use AI to decorate their backgrounds. |
| [Custom dictionary for Teams (Microsoft Copilot)](copilot-custom-dictionary) | Can upload a custom dictionary in the Microsoft 365 admin center to improve the quality of transcription for Teams meetings and events. | No control |
| [Download transcripts](https://support.microsoft.com/office/manage-webinar-recordings-in-microsoft-teams-8cf1ba61-c9d8-4628-8b5d-0dcdb8503144) | No control. | Can download transcripts from their events. |
| [Email communications](manage-email-communications) | Can control whether event organizers and co-organizers can edit email templates for their events. | Can edit email templates before they're sent out. |
| [External presenters](https://support.microsoft.com/office/schedule-a-webinar-in-microsoft-teams-0719a9bd-07a0-47fd-8415-6c576860f36a) | No control. | Can invite presenters from outside of your organization. External presenters have a unique join link to join the event without waiting in the lobby. |
| [Green room](https://support.microsoft.com/office/green-room-for-teams-meetings-5b744652-789f-42da-ad56-78a68e8460d5) | No control. | Can choose if green room is used for an event. Can use the **End meeting** button to end the event for attendees while allowing organizers and presenters to stay in the green room until they're ready to leave. |
| [Intelligent recap (Teams Premium and Microsoft Copilot)](intelligent-recap-calls-meetings) | Assigned licenses and transcription policies control this feature. | No control. Organizers, co-organizers, and presenters can access intelligent recap after the event ends. Attendees don't have access to intelligent recap. |
| [Join verification for external presenters](events-external-presenter-join-verification) | Can require anonymous and unverified external presenters to verify their identity before joining events. | If the admin specifies no verification needed, can choose whether verification is required in their meeting options. |
| [Limit presenter role permissions](presenter-role-reduction) | Can limit presenter role permissions for the tenant. | No control. |
| [Live stream with RTMP-Out](stream-teams-meetings) | Can decide whether organizers can stream events to external endpoints by providing a Real-Time Messaging Protocol (RTMP) URL and key to the built-in custom Streaming app in Teams. | Can stream events with through apps like Custom Streaming. |
| [Live translated captions (Teams Premium)](meeting-transcription-captions) | Can control whether organizers with a Premium license can have live translated captions for their events. | Can enable live translated captions for themselves; attendees can always turn on live translated captions. |
| [Live translated transcription (Teams Premium)](meeting-transcription-captions) | Can control whether organizers with a Premium license can have live translated transcription for their events. | Can turn on live translated transcription for themselves; attendees can always turn on live translated transcription. |
| [Lobby](who-can-bypass-meeting-lobby) | Can set the defaults for new events. | Can choose lobby settings for certain events. |
| [Manage what attendees see](https://support.microsoft.com/office/manage-what-attendees-see-in-teams-meetings-19bfd690-8122-49f4-bc04-c2c5f69b4e16) | No control | Can decide who to spotlight during an event. Others are hidden from view. |
| [Manage who can schedule events](set-up-events) | Can disable events for users and groups, control which organizers can schedule events, and decide whether organizers can schedule public events. | Can schedule events if allowed by admin. |
| [Meeting themes (Teams Premium)](meeting-themes) | Can define meeting themes, including colors, images, and logo. | Can turn the admin-defined theme on or off. |
| [Microphones](meeting-policies-audio-and-video) | Can use the **IP Mode for Audio** policy to control both outgoing and incoming audio for the events users organize or attend. | Can use the **Allow mic for attendees** setting when creating the event to manage whether attendees can turn on their microphones. |
| [Microsoft Copilot in Teams meetings and events](copilot-teams-transcription) | Can control the default values and enforce specific values for Microsoft Copilot in Teams meetings and events in organizers’ meeting options. | Can control whether Microsoft Copilot in Teams meetings and events is used **Only during the meeting**, **During and after the meeting**, or **Off** during their events. Attendees can use Copilot if they have a Copilot Microsoft Copilot license. |
| [Microsoft Teams Rooms (Windows) can join as a presenter](https://support.microsoft.com/office/microsoft-teams-rooms-windows-e667f40e-5aab-40c1-bd68-611fe0002ba2) | No control. | Can add Microsoft Teams Rooms on Windows with a Pro license as a presenter. Microsoft Teams Rooms see, but can't send chat messages. Organizers must add Microsoft Teams Rooms from external organizations as external presenters. |
| [Outlook add-in (classic Outlook)](outlook-add-in-authentication-policy-requirements) | Can control whether users can schedule events from classic Outlook. | If admin allows, can schedule events from classic Outlook. |
| [Prevent copying or forwarding chat, captions, and transcripts (Teams Premium)](manage-chat-sensitive-meetings#prevent-copying-or-forwarding-chat-captions-and-transcripts) | Can prevent copying or forwarding of chat contents by using a meeting template or sensitivity label. | Can manage options if admin doesn't lock label or template settings. |
| [Q&A](manage-qna-for-teams) | Can manage if organizers can use Q&A in events. | Can decide if Q&A is available for their events if allowed by admins. Organizers and co-organizers can export the event's questions and answers to a CSV file. |
| [Quality of service (QoS)](meetings-real-time-media-traffic) | Can prioritize real-time network traffic that's sensitive to network delays over traffic that's less sensitive. | No control. |
| [Reactions](manage-reactions-meetings) | Can control the default value in organizers' meeting options. | Can control whether reactions can be used in their events. |
| [Recording](meeting-recording) | Can allow or prevent event recording. | If the admin enables recording, organizers can set who can record and automatic recording. |
| [Registration](set-up-events) | Can manage who can register for events. | Organizers can decide how many people can register for an event. They can also require manual registration approval, enable a waitlist, and limit registration start and end time. |
| [Registration form](manage-registration-form-events) | Can manage the types of questions an organizer can require attendees to answer when registering for events. | Can edit the registration form depending on admin settings. |
| [RTMP-In](meetings-rtmp-in) | Can allow or disable RTMP-In for organizers. | Can produce their event directly from an external hardware or software-based encoder using Real-Time Messaging Protocol (RTMP). |
| [SRT-In](meetings-events-srt-in) | Can allow or disable SRT-In for organizers. | Can produce their event directly from an external hardware or software-based encoder using Secure Reliable Transport (SRT) protocol. |
| [Speaker Coach](meeting-speaker-coach) | Manage whether users in your organization can use Speaker Coach during events. | No control. All participants can use Speaker Coach if the admin allows. |
| [Teams events usage report](/en-us/microsoftteams/teams-analytics-and-reports/teams-events-usage-report) | View activity and usage trends for all events created in your organization. | No control. |
| [Theming](https://support.microsoft.com/office/customize-a-webinar-in-microsoft-teams-20491c28-863f-479b-8f61-85046d124f10) | No control. | Can customize their event's theme. |
| [Transcription and captions](meeting-transcription-captions) | Can allow or prevent transcription and closed captions for attendees. | Can enable captions. |
| [Video effects](meeting-policies-audio-and-video#participants-can-use-video-effects) | Control whether users can customize their video background. | If the admin allows, organizers and attendees can blur their video background, choose from the default set of images, or upload custom images to use as their background. |
| [VOD publishing](manage-vod-publishing) | Can manage the types of recordings organizers can publish. | Can publish and modify event recordings. |
| [Voice isolation](voice-isolation) | Can control whether users can use voice isolation in events. | Can enable voice isolation. |
| [Watermarks (Teams Premium)](watermark-meeting-content-video) | Can allow or prevent watermarks for attendee video and shared content | Can enforce watermarks if the admin allows. |
| [Join and lobby](who-can-bypass-meeting-lobby) | Can set the defaults for new meetings and events. | Can choose meeting join and lobby settings for each event. |

# [Events optimized for large audiences](#tab/policy-events-optimized-for-large-audiences)
| Feature | Admins | Organizers |
| --- | --- | --- |
| [Announce when callers join or leave](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams) | No control. | Control whether an entry and exit announcement plays when attendees who dialed in to the event join or leave. |
| [Attendance and engagement reports](/en-us/microsoftteams/teams-analytics-and-reports/meeting-attendance-report) | Can enforce on or off or allow organizer to choose. | Can turn on or off if allowed by admin. Organizers can also see engagement information that captures how attendees reacted and interacted during the meeting or event. |
| [Attendee reactions](https://support.microsoft.com/office/schedule-a-town-hall-in-microsoft-teams-d493b5cc-9f61-4dac-8027-d837dafb7a4c#bkmk_townhall_reactions) | No control. | Controls whether attendees can engage during the event with live reactions. |
| [Audio and video](meeting-policies-audio-and-video) | Can manage the availability and use of audio and video for presenters and organizers. | Only presenters and organizers can use their audio and video. Attendees can't share their audio or video, but interact through Q&A. |
| [Chat for attendees](manage-event-chat) | Can manage whether organizers can turn on chat for their attendees. | Can decide whether attendees can chat during events if their admin's policy allows it. |
| Event group chat (organizers, co-organizers, and presenters) | No control. | Can chat with presenters and co-organizers. Attendees don't use this chat during events. To learn how attendees can use chat during events optimized for large audiences, see [Manage chat in Teams events](manage-event-chat). |
| [Cloud Video Interop(CVI)](cloud-video-interop) | Can manage whether your organization uses CVI, a Microsoft Qualified third-party solution that enables third-party SIP and H.323 video room devices (VTCs) to join events and meetings. | To allow presenters to join and present in events using their own Video Teleconferencing (VTC) devices, organizers can share CVI join codes directly from the event’s share event dialog. VTCs aren't able to join when event access is restricted to people and groups. |
| [Compliance recording](teams-recording-policy) | Can implement an admin policy for automatic recording. | No control |
| [Content sharing](meeting-policies-content-sharing) | Can control sharing mode, who can request control, and can set a default for who can present. | Can control who can present among presenters, organizers, and co-organizers. Attendees can't share content in events. |
| [Convenience recording](meeting-recording) | Can allow or prevent recording and set recording expiration time. | If the admin allows recording, organizers can manage who can record (Teams Premium) and automatic recording. |
| [Custom dictionary for Teams (Microsoft Copilot)](copilot-custom-dictionary) | Can upload a custom dictionary in the Microsoft 365 admin center to improve the quality of transcription for Teams meetings and events. | No control |
| [Custom backgrounds (Teams Premium)](custom-meeting-backgrounds) | Can upload images for organizers, co-organizers, and presenters with a Teams Premium license in your organization to display in the background of their video feed during meetings. | Internal organizers, co-organizers, and presenters with a Teams Premium license can use the backgrounds you upload. |
| [Decorate my background (Teams Premium)](https://support.microsoft.com/office/change-your-background-in-microsoft-teams-meetings-f77a2381-443a-499d-825e-509a140f4780) | No control | Teams Premium licensed organizers, co-organizers, and presenters can use AI to decorate their backgrounds. |
| [Download transcripts](https://support.microsoft.com/office/manage-town-hall-recordings-in-microsoft-teams-88ac3af7-db67-4556-a202-b73a1d6c2e46) | No control. | Can download transcripts from their events. |
| [eCDN](streaming-ecdn-enterprise-content-delivery-network) | Can manage and configure the availability of eCDN for organizers. You can also turn off the Microsoft eCDN for organizers and switch to a partner eCDN provider. | No control. |
| [eCDN Analytics](streaming-ecdn-enterprise-content-delivery-network) | Can use the eCDN analytics dashboard to troubleshoot the attendee experience during events. | Some analytics might be available through the eCDN provider, depending on the eCDN solution used. |
| [Email communications](manage-email-communications) | Can control if event organizers and co-organizers can edit email templates for their events. | Can edit email templates before they're sent out. |
| [External presenters](https://support.microsoft.com/office/schedule-a-town-hall-in-microsoft-teams-d493b5cc-9f61-4dac-8027-d837dafb7a4c) | No control. | Can invite presenters from outside of your organization. External presenters have a unique join link to join the event without waiting in the lobby. |
| [Green room](https://support.microsoft.com/office/green-room-for-teams-meetings-5b744652-789f-42da-ad56-78a68e8460d5) | No control. | Can choose if green room is used for an event. Can use the **End meeting** button to end the event for attendees while allowing organizers and presenters to stay in the green room until they're ready to leave. |
| [Intelligent recap (Teams Premium and Microsoft Copilot)](intelligent-recap-calls-meetings) | Assigned licenses and transcription policies control this feature. | No control. Organizers, co-organizers, and presenters can access intelligent recap after the event ends. Attendees don't have access to intelligent recap. |
| [Join verification for external presenters](events-external-presenter-join-verification) | Can require anonymous and unverified external presenters to verify their identity before joining events. | If the admin specifies no verification needed, can choose whether verification is required in their meeting options. |
| [Limit presenter role permissions](presenter-role-reduction) | Can limit presenter role permissions for the tenant. | No control. |
| [Live transcription and captions](meeting-transcription-captions) | Can allow or prevent transcription and closed captions for attendees. | Only AI generated captions are currently available. |
| [Live translated captions (Teams Premium)](meeting-transcription-captions) | Can control whether organizers with a Premium license can have live translated captions for their events. | Organizers can select up to 10 languages for attendees to use when translating captions during the event without Teams Premium. |
| [Live translated transcription (Teams Premium)](meeting-transcription-captions) | Can control whether organizers with a Premium license can have live translated transcription for their events. | Can enable live translated transcription for themselves; attendees can always turn on live translated transcription. |
| [Manage what attendees see](https://support.microsoft.com/office/manage-what-attendees-see-in-teams-meetings-19bfd690-8122-49f4-bc04-c2c5f69b4e16) | No control. | Can decide who to spotlight during an event. Others are hidden from view. |
| [Manage who can schedule and attend events](set-up-events) | Can disable events for users and groups, control which organizers can schedule events, and decide whether organizers can schedule public events. | Can schedule events if allowed by admin. |
| [Meeting themes (Teams Premium)](meeting-themes) | Can define meeting themes, including colors, images, and logo. | Can turn the admin-defined theme on or off. |
| [Microsoft Copilot in Teams meetings and events](copilot-teams-transcription) | Can control the default values and enforce specific values for Microsoft Copilot in Teams meetings and events in organizers’ meeting options. | Can control whether Microsoft Copilot in Teams meetings and events is used **Only during the meeting**, **During and after the meeting**, or **Off** for their events. |
| Microsoft Teams Rooms (Android) can join as a presenter or attendee^1^ | No support. | No support. |
| [Microsoft Teams Rooms (Windows) can join as a presenter](https://support.microsoft.com/office/microsoft-teams-rooms-windows-e667f40e-5aab-40c1-bd68-611fe0002ba2)^1^ | No control. | Can add Microsoft Teams Rooms on Windows with a Pro license as a presenter. Microsoft Teams Rooms see, but can't send chat messages. Organizers must add Microsoft Teams Rooms from external organizations as external presenters. |
| [Prevent copying or forwarding chat, captions, and transcripts (Teams Premium)](manage-chat-sensitive-meetings#prevent-copying-or-forwarding-chat-captions-and-transcripts) | Can prevent copying or forwarding of chat contents by using a meeting template or sensitivity label. | Can manage options if admin doesn't lock label or template settings. |
| [Q&A](manage-qna-for-teams) | Can manage if organizers can use Q&A in events. | Can decide if Q&A is available for their events if allowed by admins. Q&A is the only way attendees can interact and engage with presenters and organizers. Organizers and co-organizers can export the event's questions and answers to a CSV file. |
| [Quality of service (QoS)](meetings-real-time-media-traffic) | Can prioritize real-time network traffic that's sensitive to network delays over traffic that's less sensitive. | No control. |
| [Recording](meeting-recording) | Can allow or prevent event recording. | Recordings start automatically for events, but organizers can turn this off. |
| [Recording expiration](meeting-recording) | Can manage whether recordings automatically expire. | By default, published recordings expire after 30 days. Organizers can extend the expiration date to 60 days. After the new date passes, they must reupload and republish the file to keep sharing. |
| [Registration](set-up-events) | Can manage who can register for events. | Organizers can decide how many people can register for an event. They can also require manual registration approval, enable a waitlist, and limit registration start and end time. |
| [Registration form](manage-registration-form-events) | Can manage the types of questions an organizer can require attendees to answer when registering for events. | Can edit the registration form depending on admin settings. |
| [RTMP-In](meetings-rtmp-in) | Can allow or disable RTMP-In for organizers. | Can produce their event directly from an external hardware or software-based encoder using Real-Time Messaging Protocol (RTMP). |
| [SRT-In](meetings-events-srt-in) | Can allow or disable SRT-In for organizers. | Can produce their event directly from an external hardware or software-based encoder using Secure Reliable Transport (SRT) protocol. |
| [Shared notes](meeting-policies-content-sharing) | Can manage whether organizers and co-organizers can use shared notes with other during events. | Can use shared notes with co-organizers during events. |
| [Speaker coach](meeting-speaker-coach) | Can manage whether organizers, presenters, and co-organizers can use speaker coach during events. | Can use speaker coach for private real-time feedback and suggestions for improvement of themselves, co-organizers, and presenters. |
| [Streaming encoders](teams-encoder-setup) | Can control whether organizers can use RTMP. | Can use encoders to take audio and video content from sources such as a camera, a microphone, a desktop screen capture. |
| [Teams event insights for organizers](https://support.microsoft.com/office/town-hall-insights-in-microsoft-teams-def99575-61bf-4ea2-ad0e-c6e75dce7741) | No control. | Organizers and co-organizers can see real-time event analytics like viewer count, attendees’ country or region, and more. The analytics consist of several data widgets, including charts and graphs, breakdowns tables, and a viewing experience timeline. |
| [Teams events usage report](teams-analytics-and-reports/teams-events-usage-report) | View activity and usage trends for all events created in your organization. | No control. |
| [Ultra-Low Latency streaming](ultra-low-latency-streaming-events) | No control. | No control. |
| [VOD publishing](manage-vod-publishing) | Can manage the types of recordings organizers can publish. | Can publish and modify event recordings. |
| [Voice isolation](voice-isolation) | Can control whether users can use voice isolation in events. | Can enable voice isolation. |
| [Who has control of production tools](https://support.microsoft.com/office/control-town-hall-production-tools-in-microsoft-teams-8a19026b-43d1-45e3-b306-35610d83e5f1) | No control. | Organizers can choose specific organizers, co-organizers, or presenters who can control production tools can start the event, manage what attendees see, and end the event. Organizers can also give Microsoft Teams Rooms (Windows) production capabilities. |
| [1080p video resolution](enable-1080p-video-resolution) | Can enable 1080p video resolution for attendees. | No control. |

^1^ Only Microsoft Teams Rooms on Windows with a Pro license are officially supported to join meetings and events as a presenter or as an attendee. To allow Rooms to join as a presenter in meetings, organizers must set **Who can present** to either **Organizer or co-organizer only** or **Specific people**. To allow Rooms to join as an attendee in events optimized for large audiences, such as town halls, organizers must add the Room as an attendee when creating the event. To allow Rooms to join as an attendee in events up to 1,000 attendees, the registered attendee must send the registration link to the Room.

---

### Need help with your events?

Are you and your organizers new to hosting events or just need some extra help? Teams Events Services offers guidance and assistance to help you plan, set up, produce, and run events in Teams. For more information, see [Teams Events Services](https://adoption.microsoft.com/virtual-event-guidance/assistance).

### Related articles

- [Overview of meetings and events in Microsoft Teams](overview-meetings-events)
- [Meetings and events feature comparison](meetings-events-feature-comparison)
- [Teams settings and policies reference](settings-policies-reference)