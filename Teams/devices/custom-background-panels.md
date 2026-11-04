---
layout: Conceptual
title: Set up and manage custom backgrounds on Teams panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/custom-background-panels
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: eviegrimshaw
ms.date: 2026-09-29T00:00:00.0000000Z
ms.topic: install-set-up-deploy
audience: Admin
ms.service: msteams
ms.subservice: itpro-devices
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: ''
locale: en-us
document_id: 5f160b25-ca9f-0cfd-fd60-5e05e4520c1a
document_version_independent_id: 5f160b25-ca9f-0cfd-fd60-5e05e4520c1a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/custom-background-panels.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/custom-background-panels
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/custom-background-panels.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 185c347c-baf1-59d2-ff9a-141c9d2308dd
---

# Set up and manage custom backgrounds on Teams panels - Microsoft Teams | Microsoft Learn

You can create custom background images for your Teams panel devices to showcase your brand or to provide instructions and support information to Teams panels users. For example, you can add your company logo, custom QR codes, a help URL link, or other organization information.

To use custom backgrounds, it depends on the version of Teams panels app installed and the license of the account that is signed in to that device:

- Verify the Teams panel is running on version 1449/1.0.96.2024081207 or later.
- Verify the account signed in on your Teams panel device is assigned a Teams Rooms Pro or Teams Shared Devices license.

To set up and manage custom backgrounds for your Teams panels:

1. Sign in to the **Teams admin center**.
2. Go to **Teams devices** &gt; **Panels** &gt; **Configuration profiles** and select **Add** or **Edit**.
3. Go to **Device settings** &gt; **Background** &gt; select **Use a custom background**. You can upload one image, which will be displayed on the panel home screen.
4. Select **Save**.

## Custom background requirements

There are a few requirements on the custom background you'll upload to the Teams panel. The minimum resolution supported is 1280 x 720. The custom background image file must be between 100 KB and 2 MB and a JPG, JPEG, and PNG file format.

Note

Custom backgrounds with resolutions or aspect ratios higher than the recommended resolution for a display may be center-cropped.

### Custom background content guidelines

Follow the best practices listed here to ensure that:

- Content doesn't collide with on-screen elements.
- Content remains legible when placed in front of visual elements in the custom background.
- Content remains visible if a custom background is cropped.

For Teams panels display, follow the following guidelines:

- Use a darker background in the top corner to ensure users can read the clock and room information that is in white text.
- For the best experience, use a contrast ratio of 4.5:1 for small text and 3:1 for large text. Use an accessibility contrast checker on the Internet to input color values to see if their contrast ratio is acceptable.

Tip

Use the custom background template in designing your custom background image.

[![Teams panel background screen layout.](media/custom-background-panels/image.png)](media/custom-background-panels/image.png#lightbox)

### Custom background template

To create custom backgrounds that meet the guidelines in the previous section, you can download the [Microsoft Teams panels Custom Background template](https://www.microsoft.com/en-us/download/details.aspx?id=106223). The template is a .PSD file. You can use apps such as Adobe Photoshop or Paint.NET (a plug-in may be required) to customize the PSD file. The template provides the guidelines to help you place text and graphics in your custom backgrounds so that on-screen elements won't be blocked or obscured.

## Deploy custom backgrounds

After you've created a background image, make sure you save it, and then you can deploy the background image.

1. Upload it to a Teams panel configuration profile in the Teams admin center.
2. Assign the Teams panel configuration profile to any Teams panel device with a Teams Rooms Pro or Teams Shared Devices license.

Once your custom image is saved and assigned to the configuration profile for your Teams panels, the custom image is applied as the screen background.

If you want to revert back to one of the Teams built-in images you can go to **Teams Admin Settings** &gt; **Backgrounds** and then select another background. To change the custom image saved on the device, you need to make the update from the Teams admin center.