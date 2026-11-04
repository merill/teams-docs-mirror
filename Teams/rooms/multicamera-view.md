---
layout: Conceptual
title: Multiple camera view in Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/multicamera-view
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: sammili
ms.date: 2026-06-05T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-rooms
audience: Admin
ms.collection:
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
ms.custom: QuickDraft
ai-usage: ai-assisted
description: Learn how to set up and manage multiple cameras in Microsoft Teams Rooms on Windows to provide various angles and perspectives during meetings.
locale: en-us
document_id: e7e4f290-7422-4fa1-3368-0836f8675e40
document_version_independent_id: e7e4f290-7422-4fa1-3368-0836f8675e40
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/multicamera-view.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/multicamera-view
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/multicamera-view.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 317aee54-b436-ff41-e056-a4d7699a5f1a
---

# Multiple camera view in Teams Rooms - Microsoft Teams | Microsoft Learn

Multiple camera view activates multiple cameras in Microsoft Teams Rooms on Windows capture in room participants in large and complex spaces such as multi-purpose rooms and classrooms. Remote participants can experience multiple camera view in Teams meetings on Microsoft Teams Desktop (Windows and Mac) and Teams Rooms on Windows. It isn't available in peer-to-peer calls or Teams Events.

## Prerequisites

- Teams Rooms resource account with an assigned Microsoft Teams Rooms Pro license. For more information, see [Microsoft Teams Rooms Licensing](/en-us/microsoftteams/rooms/rooms-licensing).
- Teams Rooms on Windows version 5.2 or later installed.
- Connect a maximum of four Teams certified single stream USB camera peripherals.

Important

Multi-stream intelligent cameras aren't supported in multiple camera configuration. Multiple camera view isn't supported in peer-to-peer (P2P) calls or Teams Events; it's available in scheduled and Meet Now Teams meetings only.

## Recommendations

- USB has limited bandwidth. Each camera should be connected to the Microsoft Teams Rooms device USB port directly. If there are insufficient USB ports for all peripheral devices, a USB hub can be used to but it should have only one camera connected to it.
- Older Microsoft Teams Rooms models might not have sufficient capacity to process multiple simultaneous videos. Video freeze or missing video streams might occur. Therefore, the following is our minimum compute recommendation:
    - Intel Core i5 processor or above
    - For two or three camera setup, minimum Intel 9th Generation CPU
    - For four camera setup, minimum Intel 12th Generation CPU
    - Cameras should support MJPEG video format.

## Set up multiple camera view

Teams Rooms on Windows can send up to four single stream cameras feeds to render on the receiver-side for remote meeting participants to view simultaneously. This feature requires admins to enable the **Multiple camera view** toggle and map cameras to the desired order that are displayed on the receiver-side.

There are two ways to set up multiple camera view:

### Using the admin settings on the device

1. In admin settings on-device, go to **Settings &gt; Peripherals**, and ensure **Default Video Camera** has been selected.
2. Enable **Multiple camera view** toggle.
3. When **Multiple camera view** is enabled, **IntelliFrame** toggle is disabled.
4. When **Multiple camera view** is enabled, **Video Camera 2** dropdown selection appears. Select a camera.
5. Check **Preview** to see and verify the camera view.
6. Continue to select **Add Camera** until you complete the configuration as desired.

### Using Remote Access in the Teams Rooms Pro Management portal

1. To manage and remotely access Teams Rooms devices, see [Microsoft Teams Rooms Pro management](/en-us/microsoftteams/rooms/rooms-pro-management).
2. Choose **Rooms** and select the room device to remotely administer. Under the **Rooms** tab, select **Remote Access**, then **Start Session**.

## How remote participants experience multiple camera view

Remote participants can view up to four camera feeds from the room simultaneously in Gallery view. Each feed is shown in a 16:9 aspect ratio, arranged equally within the room’s video tile for an optimized view. Remote participants also have the flexibility to switch between different camera angles for their view only – changing their own view does not affect what others see. Here’s how it works on different Teams clients:

- Teams desktop (Windows and Mac): In a Teams meeting, the room’s video appears as a single composite tile showing multiple camera feeds. Remote participants can use the carousel navigation controls (the arrows that appear on either side of the camera icon at the top-right of the room’s video tile) to cycle through the available camera views. For example, a remote participant can choose to see all cameras at once or switch to focus on a specific camera feed by clicking these arrows. If meeting content is being shared, the room’s tile will show only one camera feed at a time, but participants can still use the arrow controls to switch between feeds.

    **Example of a 2-camera view**![Screenshot showing a 2-camera view.](media/multicamera-view/image.png)

    **Camera 1**![Screenshot showing camera 1 view.](media/multicamera-view/image1.png)

    **Camera 2**![Screenshot showing camera 2 view.](media/multicamera-view/image2.png)
- Teams Rooms on Windows: If a remote participant is joining from another Teams Rooms system, they can switch the other room’s camera view using the participant panel on the console or directly on the video tile for touch boards. On the console, in-room participants can locate the room that has multiple cameras, and select **Switch camera view** from that participant’s contextual menu. Each time this option is selected, the other room will cycle to the next camera feed (looping through all configured cameras).

**Teams Rooms on Windows Console**

![Screenshot showing the Teams Rooms on Windows console.](media/multicamera-view/image3.png)