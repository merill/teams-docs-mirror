---
layout: Conceptual
title: Set up and manage Teams Rooms on Windows custom backgrounds - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/custom-backgrounds
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
ms.date: 2026-01-07T00:00:00.0000000Z
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Learn how to set up custom backgrounds on Teams Rooms front-of-room and touch console displays.
locale: en-us
document_id: 104c1570-b5b0-fe02-0d8c-c3d31518e8d7
document_version_independent_id: 104c1570-b5b0-fe02-0d8c-c3d31518e8d7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/custom-backgrounds.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/custom-backgrounds
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/custom-backgrounds.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 044cbb76-9c1f-727a-2d19-fc79e6fca835
---

# Set up and manage Teams Rooms on Windows custom backgrounds - Microsoft Teams | Microsoft Learn

You can create and deploy custom background images for your Teams Rooms on Windows devices to represent your brand or to provide instructions to Teams Rooms users. For example, you can add your company logo and include contact information for your organization's help desk to your custom background.

The custom background options available to you and how you configure them depends which license is assigned to your room resource account.

- **Teams Rooms Pro** - We recommend using the enhanced method but the standard method is supported as well
- **Teams Rooms Basic** - Custom backgrounds are not supported, use a included background
- Legacy **Teams Rooms Standard** or **Teams Rooms Premium** - Use the standard method

To check which Teams Rooms license is applied to your Teams Rooms resource account:

- On your Teams Rooms device:

    1. Select **More** and then **Settings**
    2. Enter your admin credentials and select **Yes**
    3. On the **Settings** screen, find the Teams Rooms license under **Room License**
- In the Pro Management Portal:

    1. Go to https://portal.rooms.microsoft.com and sign in
    2. Select **Planning** and then **Inventory** and then find resource account assigned to your device
    3. In the **License Type** column, you see what license is assigned

# [Enhanced backgrounds](#tab/Enhanced)
### Enhanced backgrounds (Teams Rooms Pro)

Enhanced backgrounds let you configure up to three custom background images and specify which image goes on the main front-of-room display, extended front-of-room display, and touch console.

In a dual-screen setup, the main display shows the room calendar and is typically installed on the right. The extended display shows the date, time, and room information and is typically installed on the left.

When you enable custom backgrounds, you must provide custom backgrounds for all of your front-of-room displays. If you have two front-of-room displays, you need to provide a custom background for each display. Providing a custom background for your touch console is optional. Otherwise, if you enable custom backgrounds and don't provide custom backgrounds for all of your front-of-room displays, all displays, including the touch console, default to `No Theme`.

Tip

If you've been using the `<CustomThemeImageUrl>` element to provide a single custom background image for your front-of-room displays, you can continue using it if it suits your needs. However, if you want to provide separate custom backgrounds for each front-of-room display, or replace your existing backgrounds with higher resolution images, or configure a custom background on your touch console, you need to use the elements provided in this section. For more information about using `<CustomThemeImageUrl>`, see [Standard backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds?tabs=Standard).

### Step 1: Create custom background images

#### Minimum supported resolutions

Front-of-room displays and touch consoles have **minimum** supported custom background **resolutions**:

- For front-of-room displays, the minimum supported resolution is 1920 x 1080.
- For touch consoles, the minimum supported resolution is 1280 x 800.

If the resolution of any custom background is below the minimum supported resolution for the display or console it's added to, all displays default to `No Theme`.

#### Recommended resolutions

The **recommended** custom background **resolution** for front-of-room displays and touch consoles depends on their aspect ratios. The following lists the aspect ratios supported by each display and the recommended custom background resolution for each:

- Single and dual front-of-room displays (per display)
    - 16:9 displays – 1920 x 1080 for 1080p displays, 3840 x 2160 for 4K displays. Up to two 16:9 displays are supported.
    - 21:9 displays – 2560 x 1080 for 1080p displays, 3840 x 1645 for 4K displays. Only one 21:9 display is supported.
- Touch console displays
    - 16:9 displays – 1920 x 1080
    - 16:10 displays – 1280 x 800
    - 3:2 displays – 1920 x 800
- Touch board displays (4K displays)
    - 16:9 – 3840 x 2160
    - 3:2 – 3840 x 2560

If you're not sure what the aspect ratio of your display is, check your display's specifications.

Important

Custom backgrounds with resolutions or aspect ratios higher than the recommended resolution for a display may be center-cropped.

[![A custom background showing a center crop in a larger image.](../media/front-of-room-16-9-center-crop.png)](../media/front-of-room-16-9-center-crop-large.png#lightbox)

Custom backgrounds with resolutions or aspect ratios lower than the recommended resolution but higher than the minimum supported resolution are scaled to fill the frame of the display and are then center-cropped. The original aspect ratio of the custom background is maintained. Custom backgrounds with resolutions lower than the minimum supported resolution won't be displayed on the device.

### Supported file formats

The custom background image file must be in one of the following formats: `JPG`, `JPEG`, and `PNG`.

### Design custom background images

Follow the best practices listed in this section to ensure the following:

- Content doesn't collide with on-screen elements
- Content remains legible when placed in front of visual elements in the custom background
- Content remains visible if a custom background is cropped

The following guidelines apply for front-of-room, touch console, and touch board displays:

- Use a darker background on the top and bottom left corners to ensure users can read the clock, room information, and tips in those locations in white.
- For the best experience, use a contrast ratio of 4.5:1 for small text and 3:1 for large text. Use an accessibility contrast checker on the Internet to input color values to see if their contrast ratio is acceptable.
- Place text, logos, or icons in the middle of the screen so it isn't blocked by home screen elements.

#### Front-of-room display guidelines

When you create a custom background, avoid placing text, logos, or icons, near these locations:

- **Upper left corner**- Time and room information.
    - **Size**: up to 46% of the screen width, up to 42% of the screen height depending on the display settings
- **Bottom left corner**- Tips.
    - **Size**: up to 46% of the screen width, up to 16% of the screen height depending on the display settings
- **Right side**- Room calendar.
    - **Size**: up to 36% of the screen width, up to 72% of the screen height depending on the display settings

**16:9 - Single front-of-room display dimensions**

[![A custom background showing a 16:9 front of room display with element dimensions and a QR code.](../media/mtr-devices/mtrw-for-qr-16x9.png)](../media/mtr-devices/mtrw-for-qr-16x9.png#lightbox)

**16:9 - Dual front-of-room display dimensions**

[![A custom background showing dual 16:9 front of room displays with element dimensions and a QR code.](../media/mtr-devices/dual-for-qr.png)](../media/mtr-devices/dual-for-qr.png#lightbox)

**21:9 - Single front-of-room display dimensions**

[![Custom background showing a 21:9 front of room display with element dimensions and a QR code.](../media/mtr-devices/mtrw-for-qr-21x9.png)](../media/mtr-devices/mtrw-for-qr-21x9.png#lightbox)

#### Touch console guidelines

When you create a custom background, avoid placing text, logos, or icons, near these locations:

- **Upper left corner**- Time and room information.
    - **Size**: 540 x 242 px
- **Bottom left corner**- Tips.
    - **Size**: 540 x 82 px
- **Middle**- User actions.
    - **Size**: 408 x 336 px
- **Right side**- Room calendar.
    - **Size**: up to 44% of the screen width, up to 80% of the screen height depending on the display settings
- **Bottom right corner**- Help.
    - **Size**: 56 x 56 px

**16:9 - Touch console dimensions**

[![A custom background showing a 16:9 touch console display with element dimensions with QR code.](../media/mtr-devices/mtrw-console-qr.png)](../media/mtr-devices/mtrw-console-qr.png#lightbox)

#### Touch board guidelines

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

[![A custom background showing a 16:9 touch board display with element dimensions with QR code.](../media/mtr-devices/mtrw-touchboard-qr-16x9.png)](../media/mtr-devices/mtrw-touchboard-qr-16x9.png#lightbox)

**3:2 - Touch board display dimensions**

[![A custom background showing a 3:2 touch board display with element dimensions with QR code.](../media/mtr-devices/mtrw-touchboard-qr-3x2.png)](../media/mtr-devices/mtrw-touchboard-qr-3x2.png#lightbox)

### Step 2: Download the background template

To create custom backgrounds that meet the guidelines in the previous section, you can download the [Microsoft Teams Rooms Theme Template](https://www.microsoft.com/en-us/download/details.aspx?id=105251). The template helps position logos, text, and graphics where they won't be obscured by on-screen elements.

The template is a .PSD file that can be opened by apps such as Adobe Photoshop or Paint.NET (a plug-in may be required). The template provides assets and guidelines to help you place text and graphics in your custom backgrounds that won't be obscured by on-screen elements.

### Step 3: Deploy custom backgrounds

Important

The Teams Rooms on Windows devices have a higher minimum resolution requirement therefore the templates are higher resolution compared to the Teams Rooms on Android templates. Confirm before uploading that your images are at the correct minimum resolution as low resolution images won't apply successfully.

After you've created backgrounds:

1. Save them with unique and descriptive filenames. For example, `ContosoBackground-Right-FoR.jpg` (main/right display), `ContosoBackground-Left-FoR.jpg` (extended/left display), and `ContosoBackground-Console.jpg` (touch console display).
2. Copy them to the `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` folder on your Teams Rooms device. You can use a USB drive or remotely connect to the network share of your device to copy the file.

    Note

    If the Teams Rooms on Windows device has been transitioned to [password-less resource accounts](/en-us/microsoftteams/rooms/passwordlessentraresourceaccounts), the correct file path to copy the files to is: `C:\Users\ResourceAccount\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.
3. To tell the Teams Rooms on Windows app to use custom backgrounds and which files to use, you must add the `<Theming>` element to your XML configuration file. Within the `<Theming>` element, you need to provide the elements in the table below.

Note

If the `<CustomThemeImageUrl>` element is also included in the XML configuration file, the following elements override the value provided in that element.

| Element | Description | Required? |
| --- | --- | --- |
| `<ThemeName>` | Set to `Custom` to use custom backgrounds. | **Yes**, if `<Theming>` element is provided. |
| `<CustomBackgroundMainFoRDisplay>` | Filename of main/right custom background. e.g., `ContosoBackground-Right-FoR.jpg` | If `<ThemeName>` is set to:<br>- `Custom` - **Yes**<br>- Other value - **No** |
| `<CustomBackgroundExtendedFoRDisplay>` | Filename of extended/left custom background. e.g., `ContosoBackground-Left-FoR.jpg` | **Yes**, if both of the following are true:<br>- `<ThemeName>` is set to `Custom`.<br>- `<DualScreenMode>` is set to `true`. |
| `<CustomBackgroundConsole>` | Filename of touch console background. e.g., `ContosoBackground-Console.jpg` | **No** |

Here's an example XML showing background images being provided for dual front-of-room displays and the touch console:

```xml
<SkypeSettings>
  <Theming> 
      <ThemeName>Custom</ThemeName> 
      <CustomBackgroundMainFoRDisplay>ContosoBackground-Right-FoR.jpg</CustomBackgroundMainFoRDisplay> 
      <CustomBackgroundExtendedFoRDisplay>ContosoBackground-Left-FoR.jpg</CustomBackgroundExtendedFoRDisplay> 
      <CustomBackgroundConsole>ContosoBackground-Console.jpg</CustomBackgroundConsole> 
  </Theming>
</SkypeSettings>
```

To apply the configuration changes included in this article to your Teams Rooms for Windows devices, you need to use the Teams Rooms XML configuration file. The XML configuration file lets you remotely deploy configuration changes to one or more Teams Rooms devices in your organization. For more information, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file).

# [Standard backgrounds](#tab/Standard)
### Teams Rooms with a legacy license

Standard custom backgrounds are supported on 16:9 and 21:9 displays. The guidelines differ slightly depending on the size of your display:

- 16:9 displays - Custom backgrounds need to be exactly 3840 x 1080 pixels in size, regardless of whether the background is used with a single front-of-room display or dual front-of-room displays. If used with a single front-of-room display, the right half of the image is used and the left half is cropped out. If used with a dual front-of-room display, the image is divided between the left and right front-of-room displays.
- 21:9 displays **-** Custom backgrounds need to be exactly 2560 x 1080 pixels in size. Only one 21:9 front-of-room display is supported.

If you want to have dual front-of-room displays, they both need to be 16:9 displays. Two 21:9 displays or mixing 16:9 and 21:9 displays isn't supported. If you're not sure if your display is 16:9 or 21:9, check your display's specifications.

#### Front-of-room displays

When you create a custom background, use the following guidelines:

- Place text, logos, or icons, in the middle of the screen so it isn't obscured by home screen elements.
- Avoid placing text, logos, or icons, near these locations:
    - **Upper left corner**- Time and room information.
        - **Size**: up to 46% of the screen width, up to 42% of the screen height depending on the display settings
    - **Bottom left corner**- Tips.
        - **Size**: up to 46% of the screen width, up to 16% of the screen height depending on the display settings
    - **Right side**- Room calendar.
        - **Size**: up to 36% of the screen width, up to 72% of the screen height depending on the display settings

**16:9 - Single front-of-room display dimensions**

[![A custom background showing a 16:9 front of room display with element dimensions with QR code.](../media/mtr-devices/mtrw-for-qr-16x9.png)](../media/mtr-devices/mtrw-for-qr-16x9.png#lightbox)

**16:9 - Dual front-of-room display dimensions**

[![A custom background showing dual 16:9 front of room displays with element dimensions with QR code.](../media/mtr-devices/dual-for-qr.png)](../media/mtr-devices/dual-for-qr.png#lightbox)

**21:9 - Single front-of-room display dimensions**

[![Custom background showing a 21:9 front of room display with element dimensions with QR code.](../media/mtr-devices/mtrw-for-qr-21x9.png)](../media/mtr-devices/mtrw-for-qr-21x9.png#lightbox)

#### Touch board displays

When you create a custom background, avoid placing text, logos, or icons, near these locations:

- **Upper left corner**- Time and room information.
    - **Size**: up to 46% of the screen width, up to 42% of the screen height depending on the display settings
- **Bottom left corner**- Tips.
    - **Size**: up to 46% of the screen width, up to 16% of the screen height depending on the display settings
- **Right side**- User actions and room calendar.
    - **Size**: up to 43% of the screen width, up to 72% of the screen height depending on display settings
- **Bottom right corner**- Help.
    - **Size**: up to 3% of the screen width, up to 5% of the screen height depending on display settings

**16:9 - Touch board display dimensions**

[![A custom background showing a 16:9 touch board display with element dimensions with a QR code.](../media/mtr-devices/mtrw-touchboard-qr-16x9.png)](../media/mtr-devices/mtrw-touchboard-qr-16x9.png#lightbox)

**3:2 - Touch board display dimensions**

[![A custom background showing a 3:2 touch board display with element dimensions with a QR code.](../media/mtr-devices/mtrw-touchboard-qr-3x2.png)](../media/mtr-devices/mtrw-touchboard-qr-3x2.png#lightbox)

### Custom background template

To create custom backgrounds that meet the guidelines in the previous sections, you can download the [Microsoft Teams Rooms Theme Template](https://www.microsoft.com/en-us/download/details.aspx?id=105251).

The template is a .PSD file that can be opened by apps such as Adobe Photoshop or Paint.NET (a plug-in may be required). The template provides assets and guidelines to help you place text and graphics in your custom backgrounds that won't be obscured by on-screen elements.

### Updating Teams Rooms device configuration

To apply the configuration changes included in this article to your Teams Rooms for Windows devices, you need to use the Teams Rooms XML configuration file. The XML configuration file lets you remotely deploy configuration changes to one or more Teams Rooms devices in your organization. For more information, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file).

### Deploy an updated custom background

First, copy your custom background to the `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` folder on your Teams Rooms device. You can use a USB drive or remotely connect to the network share of your device to copy the file.

Note

If the Teams Rooms on Windows device has been transitioned to [password-less resource accounts](/en-us/microsoftteams/rooms/passwordlessentraresourceaccounts), the correct file path to copy the files to is: `C:\Users\ResourceAccount\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.

After you've copied your custom background to the device, you need to tell Teams to use it. To use the custom background, add the following XML configuration file:

```xml
<SkypeSettings>
  <Theming><ThemeName>Custom</ThemeName>
    <CustomThemeImageUrl>ContosoBackground.png</CustomThemeImageUrl>
  </Theming>
</SkypeSettings>
```

Change `ContosoBackground.png` to the file name of your custom background.

---