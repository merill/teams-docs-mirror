---
layout: Conceptual
title: Configure the Microsoft Teams meeting lobby for sensitive meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/configure-lobby-sensitive-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: article
ms.service: msteams
ms.subservice: meetings
ms.reviewer: vivek.mohan
ms.date: 2026-07-06T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
- Tier1
description: Learn how to configure the Teams meeting lobby to enhance security for sensitive meetings by using admin policies, sensitivity labels, and meeting templates.
locale: en-us
document_id: 0b5d6aab-04dc-1eef-6430-304d72f4a724
document_version_independent_id: 0b5d6aab-04dc-1eef-6430-304d72f4a724
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/configure-lobby-sensitive-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-lobby-sensitive-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/configure-lobby-sensitive-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1f3c0c2b-4ae4-6f81-45e2-68abe2b3bd4c
---

# Configure the Microsoft Teams meeting lobby for sensitive meetings - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

The meeting lobby is a tool that you can use to help ensure that inappropriate people aren't admitted to meetings. Holding different types of participants in the lobby allows meeting organizers to make sure it's appropriate for them to attend the meeting.

By default, people in your organization and [guests](guest-access) are admitted to meetings directly. Participants from [trusted organizations](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings#specify-trusted-microsoft-365-organizations) and [anonymous participants](anonymous-users-in-meetings) must wait in the lobby until a meeting organizer admits them. Meeting organizers can change this default setting for each meeting they create.

You can use meeting policies in the Teams admin center, meeting templates, and sensitivity labels to customize the lobby experience for different users and different types of meetings.

The following table lists features that you can use to help manage the lobby experience for your organization and where to configure them.

| Setting | Admin policy | Sensitivity label | Template | Meeting organizer |
| --- | --- | --- | --- | --- |
| [Announce when dial-in callers join or leave](custom-meeting-templates-overview) | No | No | Yes | Yes |
| [Anonymous users and dial-in callers can start a meeting](who-can-bypass-meeting-lobby) | Yes | No | No | No |
| [Anonymous users can join a meeting](who-can-bypass-meeting-lobby) | Yes | No | No | No |
| [People dialing in can bypass the lobby](who-can-bypass-meeting-lobby) | Yes | Yes | Yes | Yes |
| [Who can admit from lobby](who-can-bypass-meeting-lobby) | Yes | No | No | Yes |
| [Who can bypass the lobby](who-can-bypass-meeting-lobby) | Yes | Yes | Yes | Yes |

For information about how to use templates and sensitivity labels to configure meeting settings, see [Overview of custom meeting templates in Microsoft Teams](custom-meeting-templates-overview) and [Use sensitivity labels to protect calendar items, Teams meetings, and chat](/en-us/microsoft-365/compliance/sensitivity-labels-meetings).

Note

Meeting settings in sensitivity labels and custom meeting templates require Teams Premium.

## Lobby settings for different types of meetings

Note

In Teams events, some of these features are only available in events with up to 1,000 attendees that require registration.

### Who can admit from lobby

The following settings are available for **Who can admit from lobby**:

- Organizers, co-organizers, and presenters
- Organizers and co-organizers

To manage who can bring participants from the lobby into the meeting or event, you should consider using this per-organizer policy for sensitive meetings. When set to the default value of **Organizers, co-organizers, and presenters**, only organizers, co-organizers, and presenters can admit participants into the meeting from the lobby. This policy sets a default that your organizers can change through their **Meeting options**.

### Who can bypass the lobby

The following settings are available for **Who can bypass the lobby**:

- Everyone
- People in my org and guests
- People in my org, trusted orgs, and guests
- People in my org
- Only organizers and co-organizers
- People who were invited

This per-organizer policy controls who can bypass the lobby into the meeting or event. When set to the default value of **People in my org and guests**, only people in my org and guests can bypass lobby. This policy sets a default that your organizers can change through their **Meeting options**.

Note

The **Who can bypass the lobby** meeting option isn't available for events that don't require registration or that are [optimized for large audiences](plan-events).

Another setting, **People dialing in can bypass the lobby**, controls if people calling in by phone can bypass the lobby.

While the meeting organizer normally chooses which setting to use for each meeting, you can enforce a particular setting using either a meeting template or a sensitivity label.

If your organization needs to restrict certain meetings to internal participants only, you could use a meeting template that allows only people in your organization to bypass the lobby. This option ensures that people outside the organization who were accidentally invited or sent a meeting link can't join the meeting directly.

For meetings with highly sensitive information, you could use a meeting template or sensitivity label that allows only meeting organizers to bypass the lobby. This option allows organizers to vet participants and ensures the meeting doesn't start until an organizer joins.

For sensitive meetings in general, consider using the **People who were invited** option. This option ensures that people who don't have either a direct or forwarded meeting invite go through the lobby. (The meeting organizer can also prevent forwarding when they create the meeting.)

For more information about the meeting lobby, see [Control who can bypass the meeting lobby in Microsoft Teams](who-can-bypass-meeting-lobby).

For information about using meeting templates and sensitivity labels together, see [Use Teams meeting templates, sensitivity labels, and admin policies together for sensitive meetings](meeting-templates-sensitivity-labels-policies).

### Allow organizers to chat with lobby participants

You can allow organizers to have a designated lobby chat with participants while they wait in the lobby. This per-organizer policy is on by default, but you can turn it off for specific organizers. To learn more, see [Manage chat in Microsoft Teams meetings](manage-meeting-chat#allow-organizers-to-chat-with-lobby-participants).

This option isn't available for events [optimized for large audiences](plan-events).

### Attendees calling in by phone

By default, attendees who are dialing in by phone go through the lobby. Administrators can change this default with the **People dialing in can bypass the lobby** admin meeting policy. If you want to enforce this setting to be on or off, you must use a meeting template or sensitivity label.

If you want to allow callers to bypass the lobby, meeting organizers can control this setting, or you can enforce it through a meeting template or sensitivity label.

Attendees can't dial in by phone in events [optimized for large audiences](plan-events).

#### Join and leave notifications

Meeting organizers have the option of having attendees calling in by phone announced when they join or leave a meeting. If you want to ensure that phone attendees are announced for certain types of meetings, you can enforce this setting with a meeting template.

## Meeting with anonymous participants

Unless you allow everyone to bypass the lobby, anonymous participants must go through the lobby to attend the meeting. Meeting organizers can then decide if these participants should be admitted.

If your organization doesn't allow anonymous participants in meetings, turn off the **Anonymous users can join a meeting** policy in the Teams admin center. For groups like marketing that need anonymous participants to join meetings, and others like research that don't, use Teams meeting policies to configure anonymous meeting join for different groups. For more information, see [Manage anonymous participant access to Teams meetings and events](anonymous-users-in-meetings).