---
layout: Conceptual
title: Configure line keys from Teams Admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/configuring-line-keys-tac
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Article describing how to configure line keys from TAC
author: pbadkur1
ms.author: prashibadkur
manager: serdars
ms.service: msteams
ms.topic: article
ms.date: 2025-07-24T00:00:00.0000000Z
ms.subservice: itpro-devices
locale: en-us
document_id: 4429716d-6078-7302-712c-ba88382e70ee
document_version_independent_id: 4429716d-6078-7302-712c-ba88382e70ee
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/configuring-line-keys-tac.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/configuring-line-keys-tac
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/configuring-line-keys-tac.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a3a7a060-293c-b39d-af3b-63b0ed7c1e71
---

# Configure line keys from Teams Admin center - Microsoft Teams | Microsoft Learn

This article provides a comprehensive guide for IT administrators to configure line keys on Microsoft Teams-certified phone devices using the Teams Admin Center (TAC).

Line keys allow users to quickly access contacts or perform call-related actions. Admins can centrally configure these keys via TAC for both Common Area Phones (CAP) and personal Teams phones. The configuration experience is tailored to device types and user roles, ensuring flexibility and control. The configuration is available for both common area phones, with a Teams Shared Device License and personal phones, with a Teams Phone License, for more information, see [How to Deploy Teams Phone Devices](https://techcommunity.microsoft.com/blog/microsoftteamsblog/how-to-deploy-teams-phone-devices/3994979).

### App version requirements

- Teams Phone App: 1449/1.0.94.2025443703 or later

### Steps to configure

Step 1: Update the phone device and check for default settings

1. Navigate to **Settings &gt; Calling &gt; Line Keys Settings** on the device.
2. For common area phones, verify if **Allow admin override** and **Hide unassigned line keys** are enabled and ON by default.
3. For personal phones, verify if **Allow admin override** is enabled and ON by default.

Warning

For Line keys to be assigned or configured via Teams Admin Center (TAC), the Allow admin override must be enabled.

Step 2: On TAC, create a configuration profile

1. Sign in to https://admin.teams.microsoft.com/.
2. Go to **Teams Devices &gt; Phones &gt; Configuration Profile &gt; Add Profile**.
3. Scroll to the **Line Keys** section.
4. Toggle **Configure line keys** to ON.
5. You can choose to follow either of the following options to configure line keys now:

    1. If you enable Device Profile Template, use the **Phones tab** to configure line keys on touch and non-touch devices and **Sidecar tab** for connected sidecar devices. Complete the remaining steps to configure line keys:

        1. Using the drop-down choose the device or sidecar model you wish to configure line keys for.
        2. Assign line keys for each position. If the model chosen is a touch device, contact (directory contact or a PSTN number), shared line, and call queues are available to be assigned. If the model chosen is a nontouch device, only contact (directory contact or a PSTN number) are available to be assigned. For sidecars connected to touch devices, contact (directory contact or a PSTN number), shared line, and call queues are available to be assigned.

        Note

        Assigning a contact to a line key does not save it as a speed dial in the user contact directory; pressing the line key will start an outgoing call. Similarly, if you assign a PSTN number with a label to a line key, it will not appear as a contact in the user directory. Pressing this line key will also initiate an outgoing call.

        iii. Once you choose a category—Contact, Speed Dial, or Call Queue—search the directory to select the desired entry.

        Note

        Line key configuration for a shared line is only applicable to phone devices signed in with boss or delegate accounts associated with that specific shared line. Similarly, line key configuration for a call queue can only be applied to devices signed in with accounts possessing the required permissions for the call queue.
    2. If you don't enable Device Profile Template, simply assign line keys for positions you wish to use.
6. **Review** and **Save** the configuration profile.
7. **Apply** the configuration profile to selected devices.

#### Experience

After the configuration profile is applied to the chosen devices, assigned and configured line keys should appear on the device.

![Screenshot of line keys on a touch device.](media/configuring-line-keys-tac/image.png)

*Line Keys screen with Wanda Howard and added line key notification on touch devices*

![Screenshot of line keys on a non-touch device.](media/configuring-line-keys-tac/image1.png)

*Line Keys screen with Wanda Howard and added line key notification on nontouch devices*

![Screenshot of line keys on a sidecar connected device.](media/configuring-line-keys-tac/image2.png)

*Line Keys screen with Wanda Howard and added line key notification on sidecar connected devices*

#### Frequently Asked Questions

1. **What is the purpose of configuring line keys via TAC?**

    TAC allows IT admins to centrally manage line key assignments on Teams-certified phone devices. This includes assigning speed dials, shared lines, and call queues, improving consistency, scalability, and user experience across personal and common area phones.
2. **Which devices support line key configuration through TAC?**

    Line key configuration is supported on:

    - Touch and non-touch Teams phone devices
    - Sidecars
3. **Can users override admin-configured line keys?**

    Yes, if the **Allow admin override** toggle is OFF, users can configure line keys directly on the device. If ON, admin configurations take precedence. Admins can choose to allow or restrict user overrides in the configuration profile.