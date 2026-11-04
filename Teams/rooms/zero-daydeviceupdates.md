---
layout: Conceptual
title: Day Zero Updates for Microsoft Teams Rooms, Teams panels, and Teams phones - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/zero-daydeviceupdates
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn about how Teams devices update automatically to supported releases at initial startup reducing deployment friction.
author: MattSlomka
ms.author: mattslomka
manager: srpall
ms.service: msteams
ms.topic: feature-availability
ms.date: 2026-08-26T00:00:00.0000000Z
ms.subservice: itpro-devices
locale: en-us
document_id: 0518df67-49e2-5b86-30aa-86a0472b491b
document_version_independent_id: 0518df67-49e2-5b86-30aa-86a0472b491b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/zero-daydeviceupdates.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/zero-daydeviceupdates
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/zero-daydeviceupdates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 86f0fe81-f342-d275-30c8-acbad33d22ab
---

# Day Zero Updates for Microsoft Teams Rooms, Teams panels, and Teams phones - Microsoft Teams | Microsoft Learn

Day Zero updates (also known as out of box updates) are available for Teams devices (Teams Rooms on Windows, Teams Rooms on Android, Teams panels, and Teams phones) to ensure that devices are automatically updated to supported Teams releases prior to attempting sign in. This process is intended to make onboarding new Teams devices more seamless while also improving security and supportability as devices will be on current releases at first setup.

## How day zero updates work

### Teams Rooms on Windows

When a new or re-imaged Teams Rooms on Windows device is connected to power and network, the Teams Rooms Out of Box Experience (OOBE) runs. Prior to presenting the option to login the OOBE will display a splash screen which states **Updating Teams Room, do not power off the device. The device might restart a few times during the update**. This update process can take anywhere from a few minutes to a few hours depending on the number of updates which need to occur, you will want to leave the device alone while the device updates.

![Zero Day Update for Teams Rooms on Windows ](media/zero-daydeviceupdates/zero-day-update-teams-rooms-windows.png)

In the background, the Teams Rooms on Windows device is downloading and installing one version prior to current of the Teams Rooms on Windows application ([Release Notes for Teams Rooms on Windows](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Windows)) and is updating Windows to the latest feature version supported by that application release ([Teams Rooms on Windows Supported Versions](/en-us/microsoftteams/rooms/rooms-lifecycle-support#windows-release-support)).

Requirements for this process to work:

- A certified Teams Rooms on Windows device
- The device must start with Teams Rooms on Windows application version [4.19.82.0](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Windows#419820-1312024) or later to kick off day zero updates

### Teams Rooms on Android, Teams panel, & Teams phone

When a new or factory reset Teams Rooms on Android, Teams panel, or Teams phone device is connected to power and network, the Teams Rooms Out of Box Experience (OOBE) runs. As soon as a device displays the option to login, it also checks for any available updates to the device, if an update is available, within a few minutes a prompt will display a splash screen which states **The system will start to update** with a 2 minute count down before the update starts automatically. This update process can take anywhere from a few minutes to a few hours depending on the number of updates which need to occur, you will want to leave the device alone while the device updates.

In the background, the Teams Android device is downloading and installing the latest certified firmware and any new applications (view release notes for: [Teams Rooms on Android](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Android), [Teams panels](/en-us/microsoftteams/devices/devices-release-notes?tabs=panels), [Teams phone](/en-us/microsoftteams/devices/devices-release-notes?tabs=phones), or [management apps](/en-us/microsoftteams/devices/certified-device-apps)).

Requirements for this process to work:

- A certified Teams Rooms on Android, Teams panel or Teams phone device
- The device must already have Teams Admin Agent version [1.0.0.202507210031](/en-us/microsoftteams/devices/certified-device-apps?tabs=Agent#100202507210031) or later to kick off day zero updates

## Frequently Asked Questions

Can the day zero update feature be skipped?

> 
> No. day zero updates are there to ensure supportability and security of devices, they can’t be skipped.

Does Microsoft’s day zero update implementation impact anything a Teams device manufacturer may have built?

> 
> No. The manufacturer day zero update process runs first so the Teams device will already be updated to the latest prior to the Microsoft day zero update logic checking for updates.

Do government cloud-based devices behave differently?

> 
> No. Because the Teams device is not yet signed in, there is no difference in functionality regardless of the cloud the device will access after updating.

What URLs are required for day zero updates?

> 
> The same URLs required for device functionality day to day are used to perform the day zero update mechanism. See Teams Device Security for more information.