---
layout: Conceptual
title: Set up and manage Teams Rooms on Android custom backgrounds - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/custom-backgrounds-android
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: henrikalim
ms.date: 2026-09-30T00:00:00.0000000Z
ms.topic: install-set-up-deploy
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Learn how to set up custom backgrounds on Teams Rooms on Android front-of-room and touch console displays.
locale: en-us
document_id: e77b5da2-1d1d-a990-4094-bfd390de2a00
document_version_independent_id: e77b5da2-1d1d-a990-4094-bfd390de2a00
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/custom-backgrounds-android.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/custom-backgrounds-android
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/custom-backgrounds-android.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 27349460-4c68-320d-10f3-098916673725
---

# Set up and manage Teams Rooms on Android custom backgrounds - Microsoft Teams | Microsoft Learn

You can create custom background images for your Teams Rooms on Android devices to showcase your brand or to provide instructions and support information to Teams Rooms users. For example, you can add your company logo and include contact information for your organization's help desk to your custom background.

Your ability to deploy custom backgrounds depends on the version of Teams Rooms on Android app installed on your device and the license of the account logged in on the device:

- Your Teams Rooms on Android device must be running on version 1449/1.0.96.2024070201 or later.
- The account signed in on your Teams Rooms on Android device must be assigned with a Teams Rooms Pro license.

Custom backgrounds are applied as follows:

- When you push the configuration profile to a single screen device, only the main display image will show up.
- When you have two front-of-room displays or when you connect a second display later, the extended display image will be shown.
- If no image is uploaded for the touch console, a purple gradient default image will be displayed.

### Supported resolutions

#### Minimum supported resolutions

Front-of-room displays and touch consoles have **minimum** supported custom background **resolutions**:

- For front-of-room displays, the minimum supported resolution is 1920 x 1080.
- For touch consoles, the minimum supported resolution is 1280 x 720.

#### Recommended resolutions

The **recommended** custom background **resolution** for front-of-room displays and touch consoles depends on the aspect ratio and resolution of the display used. The following lists the recommended custom background resolution for each supported display aspect ratio:

- Single and dual front-of-room displays (per display)
    - 16:9 displays – 1920 x 1080 for 1080p displays, 3840 x 2160 for 4K displays. Up to two 16:9 displays are supported.
- Touch console displays
    - 16:9 displays – 1920 x 1080
    - 16:10 displays – 1280 x 800
- Touch board displays (4K displays)
    - 16:9 – 3840 x 2160

If you're not sure what the aspect ratio of your display is, check your display's specifications.

Important

Custom backgrounds with resolutions or aspect ratios higher than the recommended resolution for a display may be center-cropped.

[![Screenshot that shows a custom background showing a center crop in a larger image.](../media/front-of-room-16-9-center-crop.png)](../media/front-of-room-16-9-center-crop-large.png#lightbox)

Custom backgrounds with resolutions or aspect ratios lower than the recommended resolution but higher than the minimum supported resolution are scaled to fill the frame of the display and are then center-cropped. The original aspect ratio of the custom background is maintained.

### Supported file size and formats

The custom background image file must be under 20MB and saved in one of the following formats: `JPG`, `JPEG`, and `PNG`.

### Design custom background images

Follow the best practices listed in this section to ensure the following:

- Content doesn't collide with on-screen elements
- Content remains legible when placed in front of visual elements in the custom background
- Content remains visible if a custom background is cropped

The following guidelines apply for front-of-room, touch console, and touch board displays. For best results, use the custom background template in designing your custom background images:

- Use a darker background on the top and bottom left corners to ensure users can read the clock, room information, and tips in those locations in white.
- For the best experience, use a contrast ratio of 4.5:1 for small text and 3:1 for large text. Use an accessibility contrast checker on the Internet to input color values to see if their contrast ratio is acceptable.
- Place text, logos, or icons, in the middle of the screen so it isn't blocked by home screen elements.

#### Front-of-room display guidelines

When you create a custom background, avoid placing text, logos, or icons, near these locations:

- **Upper left corner**- Time and room information.
    - **Size**: up to 46% of the screen width, up to 42% of the screen height depending on the display settings
- **Bottom left corner**- Tips.
    - **Size**: up to 46% of the screen width, up to 16% of the screen height depending on the display settings
- **Right side**- Room calendar.
    - **Size**: up to 36% of the screen width, up to 72% of the screen height depending on the display settings

**16:9 - Single front-of-room display dimensions**

[![Screenshot that shows a custom background showing a 16:9 front of room display with element dimensions and a QR code.](../media/mtr-devices/mtra-for-qr-16x9.png)](../media/mtr-devices/mtra-for-qr-16x9.png#lightbox)

**16:9 - Dual front-of-room display dimensions**

[![Screenshot that shows a custom background showing dual 16:9 front of room displays with element dimensions and a QR code.](../media/mtr-devices/mtra-dual-for-qr.png)](../media/mtr-devices/mtra-dual-for-qr.png#lightbox)

#### Touch console display guidelines

When you create a custom background, avoid placing text, logos, or icons, near these locations:

- **Upper left corner**- Time and room information.
    - **Size**: up to 42% of the screen width, up to 32% of the screen height depending on the display settings
- **Bottom left corner**- Tips.
    - **Size**: up to 42% of the screen width, up to 11% of the screen height depending on the display settings
- **Middle**- User actions.
    - **Size**: vertically centered between the room information section and tips section, horizontally centered between the left edge and the room calendar
- **Right side**- Room calendar.
    - **Size**: up to 44% of the screen width, up to 80% of the screen height depending on the display settings
- **Bottom right corner**- Help.
    - **Size**: up to 4% of the screen width, up to 7% of the screen height depending on the display settings

**16:9 - Touch console dimensions**

[![Screenshot that shows a custom background showing a 16:9 touch console display with element dimensions with QR code.](../media/mtr-devices/mtra-console-qr.png)](../media/mtr-devices/mtra-console-qr.png#lightbox)

#### Touch board display guidelines

When you create a custom background, avoid placing text, logos, or icons, on these locations:

- **Upper left corner**- Time and room information.
    - **Size**: up to 46% of the screen width, up to 42% of the screen height depending on the display settings
- **Bottom left corner**- Tips.
    - **Size**: up to 46% of the screen width, up to 16% of the screen height depending on the display settings
- **Right side**- User actions and room calendar.
    - **Size**: up to 43% of the screen width, up to 72% of the screen height depending on display settings
- **Bottom right corner**- Help.
    - **Size**: up to 3% of the screen width, up to 5% of the screen height depending on display settings

**16:9 - Touch board display dimensions**

[![Screenshot that shows a custom background showing a 16:9 touch board display with element dimensions with QR code.](../media/mtr-devices/mtra-touchboard-qr-16x9.png)](../media/mtr-devices/mtra-touchboard-qr-16x9.png#lightbox)

### Step 2: Download the custom background template

To create custom backgrounds that meet the guidelines in the previous section, you can download the [Microsoft Teams Rooms on Android Custom Background Template](https://www.microsoft.com/download/details.aspx?id=106161).

The template is a .PSD file that can be opened by apps such as Adobe Photoshop or Paint.NET (a plug-in may be required). The template provides assets and guidelines to help you place text and graphics in your custom backgrounds that won't be obscured by on-screen elements.

Important

The template for Teams Rooms on Android consoles is lower than the minimum supported resolution for Teams Rooms on Windows devices. If you plan to use the same image on both device platforms, use the Teams Rooms on Windows console template file.

### Step 3: Deploy custom backgrounds

After you've created background images:

1. Save them with unique and descriptive filenames. For example, `ContosoBackground-Right-FoR.jpg` (main/right display), `ContosoBackground-Left-FoR.jpg` (extended/left display), and `ContosoBackground-Console.jpg` (touch console display).
2. Log in to the [Teams Pro Management Portal](enrolling-mtrp-managed-service).
3. Select **Rooms**.
4. Select your desired room.
5. Select **Settings**.
6. Select **Theme**.
7. Adjust the drop down to **custom wallpaper** and upload your custom wallpapers.

Once the custom images are saved in the configuration profile, and the configuration profile has been assigned to Teams Rooms on Android devices with a Teams Rooms Pro license, the custom images will be applied as the background of the Teams Rooms on Android devices accordingly.

On your Teams Rooms on Android device settings, you can switch the background of your device from the custom image to one of the Teams built-in images, or vice versa: go to **Teams Admin Settings** &gt; **General** &gt; **Background** &gt; select another background thumbnail as desired. To change the custom image saved on the device, you'll need to make the update from the Teams admin center.