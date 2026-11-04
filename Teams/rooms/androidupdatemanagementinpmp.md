---
layout: Conceptual
title: Transitioning updates management for Teams Android devices from Teams Admin Center to the Teams Rooms Pro Management Portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/androidupdatemanagementinpmp
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Summary document describing how to manage updates for Android devices in new pro management portal from TAC
author: Vapati
ms.author: vapati
ms.service: skype-for-business-online
ms.topic: how-to
ms.date: 2026-06-26T00:00:00.0000000Z
ms.manager: srpall
manager: srpall
locale: en-us
document_id: fb72b963-651f-c912-a216-c142ca1566b1
document_version_independent_id: 5de26e2f-f97c-cac2-25a8-25326cca5a73
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/androidupdatemanagementinpmp.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/androidupdatemanagementinpmp
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/androidupdatemanagementinpmp.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6f38d9e4-458e-b816-fcd6-5931fd8563da
---

# Transitioning updates management for Teams Android devices from Teams Admin Center to the Teams Rooms Pro Management Portal - Microsoft Teams | Microsoft Learn

Guidance for Teams device admins on transitioning update management capabilities for Teams Android devices from the Teams admin center (TAC) to the Teams Rooms Pro Management portal (PMP).

## Overview: what is changing

Management of Teams Android devices is moving from the Teams admin center (TAC) to the Teams Rooms Pro Management portal (PMP). PMP will become the primary destination for administrators to manage Teams Rooms on Android, Teams phones, Teams panels, and related update workflows.

This guide explains what administrators need to know about the update management experience for Teams Android devices in PMP, including:

- Where to find update management settings and controls
- How automatic and forced updates work
- How TAC auto-update phases map to PMP update rings
- Changes to update management behavior during the transition from TAC to PMP.

## Transition timeline and key dates

The transition period begins at **general availability (GA)** and continues until the [**deprecation of update management in TAC**](aboutunifieddevicemanagement-pmp1).

During the transition period:

1. Auto-updates managed through PMP continue to follow the update cadence defined by TAC auto-update phases until you explicitly confirm that you want to manage updates using PMP rings.
2. Devices assigned to the **Validation**, **General**, and **Final** phases in TAC continue to receive automatic updates within **0–15 days**, **16–45 days**, and **46–60 days**, respectively.
3. When you explicitly confirm update management through PMP, a one-time mapping assigns your devices to the corresponding default PMP update rings.
4. After confirmation, administrators can no longer manage automatic updates through TAC. **This action cannot be reversed.**

For more information about explicitly confirming PMP for update management and the resulting changes to automatic update behavior, see the following sections.

Note

If automatic updates are disabled for your entire tenant in TAC (for example, due to backend-imposed restrictions), they will remain disabled in PMP. In this scenario, you must continue to update devices manually, as you do today. There is no service disruption and no change in update behavior for these tenants.

## Before you begin

- Review the [guide to transition Teams Android Device Management from Teams Admin Center to the Teams Rooms Pro Management Portal](aboutunifieddevicemanagement-pmp1) before you use PMP for Android device updates.
- Confirm that your Android Teams devices are visible in PMP.
- **Recommended**: Use PMP as the primary portal for update management once your devices are connected to and managed in PMP.

#### Supported Android device types

- Teams Rooms on Android (MTR-A)
- Teams panels
- Teams phones

## Where to manage Android updates in PMP

### For a single device

Open the device details page and use the **Updates** tab to view available updates and trigger a manual update.

1. Sign in to **PMP**.
2. Go to **Rooms** or **Phones**.
3. Select the device.
4. Open the **Updates** tab.

Admins can see the different types of updates available for a given device, install them, and view update history on the device.

### For multiple devices

Use the Android update management experience to monitor rollout progress and manage update versions across rings.

1. Sign in to **PMP**.
2. Select **Updates** &gt; **Update management** &gt; **Android updates** to view update rollouts for all eligible Android devices.

Admins can forcefully install particular update on multiple eligible devices by selecting them.

## Key update management capabilities

Updates for Teams Android devices are installed on devices in the same way as [updates for Windows Rooms in PMP](update-management), and Update Rings allow administrators to control when different devices receive a particular update.

1. **Rollout behavior:** Updates in PMP are automatically rolled out to all devices (including Android) as defined by corresponding update ring cadence. The details documentation on update rollout behavior in PMP is already [explained here.](update-management#how-updates-get-deployed)
2. **Updates States:** Each update is associated with update State. Update state defines the current state of update eg: whether it is installed, in-progress, paused etc. The updates states available in PMP are [explained here.](update-management#update-states)
3. **Visibility and Control:** Automated updates in Pro Management orchestrate updates throughout your organization. However, you have the visibility and control to intervene if needed. The behavior is [explained here.](update-management#controlling-updates)
4. **Update Rings:** Rings are used to reduce the risk of issues derived from the installation of the updates. This is done by gradually deploying the update to the entire site. Details on how to setup and manage update rings in PMP is [explained here.](update-management#update-rings) Admins can [define rollout timeline](update-management#specifying-rollout-timeline) for each ring or [create custom rings](update-management#creating-custom-rings) and based on their rollout plans [assign rooms to these rings.](update-management#assign-rooms-to-rings)
5. **Nightly maintenance window for updates:**

    - All auto-updates for Android devices occur only during the predefined nightly maintenance window defined for PMP, between **12 AM and 5 AM device local time**.
    - If a nightly device reboot is scheduled, updates are pushed to the device after the reboot.
6. **Synced updates for paired devices:**

    - PMP supports coordinated app updates for paired devices. If a front-of-room (FOR) device is paired with a touch console (TC), scheduling an app update on FOR will also update the paired console to the same app version, if eligible.
    - Co-ordinated firmware updates are facilitated directly by OEMs, if eligible.
7. **Non-disruptive updates:**

    - Updates will be installed on devices in a non-disruptive manner. If the device is busy, update request will be postponed until device is free.
8. **Pause updates:**

    - **Pause or resume a specific version across all eligible devices**
    - You can pause and resume the rollout of an individual update version at **Updates** &gt; **Update management** &gt; **Android updates** by selecting each version. This works the same way as pausing updates for Windows devices in PMP. [Learn more about controlling updates](update-management#controlling-updates).
    - *Roles & permissions required:* Any admin having role with 'Global - Grant all' permission should be able to set/resume this pause. Global administrator and Teams administrator role have these permissions by default.
    - **Pause or resume updates for all Android devices across the entire tenant**

        - In order to do so, go to **Updates** &gt; **Update management** &gt; **Android updates** and click on **Pause updates** action. All auto-update rollouts for entire fleet of Android devices in your tenant will be paused for 2 weeks.
        - Admins can **Resume updates** from same page at any time. After 2 weeks, updates will auto-resume and updates rollout will restart automatically.

Important

If you had already configured a tenant-wide update pause in TAC before general availability (GA), PMP will continue to honor that existing configured pause duration (and expiry date) until it expires. This is a one-time migration of the tenant-level pause setting from TAC to PMP during GA.

After this one-time migration:

- Any new tenant-level pause actions must be configured in PMP.
- Any requests to resume updates must also be performed in PMP.
- Tenant-level pause actions configured in TAC will be deprecated and will no longer affect automatic updates managed through PMP update rings. **This deprecation takes effect immediately when update management capabilities become generally available in PMP.**

## Moving Android updates from auto-update phases in TAC to [rings in PMP](update-management#update-rings)

As Android device management in PMP becomes **generally available (GA)**, administrators are expected to manage updates for their Teams Android devices through PMP.

The transition from TAC to PMP introduces several changes to the update management experience. The following sections highlight these changes and provide guidance to help administrators prepare for the transition and effectively manage updates in PMP.

Important

PMP update rings and TAC auto-update phases use different update deployment systems. Rollout timelines vary between the two systems, and the ability to create and manage custom update rings is available only in PMP.

**As part of general availability (GA),**

- Auto-updates via Teams admin center are stopped as of now (see an exception for Admin Agent on Android devices below).
- By default, automatic updates for Android devices are managed through PMP only. However, to avoid any disruption, auto-update rollouts for Android devices will continue to follow auto-update phases and corresponding rollout durations defined as in TAC.
- If admins wish to pause any automatic update, they have to use PMP.

**If admins prefer to use PMP update rings for auto-update rollout,**

- Admins have to explicitly provide confirmation to use PMP update rings (see steps below).
- This confirmation is **irreversible**. Once you confirm the transition to use PMP rings, any changes to auto-update phases in TAC will not have any effect on updates managed via PMP rings.
- Once device management experience in TAC is deprecated starting September ([see timelines here](aboutunifieddevicemanagement-pmp1)), Teams Android devices will be by default updated as per rings defined in PMP.

**For Teams Android devices**, management of updates through PMP requires minimum required Admin Agent version **830**[(](/en-us/microsoftteams/devices/certified-device-apps)**[1.0.0.202606082157](/en-us/microsoftteams/devices/certified-device-apps)**[)](/en-us/microsoftteams/devices/certified-device-apps) or later (see here). Thus -

- Teams Android devices running a lower version of Admin Agent than **830**[(](/en-us/microsoftteams/devices/certified-device-apps)**[1.0.0.202606082157](/en-us/microsoftteams/devices/certified-device-apps)**[)](/en-us/microsoftteams/devices/certified-device-apps) will continue to receive Admin Agent updates via TAC only.
- All other app or firmware updates on these phone devices will be paused until they update to minimum required Admin Agent version **830**[(](/en-us/microsoftteams/devices/certified-device-apps)**[1.0.0.202606082157](/en-us/microsoftteams/devices/certified-device-apps)**[)](/en-us/microsoftteams/devices/certified-device-apps) or later. (Remember, updates for all other apps and firmwares are already stopped in TAC)
- Once updated to minimum required Admin Agent version 830 or later, auto-updates for Android devices for all apps and firmwares will be managed via PMP rings only.

**To manage all your Teams Android devices in PMP, Microsoft *strongly recommend* updating your devices to minimum required Admin Agent version 830 or later ASAP (see here)**.

1. During the TAC to PMP transition (defined as per above timelines), auto-updates in PMP follow the cadence defined by TAC auto-update phases until you explicitly confirm to use PMP rings.
2. Admins can provide this explicit confirmation in PMP as below:
    1. Sign in to **PMP**.
    2. Select **Updates** &gt; **Ring Configuration** &gt; **Rings** and **Provide Confirmation** on *Action required to manage auto-updates for Android in Pro Management Portal.*
    3. Once confirmed, auto-updates for Android devices will be managed through Pro management portal. This confirmation is irreversible and admins will not be able to manage updates via TAC.

Warning

This confirmation is **irreversible**. Once you confirm the transition to use PMP rings, any changes to auto-update phases in TAC will not have any effect on updates managed via PMP rings. Admins must manage their auto-updates using PMP rings (see an exception for Admin Agent on Android devices above)

To avoid any potential disruption, it is strongly advised to upgrade your Teams Android devices to minimum required Admin Agent 830 or higher (see here).

1. Once you confirm, a one-time mapping of devices from TAC auto-update phases to rings in PMP takes place as below :

    - All **MTR-A, panels, and touch console** devices will be mapped from the Validation, General, and Final phases in TAC to the default corresponding Staging, General, and Executive rings in PMP.
    - All **phones** irrespective of their current auto-update phases in TAC, will be mapped to default General ring in PMP. (except for phones which are on Admin Agent version &lt; 830 which will continue to be updated via TAC until TAC is deprecated or Admin Agent is updated to &gt; 830).
    - Any new phone devices that are updated to 830 will also get mapped to 'General' ring in PMP, irrespective of their update phase in TAC.
    - After the one-time mapping of devices to PMP rings, all devices follow the update duration as defined by their PMP rings.
    - You can adjust the auto-update rollout to suit your preferences either by moving around devices in different PMP ring or by changing the ring configurations.
    - For customers who are using PMP first time to manage updates for their devices, TAC auto-update phases map to PMP rings as below by default. Learn more about PMP update rings [here.](update-management#update-rings)

    | Phase (TAC) → Ring (PMP) | PMP ring duration (default) | TAC phase duration |
    | --- | --- | --- |
    | Validation → Staging | 0–6 days | 0–15 days |
    | General → General | 7–13 days | 16–45 days |
    | Final → Executive | 14–20 days | 46–60 days |

Caution

As per default mapping explained above, updates in PMP will roll out faster than in TAC. Adjust your auto-update ring durations as soon as you start managing devices through PMP to avoid an unexpectedly fast rollout.

## Minimum app version requirements

Make sure your devices are updated to the minimum Admin Agent version **830**[(](/en-us/microsoftteams/devices/certified-device-apps)**[1.0.0.202606082157](/en-us/microsoftteams/devices/certified-device-apps)**[)](/en-us/microsoftteams/devices/certified-device-apps) or higher (whichever is eligible for your devices) to be able to manage Android devices in Teams Rooms Pro Management portal. Please see latest Admin Agent releases [here](/en-us/microsoftteams/devices/certified-device-apps).

Important

**Admin Agent update readiness** Microsoft will **accelerate deployment of the minimum Admin Agent version** to Android devices, so they are ready to be managed in the Teams Rooms Pro Management portal as soon as possible. This means, Admin Agent on your devices will get updated at faster cadence than duration configured via update rings.

Customers who have disabled auto updates permanently will have their devices **forcefully auto-updated to the minimum Admin Agent version** before the deprecation of device management capabilities in TAC to avoid any disruption.

Customers who don't have auto update available (specially devices on very old version of Admin Agent) should manually update their devices to the minimum Admin Agent version before the deprecation of device management capabilities in TAC to avoid any disruption.

Government cloud customers (GCC, GCC-High, DoD) will soon have their devices auto-updated to minimum required Admin Agent version **AA 856**[(**1.0.0.202607160723**)](/en-us/microsoftteams/devices/certified-device-apps) before the deprecation of device management capabilities in TAC to avoid any disruption.

These Admin Agent updates to minimum required Admin Agent for successfully managing their devices PMP are **NOT PAUSABLE** and are mandatory to manage your devices in PMP successfully.

After the deprecation, admins will no longer be able to update these devices from TAC and may need to use the OEM portal to update firmware with required Admin Agent before the devices can be managed in PMP again.

**To ensure uninterrupted device management in PMP, it is strongly recommended that you update your devices to the minimum required Admin Agent version as soon as possible (manually or via auto-updates). Failure to do so may result in disruptions to device operations.**

#### Verify available updates and updates history

1. **For MTR-A and Panel devices:**
    - Admins will be able to see only updates that are available or completed as soon as Android updates management goes GA in PMP.

        Any historical updates that happen before GA in PMP via TAC, can only be in TAC updates activity/history.
2. **For Teams Phones:**
    - Admins will be able to see available and historical updates for only phone devices which are on Admin Agent &gt; 830 and if their tenant have provided explicit confirmation to manage updates via PMP. Historical updates happened via TAC for phone devices will not be visible in PMP.

## Device type specific updates guidance

#### Teams phones

1. Admins will not be able to see phones or their historical updates happened in TAC on PMP unless they are updated to minimum required Admin Agent 830 or later. Once updated, only subsequent updates history will be visible in PMP.
2. For Teams phone devices on Admin Agent version lower than 830, Admin Agent update will be pushed via TAC and admins will not be able to pause those Admin Agent updates in TAC.
3. Unless Admin Agent is updated to 830 or later, Teams phone devices will not receive any app or firmware updates.

## Updates guidance for government cloud customers

**This guidance applies to GCC, GCC-High, and DoD cloud customers.**

Important

**Minimum Admin Agent update readiness**

Make sure your devices are updated to the minimum Admin Agent version **856** (**1.0.0.202607160723**) or higher (whichever is eligible for your devices) to be able to manage Android devices in Teams Rooms Pro Management portal. Please see latest Admin Agent releases here.

Government cloud customers (GCC, GCC-High, DoD) will soon have their devices auto-updated to minimum required Admin Agent version **856** (**1.0.0.202607160723**) before the deprecation of device management capabilities in TAC to avoid any disruption.

These Admin Agent updates to minimum required Admin Agent for successfully managing their devices in PMP are **NOT PAUSABLE** and are mandatory to manage your devices in PMP successfully.

After the deprecation, admins will no longer be able to update these devices from TAC and may need to use the OEM portal to update firmware with the required Admin Agent before the devices can be managed in PMP again.

To ensure uninterrupted device management in PMP, it is strongly recommended that you update your devices to the minimum required Admin Agent version as soon as possible (manually or via auto-updates). Failure to do so may result in disruptions to device operations.

If you do not start managing updates for your Android devices in PMP before deprecation of the corresponding experience in TAC (see migration timeline), you might lose updates management capability for your devices from Microsoft.

To facilitate this faster and avoid disruption, Microsoft may install the latest Admin Agent on your devices in an accelerated manner as an exception to the regular auto-update cadence.

As soon as Android updates management goes live in PMP for your cloud, updates management in PMP will work in the same way as public cloud customers as described above. See the migration timeline for availability dates.

## Guidance for devices that remain offline for an extended period

For Microsoft-supported devices, if a device remains offline (powered off) for an extended period, Microsoft cannot automatically update it to the required Admin Agent version. In such cases, administrators are responsible for ensuring that the device is updated to the latest required Admin Agent version.

- **Devices with Admin Agent version 794 or later** Once the device is powered on and connected to the network, Microsoft's **Zero-Day Update** mechanism automatically updates the device to the latest eligible Admin Agent version.
- **Devices with Admin Agent versions earlier than 794** Administrators must first manually update the device to a firmware version obtained from the OEM portal that includes **Admin Agent version 794 or later**. After the device is updated, powered on, and connected to the network, Microsoft's **Zero-Day Update** mechanism automatically updates the device to the latest eligible Admin Agent version.

Once the device is running the latest eligible Admin Agent version, administrators can provision it to the **Pro Management Portal (PMP)** using the standard PMP provisioning process.

## Guidance for devices with older Admin Agent versions

For Microsoft-supported devices, there are several scenarios in which a device may be running an older Admin Agent version. For example:

- The device was purchased from an OEM but remained unprovisioned and unused for an extended period.
- The device was factory reset, causing it to revert to the Admin Agent version included in the factory image.
- The device has not been updated for an extended period and is running an outdated Admin Agent version.

In these scenarios, administrators are responsible for ensuring that the device is updated to the required Admin Agent version before it can be fully managed in the **Pro Management Portal (PMP)**.

- **Devices with Admin Agent version 794 or later** Once the device is powered on and connected to the network, Microsoft's **Zero-Day Update** mechanism automatically updates the device to the latest eligible Admin Agent version.
- **Devices with Admin Agent versions earlier than 794** Administrators must first manually update the device to a firmware version available from the OEM portal that includes **Admin Agent version 794 or later**. After the device is updated, powered on, and connected to the network, Microsoft's **Zero-Day Update** mechanism automatically updates the device to the latest eligible Admin Agent version.

Microsoft is also working with OEM partners to provide firmware releases that include the required Admin Agent version. When available, administrators can install these firmware updates directly from the OEM portal to prepare their devices for management in the **Pro Management Portal (PMP)**.

## Guidance for devices that remain signed out for an extended period

For Microsoft-supported devices, if a device remains signed out for an extended period, Microsoft cannot automatically onboard the device to the **Pro Management Portal (PMP)**.

In such cases, administrators must sign in to the device at least once after it has been updated to the latest eligible **Admin Agent** version.

After the device is signed in, it can be onboarded and managed through the **Pro Management Portal (PMP)**.

## Guidance for unsupported or end of live devices

Some Teams Android devices that were previously supported are now end of life but may still be present in your environment. While Microsoft will make every effort to automatically update these devices to the latest **Admin Agent version**, they are no longer officially supported. As a result, administrators are responsible for ensuring these devices are updated to the required **Admin Agent version**.

Those legacy devices are listed here:

- C450hd
- C448hd
- rxv80
- UC-P8
- UC-P8-I
- UC-P8-C
- UC-P8-C-I
- UC-P10
- UC-P10-I
- UC-P10-C
- UC-P10-C-I
- UC-P8-TD
- UC-P8-TD-I
- UC-P10-TD
- UC-P10-TD-I
- UC-2
- UC-2-I
- expandvision3t
- ExpandControl3P
- CD-18781Y-K
- LenovoCD-18781Y
- lenovocd-18781y-s
- Trio8800
- trio8500
- CP960
- T55
- T55A
- T56
- T56A
- T58
- T58A
- VC210
- VP59
- MP52
- ThinkSmartViewPlus
- nf21f1
- deskvisiona24

## Frequently asked questions

#### What types of updates can I manage from PMP for Android devices?

> 
> All firmware and app updates that are supported in TAC are also supported in PMP for managing updates.

#### Can I manually force update single device?

> 
> Yes

#### Can I manually force update multiple devices at once?

> 
> Yes, for a given version, PMP already supports updating multiple devices at once (similar to Windows devices). Select an update that needs to be pushed to multiple devices, click on it, select force update and then select multiple devices where given update needs to be pushed.

#### Does PMP support custom maintenance window for Android device updates?

> 
> No, PMP does not let admins configure a custom maintenance window for device updates. As explained earlier, all updates happen only during the predefined nightly maintenance window defined for PMP, between **12 AM and 5 AM device local time**.

#### Where can is see all the updates available for Teams Android devices?

> 
> You can see all Android updates in Pro Management Portal (PMP) under **Updates** &gt; **Update Management** &gt; **Android updates**.

#### Can I still apply updates from TAC manually?

> 
> Yes, until the TAC device management experience is deprecated completely, admins can still apply manual updates via TAC. However, Auto-updates are disabled via TAC (except for minimum required Admin Agent which is essential for PMP connectivity). Auto-updates are happening only via PMP.

#### Can admins still pause updates via TAC?

> 
> No. Admins cannot pause auto-updates via TAC anymore. All auto-updates are being facilitated by PMP only. Admins are advised to use pause capability from PMP since we GA'd updates management in PMP (starting July).

#### Are auto-update ring durations in PMP the same for Windows and Android devices?

> 
> Yes, auto-update rings are common for all devices in PMP. The ring configuration applies the devices, which are configured to be part of those rings (irrespective of whether those are Android or Windows based).

#### Can admins manage app/firmware updates for SIP devices via PMP?

> 
> No, updates for SIP devices are neither supported in TAC or PMP.

#### Is there any training available for admins to understand updates experience in PMP?

> 
> Yes, you can refer to https://aka.ms/PMPAndroidMgmt.