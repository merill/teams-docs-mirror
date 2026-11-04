---
layout: Conceptual
title: Microsoft Teams Rooms maintenance and operations - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-operations
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: kramachandra
ms.date: 2026-08-05T00:00:00.0000000Z
ms.topic: article
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
description: Learn about managing Microsoft Teams Rooms.
locale: en-us
document_id: fd52fe62-457b-c9e1-ad13-a9b1f24c9c38
document_version_independent_id: 6a8c3285-30e1-15a8-6472-f0cfe5b30e20
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-operations.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-operations
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-operations.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 64db5871-15d1-de8c-192e-71458fce814e
---

# Microsoft Teams Rooms maintenance and operations - Microsoft Teams | Microsoft Learn

Microsoft Teams Rooms is Microsoft's conferencing solution designed to transform your meeting room into a rich, collaborative experience. Users enjoy its familiar Microsoft Teams interface and IT administrators appreciate an easily deployed and managed Windows app. Microsoft Teams Rooms is designed to use existing equipment for ease of installation to bring Microsoft Teams into your meeting room. This document provides support for managing and operating Teams Rooms on Windows devices.

## Collecting logs on Microsoft Teams Rooms

To collect logs in the Pro Management Portal, go to **Rooms** and select the display name of the device you want logs for. In the actions panel, select "Log Collection" and select "Run". Once you confirm the desired logs, the logs will be ready for download in the Activity tab after a few minutes.

#### Teams Rooms on Windows

You can also use PowerShell to collect logs locally. You must invoke the log collection script that ships with the Microsoft Teams Rooms app. In [Admin mode](rooms-operations), start an elevated command prompt, and issue the following command:

```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

The logs are output as a ZIP file in c:\rigel.

#### Teams Rooms on Android

OEM tooling or web management portals can typically be used to collected logs locally.

## Audio Processing and Noise Suppression

#### Teams Rooms on Windows

Teams Rooms on Windows utilizes Microsoft developed noise suppression by default combined with microphone manufacturer processing capabilities. When a certified digital signal processor (DSP) is connected to the Teams Rooms on Windows device, Microsoft automatically disables service side automatic echo cancellation (AEC) and relies on the DSP to handle AEC.

#### Teams Rooms on Android

On Teams Rooms on Android devices, audio enhancement capabilities such as noise suppression and other audio treatment are handled by the device manufacturer and the underlying Android-based device firmware. The Microsoft Teams Rooms on Android app does not currently perform Teams-client-based noise suppression processing. Audio-processing behavior and available controls can vary by certified OEM device, firmware, and room system configuration.

## Teams Rooms on Windows Front of Room Display Configuration

### Display Sleep/Wake Behavior

Teams Rooms on Windows devices are configured out of the box to send no video signal after 10 minutes of inactivity, at which time the Windows PC will stop sending video from its video outputs. You need to configure front of room displays in PC mode if available or set displays to automatically sleep/wake on an inactive/active HDMI video signal, consult your display OEM documentation for guidance. If the display doesn't support any of the mentioned functionalities, you may be able to use a display controller to enable the desired behavior over CEC or RS-232 control. We do not certify displays or display controllers due to the abundance of offerings in the market, this list offers a few options for display controls that have worked in the past:

- [Crestron HD-CTL-101](https://www.crestron.com/Products/Catalog/Control-and-Management/Control-System/Expansion-IO/HD-CTL-101)
- [Liberty DL-UHDILC](https://secure.libertycable.com/product_details.php?pitem=DL-UHDILC)
- [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad)

If the displays aren't visible to the Windows PC when in their sleep state, Teams Rooms may report display disconnected alerts messages in Teams Admin Center and the Pro Management Portal and you may experience instability with your Teams Rooms devices. Windows believes the displays are physically disconnected. Consult your display manufacturer documentation for how to configure your displays in a way that keeps the HDMI sync with the Windows PC. If unsuccessful, powered Extended Display Identification Data (EDID) emulators/minders can be used to mitigate the instability and prevent monitoring alerts. We do not certify or offer support for EDID minders but several options are listed which have worked for other customers:

- [Extron EDID 101H 4K PLUS](https://www.extron.com/product/edid101h4kplus)
- [StarTech EDID Emulator](https://www.startech.com/en-us/audio-video-products/vsedidhd)
- [Crestron HD-CTL-101](https://www.crestron.com/Products/Catalog/Control-and-Management/Control-System/Expansion-IO/HD-CTL-101)

### Display resolution and scaling

Teams Rooms on Windows devices apply a default resolution and scale factor when initially deployed. A Teams Rooms on Windows device will select the native resolution of connected front of room display(s) and then select the recommended scaling factor to ensure the Teams Rooms application is readable. A 1920x1080 resolution receives a scaling factor of 100%, and a 3840x2160 resolution is set to 200%. Unique resolutions above 1080p follow a sliding scale to maintain a consistent graphics display. 

If there is a need to override this default display scaling behavior, the Pro Management Portal [settings](/en-us/microsoftteams/rooms/pro-portal-settings) can be utilized to set a custom resolution and/or scaling factor which will not be overridden. 

## Microsoft Teams Rooms on Windows Reset & Factory Restore

### Simple Reset

If Microsoft Teams Rooms isn't running well, performing a reset might help. Open the Teams Rooms on Windows settings and select **Reset Device** to clear the device credentials and return the Teams Rooms application to default settings.

### Factory Reset

If the basic reset doesn't resolve your issue, you may need to do a full factory reset. We recommend using the recovery media available from your Teams Rooms on Windows OEM, however, you can also use the [Microsoft Teams Rooms recovery tool](recovery-tool) and follow the factory restore instructions.

## Teams Rooms on Windows Software Updates

By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours. For the Teams Rooms application, your device connects to the Windows Store to get the latest version of the Microsoft Teams Rooms software. Before contacting Microsoft with support issues, be sure Microsoft Teams Rooms is loaded with the latest version of the app to ensure your device is in a supported state.

If you're trying to update a severely out of date Teams Rooms on Windows device, you can run this tool which that updates both the Windows operating system and Teams Rooms applications to the latest versions automatically: [Microsoft Teams Rooms Provisioning Tool](https://aka.ms/mtrp/mtrpprovisioningtool)

If you want to manage updates manually, you can acquire and run the latest MTR-Update script from [Manually update a Microsoft Teams Rooms device](/en-us/microsoftteams/rooms/manual-update).

## Switching to Admin mode

### Switching to Admin mode and back when the Microsoft Teams Rooms app is running

1. Hang up any ongoing calls, and return to the home screen.
2. Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).
3. Select **Settings**.
4. Enter the Administrator password. The Setup screen appears. If the device isn't domain-joined, the local administrative account (username "Admin") is used by default. The default password for this account is 'sfb'. Change this password as soon as possible. If the machine is domain-joined, you can sign in with an appropriately privileged domain account.
5. Select **Windows Settings** in the left column.
6. Log in to the desktop with your administrative credentials. You have the necessary privileges to manage the device.
7. Perform the necessary administrative tasks.
8. Restart the machine when you're finished.

    The console is now back in its normal operation mode. The following procedure requires you to attach a keyboard to the device if one isn't already attached.

### Switching to Admin Mode and back when the Microsoft Teams Rooms app is frozen

1. Press the Windows key five times in rapid succession. To access the Windows logon screen.
2. Log in to the desktop with your administrative credentials.
3. Perform the necessary administrative tasks.
4. Restart the machine when you're finished.

Note

This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.

The console restarts into its normal operation mode, running the Microsoft Teams Rooms app. You can remove the keyboard, if you attached one to complete this procedure.

## Clearing the Teams Rooms on Windows Cache

To clear cache using the Pro Management Portal, go to **Rooms** and select the display name of the device you want to clear the cache on. In the actions panel, select "Restart device-Clear cache", select "Run", check the "Delete Teams cache?" box, and select "Run". Your Teams Rooms clears its cache and reboot.

You can also perform this task directly on the device with these steps:

1. Switch to Admin mode.
2. Open Windows Explorer and follow the instructions for your app version:
3. Navigate to: `C:\Users\Skype\AppData\Local\Packages\MSTeamsRooms_8wekyb3d8bbwe\LocalCache\Microsoft\MSTeams`.
4. Delete everything inside the MSTeams folder.
5. Restart the Teams Rooms device and allow it to return to the Teams Rooms interface.

## Teams Rooms on Windows language settings

### Changing the Teams Rooms console language or date & time format

1. Switch to Admin mode.
2. Select the **Start** menu.
3. Select the gear icon to launch the **Settings** app.
4. Select **Time & language** tab.
5. Select **Language & region**.
6. Under Regional format, select **Recommended**.
7. Under Preferred languages, select **Add a language**.
8. Select the language you want to add.
9. Select **Next**.
10. Under Language preferences, check **Set as my Windows display language**.
11. Select **Install**.
12. Verify that the language you added is at the top of the Preferred languages list and is the Windows display language.
13. Optionally, if you want to remove any languages:
    1. Select the three-dot menu next to the language you wish to remove.
    2. Select **Remove**.
14. Sign out.
15. Sign back in to your admin account.
16. Start an elevated command prompt.
17. Run the following command: 

    ```PowerShell
      powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
18. Clear the cache on the device following these steps: [Clear Cache](/en-us/microsoftteams/rooms/rooms-operations#clearing-the-teams-rooms-on-windows-cache)
19. Restart the system.

Your desired language is now applied to the Microsoft Teams Rooms app.

### Changing default login keyboard language

Changing the default Windows language does not change the default keyboard presented at the Windows login screen. These steps allow you to modify the keyboard shown at login.

1. Switch to Admin mode.
2. Select the **Start** menu.
3. Select the gear icon to launch the **Settings** app.
4. Select **Time & language** tab.
5. Select **Language & region**.
6. Under Regional format, select **Recommended**.
7. Under Preferred languages, select **Add a language**.
8. Select the language you want to add.
9. Select **Next**.
10. Under Language preferences, check **Set as my Windows display language**.
11. Select **Install**.
12. Verify that the language you added is at the top of the Preferred languages list and is the Windows display language.
13. Optionally, if you want to remove any languages:
    1. Select the three-dot menu next to the language you wish to remove.
    2. Select **Remove**.
14. Select the **Start** menu.
15. Select **Control Panel**.
16. Select **Clock and Region**.
17. Select the **Administrative** tab.
18. Select **Copy settings...** in the **Welcome screen and new user accounts** section.
19. Check the box next to **Copy your current settings to: Welcome screen and system accounts**.
20. Select **Ok**.
21. Reboot your device.