---
layout: Conceptual
title: Stream classification in Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/stream-classification-in-call-quality-dashboard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: jamp
ms.date: 2026-06-16T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Learn how stream quality is classified in the Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business.
locale: en-us
document_id: c697f3c0-3a9b-d02d-ca6c-3a05cd0e8890
document_version_independent_id: c3f9010d-9ec1-3453-05e3-2ed473a66b80
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/stream-classification-in-call-quality-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: stream-classification-in-call-quality-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/stream-classification-in-call-quality-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 98d88377-1709-cf4e-69b0-e797b7b5bdf7
---

# Stream classification in Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn

The Call Quality Dashboard (CQD) for Microsoft Teams allows you to gain insights into the quality of calls made using Microsoft Teams. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to set it up, see [Set up Call Quality Dashboard](turning-on-and-using-call-quality-dashboard).

For a broader and deeper view of call telemetry that looks at several factors to determine perceived user experience of calls and to identify possible root cause when there's a suspected degradation in quality, see [Intelligent media quality classifiers in CQD](cqd-intelligent-media-quality-classifiers).

## Classifier Definitions

Streams in CQD are classified as *Good*, *Poor*, or *Unclassified* based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables that follow. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a *Poor* classification. For more information on these dimensions, see [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard).

### Audio Classifier

If one or more of the following conditions are met and Packet Utilization is &gt; 500 packets, an audio stream is marked as *Poor*:

| Metric | Scenario | Condition | Explanation |
| --- | --- | --- | --- |
| Round Trip | ALL | &gt; 500 | Average round-trip network propagation time, computed in milliseconds. Details available in [RFC3550](https://tools.ietf.org/html/rfc3550). |
| Packet Loss Rate | ALL | &gt; 0.1 | Average packet loss rate for stream. |
| Jitter | ALL | &gt; 30 | Average jitter for stream in milliseconds. |

Note

The Audio Classifier uses basic network performance telemetry to assess if the optimal conditions for good quality audio were present. If any one of the thresholds breaks, then we mark the audio as *Poor*, but this doesn't mean the audio stream was actually of poor quality, nor does it mean the user perceived a quality issue. The Teams media stack is built to withstand and correct for poor network conditions, and can mitigate considerable network performance degradation in excess of the thresholds above before a drop in quality is perceived by users. We recommend admins make every effort to build and configure their networks and Teams deployments for the best possible quality, and the above metrics are a useful guideline to assess performance of those networks.

### Video Classifier due to Freeze

The video stream is marked *Good* or *Poor* based on the value of a classifier score generated to estimate that the end user experienced Frozen Video. This classifier is available for Microsoft Teams product only.

| Step # | Metric | Scenario | Condition | Classification if Condition is True | Classification if Condition is False | Classification if Metric is Unavailable | Explanation |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Video Poor Due to Freeze Classifier | Is Server Pair is Client : Server | &gt;0.246 | *Poor* | *Good* | *Unclassified* | A Score between 0 and 1 that is generated based on a combination of user experience, freeze duration statistics, and overall call experience |
| 2 | Video Poor Due to Freeze Classifier | Is Server Pair is Client : Client | &gt;0.524 | *Poor* | *Good* | *Unclassified* | A Score between 0 and 1 that is generated based on a combination of user experience, freeze duration statistics, and overall call experience |

### Video Classifier

Assuming a video stream's Packet Utilization is &gt; 500 packets, the video stream is marked as *Good* or *Poor* based on the value of the first available metric in the following order:

| Step # | Metric | Condition | Classification if Condition is True | Classification if Condition is False | Classification if Metric is Unavailable | Explanation |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Video Local Frame Loss Percentage Avg | &gt; 50% | *Poor* | *Good* | Proceed to step 2 | Average percentage of video frames lost as displayed to the user. The average includes frames recovered from network losses. |
| 2 | Video Frame Rate Avg | &lt; 7 | *Poor* | *Good* | Proceed to step 3 | Average frames per second received for a video stream, computed over the duration of the session. |
| 3 | Video Post FECPLR | &gt; 0.15 | *Poor* | *Good* | *Unclassified* | Packet loss rate after FEC has been applied, aggregated across all video streams and codecs. |

### VBSS Classifier

A VBSS stream is marked as *Good* or *Poor* based on the value of the first available metric in the following order:

| Step # | Metric | Condition | Classification if Condition is True | Classification if Condition is False | Classification if Metric is Unavailable | Explanation |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Video Local Frame Loss Percentage Avg | Codec is NOT H264SAndStreamDirection is InboundIf FrameLoss &gt; 50% | *Poor* | *Good* | *Unclassified* | Average percentage of video frames lost as displayed to the user. The average includes frames recovered from network losses. FrameLoss is only used for classifying inbound non-H264S streams. |
| 2 | Video Frame Rate Avg | &lt; 1 | *Poor* | *Good* | *Unclassified* | Average frames per second received for a video stream, computed over the duration of the session. Applies to all outbound streams and either StreamDirection for H264S. |

### Application Sharing Classifier

An application sharing stream is marked as *Poor* if one or more of the following conditions are met:

| Metric | Condition | Explanation |
| --- | --- | --- |
| Spoiled Tile Percent Total | &gt; 36 | Percentage of tiles that are discarded instead of sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles might be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | &gt; 400 | Average latency in milliseconds processing tiles on the RDP Stack at the conferencing server. |
| AppSharing Relative OneWay Average | &gt; 1.75 | Average relative one-way delay between the endpoints in seconds for application sharing streams. |

## Unclassified Streams

In CQD, a stream is marked *Unclassified* when Interactive Connectivity Establishment (ICE) connectivity fails or when all the metrics required to compute the stream classification aren't reported.

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream is marked as *Unclassified*.

If ICE connectivity succeeded for an *Unclassified* stream, the stream is likely considered *Unclassified* because key stream metrics weren't reported. There are a few reasons these metrics might not be reported:

- **QoE reports weren't received** — The metrics used for classification are reported in a QoE report sent at the end of a call. If this report isn't produced (for example, because some third-party endpoints might not send QoE) or couldn't be sent (for example, because of a network outage), CQD is unable to classify the stream.

    Tip

    The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. This dimension has a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.
- **Short calls** — Short calls might not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

    Tip

    The dimensions "Duration (Seconds)," "Duration (Minutes)," "Duration 5 seconds or less," and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.
- **Low packet utilization** — Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.

    - A common low packet utilization scenario occurs when an attendee joins a meeting to listen to the presenter, but never speaks (the microphone is muted for most of the call). Here, the audio stream inbound to the client has high packet utilization while the audio stream outbound from the client has little to no packet utilization. The duration of the stream might be an hour or longer but the packet utilization on the stream from the client to the server is low since the microphone was muted, and an *Unclassified* stream results.

    Tip

    The "Packet Utilization" dimension and "Avg Packet Utilization" measurement can be used to determine the packet activity of a stream.