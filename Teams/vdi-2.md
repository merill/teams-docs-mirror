---
layout: Conceptual
title: New VDI solution for Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/vdi-2
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: article
ms.date: 2026-11-12T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: fklurfan
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about Teams for Virtualized Desktop Infrastructure (VDI) 2.0.
ms.localizationpriority: high
locale: en-us
document_id: cfb4a86b-81cb-9b5d-412e-bb76879ecd3b
document_version_independent_id: cfb4a86b-81cb-9b5d-412e-bb76879ecd3b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/vdi-2.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: vdi-2
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/vdi-2.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 87d808e6-cfe8-afa1-ec2d-0cbef385d637
---

# New VDI solution for Teams - Microsoft Teams | Microsoft Learn

The new VDI solution for Teams is a new architecture for optimizing the delivery of multimedia workloads in virtual desktops.

## System requirements

| Requirement | Minimum version |
| --- | --- |
| Teams | -24193.1805.3040.8975 (for Azure Virtual Desktop/Windows 365) -24295.605.3225.8804 (for Citrix) -25198.1109.3837.4725 (for Amazon)-MAC endpoints require 26072.521.4595.7966 or higher -26072.521.4595.7966 (for Omnissa) |
| Azure Virtual Desktop/Windows 365 | -Windows App for Windows: 2.0.352.0-Remote Desktop Client for Windows: No longer supported. Upgrade to the latest Windows App.-Windows App for MAC: 11.3.4 Non-App Store version. Users must use the stand-alone .pkg file, which can auto-update. Store version isn't supported.-Evergreen link to the latest MAU client: https://aka.ms/RDMacMAU |
| Citrix | -Virtual Desktop Agent (VDA): 2203 Long Term Service Release (LTSR) Cumulative Update (CU) 3 or 2305 Current Release (CR)-Citrix Workspace app (CWA) for Windows: 2203 LTSR (any cumulative update), 2402 LTSR, or 2302 CR.-MsTeamsPluginCitrix: 2024.41.1.1 (for Windows)-Citrix Workspace app for MAC: 2508.10 -MsTeamsPluginCitrix: 2025.49.x.x (for MAC) https://aka.ms/macplugin-[Only CWA versions not at End of Life are supported](https://www.citrix.com/support/product-lifecycle/workspace-app.html) |
| Amazon WorkSpaces | Client 5.31.0.5733. WSP (Server Agent) 2.1.0.1840 |
| Omnissa Horizon | Client for Windows 8.17 or higher |
| Endpoint | -Windows 10 1809 (SlimCore minimum requirement)-[Windows Enterprise Long Term Service Channel](/en-us/windows/whats-new/ltsc/overview#the-long-term-servicing-channel-ltsc) Thin clients on Windows 10 2019/2021, or Windows 11 2024 are supported-GPOs must not block MSIX installations (see Step 3: SlimCore MSIX staging and registration on the endpoint) -Minimum CPU: Intel Celeron (or equivalent) @ 1.10 GHz, four Cores, Minimum RAM: 4 GB-macOS 14, 15 or 26 (requires CWA 2511) |

## Components

| Component | Role | Update | Size | Notes |
| --- | --- | --- | --- | --- |
| Teams **vdiBridge** | Server-side virtual channel module. | New version with every Teams version. |  | Bundled with Teams. |
| Custom virtual channel (VC) | Custom VC owned by Microsoft Teams. | Stable API - no updates foreseen. |  | Check the Citrix Studio policy **Virtual channels allow list**. |
| Plugin | Client-side VC dll. Responsible also for SlimCore download and clean-up. | Not frequent (ideally no updates). | Approximately 600 KB. | Bundled with Windows [Remote Desktop Client 1.2.5405.0](/en-us/azure/virtual-desktop/whats-new-client-windows), Windows App for Windows 1.3.252, and Windows App for MAC [11.3.4 MAU client](https://go.microsoft.com/fwlink/?linkid=868963) or higher. Citrix CWA 2402 for Windows or higher can fetch and install the plugin. CWA 2508.10 for MACBundled with Amazon WorkSpaces client 5.31.0.5733 for Windows or higher. Bundled with Omnissa's Horizon Client 8.17 (2512) for Windows or higher |
| SlimCore | Media engine (operating system specific, not VDI vendor specific). | Auto-updated to a new version with each new Teams version. | Approximately 50 MB. | MSIX package hosted on Microsoft's public Content Delivery Network. |

## Optimizing with new VDI solution for Teams

### Step 1: Confirm prerequisites

1. Make sure you have the new Microsoft Teams version 24193.1805.3040.8975 or higher (for Azure Virtual Desktop/Windows 365), 24295.605.3225.8804 or higher for Citrix, or 26032.206.4355.6508 for Omnissa.
2. Enable Teams policy**if necessary** for a specific user group (it's enabled by default at a Global org-wide level).
3. For Citrix, you must configure the **Virtual channels allow list** as described in the Citrix Virtual channel allow list section of this article.
4. For Amazon WorkSpaces, make sure the WorkSpace client for Windows is 5.31.0.5733 or higher.
5. For Omnissa Horizon, optimization is now generally available - make sure the Horizon client for Windows is 8.17 (2512) or higher.

### Step 2: Plugin installation on the endpoint

1. For Azure Virtual Desktop and Windows 365, MsTeamsPluginAvd.dll is bundled with the Remote Desktop Client for Windows 1.2.5405.0, with the Windows App Store app for Windows 1.3.252 or higher, and with the Windows App for MAC Non-Store version 11.3.4

    - The plugin is found in the same folder location where the Remote Desktop Client is installed. You can find the plugin at AppData\Local\Apps\Remote Desktop or C:\Program Files (x86), depending on the mode in which it was installed.
    - The [Windows App Store](/en-us/windows-app/overview) app, which is MSIX-based, is found in C:\Program Files\WindowsApps. Access to this folder is restricted.
2. For Amazon WorkSpaces, MsTeamsPluginAmazon.dll is bundled with the WorkSpaces Client for Windows 5.28.0.5487 or higher.

    - The plugin is found in the same folder location where the WorkSpaces Client is installed.
3. For Omnissa Horizon, MsTeamsPluginOmnissa.dll is bundled with the Horizon Client for Windows 8.17 (2512) or higher.

    - The plugin is found in the same folder location where the Horizon Client is installed (C:\Program Files\Omnissa\Omnissa Horizon Client).
4. For Citrix Workspace app for Windows 2402 or higher, MsTeamsPluginCitrix.dll can be installed either:

    - Using the user interface when installing Citrix Workspace app:

        On the **Add-on(s)** page, select the **Install Microsoft Teams VDI plug-in** checkbox, and then select **Install**.

        Agree to the user agreement that pops up and proceed with the installation of the Citrix Workspace app.

        Note

        Citrix Workspace app for Windows 2402 only presents the plugin installation UI on a fresh install.For in-place upgrades to also present this option, Citrix Workspace app for Windows 2405 or Mac 2603 higher is required.Automatic installation of the plugin when CWA is auto-updating was introduced in CWA for Windows 2508. Starting from Citrix Workspace app 2603 for Windows, CWA can auto-update the plugin to the latest version, even before CWA auto-updates to a newer version.For more information, [check this Citrix article](https://docs.citrix.com/en-us/citrix-workspace-app-for-windows/install#microsoft-teams-vdi-plugin)
    - Via command line or scripts for managed Windows devices using C:&gt;CitrixWorkspaceApp.exe /installMSTeamsPlugin

- Admins can also install the plugin manually on top of any existing supported Citrix Workspace app (see System Requirements) using tools like SCCM (use the Windows app package deployment type) or Intune (use the Line-of-Business app).

    Admins can use **msiexec** with appropriate flags, as discussed in [msiexec](/en-us/windows-server/administration/windows-commands/msiexec).

    Important

    - Windows Plugin MSI download link for Citrix customers:  - For 32-bit Workspace app https://aka.ms/plugin. - For 64-bit Workspace app (new) https://aka.ms/plugin_x64. - For arm-based Workspace app https://aka.ms/plugin_arm64. - Citrix Workspace app (wfica process) can only load plugins from the same architecture (in other words, 32-bit CWA loading 64-bit DLL will fail to optimize)
    - Mac Plugin download link for Citrix customers https://aka.ms/macplugin
- The plugin MSI automatically detects the CWA installation folder and places MsTeamsPluginCitrix.dll in that location.
- Plugins can only be upgraded while there's no active Virtual Desktop session.
- Plugins can't be downgraded, only upgraded or reinstalled (repaired).
- Per-user installation of CWA isn't supported.
- If no CWA is found on the endpoint, installation is stopped.

| User type | Installation folder | Installation type |
| --- | --- | --- |
| Administrator | 64-bit: C:\Program Files (x86)\Citrix\ICA Client32-bit: C:\Program Files\Citrix\ICA Client | Per-system installation |

| Release note version | Platform | Details |
| --- | --- | --- |
| 2026.38.1.42026.38.1.3 | Windows | October 2026-Supports recovery to VDI optimization when SlimCore initialization completes after an initial timeout.-Improves resilience of SlimCore downloads during temporary interruptions or Windows-imposed background-transfer restrictions.-Reduces package-verification failures caused by concurrent readers, such as antivirus scanners.-Improves diagnostic accuracy for Error 3007 by reporting underlying download errors and avoiding misleading Host-deployment timeout reports. |
| 2026.35.1.1 | Mac | September 2026-Multimonitor rendering fixes |
| 2026.29.1.4 | Windows | July 2026-Fixed MSIX provisioning and registration issues for thin clients or kiosk devices that prevented new users from getting optimized with the new architecture.-Only [split MSIX packages](/en-us/microsoftteams/vdi-2#step-3-slimcore-msix-staging-and-registration-on-the-endpoint) are supported from this plugin version forward.-Security enhancements |
| 2026.21.1.2 | Mac | June 2026-Fixed multimonitor rendering issues. Improved logging |
| 2026.15.1.1 | Windows | April 2026-Townhall optimization as attendee-Improved client-side watchdog reliability to reduce false disconnects and ensure more stable recovery from transient network interruptions.-Support for Teams as a Published Apps (Citrix Virtual Apps) |
| 2025.49.1.1 | Mac | December 2025-GA version |
| 2025.43.1.1 | Windows | November 2025-Improvements in virtual channel handling and transport.-Improvements in MSIX installation process (download location updated to localappdata when temp is unavailable). Enhanced reliability in BITS downloader.-Logging and telemetry fixes for improved diagnostics |
| 2025.29.1.2 | Windows | August 2025-Additional logging and telemetry capabilities |
| 2025.24.1.3 | Windows | July 2025-Thin Clients that use [Unified Write Filters with RAM Overlay](/en-us/windows/configuration/unified-write-filter/uwfoverlay) might experience SlimCore MSIX installation errors if TEMP/TMP Environment (System) variables are pointed to a RAM disk. This plugin fixes this problem. For more details, check the Unified Write Filters (UWF) section later in this article. It additionally supports HID disabling by creating a registry key in the Virtual Machine (see section 'Peripherals in VDI') |
| 2025.14.1.8 | Windows | May 2025-The Citrix plugin can now download SlimCore packages that are 64-bit, increasing performance and improving screen sharing experiences. This release also supports the SlimCore split MSIX package when Teams is 25094.x.x.x or higher, simplifying user prompts for camera and microphone permissions. See "New Split MSIX Package" in Step 3: SlimCore MSIX staging and registration on the endpoint. |
| 2024.41.1.1 | Windows | October 2024-When using SlimCore in multimonitor setups, a Citrix user is unable to share entire screen or individual monitors.-Attempts a [Reset-AppxPackage](/en-us/PowerShell/module/appx/reset-appxpackage) if SlimCoreVdi MSIX package registrations fail after the virtual channel is established. |
| 2024.32.X.X | Windows | August 2024-The plugin now attempts a Reset-AppxPackage for SlimCoreVdi MSIX package in the event the AppExecution alias is missing. |

### Step 3: SlimCore MSIX staging and registration on the endpoint

To find a list of released SlimCore packages, [check this table](/en-us/officeupdates/teams-app-versioning#vdi-slimcore-version-2-msix-packages).The plugin silently executes this step, without user or admin intervention. The staging and registration relies on the App Readiness Service (ARS) on the endpoint. It's possible that registry keys set by a Group Policy or a third-party tool block the MSIX package installation. For a complete list of applicable registry keys, see [How Group Policy works with packaged apps - MSIX](/en-us/windows/msix/group-policy-msix).

Important

**New Split MSIX Package** A new 64-bit Slimcore installer is available, which splits the media engine installation into two different MSIX Packages, called Host and Framework. This change has direct implications on AppLocker/App Control for Business/Group Policy Objects (GPO), if configured on the user's device:

- Host packages (~100 KB) [Microsoft.Teams.SlimCoreVdiHost.win-x64\_8wekyb3d8bbwe] are in charge of registering SlimCore as an application in the Windows OS, under a single Package Family Name (PFN) - this appears as "Microsoft Teams VDI Optimizer" under Settings/Apps/Installed apps. Once users grant permissions for camera/microphone/location to this app, they won't be prompted again. This addresses a limitation with the previous SlimCore MSIX installer, which had different PFNs, hence every time Teams was upgraded in the VM it retriggered a user prompt for peripheral access. MsTeamsVdi.exe loads from the Host package, and it remains as the process in charge of all network communications.
- Framework packages (~60 MB) [Microsoft.Teams.SlimCoreVdiFwk.win-x64.&lt;version&gt;\_8wekyb3d8bbwe] only contain Real Time Media libraries. These packages have different PFNs, with versioning. They aren't visible under Apps/Installed apps. Multiple Framework packages can coexist in the same endpoint. MsTeamsVdi.exe automatically loads the Framework package that matches the Teams version on the VM.
- Minimum System Requirements:AVD/W365 environments with Teams 25153.x.x.x and Remote Desktop client 1.2.6278 / Windows App 2.0.550.0.Citrix environments with Teams 25094.x.x.x and plugin 2025.14.1.8

The following registry keys could block new media engine MSIX package installation:

- [BlockNonAdminUserInstall](/en-us/windows/client-management/mdm/policy-csp-applicationmanagement#blocknonadminuserinstall)
- [AllowAllTrustedApps](/en-us/windows/client-management/mdm/policy-csp-applicationmanagement#allowalltrustedapps)
- AllowDevelopmentWithoutDevLicense

These three registry keys can be found at either of the following locations on the user's device:

- `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `HKLM\SOFTWARE\Policies\Microsoft\Windows\Appx`

Some policies might change these registry keys and block app installation in your organization because the admins set a restrictive policy. Some of the known GPO policies that could prevent installation include:

- Prevent non-admin users from installing packaged Windows apps.
- Allow all trusted apps to install (disabled).These three registry keys can be found at either of the following locations on the user's device:

    - `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
    - `HKLM\SOFTWARE\Policies\Microsoft\Windows\Appx`

Some policies might change these registry keys and block app installation in your organization because the admins set a restrictive policy. Some of the known GPO policies that could prevent installation include:

- Prevent non-admin users from installing packaged Windows apps.
- Allow all trusted apps to install (disabled).

Important

Managed endpoints/thin clients with BlockNonAdminUserInstall enabled can still allow SlimCore packages to install. Apply KB5052094 (Windows 11 23H2 and 22H2), KB5052093 (Windows 11 24H2), KB5055612 (Windows 10 22H2), or any subsequent KB. This installation introduces a new Group Policy called ["Allowed package family names for non-admin user install"](/en-us/windows/client-management/mdm/policy-csp-applicationmanagement#allowednonadminpackagefamilynamerules) in the Local Group Policy Editor:

> 
> Group Policy Editor -&gt; Computer Configuration -&gt; Administrative Templates -&gt; Windows Components -&gt; App Package Deployment -&gt; Administrators can then Allow-list SlimCore packages by allowing a complete Package Family Name. For the new Split MSIX Package architecture, the two packages must be added to the allow-list (`Microsoft.Teams.SlimCoreVdiHost.win-x64_8wekyb3d8bbwe` and `Microsoft.Teams.SlimCoreVdiFwk.*_8wekyb3d8bbwe`). This can also be achieved using Regex: Microsoft.Teams.SlimCoreVdi\*.\*\_8wekyb3d8bbwe

Intune-managed endpoints can set this using the following **OMA-URI**:

> 
> 
> > 
> > ./Device/Vendor/MSFT/Policy/Config/ApplicationManagement/AllowedNonAdminPackageFamilyNameRules Data type: String Value: (the encoded &#xF000 is the standard delimiter/separator)
> 
> 
> 
> ```xml
> <enabled/>
> <data id="AllowedNonAdminPackageFamilyNameRulesList" value="Microsoft.Teams.SlimCoreVdi*.*_8wekyb3d8bbwe&#xF000;MicrosoftTeamsSlimCoreVdiAllowRule"/>
> ```

Note

[AppLocker](/en-us/windows/security/application-security/application-control/app-control-for-business/applocker/applocker-overview) or [App Control for Business](/en-us/windows/security/application-security/application-control/app-control-for-business/appcontrol-and-applocker-overview) can also prevent MSIX package installation. AppLocker is a defense-in-depth security feature and not considered a defensible [Windows security feature](https://www.microsoft.com/msrc/windows-security-servicing-criteria). Use App Control for Business when the goal is to provide robust protection against a threat and you expect no by-design limitations to prevent the security feature from achieving this goal. Generally, customers who are able to implement application control using App Control, rather than AppLocker, should do so. App Control is undergoing continual improvements and is getting added support from Microsoft management platforms. Although AppLocker continues to receive security fixes, it isn't getting new feature improvements.

Important

For **App Control for Business and AppLocker**, make sure there's no blocking configuration or policy, or add an exception for SlimCore MSIX packages (Host and Framework) in Local Security Policy -&gt; Application Control Policies -&gt; AppLocker. AppLocker can't process trailing wildcards, unlike App Control for Business. Since new Framework packages contain a version-specific PackageFamilyName (for example, Microsoft.Teams.SlimCoreVdiFwk.win-x64.2025.14\_8wekyb3d8bbwe), customers can add AppX or MSIX exclusions by relying on Microsoft's unique PublisherID 8wekyb3d8bbwe instead. If that is not possible, the only option would be to allow an exhaustive list of entries of Framework packages with separate exact-name rule for each required release and architecture. The Framework releases follow a YYYY.WW -year and week- nomenclature. New Host packages are single Package Names (**ProductName** Microsoft.Teams.SlimCoreVdiHost.win-x64, with **PublisherName:**`CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`). Administrators using the more granular per-application ['AllAppList'](/en-us/windows/configuration/assigned-access/configuration-file#allapplist) to define the list of applications that are allowed to run need to add exceptions in this manner (since SlimCore follows the UWP model):

> 
> 
> > 
> > &lt;App AppUserModelId="Microsoft.Teams.SlimCoreVdi.&lt;platform&gt;-&lt;architecture&gt;.&lt;release\_version&gt;\_8wekyb3d8bbwe!MsTeamsVdi" /&gt;
> 
> 
> 
> ```xml
> <App AppUserModelId="Microsoft.Teams.SlimCoreVdiHost.win-x64_8wekyb3d8bbwe!MsTeamsVdi"/>
> ```

## Mac endpoints

Note

Mac is now rolled out 100% to General Availability for AVD/W365 and Citrix environments.

Users that meet the minimum requirements described earlier in this article can be optimized using the new architecture (SlimCore-based).

AVD and Windows 365 customers must use the nonstore Windows App version (also known as the Microsoft AutoUpdate or MAU client), since only that version bundles the Plugin. App Store Windows App doesn't include the Plugin, therefore users will remain in the WebRTC-based optimization. Evergreen link to the latest MAU client: https://aka.ms/RDMacMAU

For Citrix customers, CWA 2508.10 can present a User Interface upon installation that prompts the user to install the Plugin, but this flow requires user action. CWA 2603 also supports plugin deployment via Global App Config Service, or the Virtual Channel Plugin Download Manager policy in Citrix Studio. CWA 2609 will automatically install the Plugin. Administrators can also deploy the Plugin using other tools like JAMF.

Important

- The Plugin is in charge of virtual channel establishment and automatic and silent media engine installation on the Mac device.
- The Plugin for Mac also bundles the Host SlimCore MSIX Package. Therefore, the SlimCore package that is fetched and installed on macOS is the Framework only ('Microsoft.Teams.SlimCoreVdiBndl.mac'). Although delivered in an MSIX-format archive, this is not Windows-style MSIX provisioning and registration on macOS.
- Multiple media engine versions can coexist on the same user device. Microsoft Teams version on the VM instructs the plugin which SlimCore version should be loaded.
- All these activities are transparent to the user and the Administrators.
- Plugin location: /Applications/Utilities/MsTeamsVdi.Plugin.app
- If a user migrates from Windows app Appstore version older than 11.2.3 to a non-store Windows app, the DisableVdi2user default client setting on Windows app is not removed and the optimization is blocked. Users have to manually delete it by running the following command in Terminal: defaults delete com.microsoft.rdc.macos "ClientSettings.DisableVdi2"

#### SlimCoreVdi installation folder

- For AVD/W365, /Users/{USER}/Library/Containers/windows App/Data/Library/Application Support/Microsoft/TeamsVDI/Packages/
- For Citrix, /Users/{User}/Library/Application Support/Microsoft/TeamsVDI/Packages

#### Log collection in Mac

Logs are stored in the following directory on the user's device: ~/Library/Application Support/Microsoft/TeamsVDI

#### Unsupported Features in Mac

- Townhall optimization as an attendee
- For AVD/W365, Cross Cloud is currently not supported
- Outgoing screen sharing in end-to-end encrypted meetings is disabled​
- Share system audio
- Authenticated Proxies in macOS Network settings (AVD/W365 only)
- Link Layer Discovery Protocol (LLDP) in e911 (AVD/W365 only)
- Remote App / Published Apps

#### Known Issues in Mac

1. Presenter's mouse cursor is slow during app sharing. If the presenter stops and reinitiates app sharing, the lag is not present anymore. This is fixed in Teams 26149.x.x.x or higher.
2. Zoom VDI plugin older than 6.6.10 on the Mac device results in a Citrix Workspace app crash on call transfers.
3. If you attach/detach external monitors during the call, video might appear on the wrong screen. This also occurs when you change display alignments during the HDX session​. This is fixed in Plugin 2026.35.1.1.
4. HID requires Teams 26276.x.x.x or higher.

## Verifying that the endpoint is optimized

Once you meet all the minimum requirements, launching Teams for the first time will attempt to load in SlimCore optimized mode, by default.

You can check in the Teams client that you're optimized with the new architecture by looking at the VDI Status Indicator (top left in the UI). Also, users can select the ellipsis (three dots ...) on the top bar, then selecting **Settings** &gt; **About**. The Teams and client versions are listed there.

- AVD SlimCore Media Optimized = New optimization based on SlimCore.
- AVD Media Optimized = optimization based on WebRTC.

The plugin (MsTeamsPluginAvd.dll, MsTeamsPluginCitrix.dll, or MsTeamsPluginAmazon.dll) is responsible for eventually downloading the media engine, and SlimCore, which is an MSIX package. It installs silently without admin privileges or reboots in (example, exact path varies):

`C:\Program Files\WindowsApps\Microsoft.Teams.SlimCoreVdi.win-x64.2024.15_2024.15.1.5_x64__8wekyb3d8bbwe`

For the new Split MSIX Package: `C:\Program Files\WindowsApps\Microsoft.Teams.SlimCoreVdiFwk.win-x64.2025.28_2025.28.1.4_x64__8wekyb3d8bbwe``C:\Program Files\WindowsApps\Microsoft.Teams.SlimCoreVdiHost.win-x64_2025.28.1.4_x64__8wekyb3d8bbwe`

The remote desktop client or the Citrix Workspace app downloads the x64 or x86 SlimCore package, based on the user's device. The 'WindowsApps' folder is locked down, so users don't have access to it. Admins modify ACLs to take ownership, though this action isn't recommended. Instead, use PowerShell to list the MSIX apps in the endpoint:

```

PowerShell
PowerShellCopy

Get-AppxPackage Microsoft.Teams.SlimCore*
```

A sample of the results that can be returned from running this PowerShell is:

```

PowerShell
Name              : Microsoft.Teams.SlimCoreVdiHost.win-x64
Publisher         : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US
Architecture      : X64
ResourceId        :
Version           : 2026.20.1.7
PackageFullName   : Microsoft.Teams.SlimCoreVdiHost.win-x64_2026.20.1.7_x64__8wekyb3d8bbwe
InstallLocation   : C:\Program Files\WindowsApps\Microsoft.Teams.SlimCoreVdiHost.win-x64_2026.20.1.7_x64__8wekyb3d8bbwe
IsFramework       : False
PackageFamilyName : Microsoft.Teams.SlimCoreVdiHost.win-x64_8wekyb3d8bbwe
PublisherId       : 8wekyb3d8bbwe
IsResourcePackage : False
IsBundle          : False
IsDevelopmentMode : False
NonRemovable      : False
IsPartiallyStaged : False
SignatureKind     : Developer
Status            : Ok

Name              : Microsoft.Teams.SlimCoreVdiFwk.win-x64.2026.20
Publisher         : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US
Architecture      : X64
ResourceId        :
Version           : 2026.20.1.7
PackageFullName   : Microsoft.Teams.SlimCoreVdiFwk.win-x64.2026.20_2026.20.1.7_x64__8wekyb3d8bbwe
InstallLocation   : C:\Program
                    Files\WindowsApps\Microsoft.Teams.SlimCoreVdiFwk.win-x64.2026.20_2026.20.1.7_x64__8wekyb3d8bbwe
IsFramework       : True
PackageFamilyName : Microsoft.Teams.SlimCoreVdiFwk.win-x64.2026.20_8wekyb3d8bbwe
PublisherId       : 8wekyb3d8bbwe
IsResourcePackage : False
IsBundle          : False
IsDevelopmentMode : False
NonRemovable      : False
IsPartiallyStaged : False
SignatureKind     : Developer
Status            : Ok
```

Important

Microsoft stores up to 12 versions of SlimCoreVdi Frameworks for compatibility purposes. We store these versions in case the user accesses different VDI environments, such as persistent, where Teams auto-updates itself, and non-persistent, where Teams auto-updates are disabled.

If you're optimized, you can see MsTeamsVdi.exe running on your endpoint for Azure Virtual Desktop/W365 (as a child process of msrdc.exe) or Citrix (as a child process of wfica32.exe). When using Process Explorer, If you select msrdc.exe (or wfica32.exe), select **Show the lower pane** under **View** and switch to the **DLL** tab, you can also see the Plugin (MsTeamsPluginAvd.dll or MsTeamsPluginCitrix.dll) being loaded. This action is a useful troubleshooting step in case you're not getting the new optimization.

## VDI Status Indicator

Microsoft Teams displays information about the optimization status, helping the user understand if they're optimized or not. It also shows if they're using the WebRTC optimization or the new Slimcore-based one by hovering their cursor over the **Optimized** banner.

In cases where Microsoft Teams isn't optimized, the user sees a warning icon.

![Screenshot of the Teams app showing it's not optimized.](media/teams-not-optimized-status-indicator.png)

Users can select the three dots and choose **Optimize virtual desktop and restart** to attempt a repair.

This selection triggers a Teams restart, which can solve some known issues. If the user is still unoptimized, an error code displays for quick diagnosis by IT Admins based on the [connection error table](vdi-2-troubleshooting#connection-error).

Users are presented with a [link](https://go.microsoft.com/fwlink/?linkid=2295247) to receive more information about the error, and if it's actionable, they can try a self-remediation.

## Session roaming and reconnections

Note

If virtual desktop sessions are disconnected (not logged off, Teams is left running on the virtual machine), now Teams on Citrix can also switch optimization stacks without being restarted after reconnects. In other words, Teams tries to optimize the user with SlimCore if possible, and if the endpoint doesn't support it, WebRTC optimization is attempted.

For example, a Windows endpoint used in bring your own device (BYOD) scenarios while working from home that has the plugin installed, and a corporate-managed Linux thin client in the office that only supports WebRTC. When the user roams between the two endpoints, Teams will automatically pick the right optimization stack without asking the user to restart the application. Additionally, the user is notified about the optimization switch with a dismissible banner ("Optimizing virtual desktop ...").

This seamless stack transition replaced the modal dialogue that asked the user to manually restart the app in VDI environments.

## Networking considerations

Tip

MsTeamsVdi.exe is the process that makes all the TCP/UDP network connections to the Teams relays/conference servers or other peers (both signaling and media).

SlimCore MSIX manifest adds the following rules to the Firewall: `<Rule  Direction="in" IPProtocol="TCP"  Profile="all" />``<Rule Direction="in" IPProtocol="UDP" Profile="all" />`

Important

In VDI environments where the new optimization is used alongside Conditional Access policies with Continuous Access Evaluation (CAE) and strict location enforcement, users may experience repeated Teams sign-in prompts or failed calls because authentication requests are evaluated against the endpoint (client) IP rather than the VM host IP, causing access to be blocked when connecting from untrusted networks. This behavior is by design and reflects stricter enforcement compared to WebRTC-based optimization. To mitigate impact, customers can relax CAE policies (e.g., avoid strict location enforcement), or add relevant endpoint or ISP IP ranges to trusted locations.

Note

Make sure the user's device has network connectivity (UDP and TCP) to endpoint ID 11, 12, 47 and 127 described in [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).ID 184 [is also required](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges#microsoft-365-unified-domains). The following table is a summary for reference only, monitor these two links (via RSS subscription) for the up-to-date list.

| ID | Category | ER | Addresses | Ports | Notes |
| --- | --- | --- | --- | --- | --- |
| 11 | Optimize required | Yes | 52.112.0.0/14, 52.122.0.0/15, 2603:1063::/38 | UDP: 3478, 3479, 3480, 3481 | Media Processors and Transport Relay 3478 (STUN), 3479 (Audio), 3480 (Video), 3481 (Screen share) |
| 12 | Allow required | Yes | `*.lync.com`, `*.teams.microsoft.com`, `teams.microsoft.com`, `*.teams.cloud.microsoft`, `teams.cloud.microsoft`, 52.112.0.0/14, 52.122.0.0/15, 2603:1027::/48, 2603:1037::/48, 2603:1047::/48, 2603:1057::/48, 2603:1063::/38, 2620:1ec:6::/48, 2620:1ec:40::/42 | TCP: 443, 80, UDP: 443 |  |
| 47 | Default required | No | `*.office.net` , `graph.microsoft.com` | TCP: 443, 80 | Used for SlimCore downloads and background effects |
| 69 | Default required | No | `*.aria.microsoft.com`, `*.events.data.microsoft.com` | TCP: 443 | Backend communication services |
| 127 | Default required | No | `*.skype.com` | TCP: 443, 80 |  |
| 184 | Default required | No | `*.cloud.microsoft`, `*.static.microsoft`, `*.usercontent.microsoft` | TCP: 443, UDP 443 | Used for Ringtones, Noise Suppression, and other Models |

### Network architecture

![The network architecture of Teams VDI 2.](media/teams-vdi-2-network-architecture.png)

A walkthrough of the architecture in the diagram:

1. Start Teams.​
2. Teams client authenticates to Teams services. Tenant policies are pushed down to the Teams client, and relevant configurations are relayed to the app.​
3. Teams detects that it's running in a virtual desktop environment and instantiates the internal vdibridge service​.
4. Teams opens a secure virtual channel on the server​.
5. The RDP/HDX/Blast/DVC protocol transports the request to the VDI Client (Windows App, Citrix Workspace app, Horizon Client, or Amazon WorkSpaces) that previously loaded MsTeamsPlugin (client-side virtual channel component)​.
6. The VDI Client app spawns a new process called MsTeamsVdi.exe, which is the new media engine (SlimCore) used for the new optimization​. All the network activities are executed by this process.
7. SlimCore media engine (on the client) and msteams.exe (on the virtual desktop) now have a bidirectional channel and can start processing multimedia requests.​

User calls

1. Peer A selects the call button. MsTeamsVdi.exe communicates with the Microsoft Teams services in Azure, establishing an end-to-end signaling path with Peer B. MsTeamsVdi.exe collects a series of supported call parameters (codecs, resolutions, and so forth, which is known as a Session Description Protocol (SDP) offer). These call parameters are then relayed using the signaling path to the Microsoft Teams services in Azure and from there to the other peer.​
2. The SDP offer/answer (single-pass negotiation) takes place through the signaling channel, and the ICE connectivity checks (NAT and Firewall traversal using STUN bind requests) complete. Then, Secure Real-time Transport Protocol (SRTP) media flows directly between MsTeamsVdi.exe and the other peer (or Teams Transport Relays or Conference servers).

IP blocks for signaling, media, background effects, and other options are described in [this article](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

### Types of traffic handled by SlimCore on the endpoint

1. Teams media flows connectivity is implemented using standard IETF Interactive Connectivity Establishment (ICE) for STUN and TURN procedures.
2. Real-time media. Data encapsulated within Real-time Transport Protocol (RTP) that supports audio, video, and screen sharing workloads. In general, media traffic is highly latency sensitive. This traffic must take the most direct path possible and use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real-time media from a quality perspective.
    - As a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but we don't recommend it due to bad quality implications.
    - RTP flow is secured using SRTP, in which only the payload is encrypted.
3. Signaling. The communication link between the endpoint and Teams servers, or other clients, used to control activities (for example, when a call is initiated). Most signaling traffic uses UDP 3478 with fallback to HTTPS, though in some scenarios (for example, the connection between Microsoft 365 and a Session Border Controller) it uses SIP protocol. It's important to understand that this traffic is much less sensitive to latency but might cause service outages or call timeouts if latency between the endpoints exceeds several seconds.

### Bandwidth consumption

Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions. When bandwidth is insufficient, Teams prioritizes audio quality over video quality. Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30 fps (frames per second) for video and content. To learn more, read [Bandwidth requirements](prepare-network#bandwidth-requirements).

### Quality of services (QoS)

Implement QoS settings for endpoints and network devices and determine how you want to handle media traffic for calling and meetings.

- As a prerequisite, enable QoS globally in the Teams Admin Center. See [Configure QoS in the Teams admin center](meetings-real-time-media-traffic) for details on enabling the **Insert Quality of Service (QoS) markers for real-time media traffic** settings.

    Recommended initial port ranges:

    | Media traffic type | Client source port range | Protocol | DSCP value | DSCP class |
    | --- | --- | --- | --- | --- |
    | Audio | 50,000 - 50,019 | TCP/UDP | 46 | Expedited Forwarding (EF) |
    | Video | 50,020 - 50,039 | TCP/UDP | 34 | Assured Forwarding (AF41) |
    | App or screen sharing | 50,040 - 50,059 | TCP/UDP | 18 | Assured Forwarding (AF41) |
- For information on configuring Differentiated Services Code Point (DSCP) markings for Windows endpoints, see [Implement QoS in Teams clients](qos-in-teams-clients).

    Note

    Any endpoint-based marking must be applied to MsTeamsVdi.exe, the process that handles all multimedia offloading on the user's device. Refer to the [Playbook document](https://aka.ms/teams-vdi-2.0-playbook) for more information on QoS.
- For information on implementing QoS for routers, see your manufacturer's documentation.
- Setting QoS on network devices might include some or all of:

    - using port-based Access Control Lists (ACLs)
    - defining the QoS queues
    - defining DSCP markings

Important

We recommend implementing these QoS policies using the endpoint source ports and a source and destination IP address of "any". These policies catch both incoming and outgoing media traffic on the internal network.

### Technologies that aren't recommended with Microsoft Teams in VDI

1. **VPN network**. Not recommended for media traffic.
2. **Packet shapers**. Any kind of packet sniffer, packet inspection, proxies, or packet shaper devices aren't recommended for Teams media traffic and might degrade quality significantly.

### Media path, DNS and Ports on the endpoint

Media Processors and Transport relays are a critical part of the Teams calling services infrastructure in Azure, because relays allow media connectivity between two clients that would otherwise fail to communicate. Therefore, VDI Administrators must discuss the following topics with their Networking teams since VDI optimization shifts some of the networking requirements to SlimCore running on the user's device.

1. Relay discovery is DNS-based when a participant needs to allocate its own relay and a peer is not offering UDP 3478-3481. An optimized user that cannot resolve public relay names might not generate a relay ICE candidate, and the call will not establish (or establish without media). Relay names are covered by the Teams domains in Microsoft 365 URLs and IP Address ranges, including names under \*.teams.microsoft.com (e.g. \*.tr.teams.microsoft.com or \*.turn.teams.microsoft.com).
2. Verify that DNS filtering, split-horizon DNS, secure web gateways, PAC logic, or Firewall policies do not block external relay-name resolution.
3. Customers using Direct Routing need to take into account that Media Processors can also offer candidates in UDP 49152-53247 range in a non-media bypass call. Therefore, these destination UDP ports need to be allowed on the endpoint / branch office.

## Microsoft Teams PowerShell policy for optimization

The CsTeamsVdiPolicy cmdlets enabled administrators to control the type of meetings that users can create or the features that they can access while in a meeting specifically on a VDI environment, where WebRTC optimization was disabled using the VDI Partner's policy engine ([Citrix Studio](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html#enable-optimization-of-microsoft-teams), [VMware HTML5 ADMX template](https://docs.vmware.com/en/VMware-Horizon/2203/horizon-remote-desktop-features/GUID-8557C3D7-4B08-4C98-B474-97B795300A6E.html#GUID-8557C3D7-4B08-4C98-B474-97B795300A6E), or [this registry key](/en-us/azure/virtual-desktop/teams-on-avd) for AVD and Windows 365).

The default policy configurations are:

- `DisableCallsAndMeetings: False`
- `DisableAudioVideoInCallsAndMeetings: False`

This policy now has an additional argument as the only configuration point to control whether or not a user can get the new optimization mode based on SlimCore. In other words, the VDI Partner's policy engines don't control the new optimization mode:

- VDI2Optimization: Enabled (default value)

| Name | Definition | Example | Notes |
| --- | --- | --- | --- |
| New-CsTeamsVdiPolicy | Allows administrators to define new VDI policies that can be assigned to users for controlling Teams features related to meetings on a VDI environment. | `PS C:\> New-CsTeamsVdiPolicy -Identity RestrictedUserPolicy -VDI2Optimization "Disabled"` | The command shown here uses the New-CsTeamsVdiPolicy cmdlet to create a new VDI policy with the identity RestrictedUserPolicy. This policy uses all the default values for a VDI policy except one: VDI2Optimization. In this example, users with this policy can't be optimized with SlimCore. |
| Grant-CsTeamsVdiPolicy | Allows administrators to assign a Teams VDI policy at a per-user scope. Admins can control the type of meetings that a user can create, the features they can access on an unoptimized VDI environment, and whether a user can be optimized with the new optimization mode based on SlimCore. | `PS C:\> Grant-CsTeamsVdiPolicy -identity "Ken Myer" -PolicyName RestrictedUserPolicy` | In this example, a user with identity "Ken Myer" is assigned to the RestrictedUserPolicy. |
| Set-CsTeamsVdiPolicy | Allows administrators to update existing VDI policies. | `PS C:\> Set-CsTeamsVdiPolicy -Identity RestrictedUserPolicy -VDI2Optimization "Disabled"` | The command shown here uses the Set-CsTeamsVdiPolicy cmdlet to update an existing VDI policy with the Identity RestrictedUserPolicy. This policy uses all the existing values except one: VDI2Optimization; in this example, users with this policy can't be optimized with SlimCore. |
| Remove-CsTeamsVdiPolicy | Allows administrators to delete a previously created Teams VDI policy. Users with no explicitly assigned policy fall back to the default policy in the organization. | `PS C:\> Remove-CsTeamsMeetingPolicy -Identity RestrictedUserPolicy` | In the example shown previously, the command deletes the restricted user policy from the organization's list of policies and removes all assignments of this policy from users with the policy assigned. |
| Get-CsTeamsVdiPolicy | Allows administrators to retrieve information about all the VDI policies configured in the organization. | `PS C:\> Get-CsTeamsVdiPolicy -Identity SalesPolicy` | In this example, Get-CsTeamsVdiPolicy is used to return the per-user meeting policy that has an Identity SalesPolicy. Because identities are unique, this command doesn't return more than one item. |

## Feature list with the new optimization

The following table compares the new optimization feature set with the WebRTC-based optimization. The new optimization supports Windows endpoints for AVD/W365, Citrix, Omnissa and Amazon. Mac is only supported on AVD/W365 and Citrix. WebRTC is supported on AVD/W365, Citrix, and Omnissa.

| Feature | Available on the new optimization (Windows and MAC) | Available on WebRTC (Windows and MAC) |
| --- | --- | --- |
| 1080p | Yes | No |
| Hardware acceleration on endpoint | Yes ^1^ | No |
| Gallery View 3x3 and 7x7 | Yes | No |
| Quality of Service | Yes | No |
| Noise suppression | Yes | Yes (AVD) |
| Voice isolation and Face enrollment | Yes ^6^ | No |
| HID | Yes (Windows only) | Yes (AVD and Omnissa) |
| Presenter mode | Yes | No |
| Teams Premium | Check the Teams Premium page | Check the Teams Premium page |
| Organizational custom backgrounds | Yes (Teams Premium license required) | No |
| User-uploaded background effect | Yes ^2^ | No |
| Zoom +/- | Yes | No |
| Media bypass, Location-based routing, Operator Connect ^3^ | Yes | No |
| Call quality dashboard and Teams admin center | Yes | Limited |
| Published app/Remote app/Cloud apps | Yes (AVD/W365 and Citrix) | Yes (for AVD, Windows only) |
| Give/Take control | Yes | Yes |
| App sharing | Yes | Yes |
| e911 | Yes | Yes |
| Simulcast | Yes | Yes |
| Share system audio | Yes (Windows only) | Yes |
| Secondary ringer | Yes | Yes |
| Background blurring | Yes | Yes |
| Organizers can schedule meetings and events | Yes | Yes |
| Organizers, presenters, and attendees can join meetings and events up to 1,000 attendees, such as webinars | Yes | Yes |
| Organizers and presenters can join [large-scale](plan-events) events, such as town halls | Yes | No |
| Attendees can join [large-scale](plan-events) events, such as town halls | Yes | Yes |
| Organizers and presenters of meetings and events up to 1,000 attendees, such as webinars, are optimized | Yes ^4^ | Yes |
| Organizers and presenters of [large-scale](plan-events) events, such as town halls, are optimized | Yes | No |
| Attendees in meetings and events up to 1,000 attendees, such as webinars, are optimized | Yes | No |
| Attendees in [large-scale](plan-events) events, such as town halls, are optimized | Yes (public preview) | No |
| Annotations | Only as presenter. ^5^ | No |

^1^ Graphics hardware acceleration requires DirectX 9 or later, with WDDM 2.0 or higher for Windows 10 (or WDDM 1.3 or higher for Windows 10 Fall Creators Update).^2^ If you join a meeting as a guest, this feature isn't supported. Placing background files via scripts in the user's Appdata profile isn't supported (users must upload the desired custom file through Teams, which is then copied to the user's OneDrive -provided it has sufficient storage capacity).^3^ Operator Connect in India with mobile numbers requires latitude and longitude access from the endpoint's OS and local internet breakout. Operator Connect with wireline or wireless numbers can use IP/subnet or internet breakout to map to a location. It's critical to ensure that the endpoint OS detects the correct country, as routing traffic through breakouts outside India can cause the endpoint OS to misidentify the location. For more details, check [Choose a wireline or wireless number](operator-connect-india-plan#choose-a-wireline-or-wireless-number).^4^ NDI (Network Device Interface), the modern solution for connecting media devices (such as a studio camera and mixer) isn't supported for producers.^5^ Viewers don't see the annotations (they're hidden by the incoming video window overlay).^6^ Voice and face enrollment relies on the VDI Provider camera/mic redirection (for example, Citrix HDX, Omnissa RTAV, Microsoft RDP, etc.). See the Known issues section.

## SlimCore user profile on the endpoint

The new solution for VDI stores user-specific data on the endpoint in the following locations, depending on your vendor:

- `C:\users\<user>\AppData\Local\Packages\Microsoft.Teams.SlimCoreVdiHost.win-x64_8wekyb3d8bbwe\LocalCache\Local\Microsoft\TeamsVDI\<vdi provider>-tfw-<cloudname>\`

Older SlimCore MSIX packages (before the new Split MSIX Packages with Host and Framework) stored user-specific data on:

- `C:\users\<user>\AppData\Local\Microsoft\TeamsVDI\<vdi provider>-default-<cloudname>\`

Logs, ringtones, configurations, and AI or ML models (used in noise suppression, bandwidth estimation, etc.) are saved in this location. Additionally, custom background effects uploaded to Teams are then downloaded from the user's OneDrive to the 'downloads' folder in this location (therefore, a OneDrive account with enough storage is required for the feature to work). If these AppData folders are purged after a user signs out (for example, locked-down thin clients without roaming profiles), MsTeamsVdi.exe recreates them and downloads the user-specific configuration (about 12 MB of data). User-specific data can grow to ~100 MB (including ~60 MB for logs).

Important

Locked-down thin clients must allow these locations to be read/write. Otherwise, the new optimization might fail. For older Windows 10 1809 Thin Clients (such as Dell Wyse 5070 and similar models), SlimCoreVdi's processes write AppData to a virtualized file storage, hence the folder location for SlimCore's user profile is (depending on the SlimCore MSIX package): `C:\Users\<user>\AppData\Local\Packages\Microsoft.Teams.SlimCoreVdiHost.win-x64_8wekyb3d8bbwe\LocalCache\`.

### SlimCore installation and upgrade process in locked down Thin Client environments (optional)

By default, the MsTeamsPlugin automatically downloads and installs the right SlimCore media engine version without user or Admin intervention. But customers on restricted network environments in the branch office can opt for an alternative SlimCore distribution process, without requiring the endpoint be able to fetch SlimCore packages using https from Microsoft's public Content Delivery Network.

Note

For an updated list of SlimCore packages that match their corresponding Teams version, [check this table](/en-us/officeupdates/teams-app-versioning#vdi-slimcore-version-2-msix-packages).

Important

If you must choose this method, you must guarantee that:

1. [Teams auto-updating is disabled](teams-client-vdi-requirements-deploy#disable-teams-autoupdate-in-non-persistent-vdi) in the virtual desktop.
2. The SlimCore packages are pre-provisioned to the endpoint's local storage or network share before you upgrade Teams in the virtual desktop. Any newer Teams version requests a matching new version of SlimCore and if the plugin can't find it, the user is in fallback mode (server-side rendering).

This circumstance happens because Teams and SlimCore versions must match.

#### Configuration steps

1. On the user's endpoint (thin client/fat client), you must create the following regkey:

    - Location for Citrix: HKLM\SOFTWARE\WOW6432Node\Microsoft\Teams\MsTeamsPlugin
    - Location for Azure Virtual Desktop/W365/Omnissa: HKLM\SOFTWARE\Microsoft\Teams\MsTeamsPlugin
    - Name: MsixUrlBase
    - Type: REG\_SZ
    - Data: Either local storage or network storage UNC path, such as file://C:/Temp or file://ComputerName/SharedFolder.

    The regkey defines the Base URL.
2. Additionally, admins must download the exact SlimCore MSIX Package version from Microsoft's Content Delivery Network that matches the Teams version you're planning to deploy in the future.

    Important

    The MSIX package needs to match the architecture or bitness of the Citrix Workspace app (x86 or x64) or Windows App/Horizon clients (which are 64-bit only): `Microsoft.Teams.SlimCoreVdiHost.<platform>-<architecture>.msix`.
3. To preserve the structure, place the MSIX in a specific folder with the version within the location specified in the registry key. For example, C:\Temp\2024.4.1.9\Microsoft.Teams.SlimCoreVdiHost.win-x64.msix (same for Framework) or //ComputerName/SharedFolder/2024.4.1.9/.

    Note

    If the Plugin can't find a SlimCore MSIX package in the local or network storage, it automatically attempts to download it from the Microsoft public Content Delivery Network as a fallback.

### Unified Write Filters (UWF)

Customers with Thin Clients with [Unified Write Filters](/en-us/windows/configuration/unified-write-filter/) applied should create the following exclusions in order to allow SlimCore MSIX packages to be provisioned and activated:

- uwfmgr.exe file Add-Exclusion "C:\Program Files\WindowsApps"
- uwfmgr.exe file Add-Exclusion "C:\Users\User\AppData\Local\Packages\Microsoft.Teams.SlimCoreVdiHost.win-x64\_8wekyb3d8bbwe"

#### Thin Clients with RAM Disks

Thin Clients like HP/DELL that have a RAM Disk manager where environmental variables TEMP/TMP are pointing to a RAM Disk (for example, Z:) will fail to provision SlimCore MSIX packages ("sc\_host\_install\_error":"{"val":4390,"cat":"windows"}", when looking in the VM's Event Viewer description entries for "Microsoft Teams VDI"). The workaround is to create a new system variable MSTEAMSVDI\_BITS\_TMP\_PATH and point it to a temporary physical disk location (like C:\TMP, or C:\TEMP). This allows the Background Intelligent Transfer Service to successfully download and provision SlimCore.

## Cross Cloud Collaboration

Organizations in Microsoft’s Public, GCC (Government Community Cloud), GCCH (Government Community Cloud High), and DoD (Department of Defense) clouds can now collaborate with each other efficiently with the new optimization (this collaboration applies to both intra-company and inter-company). This collaboration often involves access to shared content, which requires authenticated access. Previously, collaboration across clouds via Teams was limited due to the lack of optimization in audio/video. With Teams and Slimcore based optimization, users can now enjoy a high definition user experience. For more information on Cross Cloud, check [this link](/en-us/microsoftteams/cross-cloud-meetings).

The following scenarios are supported:

- **Cross Cloud Anonymous** allows the scenario where a user is signed into Cloud A in Teams, and joins a meeting in a different Cloud B anonymously. Check [Manage anonymous participant access to Teams meetings and events (IT admins)](/en-us/microsoftteams/anonymous-users-in-meetings) for more details.
- **Cross-cloud Guest Access** extends functionality to allow a user to participate in rich collaboration experiences in teams, channels, documents, and Teams meetings for a full experience including audio/video optimization, screen share, file share and both 1:1 and 1:n chat. Check [here](/en-us/microsoft-365/solutions/collaborate-guests-cross-cloud?view=o365-worldwide&amp;preserve-view=true) for more details.
- **Cross-cloud authenticated meeting join** delivers the ability for a Teams user to join a meeting in another cloud while signed into their account in their home tenant. This feature provides the meeting host the ability to validate the identities of meeting participants without granting those participants any access to the host tenant.

Minimum versions: Teams 25060.205.3499.6849. Remote Desktop Client 1.2.6186. Citrix Plugin 2024.41.1.1.

Known issues:

- Omnissa Horizon is currently not supported
- HID only works in the primary Cloud.
- Muting from Teams UI doesn't play the "Mute/Unmuted" voice command in the nonprimary Cloud.
- More Peripherals limitations are described [here](/en-us/microsoftteams/troubleshoot/meetings/known-issues-teams-certified-peripherals)
- Any user signed into multiple clouds (Multi Cloud or Cross Cloud), can't get optimized with WebRTC. If the user roams to a device, which doesn't support SlimCore, they're in fallback mode (server-side rendering) until they roam back to a SlimCore capable device. This issue happens because WebRTC doesn't support any Cross Cloud features.
- If Cross Cloud features don't appear to work even though the user meets the minimum requirements, you can quit Teams (after it gets optimized with SlimCore) and try to delete a file called ecs\_settings.dat64 at the following path: %localappdata%\packages\MSTeams\_8wekyb3d8bbwe\LocalCache\microsoft\MSTeams. Restart Teams.

## Citrix virtual channel allow list

The [Virtual channel allow list](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/secure/virtual-channel-security#adding-virtual-channels-to-the-allow-list) policy setting in CVAD enables the use of an allow list that specifies which virtual channels can be opened in an ICA session. When enabled, all processes except the Citrix built-in virtual channels must be stated. As a result, more entries are required for the Teams client to be able to connect to the client-side plugin (MsTeamsPluginCitrix.dll).

With Citrix Virtual Apps and Desktops 2203 or later, the virtual channels allow list is **enabled by default**. These default settings deny access to the Teams custom virtual channels as the allow list **doesn't** include the Teams main process name.

The Teams client requires three custom virtual channels to function: MSTEAMS, MSTEAM1 and MSTEAM2. Ms-teams.exe accesses these channels. You can use wildcards to allow the ms-teams.exe executable and custom virtual channel:

- MSTEAMS, C:\Program Files\WindowsApps\MSTeams\*8wekyb3d8bbwe\ms-teams.exe
- MSTEAM1, C:\Program Files\WindowsApps\MSTeams\*8wekyb3d8bbwe\ms-teams.exe
- MSTEAM2, C:\Program Files\WindowsApps\MSTeams\*8wekyb3d8bbwe\ms-teams.exe

1. Wildcard support is available in:

    - VDA 2206 CR.
    - VDA 2203 LTSR from CU2 onwards.
2. The VDA machines must be rebooted for the policy to take effect.

Note

VDA 2603 or higher now allows the three virtual channels by default, without requiring the specific configuration of the Citrix Studio policy ('Allowed').

## Screen sharing

Both outgoing screen sharing and app sharing behave differently in optimized VDI when compared to the nonoptimized Teams desktop client. As such, these activities require encoding that employs the user's device resources (for example CPU, GPU, RAM, network, and so on). From a network perspective, sharing is done directly between the user's device and the other peer or conference server.

Note

**Virtual Machine-side screensharing (vmss)**For Omnissa, Amazon or for MAC (Citrix or AVD/W365), the sharing is done directly between the user's virtual machine -the presenter- and the other peer -viewer- or conference server, therefore administrators must allow ID 11 and 12 on the VM's network as described in [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams). This is because when a VDI user selects the screen sharing button, a p2p audio/video call is escalated to a group call, allowing Teams to share content directly from the virtual machine. Teams-optimized viewers still receive the incoming screenshare stream directly on their endpoint, where offloading takes place.This feature is currently in Public Preview for Windows users as well (Citrix, AVD/W365). Check the 'Network Architecture' diagram above for more details. Administrators can detect these outgoing screensharing sessions in Teams Admin Center (where they appear as an additional "Screen sharing stream" session for the user) or CQD (where they appear as "Microsoft Teams VDI (VM Screenshare)" on the User Agent Category)

Tip

The following registry key can be created on the VM to control vmss CPU resource consumption:

- **Path:** HKCU\Software\Microsoft\Teams\VMSS or HKLM\Software\Microsoft\Teams\VMSS (HKLM takes precedence over HKCU)
- **Name:** MaxFPS (DWORD)
- **Value:** anywhere between 1 and 15

A typical PowerPoint session consumes 3fps. If the user clicks on the "optimize" button in the sharing toolbar (intended for sharing videos), Teams attempts to ramp up to 15 fps and a higher CPU impact is expected. Capping MaxFPS somewhere between 5-10 can help reduce impact in this scenario.

**Sizing guidelines**

The following recommendations are derived from Microsoft's internal load testing. Because test outcomes can vary across deployments, customers should conduct their own validation in their specific environments. Results are influenced by several factors, including VM sizing, workload patterns, and, most importantly, the presence of GPU acceleration.

On a single-user 4vCPU/16GB RAM VM with an Intel Xeon CPU E5-2673 v4 @ 2.30GHz (with no GPU or Quick Sync, hence using H264 software encoding),

- With a 4K external monitor, the memory usage for Microsoft Teams on the VM consumed and additional ~510 MB and an additional ~ 7-8% CPU (at 3 fps) or 25-30% CPU (at 15 fps, when the user clicks 'Optimize for video' in the UI toolbar).
- With a 2K external monitor, the memory usage for Microsoft Teams on the VM consumed and additional ~320 MB and an additional ~ 3-4% CPU (at 3 fps) or 20-25% CPU (at 15 fps, when the user clicks 'Optimize for video' in the UI toolbar).

A full monitor screen share captures the Teams call monitor and makes it visible to the other participants. The video elements inside aren't visible and instead are seen as blank squares. When doing app sharing, only the application being shared is visible to the other participants and the call monitor isn't captured.

### Citrix App Protection and Microsoft Teams compatibility

Users with App Protection enabled can still share their screen and apps while using the new optimization. Sharing requires VDA version 2402 or higher, and CWA for Windows 2309.1 or higher. Users on lower versions end up sharing a black screen instead when the App Protection module is installed and enabled.

### AVD Screen Capture Protection and Microsoft Teams compatibility

Users with [Screen Capture Protection](/en-us/azure/virtual-desktop/screen-capture-protection?tabs=intune) (SCP) enabled to block screen capture on the remote desktop client (**Block screen capture on client**) can still share their screen and apps while using the new SlimCore-based optimization for Microsoft Teams. Sharing requires the following minimum versions: Teams 25060.205.3499.6849, and Remote Desktop client 1.2.6081 or Windows App 2.0.379.

Users on lower versions end up sharing a black screen instead with SCP enabled.

## AVD RemoteApp / W365 Cloud Apps and Citrix Virtual Apps

If you publish the Microsoft Teams application with RemoteApp in Azure Virtual Desktop, Cloud Apps in Windows 365 or Citrix Virtual Apps (published apps), users can get optimized with the new architecture if they meet the following minimum requirements:

- Windows App for Windows 2.0.964.0
- Citrix Plugin 2026.15.1.1
- Microsoft Teams 26043.2016.4478.2773

Known issues:

- Give/Take Control is currently not available.
- Mac endpoints aren't supported, so optimization won't take place, and users are in fallback mode (also known as server-side rendering). Upgrade to Microsoft Teams 26093.411.4595.9804 or higher if users see inconsistent behaviors and aren't in fallback mode.

## Custom background effects

The new optimization allows users to keep their background private during Teams meetings by blurring or changing their background, uploading their own images, or choose from background images already in Teams. Uploading custom images requires the user to upload the file via Teams UI, therefore the file must be available in the virtual desktop (directly or indirectly, via Client Drive Mapping). Teams will then upload the file to the user's OneDrive folder and instruct the media engine running on the user's device to download it for local processing. The user's device network must allow access to graph.microsoft.com. Placing background files via scripts in the user's Appdata profile on their local isn't supported (users must upload the desired custom file through Teams, which is then copied to the user's OneDrive -provided it has sufficient storage capacity). If you join a meeting as a guest, custom background feature isn't supported.

## Large-scale events (such as townhalls) and live events

Attendees joining these types of events aren't optimized (WebRTC or SlimCore), hence they default to server-side rendering, incurring in high resource consumption on the virtual desktop (mostly CPU, RAM, and virtual channel bandwidth). Therefore, Microsoft eCDN and Peer-to-Peer (P2P) traffic are carried out on the virtual machines themselves, since there's no offloading possible. For more details, see [this article](/en-us/ecdn/technical-documentation/vdi).

For Presenter/Organizer role support, see the Feature list with the new optimization table earlier in this article.

Note

Townhall optimization is now in public preview for Windows endpoints. Minimum requirements: Teams 26225.1803.5037.3180. Windows app 2.0.1186.0, Citrix Plugin 2026.15.1.1, Omnissa Horizon Client 2606, Amazon WorkSpaces Client 5.33.0. All existing attendee interactivity features are supported, including Live captions, DVR, Reactions, Streaming chat, Q&A, and both first‑party and third‑party enterprise CDNs (eCDNs).

## Peripherals in VDI

When Teams is optimized with SlimCore, cameras, microphones, location, and speakers connected to your physical device are mapped on your virtual desktop. Teams enumerates all the detected devices, prioritizing Default Communication Devices (as seen in the mmsys.cpl panel when run on the user's device). SlimCore-based optimization supports Human Interface Devices (HID) for [Teams certified headsets](https://aka.ms/teamsdevices), allowing users to mute/unmute and increase/decrease volume themselves directly from their headset. A Microsoft Teams button on a certified Teams device isn't currently supported.

Tip

Using Policy CSP - Privacy, you can preemptively specify a per-app setting for camera, microphone, and location by stating SlimCore's Package Family Name (Microsoft.Teams.SlimCoreVdiHost.win-x64\_8wekyb3d8bbwe). These settings are [LetAppsAccessCamera_ForceAllowTheseApps](/en-us/windows/client-management/mdm/policy-csp-Privacy#letappsaccesscamera_forceallowtheseapps), [LetAppsAccessMicrophone_ForceAllowTheseApps](/en-us/windows/client-management/mdm/policy-csp-Privacy#letappsaccessmicrophone_forceallowtheseapps), [LetAppsAccessLocation_ForceAllowTheseApps](/en-us/windows/client-management/mdm/policy-csp-Privacy#letappsaccesslocation_forceallowtheseapps)

Note

With some peripherals, two Unified Communications apps running side by side can cause HID collisions where active calls get disconnected.

> 
> See the Known issues section. This issue is fixed in Teams 26276.x.x.x (for Windows/Mac users in Public Preview / Early Access only): When multiple Teams apps run on the same endpoint—for example, Teams locally and Teams in a virtual desktop—only one app at a time controls the connected audio device’s buttons, such as **mute, answer, and hang up**. With Teams 26276.x.x.x, the app now displays a dialogue **“Transfer audio device buttons to this app?”** when it initializes HID button control and another Teams app already owns it. Transferring button control does not transfer an ongoing call or change the selected microphone and speaker. Administrators can override this behavior by configuring a registry key in the endpoint/user device. This key specifies which type of Teams instance (native or VDI) automatically takes control of headset buttons. When an instance matching the configured preference initializes headset-button control, it can take control from another Teams instance without displaying a transfer confirmation dialog. HKEY\_CURRENT\_USER\Software\Microsoft\Teams\HID Name: DefaultHidOwner Type: REG\_SZ Value: default\_to\_native (locally installed Teams can automatically take HID ownership) Value: default\_to\_vm (Teams running on VDI can automatically take HID ownership, even from other Teams VDI instances - last launch wins)

Users can still override the default or administrator-configured logic by going to Settings/Devices/Audio device button controls and selecting *Transfer controls to this app.*

HID can be completely disabled via registry key on Teams 25060.205.3499.6849 or higher, where the key can be created on the endpoint. (The key can also be created on the VM if you have the 2025.24.1.3 Plugin (Citrix), or the Remote Desktop client 1.2.6275 / Windows App 2.0.550.0).

> 
> HKEY\_CURRENT\_USER\Software\Microsoft\Teams\HID Name: DisableHidManagerV1 Type: DWORD Value: 1 (when set to 1, it disables HID) (If set to 0 or the key isn't present, HID is enabled)

## Monitoring API

Administrators can create custom scripts to [query](/en-us/windows/win32/fileio/obtaining-directory-change-notifications) vdi\_connection\_info.json - this file in the virtual machine contains information about the current and last session, such as optimization status, peripherals, and software versions of the different components.

Location (in the VDA or Remote Desktop Host): C:\Users&lt;username&gt;\AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\LocalCache\Microsoft\MSTeams\tfw

Typical use cases for the monitoring API are:

- Administrators deploying an automation script in a VDA or Remote Desktop Host to detect whether the client endpoint operating system changed since the last connection. The script consumes the contents of the JSON file to compare the last two sessions' values, and issue their own alerts/pop-up messages.
- Developers creating third-party apps that report the current state of the VDI optimization connection. The script consumes the contents of the JSON file to retrieve all available connection, optimization, and device information of the current Teams session.

Json File Structure:

- Timestamp - vdiConnectedState.timestamp indicates the timestamp of the session connection
- VDI Optimization - vdiConnectedState.vdiMode indicates the optimization version (remains static throughout the VDI session)
- Connected State - connectedStack (remote = optimized, local = not optimized) (remains static throughout the VDI session)
- SlimCore Version on the endpoint - remoteSlimCoreVersion
- VdiBridge Version on the VM - bridgeVersion
- MS Teams Plugin Version on the endpoint - pluginVersion
- Teams Version - vdiVersionInfo.teamsVersion
- Client Platform - vdiVersionInfo.clientPlatform
- VDI Client (CWA or Windows App) version - vdiVersionInfo.rdClientVersion
- VM OS Version - vdiVersionInfo.vmVersion
- Available Peripheral Devices - devices.speakers.available, devices.cameras.available, devices.microphones.available (real time update to the json file)
- Selected Peripheral Devices - devices.speakers.selected, devices.cameras.selected, devices.microphone.selected (real time update to the json file)
- Secondary Ringer - devices.secondaryRinger (real time update to the json file)

Note

When in WebRTC optimization, only the vdiConnectedState is populated, indicating which optimization the session is currently in. There's no vdiVersionInfo and device information stored in the JSON file for the session. When no optimization is available, there aren't updates made to the JSON file.

## Call Quality Dashboard in VDI

Call Quality Dashboard (CQD) allows IT Pros to use aggregate data to identify problems creating media quality issues by comparing statistics for groups of users to identify trends and patterns. CQD isn't focused on solving individual call issues, but on identifying problems and solutions that apply to many users.

VDI user information is now exposed through numerous dimensions and filters. Check [this page](dimensions-and-measures-available-in-call-quality-dashboard) for more information about each dimension.

Note

The new Quality of Experience (QER) template is available in the Power BI query templates for CQD download. Version 8 now includes templates for reviewing VDI client-focused metrics. In the VDI Report, users optimized with the new architecture are categorized as "VDI 2.0 Optimized", while "Optimized" refers to the WebRTC optimization.

Important

- In CQD, the dimension 'Second Client VDI Mode' VdiMode value (x2xx) represents both VDI SlimCore Optimized and VDI SlimCore Not Connected (Unoptimized Fallback). This duplication can lead to misinterpretation, as poor call quality in an unoptimized session might appear to be an issue with VDI SlimCore Optimization. The dimension 'Second Client VDI Is Optimized' is the accurate way to display if the user was optimized or not, as this dimension computes an end-to-end resulting value between VDI Mode and 'Second Client VDI Connected State'. End to end optimization with SlimCore only happens when Connected State is 'Connected'.
- The value 'Inactive' in CQD Reports for the dimension 'Client VDI Is Optimized' means the Administrator has disabled the Teams optimization policy (for example, via Citrix Studio policy 'Microsoft Teams redirection', or via registry keys for Omnissa and AVD/Windows 365). This results in VdiMode x0xx (second digit is a zero). Users in this scenario will revert to server-side rendering, where all the multimedia is handled by the virtual machine with no offloading to the endpoint.
- In Citrix environments, where the VDA was installed on the user's Workstation (Remote PC), the Teams session might be flagged as 'Inactive' or unoptimized if the user launches Teams on the Workstation (that is, locally).

#### Query fundamentals

A well-formed CQD query/report contains all three of these parameters:

- [Measurement](dimensions-and-measures-available-in-call-quality-dashboard#measurements)
- [Dimension](dimensions-and-measures-available-in-call-quality-dashboard#dimensions)
- [Filter](dimensions-and-measures-available-in-call-quality-dashboard#filters)

Some examples of a well-formed query would be:

1. "Show me Poor Streams [Measurement] for VDI Users with the new Optimization [Dimension] for Last Month [Filter]."
2. "Show me Poor App sharing [Measurement] by Total Stream Count [Dimension] for Last Month AND where First OR Second Client VDI mode was optimized [Filters]."

You can use many Dimension and Measurement values as filters too. You can use filters in your query to eliminate information in the same way you'd select a Dimension or Measurement to add or include information in the query.

#### What UNION does

By default, Filters allow you to filter conditions with the AND operator. But there are scenarios where you might want to combine multiple Filter conditions together to achieve a result similar to an OR operation. For example: To get all streams from VDI Users, UNION provides a distinct view of the merged dataset. To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.

#### Caller and Callee location

CQD doesn't use Caller or Callee fields, instead it uses **First** and **Second** because there are intervening steps between the caller and callee.

- **First** is always the server endpoint (for example, Audio-Video Multipoint Control Unit or the Media Processor Server) if a server is involved in the stream.
- **Second** is always the client endpoint, unless it's a server-server stream.

If both endpoints are the same type (for example, a person-to-person call), first versus second is set based on the internal ordering of the user agent category to make sure the ordering is consistent.

## Known issues

- For Omnissa (Windows), Citrix/AVD (Mac) and Citrix/AVD (Windows endpoints in Public Preview), Presenter (and by extension, the viewer) might experience mouse dragging or cursor lag while app sharing. If the presenter stops and reinitiates app sharing, the lag is not present anymore. This is fixed in Teams 26149.x.x.x or higher.
- For Omnissa (Windows), Citrix/AVD (Mac) and Citrix/AVD (Windows endpoints in Public Preview), anonymous VDI users trying to join a meeting that has Captcha enabled are not able to share their screens.
- For voice or face recognition enrollment (Teams/Settings/Recognition), users can't change the camera/mic from the drop-down menu. It will always use the default system devices that are available to the Virtual Desktop through the RDP/HDX/Blast/DCV protocol itself. Therefore, Administrators have to ensure the VM/Teams has access to them by configuring the respective policies for peripheral redirection.
- Volume mixer under System/Settings/Sound in the virtual machine can't control volume levels if Teams is optimized. Users must rely on the built-in volume sliders in Teams audio settings, or the volume mixer on the endpoint itself.
- Screen Capture Protection (SCP) causes the presenter's screen to show as a black screen with only the mouse cursor on top (as seen by the receiving side). This issue is fixed in Teams 25060.205.3499.6849 and Remote Desktop client 1.2.6081 or Windows app 2.0.379.
- If you lock the virtual machine (VM) during an active call, the call disconnects. This issue is fixed in 25094.303.3554.9058 or higher versions. Endpoint locking doesn't result in camera, mic, and screen sharing to automatically turn off.
- Calls drop on Teams running on the local machine that has an HID peripheral connected if a user launches a virtual desktop from that same local machine and logs into Teams. This issue can also happen if the user had an active virtual desktop and launches a second one that has Teams installed (or other Unified Communications apps that use optimization). This has been fixed in Teams 26276.x.x.x (currently only for Public Preview / Early Access users)
- Camera self-preview isn't supported at this time (either under Settings/Devices, or while on a call when selecting the down arrow on the camera icon).
- In the Control Panel/Apps/Installed apps of the endpoint, users see multiple "Microsoft Teams VDI" entries (one for every Slimcore package installed). The newer Split MSIX Package fixes this issue, where 'Microsoft Teams VDI Optimizer' is the only app that shows on the menu (and older 'Microsoft Teams VDI' entries will be cleaned up automatically after a certain period of time).
- When doing full monitor screen sharing, the call monitor window is visible for the other participants (without any video content inside).
- Users trying to take a screenshot of Microsoft Teams content (for example incoming screen sharing, or video feeds) aren't able to capture any content, because it's rendered (offloaded) in the user's device instead. Hence, a black square is captured. This limitation doesn't apply to PowerPoint Live, because that modality isn't offloaded (in other words, it's rendered on the virtual machine by the Teams app). Citrix customers can implement [this workaround](https://support.citrix.com/external/article/CTX267714/take-a-screenshot-of-browser-content-whe.html) to take screenshots, or use the [Citrix snipping tool.](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/graphics/introduction/citrix-snipping-tool-integration-in-assistant.html)
- In Citrix, app sharing sessions might freeze for the other participants if the presenter is on both VDA (virtual delivery agent) version 2402 and CWA for Windows 2309.1 (or higher versions).

    - The issue happens when a video element is destroyed.
        - For example, a participant turns off their camera in the middle of the app sharing session.
        - If someone turns their camera **on** only, there's no issue because the video element is created, not destroyed.
        - If the presenter maximizes the call monitor (which destroys the self preview of what the presenter is sharing).
    - Stopping and resharing the window should resolve the issue.
    - This issue is resolved in Teams 24335.206.X.X or higher versions.
- In CQD, VdiMode (x2xx) represents both VDI SlimCore Optimized and Unoptimized Fallback, which might misattribute poor call quality. For more information, see the Call Quality Dashboard in VDI section in this article.
- For Amazon WorkSpaces, Share System Audio (Include Computer Audio), and screen sharing from chat aren't supported.