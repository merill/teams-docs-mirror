---
layout: Conceptual
title: Quality of service (QoS) configuration on Teams phones - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/qos-on-teams-phones
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: mattslomka
ms.date: 2024-10-17T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about the key considerations for deploying Quality of Service (QoS) on your network to support Teams phones.
locale: en-us
document_id: c082c969-03c8-1028-dc26-99d5364f4e6c
document_version_independent_id: c082c969-03c8-1028-dc26-99d5364f4e6c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/qos-on-teams-phones.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/qos-on-teams-phones
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/qos-on-teams-phones.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: a8639165-7528-929d-1ec7-867a3c1207d2
---

# Quality of service (QoS) configuration on Teams phones - Microsoft Teams | Microsoft Learn

Deploying one or many Microsoft Teams phone devices requires planning. One of the key considerations is your organization's network capacity and quality of service (QoS) configuration.

This article explains:

1. How much bandwidth does a Microsoft Teams phone device use?
2. How to control that bandwidth usage?
3. How to ensure your devices are optimized with the right quality of service (QoS) configuration to align to your organizations requirements?

Wired network connectivity is recommended for Microsoft Teams phone devices. If wireless network connectivity is the only option, see best practice guidance [here](prepare-network-teams-phones#wireless-network-considerations).

## How much bandwidth does a Microsoft Teams phone device use?

Microsoft Teams phone is designed to give the best audio experience regardless of your network conditions.

The following table provides rough estimates of bandwidth utilized for the various streams in *kbps* (down/up)

| Feature | Standard | Advanced |
| --- | --- | --- |
| Audio | 58/58 | 76/75 |

## How do I control Microsoft Teams phone bandwidth usage?

If you wish to implement a bandwidth policy on your common area phones, we recommend allocating 100 kbps to each Teams phone resource account. This implementation can be accomplished by assigning a Teams meeting policy with a media bitrate limit configured. When setting the meeting policy at 100 kbps, Teams phones still only use the bandwidth required for the call, and dynamically adjusts if its network connection isn't able to sustain 100 kbps. For user signed in devices, the meeting policy assigned to the users account will also apply to the Teams phone device.

For information on how to configure a Teams meeting policy, see [Meeting policy settings for audio and video](../meeting-policies-audio-and-video). You want to create a custom policy and assign it to all Microsoft Teams phone resource accounts, with the limit for media bitrate configured for 100 kbps.

## Quality of Service (QoS) with Microsoft Teams phones

Microsoft Teams Rooms supports Quality of Service (QoS) Differentiated Services Code Point (DSCP) markings to ensure you can manage the media traffic on your corporate network.

We recommend the following QoS markings and port ranges for the audio, video, and application/screen sharing types of media traffic:

**Audio**:

- Client source port range: **50,000-50,019**
- Protocol: **TCP/UDP**
- DSCP value: **46**
- DSCP class: **Expedited Forwarding (EF)**

**Calling and Meetings Signaling**:

- Client source port range: **50,070-50,089**
- Protocol: **UDP**
- DSCP value: **40**
- DSCP class: **CS5**

For more information on Teams Media and implementing QoS, see [Implement Quality of Service (QoS) in Microsoft Teams](../qos-in-teams).

For Teams phones, you need to configure your Microsoft Teams tenant to insert QoS markings. Teams phone devices honor this policy and apply the markings defined earlier in this document.

For instructions on how to configure your tenant to insert QoS markings, see [Teams settings and policies reference](../settings-policies-reference).