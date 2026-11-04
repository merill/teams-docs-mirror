---
layout: Conceptual
title: Plan for Operator Connect for India - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/operator-connect-india-plan
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: pavellatif
ms.author: pavellatif
manager: roykuntz
ms.date: 2026-08-07T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
ms.reviewer: roykuntz
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn more about Operator Connect for India, such as requirements and planning for deployment.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
locale: en-us
document_id: 7bf9215f-0c26-cb14-6992-70b263f14f30
document_version_independent_id: 7bf9215f-0c26-cb14-6992-70b263f14f30
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/operator-connect-india-plan.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: operator-connect-india-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/operator-connect-india-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 52bbc28c-d833-4882-f0b6-b56b94d21646
---

# Plan for Operator Connect for India - Microsoft Teams | Microsoft Learn

Operator Connect for India is a country-specific PSTN connectivity option for Teams Phone. It connects your tenant to an Indian telecommunications operator and is designed to meet India's telephony regulatory requirements. Use this article to plan licensing, choose the appropriate number type, and understand the client and device requirements before you deploy Operator Connect for India.

## Prerequisite knowledge

- [PSTN connectivity options](pstn-connectivity)
- [Operator Connect as a PSTN connectivity option](operator-connect-plan)

## Licensing and deployment requirements

You can integrate Indian telephone numbers into your tenant through Microsoft's *Operator Connect for India* solution. Unlike Operator Connect in other countries or regions, the India operator provides the India-specific Teams Phone license.

- **Acquire the India-specific Microsoft Teams Phone license from a licensed Indian telecommunications operator.** This requirement applies even if the user already has a Teams Phone entitlement, such as the entitlement included with an E5 license.
- The India Teams Phone license supports both wireline and wireless numbers.
- Users assigned Operator Connect for India numbers must be in **TeamsOnly** mode. The entire organization doesn't need to be in TeamsOnly mode. To learn more, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability).
- Operator Connect for India supports the entitlement model for [Teams Phone Resource Account licenses](teams-add-on-licensing/virtual-user). You can assign Operator Connect for India numbers to resource accounts for Auto attendants and Call queues. These resource accounts don't require the India Teams Phone license. For more information, see [Plan overview for Teams Phone Agent, Auto attendants, and Call queues](aa-cq-plan-overview).
- Operators can provide service numbers, including toll and toll-free numbers, for services such as Auto attendants and Call queues. Service numbers support more concurrent calls than user numbers. Contact your operator to obtain service numbers.

## Choose a wireline or wireless number

Indian telecommunications regulations classify telephone numbers as **wireline** or **wireless**. The number type determines where the number can be used and which location control applies.

### Wireline numbers

Wireline numbers require you to be at the assigned network site when using the number to access the PSTN. When you use India wireline numbers, you must configure Location-Based Routing (LBR) and associate each number with the appropriate network site.

For more information, see [Plan and configure Location-Based Routing for Operator Connect for India](location-based-routing-india-plan).

Important

LBR for wireline numbers uses your Teams network topology, including trusted IP addresses, subnets, and network sites, to determine whether the endpoint is at the network site associated with the number. PSTN calls from an unknown or different site aren't allowed. Operating system location services don't replace this LBR configuration.

### Wireless numbers

Wireless numbers allow users to roam within India. The location check depends on the client or device: location-capable Teams clients share their current operating system location, while supported Teams IP phones and Teams Rooms use the static emergency address assigned to the user account. For a common area phone or Teams Room, the user account is a resource account. Location-Based Routing (LBR) is required for wireline numbers only. Wireline network-site associations aren't used for the wireless desk-device flow.

#### Location sharing for Teams clients

For Teams desktop and mobile clients that use operating system location services:

1. Turn on location services in the device's operating system and allow Teams to access the device's location. On Windows, go to **Settings &gt; Privacy & security &gt; Location**, turn on **Location services** and **Let apps access your location**, and allow **Microsoft Teams**. On macOS, go to **System Settings &gt; Privacy & Security &gt; Location Services** and allow **Microsoft Teams ModuleHost** and **Microsoft Teams WebView**.
2. In Teams, go to **Settings &gt; Privacy &gt; Location** and follow the location consent prompt. Select the option that allows Teams to use location for calling, usually **Allow all**. The **Keep emergency only** or emergency-only option restricts location use to emergency calling and doesn't provide the location sharing required for India wireless PSTN calling.
3. If the user denies consent or later turns off location access, PSTN calling isn't available and Teams might not show the dial pad. Re-enable location access, reopen Teams, and try again.

On organization-managed Windows devices, an administrator might control operating system location settings, so users might not see a consent prompt. Make sure the device management policy allows Teams to access location.

Important

**Location detection requirements for Location-Based Routing (wireline numbers)**

For users assigned India wireline numbers with Location-Based Routing (LBR) enabled, Teams requires that the user's geographic location be detected **automatically** by the operating system (for example, via GPS, Wi-Fi positioning, or network-based detection).

If Windows falls back to a manually configured "default" location (position source = Default), Teams intentionally strips the geo coordinates to prevent LBR compliance bypass. When this occurs:

- The user's location can't be verified against their assigned network site.
- **PSTN calling is disabled** until a valid, automatically-detected location is available.
- The Calls app might hide the dial pad and display a banner stating PSTN calling isn't available.

**Common causes of fallback to default location:**

- Corporate network configurations (for example, Zscaler, VPN, or proxy) that interfere with network-based location detection
- Virtual machine or remote desktop environments without GPS or Wi-Fi hardware
- Windows Location Services disabled or Teams not permitted to access location at the OS level

**Recommended actions for IT admins:**

- Ensure Windows Location Services are enabled and Microsoft Teams is permitted to access location in **Settings &gt; Privacy & security &gt; Location**.
- Verify that corporate proxy or security appliances (such as Zscaler) don't block network-based location detection.
- Test PSTN calling from the affected network. Users who can place calls off-corpnet but not on-corpnet likely have a network detection issue.

This behavior is by design to maintain India regulatory compliance. Teams can't rely on manually set locations for LBR enforcement because they can be spoofed.

For more information, see [User location consent experience in Microsoft Teams](privacy/user-location-data), [Manage location sharing in Microsoft Teams](https://support.microsoft.com/teams/notifications-settings/manage-location-sharing-in-microsoft-teams), and [Windows location service and privacy](https://support.microsoft.com/Windows/privacy/windows-location-service-and-privacy).

Location data might be shared with the Operator Connect for India partner to enable PSTN calling. Microsoft doesn't store or retain this location data.

#### Wireless support for Teams IP phones and Teams Rooms

India wireless numbers are supported on eligible Teams IP phones, including common area phones, and Microsoft Teams Rooms. This service-side capability is enabled for all production tenants. Some desk devices can't provide location through the Teams client, so these devices use the static emergency address assigned to the user account that signs in to the device instead of the location-sharing flow described above. For a common area phone or Teams Room, this user account is a resource account. Before using this flow, assign an emergency location in India to the user account. If the assigned emergency location is in India, the call can proceed, subject to the other Operator Connect for India checks. This wireless desk-device flow doesn't use network sites, subnets, or other network topology configuration.

For Teams IP phones, support is limited to the common-area and meeting-room experiences. The IP phone policy [SignInMode parameter](/en-us/powershell/module/teams/new-csteamsipphonepolicy#parameters) must be set to `CommonAreaPhoneSignIn` for a common area phone or `MeetingSignIn` for a meeting room. Teams IP phones signed in with `UserSignIn` aren't supported for India wireless numbers. For information about creating and assigning an emergency location, see [Manage emergency locations for your organization](add-change-remove-emergency-location-organization). For more information about device sign-in modes, see [Plan device deployment for Teams phones](phones/plan-device-deployment) and [Set up common area phones for Microsoft Teams](phones/set-up-common-area-phones).

#### Examples

- **Teams client:** A user with an India wireless number can make PSTN calls while working from different locations in India after granting Teams the required location permissions. If the user denies location sharing, the dial pad isn't available for PSTN calling.
- **Teams IP phone:** A common area phone with an India wireless number can make PSTN calls when its IP phone policy uses `CommonAreaPhoneSignIn` and its user account has an emergency location in India. A Teams IP phone using `UserSignIn`, or a user account without an in-country emergency location, can't use this wireless-number flow.
- **Teams Room:** A Teams Room using `MeetingSignIn` can use an India wireless number when its resource account has an emergency location in India.

For wireline LBR concepts, network-site configuration, and call outcomes, see [Plan and configure Location-Based Routing for Operator Connect for India](location-based-routing-india-plan) and [Configure network settings for Location-Based Routing in India](location-based-routing-configure-network-settings-india). Those articles apply to wireline numbers and aren't required for the wireless desk-device flow described here.

Wireless numbers aren't integrated with a user's mobile phone SIM, and Teams Phone Mobile isn't currently supported in India.

### Number type and access controls

Operator Connect for India automatically applies PSTN access and toll-bypass controls based on the number type supplied by the operator.

| Number type | PSTN access and roaming | Location information used |
| --- | --- | --- |
| Wireline | PSTN access is allowed only when the user is at the network site associated with the number. | [Location-Based Routing](location-based-routing-india-plan) |
| Wireless | Users can roam within India. Location-capable clients must provide an in-country location. Supported desk devices must have an India emergency location assigned to the user account. | Current operating system location for location-capable clients; static emergency address assigned to the user or resource account for supported Teams IP phones and Teams Rooms. |

Important

Wireline and wireless numbers aren't interchangeable. When ordering numbers, tell your Indian telecommunications operator which type of service you need for each number.

## Client and device limitations

- For prerequisites and location behavior on supported clients and devices, see Wireless numbers.
- The Teams web client doesn't support PSTN calling for Operator Connect for India wireless numbers because it can't provide the location services required for compliance.
- Custom clients developed with the Azure Communications Services client SDK don't support Operator Connect for India wireless numbers.
- SIP devices, including SIP Device Hub devices, aren't supported for Operator Connect for India wireless numbers.
- Teams IP phones that use the `UserSignIn` value of the IP phone policy `SignInMode` parameter aren't supported for the wireless desk-device flow.
- You can't convert a wireline number to a wireless number.

## Other Service Provider (OSP) deployments

India has a regulated deployment category called **Other Service Provider (OSP)**. OSP deployments can allow calls to egress India through a private network instead of using India PSTN toll. OSP deployments are typically used for call centers, and the customer must obtain the required entitlement from India's Department of Telecommunications.

This article describes a non-OSP deployment that follows India toll regulations. Microsoft support for OSP calls with international telephone numbers is pending.

## Support boundaries

Contact your Operator Connect for India operator first for technical support. If the operator determines that the issue is with Microsoft, they can ask you to open a Microsoft support case with the results of their investigation. The operator can also escalate the issue through its Microsoft support channel. Microsoft might reject a support case if the investigation shows that the operator can address the issue.