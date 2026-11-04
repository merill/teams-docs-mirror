---
layout: Conceptual
title: Create and manage meeting themes for Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-themes
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.date: 2026-07-06T00:00:00.0000000Z
ms.reviewer: margidesai
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Using approved corporate branding assets like images and logos to create custom meeting themes for Teams meetings within your organization.
locale: en-us
document_id: 117ecfa2-d4f0-f0dd-105f-d7203fe8a1ba
document_version_independent_id: 117ecfa2-d4f0-f0dd-105f-d7203fe8a1ba
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-themes.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-themes
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-themes.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9ac5dd84-dd75-af37-2a29-38ae6654fe5a
---

# Create and manage meeting themes for Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

## Overview

Meeting themes include your organization’s brand colors, a custom image, logo, and branded meeting reactions.

As an admin, you can apply a custom theme to customize the visual appearance of a meeting or event invite, pre-join screen, and lobby for your users' meetings. You can also create branded meeting reactions that participants use to express themselves. By incorporating your organization's brand elements (such as logos, mascots, and characters) or event-based visuals, custom branded reactions help personalize the user experience, fostering a sense of identity and engagement during meetings.

With the support of your brand management and corporate communications teams, you can easily set up and create meeting themes for various business units and departments within your organization. For events, organizers can also use the event registration page to configure the event's branding for registration and emails.

Only organizers with a Teams Premium license can create meetings and events that include meeting themes. Anyone who joins these meetings and events can see the themes, including users in your organization without a Teams Premium license, guests, and anonymous users.

You can set up or manage meeting themes for Teams meetings and events by using the Teams admin center or PowerShell.

[![Screenshot of Contoso Education's meeting theme featuring their brand logo, image, and colors.](media/meeting-themes-edu-small.png)](media/meeting-themes-edu.png#lightbox)

Important

Microsoft doesn't validate the ownership of brand logos or images associated with meeting themes. When your users join meetings and events with other organizations, they should always verify the authenticity of the organization they're meeting with.

Note

All participants can see uploaded images and their associated image URL, including external users, guests, unverified users, and anyone with a link to join the meeting or event. To stop displaying your images, you must delete the images from your meeting theme. To remove images from a meeting theme, go to the **Meeting customization policy** in the Teams admin center, select the chosen meeting theme, and select **Delete theme**.

## Prerequisites

Before you set up meeting themes in Teams meetings, make sure you have the following items:

- The users who need to use meeting themes have a Teams Premium license.
- You're an admin with access to the Teams admin center or you have an assigned customization policy.
- Your custom logo, image, color, and images for branded meeting reactions meet the upload requirements detailed in the following section.

## Upload requirements

Meeting themes display the following visual assets for your theme:

- **Logo** - Your organization's logo that appears on key surfaces during meetings and events, including the lobby screen.
- **Custom image** - A brand image from your organization (custom images aren't the same as [custom meeting backgrounds](custom-meeting-backgrounds)).
- **Custom color** - We recommend using either your brand's primary or secondary color - whichever one best complements your brand image and logo.
- **Branded meeting reactions** - Branded reactions replace the default meeting reactions (Like, Heart, Applause, Laugh, Surprised) that participants use during a meeting. The images you upload replace the images in the default reactions. The following screenshots show the default meeting reactions and an example of custom meeting reactions.

    [![Screenshots showing the default meeting reactions and an example of custom meeting reactions.](media/meeting-themes-custom-reactions-example.png)](media/meeting-themes-custom-reactions-example.png#lightbox)

    Use images that reflect your organization's brand identity, such as logos, icons, mascots, or characters, or event themes.

### Logos

We recommend using a square icon style logo with minimal text and the dimensions of 800 x 800 pixels. The logos you upload must comply with Microsoft accessibility contrast ratios (4:5:1) and meet the following requirements:

- PNG and JPEG image formats.
- Two variations of the logo images that appear on the pre-join and lobby UI:
    - Dark theme brand logo
    - Light theme brand logo
- Maximum size of 5 MB.
- Minimum dimension of 576 x 576 pixels.
- You can upload one image per theme from your device.

### Images

We recommend using images with the dimensions of 1,440 x 810 pixels. The custom images you upload must comply with Microsoft accessibility contrast ratios (4:5:1) and meet the following requirements:

- PNG and JPEG image formats.
- Two variations of the brand images that appear on the pre-join and lobby UI:
    - Dark theme brand image
    - Light theme brand image
- Maximum size of 5 MB.
- Dimensions:
    - Minimum dimensions: 1,024 x 574 pixels
    - Maximum dimensions: 3,840 x 2,160 pixels
- You can upload a minimum of 0 and a maximum of one image per theme from your device.

### Images for branded meeting reactions

Custom reactions should be recognizable, inclusive, and representative of your organization's brand. As part of a themed package, reactions should follow a cohesive visual language. When creating your image sets, ensure that each reaction aligns with the reaction name (Like, Heart, Applause, Laugh, Surprised). For example, avoid using an unrelated image, such as a chair, to replace the default Laugh reaction.

Note

Branded meeting reactions don't yet support skin tone preferences set by users.

Use these image guidelines for your branded meeting reactions. For each reaction that you want to customize, you must upload:

- A PNG file for the static reaction.
- A corresponding PNG image sprite for the animated reaction.

#### Static reaction

Upload one PNG file for each reaction you want to customize. This image is the base for the animated reaction. For best results, follow these guidelines:

- PNG image format with a transparent background
- Dimensions: 100 pixels x 100 pixels

#### Animated reaction

This image animates when participants send a reaction during a meeting.

After you upload the static reaction, to enable animation, upload the corresponding PNG image sprite that contains all the keyframes of the animation.

For best results, create an image sprite according to the following specifications:

- The reaction animates on the spot and loops.
- The frame rate is 24 frames per second.
- Each frame of the animation is 100 pixels x 100 pixels.
- The animation frames are arranged in a PNG vertical sprite sheet with a transparent background.
- Dimensions: One column that's 100 pixels wide x 5,100 pixels high with no spacing between the frames.
- Number of frames: 51 The animation uses 20 transition frames (10 frames for fade-in and 10 frames for fade-out). The key moment of the animation—such as thumbs up in the Like reaction—happens at frame 23.

## Create or manage meeting themes in the Teams admin center

All Teams Premium licensed users are automatically assigned the global default policy. Any custom customization policies you create override the global default. You can upload a maximum of five themes to each policy. Adding multiple themes to each policy gives your organizers more options, allowing them to select the right branding for different meetings and events.

To create or manage meeting themes, follow these steps.

### Create a new customization policy or edit an existing policy

1. In the left navigation of the Teams admin center, expand **Meetings**, and then select **Customization policies**.
2. Select an existing policy or create a new one.
3. Within your chosen policy, go to the **Customize meeting visuals** section.
4. If you're creating a new policy, select **Add a theme**. If you're managing an existing policy, select **Edit meeting themes** to make changes to your theme.

### Upload your logo, images, and set your custom color

1. In the **Meeting themes** pane:

    1. Under **Logo**, select the **Upload logo** buttons to upload a light and dark version of your logo. These square logos appear on key surfaces during the meeting or event, including the lobby screen.
    2. Under **Images**, select the **Upload image** buttons to upload a light and dark version of your custom image. Your organization's images are shown on the meetings or event screen and provide a colorful backdrop.
    3. Under **Color**, enter the hex code value of your organization's color, which displays on key surfaces of the meeting or event experience. To meet accessibility standards, the final color might differ from the color you enter.
2. Select **Preview** and then go to the **Theming colors** tab to see how your logo, images, and colors look on desktop.

### Upload images for your branded meeting reactions

1. In the **Meeting themes** pane, under **Custom reactions**, select **Upload** next to the reaction you want to customize.

    [![Screenshot of the Meeting themes pane, showing the Custom reactions section and the Upload option for each reaction.](media/meeting-themes-custom-reactions-small.png)](media/meeting-themes-custom-reactions.png#lightbox)
2. On the **Static reaction** tab, upload your PNG file, and then select **Next**.

    If you need to remove a custom uploaded image and return to the default reaction, select **Revert** next to the reaction.
3. On the **Animated reaction** tab, upload your corresponding PNG sprite file. You can download a sample sprite file to use as a reference. Select **Save**.
4. Select **Preview**, and then go to the **Custom reactions** tab to confirm your custom reaction appears as expected.
5. Repeat these steps for each reaction you want to customize.

### Apply your theme and make it active

1. When you finish setting up your theme, select **Apply** to apply your changes.
2. On your theme's row in the **Custom meeting visuals** table, switch the **Currently active** toggle to **On**.

### Assign the customization policy to users or groups

You can add up to five themes to a customization policy. After you add your themes, select **Save** to save your changes.

Then, assign the customization policy to specific users or groups in your organization. To learn more, see [Assign policies to users and groups](assign-policies-users-and-groups).

Note

Although you can access custom meeting visuals from the meeting policies page, we recommend accessing it through customization policies to avoid navigating through global organizational default policies.

## Allow organizers to turn off meeting themes for a meeting

You can give meeting and event organizers the option to turn off meeting themes for specific meetings and events. When organizers turn off meeting themes, the meeting reverts to the default Teams theme.

To allow your meeting organizers to turn off meeting themes:

1. Go to the **Meeting customization policy**.
2. Turn the **Allow organizer to control meeting theme** toggle **On**.

Meeting organizers can turn off meeting themes by following these steps:

1. Go to the **Meeting options** menu for a meeting.
2. Turn the **Meeting theme** meeting option **Off**.

Note

- For recurring meetings or series, the meeting option applies for every instance of the meeting.
- Meeting themes aren't disabled for meetings and events that are in progress. To apply changes, your users must end the call and restart the meeting or event.

## Manage meeting themes in PowerShell

To upload images, you must use the Teams admin center. You can manage meeting themes by using the following PowerShell cmdlets in Teams PowerShell:

- [Set-CsTeamsMeetingBrandingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingbrandingpolicy)
- [Grant-CsTeamsMeetingBrandingPolicy](/en-us/powershell/module/teams/grant-csteamsmeetingbrandingpolicy)
- [New-CsTeamsMeetingBrandingPolicy](/en-us/powershell/module/teams/new-csteamsmeetingbrandingpolicy)

This example assigns a meeting theme policy called 'Policy Test' to a group named group@contoso.com.

```PowerShell
Grant-CsTeamsMeetingBrandingPolicy -Group group@contoso.com -PolicyName "Policy Test" -Rank 1
```

This example assigns a meeting theme policy called 'Policy Test' to a user named alice@contoso.com.

```PowerShell
Grant-CsTeamsMeetingBrandingPolicy -identity "alice@contoso.com" -PolicyName "Policy Test"
```

You can assign meeting customization policies to users or groups with a Teams Premium license in your organization.

## Platform support

To view the list of platforms that support this feature, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-personalized-meetings).

Note

Images aren't visible on mobile clients.

| Asset type | Join Launcher | Pre-Join | Lobby | Meeting Stage | Invite |
| --- | --- | --- | --- | --- | --- |
| **Logo** | Yes | Yes | Yes | No | Yes |
| **Image** | Yes | Yes | Yes | No | No |
| **Color** | Yes | Yes | Yes | Yes | No |

Note

Logos added to the meeting theme override any logos you upload to meeting invitations. To learn more about meeting invitations, see [Customize meeting invitations](customize-meeting-invitations).

Note

If your users edit a meeting invite with Teams calendar after sending it, the logo might not appear when they resend the invite.

## Who can view a meeting theme

While only licensed users who are assigned a meeting customization policy can create meeting theme-enabled meetings and events, anyone can view the themes that are applied to a meeting or event. These users include:

- Teams Premium licensed users in your organization
- Users in your organization that don't have a Teams Premium license
- Guests
- External Users
- Anonymous users

## Best practices for meeting themes

- Use only your organization's official image assets. Don't use image content that you don't own.
- Work with your brand and marketing team to ensure that your image assets and colors together follow your organization's brand guidelines.
- Ensure you're using high-quality logo images, which are visible on small and large screen devices.
- Colors generated in Teams might differ from your brand colors. This process was created to ensure Microsoft Accessibility Standards are met.
- Users with high-contrast device settings can't see meeting themes.

### Accessibility

Here are a few points to ensure accessibility requirements are met:

- Follow existing UI patterns and structure – The current structure and text on the screen aren’t being modified with this feature.
- Image Contrast Ratio – Image assets must meet the 4:5:1 color contrast ratio.
- Accessible color generation support – We calculate the accessible color output that is the closest match to the brand color input while maintain Microsoft Accessibility standards.
- High contrast support – For users with high contrast settings enabled, branding doesn't apply. They continue to see the default Teams meeting experience.
- Controls – You and your organizers can prevent users with accessibility concerns from seeing the branding through:
    - Policies – To ensure users with accessibility concerns don't create branding-enabled meetings, avoid assigning them a customization policy.
    - Meeting Options – Meeting organizers can turn off themes if a user with accessibility concerns joins their meeting or event.

## Use cases for multiple departments or business units in one organization

Some organizations have multiple business units under different brand identities within the same organization. In these cases, you can create meeting customization policies that are dedicated to each brand. They can also assign a department or business unit user group to a specific policy.

Contoso Ltd. has a single organization in Microsoft Teams, with everyone in their organization's user profiles across different business organizations. The company is looking to adopt custom branded meetings in Teams to increase their brand presence with their clients and encourage an internal corporate culture.

Contoso has two business units (BUs) under their organization: Contoso Technical Services and Contoso Education. Both BUs have their own distinct brand imagery, and want to display their branding during their internal and external meetings.

To support this use case, Contoso's admins can create two distinct customization policies:

- Policy A - Contoso Technical Services – houses Contoso Technical Service’s brand logo, image, color, and custom reactions.
- Policy B - Contoso Education – houses Contoso Education’s brand logo, image, color, and custom reactions.

They can proceed to assign the licensed users in Contoso Technical Services to Policy A, and licensed users of Contoso Education to Policy B.

[![Screenshot of policy A, Contoso Technical Services' meeting theme featuring their brand logo, image, and colors.](media/meeting-themes-tech-services-small.png)](media/meeting-themes-tech-services.png#lightbox)