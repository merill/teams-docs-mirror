---
layout: Conceptual
title: Intelligent recap for Teams calls, meetings, and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/intelligent-recap-calls-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: mabond
author: mkbond007
manager: pamgreen
ms.reviewer: weizxue, nijait, benjamin.olson, harinlee, chenanqi
ms.date: 2026-05-07T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
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
- magic-ai-copilot
- m365initiative-voice
description: Learn how to manage intelligent recap for Teams calls, meetings, and events. Understand the licenses your users need to use intelligent recap for VoIP and PSTN calls and audio recap.
locale: en-us
document_id: a11c126d-7350-3c68-22b3-d19f55898869
document_version_independent_id: a11c126d-7350-3c68-22b3-d19f55898869
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/intelligent-recap-calls-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: intelligent-recap-calls-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/intelligent-recap-calls-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 56c0ce21-d20f-fd02-96cc-d543878e7779
---

# Intelligent recap for Teams calls, meetings, and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Calls

Intelligent recap for Microsoft Teams uses AI technology to improve your users' productivity and efficiency. This article helps you, as an admin, understand intelligent recap prerequisites and capabilities.

To learn more about how your users use intelligent recap in their meetings, see [Meeting recap in Microsoft Teams](https://support.microsoft.com/office/c2e3a0fe-504f-4b2c-bf85-504938f110ef#bkmk_intelligent_meeting_recap).

For Teams events, intelligent recap is available only to organizers, co-organizers, and presenters. Attendees don't have access to intelligent recap.

Note

For scheduled meetings, intelligent recap is also available without saving meeting transcripts. This experience requires a Microsoft Copilot license. For more information, see [Intelligent recap in Teams meetings without saving transcripts](intelligent-recap-without-saving-transcripts).

## Prerequisites

Intelligent recap is automatically available to users in your organization with the following required licenses and policies.

### Licensing

- You must assign your users a Microsoft 365 subscription that includes Teams or a Microsoft 365 (no Teams) subscription with a separate Teams license.
- You must assign a Teams Premium license or Microsoft Copilot license to your users. For audio recap, you must assign a Microsoft Copilot license.
- For Public Switched Telephone Network (PSTN) calls, you must also assign a Teams Phone license and have a calling plan for your users. For information on Teams Phone licensing, see [Microsoft Teams add-on licenses](/en-us/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing). To learn more about PSTN connectivity options, see [PSTN connectivity options](pstn-connectivity).

### Policies

#### Transcription

To allow your users to use intelligent recap, you must turn on transcription:

- **PSTN, 1:1 peer-to-peer Voice over Internet Protocol (VoIP) calls:** To turn on transcription, see [Configure call recording, transcription, and captions in Teams](call-recording-transcription-captions#enable-call-transcription).
- **Meetings, events, and group VoIP calls:** To turn on transcription, see [Admins - Manage transcription and captions for Teams meetings](meeting-transcription-captions#live-transcription).

#### Recording

For the full recap experience for meetings and events, you must assign a policy that allows recording for your users. If recording is turned off, users experience recap without the recording, speakers, topics, and chapters. To turn on recording for meetings and events, see [Manage Teams recording policies for meetings and events](meeting-recording#allow-or-prevent-users-from-recording).

## Intelligent call recap

Intelligent call recap uses AI to allow your users to focus during their calls and save time on follow-ups.

### PSTN calls

PSTN calls are made and received using a phone number. Your users can access AI-generated notes and recommended tasks for PSTN calls through the **Recap** button in the Calls app in Teams.

[![Screenshot that shows PSTN call](media/intelligent-recap-calls-meetings/pstn-call.png)](media/intelligent-recap-calls-meetings/pstn-call.png#lightbox)

### 1:1 peer-to-peer and group VoIP calls

1:1 peer-to-peer and group VoIP calls are made between Teams users. Your users can access AI-generated notes, recommended tasks, speakers, topics, mentions, and chapters for 1:1 and group peer-to-peer calls through the **Recap** button in the call's chat in Teams or through the call details in the Calls app.

[![Screenshot that shows VoIP Call w. background](media/intelligent-recap-calls-meetings/voip-call-w-background.png)](media/intelligent-recap-calls-meetings/voip-call-w-background.png#lightbox)

## Intelligent meeting recap

Intelligent meeting recap uses AI to help your users focus on the meeting discussion instead of taking notes. This feature allows them to find key information, access highlights, and save time on follow-ups.

After the meeting or event ends, your users can access the following AI powered features for their meetings through the **Recap** tab in the Teams calendar and chat:

- AI meeting notes
- AI recommended tasks
- Personalized timeline markers show when users' names were mentioned, when screens were shared, and when they joined or left the meeting.
- Speaker timeline markers show who spoke during the meeting, when they spoke, and allows your users to jump to that moment.
- Meeting chapters divide the meeting into chapters, and meeting topics that allow your users to jump to a point in the meeting when a certain topic was discussed.
- Audio recap provides a podcast-like summary of the selected meeting's content, allowing users to quickly catch up on what was discussed in multiple meetings.
- Video recap provides a narrated summary with short video clips that highlight important moments in a meeting. Users can stay informed and quickly catch up on what happened during a meeting with visual context.

[![Screenshot of intelligent meeting recap from the Recap tab.](media/intelligent-meeting-recap.png)](media/intelligent-meeting-recap.png#lightbox)

### Intelligent recap for external meetings

Intelligent meeting recap for external meetings allows your users to share the meeting's recap with external attendees. To share the recap via Outlook with specified external attendees, after the meeting, in the **Recap** tab, users can select **Share** &gt; **Share via Outlook**.

To manage policies that allow external attendees to attend meetings in your organization, see [IT Admins - Manage external meetings and chat with people and organizations using Microsoft identities](trusted-organizations-external-meetings-chat).

### Intelligent recap for multilingual meetings

Note

This feature is currently in Public preview.

Note

Intelligent meeting recap for multilingual meetings doesn't currently support events [optimized for large audiences](plan-events).

Intelligent meeting recap for multilingual meetings translates the meeting's recap into each participant's language. When the meeting ends, the recap appears in the language each participant selected for live translated transcription. Intelligent meeting recap for multilingual meetings currently supports translation in the following languages: English, Spanish, Japanese, French, German, Portuguese, Italian, Mandarin (Simplified Chinese), and Korean.

To learn more about live translated transcription, see [View live transcription in Microsoft Teams meetings](https://support.microsoft.com/office/dc1a8f23-2e20-4684-885e-2152e06a4a8b#bkmk_livetranslated).

### Audio recap

Note

This feature is currently in Public preview.

Audio recaps create a single content summary of up to eight meetings, allowing users to stay informed on the day's key discussions, critical decisions, and actionable takeaways.

Users can generate and listen to audio recaps for transcribed (or recorded) scheduled meetings on Teams desktop and mobile clients. Audio recaps are stored for 60 days within a user's OneDrive under **Documents** (or **My files** if accessing online) &gt; **Recordings** &gt; **AudioRecaps**.

For information about how your users can create and access audio recaps, see [Listen to audio recaps of your meetings](https://support.microsoft.com/office/04bd2828-5c4e-4132-ac86-a87b9ec28984).

#### Known limitations

- If a user selects a meeting with a transcription that's too short to generate insight, it isn't included in the final audio recap​.
- Occasionally, some chapters might fail to generate due to transcription quality or technical issues. These chapters are skipped in the final episode. ​
- Audio recaps, including voices, are AI-generated and might contain inaccuracies or audio glitches.

### Video recap

Video recap creates narrated highlights from recorded and transcribed meetings. This feature combines AI-generated summaries with short video clips from the recording, highlighting important moments while preserving the meeting's overall tone and flow. Users can quickly catch up on key takeaways, decisions, and discussion points with essential visual context.

Video recap data is stored as part of the original Teams meeting recording file in OneDrive or SharePoint. Each highlight adds a small amount of data (short clip and associated transcript), with up to 100 highlights allowed per recording. To learn more about meeting recording and transcript storage, see [Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change).

Users can view video recaps for recorded and transcribed meetings on Teams desktop and mobile clients.

#### Known limitations

- The meeting must be at least 10 minutes long.
- Video recap isn't available for meetings that are transcribed but not recorded. Meetings with only transcription can generate recap insights but don't support video highlights.

## Supported meetings and call types

Intelligent recap is supported on the following types of meetings and calls:

- Meetings: Meetings scheduled in the Teams client, meetings scheduled in Outlook, meet now, and events. Audio recap is only available for scheduled meetings.
- Calls: PSTN, 1:1, group peer-to-peer

## Platform support

To view the list of platforms that support the intelligent recap feature, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-intelligent-meetings).

## Data and privacy

For details on data and privacy for intelligent recap, see [Data, privacy, and security for intelligent recap in Teams Premium](/en-us/microsoftteams/privacy/intelligent-recap).