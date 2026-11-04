---
layout: Conceptual
title: Teams Rooms app and Windows versioning support - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-lifecycle-support
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: raginis
ms.date: 2026-08-10T00:00:00.0000000Z
ms.topic: concept-article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier2
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Learn about lifecycle support for Microsoft Teams Rooms, including the dynamic support structure and its phases.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 7ecd6ee6-8850-f346-5684-9c5d2444789f
document_version_independent_id: a55a7a01-211d-147a-5332-b68e1051a2a1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-lifecycle-support.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-lifecycle-support
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-lifecycle-support.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 3a39012e-0067-5786-4578-c303b12fa4d7
---

# Teams Rooms app and Windows versioning support - Microsoft Teams | Microsoft Learn

By default, the Microsoft Teams Rooms application receives updates through the Microsoft Teams Rooms Pro Management Portal. The app uses an evergreen product lifecycle and only the current and the next most recent major version of the app is supported at any given time. The app bundles a specific version of the Teams desktop app that is modified for room use. The Teams desktop app updates frequently while the Teams Rooms app updates less frequently. This means Teams Rooms app current-1 version can be several Teams desktop app updates behind, so it's recommended to keep the Teams Rooms app updated to the latest version always. Learn more about the [Teams update process](../teams-client-update).

Microsoft supports the most current release of Teams Rooms (N) and the previous major release (N-1) (5.1.xxx and 5.0.xxx for example), the support structure for Teams Rooms is dynamic and depends on the availability of the latest version. When you encounter a code defect in a version of the application that's not the latest, you must install the latest version to receive a fix.

All releases are listed in the [Microsoft Teams Rooms release notes](rooms-release-note).

Important

When installing a new device that came with an older version of the Teams Rooms application, it is recommended to [manually update the application](/en-us/microsoftteams/rooms/rooms-operations#teams-rooms-on-windows-software-updates) after setting the account this ensures correct OS version and Windows Updates are installed on your device.

## Windows release support

Microsoft Teams Rooms requires the Windows IoT Enterprise or Windows Enterprise SKUs under the Global Availability Channel servicing option. These other Windows editions aren't supported:

- Windows Enterprise Long-term Servicing Branch (LTSB) / Long Term Servicing Channel (LTSC) editions
- Windows Internet of Things (IoT) Enterprise LTSB / LTSC editions
- any other edition of Windows such as Windows Pro or Home edition

New Windows feature updates aren't offered on Microsoft Teams Rooms devices immediately. There's an intentional delay of up to six months or more after the general availability date published on the [Windows release information](/en-us/windows/release-information/) page. This time is used to validate Windows release compatibility for the Microsoft Teams Rooms app, device hardware, and certified audio video peripherals. Validation begins and continues during active development of each major release of Windows. Extra time is needed to validate that all device manufacturers have built updated images for their devices, and for Microsoft to certify and test those images. During the validation period, the Microsoft Teams Rooms app uses [Windows Update for Business group policies](/en-us/windows/deployment/update/waas-manage-updates-wufb) to delay Windows feature updates. After any compatibility issues are found and resolved, the block is lifted via updating those group policies through a new Teams Rooms app release. Devices that run the Microsoft Teams Rooms app automatically update to an appropriate Windows release during the nightly maintenance reboot.

Important

During the validation period, Microsoft Teams Rooms devices should **not** be updated to the next release of Windows by any means. This includes overriding the group policies in place, or using other device management services. Any of these may cause issues for the Microsoft Teams Rooms app or may leave devices unusable.

The following table shows recommended and supported versions of Windows that are verified to support Microsoft Teams Rooms. All dates are listed in ISO 8601 format: YYYY-MM-DD.

| Version | Availability date | Microsoft Teams Rooms support status | Microsoft Teams Rooms Minimum application version |
| --- | --- | --- | --- |
| 25H2 | 2026-08-03 | Supported,Recommended | 5.6.210.0 |
| 24H2 | 2025-08-12 | Supported | 5.3.205.0 |
| 23H2 | 2023-10-31 | Not Supported | — |
| 22H2 | 2022-10-18 | Not Supported | — |

## Supported device lifecycle

Teams Rooms on Windows OEMs (Original Equipment Manufacturers) define their hardware sales and software support lifecycles. Once a Teams Rooms on Windows OEM no longer supports the device, Microsoft adds the device to the [end of service tab of the certified devices page](/en-us/microsoftteams/rooms/certified-hardware?tabs=eos). Hardware on this list may continue to receive Teams Rooms on Windows app updates as well as Windows feature updates; however, without OEM support the device may encounter bugs which cannot be fixed. Microsoft recommends customers replace hardware on the end of service list to ensure full supportability within an environment.

## Windows 10 end of support

### Support has ended for Teams Rooms devices running Windows 10

Support ended for Windows 10 on October 14, 2025, and devices will no longer receive security and feature updates and Teams Rooms and Teams Rooms Pro Management will no longer update, support, or test Teams Rooms apps on Windows 10. Upgrade your Teams Rooms on Windows devices to Windows 11 to continue to receive the latest productivity, security, and management features.

Utilize the Teams Rooms Pro Management Room Inventory export or the Windows 11 readiness checker to identify devices that need action. Devices running on Windows OS version 10.0.19045 or lower must be updated to Windows 11, if eligible, or replaced to continue receiving Teams Rooms and Teams Rooms Pro Management support and updates.

Most Teams Rooms devices running Windows 10 were automatically upgraded to Windows 11. However, some certified Teams Rooms devices can't be upgraded to Windows 11 and need to be replaced. The devices which can't upgrade to Windows 11 have been added to the [end of service tab of the certified devices page](/en-us/microsoftteams/rooms/certified-hardware?tabs=eos). Contact your device manufacturer for the specific models that are impacted.

Also, see [Microsoft product lifecycle notices for Windows 10 Enterprise](/en-us/lifecycle/products/windows-10-enterprise-and-education) and [Windows10 IoT Enterprise](/en-us/lifecycle/products/windows-10-iot-enterprise).

Important

Teams Rooms on Windows will not support devices placed on ESU: Teams Rooms on Windows has ended support for Windows 10 on the normal Windows 10 end-of-service date, October 14, 2025.

### Microsoft Teams App End of Availability on Surface Hub Running Windows 10 Team Edition

Effective October 14, 2025, the Microsoft Teams Rooms app based on classic Teams is no longer accessible on Surface Hub v1 and Surface Hub 2S devices running Windows 10 Team edition. This change aligns with the previously announced [retirement of the Teams classic client](/en-us/microsoftteams/teams-classic-client-end-of-availability) and the [end of support for Windows 10](/en-us/lifecycle/products/windows-10-team-surface-hub).