---
layout: Conceptual
title: Join meetings on Teams Rooms using a QR code - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/teams-rooms-qr-codes
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
ms.date: 2026-04-13T00:00:00.0000000Z
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-consoles
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: 'Admins learn how to use and configure QR codes on Microsoft Teams Rooms on Windows and Microsoft Teams Rooms on Android to join a meeting. This is an alternative proximity join experience for easier ad-hoc usage of meeting rooms. '
locale: en-us
document_id: da00476e-2edb-5ae0-3236-57360fe65f78
document_version_independent_id: da00476e-2edb-5ae0-3236-57360fe65f78
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/teams-rooms-qr-codes.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/teams-rooms-qr-codes
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/teams-rooms-qr-codes.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e7dab3af-2e0a-e1dc-5a82-00793235fd05
---

# Join meetings on Teams Rooms using a QR code - Microsoft Teams | Microsoft Learn

**Teams Rooms on Windows** and **Teams Rooms on Android** let users scan a QR code on the home screen to join a meeting, start an ad hoc meeting, or cast content from a mobile device. QR code join is available with all Teams Rooms licenses.

A QR code is displayed by default on the Teams Room home screen. To ensure security, the QR code is refreshed every minute. You can hide the room QR code from the home screen by disabling the feature through the [Teams Pro Management Portal](enrolling-mtrp-managed-service).

![Teams Rooms home screen showing QR code.](media/teams-rooms-qr-codes/mtrhomeqr.png)

Once a user scans the QR code with their mobile camera, they can select an action on their mobile device that they would like to perform with the room system. The user can choose from either:

- Joining an ongoing meeting on their mobile calendar or any meeting that begins within 10 minutes,
- Starting an ad-hoc meeting, or
- Casting content from their mobile device to the front of room display.

Cross-tenant meetings are also supported when the Teams external access organization settings and user policies in the Teams admin center allow it. For more information, see [Organization settings and user policies for external access](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings&amp;branch=main). If the meeting participant using QR code join from their device is unable to bypass the Teams Meeting lobby, the QR code join will fail as the participant is unable to add an additional device to the meeting from the lobby due to security restrictions.

If the user doesn't have the Teams iOS or Android mobile app, they will be directed to download it after scanning the QR code.

![Actions on the Teams mobile app that a user can take after scanning the QR code on a Teams Room device.](media/teams-rooms-qr-codes/mobileqr.png)

Under **Join with room**, users can select an online Teams meeting that is in progress or scheduled to start within 10 minutes.

After the user selects an action on their mobile device, by default, the room system automatically accepts the meeting nudge and joins the meeting without additional user action. The user then enters the full meeting experience on Teams Rooms and the room companion mode experience on Teams mobile. You can disable the room auto-accept functionality for any QR code meeting join through the [Teams Pro Management Portal](enrolling-mtrp-managed-service).

After scanning the QR code, the user has two minutes to select an action on the mobile device. After two minutes, automatic acceptance is disabled, and the user must select Accept on the room console or touch display.

## Configure QR code settings in Teams Rooms Pro Management Portal

### Hide the room QR code

1. In the [Teams Pro Management Portal](enrolling-mtrp-managed-service), select the room device.
2. Go to **Device settings**.
3. Turn off **Show room QR code**.
4. Save your changes.

### Disable automatic acceptance for QR code joins

1. In the [Teams Pro Management Portal](enrolling-mtrp-managed-service), select the room device.
2. Go to **Device settings**.
3. Turn off **Automatically accept proximity-based meeting invitations**.
4. Save your changes.

## Requirements for Teams Rooms and Teams mobile

To enable your users to join meetings using QR codes:

1. Your Teams Rooms devices must be running on the following app version:

    1. Teams Rooms on Windows - version 5.0.111.0 or later
    2. Teams Rooms on Android - version 1449/1.0.96.2024042506 or later
2. Your users' mobile devices must have the following app version installed:

    1. iOS - version 6.7.0 or later
    2. Android - version 1416/1.0.0.2024071301 or later

Important

Although there are many QR code scanner apps available, we recommend using the built-in camera app or code scanner app that are natively available on all iOS and Android devices. If your users are using an Android device with both work and personal profiles enabled, both the Teams app and the camera app and/or the code scanner app must be listed under the same profile. Otherwise, if they are in separate profiles, the camera app and/or the code scanner app isn't able to correctly scan and transfer the information over to the Teams app. For more information about adding the Teams app and camera app and/or code scanner app to a work profile, see [Manage Android Enterprise system apps in Microsoft Intune](/en-us/mem/intune/apps/apps-ae-system).

Warning

If your Teams Rooms on Windows devices have existing custom backgrounds, your custom backgrounds may be impacted with this new element on the home screen. You can find the latest home screen templates and updated custom background design guidelines at [Set up and manage Teams Rooms on Windows custom backgrounds.](/en-us/microsoftteams/rooms/custom-backgrounds?tabs=Enhanced)