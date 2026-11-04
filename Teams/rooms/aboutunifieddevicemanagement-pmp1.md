---
layout: Conceptual
title: Transitioning Teams Android Device Management from Teams Admin Center to the Teams Rooms Pro Management Portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/aboutunifieddevicemanagement-pmp1
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Transitioning Teams Android Device Management from Teams Admin Center to the Teams Rooms Pro Management Portal
author: ArchanaYerragangu
ms.author: ayerragangu
manager: srpall
ms.service: msteams
ms.topic: article
ms.date: 2026-10-30T00:00:00.0000000Z
ms.subservice: itpro-devices
locale: en-us
document_id: 99508871-dfed-2c8d-9658-6da667a3b972
document_version_independent_id: 99508871-dfed-2c8d-9658-6da667a3b972
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/aboutunifieddevicemanagement-pmp1.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/aboutunifieddevicemanagement-pmp1
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/aboutunifieddevicemanagement-pmp1.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: be55bf11-e9df-243e-0651-8fc05f1b94ee
---

# Transitioning Teams Android Device Management from Teams Admin Center to the Teams Rooms Pro Management Portal - Microsoft Teams | Microsoft Learn

Roadmap: [555235](https://www.microsoft.com/en-us/microsoft-365/roadmap?msockid=33e5aaeea36b65a61ef4bdeaa2fe641f&amp;searchterms=555235#Roadmap)

As part of our ongoing mission to deliver a modern, secure, and scalable one-stop management portal for admins, we're transitioning **Teams Android device management from the Teams admin center (TAC) to the Teams Rooms Pro Management portal (PMP)**.

This consolidation brings management of all Teams devices, including Teams Rooms on Windows, Teams Rooms on Android, Teams panels, Teams phones, and SIP Phones into a **single, unified portal**, giving IT Admins a consistent, and seamless experience for managing their Teams devices at scale.

This article serves as the **main information source for this** transition. We continue updating it with timelines, milestones, migration guidance, and readiness steps as the rollout progresses.

[![Thumbnail showing the Teams Rooms Pro Management Portal - Android Mgmt YouTube Video.](media/aboutunifieddevicemanagement-pmp1/teams-rooms-portal-android-youtube-video.png)](https://aka.ms/PMPAndroidMgmt)

## Why This Change?

Organizations today manage a diverse fleet of Teams devices across meeting rooms, shared spaces, and personal work environments. Managing these devices across multiple portals creates operational complexity and fragmented workflows.

By consolidating Teams device management into the Teams Rooms Pro Management Portal, admins gain:

- One unified management experience across all Teams device types.
- Enhanced monitoring and operational insights.
- Advanced automation and AI-assisted management capabilities.

## What’s Changing?

Starting **June 2026**, device inventory, monitoring, and management for the following Android-based Teams devices transition from TAC to the Teams Rooms Pro Management Portal:

- Teams Rooms on Android
- Teams Phones
- Teams Panels
- SIP devices

Note

The management of Teams Displays won't be migrated from Teams Admin Center to Teams Rooms Pro Management portal. This is in line with the end of support for the Teams Displays app. See [Microsoft Teams Displays](/en-us/microsoftteams/devices/teams-displays).

**The following capabilities to be available, and enhanced in PMP:**

- Complete device inventory, including metadata and app information.
- Remote actions (restart, log collection, sign-in, sign-out, provisioning, and more).
- Update management (manual and automated).
- Device settings and configuration profiles.
- Device health signals and monitoring.
- SIP device management.

Monitor this article and Message Center posts for any feature-specific updates and timelines.

Once the transition is complete, **PMP becomes the primary portal for all Teams device management**, and the **overlapping device management functionalities in TAC are gradually retired to streamline the experience.**

## How Migration Works

The transition occurs in phases. Device management capabilities become available in the Pro Management portal as they reach **General Availability (GA)**.

When Android device management reaches GA:

- Your existing devices automatically appear in the Pro Management portal.
- Device management actions in TAC begin redirecting to Pro management portal.
- Clear advance communication provided before any TAC workflows are retired.

## Migration Timeline

Below is the current high-level rollout plan. Dates are subject to refinement as development progresses.

- **Phase 1** **(Until May 2026)** **- Preparation and Early Guidance**

    - Admin onboarding guidance available.
    - Ongoing updates on Android features in PMP and roadmap progress.
- **Phase 2** **(End of June 2026)** **- Transition Begins**

    - Android device management capabilities start appearing in PMP.
    - Select device management workflows begin redirecting from TAC to PMP.
    - Continued feature rollout and enablement.
- **Phase 3** **(July and Aug 2026)** **- Expanded Capability and Default Experience**

    - Full management workflows available in PMP (July 2026).
    - TAC workflows increasingly redirected to PMP (Aug 2026).
    - Customer migration completed.
    - Formal deprecation notices issued.
- **Phase 4** **(Start November 2026)** **- Decommissioning the overlapping Teams device management features in TAC**

    The deprecation of Teams device management capabilities in TAC will begin in November 2026 and will roll out in phases based on device type and feature readiness.

    - For public clouds -
        - SIP, MTR-A and Panels devices administration experience in TAC will start deprecating by Mid-November and will complete by end of November.
        - Phones devices administration experience in TAC will start deprecating by early December and complete by December 15th.
    - For Gov clouds ( GCC, GCC-H and DoD)
        - For GCC-H and DoD, device administration experience in TAC will start deprecating by early December and will be completed by December 15th.
        - For GCC, devices administration experience in TAC will start deprecating by early January and will be completed by January 30th.
        - Phones devices administration experience for all Sovereign cloud (GCC, GCC-H, DoD) customers will start deprecating by early January and will be completed by January 30th.
- **Remaining TAC device management workflows retired.**
- PMP becomes the primary management portal.

## Migration checklist and prerequisites

#### Step 1: Access the Teams Rooms Pro Management Portal

1. Access the Teams Rooms Pro Management Portal (PMP):

    1. Public / GCC: [https://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)
    2. GCCH: https://devices.gov.teams.microsoft.us/
    3. DoD: https://devices.dod.teams.microsoft.us/
2. Access requires:
3. Either an appropriate Microsoft Entra ID role **(Global Administrator, Teams Administrator, Teams Device Administrator, Global Reader).**
4. Or PMP built-in role (**Teams Rooms Pro Manager, Site Lead,** and **Site Technician**).
5. Or PMP custom roles that can be scope to specific devices and device groups
6. See the role requirements [here](/en-us/microsoftteams/rooms/rooms-pro-rbac).
7. Licensing requirements for PMP access:

    1. Org has at least one **Teams Rooms Pro** or **Teams Rooms Basic** or **Teams Rooms Standard** license, **or**
    2. Org has at least one **Teams Shared Space** license (formerly Shared devices), **or**
    3. Org has at least one Teams device already enrolled in PMP *(primarily applicable to the customers managing only Teams Phones and don’t have above-mentioned licenses)*

        1. Existing Teams Phones enrolled in TAC automatically enroll in PMP after updating to Admin Agent version AA 830 version (**1.0.0.202606082157.product**) or later. Please see latest Admin Agent releases [here](/en-us/microsoftteams/devices/certified-device-apps).
        2. New customers have to sign-in into at least one of their Teams Phones for the automatic enrollment of the device leading to the tenant provisioning into PMP.

Note

**Administrative units (AU):** If an admin is scoped to an Administrative Unit in Entra ID, they won't be able to access the portal. In that case, have an administrator with full access create custom roles in the Pro Management Portal to delegate granular access. Learn more about [custom roles](/en-us/microsoftteams/rooms/rooms-pro-rbac).

#### Step 2: Verify Android devices are visible and manageable in PMP

1. Teams Devices including MTR-A, Teams Panels, Teams Phones and SIP Phones, that are enrolled in Teams Admin Center (TAC) appear automatically in Pro Management Portal (PMP).
2. If your Teams Android devices: aren't visible, are unmanageable, or display "Device is not connected to IoT Hub" message within the Pro Management Portal:

    ![Screenshot shows the hub error message.](media/aboutunifieddevicemanagement-pmp1/hub-error-message.png)

    1. Ensure required URLs listed in [Teams Devices - Network Security](/en-us/microsoftteams/rooms/security?tabs=Android) are allowed on your network for both Teams Rooms on Windows and Teams Android devices.
    2. Ensure the device(s) are updated to the minimum Admin Agent version provided in the version requirements section.
    3. Ensure no unsupported [conditional access policies](/en-us/microsoftteams/rooms/supported-ca-and-compliance-policies) are assigned to the Teams Resource Accounts which could prevent authentication

Important

**Admin Agent update readiness**

Microsoft will **accelerate deployment of the minimum Admin Agent version** to Android devices, so they are ready to be managed in the Teams Rooms Pro Management portal as soon as possible. This means, Admin Agent on your devices will get updated at faster cadence than duration configured via update rings.

Customers who have disabled auto updates permanently will have their devices **forcefully auto-updated to the minimum Admin Agent version** before the deprecation of device management capabilities in TAC to avoid any disruption. Customers who don't have auto update available (specially devices on very old version of Admin Agent) should manually update their devices to the minimum Admin Agent version before the deprecation of device management capabilities in TAC to avoid any disruption.

Government cloud customers (GCC, GCC-High, DoD) will soon have their devices auto-updated to minimum required Admin Agent version **AA 856**[(**1.0.0.202607160723**)](/en-us/microsoftteams/devices/certified-device-apps) before the deprecation of device management capabilities in TAC to avoid any disruption.

These admin Agent updates to minimum required Admin Agent for successfully managing their devices PMP are **NOT PAUSABLE** and are mandatory to manage your devices in PMP successfully.

After the deprecation, admins will no longer be able to update these devices from TAC and may need to use the OEM portal to update firmware with required Admin Agent before the devices can be managed in PMP again.

**To ensure uninterrupted device management in PMP, it is strongly recommended that you update your devices to the minimum required Admin Agent version as soon as possible (manually or via auto-updates). Failure to do so may result in disruptions to device operations.**

#### Step 3: Complete feature specific tasks

The following action items are dependent on the feature availability timelines provided in the next section.

1. **Settings management** - If you wish to carry over the existing configuration profiles in Teams admin center, you can import them as **Settings Templates** in the Teams Rooms Pro Management portal. Check [Settings management in PMP](/en-us/microsoftteams/rooms/pro-portal-settings) for more information.

    Note

    The following settings are not migrated from Teams admin center (TAC) to Teams Rooms Pro Management (PMP) as part of this transition:

    1. Non-disruptive updates - Updates managed through PMP are non-disruptive by default. If a device is in use when an update is scheduled, the update is automatically postponed until the device is no longer in use.
    2. Maintenance window - The maintenance window setting is not migrated because it was not honored by Teams admin center. Devices continue to receive updates between **12:00 AM and 5:00 AM, based on the device's local time**. This behavior remains unchanged after the transition to PMP.
2. **Updates management**:

    1. After TAC to PMP migration, Customers who have their updates disabled/paused in TAC continue to have their updates disabled/paused in PMP as well.
    2. Since PMP auto update rings are relatively different than TAC auto update phases, During TAC to PMP transition period (from GA to deprecation of device administration in TAC), auto update via PMP continues to follow update cadence defined by TAC auto update phases until PMP admins explicitly adopt new auto update rings as per PMP. Check [Updates management in PMP](/en-us/microsoftteams/rooms/update-management) for more information.
    3. For Phones, All existing phones devices that aren't on minimum required Admin Agent version move to default ‘General’ auto update ring in PMP (Irrespective of TAC update phases they were part of). Once updated to minimum AA version, admins can change these phases in PMP.
    4. All updates in PMP are carried out in new default nightly maintenance window (between 12AM to 5 AM device local time). Admins can not set any different maintenance window in PMP as yet.
    5. For more information on Android updates management in PMP, check [Manage updates for Teams android devices in Pro Management portal](/en-us/microsoftteams/rooms/androidupdatemanagementinpmp).
3. **Tags** - If you wish to carry over the existing Tags in Teams admin center, you can import them as **Groups** in the Teams Rooms Pro Management portal.

    Go to **Settings &gt; Groups &gt; Import from Teams admin center**.

The import wizard guides you through the following steps:

1. **Select Tags**: The wizard loads all available Tags from Teams admin center. Select one or more Tags that you want to import.

    1. **Review:** Review the Tags selected for import and the number of devices associated with each Tag.

        Note

        Tags in Teams admin center are associated with the account signed in to the device, whereas Groups in the Teams Rooms Pro management portal are associated directly with the device. When you import a Tag, a corresponding Group is created containing the devices that are signed in with the accounts associated with that Tag.
    2. **Import**: Select Import to create Groups for all selected Tags.

## Minimum app version requirements

Make sure your devices are updated to the minimum Admin Agent version **AA 830** (**1.0.0.202606082157.product) or higher** (whichever is eligible for your devices) to be able to manage Android devices in Teams Rooms Pro Management portal. Please see latest Admin Agent releases [here](/en-us/microsoftteams/devices/certified-device-apps).

### Guidance for devices that remain offline for an extended period

For Microsoft-supported devices, if a device remains offline (powered off) for an extended period, Microsoft cannot automatically update it to the required Admin Agent version. In such cases, administrators are responsible for ensuring that the device is updated to the latest required Admin Agent version.

- **Devices with Admin Agent version 794 or later** Once the device is powered on and connected to the network, Microsoft's **[Zero-Day Update](/en-us/microsoftteams/rooms/zero-daydeviceupdates#teams-rooms-on-android-teams-panel--teams-phone)** mechanism automatically updates the device to the latest eligible Admin Agent version.
- **Devices with Admin Agent versions earlier than 794** Administrators must first manually update the device to a firmware version obtained from the OEM portal that includes **Admin Agent version 794 or later**. After the device is updated, powered on, and connected to the network, Microsoft's **Zero-Day Update** mechanism automatically updates the device to the latest eligible Admin Agent version.

Once the device is running the latest eligible Admin Agent version, administrators can provision it to the **Pro Management Portal (PMP)** using the standard PMP provisioning process.

### Guidance for devices with older Admin Agent versions

For Microsoft-supported devices, there are several scenarios in which a device may be running an older Admin Agent version. For example:

- The device was purchased from an OEM but remained unprovisioned and unused for an extended period.
- The device was factory reset, causing it to revert to the Admin Agent version included in the factory image.
- The device has not been updated for an extended period and is running an outdated Admin Agent version.

In these scenarios, administrators are responsible for ensuring that the device is updated to the required Admin Agent version before it can be fully managed in the **Pro Management Portal (PMP)**.

- **Devices with Admin Agent version 794 or later** Once the device is powered on and connected to the network, Microsoft's **Zero-Day Update** mechanism automatically updates the device to the latest eligible Admin Agent version.
- **Devices with Admin Agent versions earlier than 794** Administrators must first manually update the device to a firmware version available from the OEM portal that includes **Admin Agent version 794 or later**. After the device is updated, powered on, and connected to the network, Microsoft's **Zero-Day Update** mechanism automatically updates the device to the latest eligible Admin Agent version.

Microsoft is also working with OEM partners to provide firmware releases that include the required Admin Agent version. When available, administrators can install these firmware updates using OEM tooling to prepare their devices for management in the **Pro Management Portal (PMP)**.

### Guidance for devices that remain signed out for an extended period

For Microsoft-supported devices, if a device remains signed out for an extended period, Microsoft cannot automatically onboard the device to the **Pro Management Portal (PMP)**.

In such cases, administrators must sign in to the device at least once after it has been updated to the latest eligible **Admin Agent** version.

After the device is signed in, it can be onboarded and managed through the **Pro Management Portal (PMP)**.

### Guidance for devices which are end of life

There are some Teams Android Devices that were previously supported, but are now end of life, which you may still have in your environment. Microsoft will make the latest **Admin agent** version available which supports connectivity to the Pro Management Portal. However, since these are not supported, managability hasn't been tested and may not work as expected.

Those end of life devices are listed here:

- [Teams Rooms on Android - End of Life](/en-us/microsoftteams/devices/certified-hardware-android?tabs=eol)
- [Teams panels - End of Life](/en-us/microsoftteams/devices/teams-panels-certified-hardware?tabs=eol)
- [Teams phones - End of Life](/en-us/microsoftteams/devices/teams-phones-certified-hardware?tabs=eol)

## Specific feature availability in PMP

Here are the broad feature timelines. More details become available when feature rollouts begin.

| Area | Features | Public | GCCH | DoD | GCC |
| --- | --- | --- | --- | --- | --- |
| Android device inventory | Devices view for MTR-A and Panels | June 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Devices view for Teams Phones | June 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
| Android update management | Update management for MTR-A, Panels and Phones | June 2026 (completed) | August 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Tenant level pause | June 2026 (completed) | August 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Updates ring management | June 2026 (completed) | August 2026 (completed) | October 2026 (completed) | November 2026 |
| Android settings management | Individual device settings for MTR-A, Panels and Phones | June 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Setting templates for MTR-W, MTR-A, Panels and Phones | June 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Custom background for MTR-A and Panels | mid-October 2026 (completed) | October 2026 | October 2026 | November 2026 |
|  | Hotline setting for Phones | Mid-July 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Line keys for Phones | Mid-July 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Device lock pin for Phones | Mid-July 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
| Device Health signals and monitoring | Android signals for MTR-A, Panels, and Phones | June 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Incident management for Android | June 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
| Device Provisioning using MAC address | Device provisioning for MTR-A, Panels and Phones | Mid-July 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
| Tags as Groups in PMP | Import Tags as Groups in PMP | August 2026 (completed) | September 2026 (completed) | October 2026 (completed) | November 2026 |
| Other remote actions | Device restart | June 2026 (completed) | July 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Sign-in/ sign-out | June 2026 (completed) | August 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Device remove/ Unenroll | June 2026 (completed) | August 2026 (completed) | October 2026 (completed) | November 2026 |
|  | Collect logs | June 2026 (completed) | August 2026 (completed) | October 2026 (completed) | November 2026 |
| Bulk actions | For Restart, Remove and Sign-out | August 2026 (completed) | September 2026 (Completed) | October 2026 (Completed) | November 2026 |
| SIP device management | SIP devices view | June 2026 (completed) | September 2026 (completed) | NA | November 2026 |
|  | SIP device remote actions | June 2026 (completed) | September 2026 (completed) | NA | November 2026 |
|  | SIP device provisioning | September 2026 (completed) | September 2026 (completed) | NA | November 2026 |

## Resources

- See the Pro Management portal overview at: [Teams Rooms Pro Management | Microsoft](https://www.youtube.com/watch?v=HTUg-7aDKiU&amp;list=PLyhj1WZ29G65glMRLXqtlq7DGBvXg-TnT&amp;index=6)
- Learn more about Pro Management portal features [with these short YouTube videos](https://www.youtube.com/playlist?list=PLyhj1WZ29G65glMRLXqtlq7DGBvXg-TnT)
- Find product documentation at: [Microsoft Teams Rooms Pro management](/en-us/microsoftteams/rooms/rooms-pro-management)
- Transitioning Teams Android Device Management from Teams Admin Center to the Teams Rooms Pro Management Portal - [Webinar](https://www.youtube.com/watch?v=0qEDWvwhBbs)

## Frequently Asked Questions

#### Do I need to manually migrate my devices?

> 
> No. Devices automatically appear in the Pro Management portal when Android device management reaches general availability. Make sure the required URLs are allowlisted and devices are on AA 830 version.

#### Will Teams device management in TAC stop working immediately?

> 
> No. The deprecation of device management capabilities is planned to happen gradually. You will receive advance communication before any workflows are deprecated.

#### Will my existing configurations and policies move to PMP?

> 
> Yes. Device management capabilities transition with equivalent or enhanced functionality. Detailed guidance to be provided before migration milestones.

#### Do I need a new license?

> 
> The current access to PMP is included with Teams Rooms and Teams shared device licensing. Additional guidance to be provided if any licensing scenarios require attention.

#### Can I continue using the device management capabilities in TAC during the transition?

> 
> Yes. The device management in TAC remains available during the transition period. Some workflows may redirect to PMP as features become available.

#### What happens if my organization has never used PMP?

> 
> Admins can begin accessing PMP now to prepare. Enrollment guidance and readiness documentation are available.

#### Where should I look for the latest updates?

> 
> This article and MC post is continuously updated with rollout status, migration steps, and timelines.

#### What is the deadline to migrate from TAC to PMP?

> 
> The phased deprecation of the device management features in TAC will begin in October 2026 and is expected to be completed by the end of October 2026.

#### How does the Teams Rooms Pro management portal simplify Microsoft Teams administration compared to the Teams Admin Center?

> 
> The Teams Rooms Pro Management Portal provides a consistent, proactive, and reliable device management experience:
> 
> 1. Unified device management – Provides management parity across Teams Rooms on Windows and Teams Rooms on Android, enabling administrators to manage both platforms through a consistent experience.
> 

1. Proactive incident management – Helps administrators identify and address device issues proactively through alerts and incident management, reducing the need for manual monitoring.
2. Flexible access and update controls – Enables custom RBAC for more granular administrator permissions and custom update rings for greater control over how and when device updates are deployed.
3. Faster, more reliable device communication – Provides improved device-to-portal communication, enabling management actions and device data to flow more quickly and reliably.

#### When will all the device management features be available in PMP?

> 
> Refer to this article for release timelines per feature and their availability in all the clouds.

#### Any chance the URL for PMP will be changed to be consistent with other m365 admin portals?

> 
> The PMP URL will remain unchanged as part of this transition. If there are plans to change the URL in the future, we will communicate the change in advance.

#### What are the must-have prerequisites before Android-based Teams devices are fully manageable in Pro Management Portal?

> 
> For more information, see #migration-checklist-and-pre-requisites section.

#### Why are actions like Remove, Restart sometimes in disabled state for Android devices?

> 
> As mentioned in the #migration-checklist-and-pre-requisites section, Android devices must be connected to IoTHub to be fully manageable from Teams Rooms Pro management portal. If a device is not connected to IoThub, actions such as Remove and Restart are disabled.

#### How will configuration profiles work with PMP for Android devices?

> 
> If you wish to carry over the existing configuration profiles in Teams admin center, you can import them as **Settings Templates** in the Teams Rooms Pro Management portal. For more information, see [Microsoft Teams Rooms Pro management](/en-us/microsoftteams/rooms/pro-portal-settings).