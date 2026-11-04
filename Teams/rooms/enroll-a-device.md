---
layout: Conceptual
title: Enroll a Teams Rooms device into the Pro Management Portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/enroll-a-device
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: altsou
ms.date: 2026-03-11T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Onboarding Teams Rooms devices to the Pro Management Portal
f1keywords: 
locale: en-us
document_id: 926bcf08-5326-ed74-8170-14b46fd5ade7
document_version_independent_id: 926bcf08-5326-ed74-8170-14b46fd5ade7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/enroll-a-device.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/enroll-a-device
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/enroll-a-device.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 97127483-2a29-c7be-51ed-3f33515566be
---

# Enroll a Teams Rooms device into the Pro Management Portal - Microsoft Teams | Microsoft Learn

This article explains how to enroll Teams Rooms devices to the Pro Management Portal. The Pro Management Portal supports Teams Rooms on Windows, Teams Rooms on Android, and Teams panel devices.

For Teams Rooms on Windows devices, the Teams Rooms Pro Management agent is automatically downloaded and installed at device setup. For Teams Rooms on Android devices or Teams panels, the admin agent included on the device automatically connects to the Pro Management Portal. Devices once signed into Teams automatically enrolls and appears in the Teams Rooms Pro Management Portal.

## Prerequisites

Follow these procedures to set up your environment or device prior to attempting to connect a device to the Pro Management Portal.

### Network security

Ensure the required URLs listed in [Teams Devices - Network Security](/en-us/microsoftteams/rooms/security?tabs=Windows) are allowed on your network for both Teams Rooms on Windows and Teams Android devices.

### If necessary, configure proxy settings on the device

Review proxy requirements and configuration steps for your Teams Rooms devices in [Prepare your environment for Teams devices](rooms-prep#proxy-for-teams-rooms-on-windows).

Important

Teams Rooms devices automatically include the Pro Management Portal agent and don't require manual installation. These steps are here for troubleshooting purposes only.

## Manual Teams Rooms on Windows enrollment process

The enrollment process involves these steps:

1. On the left navigation bar of the Microsoft Teams Rooms Pro Management portal [Commercial & GCC: http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/) or [GCC-High: https://devices.dod.teams.microsoft.us](https://devices.gov.teams.microsoft.us), expand **Settings** and select **General**.
2. Under *Enroll a room*, select **Download installer** to download the monitoring agent software.
3. Install the agent using the installer downloaded in step 2. This can be done either by running the MSI locally or via Intune.
4. The room appears in the portal within 5-10 minutes.

    ![Screenshot of settings and self-enrollment keys.](../media/software-installation-005new.png)

### Agent Installation

After downloading the installer, unzip its contents to access the file **ManagedRoomsInstaller.msi**.

There are two modes of installation: 1) individual local machine install and 2) mass deploy mode (usually via Intune). We recommend individual install for nondomain joined machines or for machines that you have no way of running MSI installers remotely.

#### Individual device installation

1. Log in to the device as administrator. Ensure the *Performing operations as the Admin user of the device* steps are followed.
2. Copy the file **ManagedRoomsInstaller.msi** to the Teams Rooms on Windows device.

    On running the ***ManagedRoomsInstaller.msi*** is a License Agreement screen.
3. After reading the agreement, check ***I accept the terms in the License Agreement*** and press **Install**.

    This begins the Microsoft Teams Rooms Pro monitoring software install. A prompt for elevation (run as administrator) is displayed.
4. Select **Yes**.

    The installation continues. During the installation procedure, a console window opens and begins the final stage of the Microsoft Teams Rooms Pro monitoring software installation.

    Note

    Don't close the window. Once the installation is complete, the wizard displays a "Finish" button.

#### Intune-enrolled device bulk deployment

The following components are prerequisites for successful installation:

- **Intune enrollment**: Teams Rooms on Windows devices must be already enrolled in Intune. For more information about how to enroll Teams Rooms on Windows devices in Intune, see [Enrolling Microsoft Teams Rooms on Windows devices with Microsoft Endpoint Manager - Microsoft Tech Community.](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Microsoft Entra group with all Teams Rooms on Windows devices as members** – a group created in Microsoft Entra ID that includes all Teams Rooms on Windows devices that should be part of the Microsoft Teams Rooms Premium service. This group is used for targeting the deployment of the Pro agent.

Note

You may consider using Dynamic groups in Microsoft Entra ID for this purpose, more information at [Enrolling Microsoft Teams Rooms on Windows devices with Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)

**To install using Intune**

1. Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Apps** &gt; **All apps** &gt; **Add**.
3. In the **Select app type** pane, under **Other** app types, select **Line-of-business app**.
4. Click **Select**. The **Add app** steps are displayed.
5. In the **Add app** pane, click **Select app package file**.

    1. In the **App package file** pane, select **Browse**. Then, select the **ManagedRoomsInstaller.msi** file downloaded previously (refer to the prerequisites section).
    2. When you're finished, select **OK** on the **App package file** pane to add the app.
6. In the **App information** page, perform the following changes:

    1. Publisher: enter **Microsoft Corporation**.
    2. Ignore app version: select **Yes**.

        Note

        The Pro agent is self updating; hence, you should explicitly ignore the app version (any baseline version can update automatically).
    3. (Optional) Category: Select **Computer Management**.
7. Click **Next** to display the **Assignments** page.

    1. Under the **Required** section, click **+ add group** to target a group of devices for installation of the agent.
    2. In the **Select group** pane, type the group name in the Search box (refer to prerequisites above) and click on the desired **group** and click **Select**. For more information, see [Add groups to organize users and devices](https://go.microsoft.com/fwlink/?linkid=2202166) and [Assign apps to groups with Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
8. Click **Next** to display the **Review + create** page.
9. Review the values and settings you entered for the app. When you're done, click **Create** to add the app to Intune.

Once the process is completed, your devices will start installing the Pro agent after a few minutes.

Note

Following installation, the Teams Rooms Pro management agent may take up to eight hours to execute a self-update to the latest version and become listed in the Teams Rooms Pro management portal. To expedite the automatic enrollment in the Teams Rooms Pro management portal, consider restarting the Teams Rooms device following the agent deployment.

## Troubleshooting table

Note

All Microsoft Teams Rooms Pro monitoring errors are logged on a specific Event Log file named **Microsoft Managed Rooms**.

***Application runtime log file location*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, where **x.x.x** is the app version number.

| Symptom | Recommended Procedure |
| --- | --- |
| You receive an error message stating: <br>***ERROR: Please run this application with*** ***elevated privileges*** | Run the application with escalated privileges and try again. |
|  |  |
| You receive an error message stating: <br>***TPM data cannot be found*** | Ensure that your device has TPM (Trusted Platform Module) turned on in its BIOS. This is found in the security settings of the device BIOS. |
|  |  |
| You receive an error message: <br>***ERROR: Local user account named 'Admin' or 'Skype' not found*** | Ensure that the user accounts exist on the certified Microsoft Teams Rooms systems device. |
|  |  |
| You receive any error state messages that aren't covered here. | Provide a copy of your installation log to your Microsoft Teams System support agent. |