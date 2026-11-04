---
layout: Conceptual
title: Manage chat in Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-meeting-chat
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: heiris
ms.date: 2026-07-06T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- Tier2
- m365initiative-meetings
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Learn how to manage meeting chat in Teams meetings and in events with up to 1,000 attendees, and manage meeting chat in unfederated Teams meetings hosted by other organizations that you don't have a trusted relationship with.
locale: en-us
document_id: 069f2c57-1eba-cbc3-ecdf-9e264edf4beb
document_version_independent_id: 069f2c57-1eba-cbc3-ecdf-9e264edf4beb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-meeting-chat.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-meeting-chat
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-meeting-chat.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f457a69d-91e8-c347-e60c-3b4f8f4f6d1c
---

# Manage chat in Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

## Overview

In Microsoft Teams, chat in meetings and in events with up to 1,000 attendees allows participants to exchange messages before, during, and after the meeting or event, with interactive capabilities such as replies, @mentions, reactions, and support for formatting options, sharing images, and files.

In events [optimized for large audiences](plan-events), chat is designed to support scale. Organizers, co-organizers, and presenters can chat with each other before, during, and after the event in the event group chat. Attendee chat, when enabled, is only available during the event. For more information about how attendees can use chat in events optimized for large audiences, see [Manage chat for Microsoft Teams events](manage-event-chat).

As an admin, you can control:

- Whether participants in your users' meetings and events with up to 1,000 attendees can read and send chat messages.
- Whether users in your organization can use chat when they're participants in Teams meetings hosted by other organizations where there isn't a trusted relationship.

## Manage chat messages for your organization's Teams meetings

The **Meeting chat** setting controls whether participants in your users' meetings can read and send chat messages. This setting doesn't apply to channel meetings and is a per-user and per-organizer policy.

In addition to this **Meeting chat** policy, your users have their own **Meeting chat** control in their meeting options. When you don't set the admin policy to **Off**, organizers can manage chat availability in their meetings and in their events with up to 1,000 attendees. They can choose to set chat to **On**, **Off**, or **In meeting only**. For more information about your users' **Meeting chat** controls, see [Chat in a Teams meeting](https://support.microsoft.com/office/64e2cb91-8a11-4781-94ea-fbb23f2b922f).

Note

The admin policy doesn't control what organizers see in their **Meeting options**. For example, when you set the **Meeting chat** policy to **In-meeting only for everyone**, the organizer still sees the option to set it to **On**. However, the admin policy enforces that chat will only be available during the meeting. Your policy determines the chat experience during meetings and events, regardless of what's shown and selected in **Meeting options**.

The following table describes the behavior for your **Meeting chat** policy settings:

| Teams admin center value | PowerShell value | Behavior |
| --- | --- | --- |
| **On for everyone** | Enabled | All participants can read and send chat messages, but the organizer's **Allow meeting chat settings** determine the chat experience. Organizers can also control when chat is available during their meetings and their events with up to 1,000 attendees. |
| **On for everyone but anonymous users** | EnabledExceptAnonymous | All participants, except anonymous ones, can read and send chat messages. The organizer's **Allow meeting chat** settings control the chat experience for everyone. Anonymous participants, however, can't read or send any messages. Organizers can also manage when chat is available during their meetings and their events with up to 1,000 attendees. |
| **Off** | Disabled | Meeting chat is turned off for all participants; organizers can't use their **Allow meeting chat** to turn on chat in their meetings. Organizers can't override this setting. |
| **In-meeting only for everyone** | EnabledInMeetingOnlyForAll | Chat is available only during the meeting. Participants and organizers can't send messages before the meeting starts or after it ends. Organizers can't override this setting. |
| **In-meeting only for everyone but anonymous users** | EnabledInMeetingOnlyForAllExceptAnonymous | Chat is available only during the meeting for all participants, except anonymous users, who don't have any access to the chat. Participants and organizers can't send messages before the meeting starts or after it ends. Organizers can't override this setting. |

### Use the Teams admin center to manage meeting chat

To manage meeting chat for your users in the Teams admin center, use the following steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy you want to edit.
3. Go to the **Meeting engagement** section.
4. Set **Meeting chat** to your chosen value of **On for everyone**, **On for everyone but anonymous users**, **Off**, **In-meeting only for everyone**, or **In-meeting only for everyone but anonymous users**.
5. Select **Save**.

### Use PowerShell to manage meeting chat

You can use the **`-MeetingChatEnabledType`** parameter in the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet to control the availability of meeting chat.

To allow meeting chat to be on for everyone but anonymous users with this assigned policy, run the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -MeetingChatEnabledType EnabledExceptAnonymous
```

To turn off meeting chat for users with this assigned policy, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -MeetingChatEnabledType Disabled
```

To make chat available only during meetings organized by users with this policy, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -MeetingChatEnabledType EnabledInMeetingOnlyForAll
```

To make chat available only during meetings organized by users with this policy and prevent anonymous users from seeing or writing in chat, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -MeetingChatEnabledType EnabledInMeetingOnlyForAllExceptAnonymous
```

To learn more about chat for your end users, see [Chat in a Teams meeting](https://support.microsoft.com/office/64e2cb91-8a11-4781-94ea-fbb23f2b922f).

## Manage chat messages in Teams meetings hosted by other organizations that you don't have a trusted relationship with

The **Chat in external meetings** setting determines if users in your organization can chat in Teams meetings hosted by other organizations without a trusted relationship configured in [external access](trusted-organizations-external-meetings-chat). In such cases, the other organization considers your users to be anonymous. This setting is a per-user and per-participant policy.

The following table describes the behavior for your **Chat in external meetings** policy settings:

| Teams admin center value | PowerShell value | Behavior |
| --- | --- | --- |
| **On** | True | **This is the default value.** Users in your organization can read and send meeting chat messages in Teams meetings hosted by other organizations that you don't have a trusted relationship with. You must also set **Meeting chat** to **On for everyone** and the meeting organizer must set [**Allow meeting chat**](https://support.microsoft.com/office/participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) to either **Enabled** or **In meeting only**. |
| **Off** | False | Users in your organization can't read or send meeting chat messages in Teams meetings hosted by other organizations that you don’t have a trusted relationship with. |

You can use the Teams admin center or PowerShell to manage whether users in your organization can use chat messages in Teams meetings hosted by other organizations without a trusted relationship.

### Use the Teams admin center to manage chat in meetings hosted by other organizations

To choose whether users in your organization can use chat in Teams meetings hosted by other organizations, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy you want to edit, or create a new one.
3. Go to the **Meeting engagement** section.
4. Turn the **External meeting chat** toggle **On** or **Off**.
5. Select **Save**.

### Use PowerShell to manage chat in meetings hosted by other organizations

The **`-AllowExternalNonTrustedMeetingChat`** parameter in the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet controls the availability of meeting chat for your users when they attend external meetings.

To turn off chat in Teams meetings hosted by other organizations for users with the assigned policy, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowExternalNonTrustedMeetingChat $False
```

To allow chat in Teams meetings hosted by other organizations for users with the assigned policy, run the following command:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowExternalNonTrustedMeetingChat $True 
```

## Allow organizers to chat with lobby participants

You can allow organizers to chat with participants who can't bypass the lobby due to meeting policy. These participants can send messages in the lobby chat that the organizer can see and respond to.

Before you turn on this policy, you must first set **Meeting chat** to **On for everyone** or **On for everyone but anonymous users**.

To manage whether organizers can chat with lobby participants, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy you want to edit, or create a new one.
3. Go to the **Meeting engagement** section.
4. Turn the **Organizers can chat with lobby participants** toggle **On** (default) or **Off**.
5. Select **Save**.

## Limitations

- Microsoft Teams Rooms on Windows with a Pro license can't use chat when they join meetings as a presenter.