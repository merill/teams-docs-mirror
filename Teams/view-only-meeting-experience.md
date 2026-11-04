---
layout: Conceptual
title: View-only meeting experience - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/view-only-meeting-experience
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
ms.reviewer: christi.balaki
ms.date: 2024-09-26T00:00:00.0000000Z
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: meetings
search.appverid: MET150
description: Learn about the Teams view-only meeting experience for admins, presenters, and attendees.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
locale: en-us
document_id: 2bf705c2-1f24-bdb5-e712-e8408b941aca
document_version_independent_id: ddedd7e0-7d85-06e0-7f20-8b83b3dccec7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/view-only-meeting-experience.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: view-only-meeting-experience
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/view-only-meeting-experience.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 02ea9ab3-3b08-ebdb-487a-efb0018201ef
---

# View-only meeting experience - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events

Microsoft Teams supports up to 10,000 attendees in a meeting. Once the main meeting reaches capacity at around 1,000 users, additional attendees join with a view-only experience. Attendees in the view-only experience can view the meeting, but have limited access to meeting features. Meeting organizers see notifications for the view-only experience when around 500 users are in the meeting.

Initial attendees who join before the meeting capacity enjoy the full meeting experience. These attendees can share audio/video, see shared content, and participate in chat.

Attendees who join after the main meeting capacity is reached have a view-only experience. These attendees can join the view-only experience through desktop, web, and Teams mobile (Android and iOS).

As an admin, you can assign this policy to your organizers. This policy allows attendees who join the meeting after the 1,000-user capacity is reached to have a view-only experience. If you turn off the view-only experience, the meeting is limited to the first 1,000 attendees.

To learn how to monitor, scale, and optimize the distribution of video during view-only meetings, see [Enterprise content delivery networks for streaming Microsoft Teams events](streaming-ecdn-enterprise-content-delivery-network).

## Teams view-only experience controls

You enable the view-only experience using the [`Set-CsTeamsMeetingPolicy`](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

To enable the view-only experience, use the following PowerShell script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

To disable the view-only experience, use the following PowerShell script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

## User experience

The user experience varies based on several factors.

When the capacity of the main meeting is reached, an attendee can't join the meeting if any of the following are true:

- You didn't enable the Teams view-only experience for either the organizer or for the entire tenant.
- The view-only attendee can't bypass the lobby. For example, if a meeting organizer chooses to have only **People in my organization** bypass the lobby, an attendee outside of the org can't join the meeting as a view-only attendee.

When the capacity of the main meeting is reached, the meeting organizer and presenters see a banner informing them that new attendees might join as view-only attendees.

![the Teams client and banner message for organizers and presenters.](media/chat-and-banner-message.png)

When the capacity of the main meeting is reached, meeting attendees are informed on the pre-join screen that they're joining in view-only mode.

![the Teams pre-join screen and the message for participants telling them that they will join in view-only mode.](media/view-only-pre-join-screen.png)

Before the meeting reaches capacity, attendees always join the main meeting. Once the meeting reaches capacity, view-only attendees can't be promoted to the main meeting.

When presenter and attendee roles are set up, the main meeting reserves space for up to 50 presenters. Any extra presenters who join after the main meeting reaches capacity become view-only attendees. These presenters have the same limitations as other view-only attendees. Organizers are always guaranteed space in the main meeting.

## Meeting presenter and organizer limitations

Limitations for meeting presenters and organizers include:

- Users in the main meeting can't see the view-only attendees in the People panel.
- They can't remove a view-only attendee from the meeting.
- We don't support E-discovery for view-only attendees.

Note

Attendee count reflects the attendees in the main meeting and the view-only attendees. Organizers can review the view-only attendees who joined using the attendance report after the meeting is over.

## Experience for view-only attendees

The Teams view-only experience allows attendees to:

- Listen to the participants in the main Teams meeting.
- See the video feed for the active speaker (if the active speaker is sharing video).
- See content being shared using the share desktop or screen functionality.

View-only attendees can't perform these actions in the meeting:

- Join the meeting if they don't have permission to bypass the lobby.
- Join the view-only meeting using Audio Conferencing.
- Join the view-only meeting using Microsoft Teams Rooms on Android system or using Cloud Video Interop (CVI) services.
- Share their audio or video.
- See or participate in the meeting chat.
- See the video feed of meeting participants unless the participant is the active speaker.
- See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).
- Raise their hand in the meeting.
- Send or see reactions.
- Interact with any third-party App integrating into the Teams Meeting, including Polls.
- Access the meeting recording.

## View-only feature limitations

- View-only attendees can only see Live Captions on Desktop and Web. Only English captions are supported at this time.
- View-only attendees don't have Information Barrier support. If you need Information Barrier support in your organization, you should disable this feature.
- Streaming technology supports view-only attendees.
- View-only attendees aren't supported in [Call Analytics](use-call-analytics-to-troubleshoot-poor-call-quality).
- View-only attendees have a single video experience. They can see either the active speaker or the content being shared, but not both.
- We don't currently support **Gallery** or **Large gallery** layouts for view-only attendees.
- The following lobby policies support view-only attendees: **'People in my org,'** **'People in my org and guests,'** **'People in my org, trusted orgs, and guests,'** and **'Everyone'**. If you use a lobby policy that doesn't support view-only attendees, they're rejected from the meeting.
- View-only attendees don't have the same latency as a regular attendee. ^1^

    ^1^ View-only attendees have a 30-second video and audio delay in the meeting.

## Networking Considerations

Teams view-only meetings use the same platform as Teams live events. View-only attendees receive meeting content, audio, and video as TCP HTTPS streams. We strongly recommend that you bypass proxy infrastructure for Teams live events URLs and IP addresses. For more information, see [Azure CDN Coverage by Metro](/en-us/azure/cdn/cdn-pop-locations).