---
layout: Conceptual
title: Use Windows Autopilot and Autologin to easily deploy Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/autopilot-autologin
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: mattslomka
ms.date: 2026-11-06T00:00:00.0000000Z
ms.topic: install-set-up-deploy
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: itpro-rooms
audience: Admin
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to set up and use the Windows Autopilot and Autologin features to deploy and provisioning Microsoft Teams Rooms on Windows devices in your organization.
locale: en-us
document_id: ad7e2686-992e-5994-6bcf-4d74adba85b8
document_version_independent_id: ad7e2686-992e-5994-6bcf-4d74adba85b8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/autopilot-autologin.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/autopilot-autologin
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/autopilot-autologin.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/4b132a0c-342a-42eb-91ff-8159e1ed413d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f2b71146-ce8e-46a8-9965-8aa8b3aa8235
platformId: 459bfe3c-0682-6b8d-62f7-88650cb189a8
---

# Use Windows Autopilot and Autologin to easily deploy Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

You can use Windows Autopilot and Autologin to deploy, provision, reset, redeploy, and recover Microsoft Teams Rooms on Windows in your organization.

Windows Autopilot with Autologin for Teams Rooms simplifies and accelerates the on-site deployment time for Teams Rooms running Windows. The combination of these technologies removes the need for direct interaction with the Teams Rooms device during provisioning and deployment. Windows Autopilot and Autologin ensures no one must physically interact with the Teams Rooms device to deploy it.

Instead, the Teams Rooms device completes the Windows and Teams app installation automatically out-of-box. Once installation is complete, it then signs in to the Teams Rooms app without the need for someone to have physical access to the device. The combinations of these features greatly simplify the Teams Rooms lifecycle, from its initial deployment to its end of life.

## Overview of steps

To use Windows Autopilot and Autologin to provision and deploy Microsoft Teams Rooms devices in your organization, you must perform these tasks:

- Step 1: Verify that all prerequisites are met
- Step 2: Register devices as Windows Autopilot devices
- Step 3: Create a device group
- Step 4: Deploy Teams Rooms app update tool
- Step 5: Create an Enrollment Status Page (ESP) profile
- Step 6: Create and assign a Windows Autopilot profile
- Step 7: Create and assign a Local Administrator Password Solution policy
- Step 8: Set up Autologin in the Pro Management Portal
- Step 9: Deploy the device

## Step 1: Prerequisites

To successfully deploy Microsoft Teams Rooms devices, verify that these prerequisites are met.

1. You must buy enough Teams Rooms Pro licenses for each of the devices you're provisioning and deploying. Teams Rooms Pro licenses include the correct Intune and Microsoft Entra ID P1 licenses. To see more information on the licensing requirements for Windows Autopilot, see [Windows Autopilot licensing requirements](/en-us/autopilot/requirements?tabs=licensing#licensing-requirements).
2. You must verify the account you're using to deploy the devices has the correct permissions.

    1. For Intune, verify that the account has the Intune Administrator or Policy and Profile Manager permissions, see [Learn more](/en-us/autopilot/add-devices#required-permissions).
    2. For the Teams Management Pro portal, the account has the Teams Rooms Pro Manager permissions.
3. You must [Set up Windows automatic Intune enrollment](/en-us/autopilot/tutorial/self-deploying/self-deploying-automatic-enrollment#set-up-windows-automatic-intune-enrollment).
4. You must join Microsoft Entra devices. Windows Autopilot self-deploying mode isn't supported for Microsoft Entra hybrid join devices.
5. You must create and set up the required resource accounts. See, [Create a resource account](/en-us/microsoftteams/rooms/create-resource-account).
6. You must be only deploying Microsoft Teams Rooms on Windows devices with Windows 11 installed. See, [Teams Rooms Windows support](/en-us/microsoftteams/rooms/rooms-lifecycle-support).

## Step 2: Registering Teams Rooms devices using Windows Autopilot

To use the Autopilot deployment process, Teams Rooms devices must be registered in Intune as Autopilot devices.

Registration can be completed in three ways:

1. [OEMs can automatically load the hardware identity](/en-us/autopilot/oem-registration)
2. [Cloud Solution Providers (CSPs) can use Partner Center to load the hardware identity](/en-us/microsoftteams/rooms/autopilot-registration4partners)
3. [Customers can load the hardware identity in Intune](/en-us/autopilot/manual-registration)

When loading the hardware identity, it's required to set the GroupTag prefixed with **MTR-**. You can easily do this by adding the GroupTag to the .csv file described [here](/en-us/autopilot/add-devices#ensure-that-the-csv-file-meets-requirements) or entering the prefix in the **Group name** field when adding identities using the Microsoft Partner Center. This GroupTag field is critical for the Teams Pro Management portal so it can tell the difference between the Teams Rooms devices and other devices that are registered with Windows Autopilot. The GroupTag field is also useful when you're using dynamic device groups.

Important

If a device is returned to the manufacturer or swapped to another tenant, disassociate the device by [deleting it as an Autopilot device](/en-us/autopilot/add-devices#delete-windows-autopilot-devices).

## Step 3: Create a group for the Teams Rooms devices

To create a Teams Rooms on Windows device group, see [Create a device group](/en-us/autopilot/tutorial/self-deploying/self-deploying-device-group).

To create a dynamic device group that includes all of the Teams Rooms devices to use Windows Autopilot, use the following query filtering by Group Tag / Order ID:

```odata
(device.devicePhysicalIds -any _ -startswith"[OrderID]:MTR-")
```

Tip

If you use Intune to manage other Windows devices besides Teams Rooms, we recommend opening each configuration and compliance policy and adding this newly created device group as an exclusion for any policy assignments. This will ensure Teams Rooms devices only receive desired policy assignments.

## Step 4: Deploy Teams Rooms app update tool

Note

As of November 2026, the app update tool is no longer a recommended step in the deployment process for Autopilot + Autologin. The Teams Rooms app has had the automatic update functionality included since April 2024 with version [5.0.111.0](/en-us/MicrosoftTeams/rooms/rooms-release-note?tabs=Windows#501110-4242024), all new devices being deployed should have the feature included out of box.

If you have the app update tool still included in your Intune configuration it's recommended that you unassign it unless you're deploying devices older than 2025.

The Teams Rooms app update tool updates the Teams room app running on the device to a version that supports Windows Autopilot and Autologin. The update tool needs to be first downloaded, then uploaded to Intune, and deployed to the Teams Rooms on Windows devices. Although it's not required, use dynamic device groups. During the Windows Autopilot Enrollment Status Page (ESP), Intune installs the update tool to the Teams Rooms device and updates the Teams room app before it starts.

Going through these steps enables Intune to push the update tool to the Teams Rooms enrolling through Windows Autopilot. The update tool then automatically updates the Teams app on the device so it can automatically log in.

Note

The update tool Win32 package automatically downloads the latest Teams Rooms application when it runs, it isn't necessary to replace the update tool each time a new Teams Rooms app version is released. At times a new version of the Win32 package update tool may be released to resolve bugs or add new features, at such time, you can delete the existing app from Intune and redeploy a newer build of the update tool. The app will only run once on each Teams Rooms device.

To deploy the Teams Rooms app update tool to your devices:

1. To download the update tool Win32 package, see [here](https://aka.ms/mtrp/autopilot-tool).
2. In the Microsoft Intune Admin center, navigate to **Apps** and under **By platform** select **Windows**.
3. Select **Add**. In the **Select app type** detail pane, select **Windows app (Win32)** in the drop-down menu.
4. Browse to select the update tool app package file downloaded in Step 1.
5. On this page, most fields are automatically populated. To see the update tool in the list, put in **Microsoft** as the publisher, then select **Next**.
6. Under **Program**, change **Device Restart Behavior** field to **Intune will force a mandatory device restart**. Select **Next**.
7. Under **Requirements** set the following:

    1. Under **Operating system architecture**, select **32-bit** and **64-bit**.
    2. Under **Minimum operating system**, select **Windows 10 21H2**.
8. Under **Detection rules**, set:

    1. **Rules format: Manually configure detection rules**, select **Add**.
    2. In the **Detection rule** detail pane, select **MSI** in the **Rule type**. The **MSI product code** should fill in automatically.
    3. Select **No** for **MSI product version check**.
    4. Select **OK**.
    5. Select **Next**.
9. Under **Dependencies**, select **Next**.
10. Under **Supersedence**, select **Next**.
11. Under **Assignments**, select **Add group**.
12. Under the **Required** section, in the **Select groups** detail pane, choose the group created for the Microsoft Teams Rooms devices being deployed with Windows Autopilot. Select **Next**.
13. On the **Review + create** page, review your settings. If everything is set correctly, select **Create**.

For more information on Win32 app deployment in Intune, see [Add and assign Win32 apps to Microsoft Intune](/en-us/mem/intune/apps/apps-win32-add#add-a-win32-app-to-intune).

## Step 5: Create a Windows Autopilot Enrollment Status Page (ESP) profile

To create an enrollment status page profile for your Teams Rooms on Windows devices, see [Configure and assign the Enrollment Status Page (ESP)](/en-us/autopilot/tutorial/self-deploying/self-deploying-esp).

The required settings for ESP on Teams Rooms are:

| Setting | Option |
| --- | --- |
| Show app and profile configuration progress | Yes |
| Block device use until all apps and profiles are installed | Yes |
| Turn on log collection and diagnostics page for end users | Yes |
| Only show page to devices provisioned by out-of-box experience (OOBE) | Yes |
| Allow users to reset device if installation error occurs | Yes |
| Allow users to use device if installation error occurs | No |
| Block device use until required apps are installed if they're assigned to the user/device | Selected |

Under **Blocking apps**, select the Microsoft Teams Rooms Pro Provisioning (MTRP) tool. Set **Only fail selected blocking apps in technician phase** to **Yes**.

Then assign the ESP to the device group you created in Step 3.

## Step 6: Create a Windows Autopilot profile

For the Teams Rooms devices, you must create a Self-deploying Windows Autopilot profile. See [Create and assign self-deploying Windows Autopilot profile](/en-us/autopilot/tutorial/self-deploying/self-deploying-autopilot-profile#create-and-assign-self-deploying-windows-autopilot-profile).

Then assign the Windows Autopilot profile to the previously created device group in Step 3.

## Step 7: Create and assign a Local Administrator Password Solution (LAPS) policy

For the Teams Rooms devices, we recommend that you create and assign a LAPS policy as a best security practice.

To set up and configure a LAPS policy, see [LAPS authentication on Teams Rooms with Windows](/en-us/microsoftteams/rooms/laps-authentication#laps-deployment).

## Step 8: Set up Autologin in the Teams Rooms Pro Management portal

After the Endpoint Manager portal configuration is complete, you must assign the resource accounts for the devices listed as Windows Autopilot devices that let the Teams Rooms devices automatically log in when they're deployed.

1. Go to the Microsoft Teams Rooms Pro Management portal and sign in.
2. In the left navigation of the Microsoft Teams Rooms Pro Management portal, go to **Planning &gt; Autopilot devices**.
3. On the **Windows Autopilot devices** page, select **Sync** to populate the device list.

To assign an account to a Windows Autopilot device, the device must have a Windows Autopilot profile assigned. You can see the devices in the **Profile assignment status** column and they should be listed as **Assigned**.

1. Select a device from the list.
2. Select **Assign account**.
3. On the **Device selection** page, the device is preselected. Select **Next**.
4. On the **Account selection** page, select the account you want to use on this device, then select **Next**.

    Tip

    If a recently created resource account isn't listed in the account selection page, perform an inventory sync to import newly created accounts: [Click Here](/en-us/MicrosoftTeams/rooms/inventory#refresh-your-inventory-on-demand)
5. On the **Configuration** page, select one of the password options:

    - **Automatically generate password for selected account** - A new unique password will be generated for the selected resource account(s), the account will be assigned this new password in Entra ID, and Autologin will be configured to deliver that new password.
    - **Use existing password for selected account** - Enter the existing functional password for the resource account(s) and Autologin will be configured to deliver the existing password.

        Note

        Generate password requires administrative permissions to reset a user account password, User Administrator, or Exchange Administrator are Microsoft 365 privileged roles which can work, but other admin roles can provide permission as well.
6. On the **Review** page, select **Finish** to link the resource account to Windows Autopilot device.

When the device is ready to be provisioned, the **Provisioning status** shows as **Ready**. This link and association is valid for up to 90 days.

### Autologin if you're resetting a Teams Room

When resetting a Teams Rooms for Windows Autopilot and Autologin, verify there's a resource account assigned to the Windows Autopilot device with the **Provisioning status** showing as **Ready**. If the status is **Consumed**, you must reassign the resource account to the Windows Autopilot device for the device you're resetting.

## Step 9: Deploy the Teams Rooms device

Once all the configuration steps for Windows Autopilot self-deploying deployment and Autologin are completed, the next step is to start the deployment process.

To start the Windows Autopilot deployment process on the device that is Windows Autopilot registered and has a resource account assigned.

1. If a wired network connection is available, connect the device to the wired network connection.
2. Turn on the device.
3. Once the device boots up, one of two things occurs depending on the state of network connectivity:

    Important

    Connectivity to the Internet is required.

    - If the device is connected to a wired network, the device may reboot to apply critical security updates if they're available. After the reboot to apply critical security updates, the Windows Autopilot process begins.
    - If the device isn't connected to a wired network or if it doesn't have network connectivity, it prompts you to connect to a network.

    1. The OOBE (Out of Box Experience) begins and a screen asking for a country/region appears. Select the appropriate country or region, and then select **Yes**.
    2. The keyboard screen appears to select a keyboard layout. Select the appropriate keyboard layout, and then select **Yes**. If needed, you can select additional keyboard layouts by selecting **Add layout**, or select **Skip** if you don't want to add additional keyboard layouts.

        Note

        When there's no network connectivity, the device can't download the Windows Autopilot profile to identify the country/region and keyboard settings to use. This is why when there's no network connectivity, the country/region and keyboard screens appear and must be set to hidden in the Windows Autopilot profile. These settings need to be set for the network connectivity screens to work properly.
    3. The **Let's connect you to a network** screen appears. At this screen, either plug the device into a wired network (if available), or select and connect to a wireless Wi-Fi network.
    4. Once network connectivity is established, the **Next** button is available. Select **Next**.
    5. The device may reboot to apply critical security updates if they're available. After the reboot to apply critical security updates, the Windows Autopilot process begins.
4. The Enrollment Status Page (ESP) displays progress during the provisioning process in two phases:

    - **Device preparation** (Device ESP)
    - **Device setup** (Device ESP)

    The first two phases of **Device preparation** and **Device setup** are part of the Device ESP. The second phase of **Account setup** is part of the User ESP. For Windows Autopilot self-deploying mode, only the Device ESP and these two related phases (**Device preparation** and **Device setup**) run.

    Note

    User ESP and **Account setup** aren't recommended for Teams Rooms deployments.
5. During **Device setup** the Teams Rooms app update tool runs and updates the Teams app. When the device ESP process completes, the Windows Autopilot self-deploying deployment is complete, and the Teams Rooms Out-of-box experience starts.
6. The Teams Rooms app now detects the Windows Autopilot profile and initiates Autologin. The credentials for the resource account assigned to this Windows Autopilot device are used. When this part is complete, the device will automatically log in and is ready for Teams meetings.

## Frequently asked questions

**Question:** How can Intune be used to reset or redeploy a Teams Rooms on Windows device which has gone through Autopilot and Autologin?

**Answer:** First you must run the Teams Rooms [Recovery Tool](/en-us/microsoftteams/rooms/recovery-tool#running-the-tool) to prepare the Windows operating system for recovery with the Teams Rooms components included (If the recovery tool is not used you may reset the device to a non-Teams Rooms state). Then within Intune, select the device to reset, then select **Wipe**, and then select **Wipe** again. Once Windows resets, the Teams Rooms application will re-deploy through Autopilot and Autologin again.

**Question:** Why aren't my Windows Autopilot devices syncing into the Teams Rooms Pro Management portal?

**Answer:** In the Teams Pro Management portal on the Windows Autopilot device page, select **Sync** to initiate an update to the device list. Check the "Last synced" time on the page to see if it corresponds to the time the last sync was initiated. If devices are still not syncing, check that the GroupTag is configured correctly with the prefix **MTR-DeviceName**.

**Question:** Why does the device not automatically login after resetting the device?

**Answer:** If the device hasn't completed Windows Autopilot provisioning before, a Windows reset is required. It's recommended to reset to a factory image. A simple reset initiated through the Teams app won't reset Windows.

If the device successfully completed Windows Autopilot provisioning and the Teams app fails to log in, check the respective device in the Pro Management portal and verify the **provisioning status** shows as **Ready**.