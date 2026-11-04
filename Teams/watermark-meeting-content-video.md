---
layout: Conceptual
title: Require a watermark for sensitive Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/watermark-meeting-content-video
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: maahma
ms.date: 2025-01-16T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
- Tier1
description: Learn how to enable or require watermarks on attendee video and shared content in sensitive Teams meetings.
locale: en-us
document_id: e59935c0-1654-e630-41f0-8c42ba9c0464
document_version_independent_id: e59935c0-1654-e630-41f0-8c42ba9c0464
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/watermark-meeting-content-video.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: watermark-meeting-content-video
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/watermark-meeting-content-video.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 92eb8a27-e40c-98e7-7daa-4fae6dbc8ff0
---

# Require a watermark for sensitive Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

Note

In Teams events, this feature is available only in events with up to 1,000 attendees.

As an admin, can allow organizers with a Teams Premium license to turn on watermarks in Teams meetings both for content shared on screen and for participant's video. The watermark displays the email address of the meeting participant. Each participant sees their own email address overlaid on the meeting video or shared content. Watermarks deter participants from taking unauthorized screenshots of the meeting content. To understand how your organizers use watermarks, see [Watermark for Teams meetings](https://support.microsoft.com/office/watermark-for-teams-meetings-a9166432-f429-4a19-9a72-c9e8fdf4f589).

Watermarks are supported on Teams desktop, mobile, and Microsoft Teams Rooms. Watermarks are also supported on live share, PowerPoint Live, and Excel Live. Users joining meetings from unsupported platforms have an audio-only experience.

The following participants have an audio-only experience when a watermark is in use:

- Virtual Desktop Infrastructure (VDI) participants
- Anonymous participants
- Overflow participants
- Older Teams clients
- [Direct Guest Join on Microsoft Teams Rooms devices](/en-us/microsoftteams/rooms/third-party-join)

[![Screenshot of Contoso Education's meeting theme featuring their brand logo, image, and colors.](media/watermark-small.png)](media/watermark-expand.png#lightbox)

Note

Meeting settings in sensitivity labels and custom meeting templates require a Teams Premium license.

Meeting watermarks are managed in the Teams admin center. After you turn on watermarks, organizers with a Teams Premium license can add them to their meetings, or you can enforce watermarks with a template or sensitivity label.

The following table shows where watermarks are configured:

| Setting | Admin policy | Sensitivity label | Template | Meeting organizer |
| --- | --- | --- | --- | --- |
| Apply a watermark to shared content | Yes | Yes | Yes | Yes |
| Apply a watermark to everyone's video feed | Yes | Yes | Yes | Yes |

When a watermark is being used in a meeting, the following features are turned off:

- Large gallery
- Content from camera

## Watermarks for sensitive and highly sensitive meetings

Watermarks can be useful for protecting confidential information shared in meetings. This is most useful when sharing information with users who don't normally have access to the information. For example, a member in the finance organization might use watermarks when sharing quarterly estimates with managers from different divisions.

Watermarks are designed to reduce the chances that confidential information being transferred out. Using watermarks in meetings where all the participants have direct access to the content being shared might not add to security.

For information about using watermarks with other meeting features to help protect confidential information in meetings, see [Configure Teams meetings with protection for highly sensitive data](/en-us/microsoftteams/configure-meetings-highly-sensitive-protection).

## Meeting recordings

If a meeting with a watermark is recorded, Microsoft Stream applies the watermark at playback time. Viewers of the recording see their own email address as a watermark on the video. If the recording file is edited or moved, the watermark isn't available at playback time.

By default, download of the meeting recording (.mp4) file is turned off for watermarked meeting recordings. However, the user who recorded the meeting can change that permission. Downloaded .mp4 files don't contain a watermark.

## Manage watermarks

You can turn on watermarks for your organizers in the Teams admin center. You can use sensitivity labels to enforce watermarks even if you turn them off for the meeting organizer in this meeting policy.

To manage watermarks for meetings, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one.
3. Within your chosen policy, go to the **Content Protection** section.
4. For watermarks on attendee video, turn the **Watermark videos** toggle **On** (default) or **Off**.
5. For watermarks on content shared on screen in a meeting, turn the **Watermark shared content** toggle **On** or **Off**.
6. To set the watermark pattern or transparency, or see a preview, select **Edit settings**. Select **Apply** if you make changes.
7. Select **Save**.

    You can also turn watermarks on or off by using PowerShell. Use the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet with the **`-AllowWatermarkForCameraVideo`** and **`-AllowWatermarkForScreenSharing`** parameters.

    For example:

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 
    
    Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
    ```

## Platform support

To view the list of platforms that support this feature, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-advanced-management-for-meetings).