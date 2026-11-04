---
layout: Conceptual
title: Monitor and improve call quality for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/monitor-call-quality-qos
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.topic: article
ms.service: msteams
ms.subservice: meetings
audience: admin
ms.reviewer: siunies
ms.date: 2024-06-17T00:00:00.0000000Z
description: Use Quality of Service (QoS) settings and then Call Analytics and Call Quality Dashboard in Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
- ContentFreshnessFY24
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 5450e8d0-4188-456c-1a1f-64aaa92517a7
document_version_independent_id: 383fbbc0-c5eb-6a61-6082-ff3020ad05fc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/monitor-call-quality-qos.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: monitor-call-quality-qos
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/monitor-call-quality-qos.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: c268d4b5-6b1f-ba2a-2dab-c5fc123426a9
---

# Monitor and improve call quality for Microsoft Teams - Microsoft Teams | Microsoft Learn

This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.

- **Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance
- **Teams admin center**: To analyze call and meeting quality (in-progress and completed) for individual users.
- **Quality of Service (QoS)**: To prioritize important network traffic

## Monitor and troubleshoot call quality

You'll use **Teams admin center** and **Call Quality Dashboard** to find and troubleshoot call and meeting quality problems that come up during ongoing operation. This lets you drive performance improvements across your network.

- **Teams admin center** shows detailed information about the devices, networks, and connectivity related to ***specific calls and meetings*** for each user in Teams. Teams admin and helpdesk agents can use this information to troubleshoot quality and connection problems in specific meetings and calls. To learn more, read [Monitor and troubleshoot Teams meetings and calls](monitor-troubleshoot-teams-meetings-calls).
- **Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization. Use CQD information to help you identify and fix problems. First, [Set up CQD](turning-on-and-using-call-quality-dashboard). Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide).

Teams admin center and CQD can be used independently or together. For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call. In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in Teams admin center. The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.

## Participant visibility in call quality tools

If an organization's users join a federated meeting but did not organize the meeting, that organization will only see details for their own users in all call quality tools. This includes the troubleshooting experience in Teams admin center and Call quality dashboard. The organization that organized a federated meeting will see all participants.

## Prioritize important network traffic using QoS

As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting. Shared video may freeze or pixelate, or fail altogether. This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all. If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.

With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal). QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.

Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime. If you're small enough, you might not need QoS.

When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](qos-in-teams).

To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).