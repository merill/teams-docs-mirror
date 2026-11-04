---
layout: Conceptual
title: Introduction to recording Microsoft Teams calls, meetings, and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-recording-policy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
ms.date: 2024-11-11T00:00:00.0000000Z
audience: Admin
ms.topic: concept-article
ms.service: msteams
ms.subservice: meetings
ms.reviewer: ritikag
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about Teams recordings for calling, meetings, and events.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- m365initiative-meetings
- m365initiative-voice
- purview-compliance
locale: en-us
document_id: 896e3ed7-aaf5-ad40-9a5f-1374d85c3e82
document_version_independent_id: 253d2a6b-9225-723a-cbc1-c296c3cfd36c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-recording-policy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-recording-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-recording-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 933f82ff-821d-a47c-b2e4-703cc77fe732
---

# Introduction to recording Microsoft Teams calls, meetings, and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Calls

## Overview

In Microsoft Teams, your users can record calls, meetings, and events to reference later and share with others. Communications can also be automatically preserved for industry compliance reasons. Recordings capture media shared during the session (audio, video, and screen sharing activity), and are stored according to your policies.

There are two recording features that can be enabled with policy:

- **Convenience recording**: An ad-hoc recording of a call, meeting, or event that a user starts and manages. For an overview of convenience recording, see [Overview- Recording and transcription for Teams meetings and calls](recording-transcription-overview).
- **Compliance recording**: Calls, meetings, and events that are automatically recorded without user intervention and owned by the company, using a third-party solution.

The following table compares convenience and compliance recording.

| Property | Native convenience recording | Third-party compliance recording |
| --- | --- | --- |
| Recording initiator | Licensed Teams user, enabled with meeting / calling policy | Admin (system) |
| Storage and access owner | [Meeting storage and permissions](tmr-meeting-recording-change) | Admin / compliance officer |
| Participant notification enforced | Yes | Yes |
| Participant consent supported | Yes | No |
| Media recorded | Voice, video, screen share, PPT Live | Voice, video, screen share |
| Retention policy | [Meeting storage and permissions](tmr-meeting-recording-change) | Configurable with partner solution |
| Recording policy | Configurable with Teams admin center (Meeting, Calling, and Events policy settings) | Configurable with user policy |
| Audio only supported | Yes | No |

#### Considerations

- Guests can't initiate convenience recordings.
- Users in trusted organizations can't initiate convenience recordings when they join meetings in your organization.
- Users in trusted organizations can initiate convenience recordings of unscheduled, 1:1 calls originated by either party. If they initiate, the recording adheres to the calling policy defined in the trusted organization's tenant.
- Users assigned with Edu A1 license only, can record manually but can't use meeting options to auto-record.

Meeting recordings don't capture:

- More than four people's video streams at once
- Whiteboards and annotations
- Shared notes
- Content shared by apps
- Videos or animations embedded in PowerPoint Live presentations
- Multi-screen share
- Attendee video streams in events [optimized for large audiences](plan-events) and in live events

Calls in Teams are unscheduled, peer-to-peer Teams client sessions (encompassing internal and external Teams users). In convenience recording, policy scope for calls includes Teams PSTN calls, if the user has one of the following licenses: Microsoft 365 E5, Office 365 E5, or Microsoft/Office 365 E3 with Teams Phone Add-on license.

Tip

To learn more about recording options that you might allow your users to control, see [Record a meeting in Microsoft Teams](https://support.microsoft.com/office/record-a-meeting-in-microsoft-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24). 

## Managing recording policies

For more specific details on convenience and compliance recording, see the following resources.

| Meeting convenience recording | Call convenience recording | Meeting and call compliance recording |
| --- | --- | --- |
| [Manage Teams recording policies for meetings and events](meeting-recording) | [Manage Teams recording policies for calls](call-recording-transcription-captions) | [Third-party compliance recording for Microsoft Teams calls, meetings and, call queues](teams-recording-compliance) |

### Related articles

- [Teams settings and policies reference](settings-policies-reference)
- [Overview- Recording and transcription for Teams meetings, events, and calls](recording-transcription-overview)