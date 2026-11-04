---
layout: Conceptual
title: OEM image creation for Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/console
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
ms.reviewer: travis-snoozy
manager: pamgreen
ms.date: 2026-11-04T00:00:00.0000000Z
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
description: This article describes how an OEM creates an image for a Teams Rooms device.
locale: en-us
document_id: 6f8b204f-9650-d268-8566-7a75ba0a1b6a
document_version_independent_id: 9a963e63-6716-7522-8abe-c8a407d3a46d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/console.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/console
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/console.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 3248b838-3c5d-8779-8fae-dec753357750
---

# OEM image creation for Teams Rooms - Microsoft Teams | Microsoft Learn

Caution

This information is intended for manufacturers to create images. This article doesn't allow creation of a "build your own" Teams Room, deploying an image created with this method on a device not certified for Teams Rooms won't function.

Note

If you're recovering a device, contact your Original Equipment Manufacturer (OEM) for support. The following steps should only be used when creating a [WIM-based image](/en-us/windows-hardware/manufacture/desktop/capture-and-apply-an-image) for mass deployment.

## Prepare the installation media

Creating the Microsoft Teams Rooms installation media requires a USB storage device with at least 32 GB of capacity. There should be no other files on the device; any existing files on the USB storage will be deleted. The script requires a specific Windows ISO in order to generate the installation media. That ISO is available only through [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/).

Note

The process below is for creating installation media to image new Microsoft Teams Rooms devices. New devices out of the box automatically update to the latest Teams Rooms and Windows versions. Devices already deployed update automatically using the Pro Management Portal.

1. Download the [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).
2. Run the CreateSrsMedia.ps1 script from an elevated prompt on a Windows machine.
3. Follow the script's instructions to create a Microsoft Teams Rooms USB setup disk.

Tip

Each time the CreateSrsMedia.ps1 script starts, the screen output includes the name of a log file or transcript for the session. If there are issues with running the script, make sure to have a copy of that transcript available when requesting support.

When finishes, you can safely eject and remove the USB disk from your computer and proceed to [Install Windows and the Microsoft Teams Rooms console app](console#Reimage).

## Install Windows and the Microsoft Teams Rooms console app

You now need to apply the installation media.

Important

Installation is supported only on [certified Microsoft Teams Rooms on Windows hardware](certified-hardware?tabs=Windows). The Teams Rooms application won't operate and isn't supported on noncertified device.

1. If the target device is installed in a dock (for example, a Surface Pro), disconnect it from the dock.
2. Ensure the target device isn't connected to the network.
3. Ensure the target device is connected to power.
4. Plug your USB setup disk into the target device.
5. Boot to the USB setup disk. Refer to the manufacturer instructions. If your target device is a Surface Pro, use the following steps to boot to the USB setup disk:

    a. Press and continue to hold the volume down (-) button. b. Press and release the power button. c. Once Windows setup is booted, release the volume down (-) button.
6. The system shuts down once installation is complete.

After the system shuts down, it's safe to remove the USB installation media. A drive image can now be captured from this device, for use in bulk deployment of identical hardware if necessary.