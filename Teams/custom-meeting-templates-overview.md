---
layout: Conceptual
title: Overview of custom meeting templates in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/custom-meeting-templates-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: concept-article
ms.service: msteams
ms.subservice: meetings
ms.reviewer: idilates
ms.date: 2024-12-06T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
description: Learn about custom meeting templates in Microsoft Teams Premium.
locale: en-us
document_id: 4e36bdfd-96f6-a3b4-6ae4-23a103321c03
document_version_independent_id: 4e36bdfd-96f6-a3b4-6ae4-23a103321c03
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/custom-meeting-templates-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: custom-meeting-templates-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/custom-meeting-templates-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4fa2239b-ed21-0c4e-b098-a299f8ad96d8
---

# Overview of custom meeting templates in Microsoft Teams - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

[Microsoft Teams Premium](enhanced-teams-experience) includes the ability to create custom meeting templates. Meeting templates can be used to control meeting options that the meeting organizer normally controls. With templates, you can create consistent meeting experiences in your organization and help enforce compliance requirements and business rules.

You can use meeting templates to enforce meeting options or to set defaults. Each template option can be locked so the meeting organizer can't change it, or can be left unlocked for the meeting organizer to change if needed. Meeting options can also be hidden so meeting organizers don't see them.

You can also set a custom meeting template as the default so that it's automatically applied when users create new meetings.

Important

To select a sensitivity label in custom meeting templates, the compliance admin must first publish the label to the Teams admin's account using the Purview label policy. Teams admins can't see sensitivity labels in meeting templates unless those labels are published to their account.

The following meeting options can be controlled by using a meeting template:

| Option | Description |
| --- | --- |
| **Security** |  |
| Apply sensitivity label | Specifies the sensitivity label to be used for the meeting. |
| Lobby | Specifies who can bypass the lobby and join the meeting directly. |
| People dialing in can bypass the lobby | Specifies whether users dialing in can bypass the lobby and join the meeting directly. |
| End-to-end encryption | Specifies if the meeting is encrypted. |
| Enable watermark for screenshare | Specifies if watermarks are used for content that is shared on screen in the meeting. |
| Enable watermark for video | Specifies if watermarks are used for camera feeds in the meeting. |
| Detect sensitive content during screen sharing | Specifies whether meetings can detect sensitive content during screen sharing. |
| Restrict participants from copying or forwarding meeting chat messages | Prevents participants from copying or forwarding content in the meeting chat. |
| **Audio & video** |  |
| Allow mic and camera for attendees | Specifies if attendees can unmute and use their camera. |
| **Recording & transcription** |  |
| Recording | Specifies who can record and if the meeting is recorded automatically. |
| Allow Copilot | Specifies how transcripts are used for Microsoft Copilot in Teams meetings and events. |
| **Roles** |  |
| Announce when people dialing in join or leave | Specifies if a sound plays when people calling in by phone join or leave the meeting. |
| **Meeting engagement** |  |
| Meeting chat | Specifies if the meeting chat is available. Can also be used to prevent chat before and after the meeting. |
| Allow reactions | Specifies if attendees can use reactions or raise their hand in the meeting. |
| Q&A | Specifies if attendees can use the Q&A feature to ask questions during the meeting. |
| Manage what attendees see | Specifies if meeting organizers can preview and approve content being shared on screen before other meeting participants can see it. |

Some examples of when a template can be useful are:

- Enforcing automatic meeting recording for certain types of meetings.
- Restricting chat and attendee camera and audio and using the Q&A feature for presentation-style meetings.
- Using a stricter default for who can bypass the lobby, but allowing the meeting organizer to change the option if needed.

To learn how to create a custom meeting template, see [Create a custom meeting template in Microsoft Teams](create-custom-meeting-template).

To learn how to set a custom meeting template as the default, see [Set a custom meeting template as the default in Microsoft Teams](custom-meeting-templates-set-default).

Note

The option to select a custom meeting template when creating a new meeting isn't available on Outlook for Mac or Outlook on the web.

## Templates with sensitivity labels

Templates have the option of specifying a sensitivity label. Labels can also be applied directly to meetings, independent of templates. Sensitivity labels can control some of the same meeting options as templates:

- Apply a watermark to everyone's video feed
- Apply a watermark to shared content
- Detect sensitive content during screen sharing
- End-to-end encryption
- Meeting chat
- Prevent copying chat content to clipboard
- Record meetings automatically
- Require a verification check from
- Who can bypass the lobby?
- Who can present
- Who can record

If any of these options are configured in a sensitivity label, the label overrides the options in the template.

## Templates included with Teams

Teams includes the following default meeting template:

- Controlled-content meeting

Teams Premium includes the following default meeting template:

- [Virtual appointment](virtual-appointment-meeting-template)

Additionally, these templates are available in Teams for Education:

- Class
- Lecture
- Webinar

For information about the class and lecture templates, see [Use education templates for Teams meetings](https://support.microsoft.com/topic/9567d25f-3ac5-4fcf-9b66-18f70e5d42b3).

## Platform support

To view the list of platforms that support this feature, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-personalized-meetings).