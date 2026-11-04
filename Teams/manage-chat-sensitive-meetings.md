---
layout: Conceptual
title: Manage chat for sensitive Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-chat-sensitive-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: yilin.yang
ms.date: 2024-12-06T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
description: Learn how to manage Teams meeting chat options for sensitive meetings by using admin policies, sensitivity labels, and meeting templates.
locale: en-us
document_id: ab1a95a8-0836-900f-523b-8333c64f79d4
document_version_independent_id: ab1a95a8-0836-900f-523b-8333c64f79d4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-chat-sensitive-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-chat-sensitive-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-chat-sensitive-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 344f4681-f1da-f6a4-f08f-1f72870e34f1
---

# Manage chat for sensitive Teams meetings - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

By default, all meeting attendees can chat both during and after a meeting. Meeting organizers can turn off meeting chat or allow chat only during the meeting.

If you have compliance requirements for certain types of meetings, you can manage how and when chat is enabled by using a combination of Teams admin policies, meeting templates, and sensitivity labels. You can also prevent copying chat content to the clipboard.

Note

Meeting options in sensitivity labels and custom meeting templates require Teams Premium.

The following table show what chat-related controls are available and where they can be managed.

| Setting | Admin policy | Sensitivity label | Template | Meeting organizer |
| --- | --- | --- | --- | --- |
| Meeting chat | Yes | Yes | Yes | Yes |
| Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcripts | No\* | Yes | Yes | Yes |
| Q&A | Yes | No | Yes | Yes |

You can use the Teams admin policy to allow or prevent meeting organizers from using the **Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcripts** feature, but can't enforce the use of the feature.

By default, chat is turned on for meeting participants. There are several ways you can manage chat:

- Prevent anonymous meeting participants from using chat
- Prevent the meeting chat from being used before or after the meeting
- Preventing copying of chat, captions, and transcripts
- Turn off the chat entirely

If you want to prevent anonymous meeting participants from using chat, you must use the **Chat in meetings** Teams admin policy to exclude them. Meeting organizers, meeting templates, and sensitivity labels can't control this setting.

Meeting organizers can specify that the chat only be available while the meeting is in progress. This can also be configured by using a meeting template or sensitivity label if you require this for certain types of meetings.

## Prevent copying or forwarding chat, captions, and transcripts

As an admin, you can choose whether organizers in your organization can restrict participants from copying or forwarding meeting chat messages, live captions, transcripts, and AI-generated insights in the meeting recaps. This setting also restricts forwarding and sharing messages to Outlook. By default, this per-organizer setting is set **On**.

You can require organizers to prevent copying or forwarding of chat messages, live captions, and transcripts with a meeting template or sensitivity label. If you don't enforce this option with a template or sensitivity label, meeting organizers can control this feature in their meeting options.

### Allow participants to copy or forward chat messages, live captions, and transcripts

Note

Currently, prevent copy meeting option only applies to live captions, transcript and recap content inside of Teams.

If you want meeting participants to copy or forward meeting chat messages, you must use a Teams admin policy to turn off the setting. When you use a policy to turn off this feature, organizers won't see the **Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcripts** setting in their meeting options or template. Meeting organizers who have this feature turned **Off** in their assigned policy can't prevent participants from copying or forwarding of chat messages, live captions, and transcripts in meetings they organize.

To allow participants to copy or forward meeting chat content, use the following steps:

1. In the Teams admin center, expand **Meetings**, and then select **Meeting policies**.
2. Choose the policy that you want to update, or create a new one.
3. In the **Content sharing** section, set **Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcripts** to **Off**
4. Select **Save**.

Meetings with a sensitivity label that prevents copying chat content to the clipboard override the Teams admin policy.

Important

If a sensitivity label that restricts copying from the chat is specified as the default channel label in a container label, then teams with that container label will restrict copying from the chat for all channels in the team, both in and out of channel meetings.

### Platform support

To view the list of platforms that support this feature, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-advanced-management-for-meetings).

## Options for meetings without chat

Some organizations require that meeting chat be turned off entirely for certain types of meetings. For example, an organization that holds meetings where personal data is discussed might want to turn off the meeting chat because of the regulatory requirements around storing this information.

For meetings where sensitive or highly sensitive information is shared and you want to turn off the meeting chat, you can enforce this requirement by using a meeting template or sensitivity label.

In meetings where the chat isn't available, meeting organizers can turn on the [Q&A feature](https://support.microsoft.com/office/f3c84c72-57c3-4b6d-aea5-67b11face787). This allows attendees to ask questions or comment in writing. This feature is available but off by default for meeting organizers. Teams administrators can prevent meeting organizers from using it by turning off the **Q&A** admin meeting policy or disabling it in a meeting template.

By default, Teams also allows meeting attendees to [create shared meeting notes](https://support.microsoft.com/office/3eadf032-0ef8-4d60-9e21-0691d317d103), [use annotation while sharing your screen](https://support.microsoft.com/office/876ba527-7112-437e-b410-5aec7363c473) and use the [whiteboard](https://support.microsoft.com/whiteboard). While the meeting organizer can't turn off these features, you can turn them off for people and groups by using meeting policies in the Teams admin center.