---
layout: Conceptual
title: Enroll and provision Teams Android devices in the Pro Management portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/provisionandroiddevicespromanagementportal
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Enroll and provision Teams Android devices in the Pro Management portal
author: ivlists
ms.author: vapati
ms.service: msteams
ms.topic: how-to
ms.date: 2026-11-01T00:00:00.0000000Z
ms.subservice: itpro-devices
ms.manager: srpall
manager: srpall
locale: en-us
document_id: 405b8b21-f19e-d37a-3002-804303d88a1e
document_version_independent_id: 405b8b21-f19e-d37a-3002-804303d88a1e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/provisionandroiddevicespromanagementportal.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/provisionandroiddevicespromanagementportal
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/provisionandroiddevicespromanagementportal.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: fcade2b7-70b6-365f-6747-9c65914cfb1f
---

# Enroll and provision Teams Android devices in the Pro Management portal - Microsoft Teams | Microsoft Learn

Use the **Microsoft Teams Rooms Pro Management portal (PMP)** to enroll and provision Teams Android devices for your organization. You attest each device to your tenant with a verification code, activate it on-site, and then remotely sign in a device account — all from a single page.

This experience centralizes Android device provisioning in PMP and replaces the equivalent experience in the **Microsoft Teams admin center (TAC)**. It supports Microsoft Teams Rooms on Android (MTR-A), Teams panels, Teams phones, and SIP devices.

Important

**Admin Agent version 1.0.0.202407020009** or later is required to provision Teams Android devices in PMP. [Day zero updates](/en-us/microsoftteams/rooms/zero-daydeviceupdates) should automatically update devices to this build or later to ensure provisioning within the Pro Management Portal functions.

## Prerequisites

Before you begin, make sure you have the following:

- A device running a supported **Admin Agent** version (see the note above).
- A **device account** created in Microsoft Entra ID for each device you plan to sign in. Personal user credentials aren't supported for remote sign-in.
- One of the following roles. Android provisioning uses the same access model as Windows Autopilot devices in PMP — no additional or more restrictive roles are required.

| Role | Access |
| --- | --- |
| Global Administrator | Add, edit, delete, generate verification codes, and sign in a user |
| Teams Administrator | Add, edit, delete, generate verification codes, and sign in a user |
| Teams Device Administrator | Add, edit, delete, generate verification codes, and sign in a user |

## Supported device types

| Device type | ID type used |
| --- | --- |
| Microsoft Teams Rooms on Android (MTR-A) | MAC address |
| Teams panels | MAC address |
| Teams phones | MAC address |
| SIP IP phones | MAC address |
| SIP analog | Hardware ID (analog) — `MAC address:port` |

Note

SIP analog devices are identified by a **Hardware ID (analog)** rather than a MAC address.

## How provisioning works

In PMP, go to **Planning** &gt; **Android Devices** to open the **Provision Android devices** page. This page is the hub for every provisioning action — adding devices, generating verification codes, tracking status, and signing in users.

The page shows a list of devices with these columns:

| Column | Description |
| --- | --- |
| ID | The MAC address or Hardware ID of the device |
| ID type | **MAC address** or **Hardware ID (analog)** |
| Location | An optional location tag you assign |
| Provisioning Status | The current stage of the device in the provisioning lifecycle |

Use the **ID type** and **Provisioning Status** filters, or the search box, to narrow the list.

**Provisioning Status** values:

- **Awaiting activation** — The device has been added and has (or is awaiting) a verification code, but hasn't yet been activated on the hardware.
- **Ready for provisioning** — The device has been activated with its verification code and is ready for a user to be signed in.

### End-to-end workflow

| Step | Action | Result |
| --- | --- | --- |
| 1 | Add device(s) — manually (**Add**) or in bulk (**Upload** a CSV) | Devices appear with the **Awaiting activation** status |
| 2 | Select the device(s) and select **Generate verification code** | A verification code is issued for each device |
| 3 | Export or share the verification code with the on-site technician or user | Code shared; device awaits on-site input |
| 4 | The technician enters the code on the physical device | Device completes activation |
| 5 | The device moves to **Ready for provisioning** automatically | Device is signed out and ready |
| 6 | Remotely sign in a user — select **Sign in a user** and follow the steps | Device is fully provisioned and deployed |

## Add devices

### Add a single device

1. Go to **Planning** &gt; **Android Devices**.
2. Select **Add**.
3. In the dialog, select the **ID type** — **MAC address** or **Hardware ID (analog)**.
4. Enter the **MAC address** (format `XX-XX-XX-XX-XX-XX`) or **Hardware ID**.
5. Optionally, enter a **Location**.
6. Select **Save**.

The device appears in the list with the **Awaiting activation** status and no verification code yet.

Note

MAC addresses and Hardware IDs are unique. Re-adding an ID that already exists doesn't create a duplicate and doesn't overwrite the existing entry or its verification code. A code changes only when you explicitly select **Generate verification code**.

### Add devices in bulk with a CSV file

1. On the **Provision Android devices** page, select **Upload**.
2. In the **Upload CSV to associate devices** dialog, select **template** to download the CSV template.
3. Fill in the template columns: **ID**, **ID Type** (`macAddress` or `hardwareId`), and **Location** (optional).
4. Select **Select file** and choose your completed CSV.
5. Select **Upload**. The results appear in the device list once the file is processed.

CSV columns:

| Column | Required | Values |
| --- | --- | --- |
| ID | Yes | MAC address (`XX-XX-XX-XX-XX-XX`) or Hardware ID (`XX-XX-XX-XX-XX-XX:YYY`) |
| ID Type | Yes | `macAddress` or `hardwareId` |
| Location | No | Free text (for example, `BLR`, `US`) |

Note

In the CSV, enter the **ID Type** value exactly as `macAddress` or `hardwareId`. These are the literal values the template expects — they differ from the display labels shown in the portal (**MAC address** and **Hardware ID (analog)**).

Example:

> 
> ID,ID Type,Location 64-16-7f-e1-2b-1c,macAddress,US 00-90-8f-08-c4-94,macAddress,BLR 00-e0-db-89-25-22:099,hardwareId,BgFg

Note

You can upload a maximum of **500 devices** in a single CSV file.

## Generate a verification code

A verification code is a unique, time-limited, six-digit code that's entered on the physical device during setup to complete provisioning.

1. In the list, select one or more devices with the **Awaiting activation** status.
2. Select **Generate verification code**.
3. A unique code is generated for each selected device. To view a code, select a device to open its details pane.
4. Share the code with the person deploying the device on-site.

Tip

To share codes for many devices at once, select the arrow next to **Generate verification code** and choose **Export verification codes**. PMP downloads a CSV file that contains each device's MAC address or Hardware ID and its verification code.

### Verification code states

| State | Display | Description |
| --- | --- | --- |
| Not generated | — (dash) | No code has been generated yet |
| Active | Six-digit code (for example, `036905`) | The code is valid and can be entered on the device |
| Expired | Expired | The code is no longer valid; generate a new one |

Important

Verification codes are valid for **24 hours**. After a code expires, it can't be used on the device — select the device and choose **Generate verification code** again to issue a new one.

## Edit a device

1. In the list, select a device.
2. Select **Edit**.
3. Update the **ID**, **ID type**, or **Location**.
4. Select **Save**.

Warning

If you change a device's **MAC address** or **Hardware ID**, its existing verification code is immediately invalidated and the code resets to — (dash). You must select **Generate verification code** to issue a new code before the device can be activated.

## Delete a device

1. In the list, select one or more devices.
2. Select **Delete**.
3. Confirm the deletion.

Caution

Deleting a device removes it from the provisioning list. This action can't be undone.

## Activate the device on-site

After you share a verification code, the on-site technician or user enters it during the device's initial setup. When the code is accepted, the device completes activation and automatically moves to the **Ready for provisioning** status. It's then signed out and ready for a user to be signed in.

## Sign in a user remotely

After a device shows **Ready for provisioning**, you can sign in a device account remotely — no physical access required.

1. Select a device that's **Ready for provisioning** (signed out).
2. Select **Sign in a user**.
3. Confirm the selected device and the most recent signed-in user, then follow the on-screen steps to complete sign-in.

Setup can take several minutes. You can continue working while it completes.

Important

Remote sign-in requires a **device account created in Microsoft Entra ID** — personal user credentials aren't supported. When no personal user is signed in, the device is signed in as a shared device.

Remote sign-in constraints:

| Constraint | Detail |
| --- | --- |
| Personal credentials | Not supported for remote sign-in |
| Account type | A device account created in Microsoft Entra ID |
| Shared devices | Used when a personal user isn't signed in |
| Bulk remote sign-in | Not supported — sign in each device individually |

## View device details

Select any device to open its details pane, which shows read-only properties:

- **ID** and **ID type**
- **Provisioning Status**
- **Connected** / **Disconnected** — the device's current connection status
- **Location**
- **Verification code** and its expiry time
- **Generated by** — the admin who generated the current code
- **Hub Endpoint** — shown for Hardware ID (analog) devices

You can also select **Generate verification code** directly from the details pane.

## Verification code lifecycle

| From state | Trigger | To state |
| --- | --- | --- |
| No code | Select **Generate verification code** | Code active |
| Code active | Device enters the code on the hardware | Activated (**Ready for provisioning**) |
| Code active | Validity period expires | Expired |
| Expired | Regenerate the code | Code active (new code) |
| Code active or Expired | Edit the MAC address or Hardware ID | No code (invalidated) |

## Troubleshoot common issues

| Scenario | What happens |
| --- | --- |
| You add a duplicate MAC address | The entry is rejected with an inline error: "This MAC address already exists." |
| The MAC address format is invalid | The entry is rejected: "Enter a valid MAC address in the format XX-XX-XX-XX-XX-XX." |
| A CSV upload contains invalid rows | Valid rows are imported; invalid rows are listed in an error summary with row numbers |
| The verification code expires before activation | Generate a new code — the device can't activate with an expired code |
| You edit a device's MAC address or Hardware ID | The existing code is invalidated; generate a new one |
| The device is offline during remote sign-in | Sign-in waits until the device is back online |
| You don't have permission to provision | You see an access-denied message; contact your administrator |

## Known limitations

- **Bulk remote sign-in** isn't supported. Sign in each device individually.