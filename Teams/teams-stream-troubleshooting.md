---
layout: Conceptual
title: Troubleshooting live streaming in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-stream-troubleshooting
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: troubleshooting-general
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
ms.reviewer: christi.balaki,cmunden
ms.date: 2025-03-28T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
description: This article discusses troubleshooting options for Microsoft Teams streaming events.
ms.localizationpriority: medium
ms.custom: 
locale: en-us
document_id: f758c73e-1237-111e-1f60-542ddc25f8ea
document_version_independent_id: f758c73e-1237-111e-1f60-542ddc25f8ea
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-stream-troubleshooting.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-stream-troubleshooting
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-stream-troubleshooting.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
platformId: 4c1cf1f2-8142-18c6-9e7a-6181ec457877
---

# Troubleshooting live streaming in Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

Important

**China**: Users located in China won't be able to set up or attend Teams or Viva Engage live events or view videos on-demand because currently, Azure CDN, which these apps rely on, might not be accessible in China.

As an administrator, you might need to set up a VPN to connect your corporate network for these apps to work seamlessly. Once that's complete, people in your organization can schedule and attend live events.

## Before a live event

### Make sure all events are reachable in your network

#### General Teams endpoints

Teams requires connectivity to the internet. All endpoints listed on [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges) need to be reachable by users of Teams within your organization's network.

#### Teams Encoder live events - RTMP ingest endpoints

To get a video feed for a Teams Encoder live event sent to Teams from your encoder, you need the domain name and ports open in your network's firewall:

- **Domains**: \*.rtmpingest.mcr.teams.microsoft.com
- **Ports**: 1935/1936 (for RTMP/RTMPS)

### Make sure you have enough upload bandwidth

When producing or streaming a live event via RTMP, it’s possible that the internet upload bandwidth at the site pushing the live stream might not be enough. Low upload bandwidth might result in dropped frames or issues in the live video itself, which might result in playback issues for viewers.

Make sure that your upload speed for the machine and network pushing the live stream is higher than the bitrate you set for the live stream. If you're outputting a 5 Mbps stream from your encoder but your upload bitrate is close to or lower than 5 Mbps, you could run into problems not being able to upload your stream fast enough.

If you have issues with upload bandwidth, here are a few things you can try:

1. Use a hard-wired ethernet connection for any machine you're pushing the stream from to avoid any drops in WiFi.
2. Lower the encoding bitrate of your live feed to a value well below your max upload speed.

### Preparing your network for many concurrent viewers

Many viewers watch live events, which can strain your network and download bandwidth. It's important to evaluate your network infrastructure and ensure that there's enough bandwidth for viewers within your corporate network. To help reduce internet traffic needed for live events, there are two options:

1. Configure existing cache proxies within your network to cache videos from Teams.
2. Use a partner eCDN video delivery solution to optimize video traffic.

Viewers receive the Teams live event's stream via TCP HTTPS. The following URLs should bypass any proxy servers within your environment, and have SSL inspection disabled:

- \*.bmc.cdn.office.net
- \*.ml.cdn.office.net
- \*.cdn.ml.gcc.teams.microsoft.com (Microsoft 365 U.S. Government Community Cloud (GCC))
- \*.cdn.ml.gov.teams.microsoft.us (Microsoft 365 U.S. Government GCC High Cloud (GCC High))
- \*.cdn.ml.dod.teams.microsoft.us (Microsoft 365 U.S. Government DoD Cloud (DoD))

### I can't create a live event

Users require specific permissions in both Microsoft Teams and Viva Engage to create a live event, depending on the service being used.

1. Verify that your Teams admin enabled you to create live events.
2. Check with your administrator that you have a valid Teams license that allows you to create live events.
3. Select **Run Tests**, which populates the diagnostic in Microsoft 365 admin center to help you validate if a user is able to schedule Teams live events.

### Make sure viewers have permission to watch the event

Microsoft Teams live events have a few different roles for permissions on the event itself (organizer, producer, presenter, attendee).

For more information, see [Microsoft Teams event group roles](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles).

## Producing a live event

### I don't know how to set up my encoder

To get started, see [Use an encoder for streaming with Microsoft Teams](teams-encoder-setup).

### My encoder isn't connecting to the server ingest URL

- Check that the RTMP URL is correctly entered as the output of your encoder.
- Check that the RTMP Key is correctly entered as the output of your encoder.
- Check the status of your internet connection to ensure that your encoder is correctly connected and online.
- You might have network security or firewall-related settings that might be blocking the output of your connection.
- Your encoder might not be supported with Teams. Check out the list of tested encoders in [Use an encoder for streaming with Microsoft Teams](teams-encoder-setup).

### I can't get RTMPs to work

- Some encoders might support an implementation that Teams doesn't support. Check out the list of tested encoders that work with Teams in [Use an encoder for streaming with Microsoft Teams](teams-encoder-setup).
- Not all encoders or versions support RTMPs. Check with the manufacturer or software creator to see what they support.

### I tried to start setup and it's taking a long time

In general, it can take a few minutes to get the setup going before you can start pushing your encoder. If the service is busy, setup may take longer, so we recommended allocating sufficient time before your scheduled live event.

### I tried to start setup but there are too many events happening

When starting an event, if you get a message indicating the maximum number of events has been reached, contact a Teams admin. A Teams admin can prioritize your high priority event by stopping others if necessary.

### I can't see producer view

1. It might take a few seconds for the producer preview to appear after you start streaming from your encoder.
2. Make sure that the encoder is connected to Teams.
3. It can sometimes help to refresh the page in Teams. You might be asked if you want to leave the page; this doesn't affect your live event.
4. Some networks might block access to content. Ensure that your network security and firewall settings allow the RTMP protocol and the [required domains](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges) are in the allowed list. It can help to try to see if it works on a different network environment, independent from a corporate network, VPN, or locked-down network.

### My feed looks bad, has poor quality, or is glitchy

1. Ensure that there's sufficient upload bandwidth from your streaming device. Low bandwidth might result in dropped frames or poor video quality. Upload bandwidth should exceed the streaming bitrate.
2. Make sure you're using the recommended encoder settings for Teams. See [Configuring encoders for live event streaming in Microsoft Teams](teams-encoder-configuration) for more info.
3. Verify that the audio/video coming into the encoder doesn't have any issues. Source audio or video feeds sent to the encoder may have issues, leading to a poor viewer experience.
4. Monitor CPU load on your encoder. Maxing out your CPU could stem from source content or bitrate. Try simplifying overlays/content or lowering streaming bitrate.
5. Make sure your encoder is up to date. If it's a hardware encoder, ensure you have the latest firmware updates. If it's a software encoder, make sure you're running the latest version.
6. Try resetting or restarting your encoder. If you do this during a live stream, your viewers see an error during playback while your encoder is restarting. After you restart live streaming from the encoder, viewers must reload the page to get the live stream again.

### I ended my live event from my encoder, but viewers are seeing an error

Select **Stop event** before disconnecting your encoder. If you already disconnected your encoder, you can still select **Stop event**, but viewers might see an error.

### My viewers are seeing issues

- If a single viewer is reporting an issue, ensure that the viewer has enough bandwidth and is on a good internet connection to watch the event.
- If multiple people within the same network are having issues, you might be experiencing network congestion related issues. To see if you can identify a solution to your issue, see [Enterprise content delivery networks for streaming Microsoft Teams events](streaming-ecdn-enterprise-content-delivery-network).
- Many times, when multiple viewers are seeing an issue, it's related to the encoder feed.
    - Check that the encoder is properly set to the specifications outlined in the encoder setup, and configured correctly.
    - Ensure that you have enough upload bandwidth to stream. You can try reducing the bandwidth from the encoder output.
    - Sometimes resetting the encoder helps, but note that you must maintain the same settings when reconnected. Audience members might see an error or glitch in the live event.

### I, or my viewers, can't hear the video

1. Check that the encoder is sending audio.
2. Check that the audio device is plugged in.
3. If on Windows, make sure the correct audio device is selected and unmuted.
4. If there was an encoder disruption, some browsers or devices might not be able to recover and play back the audio correctly.

Note

If you've deployed Microsoft eCDN as your video distribution provider for live events, please refer to [Troubleshooting eCDN performance issues](/en-us/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) for more details on troubleshooting the eCDN performance issues you may be experiencing.