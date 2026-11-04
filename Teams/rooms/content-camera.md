---
layout: Conceptual
title: Learn how to set up content cameras - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/content-camera
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: leungsam
ms.date: 2024-08-20T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-mar2020
description: Use a content camera in Microsoft Teams Rooms that interacts with image-processing software to allow presenters to draw on an analog whiteboard.
locale: en-us
document_id: b06af4b9-8034-c287-b30c-ca009b8549c1
document_version_independent_id: bf2e1bd9-9b86-68a9-42dd-89001bedf0cd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/content-camera.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/content-camera
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/content-camera.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2fb5495e-8d11-785e-5ada-3725f59ce387
---

# Learn how to set up content cameras - Microsoft Teams | Microsoft Learn

You can now use a content camera with a Microsoft Teams Rooms system. A content camera interacts with special image-processing software and a whiteboard to allow a presenter to draw on an analog whiteboard and share the content with remote participants.

## Step 1: Confirm requirements

To use this feature with a Teams Rooms device, you need to assign a Microsoft Teams Rooms Pro license to the device. For more information, see [Microsoft Teams Rooms licenses](rooms-licensing).

See the following video for examples of content camera functionality.

## Step 2: Plan the content camera installation

### Review installation safety requirements

Always adhere to your country/region or area's building code, which may define a minimum distance from the floor or a requirement that ceiling-mounted equipment be secured to a rafter or other structure. Follow the mounting instruction for the hardware provided with the camera you've selected. OEM camera mounting kits include a camera, USB 2.0 extenders, and required cabling.

The size of the whiteboard used for sharing affects the placement of the camera. Board size recommendations are:

- 3–6 ft. (0.9–1.8 m) wide — Supported
- 6–9 ft. (1.8–2.7 m) wide — Recommended
- 9–12 ft. (2.7–3.6 m) wide — Supported
- Above 12 ft. (3.6 m) wide — camera covers 9–12 ft. (2.7–3.6 m) and crops the rest.

### Determine the camera location

Ideal placement of a content camera is centered vertically and horizontally on the whiteboard. Local building codes may have height restrictions that require the camera be elevated higher than the top of the white board.

You can install the camera up to 6 in. (152 mm) higher than the top of the whiteboard, and centered on the white board as shown. Make sure that the camera image includes at least a 6 in. (152 mm) border on both sides horizontally. You can use the camera preview in the Microsoft Teams Rooms app to determine final placement of the camera.

![Content camera placement diagram.](../media/magic-whiteboard.png)

### Determine the camera distance

Using typical whiteboard markers, the optimal remote user experience is to share ink strokes in the 1–2 mm per pixel range in the content camera image, and the best results use 1.5 mm per pixel. All supported cameras provide 1920 x 1080 resolution, and some can exceed that resolution.

The distance of the camera from the whiteboard combines with the camera resolution and Horizontal Field of View (HFoV) to determine the distance from the whiteboard. The following table shows examples of distances for various whiteboard sizes. You can use these values as starting points to determine final placement of the content camera.

**Content camera distance by whiteboard size**

| Camera HFoV | 3 ft. (0.91 m) | 6 ft. (1.8 m) | 9 ft. (2.74 m) | 12 ft. (3.65 m) | Max distance from Whiteboard |
| --- | --- | --- | --- | --- | --- |
| 80° | 1.79 ft. (0.54 m) | 3.58 ft. (1.09 m) | 5.36 ft. (1.6 m) | 7.15 ft. (2.17 m) | 7.51 ft. (2.28 m) |
| 90° | 1.5 ft. (0.45 m) | 3.00 ft. (0.91 m) | 4.5 ft. (1.37 m) | 6.0 ft. (1.82 m) | 6.3 ft. (1.92 m) |
| 100° | 1.26 ft. (0.38 m) | 2.52 ft. (0.77 m) | 3.78 ft. (1.15 m) | 5.03 ft. (1.53 m) | 5.29 ft. (1.61 m) |
| 110° | 1.05 ft. (0.32 m) | 2.10 ft. (0.64 m) | 3.15 ft. (0.96 m) | 4.2 ft. (1.28 m) | 4.41 ft. (1.31 m) |
| 120° | 0.87 ft. (0.26 m) | 1.73 ft. (0.52 m) | 2.60 ft. (0.79 m) | 3.46 ft. (1.05 m) | 3.64 ft. (1.10 m) |

The distance between the content camera and the wall the whiteboard is mounted on depends on the HFoV for that model of camera, which varies. Install cameras with a larger HFoV (120 degrees for example) closer to the wall, and cameras with a narrower HFoV farther away from the wall. Check the HFoV before you start to install the chosen camera.

If you have whiteboards larger than 12 ft. (3.65 m) or with no corners (like full wall whiteboards), you can place the camera anywhere in the middle. The enhancement software selects an area in the middle if it fails to find whiteboard corners.

## Step 3: Define the capture area

Use dark-colored tape or another visible marker to define the content camera capture area on a full-wall whiteboard. This helps in-room participants keep their writing within the area the camera captures.

You can choose to have the camera mounted on a moveable tripod instead of a permanent mount. Place the tripod centered on the whiteboard. This setup may be temporary or used where there's little chance of knocking over the equipment. If you use a temporary mount, remember that content enhancement will be impacted if you move the camera after the initial share and you'll need to re-share to correct for movement.

A writing board that isn't white isn't supported.

## Step 4: Select and configure a content camera

# [Teams Rooms for Windows](#tab/Windows)
Any certified Teams Rooms on Windows camera can be used as a content camera. However, we recommend using a camera which has been specifically certified as a content camera for the best experience. Refer to [Teams Rooms certified systems and peripherals](/en-us/microsoftteams/rooms/certified-hardware?tabs=Peripherals) for certified cameras.

You can also refer to the Microsoft Teams devices marketplace for supported Content Camera Kits at https://aka.ms/teamsdevices.

After the camera is installed in the room, set it up on that room's Microsoft Teams Rooms console:

1. Select **Settings**, sign in as Admin, and select **Peripherals**.
2. In the **Content Camera** section, select the content camera and make sure **Content enhancements** is selected.
3. (Optional) If the camera was installed upside down because it was mounted from the ceiling, select **Rotate content camera 180°**.
4. Select **Save and exit**.

![Content camera setup.](../media/content-camera1.png)

# [Teams Rooms for Android](#tab/Android)
To determine whether your Teams Rooms on Android supports the addition of a content camera, check with your Teams Rooms on Android manufacturer.

If supported, configure the content camera on the Teams Rooms console:

1. Select **Settings** &gt; **Peripherals**.
2. Under **Content Camera**, select the content camera and turn on **Content enhancements**.
3. If the camera is mounted upside down, turn on **Rotate content camera 180°**.
4. Select **Save and exit**.

To manage Teams Rooms devices and settings remotely, see [Teams Pro Management Portal](enrolling-mtrp-managed-service).

**Selecting the content camera**![Select content camera.](../media/mtr-devices/content-camera-android-800px.png)

**Inversing the content camera**![Inversing the camera.](../media/mtr-devices/content-camera-android2-800px.png)

---