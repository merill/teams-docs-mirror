---
layout: Conceptual
title: Certified Native Bluetooth Devices - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/bluetooth-devices
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: slamprianou
ms.date: 2025-01-16T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
ms.localizationpriority: medium
ms.custom: QuickDraft
search.appverid: MET150
f1.keywords:
- NOCSH
ai-usage: ai-assisted
description: This article provides a comprehensive overview of Native Bluetooth personal peripherals and outlines the certification requirements necessary for compatibility with Microsoft Teams.
locale: en-us
document_id: 2530371f-79b5-7025-4d7c-17a5e56173ab
document_version_independent_id: 2530371f-79b5-7025-4d7c-17a5e56173ab
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/bluetooth-devices.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/bluetooth-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/bluetooth-devices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/19ec6774-09b8-473e-a17e-b17b518bbad7
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ade36b61-c646-4bd8-87ee-f3a843461962
platformId: f1093c9c-73e7-90ba-7fed-3eda1d850741
---

# Certified Native Bluetooth Devices - Microsoft Teams | Microsoft Learn

Native Bluetooth personal peripherals refer to personal headsets or speakerphones that are directly paired and connected to the integrated Bluetooth radio of a host device, such as a PC or mobile phone, without requiring an adapter or also called a dongle. This article provides a comprehensive overview of Native Bluetooth personal peripherals and outlines the certification requirements necessary for compatibility with Microsoft Teams.

## Certification requirements

The certification program ensures that audio personal peripherals offer rich audio quality and full functionality with the Teams app experience. Functionalities included in this certification are:

- Calling
- Mute
- Teams button

Certified devices work with plug & play functionality with no extra configuration required and offer call control with Microsoft Teams. They also offer Mute sync status between the device and the Teams desktop client and vice versa. The certification program scope includes the use of the Teams desktop client only.

## Pairing Native Bluetooth peripherals to a Windows PC

To pair a Native Bluetooth Peripheral to your Windows 11 PC, start by ensuring that your peripheral and PC meets the minimum requirements.

1. Place the peripheral in pairing mode following the instructions from the manufacturer.
2. If the peripheral and your Windows PC support Swift Pair, you may see a notification prompting you to pair the device with a single select.
3. If you don't see this notification when the device enters pairing mode, the device can be paired manually through the **Settings** app. For more information about pairing Bluetooth peripherals with Windows, see [Pair a Bluetooth device in Windows - Microsoft Support](https://support.microsoft.com/windows/pair-a-bluetooth-device-in-windows-2be7b51f-6ae9-b757-a3b9-95ee40c3e242).

## Minimum Requirements

### Hardware Requirements

Native Bluetooth peripherals are supported on PCs that meet the minimum requirements for Windows 11 and have an integrated Bluetooth radio.

We recommend the following processors:

- **AMD - all Windows 11 compatible models**
- **Intel - Intel® Core™ 12th Gen processors or newer**
    - See the OS and software requirements section for recommended driver versions
- **Qualcomm - Snapdragon X or newer**

PCs using aftermarket USB Bluetooth adapters are not recommended or certified. USB Bluetooth audio dongles that connect to the PC as a USB Audio device instead of a Bluetooth controller cannot support the Native Bluetooth experience in Microsoft Teams.

### OS and software requirements

- Windows: Windows 11
- macOS: Not supported yet

On Windows 11 PCs with Intel processors, we recommend the following minimum driver versions:

- **Intel Smart Sound Technology (Intel SST):**

    - Intel Core Ultra processors (Series 2): 20.42.11233.0 or newer
    - Intel Core Ultra processors (Series 1): 20.40.11112.5 or newer
    - Intel Core 12th Gen / 13th Gen: 10.29.00.11261 or newer
- **Intel Bluetooth: 23.70.x or newer**
- **Intel Wi-Fi: 23.70.x or newer**

### Minimum Teams desktop app version

- Teams App version: 24335.208.3315.1951 or newer

## Known issues

- Teams button won't work consistently in the following cases:
    - Connecting more than one Bluetooth peripheral directly to the laptop at the same time.
    - Logging into more than one tenant under the same Teams desktop client.
    - When the Teams desktop client is closed and reopened, it needs a few seconds for the Teams button to work again. If this doesn't work, turn off and on your headset to resolve the issue.
- Mute status sync from the Teams desktop client to the device works only with Teams-certified peripherals.

### Checking driver versions

#### Checking iSST driver version

1. Open **Device Manager**.
2. Locate **Sound, Video, and Game Controllers** and expand it.
3. Find **Intel Smart Sound Technology (iSST)**.
4. Right-click and select **Properties** and go to the **Driver** tab to check the driver version.

#### Checking Intel Bluetooth driver version

1. Open **Device Manager**.
2. Locate **Bluetooth** and expand it.
3. Find **Intel(R) Wireless Bluetooth**.
4. Right-click and select **Properties** and go to the **Driver** tab to check the driver version.
5. Download the latest version from [Intel Wireless Bluetooth Drivers for Windows 10 and Windows 11](https://www.intel.com/content/www/us/en/download/19351/intel-wireless-wi-fi-drivers-for-windows-10-and-windows-11.html?wapkw=wifi).

#### Checking Intel Wi-Fi driver version

1. Open **Device Manager**.
2. Locate **Network Adapters** and expand it.
3. Find **Intel(R) Wi-Fi Component**.
4. Right-click and select **Properties** and go to the **Driver** tab to check the driver version.
5. Download the latest version from [Intel Wireless Wi-Fi Drivers for Windows 10 and Windows 11](https://www.intel.com/content/www/us/en/download/19351/intel-wireless-wi-fi-drivers-for-windows-10-and-windows-11.html?wapkw=wifi).

## Certified Native Bluetooth peripherals

This certification is currently for Classic Bluetooth devices. The Microsoft Teams Certification Program has not started certifying Bluetooth Low Energy (LE) Audio headsets yet. We will update this article when the time comes. We do not anticipate issues with headsets that support both Classic Bluetooth and Bluetooth LE Audio, but the latter mode is not certified for Teams.

To see a list of supported Bluetooth personal peripherals, see [Certified personal peripherals](/en-us/microsoftteams/devices/usb-devices?tabs=bluetooth).

## Troubleshooting

The performance of a peripheral in Native Bluetooth mode is impacted by the Bluetooth radio on the host PC. We recommend installing the latest firmware updates for both peripherals and Bluetooth radio.

If problems persist, start by reviewing the Bluetooth troubleshooting steps at [Fix Bluetooth problems in Windows - Microsoft Support](https://support.microsoft.com/help/14169/windows-10-fix-bluetooth-problems).

A small portion of users may need to continue to use a USB dongle to connect to the peripheral instead of using a Native Bluetooth connection to their Windows PC. This can happen in scenarios such as working in a high-density wireless environment, if the PC's Bluetooth radio is heavily used by multiple paired devices, or with certain PCs with older Bluetooth radios that are no longer receiving manufacturer support.