---
layout: Conceptual
title: Prepare your environment for Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-prep
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
ms.date: 2026-06-29T00:00:00.0000000Z
ms.topic: how-to
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
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: Learn about how to prepare your infrastructure for deploying Microsoft Teams Rooms so that you can take advantage of all of the features.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: a711c07e-10b3-baf0-b92c-9dbcf6ab9474
document_version_independent_id: 2038cd48-44b1-1ed1-6e50-48290eef5605
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-prep.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-prep
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-prep.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 78b0cc1e-3af5-29a4-bc21-cf5fb9a26970
---

# Prepare your environment for Teams Rooms - Microsoft Teams | Microsoft Learn

This section contains an overview of the steps required to prepare your network environment so that you can use all of the features of Microsoft Teams Rooms. This section also includes information on configuring local administrative access to your Teams Rooms devices.

## Confirm network configuration

In order to function properly, Microsoft Teams Rooms devices must have access to a network that meets these requirements:

- Review access to: Microsoft Teams, SharePoint/OneDrive, Pro Management Portal, Microsoft Store, Windows Update, Intune, Microsoft Entra ID, & Microsoft Common destinations. Open required ports to the required destinations documented in [Teams Rooms Network Security](/en-us/microsoftteams/rooms/security?tabs=Windows#network-security)
- Review network bandwidth and quality of service (QoS) requirements: [QoS on Teams Devices](/en-us/microsoftteams/devices/qos-on-teams-devices)
- Review if your organization utilizes a proxy, you need the proxy address or proxy autoconfiguration (PAC) file url
- Review if your organization utilizes certificates for network access, you need the certificates for a successful setup

Important

Be sure to use a network connection with enough bandwidth (we recommend 10 mbps up/down per Teams Room) to ensure your meetings perform well.

### Certificates

Your Microsoft Teams Rooms device trusts public certificate authorities (CA) and uses Microsoft issued certificates for Microsoft Teams and authentication. If, intermediary equipment on a customer network requires a certified signed by a private CA then the device needs to trust that CA. This means having the CA + CA chain certificates installed on the device. Certificates can be installed via Intune for your Teams Rooms devices or via OEM tooling.

### Proxy

Important

Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room. Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production. If your proxy server utilizes internally signed certificates, you must install the internal certificate chain, including the root CA, on the Microsoft Teams Rooms device.

#### Proxy for Teams Rooms on Windows

A Teams Rooms on Windows device has several components that make outbound connections, each must be able to reach the internet through your proxy:

- **Teams Rooms app**: which runs as the local **Skype** user or Resource Account.
- **Pro Management agent** (`ServicePortalAgent`): which runs as **LocalSystem** and keeps the device connected to the Pro Management portal and delivers updates.
- **Windows & Store Updates**: Connects to Microsoft update delivery services.

We recommend configuring a **machine-wide (per-machine) proxy**. A single machine-wide setting applies to every account on the device, regardless of whether the Teams Room signs in with the Skype user or a Resource Account. Unlike the previously recommended LocalSystem method, a machine-wide proxy isn't removed by Windows feature updates (as documented in the [known issue](/en-us/troubleshoot/microsoftteams/teams-rooms-and-devices/teams-rooms-known-issues-windows#software-issues) where a feature update deletes the LocalSystem proxy settings by design).

##### Option 1: Across multiple devices with Intune

Use the **NetworkProxy CSP** to push the proxy to your Teams Rooms devices: [NetworkProxy CSP](/en-us/windows/client-management/mdm/networkproxy-csp).

Set the following:

- `ProxySettingsPerUser` = **0** (apply the proxy per-machine to all users)
- `ProxyServer` / `ProxyAddress` = `proxyserver:port` — **or**`SetupScriptUrl` = your PAC file URL for autoconfiguration
- (Optional) `Exceptions` and `UseProxyForLocalAddresses` as needed

Once configured, **reboot the device** so the Teams Rooms app and the Pro Management agent re-read the proxy. After the reboot, both the Teams Rooms app and the Pro Management agent route their traffic through the configured proxy.

##### Option 2: Per device using PowerShell

Run an elevated PowerShell prompt on the device in [admin mode](/en-us/microsoftteams/rooms/rooms-operations#switching-to-admin-mode), then set the machine-wide proxy in the registry:

```powershell
# Run as administrator. Replace the proxy address (or set a PAC URL instead).
$proxy  = 'contosoproxy.corp.net:8080'
$policy = 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings'
$inet   = 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings'

# 1) Switch the device to machine-wide (per-machine) proxy mode
New-Item -Path $policy -Force | Out-Null
Set-ItemProperty -Path $policy -Name 'ProxySettingsPerUser' -Type DWord  -Value 0

# 2) Set the machine-wide proxy
Set-ItemProperty -Path $inet   -Name 'MigrateProxy'         -Type DWord  -Value 1
Set-ItemProperty -Path $inet   -Name 'ProxyEnable'          -Type DWord  -Value 1
Set-ItemProperty -Path $inet   -Name 'ProxyServer'          -Type String -Value $proxy

# --- PAC file instead of a fixed proxy? Use this instead of ProxyEnable/ProxyServer above:
# Set-ItemProperty -Path $inet -Name 'AutoConfigURL' -Type String -Value 'http://contosoproxy.corp.net/proxy.pac'

# Reboot for Windows, the Teams Rooms app, and the Pro Management agent to pick up the proxy.
Restart-Computer
```

Note

You can also apply the same machine-wide settings with the community **`Set-WinInetProxy`** cmdlet (`WinInetProxy` module) using `-ProxySettingsPerUser 0`.

Once configured, **reboot the device** so the Teams Rooms app and the Pro Management agent re-read the proxy. After the reboot, both the Teams Rooms app and the Pro Management agent route their traffic through the configured proxy.

#### Proxy on Teams Rooms on Android

Proxy settings on Teams Rooms on Android vary by device manufacturer. Consult OEM documentation for how to best configure Teams Rooms on Android devices for a network with a proxy.

## Wireless network considerations

We strongly recommend that you connect your Teams Rooms devices to a wired network for greater stability and performance, ensuring a seamless meeting experience. If using a wired connection isn't available, you may opt to use a wireless connection.

Important

Wireless networks can be prone to network interference leading to quality degradation. We strongly recommend that you follow your wireless equipment provider's best practices when configuring a wireless connection to improve video and audio quality.

Here are some examples of wireless network configuration best practices recommended by various manufacturers:

- Deploy wireless equipment, such as access points and routers, that can handle and distribute the bandwidth load across all connected devices in the network.
- As much as possible, use access points and routers from a single manufacturer to avoid further congesting the radio-spectrum.
- Ensure wireless equipment is installed in a way that reduces or eliminates interference from objects and other equipment.
- Ensure the wireless network shows strong signal strength (Wi-Fi signal showing full bars is preferred) on Teams Rooms and other device screens.
- Default to prioritizing 5-GHz coverage for devices to optimize for higher bandwidth.
- Enable band steering to ensure that 5 GHz is always given more priority when sharing the same network name as 2.4 GHz.
- Keep wireless channel utilization below 50%.
- Keep access point and router firmware up to date with the latest firmware versions and hot fixes.
- Verify that Teams Rooms devices and at least one access point see each other with a signal strength of -60 dBm or better. A dBm value closer to zero is preferred. Follow your equipment manufacturer's recommendations.
- Implement QoS whenever possible to allow monitoring and resolution of issues in real time.

For more best practices specific to your wireless network hardware, check your manufacturer's documentation.

You can also troubleshoot wireless network issues using the wireless network report built into Windows 10. For more information, see [Analyze the wireless network report - Microsoft Support](https://support.microsoft.com/windows/analyze-the-wireless-network-report-76da0daa-1db2-6049-d154-7bb679eb03ed).

## Tenant Restrictions

For organizations which utilize [tenant restrictions](/en-us/entra/identity/enterprise-apps/tenant-restrictions) features of Microsoft Entra ID, this is supported on some Teams Devices if your organization utilizes the proxy deployment variant with header injection.

#### Teams Rooms on Windows

To support tenant restrictions, ensure you have your proxy configuration on your Teams Rooms device completed per this Learn document and ensure the Teams Rooms on Windows device has the replacement SSL certificates installed on it to trust the header injected web traffic.

#### Teams Rooms on Android

Tenant restrictions aren't supported today on Teams Rooms on Android devices. Consult with your Android device OEM for potential workarounds.

## Teams Rooms on Windows administrative access

### Using an admin group

If you choose to join a Teams Rooms on Windows device to a domain (Microsoft Entra ID or Active Directory), you can use Microsoft Intune, Group Policy, or Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain. Anyone who is a member of that security group can enter their credentials and unlock Settings.

Note

If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings. The workaround is to log in with the local Admin account.

### Local "Admin" User Account

Caution

Be sure to change the Microsoft Teams Rooms password as soon as possible.

Microsoft Teams Rooms default password is set to `sfb`. The password can be changed in several ways:

- Recommended: [Configuring LAPS on Teams Rooms on Windows](/en-us/microsoftteams/rooms/laps-authentication)
- Intune: [Set-LocalUser](/en-us/powershell/module/microsoft.powershell.localaccounts/set-localuser)
- Locally: [Change or reset your Windows password](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)

You can read more about the Admin account in the [Microsoft Teams Rooms security](security) article.

### Local 'Skype' User Account

Caution

Any modifications to the "Skype" user account are not supported by Microsoft and will prevent your Teams Rooms on Windows device from functioning correctly.

Teams Rooms on Windows include a local account named "Skype" which is passwordless. This account is used to sign in to Windows to launch the Teams Rooms app. For more information on how the "Skype" user is security, review [Microsoft Teams Rooms security](security).

### Machine Account

Much like any Windows device, the machine name can be renamed by right-clicking in **Settings** &gt; **About** &gt; **Rename PC**.

If you would like to rename the computer after joining it to a domain, use [Rename-Computer](/en-us/powershell/module/microsoft.powershell.management/rename-computer), a PowerShell command, followed by the computer's new name.

## Teams Rooms on Android administrative access

Local administrative access to Teams Rooms on Android devices is controlled by the Teams device equipment manufacturer. Consult the device documentation for default accounts and passwords and instructions for how to change those passwords.