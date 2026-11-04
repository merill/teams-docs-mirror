---
layout: Conceptual
title: Miracast for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/miracast
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Overview of how to enable and use Miracast on Microsoft Teams Rooms
author: elaineho-msftservice
ms.author: elaineho
manager: kspiess
ms.service: msteams
ms.topic: how-to
ms.date: 2026-10-29T00:00:00.0000000Z
ms.subservice: itpro-rooms
locale: en-us
document_id: b7280467-fb81-5d9c-2e0d-a23083047671
document_version_independent_id: b7280467-fb81-5d9c-2e0d-a23083047671
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/miracast.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/miracast
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/miracast.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 5ad089c1-bec0-81e0-c49b-2b86afbcde59
---

# Miracast for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

This article explains how administrators can enable, manage, and support Miracast for Microsoft Teams Rooms on Windows devices, including prerequisites, configuration scope, and operational considerations.

## What is Miracast for Teams Rooms?

Miracast allows users to wirelessly project their Windows device screen to a Microsoft Teams Room on Windows without cables, complementing existing sharing options such as Teams Cast and HDMI ingest. Miracast is disabled by default on Teams Rooms devices but can be enabled with device-level settings. Miracast isn't available for Teams Rooms on Android.

### Miracast operating modes

Miracast has two operating modes:

- **Peer-to-peer projection**: With peer-to-peer, the Miracast sender and receiver can be on entirely separated networks and the wireless adapters in the devices communicate directly with each other.
- **Over the network**: With over the network, the devices must be on the same network in order for the Miracast connection to function.

Over the network is preferred in most scenarios and is used when possible, and peer-to-peer is used if the sender and receiver can't communicate over the same network. Teams Rooms devices are the receiver in this Miracast connection and when Miracast is set to **On**, they support both peer-to-peer and over the network functionality.

For technical details on the implementation of Miracast in Windows and the operating modes, see [Understanding Windows Wireless Projection](/en-us/windows-hardware/design/device-experiences/wireless-projection-understanding).

## Step 1: Confirm requirements

Before enabling Miracast, ensure the following requirements are met:

- Use an all-in-one touch board Teams Rooms on Windows device (Teams Rooms devices with a console are not yet supported)
- License the device with a Teams Rooms Pro license.
- User workstations must support Miracast to use this feature.

## Step 2: Configure Miracast

1. Sign in to the Teams Rooms Pro Management Portal.
2. Select **Rooms**, and then select the room you want.
3. Select **Settings**.
4. Select **Device** and scroll down to Miracast.
5. Toggle **Miracast** to **On**.
6. Toggle the **Connection PIN requirement** as desired.
7. Select **Apply**.

You can also apply these settings across multiple rooms at once using a [settings job](/en-us/microsoftteams/rooms/pro-portal-settings).

Note

To avoid accidental shares, a best practice is to configure the **Connection PIN requirement** setting to **Always on**.

After you finish customizing your Miracast settings in the Pro Management Portal, the changes take effect after a device restart. The device is then discoverable for Miracast projection.

The Miracast beacon name displays the value from the *Computer description* field. To customize this field, you can update this in your settings or use the following PowerShell command.

## Change the Miracast beacon name

```PowerShell
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" -Name "srvcomment" -Value "Miracast Broadcast Name Here"
```

## User experience

After you enable this feature for your organization:

- Users can project content using the Windows built‑in Cast (Win + K) feature.
- Teams Cast and HDMI remain available as alternative forms of sharing with the Teams meeting room.
- Miracast is treated just like the HDMI ingest so content is visible in the room and can also be shared to remote participants in a Teams meeting.
- If the **Automatic screen sharing** toggle in the Pro Management Portal is enabled for this room device, a Miracast projection of the content from your PC is automatically shared into the meeting to remote audiences when casting with Miracast.

### Wireless casting scenarios matrix and outcomes

| PIN requirement | Automatic screen sharing | Outcome |
| --- | --- | --- |
| **Always on** | **On** | - PIN is displayed on the Teams Rooms device after a Miracast session is initiated from a personal device.- After the personal device is authorized by the user, content from that device is automatically cast onto the Teams Rooms front-of-room (FoR) display and into the remote meeting. |
| **Always on** | **Off** | - PIN is displayed on the Teams Rooms device after a Miracast session is initiated from a personal device.- After the personal device is authorized by the user, content from that device is automatically cast onto the Teams Rooms FoR display.- To share content to remote participants, the user must initiate from the share tray during the meeting. |
| **First time only** | **On** | - PIN is displayed on the Teams Rooms device after a Miracast session is initiated from a personal device if it's the first time for that device.- After a personal device has been authorized once by the user, content from that device is automatically cast onto the Teams Rooms FoR display and into the remote meeting. |
| **First time only** | **Off** | - PIN is displayed on the Teams Rooms device after a Miracast session is initiated from a personal device if it's the first time for that device.- After a personal device has been authorized once by the user, content from that device is automatically cast onto the Teams Rooms FoR display.- To share content to remote participants, the user must initiate from the share tray during the meeting. |
| **Off** | **On** | - PIN isn't displayed on the Teams Rooms device after a Miracast session is initiated from a personal device.- Content from the personal device is automatically cast onto the Teams Rooms FoR display and into the remote meeting. |
| **Off** | **Off** | - PIN isn't displayed on the Teams Rooms device after a Miracast session is initiated from a personal device.- Content from the personal device is automatically cast onto the Teams Rooms FoR display.- To share content to remote participants, the user must initiate from the share tray during the meeting. |

For more information about the user experience, see [Cast content to a Microsoft Teams Room using Miracast](https://support.microsoft.com/office/cast-content-to-a-microsoft-teams-room-using-miracast-2fea0380-f82e-42e5-a8b4-f6c7167affab).