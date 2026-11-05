---
layout: Conceptual
title: Troubleshooting the VDI 2.0 solution for Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/vdi-2-troubleshooting
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
ms.date: 2026-11-05T00:00:00.0000000Z
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
description: Learn about troubleshooting Teams for Virtualized Desktop Infrastructure (VDI) 2.0 issues.
ms.localizationpriority: medium
locale: en-us
document_id: 6a89f001-6cbb-bf45-1d49-818e16deb9c3
document_version_independent_id: 6a89f001-6cbb-bf45-1d49-818e16deb9c3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/vdi-2-troubleshooting.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: vdi-2-troubleshooting
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/vdi-2-troubleshooting.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: bc108338-c73c-2506-6c88-d0e9bd02d904
---

# Troubleshooting the VDI 2.0 solution for Teams - Microsoft Teams | Microsoft Learn

When troubleshooting the new Slimcore-based optimization for Microsoft Teams, you need to know if users are optimized with the legacy WebRTC stack or the new stack. They may also end up in the fallback mode "SlimCore Media Not Connected" (or server-side rendering).

- Not optimized with SlimCore and instead you see:"Azure Virtual Desktop Media Optimized" "Citrix HDX Optimized"

    - Error Codes 2000 ("No Plugin") and 2003 ("Virtual Channel not allowed") are the most likely causes.

    1. Make sure your 'Virtual Channel Allow list' policy in Citrix Studio is properly configured to allow MSTEAMS, MSTEAM1, MSTEAM2.
    2. Make sure the endpoint has the plugin, and the VDI Client with Process Explorer loads it:
        1. Run [process explorer](/en-us/sysinternals/downloads/process-explorer).
        2. Enable the bottom pane and switch to the DLL tab.
        3. On Azure Virtual Desktop, look for the msrdc.exe process and ensure the MsTeamsPluginAvd.dll is loaded.
        4. On Citrix, look for the wfica32.exe process and ensure the MsTeamsPluginCitrix.dll is loaded.
    3. Restart the Teams app. It requires one restart to transition from WebRTC to SlimCore, when the plugin is detected for the first time.
    4. If the problem persists, check Event Viewer in the virtual machine (VM) for **Microsoft Teams VDI**-related errors (Teams 24123.X.X.X or higher).
- Not optimized with SlimCore and instead you see: "Azure Virtual Desktop SlimCore Media Not Connected" or "Citrix SlimCore Media Not Connected".

    - Check the Troubleshooting SlimCoreVdi MSIX deployment errors section. MSIX or AppX-related errors are the most likely reasons for this error.

## Teams Client Health dashboard

[Teams client health](/en-us/microsoftteams/teams-client-health) inside Teams Admin Center is an all-new page with a set of data, insights, and tools to help administrators troubleshoot and resolve VDI issues. Under the "Issues" tab, administrators can find "VDI optimization failure" errors, with descriptions and remediation actions to manage and fix issues before they impact end user productivity or cause further escalations. These errors are typically actionable - either via GPOs, Network settings, configurations or AppX. They are caused by MSIX-related activities when the Plugin tries to install/load/deploy SlimCore, or missing configurations like the Citrix Virtual Channel Allow List, or missing Plugin. [The error codes are mapped in the table below.](/en-us/microsoftteams/vdi-2-troubleshooting#connection-error)

Tip

The information exposed in TCH is invaluable for the administrator - both as a proactive and reactive monitoring tool. Microsoft recommends reviewing the information on a daily/weekly basis and creating the corresponding automated reports.

![Screenshot that shows the Teams client health page.](media/vdi-2-troubleshooting/tch.png)

## Teams logs for VDI

Teams logs can be collected by selecting Ctrl+Alt+Shift+1 while running Teams on a VM. This action produces a ZIP folder in the Downloads folder. Inside the PROD-WebLogs-\*.zip file, look for the Core folder.

## Vdi\_debug.txt (main file for VDI-related information)

| Azure Virtual Desktop/W365 | Citrix |
| --- | --- |
| "vdiConnectedState": {"connectedStack": "remote"}, "vdiVersionInfo": {"bridgeVersion": "2024.18.1.11", "remoteSlimcoreVersion": "2024.18.01.11", "nodeId": "1051a908af6b160e", "clientOsVersion": "10.0.22631", "rdClientVersion": "1.2.5405.0", "rdClientProductName": "Microsoft® Remote Desktop", "pluginVersion": "2024.14.01.1", "screenShareFallback": true} | "vdiConnectedState": {"connectedStack": "remote"}, "vdiVersionInfo": {"bridgeVersion": "2024.18.1.14", "remoteSlimcoreVersion": "2024.18.01.14", "nodeId": "ffffffff93eaee6a", "clientOsVersion": "10.0.22631", "rdClientVersion": "24.3.0.64", "rdClientProductName": "Citrix Workspace", "pluginVersion": "2024.15.01.3", "screenShareFallback": true} |

- **vdiConnectedState**shows the current active calling stack.
    - **connectedStack**: **remote** indicates Teams successfully connected to the remote endpoint through the virtual channel. It doesn't necessarily mean the calling stack is successfully initialized, so the user can still encounter calling-related failures, such as being unable to start a call.
    - **connectedStack**: **local** indicates the virtual channel connection failed. The user is now on fallback mode.
- **vdiVersionInfo**provides useful information for the Teams client and the endpoint.
    - **bridgeVersion** is tied to the version of the Teams desktop client running on the VM.
    - **remoteSlimcoreVersion** is the version of the SlimCore VDI that's available on the endpoint.
    - **nodeId** is a unique ID tied to the endpoint.
    - **clientOsVersion** is the OS version for the endpoint.
    - **rdClientVersion** is the version of the remote desktop client running on the endpoint, which is used to connect to the VM.
    - **rdClientProductName** is the name of the remote desktop client running on the endpoint.
    - **pluginVersion** is the version of the plugin that is integrated into the remote desktop client.

## Diagnostics-logs.txt

This file might also be found under Weblogs\user(..). To further investigate VDI connection-related issues, using keyword **vdiBridgeEventsHandler** provides the logs from the vdiBridge connection and disconnection event handlings, as shown (onConnected event handling) in the following example of a successful connection with the new optimization stack:

`7432 2024-03-01T17:51:22.032Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - onConnected: end, currentStack=remote 7435 2024-03-01T17:51:22.032Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - new calling stack type set: currentStack=remote 7436 2024-03-01T17:51:22.032Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - deviceManagerService reloaded 7445 2024-03-01T17:51:22.031Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - calling stack reinit complete with nextStack=remote 7464 2024-03-01T17:51:21.785Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - starting calling stack reinit with nextStack=remote 7465 2024-03-01T17:51:21.785Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - SlimCore replacement complete, remote is now available 7467 2024-03-01T17:51:21.783Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - setVDIOptimizationModeOverride: from SlimCore to SlimCore 7468 2024-03-01T17:51:21.782Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - onConnected: isVersionMismatch=false, forceVersion=undefined, bridgeVersion=2024.5.1.11 7469 2024-03-01T17:51:21.782Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - cached local SlimCore for future (fallback), currentStack=local 7470 2024-03-01T17:51:21.782Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - onConnected: start, vendorType=1, remoteSlimcoreVersion=2024.05.01.11, platform=win-x86, loadErrc=1, deployErrc=24002, nodeId=ffffffffbd7d5e77 7471 2024-03-01T17:51:21.782Z Inf    vdiBridgeEventsHandler: VDI Mode: slimcore - enqueueBridgeCallback: adding onConnected to queue, 0 bridge callbacks in queue, isBridgeCallbacksQueueProcessing=false`

## Connection error

If there's a connection error, the error code can be found from the log line containing "loadErrc" and "deployErrc". A deploy error (also known as install\_error) is an error that happens when the plugin was trying to download the SlimCore MSIX package from Microsoft's Content Delivery Network. The plugin then tries to stage or provision the package to the endpoint using the App Readiness Service for AppX. A load error is an error that happens when the plugin tried to start MsTeamsVdi.exe and establish a Remote Procedure Call (RPC) to it.

The code logged here needs to be mapped using this table:

| Standard Error Code | loadErrc or deployErrc | Definition | Notes |
| --- | --- | --- | --- |
| 0 | 0 | OK | Not an error. 'SlimCore Connected' success, user is properly optimized |
| 2 | 19 | ERROR\_FILE\_NOT\_FOUND | A file required for SlimCore deployment or startup couldn't be found. Check the endpoint's Event Viewer AppXDeployment-Server/Operational logs to identify the missing file and failing operation. If the error occurs during package registration or startup, verify that the required SlimCore Host and Framework packages are present and registered for the affected user. Check whether an endpoint cleanup script or security product removed the package or its files. An initial registration attempt can return this error before the plugin downloads and stages the package; if subsequent deployment and optimization succeed, no remediation is required for that initial failure. Please upgrade your plugin to 2026.29.1.4 or higher, which contains a fix for this issue. |
| 5 | 43 | ERROR\_ACCESS\_DENIED | MsTeamsVdi.exe process failed at startup. BlockNonAdminUserInstall being enabled could cause this error. Or the endpoint could be busy registering multiple MSIX packages after a user logon and AppX service didn't finish registering SlimCoreVdi. |
| 6 | 51 | ERROR\_INVALID\_HANDLE | Windows returned 'the handle is invalid' during SlimCore download, deployment or start-up operation. Review the Microsoft-Windows-Bits-Client\Operational Event Viewer log on the endpoint. For MSIX package deployment failures, check AppXDeployment-Server/Operational Event Viewer log on the endpoint. The underlying Windows OS error might appear as 0x80070006. HP and DELL devices that have a RAM Disk Manager where environmental variables TEMP/TMP are pointing to a RAM Disk (for example, Z:) can experience this error. For a workaround, check the same link as in Error 4390 below - 'Thin Clients with RAM Disks' |
| 32 | 259 | ERROR\_SHARING\_VIOLATION | A file required for SlimCore deployment or startup is in use by another process, and the requested access conflicts with the existing file handle. Check the endpoint's logs and AppXDeployment-Server/Operational event log to identify the affected file and operation. Allow any ongoing package installation or update to complete, then retry optimization. If the issue persists, use Process Explorer to identify the process holding the file open. Coordinate any process restart with the user's status to avoid interrupting active calls. |
| 104 | 835 | BG\_E\_BLOCKED\_BY\_BATTERY\_SAVER | Windows Background Intelligent Transfer Service (BITS) paused the SlimCore MSIX download because the endpoint is in Battery Saver mode. Connect the endpoint to AC power or turn off Battery Saver/Energy saver, then retry optimization if it doesn't recover automatically. Confirm HRESULT 0x80200068 in the endpoint's AppXDeployment-Server/Operational logs. This is a power-management restriction, not necessarily a network or CDN failure. |
| 110 |  | ERROR\_OPEN\_FAILED | Windows Background Access policies blocking BITS ('BG\_E\_BLOCKED\_BY\_BACKGROUND\_ACCESS\_POLICY'), which prevents SlimCore downloads during optimization. For AVD/W365 users, the Windows App might not have [Background app permission-&gt;'Let this app run in background' set to 'Always'](https://support.microsoft.com/Windows/Experience/Performance-Optimization/manage-background-activity-for-apps-in-windows) on Windows Settings/Apps/Installed apps/Windows App. If this option is not visible, check if GlobalUserDisabled is set to 1 and change it to 0, under HKCU\Software\Microsoft\Windows\CurrentVersion\BackgroundAccessApplications |
| 403 | 3227 | HTTP\_STATUS\_FORBIDDEN | Check with your networking and proxy teams, as something is blocking the SlimCore MSIX downloads. HTTP status 403 - server understood the request, but declined to fulfill it. |
| 404 | 3235 | HTTP\_STATUS\_NOT\_FOUND | Publishing issue: SlimCore MSIX package isn't found on Content Delivery Network. Possible interference from Proxy servers |
| 1260 | 10083 | ERROR\_ACCESS\_DISABLED\_BY\_POLICY | This error usually means that Windows Package Manager can't install the SlimCore MSIX package. Event Viewer can show the hex error code 0x800704EC. AppLocker Policies can cause this error code. You can either disable AppLocker, or add an exception for SlimCoreVdi packages in Local Security Policy -&gt; Application Control Policies -&gt; AppLocker. Check [Step 3](vdi-2#step-3-slimcore-msix-staging-and-registration-on-the-endpoint) under "Optimizing with new VDI solution for Teams". |
| 1460 | 11683 | ERROR\_time-out | MsTeamsVdi.exe process failed at startup (60-second time-out). Symptoms can be a slow transition to SlimCore optimization, a possible "SlimCore Media Not Connected" and an eventual recovery after waiting or restart. Most likely root cause SlimCore MSIX deployment/registration completed too slowly. |
| 1722 | 13779 | RPC\_S\_SERVER\_UNAVAILABLE | 'The Remote Procedure Call (RPC) server is unavailable'. MsTeamsVdi.exe was unable to communicate with a Windows service component it depends on during SlimCore startup, most likely the App Readiness Service (ARS), Package Manager APIs or Package Registration APIs. If those components are unavailable, hung, or restarting, RPC errors are expected. A common scenario is slow Thin Clients that are overloaded on user logons, or AppX Registrations are delayed. Corrupted or incomplete SlimCore registration can also be the cause. If optimization eventually succeeds, treat 1722 as a transient condition rather than a hard MsTeamsVdi.exe startup failure. Additional logging information can be obtained from the endpoint's [Event Viewer (AppXDeployment-Server/Operational and AppxPackagingOM/Operational)](/en-us/microsoftteams/vdi-2-troubleshooting#troubleshooting-slimcorevdi-msix-deployment-errors) |
| 2000 | 16002 | No Plugin | Endpoint doesn't have the MsTeamsPlugin, or if it has it, it didn't load (check with Process Explorer). |
| 2001 | 16008 | Virtual Channel Not Available | Error on the Citrix VDA (virtual delivery agent) WFAPI or Omnissa Agent Blast API |
| 2003 | 16026 | Custom Virtual Channels (MSTEAMS, MSTEAM1 and MSTEAM2) are blocked due to a Citrix Studio policy | Review the [Citrix virtual channel allow list](vdi-2#citrix-virtual-channel-allow-list) section of the VDI 2.0 article. |
| 2004 | 16032 | Citrix Workspace App version not supported. Please upgrade |  |
| 2005 | 16043 | Teams is running as a Published App (Citrix) or RemoteApp (AVD/Windows 365) | User does not meet minimum version requirements - Teams doesn't load SlimCore in this case, and users are always optimized with WebRTC. |
| 2008 | 16066 | Windows app for MAC in AVD/365 is from the App Store, which is not supported. Only non-store Windows app is supported. | Evergreen link to the latest MAU client: [https://aka.ms/RDMacMAU|](https://aka.ms/RDMacMAU%7C) |
| 3000 | 24002 | SlimCore Deployment not needed | This code isn't really an error. It's a good indicator that the user is on the new optimization architecture with SlimCore. |
| 3001 | 24010 | SlimCore already loaded | This code isn't really an error. It's a good indicator that the user is on the new optimization architecture with SlimCore. |
| 3002 | 24018 | No Local SlimCore | SlimCore wasn't downloaded successfully on the endpoint. |
| 3004 | 24035 | Plugin irresponsive | Try restarting Teams. This is typically a transient error, where the Plugin is busy staging the media engine. This error is different than 2000, where a virtual channel fails to establish. In Error 3004, there is a transport established, but the Plugin never replied to Teams with a 'ClientHello' |
| 3005 | 24043 | Plugin time-out while downloading | Failure to download the MSIX within 2 minutes. |
| 3007 | 24058 | Load time-out | SlimCore download or installation timed out (slow internet or App Readiness Service is busy). |
| 3018 | 24146 | IPC ERROR | Communication between the Teams VDI plugin and the endpoint SlimCore process failed during startup. Check the endpoint plugin and SlimCore logs for IPC/RPC exceptions or unexpected process termination. Reconnect the remote session and restart Teams. If the issue persists, collect endpoint logs and any associated crash reports. |
| 3021 | 24170 | No usable SlimCore package | Some MSIX packages are present (usually Framework), but no usable combination (usually missing Host MSIX Package). Some user setting is preventing Host installations. |
| 4000 |  | ERROR\_WINS\_INTERNAL | WINS encountered an error while processing the command. |
| 4390 |  | ERROR\_NOT\_A\_REPARSE\_POINT | SlimCore MSIX related error in Thin Clients with Unified Write Filters and RAM Disk overlays. Please check [this section](/en-us/microsoftteams/vdi-2#unified-write-filters-uwf) |
| 6000 | 48002 | NETWORK SESSION ERROR | The macOS download session failed while retrieving SlimCore. Check the endpoint logs for the underlying network error, then investigate internet connectivity, DNS resolution, proxy/VPN configuration, and TLS or certificate errors. Ensure the endpoint can reach the Microsoft CDN locations required by the new VDI solution, then retry the connection. |
| 6004 | 48034 | NETWORK HTTP ERROR | The SlimCore download on a macOS returned an HTTP status other than 200, or no downloaded-file location was available. Check the endpoint logs for the requested URL and HTTP status. Investigate proxy restrictions, CDN availability, or missing package content as indicated by that status. If HTTP 200 was returned, review the logs for a missing downloaded-file location rather than assuming that the server rejected the request. |
| 12002 |  | ERROR\_INTERNET\_TIMEOUT | Internet connectivity issues on the endpoint. The HTTP request has timed out. Recommended action for user is to run [NAT Tool](https://www.microsoft.com/download/details.aspx?id=103017) and detect issues on their network to resolve the problem |
| 12030 |  | ERROR\_INTERNET\_CONNECTION\_ABORTED | Internet connectivity issues on the endpoint. The connection with the Microsoft CDN server was terminated abnormally. Recommended action for user is to run [NAT Tool](https://www.microsoft.com/download/details.aspx?id=103017) and detect issues on their network to resolve the problem |
| 15615 | 1951 | ERROR\_INSTALL\_POLICY\_FAILURE | SlimCore MSIX related error. To install this app, you need either a Windows developer license, or a sideloading-enabled system. AllowAllTrustedApps regkey might be set to 0? |
| 15616 |  | ERROR\_PACKAGE\_UPDATING | SlimCore MSIX related error. 'The application cannot be started because it is currently updating'. Transient MSIX lifecycle race condition, not a hard deployment failure. Windows returns this when the Plugin tries to start or load SlimCore while the AppX/MSIX subsystem is still updating, registering, repairing, or replacing the SlimCore package on the endpoint. If optimization eventually succeeds, treat 15616 as a retryable condition rather than a deployment failure. Only investigate further if users remain in "SlimCore Media Not Connected" or never gets optimized with SlimCore. |
| 15618 |  | ERROR\_PACKAGES\_IN\_USE | SlimCore MSIX related error. 'The package could not be installed because resources it modifies are currently in use'. |
| 15700 |  | APPMODEL\_ERROR\_NO\_PACKAGE | The process has no package identity. There's no alias for MsTeamsVdi in %LOCALAPPDATA%\Microsoft\WindowsApps. [Feedback Hub](https://support.microsoft.com/windows/send-feedback-to-microsoft-with-the-feedback-hub-app-f59187f8-8739-22d6-ba93-f66612949332) logs are needed while reproducing the error (make sure you select **Developer Platform** as the category and **App deployment** as the subcategory) |
| 16389 |  | E\_FAIL reported by Package Manager | Usually the same as Load error code 5 (ERROR\_ACCESS\_DENIED). Most likely caused by the BlockNonAdminUserInstall policy when the user isn't an Admin. Check [this link](/en-us/windows/client-management/mdm/policy-csp-applicationmanagement#blocknonadminuserinstall) for more details. Intune MDM can also set this value. Under some conditions, Windows reports error 16389 (E\_FAIL) as a generic error, so BlockNonAdminUserInstall is not the only root cause - see detailed description below. |

## Using Event Viewer on the VM for troubleshooting

Every connect/disconnect event gets logged in the Event Viewer running on the Virtual Machine. The Event Viewer can also display client-side related errors. Filter by Source (Microsoft Teams VDI) and Event ID (0) under Windows Logs\Application. Error codes can be found in the Teams logs for VDI section.

Note

In order to be able to filter by Source, you need to run this command from an elevated PowerShell window:

`PS C:\Windows\system32> New-EventLog -LogName Application -Source "Microsoft Teams VDI"`

## Troubleshooting Plugin deployment errors

Diagnostic information can be found in the detailed event logs on the user's device. After install, MsTeamsPluginCitrix.dll is written into the CWA (Citrix Workspace app) folder. Only for the Citrix platform, the following keys on the Endpoint (not VM) are created:

| Key | Key type | Key name | Key value |
| --- | --- | --- | --- |
| HKLM\SOFTWARE\WOW6432Node\Citrix\ICA Client\Engine\Configuration\Advanced\Modules\ICA 3.0 | String | VirtualDriverEx | MicrosoftTeamsVDI |
| HKLM\SOFTWARE\WOW6432Node\Citrix\ICAClient\Engine\Configuration\Advanced\Modules\MicrosoftTeamsVDI | String | DriverNameWin32 | MsTeamsPluginCitrix.dll |

To debug installations, you can enable installer logging, but then you must use msiexec manually, and pass correct flags. For example, if the plugin isn't currently installed, it can be installed with logs: msiexec.exe /i MsTeamsPluginCitrix.msi /l\*vx installer.log.txt.

## Troubleshooting SlimCoreVdi MSIX deployment errors

Make sure you review the [SlimCore MSIX staging and registration on the endpoint](vdi-2#step-3-slimcore-msix-staging-and-registration-on-the-endpoint) section, as certain GPOs (group policies) can prevent MSIX installations.

Diagnostic information can be found in the detailed event logs on the user's device.

1. Go to the Event Viewer (Local) &gt; Applications and Services Logs &gt; Microsoft &gt; Windows.
2. Check for available logs under these categories:

    - AppxPackagingOM &gt; Microsoft-Windows-AppxPackaging/Operational
    - AppXDeployment-Server &gt; Microsoft-Windows-AppXDeploymentServer/Operational
3. Review the logs under AppXDeployment-Server.

## Error 16389

Error 16389 (E\_FAIL) is often an error where the Windows Package Manager/AppX stack encountered some underlying failure but only surfaced the generic E\_FAIL value. The most likely cause is the BlockNonAdminUserInstall policy. This [CSP Policy for ApplicationManagement](/en-us/windows/client-management/mdm/policy-csp-applicationmanagement#blocknonadminuserinstall) manages non-Administrator users' ability to install Windows app packages, for example the SlimCore Host and Framework.

Note

The issue can also be caused when the MDM policy ApplicationManagement/BlockNonAdminUserInstall (Intune Settings Catalog → App Package Deployment → Block non admin user install) is set to 1 (Enabled) on the endpoint. Effective policy is read from: HKLM\SOFTWARE\Microsoft\PolicyManager\current\device\ApplicationManagement\BlockNonAdminUserInstall = 1 (REG\_DWORD). AppX Deployment Server returns E\_ACCESSDENIED (0x80070005) to the caller (msrdc.exe, for example). The Teams VDI plugin surfaces this as windows\_error\_16389 and aborts SlimCore registration → new optimization is not initialized → call falls back to non-optimized or, if available, WebRTC.

| Cause | Likelihood | Notes |
| --- | --- | --- |
| BlockNonAdminUserInstall | Very high |  |
| AppLocker / WDAC | High |  |
| SlimCore Host/FWK registration mismatch | High | Fixed on Plugin 2026.29.1.4 |
| Shared kiosk multi-user registration issue | High | Fixed on Plugin 2026.29.1.4 |
| Temp folder access denied | Medium-High |  |

## Error 15615

Error 15615 usually means that the Windows Package Manager can't install the MSIX package with SlimCoreVdi.

- Make sure the Endpoint trusts the digital signature of that MSIX (Go to MSIX &gt; Properties &gt; Digital signatures &gt; Details). It's a valid store-friendly Microsoft signature, but customers may have something special configured.
- Try enabling the [AllowAllTrustedApps policy](/en-us/windows/client-management/mdm/policy-csp-applicationmanagement).
- Try to allow sideloading apps from trusted nonstore sources.
    - On Windows 10, this setting is enabled by default, so modify it here if you find it disabled: Settings &gt; Update and Security &gt; For developers &gt; Sideload apps.
    - On Windows 11, this setting is enabled by default: Settings &gt; Apps &gt; Advanced app settings &gt; Choose where to get apps &gt; Anywhere.

## Log collection

Logging can be found in the following locations:

- On the client (for old SlimCores before the new split architecture with Host and Framework):

    - `AppData\Local\Microsoft\TeamsVDI\<vdi_vendor>-default-<cloudname>\skylib`
    - `AppData\Local\Microsoft\TeamsVDI\<vdi_vendor>-default-<cloudname>\media-stack`
- On the client (for new SlimCores with split architecture with Host and Framework):

    - `AppData\Local\Packages\Microsoft.Teams.SlimCoreVdiHost.win-x64_8wekyb3d8bbwe\LocalCache\Local\Microsoft\TeamsVDI\<vdi_vendor>-default-<cloudname>\skylib`
    - `AppData\Local\Packages\Microsoft.Teams.SlimCoreVdiHost.win-x64_8wekyb3d8bbwe\LocalCache\Local\Microsoft\TeamsVDI\<vdi_vendor>-default-<cloudname>\media-stack`
- On the Server:

    - `AppData\Local\Packages\MSTeams_8wekyb3d8bbwe\LocalCache\Microsoft\MSTeams\Logs\skylib`