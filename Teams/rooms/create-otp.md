---
layout: Conceptual
title: Create a one-time password - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/create-otp
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: serdars
ms.reviewer: altsou
audience: ITPro
ms.date: 2024-09-12T00:00:00.0000000Z
ms.topic: quickstart
ms.service: msteams
ms.subservice: itpro-rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: This article is for the IT administrator to learn about how to create a one-time password that will be shared with the system installer personnel.
locale: en-us
document_id: 09d4ad57-30ca-1bea-4577-ef7de4724fd0
document_version_independent_id: 09d4ad57-30ca-1bea-4577-ef7de4724fd0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/create-otp.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/create-otp
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/create-otp.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 83a280c6-34d8-757e-776e-34ac13a42c2e
---

# Create a one-time password - Microsoft Teams | Microsoft Learn

A one-time password (OTP) is used to provide authentication when someone is setting up and deploying Teams Rooms consoles that run on Windows without the need for a specific username and password used on the device. The one-time password is created in the Microsoft Teams Rooms Pro Management portal and only used for a single sign in session. Each Teams Rooms console you're deploying in your organization will need its own one-time password, else, its credentials will need to be added during a manual setup.

When someone is adding Microsoft Teams Rooms consoles to your organization, the one-time password will be used for device authentication instead of a username and password that in the past was required to set up the console.

## How to create a one-time password

To create a one-time password, perform the following steps:

1. Sign in to the Teams Rooms Pro Management portal.
2. On the left navigation pane, select **Planning &gt; Resource Accounts**. The **Resource Accounts** page appears.
3. Select **Generate OTP** wizard on the command bar.

    The **Account selection** page appears.
4. Select the resource accounts for which you want to create a one-time password, and then select **Next**.

    Note

    You must select a resource account for which the value in the **Readiness status** column is **No action needed**. You can also search for specific resource accounts using the search bar. You just have to ensure that whatever is the resource account that you've searched for, that resource account should have the value **No action needed** in its **Readiness status** column.

    The **Configuration** page appears.

    [![Screenshot that shows the Configuration page.](../media/mtr-devices/configuration-screen.png)](../media/mtr-devices/configuration-screen.png#lightbox)
5. Select if you would like to **Automatically generate passwords for all selected accounts** OR **Upload sign in data from CSV file**.

    1. Select the **Automatically generate passwords for all selected accounts** option if you want to reset/delete the existing password for the resource accounts for which you're generating a one-time password.
    2. Select **Upload sign in data from CSV file** if you want to retain the existing password for the resource accounts in which you're generating a one-time password.
6. Select **Next**. The **Review** page appears.

    [![Screenshot that shows the Review page.](../media/mtr-devices/review-screen.png)](../media/mtr-devices/review-screen.png#lightbox)
7. Review the settings you have configured, and then select **Generate**.

    Note

    On the **Review** page, if you want to edit the **Auto generate passwords** setting, select the **Edit** icon next to **Configuration** or if you want to change the resource accounts for which you want to create a one-time password, select the **Edit** icon next to **Account selection**. Then, select **Generate**.
8. Once you've generated the OTP you're presented with the option to download the OTPs with or without the resource account passwords so you can save this information and share it with whomever might be setting up your devices.

## Verify and approve/reject one-time password

You can verify and approve a one-time password that was entered by the setup personnel while trying to sign in their Teams Rooms console into the app.

To verify and approve a one-time password, do the following:

1. Sign in to the Teams Rooms Pro Management portal.
2. On the left navigation pane, select **Planning &gt; Resource Accounts**. The **Resource Accounts** page appears.
3. Select a resource account that has the value **Awaiting OTP Approval**.

    [![Screenshot that shows the page on which you select a resource account that has awaiting one-time password approval as its provisioning status.](../media/mtr-devices/resource-account-provisioning-status.png)](../media/mtr-devices/resource-account-provisioning-status.png#lightbox)

    The page displaying the details of the chosen resource account appears.
4. Select the **OTP** tab. The page displaying the details of the one-time password appears.
5. Verify the details such as:

    - The date when this one-time password was entered on the device, which is displayed in the **Requested date** column.
    - The expiration date, which is displayed in the **Expiration date** column.
    - The device-related information such as make, model, and serial number, which is displayed in the **Device information** pane.
6. Select the **Approve the request** button, if you want to approve the one-time password request.
7. Select the **Reject the request** button, if you want to reject the one-time password request.

    1. Provide the reason for rejecting the one-time password request by choosing a value from the **Reason for rejection** drop-down.

    [![Screenshot that shows the page on which you choose the reason for rejecting the OTP request.](../media/mtr-devices/select-reason-for-rejection.png)](../media/mtr-devices/select-reason-for-rejection.png#lightbox)
8. Select **Submit**.

## Modify the one-time passcode expiration or enable OTP auto approval

By default the OTP is valid for 8 hours, however you can adjust the validity period of the OTP to be up to 2 weeks (336 hours). You can also choose to automatically approve OTPs instead of needing to select the approve button as the IT admin.

To change these settings:

1. Sign in to the Teams Rooms Pro Management portal.
2. In the left navigation pane, select **Planning &gt; Resource Accounts**. The **Resource Accounts** page appears.
3. Select **Preferences** on the command bar.
4. Adjust the OTP expiration by selecting from the predefined hours or set a custom expiration (between 1 hour and 336 hours).
5. You can also toggle **OTP Auto approval** on or off.
6. Select **Save** when you're done to save your changes.