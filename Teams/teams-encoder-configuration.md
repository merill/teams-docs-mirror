---
layout: Conceptual
title: Encoder configuration for streaming in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-encoder-configuration
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: article
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
ms.reviewer: christi.balaki,cmunden
ms.date: 2024-10-03T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
description: This article discusses encoder-based RTMP configuration for Microsoft Teams streaming events.
ms.localizationpriority: medium
ms.custom: 
locale: en-us
document_id: 967cbadd-bd42-113a-f501-b311459444db
document_version_independent_id: 967cbadd-bd42-113a-f501-b311459444db
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-encoder-configuration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-encoder-configuration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-encoder-configuration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ddc6de92-837a-faf1-bcec-89f2415d698f
---

# Encoder configuration for streaming in Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

Teams accepts live feeds from various different encoders that output RTMP or RTMPS. Each encoder is different, so make sure to follow the guidelines for the encoder configurations when sending to Teams.

To learn how to set up a live event in Teams, see [Set up for live events in Microsoft Teams](/en-us/MicrosoftTeams/teams-live-events/set-up-for-teams-live-events). If you're already using an encoder integrated with Teams, see [Use an encoder for streaming with Microsoft Teams](teams-encoder-setup).

## Configuration Steps

After you schedule the live event using Teams or Viva Engage, and select the **Teams Encoder** option, you can retrieve the RTMP URL and key from the meeting invite and use them to send the feed into the Teams producer UI.

### Gather the RTMP information

#### Scheduled in Teams

1. Open the Teams client and navigate to the **Calendar**.
2. Select the scheduled live event and select the double arrow button to see the invite details.
3. Go down to the **RTMP in details** section.
4. Select the **Get RTMP** link to copy the RTMP ingest URL to the clipboard.
5. Select the **Get RTMP key** to copy the RTMP key to the clipboard.

#### Scheduled in Viva Engage

1. Navigate to the Viva Engage community where the event was scheduled.
2. Select the **Events** tab to see upcoming scheduled events.
3. Select the desired event to bring up the details page.
4. On the right side, under **Produce**, Select the **RTMP information** link to expose the RTMP URL and key.

## Encoder Setup

1. Once you collect the RTMP information, ensure your encoder is configured with the correct settings in the recommended encoder settings section.
2. Enter the RTMP URL and Key into your encoder's streaming settings (refer to the manufacturer's documentation for specifics).
3. Configure your encoder with the desired audio and video sources.
4. Open the Teams client and join the live event as a Producer.
5. Start streaming from the encoder to the Teams RTMP ingest URL.
6. In the Teams Producer window, after a few seconds, the encoder's RTMP feed appears in the presenter area.
7. Select the RTMP feed in the presenter area to place it into the queue on the left side.
8. When you're satisfied with the feed, select **Send Live** - the feed then also appears on right side of the Producer window.
9. Select **Start** to begin the stream.

## Recommended encoder settings

### Ingest protocols

- Single bitrate RTMPS or RTMP

### Video format

- Aspect Ratio: 16:9
- Codec: H.264
- Profile: High (Level 4.0)
- Bitrate: 720p up to 5 Mbps (5,000 kbps) | 1080p up to 10 Mbps (10,000 kbps)
- 720p - Strict Constant Bitrate (CBR) | 1080p - Strict Constant Bitrate (CBR) or Variable Bitrate (VBR)
- Keyframe/GOP: 2 seconds

    - There must be an IDR frame at the beginning of each GOP
    - Frame Rate: Minimum 29.97 fps or 30 fps
    - Resolution: 1280 x 720 (720 P) | 1920 x 1080 (1080p)
    - Interlace Mode: Progressive

### Audio format

- Codec: AAC (LC)
- Bitrate: 192 kbps
- Sample Rate: 48 kHz or 44.1 kHz (recommend 48 kHz)

### Playback requirements

- Both an audio and video stream must be present in order to play back content in Teams.

### Configuration tips

- Whenever possible, use a hardwired internet connection.
- When determining bandwidth requirements, it's advisable to double the streaming bitrates. While doubling the streaming bitrates isn't a mandatory requirement, it helps mitigate network congestion.
- When using software-based encoders, close any unnecessary programs.
- Don't change your encoder configuration after it starts pushing. It has negative effects on the event and can cause the event to be unstable. If you want to change encoder configurations before the event starts, you must disconnect using the producer controls in Teams and start setup again.
- If the encoder is disconnected during the live event, reconnect it keeping the same timestamps of continuing process. Any discontinuity might cause audio or video issues on certain browsers and devices.
- Give yourself ample time to set up your event. For high scale events, it's recommended to start the setup an hour before your event.
- If you're using the vMix encoder for RTMP-In, make sure to select the FFMPEG6 option from the **Application** drop-down menu in the vMix encoder settings.