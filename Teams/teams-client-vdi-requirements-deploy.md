---
layout: Conceptual
title: Microsoft Teams for Virtualized Desktop Infrastructure (VDI) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-vdi-requirements-deploy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: upgrade-and-migration-article
ms.date: 2026-08-25T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: fklurfan
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about install Teams for Virtualized Desktop Infrastructure (VDI)
ms.localizationpriority: medium
locale: en-us
document_id: daebac54-993e-c5d5-4b79-617efcbb1ffb
document_version_independent_id: daebac54-993e-c5d5-4b79-617efcbb1ffb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-vdi-requirements-deploy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-vdi-requirements-deploy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-vdi-requirements-deploy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 59af0e76-1442-df69-395c-707ff49a6286
---

# Microsoft Teams for Virtualized Desktop Infrastructure (VDI) - Microsoft Teams | Microsoft Learn

This article describes the requirements and limitations of using the Microsoft Teams client in a virtualized environment.

Important

As communicated on Message Center post 1239928, the WebRTC-based optimization for **Windows-based** endpoints connecting to Citrix and Azure Virtual Desktop (AVD) / Windows 365 environments will be deprecated, and the new optimization becomes the default mode. Deprecation will be rolled out in two subsequent milestones: 

- **End of Support October 1st, 2026**: WebRTC-based optimization will continue to work, but it is no longer officially supported by Microsoft and Citrix when connecting from Windows endpoints. Two months before this milestone, users will see dismissible dialogues upon application launch time alerting about the upcoming change.
- **End of Availability April 1st, 2027**: WebRTC stops working; the new optimization is enforced. If Teams fails to optimize, it will fall back to server-side rendering (i.e. all multimedia is processed on the virtual machine, degrading the user experience). Two months before this milestone, users see a modal dialogue window alerting about the upcoming change. If the reason for not being optimized with the new stack is that the plugin is not installed, users are instructed to download the plugin from Microsoft's website. Optimization Policies related to the legacy optimization (such as in Citrix Studio) no longer take effect after End of Availability.

**Apple MacOS** timelines for Citrix and AVD/W365 are communicated via Message Center post 1481308:

- **End of Support April 1st, 2027**
- **End of Availability September 1st, 2027**

**Omnissa** timelines for **Windows-based** endpoints only are communicated separately via Message Center post 1465766:

- **End of Support July 1st, 2027**
- **End of Availability October 1st, 2027**

Note

Customers using supported Linux-based Thin Clients (IGEL, Dell, HP, 10ZiG, NComputing, etc) are not impacted by the End of Support / End of Availability statements above. The existing multimedia optimization will continue to be supported normally on AVD/W365, Citrix and Omnissa until Microsoft releases a new VDI solution for Linux, designed to close the existing feature gaps.

## Requirements

Microsoft recommends the latest Teams version. In addition, virtual machines must meet the minimum requirements listed here:

| Requirement | Version |
| --- | --- |
| Windows | - Windows 10.0.19041 or higher (excluding Windows LTSC for Teams desktop app, which are not supported) - Windows Server 2022 (20348.2402) or higher- Windows Server 2025 (26100.2886) or higher- Windows Server 2016 and 2019 are NOT supported. Plan upgrades.- WebView2 framework required in Windows Server and Windows 10/11 Multi-User environments |
| Webview2 | Update to the most current version. Learn more: [Enterprise management of WebView2 Runtimes](/en-us/microsoft-edge/webview2/concepts/enterprise) |
| Settings | Turn on the **Show Notification Banners** setting in System &gt; Notifications &gt; Microsoft Teams to receive Teams Notifications. |
| Exclude antivirus and DLP | Add Teams to antivirus and DLP applications so Teams can start correctly. Learn more: [Exclude antivirus and DLP applications from blocking Teams](/en-us/microsoftteams/troubleshoot/teams-administration/include-exclude-teams-from-antivirus-dlp) |

Note

The [Modern Lifecycle Policy](/en-us/lifecycle/policies/modern) defines support for Microsoft Teams and Microsoft 365 Apps, which requires customers maintain an up-to-date configuration to stay supported. Check Microsoft Teams [Service Agreement here.](/en-us/microsoftteams/teams-client-update#servicing-agreement)As announced on Message Center Post 931401, if a Teams version is older than 60 days, in-app alerts will be displayed, and for versions older than 90 days, users will see blocking pages. Release dates and enforcement timelines can be tracked [on the VDI section of this page.](/en-us/officeupdates/teams-app-versioning)

Note

As announced on Message Center post 994280, End-of-support dates for Windows Server 2019 and Windows Server 2022 are October 2025 and October 2026 respectively. For further information, check [this link](https://go.microsoft.com/fwlink/?linkid=2274805).

## Virtualization provider requirements

Currently, Teams on VDI with audio/video (AV) optimization is certified with Azure Virtual Desktops, Windows 365, Citrix, Omnissa and Amazon. Review the information in this article to ensure that you meet all requirements for proper functionality.

For RDS scenarios, see [this section](/en-us/microsoftteams/teams-on-rds).

## Azure Virtual Desktop

Azure Virtual Desktop provides AV optimization for Teams on VDI. To learn more on requirements and installation, see [Use Teams on Azure Virtual Desktop](/en-us/azure/virtual-desktop/teams-on-avd).

The following minimum versions are necessary to support the Teams client:

- Remote Desktop Client for Windows (no longer supported, upgrade to Windows App)
- Windows app for Windows 2.0.360.0
- Remote Desktop Client for Mac (no longer supported, upgrade to Windows App)
- Windows app for Mac 11.3.4
- Windows app for iOS 11.2.5 [WebRTC based optimization only]
- Windows app for Android (11.0.0.78) [WebRTC based optimization only]
- Web browsers don't support Microsoft Teams optimization
- Linux Thin Clients - only Partners listed [on this page](/en-us/azure/virtual-desktop/thin-clients#partner-thin-client-devices) support Microsoft Teams optimization (WebRTC based)
- WebRTC Redirector Service 1.54.2408.19001

Microsoft recommends using the latest available versions.

Note

Customers using Linux Thin Clients must contact their Thin Client provider's Technical Support first for any Teams multimedia or optimization related issues. If the issue isn't multimedia or optimization related, Customers can contact Microsoft's Support directly.

In addition, you must deploy the following registry key on the virtual desktop for the Teams client to be optimized:

HKLM\SOFTWARE\Microsoft\Teams:

- Name: IsWVDEnvironment
- Type: DWORD
- Value: 1

### RemoteApp

You can publish Teams using the Windows `shell:appsFolder` location in the format: `shell:appsFolder\MSTeams_8wekyb3d8bbwe!MSTeams`.

For more information on RemoteApp, see [this article](/en-us/azure/virtual-desktop/publish-applications?tabs=portal). For information on the new optimization stack (SlimCore-based) and the new stack, see [this article](/en-us/microsoftteams/vdi-2).

## Windows 365

Windows 365 uses the same Audio/Video optimization provided by Azure Virtual Desktop to ensure optimal Teams experiences from Cloud PCs. To learn more on requirements and installation, see [Use Teams on Cloud PC](/en-us/windows-365/enterprise/teams-on-cloud-pc).

The Windows 10/11 images in the gallery are preconfigured with required optimization components. When you install and use Microsoft Teams in your Cloud PC, you get an optimized experience.

If you want to create custom images that include optimizations for Microsoft Teams, you need to perform the steps described in [Create a custom Cloud PC image to support Microsoft Teams](/en-us/windows-365/enterprise/create-custom-image-support-teams).

The same minimum versions as in Azure Virtual Desktops are necessary to support the Teams client on Windows 365. See section above.

In addition, you must deploy the following registry key on the virtual desktop for the Teams client to be optimized:

HKLM\SOFTWARE\Microsoft\Teams:

- Name: IsWVDEnvironment
- Type: DWORD
- Value: 1

## Citrix Virtual Apps and Desktops and Citrix DaaS requirements

The following minimum versions are necessary to support the Teams client:

Citrix Workspace app:

- Windows 2402 LTSR (latest CU)
- Windows 2409.10 CR
- Linux 2503
- Mac 2411.10
- HTML5 2502
- ChromeOS - latest Citrix Workspace app for ChromeOS published in Chrome Web Store. The previous (N minus 1) version is supported on the compatible ChromeOS version and maintained until the next release.

Note

Unicon -now part of Citrix- and its eLux OS (a secure, lightweight, hardware agnostic, Linux-based operating system which is used on managed endpoints) is fully supported with WebRTC-based optimization, until the new VDI optimization (also known as VDI 2.0) is delivered to Linux-based platforms. Monitor Microsoft 365 Roadmap for public announcements. For more information on Unicon, please visit the Citrix website https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/2411/unicon.html.

Citrix Virtual Delivery Agent (VDA):

- 2507 LTSR (and any CU)
- 2402 LTSR (and any CU)
- 2203 LTSR (and any CU)
- 2503 CR
- 1912 LTSR is not supported

In addition, you must deploy the following registry key on the VDA for the Teams client to be optimized:

- Location: HKLM\SOFTWARE\WOW6432Node\Citrix\WebSocketService
- Key (REG\_Multi\_SZ): ProcessWhitelist
- Value: msedgewebview2.exe

If this registry key is missing, the Teams client operates in nonoptimized mode (server-side rendering). This regkey isn't needed anymore if you're using VDA 2402 ([check here](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams) for more details).

Note

Citrix Virtual Apps (also known as published apps) is also supported with VDA 2402 LTSR (latest CU).

For additional information, learn more at [Optimization for Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

## Omnissa Horizon and Workspace ONE requirements

Note

Horizon and Workspace ONE were developed and formerly maintained by Omnissa.

The following minimum versions are necessary to support the Teams client:

- Horizon 8 2111 ESB (8.4)

To learn more about the latest requirements and instructions, including how to configure media optimization for Teams, see [Microsoft Teams Optimization with Horizon | Omnissa](https://techzone.omnissa.com/resource/microsoft-teams-optimization-horizon).

## Amazon WorkSpaces requirements

For more details, see the [new VDI optimization page (SlimCore-based)](/en-us/microsoftteams/vdi-2#system-requirements). AppStream isn't supported.

## Deploy the Microsoft Teams client

To deploy the Microsoft Teams client to your organization, select one of the following options.

Important

You must use the latest version of the bootstrapper.exe. If .exe was already downloaded, check **Properties &gt; Details &gt; Product version** for your version and compare it to the properties on the latest download.

### Install the Teams client

**Recommended way to deploy Teams in VDI.** The direct or 'bulk deployment' method is used for this option. Learn more at [**Bulk deploy the Microsoft Teams desktop client**](teams-client-bulk-install).

Using the teamsbootstrapper.exe -p command always guarantees the latest Teams client is installed.

A phased and controlled rollout can then be achieved by selectively expanding the new computer catalogue/delivery group assignments to more users.

Admins can also use a local teams MSIX to provision Teams. This option minimizes the amount of bandwidth used for the initial installation. The MSIX can exist in a local path or UNC.

1. [Download the .exe installer.](https://go.microsoft.com/fwlink/?linkid=2243204&amp;clcid=0x409)
2. Download the MSIX:- [MSIX x86](https://go.microsoft.com/fwlink/?linkid=2196060&amp;clcid=0x409)- [MSIX x64](https://go.microsoft.com/fwlink/?linkid=2196106)- [ARM64](https://go.microsoft.com/fwlink/?linkid=2196207&amp;clcid=0x409).
3. Open the Command Prompt as an Admin.
4. Depending on where your MSIX is located, do the following steps:

    **For local path, enter:***.\teamsbootstrapper.exe -p -o "c:\path\to\teams.msix"*

    *Example:*

    ![local path location for offline installer](media/new-teams-bulk-offline-localpath.png)

    **For UNC, enter:***.\teamsbootstrapper.exe -p -o "\unc\path\to\teams.msix"*

    *Example:*

    ![offline location using unc](media/new-teams-bulk-offline-unc.png)

Note

Teamsbootstrapper.exe logs are located in C:\WINDOWS\Temp\teamsprovision.log.xxxxxxxx.

If IT administrators set restrictions for MSIX or deploy GPOs, it could prevent users from downloading and installing the app. If restrictions are in place, the user could see errors like this one:

![error with org policies.](media/new-teams-troubleshooting-error-isntallation-org-policies.png)

## Teams installers in VDI environments

You should have an awareness of the install location for the Teams client.

| Installer format | Install location | Auto update |
| --- | --- | --- |
| Classic Teams MSI with the ALLUSERS=1 flag | C:\Program Files (x86)\Microsoft\Teams | Disabled |
| Classic Teams .EXE | %localappdata%\Microsoft\Teams | Enabled |
| New Teams .EXE bootstrapper | **Teamsbootstrapper.exe** is a lightweight wrapper online installer with a headless command-line interface. It allows admins to 'provision' (install) the app for all users on a given target computer. It installs the Teams MSIX package on a target computer, making sure that Teams can interoperate correctly with Office and other Microsoft software. C:\Program Files\WindowsApps\PublisherName.AppName\_AppVersion\_architecture\_PublisherID**Example**C:\Program Files\WindowsApps\MSTeams.23306.3314.2555.9628\_x64\_8wekyb3d8bbwe | Enabled. It can be disabled via regkey. Learn more: Disable new Teams autoupdate |

## Troubleshooting Teams deployment errors

Administrators can rely on the teamsbootstrapper.exe [error code](/en-us/windows/win32/seccrypto/common-hresult-values) that describes the problem. If the error code doesn't provide enough information, more diagnostic information can be found in the detailed event logs.

1. Go the Event Viewer (Local) **&gt; Applications and Services Logs &gt; Microsoft &gt; Windows**.
2. Check for available logs under these categories:

    - AppxPackagingOM &gt; Microsoft-Windows-AppxPackaging/Operational
    - AppXDeployment-Server &gt; Microsoft-Windows-AppXDeploymentServer/Operational
3. Review logs under **AppXDeployment-Server**.

    Learn more here: [Common error codes](/en-us/windows/win32/appxpkg/troubleshooting#common-error-codes)

    | Teamsbootstrapper.exe common error codes | Further information |
    | --- | --- |
    | 0x80070057 | The bootstrapper command doesn't have the full path (avoid URIs using .). Try the full path instead (for example, c:\temp\MSTeams-x64.msix). |
    | 0x80070032 | A probable error on the UNC path. Try copying the MSIX to a local folder instead. |
    | 0x80004004 | There might be a regkey 'maglevInstallationSource' left behind in regkey HKLM\Software\WoW6432Node\Microsoft\Office\Teams. Try deleting it and reattempting the install. |

## Installation instructions for Windows Server 2019 (no longer supported - plan upgrades to Windows Server 2025)

For Windows Server 2019, the only supported installation method is:

```Command
Dism /Online /Add-ProvisionedAppxPackage /PackagePath:<MSIX package path> /SkipLicense
```

Make sure sideloading is enabled, and that WebView2 is installed. See the Requirements section.

The `/SkipLicense` command is needed because the MSIX package isn't considered a "Store Package" (since it wasn't downloaded from the store). Therefore, for the Dism installation command to succeed, you need to enable this policy as well during installation time: Computer Configuration &gt; Administrative Templates &gt; Windows Components &gt; App Package Deployment &gt; **Allow all trusted apps to install**.

Important

`AllowAllTrustedApps` must be enabled after the Teams package is successfully staged in the golden image. Otherwise, the registration of the package to each user (which happens only on login) fails and users aren't able to launch the app.

Known limitations:

- If you're using FSLogix as the Profile Manager solution, Teams on Windows Server 2019 needs [FSLogix 2210 HotFix 4](/en-us/fslogix/overview-release-notes#fslogix-2210-hotfix-4-29888427471) or higher (Microsoft recommends the latest available version).

### Outlook presence integration with Teams in Windows Server 2019

For Outlook to properly display presence status, the following steps are required on the golden image:

1. Install machine-wide (ALLUSERS=1) the '[Windows 10 1809 and Windows Server 2019 KB5035849 240209_02051 Feature Preview.msi](https://statics.teams.cdn.office.net/evergreen-assets/DesktopClient/Windows%2010%201809%20and%20Windows%20Server%202019%20KB5035849%20240209_02051%20Feature%20Preview.msi)'.
2. Open your Group Policy Editor. Navigate to Computer Configuration\Administrative Templates\KB5035849 240209\_02051 Feature Preview\Windows 10, version 1809 and Windows Server 2019. Change the value of that Setting to **Enabled**.
3. Install [KB5035849](https://support.microsoft.com/topic/march-12-2024-kb5035849-os-build-17763-5576-719f5f8d-51c6-43f0-a612-1c15802fed06) March 2024 cumulative update from the [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=2024-03%20Cumulative%20Update%20for%20Windows%20Server%202019%20for%20x64-based%20Systems%20%28KB5035849%29) or WSUS for Enterprises.
4. Install machine-wide (ALLUSERS=1) the '[MSTeamsNativeUtility.msi](https://statics.teams.cdn.office.net/evergreen-assets/DesktopClient/MSTeamsNativeUtility.msi)'.
5. Reboot the virtual machine.
6. Install Teams 24033.811.2738.2546 or higher, using Dism as described previously.

    Note

    Steps 1, 2, 3, 4, and 5 are only required once. These steps aren't required in subsequent golden image maintenance.

    Important

    Outlook must be started **after** Teams is launched for presence to be shown correctly.

## Remove Teams for all users

To uninstall and deprovision Teams for all users, use the following command:

```powershell
./teamsbootstrapper -x
```

This command unregisters and deprovisions Teams for all users. Teams user profile/cache is deleted.

## Disable Teams autoupdate in non-persistent VDI

To prevent Teams from autoupdating, use the following registry key on the virtual machine. Only Teams builds higher than 23306.3314.2555.9628 in VDI can process this registry key.

```Registry
Location: Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams
Name: disableAutoUpdate
Type: DWORD
Value: 1
```

Important

If this regkey is present in the virtual machine, Teams MSIX installer doesn't attempt to install or upgrade the Teams Meeting add-In (TMA). Administrators must provision TMA using scripts or other deployment tools. For more information, see the Teams Meeting add-In section of this article.

## Teams autostart

Three components control the autostart behavior of Teams:

1. By default, MSIX-based applications don't autostart until there's a first launch, because the Windows OS doesn't autostart packages in a provisioned state. An AppX registration is needed with user consent. After the first launch, users can go to **Settings** &gt; **General** and fill the **Autostart Teams** checkbox, or enable autostart from the Windows Setting menu.
2. If the "Autostart Teams" checkbox is greyed out, it means a system-wide GPO is disabling this option for UWP apps:

    ```Registry
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System]
    "EnableFullTrustStartupTasks"=dword:00000000
    "EnableUwpStartupTasks"=dword:00000000
    "SupportFullTrustStartupTasks"=dword:00000000
    "SupportUwpStartupTasks"=dword:00000000
    ```

    This registry setting causes the option to be unavailable in the operating systems under **Settings** &gt; **Apps** &gt; **Installed Apps**. In order to change this setting, create the regkeys with the values as shown in this example:

    ```Registry
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System]
    "EnableFullTrustStartupTasks"=dword:00000002
    "EnableUwpStartupTasks"=dword:00000002
    "SupportFullTrustStartupTasks"=dword:00000001
    "SupportUwpStartupTasks"=dword:00000001
    ```

    Restart the virtual machine to see the startup options active in the operative system's settings menu.
3. This registry key controls the Teams autostart behavior, so you can enable or disable it programmatically.

    ```Registry
    [HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\Windows\CurrentVersion\AppModel\SystemAppData\MSTeams_8wekyb3d8bbwe\TeamsTfwStartupTask]
    "State"=dword:00000002
    "UserEnabledStartupOnce"=dword:00000001
    ```

    | State | Number | Information |
    | --- | --- | --- |
    | Disabled | 0 | The task is disabled. |
    | DisabledByUser | 1 | The user disabled the task. Only the user can re-enable the task. |
    | EnabledByUser | 2 | The task is enabled. |
    | DisabledByPolicy | 3 | The administrator or group policy disabled the task. Platforms that don't support startup tasks also report DisabledByPolicy. |
    | EnabledByPolicy | 4 | The administrator or group policy enabled the task. |

    You can learn more at [this link](/en-us/uwp/api/windows.applicationmodel.startuptaskstate#fields).

Important

If you're using non-persistent VDI, you must make sure the TeamsTfwStartupTask registry key is roamed. FSLogix ODFC containers don't roam this registry key, so you must rely on your other profile management tools (Omnissa DEM, AppSense, Citrix UPM) to persist this key.

## Profile and cache location for the Teams Client

All the user settings and configurations are now stored in:

- C:\Users&lt;username&gt;\AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\
- C:\Users&lt;username&gt;\AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\Settings\settings.dat
- C:\Users&lt;username&gt;\AppData\Local\Publishers\8wekyb3d8bbwe\TeamsSharedConfig\app\_switcher\_settings.json
- C:\Users&lt;username&gt;\AppData\Local\Publishers\8wekyb3d8bbwe\TeamsSharedConfig\tma\_settings.json

Make sure these folders and files are persisted for proper Teams functioning.

Note

It's critical that **all** the necessary directories and top folder structure under AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe are correctly set up as directories, not as files or reparse points, and roam with the user's profile:

AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\AC AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\AppData AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\LocalCache AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\LocalState AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\RoamingState AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\Settings AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\SystemAppData AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\TempState

The folder "meeting-addin" under TeamsSharedConfig shouldn't be persisted, as persisting could cause issues with the default meeting coordinates in the meeting templates inserted into Outlook.

Important

Microsoft recommends FSLogix 2210 HotFix 4 ([2.9.8884.27471](/en-us/fslogix/overview-release-notes#fslogix-2210-hotfix-4-29888427471)) in order to guarantee proper integration with the Teams client in VDI. The following issues have been addressed on that release:

- Windows Server 2019 would sometimes fail to query the provisioned AppX applications for the user during sign-out.
- [MSIX folders that should not be backed](/en-us/fslogix/troubleshooting-appx-issues#non-roamable-folders-not-backed-up) up would be removed during sign-out instead of only removing the contents of those folders.
- New Microsoft Teams crashes or fails to start in Windows Server 2019.
- New Microsoft Teams would display an error during launch with **The parameter is incorrect**.
- New Microsoft Teams would display an error during launch with **Invalid function**.
- New Microsoft Teams wouldn't on-demand register during sign-in when using the ODFC container.
- New Microsoft Teams wouldn't on-demand register during profile creation and wouldn't register during future sign-ins, despite being installed.
- User-based Group Policy settings would persist in the user's profile after the policy setting was removed or set to disabled.

*Note:* Customers using Profile and ODFC, or just ODFC containers, still need to add the setting 'IncludeTeams' for the Teams user data/cache to be preserved.

Note

[Folder Redirection or Roaming User Profiles](/en-us/windows-server/storage/folder-redirection/folder-redirection-rup-overview) aren't supported with the Teams client in VDI environments since they can't roam folders in AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\LocalCache\Microsoft\MSTeams. Customers can continue to use Folder Redirection or Roaming User Profiles with a complementary product, such as FSLogix, Citrix Profile Manager, and Omnissa DEM, that can roam the Appdata\Local folders.

Important

Citrix recommends Citrix Profile Manager version 2402 or 2203 CU5. Those versions address Teams registrations errors and "the parameter is incorrect" error when trying to launch the application. If customers still experience Teams related issues, reach out to Citrix for a private build for 2402 CU1 or 2203 CU6.

Omnissa customers using DEM in combination with the Windows OS Optimization Tool might experience Teams app launch failures if the setting 'Clean Default User Profile' is checked under 'Choose information to clear' in the tool's UI.

### Folder exclusions

#### Disk storage usage

To make it easier to distribute our client to Windows devices, support is added for MSIX, which improves the dependability of installations and app updates, as well as reduces network bandwidth and disk space consumption. This packaging technology also shows the accurate disk space usage.

#### Disk Footprint - Key folders and location

- **App installer**: C:\Program Files\WindowsApps\MSTeams\_[version]\_[arch]\_\_8wekyb3d8bbwe Includes the installation package, supports the ability to reset the app, and allows single instancing.
- **User and app data**: C:\Users&lt;alias&gt;\AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe Includes code (JavaScript bundles), code cache, browser caches, databases for user data (like conversations, which scale based on usage), and web storage (from domains hosted within Teams, such as Sharepoint, Viva Learning, Apps, and so on).

For non-persistent setups where storage footprint is a consideration, the following guidance applies:

##### Recommended for exclusion

| Folder | Folder path | Role | Exclusion impact |
| --- | --- | --- | --- |
| **Logs** | LocalCache\Microsoft\MSTeams\Logs LocalCache\Microsoft\MSTeams\PerfLog | Diagnostics, perf logs, and so on. | No impact. |
| **WebStorage** | LocalCache\Microsoft\MSTeams\EBWebView\WV2Profile\_tfw\WebStorage | Storage used and managed by the browser when accessing other web apps inside a web app using iframes. For example, loading Sharepoint, OneDrive and office apps within Teams. | Loading these apps again could be slower after clearing this cache. |
| **GPU Cache** | LocalCache\Microsoft\MSTeams\EBWebView\WV2Profile\_tfw\GPUCache | GPU cache. | No impact. |
| **StartMenuExperienceHost** | AppData\Local\Packages\Microsoft.Windows.StartMenuExperienceHost\_cw5n1h2txyewy\TempState | Responsible for the **Start Menu** button and the tiles within it. | No impact. The exclusion is recommended to solve a missing Teams icon in the Start menu issue. |
| **ShellExperienceHost (For Windows Server 2019 only)** | AppData\Local\Packages\Microsoft.Windows.ShellExperienceHost\_cw5n1h2txyewy\TempState | Responsible for the **Start Menu** button and the tiles within it. | No impact. The exclusion is recommended to solve a missing Teams icon in the Start menu issue. |

##### Review tradeoff considerations, requiring evaluation and testing for these environments

| Folder | Folder path | Role | Exclusion impact |
| --- | --- | --- | --- |
| **Service worker** | LocalCache\Microsoft\MSTeams\EBWebView\WV2Profile\_tfw\ Service Worker\CacheStorage LocalCache\Microsoft\MSTeams\EBWebView\WV2Profile\_tfw\Code Cache | Code and caching of Web/JS Scripts for the app to run. | - Reduced performance to download and load scripts on every app launch - No offline access to app |
| **IndexedDB** | LocalCache\Microsoft\MSTeams\EBWebView\WV2Profile\_tfw\IndexedDB | Holds app and user data and is the recommended way to cache data at scale in a web app to improve responsiveness. | - Significantly higher app launch times as data (such as chat or channel conversations) must be pulled down, along with network usage as data needing to be downloaded and cached every time. - The size of the data varies based on the user profile. - Users might see **We're setting things up for you** in the launch splash-screen. |
| **Cache** | LocalCache\Microsoft\MSTeams\EBWebView\WV2Profile\_tfw\Cache | Cache used and managed by the browser for the contents of all network calls that leave the app. Also known as Disk Cache. | For example, the browser caches Teams profile pictures in this storage. These pictures need to be downloaded again. |

Other than the folders in this section, we don't recommend excluding additional directories.

## Teams and Outlook integration

The selection of the "Register the new Teams as the chat app for Microsoft 365" checkbox under **Settings &gt; General &gt; System** lets the Teams client integrate with all the Microsoft 365 apps that have instant message capabilities (presence, chat, VOIP, and so on).

For example, Outlook goes through the discovery process outlined here to integrate with the default IM client application: [Integrating IM applications with Office](/en-us/office/client-developer/shared/integrating-im-applications-with-office#discovering-the-im-application)

### Teams Meeting add-in

Additionally, the Teams MSIX package bundles the Teams Meeting add-in (or TMA) MSI ("MicrosoftTeamsMeetingAddinInstaller.msi"). TMA lets you schedule a Teams meeting from Outlook.

For Security articles related to TMA integration with the Outlook client, learn more at [**Teams meeting add-in security when using your Outlook client**](/en-us/microsoftteams/teams-meeting-addin-security-with-outlook).

All Teams files installed on the computer are signed, so IT admins can use [AppLocker](/en-us/microsoftteams/applocker-in-teams)/Code Integrity/Windows Defender Application Guard policies configured to for enforcement.

- For Teams per-user installations of TMA, the install folder is in AppData\Local\Microsoft\TeamsMeetingAdd-in
- Installation logs for TMA MSI are stored here: *AppData\Local\Packages\MSTeams\_8wekyb3d8bbwe\LocalCache\Microsoft\MSTeams\Logs \tma\_addin\_msi.txt*

Note

In non-persistent environments (for example, Windows Server or Windows 10/11 Single or Multiuser), installation of MicrosoftTeamsMeetingAddinInstaller.msi can fail with the error *"Installation success or error status: 1625."*.

This error is caused by GPOs affecting Windows Installer, and includes [**DisableUserInstalls**](/en-us/windows/win32/msi/disableuserinstalls), [**DisableMSI**](/en-us/windows/win32/msi/disablemsi), or AppLocker policies based on Publisher rule conditions, or a RuleCollection for MSI installs. In this case, you must create an exception such as:

- FilePathCondition Path="%PROGRAMFILES%\WINDOWSAPPS\*\MICROSOFTTEAMSMEETINGADDININSTALLER.MSI"

#### Deployment method for non-persistent environments where Teams autoupdate is disabled

Note

teamsbootstrapper.exe (Product version 1.0.2508703) now supports an additional parameter that installs Teams Meeting Add In (TMA) for Outlook automatically, in a machine-wide installation fashion (for example, msiexec /ALLUSERS=1).

-Fresh install (provisions Teams and installs TMA machine-wide): teamsbootstrapper.exe -p --installTMA

-If Teams was already provisioned and you want to install TMA only: teamsbootstrapper.exe --installTMA

-Uninstall TMA (Outlook Classic must be closed): teamsbootstrapper.exe --uninstallTMA

-Uninstall Teams and TMA (Outlook Classic must be closed): teamsbootstrapper.exe -x

-If Teams isn't provisioned (isn't present or failed to provision), TMA isn't installed

-Running teamsbootstrapper.exe -p or teamsbootstrapper.exe -p -o "full path to msix" alone doesn't install TMA machine-wide

-Outlook Classic must be closed when trying to uninstall TMA using the bootstrapper

If Administrators don't want to use the new --installTMA flag, they can still install the TMA MSI located in the Teams installation directory from an Admin Command prompt using:

```powershell

msiexec.exe /i "C:\Program Files\WindowsApps\MSTeams_X.X.X.X_x64__8wekyb3d8bbwe\MicrosoftTeamsMeetingAddinInstaller.msi" ALLUSERS=1 /qn /norestart TARGETDIR="C:\Program Files (x86)\Microsoft\TeamsMeetingAdd-in\<version>\"

```

- TARGETDIR must be kept consistent across installs so that the Teams Meeting Add-in MSI can detect and clean up older versions. If multiple directories are used, then the installation may not behave as expected.
- **X.X.X.X** needs to be replaced by the Teams version. Make sure there's a double underscore between the CPU architecture (x64) and the PublisherID (8wekyb3d8bbwe). The exact version number can be extracted by running this command in PowerShell:

    ```powershell
    
    Get-AppXPackage -Name "*msteams*" | Select-Object -ExpandProperty Version
    
    ```
- **version** must be replaced with the MSI file version, for example, 1.24.2203.0. The exact version number can be extracted by running this command in PowerShell:

```powershell

PS C:\WINDOWS\system32> Get-AppLockerFileInformation -Path "C:\PROGRAM FILES\WINDOWSAPPS\MSTEAMS_24026.1000.2656.1710_X64__8WEKYB3D8BBWE\MICROSOFTTEAMSMEETINGADDININSTALLER.MSI" | Select -ExpandProperty Publisher | select BinaryVersion

BinaryVersion

1.24.2203.0

```

**Example:** The following are examples of the final command:

```command

msiexec.exe /i "C:\Program Files\WindowsApps\MSTeams_23320.3021.2567.4799_x64__8wekyb3d8bbwe\MicrosoftTeamsMeetingAddinInstaller.msi" ALLUSERS=1 /qn /norestart TARGETDIR="C:\Program Files (x86)\Microsoft\TeamsMeetingAdd-in\1.24.2203.0\"
```

The following PowerShell script can be used as a reference for deployment. Customers should validate in their QA/TEST environments:

```powershell
If (-not ([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([Security.Principal.WindowsBuiltInRole] 'Administrator') ){
    Write-Error "Need to run as administrator. Exiting.."
    exit 1
}

# Get Version of currently installed Teams Package
if (-not ($NewTeamsPackageVersion = (Get-AppxPackage -Name MSTeams).Version)) {
    Write-Host "Teams Package not found. Please install Teams from https://aka.ms/GetTeams ."
    exit 1
}
Write-Host "Found Teams Version: $NewTeamsPackageVersion"

# Get Teams Meeting Addin Version
$TMAPath = "{0}\WINDOWSAPPS\MSTEAMS_{1}_X64__8WEKYB3D8BBWE\MICROSOFTTEAMSMEETINGADDININSTALLER.MSI" -f $env:programfiles,$NewTeamsPackageVersion
if (-not ($TMAVersion = (Get-AppLockerFileInformation -Path $TMAPath | Select-Object -ExpandProperty Publisher).BinaryVersion))
{
    Write-Host "Teams Meeting Addin not found in $TMAPath."
    exit 1
}
Write-Host "Found Teams Meeting Addin Version: $TMAVersion"

# Install parameters
$TargetDir = "{0}\Microsoft\TeamsMeetingAdd-in\{1}\" -f ${env:ProgramFiles(x86)},$TMAVersion
$params = '/i "{0}" TARGETDIR="{1}" /qn ALLUSERS=1' -f $TMAPath, $TargetDir

# Start the install process
write-host "executing msiexec.exe $params"
Start-Process msiexec.exe -ArgumentList $params
write-host "Please confirm install result in Windows Eventlog"
```

After installation, restart Outlook and verify TMA is loading. Logs are located on %localappdata%\Temp\Microsoft\Teams\meeting-addin.

For Teams Meeting add-in troubleshooting articles, learn more at: [**Resolve issues with Teams Meeting add-in for Outlook**](/en-us/microsoftteams/troubleshoot/meetings/resolve-teams-meeting-add-in-issues).

### Troubleshooting Teams and Outlook integration

#### Symptoms

You see any of the following issues when you check the presence status for a user in Outlook:

- The presence indicator isn't visible.
- The displayed presence is incorrect.
- The presence status is **Status unknown**.

#### Troubleshooting steps

1. Make sure Teams is running. Then launch Outlook.
2. Check the registry settings on your computer to verify that Teams is registered as the default instant messaging (IM) app.

    1. Start Registry Editor.
    2. Locate the following subkey: `HKEY_CURRENT_USER\Software\IM Providers`
    3. Verify the following values:

    ```
     - **Name:** DefaultIMApp
     - **Type:** REG_SZ
     - **Data:** MsTeams
     ```
    
    ```
3. Locate the following subkey:

    - HKEY\_CURRENT\_USER\Software\IM Providers\MsTeams (Outlook monitors this registry key for value changes)
4. Verify the following values:

    -Name: UpAndRunning -Type: REG\_DWORD -Data: 2 (0—Not running, 1—Starting, 2—Running)
5. If the issues persist, contact Microsoft Support.

## Control fallback mode in Teams

When users connect from an unsupported endpoint, the users are in fallback mode, in which Audio/Video isn't optimized. You can disable or enable fallback mode by setting one of the following registry DWORD values:

`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback``HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

- This registry key can only be processed by Teams 24257.x.x.x or higher.
- To disable fallback mode, set the value to 1.
- To enable audio only, set the value to 2.
- If the value isn't present or is set to 0 (zero), fallback mode is enabled.
- On Fallback, screen sharing functionality is supported with a different screen picker UI (similar to the experience a user would see on Teams for Web).

## Multitenant and Multi-account in VDI

Teams in VDI allows you to sign in quickly and easily, and allowing you to switch between multiple accounts and organizations **from the same** Microsoft 365 cloud environment.

Note

Cross cloud guests and Cross cloud meetings aren't supported on VDI. For more information, see [Collaborate with guests from other Microsoft 365 cloud environments](collaborate-guests-cross-cloud) and [Manage accounts and organizations in Microsoft Teams](https://support.microsoft.com/office/manage-accounts-and-organizations-in-microsoft-teams-7b221128-6643-465c-a317-679e48cd2ce9).

If any of your accounts have guest access to other organizations, you don't need to add them--they appear automatically. A guest is someone from outside an organization that a team owner invites to join the team, such as a partner or consultant. Guests have fewer capabilities than team members or team owners.

Learn more: [Manage accounts and organizations in Microsoft Teams](https://support.microsoft.com/office/manage-accounts-and-organizations-in-microsoft-teams-7b221128-6643-465c-a317-679e48cd2ce9)

## Features currently not available and known issues in VDI with Teams

- AVD/W365 users optimized with WebRTC fail to see incoming video/screensharing if they are on a virtual desktop running Windows 11 24H2/25H2 (26100.6725 and 26200.6725 or higher) and User Account Control (UAC) is disabled. Current workaround for this issue requires Administrators to enabled UAC on the Windows virtual machine.
- Microsoft Teams optimization isn't supported in nested or double hop scenarios (i.e. launching a second virtual desktop from another virtual desktop).
- In some scenarios, Citrix RemotePC users might experience a Teams crash and restart loop when using VDA 2411 and accessing Teams locally (not via HDX). Check CTX585013 for more details.
- Teams doesn't on-demand register during FSLogix profile creation (even with HotFix 4), and doesn't register during future sign-ins, despite being installed. A race condition between Process Lifetime Manager (PLM) service and AppxSvc causes this issue. causing a transient failure when updating the package with error 0x80004001 (E\_NOTIMPL). If the PLM service isn't running, Teams registration fails.
    - (In MSIX, Registration occurs on a per-user basis and begins when a user logs on. The OS then loads the preinstalled packaged app, creating user-specific app data, FTAs, and app tiles in the Start menu. This action is done by the AppReadiness Service, which is aware of all preinstalled apps and requests the Appx Deployment Service (AppxSvc) deploy those packages.)
    - Customers hitting this error, even with FSLogix Hotfix 4, must deploy these fixes:
        - Windows 11 21H2 [KB5043067](https://support.microsoft.com/topic/september-10-2024-kb5043067-os-build-22000-3197-62287850-4f0d-4e4a-9fe8-b026bb1be994)
        - Windows Server 2022 [KB5042881](https://support.microsoft.com/topic/september-10-2024-kb5042881-os-build-20348-2700-5b548143-9613-4e5a-9454-8ed9be8b2bd2)
        - Windows Server 2019 [KB5043050](https://support.microsoft.com/topic/september-10-2024-kb5043050-os-build-17763-6293-66e9809a-1838-4474-a6a7-90d64f042f00)
    - This bug is addressed with [KB5037849](https://support.microsoft.com/help/5037849) for Windows 10 (May 2024). The issue isn't present on Windows 11 22H2 or higher.
- Teams fails to launch for users logging into single-user non-persistent Windows 10 virtual desktops, or the app isn't visible in the Start menu. But the app might become visible and launches successfully 15 minutes after logging in.
    - This issue is addressed in [KB5041582](https://support.microsoft.com/topic/august-29-2024-kb5041582-os-build-19045-4842-preview-f4c4d191-5457-475c-80ac-e1d43cf9c941)[KB5041587](https://support.microsoft.com/topic/august-27-2024-kb5041587-os-builds-22621-4112-and-22631-4112-preview-9706ea0e-6f72-430e-b08a-878963dafe08) for Windows 10/11, and Teams 24215.1007.3082.1590 (or higher) - both components are needed.
    - You might also need to exclude the following location from your roaming profile solution (for FSLogix customers, as an example, via redirections.xml): `AppData\Local\Packages\Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy\TempState`.
    - **NOTE** - The issue isn't seen in **multi-user** Windows 10 or 11. For Windows 2019. A fix to resolve this issue is available: [KB5044227](https://support.microsoft.com/topic/october-8-2024-kb5044277-os-build-17763-6414-edccc872-2f4e-4ac6-b224-50ca8f1acd4f).
- Customers installing Teams on a golden image, which later undergoes a sysprep to generalize it, are failing to launch the app. This circumstance includes templates from Azure Image Gallery.
    - Users logging in to the provisioned virtual machines see the Teams icon greyed out in the start menu and clicking on it has no effect.
    - The AppX log in the Event Viewer has the error 0x80073CF1.
    - Running `Get-AppxPackage -name MsTeams -allusers` from an elevated PowerShell window shows that PackageUserInformation is in a **Paused state** for SID S-1-15-18 (LocalSystem). This error isn't seen on W11 22H2 or higher. Install [KB5039299](https://support.microsoft.com/topic/june-25-2024-kb5039299-os-build-19045-4598-preview-d4e3e815-fdd8-465e-8144-42afa165efed) for Windows 10 [KB5040437](https://support.microsoft.com/topic/july-9-2024-kb5040437-os-build-20348-2582-5b28d9b8-fcba-43bb-91e6-062f43c7ec7c) for WS2022, and [KB5040431](https://support.microsoft.com/topic/july-9-2024-kb5040431-os-build-22000-3079-346db750-842d-41b8-a55a-103cc04d175a) for W11 21H2.
- Screen sharing from chat for Azure Virtual Desktops/Windows 365 (This issue is now fixed on RD Client 1.2.5105 and Redirector Service [1.50.2402.29001](/en-us/azure/virtual-desktop/whats-new-webrtc#updates-for-version-150240229001)).
- Screen sharing from chat for Citrix when using Workspace app 2311 only.
- msteams\_autostart.exe "The parameter is incorrect": In non-persistent environments that use FSLogix (any version before 2210 HotFix 4) or Citrix Profile Manager profile containers, when Teams attempts to autostart or a user tries to launch Teams from the Start menu, it throws the error: "The parameter is incorrect." The frequency and reproducibility of the error varies depending on the environment and especially the antivirus software being used (SentinelOne, Palo Alto, Trend Micro, Bitdefender, CrowdStrike, and so on.) and exclusions in place. This issue is now fixed on FSLogix 2210 HotFix 4. Customers facing this issue with Citrix Profile Manager must upgrade to CPM 2402 or 2203 CU5.
    - "The parameter is incorrect" error can be caused by other file system drivers. Running fltmc from an elevated command window lists the drivers. Two Citrix drivers (UPMAction and upmjit) can cause the error, even if you're only using FSLogix HotFix 4 and don't have Citrix Profile Manager. This error happens because Citrix VDA installers typically install profilemgt\_x64.msi by default for Citrix Director monitoring of logon time counters. Removing that MSI can fix "the parameter is incorrect" error.
- Teams fails to launch for users logging into non-persistent virtual desktops, or the app is **not**visible in the Start menu.
    - Admins don't experience this issue - after installing Teams on the golden image they can launch it successfully.
    - After you seal the golden image and deploying it at scale (with provisioning tools like Citrix MCS/PVS or Omnissa Instant-Clones), users log in to the virtual machines and select the Teams icon, but aren't able to launch the app. The issue is caused by a failed registration of the MSIX package at the user level with different profile management software (FSLogix before 2210 HotFix 4, Citrix CPM 2308 or 2311 **but not on 2402**, Ivanti UEM, and so on), even though the staging of the package was successful (the OS stored the package's contents on the disk in the %ProgramFiles%\WindowsApps directory). This issue can be confirmed by running Get-AppxPackage -name MsTeams for the affected users. Running this code returns an empty output.
    - If Get-AppxPackage -name MsTeams -allusers is run from an elevated PowerShell command window, the output shows that Teams is registered (see line PackageFullName) and the Status is **OK**.
    - This issue is fixed in FSLogix 2210 HotFix 4.
- When you use Azure Virtual Desktops or Windows 365, and the MAC Remote Desktop Client or Windows app, Microsoft Teams UI doesn't enumerate all the peripherals connected to the device. Instead, only the device selected at the macOS-level is shown in the Devices' drop-down menu of Microsoft Teams. The peripheral is labeled. "MAC device name" + "Speakers" is an example of this labeling.
- Teams meetings can't be launched when selecting a link from Outlook. There's an authentication prompt (Access to '{tenant}' tenant is denied) when users attempt to join an **external** meeting. This issue is fixed in Teams 24091.214.2846.1452.

## Teams for web in VDI

Teams for Web isn't supported in VDI environments, so performance and reliability may be negatively impacted if used in VDI.

## Features not supported in VDI

The following features aren't supported in Teams when using the WebRTC-based optimization. Most of these limitations are addressed with the new SlimCore-based optimization. Check out the [Feature list with the new optimization](vdi-2#feature-list-with-the-new-optimization) section of our VDI 2.0 article for more information.

- QoS.
- 1080p.
- Custom Backgrounds uploaded by users.
- Teams Premium features (End to End Encryption, Watermark, Premium Events aren't optimized, Custom meeting backgrounds for organizations).
- Avatars.
- Gallery View 3x3 and 7x7.
- Noise Suppression (except for Azure Virtual Desktop/W365, where noise suppression is on by default, but confirmation isn't shown in Teams client UI. This behavior is by design).
- Zoom In / Out.
- Media Bypass.
- HID (Citrix only).
- Share System Audio (Omnissa only).
- Broadcast and live event producer and presenter roles.
- Cross cloud in Government Clouds (GCC, GCC High, and DoD) and Sovereign Clouds operated by 21Vianet
- **Record video clip** doesn't capture screen share.
- The call monitor (the small floating window after you minimize the main Teams window) doesn't display video or screen share.
- Teams calls drop on a local machine that has an HID peripheral connected if a user launches a virtual desktop from that local machine and logs into Teams (Azure Virtual Desktop/W365 and Omnissa with both WebRTC and SlimCore, Citrix with SlimCore only).
- Organizers and presenters can't join [large-scale](plan-events) events, such as town halls.