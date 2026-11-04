---
layout: Conceptual
title: Manage line keys for speed dial on Teams phones - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/line-keys
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: prashibadkur
ms.date: 2024-11-04T00:00:00.0000000Z
ms.topic: how-to
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
description: Learn how to set up and manage line or speed dial keys on Microsoft Teams certified phones for quick access to custom contacts and speed dial.
locale: en-us
document_id: 9af9991d-7546-5404-25e9-00f91b25d2fc
document_version_independent_id: 9af9991d-7546-5404-25e9-00f91b25d2fc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/line-keys.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/line-keys
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/line-keys.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 538acccf-23a7-b433-140d-b527c17481e3
---

# Manage line keys for speed dial on Teams phones - Microsoft Teams | Microsoft Learn

This article provides you with guidance on setting up and managing line keys on Microsoft Teams certified phones. This feature allows your users to use a phone line key to set up line keys for quick access using buttons on touch, nontouch, and sidecar devices. These keys allow users to quickly access key calling features such as speed dial, shared lines, call queues, and collaborative delegation.

## Supported Devices

Line keys are supported on:

- Nontouch Teams Phones
- Touch Teams Phones (via the Line Keys app on the home screen)
- Teams Phones with sidecars (for extended key capacity)

## Software Requirements

To use line keys, devices must be running the following minimum Teams versions: 

- Nontouch devices: 1449/1.0.94.2024101709 or later
- Touch devices: 1449/1.0.94.2025084203 or later
- Sidecar support: 1449/1.0.94.2025165302 or later

To set up a line key for speed dial, follow these steps:

## Update to required Teams app

After updating the phone, you notice a new home screen experience on your device with a dedicated place for your line keys. To update your Teams phones, see [Update your phones remotely](remote-update-teams-phones). Verify that you're running the minimum Teams versions.

1. You can see the versioning information in the Teams admin center or on the Teams phone.

    To see it in the Teams admin center:
2. Sign in to the Teams admin center.
3. Go to **Teams devices** &gt; **Phones** &gt; then select the phone you want to look at.
4. Then in the table under **Software type** look for **Teams** and in the **Current version** column you can see the version.

    To see the versioning information on the Teams phone itself: Go to the **Profile** icon &gt; **Settings** &gt; **About**.

## Assignment of line keys

When you first start to assign line keys, you see available and unassigned line keys:

![An image showing unassigned line keys. The image shows six boxes with a plus sign to the left of the words Assign line key.](media/line-keys/l2-first-time.png)

Note

Line key assignment UI might differ on touch, nontouch, and sidecar devices.

1. Steps to assign line keys:

    1. Find an available line key on your device.
    2. Select Assign line key.
    3. Choose the type of assignment (for example, contact, shared line, call queue).
2. The following options are supported for assignment:

    1. Speed dial: Assign a frequently contacted person or external phone number.
    2. Shared line: Assign a shared line to monitor and pick up calls on behalf of another user.
    3. Collaborative call delegation: Assign a boss or delegate group to manage calls collaboratively.
    4. Call queue: Assign a call queue to monitor its status and pick up incoming calls.
    5. Call transfer: Assign a contact to enable one-touch transfer of active calls.

Important

Call queue and shared lines assignments on nontouch devices don't work as they're not supported.

## Management of line keys

Users can manage an assigned line key by selecting or long pressing the key. Management options include: 

- Assign: Add a new contact or number
- Unassign: Remove an existing assignment
- Reassign: Change the contact or number
- Manage: View and edit all line key assignments
- Manage ringtone: Set a custom ringtone for the line key

    - To set a ringtone for a line key on a Microsoft Teams phone, do the following:

        1. From the home screen, go to **Line keys**.
        2. Press and hold the line key you want to change.
        3. Select **Manage ringtone**, and then choose a ringtone.

Note

If a line key is assigned to a call queue, the ringtone you select for that line key doesn't apply. Incoming call queue calls continue to ring with the default ringtone.

Unassigned line keys can be hidden via the Calling settings menu.

## Call handling assigned line keys

1. Speed Dial: Assign frequently contacted numbers to line keys for one-touch dialing.
2. Shared Line: Assign a shared line to a line key to: 

    1. View the presence of the boss and delegates.
    2. Pick up calls on behalf of the boss.
    3. Barge into active calls.
3. Collaborative Call Delegation: Assign a group to a line key to: 

    1. View presence of the group members.
    2. Pick up incoming calls on behalf of others.
    3. Join active calls.
4. Call Queues: Assign call queues to line keys to: 

    1. Monitor queue status (for example, available, active call).
    2. Pick up calls directly from the queue.
5. Call Transfers: Assign a contact to a line key to enable one-touch transfer (including blind and consult transfer) of active calls.

## LED conventions of line keys

LED indicators on line keys provide visual cues for call status: 

1. Solid green: Line is available.
2. Blinking red: Line has a call on hold.
3. Solid red: Line is busy or an active call.
4. Blinking green: Line is receiving an active call.

Note

LED support will be introduced by device manufacturers— check with them directly for rollout timelines.

## Frequently Asked Question

**Question:** What other functions can I perform using line keys?

**Answer:** With this update, you can use line keys for quick access to speed dial, assign shared lines, collaborative call delegation, call queues and call transfers. In the future, we'll support line keys for other call controls.

**Question:** Does this change the existing functionality of sidecars?

**Answer:** No, the current functionality of the pinning of speed dial, shared lines, and group contacts doesn't change. However, you can now assign line keys to sidecars in addition to automatic syncing of speed dial, shared lines, and group contacts.

### Related articles

- [Microsoft Certified Teams phones](../devices/teams-phones-certified-hardware)
- [Phones for Microsoft Teams](phones-for-teams)