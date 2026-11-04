---
layout: Conceptual
title: Whiteboard on Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/whiteboard-rooms
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: yoojinjung
ms.date: 2026-04-23T00:00:00.0000000Z
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- teams-rooms-consoles
- Tier1
ms.custom: QuickDraft
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn how to use Microsoft Whiteboard on Microsoft Teams Rooms to enhance collaboration during and outside of scheduled meetings.
locale: en-us
document_id: 993345be-44cf-8358-e7d7-992f79ea5a8a
document_version_independent_id: 993345be-44cf-8358-e7d7-992f79ea5a8a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/whiteboard-rooms.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/whiteboard-rooms
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/whiteboard-rooms.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/622cdb89-fa44-4dc3-87e9-f495242dcd5a
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d1478bb7-eb0a-4eae-b619-c1761960995f
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 8f420ae5-e6da-c120-5382-b69648ca9dc1
---

# Whiteboard on Teams Rooms - Microsoft Teams | Microsoft Learn

Microsoft Whiteboard on Microsoft Teams Rooms is a tool for enhancing collaboration by allowing participants to visually share ideas and work together in real-time, no matter where they are. This article provides information on how to use Whiteboard in both meeting and nonmeeting scenarios.

For more information on Microsoft Whiteboard, see [Introduction to Microsoft Whiteboard](/en-us/microsoft-365/whiteboard).

## Whiteboard outside of a meeting

Brainstorm effortlessly in the office by tapping the **Whiteboard** button on the home screen. With a single touch, Microsoft Whiteboard launches, enabling collaboration outside of a Teams meeting.

- **Temporary Whiteboards:** Since resource accounts don't have OneDrive, starting a whiteboard from Teams Rooms creates a temporary session. To save your work, start a meeting following the steps below or on Teams Rooms on Windows select the **Save** button and invite your Teams work account. This ensures the whiteboard is saved to OneDrive for Business.

    Temporary whiteboard example:

    ![Whiteboard example for content that isn't saved to OneDrive for Business.](media/whiteboard-rooms/whiteboard-image-1.png)

    Warning

    Users get an error to save the Whiteboard if they invite a participant who doesn't have OneDrive or has invited a guest.
- **Switch to online collaboration:** Transition seamlessly from local to online collaboration by selecting **Start meeting** on the whiteboarding screen. This initiates an ad-hoc meeting and presents a temporary whiteboard. Add participants to the meeting and collaborate in real-time. The temporary whiteboard is saved to the OneDrive of the first participant, in the same tenant, who doesn't join through a Teams Rooms device. Participants get an email from the whiteboard owner with a link to the whiteboard. Additionally, participants can access the whiteboard in the meeting chat's **Meeting Whiteboard** tab menu.

    Once it's saved to a participant's OneDrive for Business:

    ![Whiteboard example for content that is saved to OneDrive for Business.](media/whiteboard-rooms/whiteboard-image-2.png)

After you select Start meeting, invite at least one participant who joins from a device other than Teams Rooms. A whiteboard doesn't become collaborative when the only participants are using Teams Rooms devices.

## Whiteboard in a meeting

When a remote participant shares a whiteboard in a meeting, Teams Rooms displays it in the shared content area.

- **Interactive whiteboarding:** If your Teams Rooms device is a Touch board or configured with a touch-enabled Front of Room display, you can interact with the shared whiteboard.
- **Start a whiteboard:** To start a whiteboard during a meeting from Teams Rooms devices, tap **Share** button and select **Microsoft Whiteboard**. To use this feature, ensure that your tenant settings meet the requirements outlined in Manage sharing for Microsoft Whiteboard to have the Start Whiteboard feature.
- If the meeting is scheduled by a non-MTR user in the same tenant, the whiteboard is saved in the organizer's OneDrive if they're present when the whiteboard is initiated. If the organizer isn't present when the whiteboard is initiated, the whiteboard will instead be saved in the OneDrive of a non-MTR participant present in the meeting.

## Teams Rooms on Windows

The **Start whiteboard** feature is enabled by default for Touch board devices like Surface Hub 3. This means:

- **Home screen:** The **Whiteboard** button appears outside of meetings next to **Calendar**.
- **In-meeting Share Tray:** The **Microsoft Whiteboard** option is available.

## Configure a touch-enabled front-of-room display

You can connect a touch-enabled front-of-room display to a Teams Rooms on Windows device that uses a separate touch console. Connect the display’s video and touch connections to the Teams Rooms compute module according to the display manufacturer’s instructions. Ensure that the compute module has the required video and USB connections available.

After you connect the display, configure Windows to associate touch input with the correct screen:

1. Connect a keyboard to the Teams Rooms device.
2. On the Teams Rooms console, select **More** &gt; **Settings**, enter the administrator credentials, and then select **Windows Settings** &gt; **Go to Admin Sign-in**.
3. Sign in to Windows with the local administrator account.
4. In the Windows search box, search for and open **Calibrate the screen for pen or touch input**.
5. In **Tablet PC Settings**, under **Display options**, select the touch-enabled front-of-room display.
6. Under **Configure**, select **Setup**, and then select **Touch input**.
7. Follow the instructions that appear on each display. Touch the front-of-room display when prompted. If the prompt appears on a non-touch display, press Enter to move the prompt to the next display.
8. After the front-of-room display is identified, complete the on-screen calibration steps if calibration is required.
9. Sign out of the administrator account, and then return to the Teams Rooms account.

After configuration, users can interact with Microsoft Whiteboard directly on the touch-enabled front-of-room display.

Note

Configure touch input for the front-of-room display without changing the existing touch-console configuration. The connections and calibration options available can vary by Teams Rooms system and display manufacturer.

The feature is available in Worldwide and GCC environments.

Even if the **Start Whiteboard** feature is disabled and/or your Teams Rooms device isn't a Touch board device like Surface Hub 3, you can view and follow whiteboards shared by remote participants in a meeting. It mirrors a remote participant's view when the remote participant uses the [Follow me](https://support.microsoft.com/office/guide-participants-through-a-whiteboard-with-follow-e5950c68-4fe1-4567-b39f-8fe523abc67a) feature on the whiteboard.

## Teams Rooms on Android

The **Start Whiteboard** feature is enabled by default for any Teams Rooms on Android devices. We recommend enabling the Start Whiteboard feature only for Touch board devices because they are certified for the best whiteboarding experience. When the feature is enabled:

- **Home screen:** The **Whiteboard** button appears outside of meetings next to **Calendar**.
- **In-meeting Share Tray:** The **Microsoft Whiteboard** option is available.

The feature is available in Worldwide and GCC environments.

Even if the **Start Whiteboard** feature is disabled on your Teams Rooms on Android device, you can view and follow whiteboards shared by remote participants in a meeting. It mirrors a remote participant's view when the remote participant uses the [Follow me](https://support.microsoft.com/office/guide-participants-through-a-whiteboard-with-follow-e5950c68-4fe1-4567-b39f-8fe523abc67a) feature on the whiteboard.

Note

If needed, you can disable the **Start Whiteboard** feature via the admin setting on your device or by applying a configuration profile in Teams Admin Center under **Allow room to use Microsoft Whiteboard** setting in the **Meeting settings** section.