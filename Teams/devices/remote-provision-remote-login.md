---
layout: Conceptual
title: Remote provisioning and sign in for Teams Android devices - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/remote-provision-remote-login
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: vapati
ms.date: 2026-08-17T00:00:00.0000000Z
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
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to remote provisioning and sign in for Teams Android devices
locale: en-us
document_id: 344ac314-e98e-ab21-ef47-fb0da80ec884
document_version_independent_id: 8f3d2fe8-5d96-4298-f875-fb3e64688afc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/remote-provision-remote-login.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/remote-provision-remote-login
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/remote-provision-remote-login.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e943e8ce-bd5d-2270-ded3-d5c2ee17bb03
---

# Remote provisioning and sign in for Teams Android devices - Microsoft Teams | Microsoft Learn

IT admins can remotely provision and sign in to a Teams Android device. To provision a device remotely an IT admin will: upload the MAC address or hardware ID of the device(s) being provisioned, create a verification code, enter that code into the Android device locally, and then the remote sign-in code appears within the Pro Management Portal. This allows the sign-in to be completed remotely and at a different time than the device is being physically installed to support IT administrators in different time zones.

Note

Once you've signed in to a Teams Android device once, this feature behaves slightly differently as outlined at the end of this article.

## Supported devices

All Teams Rooms on Android, Teams panel, Teams phone, and SIP gateway devices can be provisioned remotely from the Teams Pro Management Portal.

## Step 1: Add a device identifier for remote provisioning

To begin the device attestation process, the ethernet MAC address for the device must be uploaded into the Pro Management Portal.

### Add a single device

1. Sign in to the [Teams Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service)
2. Expand **Planning**
3. Select **Android Devices**
4. Select **Add**
5. Adjust the **ID type** if required
6. Enter the MAC address or hardware ID
7. Optionally, enter a location of the device to be used as an internal reference later
8. Select **Save**

### Bulk upload devices

1. Sign in to the [Teams Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service)
2. Expand **Planning**
3. Select **Android Devices**
4. Select **Upload**
5. Download the template
6. Complete the template with the relevant details for your devices (ID, ID Type (macAddress or hardwareId), and Location)
7. Come back to the Pro Management Portal and select the **Select file** button and choose your file
8. Select **Upload**

Once the details are uploaded (either manually or in bulk), review the list of devices showing as **Ready for provisioning** to ensure the devices are there and ready.

## Step 2: Generate a verification code

You need a verification code for the devices. The verification code is generated in bulk or at the device level and is valid for 24 hours.

1. From the devices listed as **Ready for provisioning**, select an single device or check multiple devices
2. Select **Generate verification code**
3. Select the individual device to view the verification code or select multiple and select **Export** to export multiple verification codes at once
4. Provide the list of IDs and verification codes to the field technicians

## Step 3: Connect the device to your Teams environment with the provisioning code

When the device is powered on and connected to the network, the technician enters the provisioning code on the device locally.

1. The technician selects **Provision device** from the **Settings**.

    ![Provision new device option from the Actions tab.](../media/provision-device1.png)
2. The technician enters the device-specific verification code in the provided input field.

    ![Provision new device verification.](../media/provision-device-verification1.png)

    Once the device is provisioned successfully, the tenant name appears on the sign-in page.

    ![Tenant name on sign-in page.](../media/provision-code.png)

## Step 4: First time remote sign in

The provisioned device appears in the **Waiting for sign in** tab. Start the remote sign-in process by selecting the individual device.

1. Return to the [Teams Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service)
2. Expand **Planning**
3. Select **Android Devices**
4. View devices in the list which have a status of **Waiting for sign in**
5. Follow the instructions to sign in the device remotely using the code presented at: microsoft.com/devicelogin

## Sign in a device which was previously signed in

For devices already connected to the Pro Management Portal which has been signed out or that you wish to change the account on, you can generate a sign-in code and sign the device back in.

1. Sign in to the [Teams Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service)
2. Select **Rooms**
3. Select the signed-out device you wish to sign back in
4. Select the **Account** tab ![Pro Portal Device Signed Out](media/remote-provision-remote-login/pro-portal-device-signed-out.png)
5. Select **Generate code**
6. On the prompt which appears, follow the sign-in steps ![Pro Portal Device Code](media/remote-provision-remote-login/pro-portal-device-code.png)
7. After a few minutes, refresh the page and the account tab should show the user principal name of the account signed in

## Sign out a device which is currently signed in

For devices already connected to the Pro Management Portal, you can sign out that device remotely.

1. Sign in to the [Teams Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service)
2. Select **Rooms**
3. Select the device you wish to sign out
4. Select the **Account** tab
5. Select **Sign out**
6. Select **Sign out** on the confirmation prompt

![Pro Portal Device Signed In](media/remote-provision-remote-login/pro-portal-device-signed-in.png)