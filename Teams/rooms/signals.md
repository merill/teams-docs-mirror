---
layout: Conceptual
title: Health signals - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/signals
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: srpall
manager: mattslomka
ms.reviewer: mattslomka
ms.date: 2026-10-05T00:00:00.0000000Z
ms.topic: article
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
description: This article shows you the health signals that are available, not available, or not applicable for Teams Rooms on Windows, Teams Rooms on Android, Teams panels, Teams phones, and Microsoft Device Ecosystem Platform (MDEP).
locale: en-us
document_id: bf0f9eb7-7056-b845-7262-c0d2562a0672
document_version_independent_id: bf0f9eb7-7056-b845-7262-c0d2562a0672
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/signals.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/signals
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/signals.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 216e3a89-4a43-2d48-07af-6fc33deaf887
---

# Health signals - Microsoft Teams | Microsoft Learn

The Pro Management Portal monitors your Teams devices through granular signals, which are telemetry-based monitors for components that are important to the function of Teams devices. Each signal is used to proactively detect issues, trigger alerts, and support automated ticketing and remediation workflows.

The health of a Teams device is determined by signals that monitor important functions of the device. When a signal activates and is marked as unhealthy, an [incident](/en-us/microsoftteams/rooms/managed-meeting-rooms-portal) is generated with a unique incident ID. This is the tracking number for a specific issue associated with a particular signal. Your organization can have different preferences or needs for your environment. To help focus on the signals that are important to you, it is possible to suppress specific signals for individual devices. Additionally, you can enable or disable signals for all applicable devices through the [signal settings](/en-us/microsoftteams/rooms/signal-settings) page.

[![Teams Rooms Pro Management Portal - Signals YouTube](media/signals/teams-rooms-pro-management-portal---signals-youtube.png)](https://aka.ms/PMPSignals)

#### How signals work

Signals activate based on properties reported by the agent and remain active as long as they are not healthy. Depending on the signal, activation may not be immediate. Two factors introduce delays in activation, polling frequency and an intermediate "watching" state. Some properties are checked every 5 minutes, while others may only be evaluated every 2 hours. Certain signals include a watching period—up to 150 minutes—before activation.

For example, the calendar sync signal is polled every 5 minutes, but it requires a 30-minute watching period, resulting in a maximum activation latency of 35 minutes. Refer to the signal delay reference table for specific timing details per signal.

After activation, some signals support automatic diagnostics or remediation workflows. When triggered, these workflows attempt to run remediations to resolve the issue. Output from these is recorded in the incident for reference.

When the underlying properties return to a healthy state, the associated ticket is automatically marked as resolved. If the signal remains healthy for 7 consecutive days, the ticket is closed. If the signal becomes unhealthy again during this 7-day period, the same ticket is reactivated and returns to an unhealthy state.

# [Windows](#tab/MTRW)
These are the signals that are available currently for Microsoft Teams Rooms on Windows with Teams Rooms Pro licenses.

| **Signal name** | **Description** | **Category** | **Severity** | Polling frequency (min) | Watching period (min) |
| --- | --- | --- | --- | --- | --- |
| Recorded issue | Problem was observed and recorded. | Recorded | Critical | 0 | 0 |
| [Sign in (Teams)](/en-us/microsoftteams/devices/pmpsignal-resource-account-sign-in) | This ticket is triggered when Teams fails to sign in. | Account management | Critical | 5 | 30 |
| Calendar sync | This ticket is triggered when the device is unable to sync calendar data. This signal applies to devices with the refreshed user interface (UI), and it replaces the Exchange Sign-In as the device no longer authenticates directly with Exchange but syncs via Teams which aligns with other teams' clients. | Account management | Critical | 5 | 30 |
| Meeting app version | This signal is triggered when the Microsoft Teams Room app version is an earlier one (n-2 version) to help identify rooms that aren't taking app updates and, hence, running out-of-support versions. | OS, firmware, and apps | Warning | 120 | 0 |
| [Meeting app (heartbeat)](/en-us/microsoftteams/devices/pmpsignal-meeting-app-status) | This ticket triggers when the Teams Rooms application isn't running which can be a result of "inability to sign in using the local account" or as a result of some issue with the App or Windows. This signal includes an auto remediation that attempts to fix some common causes and report back more information if it can't resolve. | Configurations and settings | Critical | 10 | 60 |
| Nightly Reboot disabled | A Teams Rooms device has been running continuously for two or more days, and the nightly Reboot task is disabled. This can affect scheduling of updates or effectiveness of remediations by the agent. | Configurations and settings | Warning | 120 | 0 |
| [Camera, Room](/en-us/microsoftteams/devices/pmpsignal-camera-status-unhealthy) | This alert is triggered when the system reports that "no room camera has been detected". Any camera configured as a content/whiteboard camera isn't tracked by this alert. | Hardware and peripherals | Important | 5 | 5 |
| [Camera, Default](/en-us/microsoftteams/devices/pmpsignal-camera-status-unhealthy) | Configured default room camera is missing, but another room camera (not content or whiteboard camera) is found and healthy. | Hardware and peripherals | Warning | 5 | 5 |
| Camera (Enhanced) | As part of enhanced diagnostics that run during the nightly maintenance window, this signal validates that the camera is producing clear and usable video for meetings. This ticket triggers when the camera quality produces black or empty video output. | Hardware and peripherals | Important | 1440 | 1440 |
| [Content/Whiteboard camera](/en-us/microsoftteams/devices/pmpsignal-camera-status-unhealthy) | The configured Content (Whiteboard) camera is no longer found. | Hardware and peripherals | Important | 5 | 5 |
| [HDMI ingest](/en-us/microsoftteams/devices/pmpsignal-hdmi-ingest) | This signal is triggered when the wired video ingest hardware isn't detected. In-room participants won't be able to share from external devices (for example, laptop) using the wired video input. | Hardware and peripherals | Important | 5 | 10 |
| [Low disk space](/en-us/microsoftteams/devices/pmpsignal-disk-space) | This ticket is triggered when the room is low on available disk space. When this alert is active, an automatic remediation job is executed outside business hours (between 9PM and 2AM of local room time zone) to remove cleanable files and free enough space to maintain daily operations. | Hardware and peripherals | Important | 120 | 15 |
| Disk health | The primary drive has high disk wear or SMART errors. | Hardware and peripherals | Important | 120 | 0 |
| [USB Selective Suspend](/en-us/microsoftteams/devices/pmpsignal-usb-selective-suspend) | This signal is triggered when the USB selective suspend is enabled, under **power plan** settings of Windows. When this setting is enabled, it may cause device peripherals to become unresponsive or disconnected. | Hardware and peripherals | Warning | 120 | 0 |
| [USB Peripheral Power Draining](/en-us/microsoftteams/devices/pmpsignal-usb-peripherial-power-drain) | This signal is triggered when the USB Peripheral Power Drain is enabled under Windows settings. USB devices can go under low-power state when the screen goes to sleep and may not recover when the screen is back on. | Hardware and peripherals | Warning | 120 | 0 |
| [Bluetooth disabled](/en-us/microsoftteams/devices/pmpsignal-bluetooth) | This signal is triggered when the Bluetooth is disabled under Windows settings (OS level). When this setting is disabled, it prevents a room from being discovered via proximity join or Teams casting (relying on Bluetooth Low Energy beacon). | Hardware and peripherals | Warning | 120 | 0 |
| [Conferencing microphone](/en-us/microsoftteams/devices/pmpsignal-microphone-speaker-status) | This alert is triggered when the system reports that "no conferencing microphone has been detected or is viable". | Hardware and peripherals | Important | 5 | 5 |
| [Configured conferencing microphone](/en-us/microsoftteams/devices/pmpsignal-microphone-speaker-status) | This alert is triggered when the system reports that "the configured conferencing microphone isn't detected but another viable microphone is being used for calls". | Hardware and peripherals | Warning | 5 | 5 |
| [Conferencing speaker](/en-us/microsoftteams/devices/pmpsignal-microphone-speaker-status) | This alert is triggered when the system reports that "there's no conferencing speaker detected or that no conferencing speaker is viable." | Hardware and peripherals | Important | 5 | 5 |
| [Configured conferencing speaker](/en-us/microsoftteams/devices/pmpsignal-microphone-speaker-status) | This alert is triggered when the system reports that "the configured conferencing speaker isn't detected but another viable speaker is being used for calls". | Hardware and peripherals | Warning | 5 | 5 |
| [Misconfigured conferencing speaker](/en-us/microsoftteams/devices/pmpsignal-microphone-speaker-status) | This alert is triggered when the system reports that the conferencing speaker is set to use the speakers within a front-of-room display which is unsupported. Until this is resolved, the in-room participants' audio experience is degraded. Critical alerts for conferencing speaker will also be suppressed to avoid the alerts getting opened/closed every time the display sleeps. | Hardware and peripherals | Warning | 5 | 5 |
| [Configured default speaker](/en-us/microsoftteams/devices/pmpsignal-microphone-speaker-status) | This alert is triggered when the system reports that "the configured default speaker isn't detected". | Hardware and peripherals | Warning | 5 | 5 |
| Audio (Enhanced) | As part of enhanced diagnostics that run during the nightly maintenance window, this signal identifies problems affecting audio output and playback quality. A test tone is played through the conferencing speaker to verify successful playback. | Hardware and peripherals | Important | 1440 | 1440 |
| Logitech Rally Mic Pod | This alert is triggered when Logitech Sync reports that "one or more Logitech Rally Mic Pods are missing." | Hardware and peripherals | Warning | 5 | 5 |
| Logitech Rally Speaker | This alert is triggered when Logitech Sync reports that "one or more Logitech Rally Speakers are missing." | Hardware and peripherals | Warning | 5 | 5 |
| [CPU performance limited](/en-us/microsoftteams/devices/pmpsignal-cpu-performance-unhealthy) | This alert is triggered when the power settings of Windows are set to limit the maximum performance of the CPU (even when connected to an external power supply). This may have an effect in the overall CPU performance during peak times. | Hardware and peripherals | Warning | 120 | 0 |
| [Sleep timer](/en-us/microsoftteams/devices/pmpsignal-sleep-timer) | This signal is triggered when the 'Sleep after' timer is set on Windows Power Plan settings. When the Sleep Timer is enabled, the device won't wake up from sleep mode when a meeting is scheduled. | Hardware and peripherals | Warning | 120 | 0 |
| [Display, Front of Room](/en-us/microsoftteams/devices/pmpsignal-front-of-room-display) | Number of detected front-of-room (FoR) displays are fewer than configured. For example, a room is configured for dual FoR, and fewer than two displays are currently detected. If configured for a single FoR, no display is currently detected. | Display | Important | 5 | 5 |
| [Display, Console](/en-us/microsoftteams/devices/pmpsignal-front-of-room-display) | Certified console display isn't detected. | Display | Important | 5 | 5 |
| Display (Enhanced) | As part of enhanced diagnostics that run during the nightly maintenance window, this signal validates that Teams application windows are positioned and scaled correctly on front-of-room (FoR) displays and console. It evaluates whether window bounds and scaling align within expected tolerances, based on recommended configuration. | Display | Warning | 1440 | 1440 |
| [Default credentials](/en-us/microsoftteams/devices/pmpsignal-mtrw-default-credentials) | This alert is triggered if the Teams Room system remains with the default username and password of the preconfigured local administrator ('Admin' username and a well-known password) out of the box. This signal is assessed periodically for changes (every 2 hours), and the severity of the alert (Warning only) doesn't affect the overall health state of the room. | Security | Warning | 120 | 0 |
| Network | This alert is triggered when the Teams Room app reports that "the network access to the Internet is limited", which may have potential implications in connecting to Microsoft Teams services. | Connectivity | Warning | 5 | 0 |
| Monitoring | This is triggered when Teams Room Pro management portal doesn't receive telemetry from a device, even though Teams service may still report a successful Sign in from the device recently. In this state, the Teams Room Pro management portal is unable to report the health of the device, deploy updates, operate automatic remediations or enable execution of remote tasks (for example, collect logs). | Connectivity | Important | 60 | 1 |
| Monitoring connectivity issue | This alert is triggered when the Pro Management agent is unable to provide a complete set of signals due to restrictions in network connectivity. It may occur due to general failures and potential network connection issues that come up due to incorrect proxy settings. The underlying issue often also prevents the agent's ability to operate routine updates on the device, raise specific alerts (incidents), or complete automated diagnostics/remediations. | Connectivity | Warning | 120 | 150 |
| [Unmonitored](/en-us/microsoftteams/devices/pmpsignal-unmonitored-offline) | This is triggered when the Admin agent running on the device ceases to report information. This condition would likely indicate that a device is powered off or is disconnected from the network so that the management service can be reached. | Connectivity | Important | 180 | 1 |
| [OS edition](/en-us/microsoftteams/devices/pmpsignal-os-edition) | When a device is running a version of OS that's not yet supported, it's important to roll it back or upgrade it to a certified version. | OS, firmware, and apps | Warning | 120 | 0 |
| Connected using Wi-Fi | When an Teams Room device is exclusively connected to the Internet via Wi-Fi, call quality might be negatively affected, affecting the overall user experience. While some organizations have Ethernet (wired) as primary/default connection to the Internet, they also leave Wi-Fi connection configured to be used as a fallback option. This alert is triggered when no Ethernet connectivity to the Internet is available. | Connectivity | Recommended | 120 | 0 |
| Wi-Fi signal strength | When an Teams Room device is exclusively connected to the Internet via Wi-Fi, call quality might be negatively affected, affecting the overall user experience. This alert is triggered when the Teams Room device is connected exclusively to a Wi-Fi network that has low strength. | Connectivity | Warning | 120 | 0 |
| Time drift | Time gap is detected between the current time (UTC) on the Windows device and the time (UTC) of the Teams Rooms Pro Management service. This time gap can result in sign-in issues, update-related failures, or meetings not appearing on the device calendar. | OS, firmware, and apps | Warning | 120 | 0 |
| [Windows Update disabled](/en-us/microsoftteams/devices/pmpsignal-windows-update) | This signal is triggered when Windows Update service is disabled on the device to help identify rooms that aren't receiving Windows Updates and, hence, that run out-of-support versions or get subjected to vulnerabilities. | OS, firmware, and apps | Warning | 120 | 0 |
| Windows OS activation status | This alert is triggered when Windows OS activation state is being reported as "not licensed". This state could indicate that the activation process wasn't successful. | OS, firmware, and apps | Recommended | 120 | 0 |
| Windows Server Update Service (WSUS) enabled | No recent updates have been installed via Windows Update, and agent has detected an existing WSUS configuration set on the device. | OS, firmware, and apps | Important | 120 | 0 |
| Windows Updates Components need reset | This ticket is created when the system hasn't had recent Windows updates and when one of the following conditions is true:  1. The device has rolled back to a previous version.  2. Windows update services are failing.  3. There's a significant number of errors in the Windows Update logs.  4. This remediation is allowed to be executed only once a month. | OS, firmware, and apps | Important | 120 | 0 |
| Windows Update blocked | Windows Update endpoints may not be reachable, and this condition prevents the device to stay up-to-date. | Connectivity | Warning | 120 | 10 |
| Outage | Service outage | Outage | N/A |  |  |

# [Android (Video bar)](#tab/MTRA)
These are the signals that are available for video bar devices running Microsoft Teams Rooms on Android.

| **Signal name** | **Description** | **Category** | **Severity** | Polling frequency (min) | Watching period (min) |
| --- | --- | --- | --- | --- | --- |
| Recorded issue | Problem was observed and recorded. | Recorded | Critical | 0 | 0 |
| [Sign in (Teams)](/en-us/microsoftteams/devices/pmpsignal-resource-account-sign-in) | This signal is triggered when the device doesn't have an account signed in. | Account management | Critical | 120 | 0 |
| [Bluetooth disabled](/en-us/microsoftteams/devices/pmpsignal-bluetooth) | This signal is triggered when the Bluetooth is disabled under Windows settings (OS level). When this setting is disabled, it will prevent a room from being discovered via proximity join or Teams casting (relying on Bluetooth Low Energy beacon). | Hardware and peripherals | Warning | 120 | 20 |
| Pairing (Touch console) | This device does not appear to be paired by Teams with a touch console. An unpaired touch console makes it difficult for end users to start or join meetings. | Hardware and peripherals | Warning | 120 | 60 |
| Offline | This is triggered when the Admin agent running on the device ceases to report information. This condition would likely indicate that a device is completely powered off or is disconnected from the network so that the management service can be reached. | Connectivity | Critical | 120 | 60 |

# [Android (Touch Console)](#tab/console)
These are the signals that are available for touch console devices running Microsoft Teams Rooms on Android.

| **Signal name** | **Description** | **Category** | **Severity** | Polling frequency (min) | Watching period (min) |
| --- | --- | --- | --- | --- | --- |
| Recorded issue | Problem was observed and recorded. | Recorded | Critical | 0 | 0 |
| [Sign in (Teams)](/en-us/microsoftteams/devices/pmpsignal-resource-account-sign-in) | This signal is triggered when the device doesn't have an account signed in. | Account management | Critical | 120 | 0 |
| [Bluetooth disabled](/en-us/microsoftteams/devices/pmpsignal-bluetooth) | This signal is triggered when the Bluetooth is disabled under Windows settings (OS level). When this setting is disabled, it will prevent a room from being discovered via proximity join or Teams casting (relying on Bluetooth Low Energy beacon). | Hardware and peripherals | Warning | 120 | 20 |
| Pairing (Video bar) | This device does not appear to be paired by Teams with a video bar. The touch console cannot control the unpaired video bar. The end user experience is likely to be degraded. | Hardware and peripherals | Warning | 120 | 60 |
| Offline | This is triggered when the Admin agent running on the device ceases to report information. This condition would likely indicate that a device is completely powered off or is disconnected from the network so that the management service can be reached. | Connectivity | Critical | 120 | 60 |

# [Android (Teams panel)](#tab/panel)
These are the signals that are available for Teams panel devices running Microsoft Teams Rooms on Android.

| **Signal name** | **Description** | **Category** | **Severity** | Polling frequency (min) | Watching period (min) |
| --- | --- | --- | --- | --- | --- |
| Recorded issue | Problem was observed and recorded. | Recorded | Critical | 0 | 0 |
| [Sign in (Teams)](/en-us/microsoftteams/devices/pmpsignal-resource-account-sign-in) | This signal is triggered when the device doesn't have an account signed in. | Account management | Critical | 120 | 0 |
| Offline | This is triggered when the Admin agent running on the device ceases to report information. This condition would likely indicate that a device is completely powered off or is disconnected from the network so that the management service can be reached. | Connectivity | Critical | 120 | 60 |

# [Teams phone](#tab/phone)
These are the signals that are available for Teams phone devices running Microsoft Teams on Android.

| **Signal name** | **Description** | **Category** | **Severity** | Polling frequency (min) | Watching period (min) |
| --- | --- | --- | --- | --- | --- |
| [Sign in (Teams)](/en-us/microsoftteams/devices/pmpsignal-resource-account-sign-in) | This signal is triggered when the device doesn't have an account signed in. | Account management | Critical | 120 | 0 |
| Offline | This is triggered when the Admin agent running on the device ceases to report information. This condition would likely indicate that a device is completely powered off or is disconnected from the network so that the management service can be reached. | Connectivity | Important | 120 | 1 |

---