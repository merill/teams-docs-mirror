---
layout: Conceptual
title: Manage chat for Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-event-chat
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.reviewer: chbalaki
ms.date: 2026-10-06T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
description: Learn how to manage the chat experience for Teams events.
locale: en-us
document_id: a1d99d87-552d-632a-ecb5-fcf77e009528
document_version_independent_id: a1d99d87-552d-632a-ecb5-fcf77e009528
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-event-chat.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-event-chat
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-event-chat.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 44e66ca7-b712-6bac-26bc-45294e923ba9
---

# Manage chat for Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

In Teams events, the chat experience for participants—and how admins manage it—depends on the event type and capacity:

- Events up to 1,000 attendees
- Events optimized for large audiences

## Events up to 1,000 attendees

Chat in events with up to 1,000 attendees, such as webinars, uses the same experience as chat in Teams meetings. Participants can exchange messages with each other before, during, and after the event, with interactive capabilities such as replies, @mentions, reactions, and support for formatting options, sharing images, and files.

As an admin, you can control whether participants in your organizers' events with up to 1,000 attendees can read and send chat messages. For more information, see [Manage chat in Microsoft Teams meetings](manage-meeting-chat).

## Events optimized for large audiences

In [events optimized for large audiences](plan-events), such as town halls, the chat experience differs depending on the event role.

Organizers, co-organizers, and presenters can chat with each other in the event group chat. The event group chat is available before, during, and after an event, and is a separate experience from the chat with attendees.

Meeting chat for attendees is available only during the event. Organizers can turn on **Meeting chat** in their **Meeting options** to allow attendees to send and view chat messages.

As an admin, you can manage whether organizers can turn on meeting chat for their attendees in events optimized for large audiences.

Note

Attendee meeting chat is supported in events with up to 20,000 attendees.

### Manage meeting chat for your organizers in events optimized for large audiences

You can use the Teams admin center or PowerShell to manage whether organizers can turn on chat for their attendees in events optimized for large audiences.

#### Use the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select the policy you want to edit or create a new one.
3. In the **Town hall chat experience** dropdown list, select **Optimized** (the default value) or **None**.
4. Select **Save**.

#### Use PowerShell

To manage whether organizers can turn on chat for their attendees, use the **`-TownhallChatExperience`** parameter within the [**CsTeamsEventsPolicy**](/en-us/powershell/module/teams/set-csteamseventspolicy) PowerShell cmdlet.

The following table outlines the behaviors of the settings for the **`-TownhallChatExperience`** parameter:

| Setting value | Behavior |
| --- | --- |
| Optimized | **This is the default value.** Organizers with this policy can turn on chat for their attendees. |
| None | Organizers with this policy can't turn on chat for their attendees. |

#### Turn off chat

To turn off chat for attendees in events optimized for large audiences, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -TownhallChatExperience None
```

#### Turn on chat

To turn on chat for attendees in events optimized for large audiences, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -TownhallChatExperience Optimized
```

### Event chat eDiscovery and storage

Meeting chat messages in events optimized for large audiences, excluding the event group chat, are stored only in an organizer's mailbox for up to 30 days. During this time, if you do a content search for the organizer, you can see all the messages that were sent in that chat. However, if you place the organizer’s mailbox on legal hold, the mailbox keeps the chat messages for longer.

When an organizer leaves the company anytime from when the event is scheduled to 30 days after the event ends, the following details apply:

- Chat might be unavailable during the event.
- Chat might be available during the event, but might not get sent to the organizer’s mailbox.
- Some messages aren't e-discoverable in the organizer’s mailbox depending on when the organizer leaves the company.

If an organizer leaves the company, reschedule the event.

You can't see which users viewed specific messages during the event. You also can't search for chat messages in an attendee's mailbox.

### Limitations

The following limitations apply to meeting chat in events optimized for large audiences:

- Chat isn't supported for events with more than 20,000 attendees.
- Chat is only available for attendees, organizers, co-organizers, and presenters during the event. Chat isn't available before or after the event.
- Attendees can only send up to 200 characters of text and emojis into the chat.
- All other message composition options that are available in a [Teams meeting chat](manage-meeting-chat) like sending pictures, sending GIFs, attaching files, or formatting text aren't supported. Hyperlinks are only supported if they're fewer than 200 characters.
- Attendees can't use `@` to mention others, reply to other chat messages using the "reply" function, or "react" to messages.
- During the event, attendees can only see the last 200 messages.
- Attendees sending chat messages might experience a 15-30 second latency from the presenters and organizers.
- If an event restarts, chat isn't available in the new event.
- Microsoft Teams Rooms on Windows with a Pro license can't use chat when they join events as a presenter.
- Chat isn't available on the GCC, GCCH, and DoD government clouds at this time.
- Chat doesn't support Information Barriers.

To view the list of platforms that support this feature, see [Platform support for Teams events features](events-platform-support).