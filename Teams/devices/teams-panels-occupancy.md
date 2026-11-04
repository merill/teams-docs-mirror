---
layout: Conceptual
title: Occupancy state on Teams panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/teams-panels-occupancy
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
ms.date: 2025-03-11T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: This article provides you with the information needed so that Teams panels show the correct status when they are in a call, free, or when the meeting room is occupied.
locale: en-us
document_id: 3cdddee1-7540-0f55-e5e9-1594139b5778
document_version_independent_id: 3cdddee1-7540-0f55-e5e9-1594139b5778
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/teams-panels-occupancy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/teams-panels-occupancy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/teams-panels-occupancy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b0da858e-3428-5d35-be18-5f5d1381d2eb
---

# Occupancy state on Teams panels - Microsoft Teams | Microsoft Learn

Teams panels can now smartly utilize signals from Teams Rooms devices and occupancy sensors paired with Teams panels to indicate when a room is in use, so users aren't surprised to find an available room is occupied.

Access to this feature is dependent on the version of Teams panels app installed and the license assigned to the resource account that is signed in to that Teams panel. Verify the following:

- The Teams panel is running on version 1449/1.0.97.2025086303 or later.
- The account signed in on your Teams panel device is assigned a Teams Rooms Pro or Teams Shared Devices license.

If the above requirements are met, this feature is on by default. The room is in use when the room isn't currently reserved, and a user is in a call or casting with a Teams Rooms device (Windows or Android), or the room is detected as occupied through a paired occupancy sensor. You can see which occupancy sensors are currently supported at [What's new in Microsoft Teams devices](/en-us/microsoftteams/devices/devices-release-notes?branch=main&amp;tabs=panels).

When the room is in use, the panel's LED adjusts to the color selected by the admin for the busy state. In addition, the panel's home screen reflects that the room is occupied.

Note

The room can still be reserved on the device itself, through Microsoft Outlook, or through Microsoft Teams.

[![Screenshot of Inventory rooms tab.](media/occupy-reserve-low-res.png)](media/occupy-reserve-hi-res.png#lightbox)

If the device is paired with a Microsoft Teams Rooms on Android, after a user reserves the occupied room from the device, a message will appear on the room display to let the user inside of the room know that the room has been reserved and to exit. This notification will be off by default, and the admin will need to enable it after pairing the device. To utilize this feature, please make sure you are on 1449/1.0.96.2025126202 or higher on Teams Rooms on Android.

An admin can choose to turn off these features from the device in Teams admin settings &gt; *Device settings &gt; Occupied state.* The two settings are *Allow occupied state* and *Allow booking notifications*. If *Allow occupied state* is turned off, the booking notifications will also be turned off.