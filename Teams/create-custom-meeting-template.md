---
layout: Conceptual
title: IT admins - Create a custom meeting template in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/create-custom-meeting-template
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
ms.reviewer: idilates
ms.date: 2024-11-19T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
- Tier1
description: Learn how Microsoft Teams administrators can create a custom meeting template to set or enforce meeting organizer options for enhanced meeting security and compliance.
locale: en-us
document_id: 0cfc2fcd-9c92-c26d-c016-bf503790130d
document_version_independent_id: 0cfc2fcd-9c92-c26d-c016-bf503790130d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/create-custom-meeting-template.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-custom-meeting-template
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/create-custom-meeting-template.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 508188b3-5565-9fce-aee0-27a77d1d564a
---

# IT admins - Create a custom meeting template in Microsoft Teams - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

Microsoft Teams Premium's custom meeting templates allow you to specify values for many of the meeting options available to meeting organizers. Templates can be used to configure options that meeting organizers can change or can be used to lock options so that meeting organizers can't change them. For more information about custom meeting templates, see [Overview of custom meeting templates in Microsoft Teams](custom-meeting-templates-overview).

You can create up to 50 custom templates. For information on how to manage which templates are available to your user, see [Manage meeting templates in Microsoft Teams](manage-meeting-templates).

For each option in the template, you can define the following:

- **Default value** - This is the value that's applied to a meeting when the template is used.
- **Visibility** - This determines if the meeting organizer can see this option.
- **Lock status** - This determines if the meeting organizer can change the option that was set by the template. If the option is locked, the meeting organizer can't change it.

## Video demonstration

Watch this video for a walkthrough of the procedures described in this article. 

## Create a custom meeting template

Use this procedure to create a custom meeting template in the Teams admin center.

To create a custom meeting template

1. In the Teams admin center, expand **Meetings** and select **Meeting templates**.
2. Select **Add**.
3. Enter a name and description for the template. The name and description truncates after 40 characters when viewed in Teams, but the full name and description are viewable on hover.
4. Choose the options that you want to use for this template. (See the sections below for descriptions of each option.)
5. To prevent the meeting organizer from changing an option, select the option and then select **lock**.
6. To prevent the meeting organizer from seeing an option, select the option and then select **Hide**.
7. Select **Save**.

    Once you create the template, it might take up to 24 hours for your users to see it.

    If you change the options of an existing template, the changes affect new meetings scheduled using that template, as well as any meetings that are already scheduled with that template.

### Security

| Option | Description |
| --- | --- |
| Apply sensitivity label | Specifies the meeting sensitivity label to use for the meeting. Note that the sensitivity label may override certain options in the template. Once you save the template, the label can't be changed in the template, but organizers can change the label if you leave the option unlocked. |
| Who can bypass the lobby? | Specifies who can bypass the lobby and join the meeting directly. |
| People dialing in can bypass the lobby | Specifies if people calling in by phone can bypass the lobby and join the meeting directly. |
| End-to-end encryption | Specifies if the meeting uses end-to-end encryption. Recording and transcription don't work if this setting is on. |
| Enable watermark for screenshare | Specifies if a watermark is overlaid on content that is shared on screen in the meeting. |
| Enable watermark for video | Specifies if a watermark is overlaid on attendees' video feeds in the meeting. |
| Detect sensitive content during screen sharing | Specifies whether meetings can detect sensitive content during screen sharing. |
| Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcripts | Prevent participants from copying messages, links, live captions, transcripts, and AI-generated insights in the meeting recaps. This setting also prevents forwarding and sharing messages to Outlook. |

### Audio & video

| Option | Description |
| --- | --- |
| Allow mic for attendees | When **On**, attendees can unmute. |
| Allow camera for attendees | When **On**, attendees can turn on their cameras. |

### Recording & transcription

| Option | Description |
| --- | --- |
| Record meetings automatically | When **On** meetings are recorded automatically. |
| Who can record | Specifies whether meetings can be recorded by organizers and co-organizers only or by organizers, co-organizers, and presenters. |
| Allow Copilot | Specifies when Copilot is available and how Copilot uses meeting transcripts. |

### Roles

| Option | Description |
| --- | --- |
| Announce when people dialing in join or leave | Specifies if a sound is played when people calling in by phone join or leave the meeting. |

### Meeting engagement

| Option | Description |
| --- | --- |
| Meeting chat | Specifies if the meeting chat is available. Can also be used to prevent chat before and after the meeting. |
| Allow reactions | Specifies if attendees can use reactions in the meeting. This must be **On** for the raise hand feature to work. |
| Q&A | Specifies if attendees can use the Q&A feature to ask questions during the meeting. |
| Manage what attendees see | When **On**, meeting organizers can preview and approve content being shared on screen before other meeting participants can see it. |