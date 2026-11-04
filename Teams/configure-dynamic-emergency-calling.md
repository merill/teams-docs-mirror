---
layout: Conceptual
title: Configure dynamic emergency calling - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/configure-dynamic-emergency-calling
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: pavellatif
manager: roykuntz
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
ms.reviewer: roykuntz
ms.date: 2026-09-23T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn how to configure the Teams Phone dynamic emergency calling feature.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 358dfc73-9414-13e2-4682-c3e82603692f
document_version_independent_id: 3faae1d9-efbe-c20c-6598-a5073c2306e2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/configure-dynamic-emergency-calling.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-dynamic-emergency-calling
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/configure-dynamic-emergency-calling.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 12924534-5265-39f7-d6a0-f149e7c8f97b
---

# Configure dynamic emergency calling - Microsoft Teams | Microsoft Learn

Dynamic emergency calling for Microsoft Calling Plans, Operator Connect, Teams Phone Mobile, and Direct Routing supports routing emergency calls and notifying security personnel, based on the *connected location of the Teams client*.

The Teams client uses the network topology (network elements associated with emergency addresses) that the tenant admin defines to provide network connectivity information in a request to the Location Information Service (LIS). If there's a match, the LIS returns a location to the client.

The Teams client includes location data as part of an emergency call. The emergency service provider uses this data to determine the appropriate Public Safety Answering Point (PSAP), route the call to that PSAP, and provide the PSAP dispatcher with the caller's location.

## Plan for emergency calling

For dynamic emergency calling to work, these events must occur:

1. The network admin sets up network settings and the LIS to create a network and emergency location map.
2. During startup and periodically after, or when a network connection changes, the Teams client sends a location request with its network connectivity information to the network settings and the LIS.

    - If there's a network settings site match, the Teams client gets emergency calling policies from that site. For more information about policies, see Configure emergency policies.
    - If there's an LIS match, the Teams client gets an emergency location from the network element it's connected to. The match happens in this order, and the first match is used:

        - WAP
        - Ethernet switch/port
        - Ethernet switch
        - Subnet
3. When the Teams client makes an emergency call, it sends the emergency location to the Public Switched Telephone Network (PSTN).

The ability to automatically route calls to the right Public Safety Answering Point (PSAP) depends on the country or region where the Teams user is located.

Microsoft Calling Plans, Operator Connect partners, and Teams Phone Mobile partners provide dynamic emergency routing services for users in the United States and Canada.

## Emergency calling prerequisites for Direct Routing

For Direct Routing, you need to meet additional prerequisites for routing emergency calls and possibly for partner connectivity. In Teams, ensure that you configure the peer PSTN gateway settings to add location information to the outgoing emergency call's INVITE protocol.

To change the emergency call settings, set the *PidfloSupported* parameter to True. You can change these settings in PowerShell or in Teams admin center (TAC).

### Change PIDF/LO in Teams admin center

To change the PidfloSupported value in TAC, expand **Voice**, select **Direct Routing**, select the Session Border Controller (SBC) that supports your emergency call routing, select **Edit**, ensure **SBC supports PIDF/LO for emergency calls** is turned on, and save the SBC profile.

### Change PIDF/LO in PowerShell

To change the PidfloSupported value in PowerShell, see [Set-CsOnlinePSTNGateway](/en-us/powershell/module/teams/set-csonlinepstngateway) with the *-PidfloSupported* attribute set to *$true*.

For example, in a remote PowerShell session in Teams, enter:

```PowerShell
set-CsOnlinePSTNGateway -Identity sbc1.fabrikam.onmicrosoft.com -PidfLoSupported $true
```

Check that the setting is applied by entering:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc1.fabrikam.onmicrosoft.com
```

### Set up an Emergency Routing Service provider

For Direct Routing, you must also configure a connection to an Emergency Routing Service (ERS) provider (United States and Canada) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application. For information about SBCs that support ERS providers, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers).

## Configure emergency calling

These sections outline how to set up emergency calling in Teams.

- Assign emergency addresses
- Configure network settings
- Configure Location Information Service
- Configure emergency policies
- Enable users and sites
- Test emergency calling

For more information about emergency calling, including emergency addresses, call routing, country or region-specific details, and network settings or topology, see the following articles:

- [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing)
- [Manage network settings for cloud voice features](cloud-voice-network-settings)
- [Manage your network topology for cloud voice features](manage-your-network-topology)

For more information about which features are available in the government clouds, see Government support at the end of this article.

## Supported clients

The following clients are currently supported. Check back often for updates.

- Teams desktop client for Microsoft Windows
- Teams desktop client for Apple macOS
- Teams mobile client for Apple iOS, client version 1.0.92.2019121004 and App Store version 1.0.92 or later
- Teams mobile client for Android, client and Google Play store version 1416/1.0.0.2019121201 or later
- Teams phones with Teams app version 1449/1.0.94.2019110802 or later
- Teams Rooms on Windows
- Teams Rooms on Android
- Teams for Virtualized Desktop Infrastructure (VDI)

Note

Subnet locations are supported on all Teams clients. WiFi-based locations are supported on all Teams clients except Teams phones.

Ethernet/Switch (LLDP) is supported on:

- Windows versions 10.0 or later.
- Mac OS, which requires [LLDP enablement software](https://www.microsoft.com/download/details.aspx?id=103383).
- Teams phones with Teams app version 1449/1.0.94.2021110101 or later.
- Teams Rooms on Windows
- Teams Rooms on Android (OEM-specific configuration might be required)

Note

Dynamic emergency calling, including security desk notification, isn't supported on the Teams web client. To prevent users from using the Teams web client to call PSTN numbers, create a Teams calling policy, turn off the **Web PSTN calling** setting, and assign it to users of the web client. For more information, see [Calling policies in Teams](teams-calling-policy) and [Set-CsTeamsCallingPolicy](/en-us/powershell/module/teams/set-csteamscallingpolicy).

## Assign emergency addresses

You can assign emergency addresses to:

- Calling Plan users
- Operator Connect and Teams Phone Mobile users, depending on the capabilities assigned to the number when the carrier uploads them into a customer's inventory
- Network identifiers that are required for dynamically obtaining a location

To support automated routing of emergency calls within the United States, ensure the emergency locations assigned to network identifiers include the associated geo codes. You can't assign emergency addresses without geo codes to the network identifiers required for dynamic locations.

Azure Maps provides location-based services. When you enter an emergency address in the Microsoft Teams admin center, Teams checks Azure Maps for the address:

- If a match is found, Teams automatically includes the geo codes.
- If a match isn't found, you can manually create an emergency address by using the PIN drop feature.

Note

You can't assign emergency addresses that are more than a couple of years old to network identifiers. You need to re-create older addresses.

Add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell. For more information, see [Manage emergency locations for your organization](add-change-remove-emergency-location-organization).

## Configure network settings

Network settings determine the location of a Teams client and help the client dynamically get emergency calling policies and an emergency location. Configure network settings based on how your organization wants emergency calling to work.

Network settings include sites that consist of a collection of subnets. Use these sites exclusively for dynamic policy assignment to users. For example, assign an emergency calling policy and an emergency call routing policy to the "Redmond site" so that any user who roams from home or another Microsoft location gets emergency numbers, routing, and security desk specific to Redmond.

Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network. Use them to determine if the user's endpoint is inside the corporate network. The system attempts to get a dynamic policy or location based on the endpoint's IP address only if the user's external IP address matches an IP address in the trusted IP addresses.

Note

The system makes requests based on Ethernet/Switch (PortID or ChassisID) and Wireless AccessPoint (BSSID) regardless of whether the external IP address matches an IP address in the trusted IP addresses.

For more information about IP addresses, network regions, sites, and subnet addresses, see [Network settings for cloud voice features](cloud-voice-network-settings).

Configure network settings in the Microsoft Teams admin center or by using PowerShell. To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology).

It can take up to four hours for some changes to network settings (such as a new address or network identifier) to propagate and be available to Teams clients.

Note

You can also define subnets in LIS and associate them with an emergency location. LIS calculates the network ID from the client's IP address and client-reported prefix length. The calculated network ID must match a subnet configured in LIS. For example, the network ID for a client IP/mask of 10.10.10.150/25 is 10.10.10.128. For IPv6 requirements, see IPv6 subnet matching. For more information about network IDs, see [Understand TCP/IP addressing and subnetting basics](/en-us/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

Important

Cloud proxy service deployments that modify the source IP addresses from Teams clients don't support network configuration setting lookups.

**For Calling Plan, Operator Connect, and Teams Phone Mobile users:**

- If you need dynamic configuration of security desk notification, configure both trusted IP addresses and network sites.
- If you need only dynamic locations, configure only trusted IP addresses. You don't need to configure network settings.
- If you don't need either, you don't need to configure network settings.

**For Direct Routing users:**

- If you need dynamic enablement of emergency calling or dynamic configuration of security desk notification, configure both trusted IP addresses and network sites.
- If you need only dynamic locations, configure only trusted IP addresses. You don't need to configure network settings.
- If you don't need either, you don't need to configure network settings.

## Configure Location Information Service

A Teams client gets emergency addresses from the locations linked to different network identifiers.

To enable a client to get a location, you need to fill the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations. You can do this in the Microsoft Teams admin center or by using PowerShell.

### IPv6 subnet matching

LIS subnet matching uses the client's IP address and reported prefix length to calculate a network ID. That network ID must match a subnet configured in LIS.

On Windows, an IPv6 address assigned through stateful DHCPv6 can be reported with a prefix length of `/128`. Stateful DHCPv6 address assignment (IA\_NA) supplies an address but not a subnet prefix length. Teams reports the address and prefix length supplied by Windows. When the client reports `/128`, LIS calculates a network ID that is the full client address, rather than the network ID of a `/64` network.

For example, with client address `2001:db8:1234:5678::25` and reported prefix length `/128`, LIS looks for network ID `2001:db8:1234:5678::25`. It doesn't match an LIS entry whose network ID is `2001:db8:1234:5678::`, representing the `/64` network.

For this `/128` client and a network-site subnet configured with `/64`, network-site matching applies the configured `/64` prefix to determine whether the client's address is within that subnet. Consequently, the same client can match a network site and receive its emergency policies without matching an emergency location through IPv6 LIS subnet matching.

Important

A successful network-site match doesn't confirm that the client obtained an emergency address.

If IPv6 subnet matching doesn't return an emergency location, use one of the following supported alternatives. The supported client and network settings requirements still apply.

| Scenario | Configuration |
| --- | --- |
| Dual-stack endpoint | Configure the corresponding IPv4 subnet in LIS and associate it with an emergency location. IPv4 subnet matching is supported long-term. The client must report an IPv4 address and prefix length whose calculated network ID matches the LIS entry. An IPv6 subnet mismatch doesn't prevent an IPv4 match. |
| IPv6-only, wired endpoint | Configure a switch or switch/port identifier in LIS and associate it with an emergency location. The client must support Ethernet/Switch (LLDP) and report the configured identifier. |
| IPv6-only, wireless endpoint | Configure the wireless access point's BSSID in LIS and associate it with an emergency location. The client must support Wi-Fi-based locations and report the configured BSSID. |

These alternatives don't require changing your IPv6 address assignment method. Use the Teams admin center or the PowerShell cmdlets described in this section to configure the identifiers. Don't create per-device `/128` LIS subnet entries as a workaround. IPv6 addresses can change, leaving those entries out of date.

After configuring an alternative identifier, follow the steps in Test emergency calling to confirm the returned emergency location. Don't rely only on a network-site match.

### Using the Microsoft Teams admin center

In the Teams admin center, you can add or upload subnet, Wi-Fi access point, switch, or port information.

1. In the left navigation of the Teams admin center, go to **Locations** &gt; **Networks & locations**.
2. At the top of the page, select the tab for the network identifier that you want to add, such as **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.
3. From the table on the tab, select one of the following options:
    - **Add**- Use this option to add network identifiers one at a time.
        1. Fill out the ID and description fields.
        2. Enter an emergency location.
        3. Select **Apply**.
    - **Upload**- Use this option to add many network identifiers at once by using a CSV or TSV template.
        1. Download the zipped CSV or TSV templates.
        2. Open the template file for the network identifier you want to add.
        3. Complete the fields in the file.
        4. Save the template file.
        5. In the Teams admin center, select **Select a file** and choose the file you saved.
        6. Select **Upload**.

### Using PowerShell

Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.

- [Get](/en-us/powershell/module/teams/get-csonlinelissubnet), [Set](/en-us/powershell/module/teams/set-csonlinelissubnet), [Remove](/en-us/powershell/module/teams/remove-csonlinelissubnet) -CsOnlineLisSubnet
- [Get](/en-us/powershell/module/teams/get-csonlinelisport), [Set](/en-us/powershell/module/teams/set-csonlinelisport), [Remove](/en-us/powershell/module/teams/remove-csonlinelisport) -CsOnlineLisPort
- [Get](/en-us/powershell/module/teams/get-csonlineliswirelessaccesspoint), [Set](/en-us/powershell/module/teams/set-csonlineliswirelessaccesspoint), [Remove](/en-us/powershell/module/teams/remove-csonlineliswirelessaccesspoint) -CsOnlineLisWirelessAccessPoint
- [Get](/en-us/powershell/module/teams/get-csonlinelisswitch), [Set](/en-us/powershell/module/teams/set-csonlinelisswitch), [Remove](/en-us/powershell/module/teams/remove-csonlinelisswitch) -CsOnlineLisSwitch

Important

If you use subnets as part of network sites, you must redefine them in the Location Information Service to render dynamic locations.

## Configure emergency policies

Use the following policies to configure emergency calling. You can manage these policies in the Microsoft Teams admin center or by using PowerShell.

- **Emergency call routing policy – Applies only to Direct Routing**. This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number. You can assign this policy to users, to network sites, or to both. To learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies).

    (Calling Plan, Operator Connect, and Teams Phone Mobile users are automatically enabled for emergency calling with the emergency numbers from the country/region based upon their Microsoft 365 or Office 365 usage location.)
- **Emergency calling policy - Applies to Calling Plans, Operator Connect, Teams Phone Mobile, and Direct Routing.** This policy configures the security desk notification experience when an emergency call is made. You can set who to notify and how they are notified. For example, to automatically notify your organization's security desk and have them listen in on emergency calls. You can set unique experiences per emergency number, including not alerting the security desk for test calls to 933. This policy can either be assigned to users or network sites or both. To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies).

## Enable users and sites

You can assign emergency call routing policies and emergency calling policies to users and to sites. Keep in mind that emergency call routing policies apply to Direct Routing only. (Although it's possible to assign this policy to a Calling Plan, Operator Connect, or Teams Phone Mobile user, the policy has no effect.)

Assign policies in the Microsoft Teams admin center or by using PowerShell. To learn more, see:

- [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies)
- [Manage emergency calling policies in Teams](manage-emergency-calling-policies)

The following examples are in PowerShell.

To enable a specific user for security desk notification, use the following command:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

To enable a specific Direct Routing user for emergency calling, use the following command:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.

## Test emergency calling

Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.

- **Calling Plan, Operator Connect, and Teams Phone Mobile users in the United States or Canada** can use the predefined test emergency number 933 to validate their emergency calling configuration. This number routes to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether an actual emergency call would be automatically routed to the PSAP or screened first.
- **Direct Routing customers in the United States** should coordinate with their ERSP for a test service.

## Government support

The following table shows support for dynamic emergency calling in the government clouds:

| Cloud | Availability |
| --- | --- |
| World Wide Multi Tenant | Available on all Teams clients |
| GCC | Available on all Teams clients |
| GCCH | - Available on Teams desktop  - Available on Teams mobile clients  - Available on Teams phones, app version: 1449/1.0.94.2022061702 |
| DoD | - Available on Teams desktop - Available on Teams mobile clients - Available on Teams phone application released on Teams admin center |