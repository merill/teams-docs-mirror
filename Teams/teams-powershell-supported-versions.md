---
layout: Conceptual
title: Teams PowerShell Module - Supported Versions - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-powershell-supported-versions
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
ms.date: 2022-01-08T00:00:00.0000000Z
manager: sshastri
ms.topic: reference
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.collection:
- M365-collaboration
description: Learn about versions supported of the Teams PowerShell Module, used for administration of Microsoft Teams.
locale: en-us
document_id: 8c413445-e3d6-d6b8-4671-bd737bbdf130
document_version_independent_id: 8c413445-e3d6-d6b8-4671-bd737bbdf130
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-powershell-supported-versions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-powershell-supported-versions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-powershell-supported-versions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: aadf6383-64da-270b-5dde-688f4e7bb5eb
---

# Teams PowerShell Module - Supported Versions - Microsoft Teams | Microsoft Learn

Microsoft Teams PowerShell Module (TPM) versions in the 4.x.x series or later are the only versions supported now. All earlier versions are fully retired.

It’s recommended to update to the latest Teams PowerShell Module version.

## Important notes

- Release notes for all the Teams PowerShell Module versions can be found at [Teams PowerShell release notes](teams-powershell-release-notes).
- To update any PowerShell module, you should use the same method used to install the module. For example, if you originally used Install-Module, then you should use [Update-Module](/en-us/powershell/module/powershellget/update-module) to get the latest version.

    ```powershell
    Update-Module MicrosoftTeams
    ```
- If updating from Teams PowerShell Module version 1.1.6, update your scripts to use `Connect-MicrosoftTeams` instead of `New-CsOnlineSession`.
- During the update, it's suggested to not use TPM 4.x.x/3.x.x alongside versions earlier than 3.0.0. For example, using versions 4.x.x & 2.6.0 together for different admin operations in the same organization isn't recommended.
- Related changes

    - Updates to Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.x.x and later – more details in [Get-CsOnlineUser](/en-us/powershell/module/teams/get-csonlineuser) & [Get-CsOnlineVoiceUser](/en-us/powershell/module/teams/get-csonlinevoiceuser) (Message center post – MC340774/MC511150).
    - Changes coming to Phone number assignment - more details in [Set-CsUser](/en-us/powershell/module/teams/set-csuser), [Set-CsOnlineVoiceUser](/en-us/powershell/module/teams/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/en-us/powershell/module/teams/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/en-us/powershell/module/teams/set-csonlinevoiceapplicationinstance) (Message center post – MC316139).
    - Parameter changes in Get-CsTenant - more details in [Get-CsTenant](/en-us/powershell/module/teams/get-cstenant) (Message center post – MC365397).
    - If your scripts use New/Set of Policy or Configuration cmdlets with PSListModifier type parameters, it’s recommended to use the latest version (4.2.0 or later). Message center post for reference - MC397428.
    - [New|Get]-CsCloudCallDataConnection cmdlets are now supported from versions 4.6.0 or later (Message center post - MC408993).
    - [New|Remove]-CsHybridTelephoneNumber cmdlets are now supported from versions 4.5.0 or later in GCC High and DoD environments.
- While using TPM 4.x.x or later, it's recommended to not use any of the deprecated or unsupported cmdlets.

## Deprecated cmdlets

- Following are some of the cmdlets that were deprecated recently. Details on the same can be found in the respective documentations.

    | Cmdlets | Notes / Suggested alternatives |
    | --- | --- |
    | [Get-CsOnlineVoiceUser](/en-us/powershell/module/teams/get-csonlinevoiceuser) | Deprecated only in commercial & GCC environments currently |
    | [Get-CsOnlineTelephoneNumber](/en-us/powershell/module/teams/get-csonlinetelephonenumber) |  |
    | Get-CsOnlineDialInConferencingUserInfo & Get-CsOnlineDialInConferencingUserState | [Get-CsOnlineDialInConferencingUser](/en-us/powershell/module/teams/get-csonlinedialinconferencinguser) |
    | [Enable|Disable]-CsOnlineDialInConferencingUser | To enable/disable Audio Conferencing for a user, assign/unassign the Audio Conferencing license, more information at [Assign licenses to users](/en-us/microsoft-365/admin/manage/assign-licenses-to-users) |
    | [Get-CsOnlineDirectoryTenant](/en-us/powershell/module/teams/get-csonlinedirectorytenant) |  |
    | New-CsOnlineAudioFile | [Import-CsOnlineAudioFile](/en-us/powershell/module/teams/import-csonlineaudiofile) |
    | Get-CsOnlineApplicationEndpoint | [Get-CsOnlineApplicationInstance](/en-us/powershell/module/teams/get-csonlineapplicationinstance) |
    | Set-CsOnlineApplicationEndpoint | [Set-CsOnlineApplicationInstance](/en-us/powershell/module/teams/set-csonlineapplicationinstance), [Set-CsPhoneNumberAssignment](/en-us/powershell/module/teams/set-csphonenumberassignment), [Remove-CsPhoneNumberAssignment](/en-us/powershell/module//teams/remove-csphonenumberassignment) |
    | New-CsOnlineApplicationEndpoint | [New-CsOnlineApplicationInstance](/en-us/powershell/module/teams/new-csonlineapplicationinstance) |
    | [Remove|Switch]-CsOnlineApplicationEndpoint |  |
    | Get-CsOnlineTelephoneNumberInventoryCities, Get-CsOnlineTelephoneNumberInventoryAreas, Get-CsOnlineTelephoneNumberInventoryCountries, Get-CsOnlineTelephoneNumberInventoryRegions, Get-CsOnlineTelephoneNumberInventoryTypes, [Search|Select]-CsOnlineTelephoneNumberInventory, Get-CsOnlineTelephoneNumberAvailableCount, Clear-CsOnlineTelephoneNumberReservation, Get-CsOnlineTelephoneNumberReservationsInformation, Get-CsOnlineDirectoryTenantNumberCities | [New-CsOnlineTelephoneNumberOrder](/en-us/powershell/module/teams/new-csonlinetelephonenumberorder) |
    | [Set-CsTeamsAppSetupPolicy](/en-us/powershell/module/teams/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/en-us/powershell/module/teams/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/en-us/powershell/module/teams/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/en-us/powershell/module/teams/new-csteamsapppermissionpolicy) |  |
    | Test-CsOnlineLisCivicAddress | The validation checks are incorporated into [New-CsOnlineLisCivicAddress](/en-us/powershell/module/teams/new-csonlineliscivicaddress) |
- Cmdlets that aren't supported/relevant for Microsoft Teams scenarios.

    - [Get|Set]-CsUserPstnSettings
    - [Get|Set|Enable|Disable]-CsMeetingRoom
    - [Grant|Get|Set|New|Remove]-CsConferencingPolicy
    - [Grant|Get|Set|New|Remove]-CsClientPolicy
    - [Grant|Get]-CsHostedVoicemailPolicy
    - [Grant|Get|Set|New|Remove]-CsMobilityPolicy
    - [Grant|Get]-CsVoiceRoutingPolicy
    - [Grant|Get]-CsBroadcastMeetingPolicy
    - [Grant|Get]-CsCloudMeetingPolicy
    - [Grant|Get]-CsGraphPolicy
    - [Grant|Get|Set|New|Remove]-CsExternalUserCommunicationPolicy
    - [Grant|Get|Set]-CsIPPhonePolicy
    - Get-CsUserServicesPolicy
    - [Get|Set]-CsBroadcastMeetingConfiguration
    - [Get|Set]-CsOAuthConfiguration
    - [Get|Set]-CsMeetingConfiguration
    - [Get|Set]-CsTenantHybridConfiguration
    - [Get|Set]-CsPushNotificationConfiguration
    - [Get|Set]-CsUCPhoneConfiguration
    - Get-CsImFilterConfiguration
    - Get-CsAudioConferencingProvider
    - [Get|Set]-CsTenantPublicProvider
    - Get-CsHostingProvider
    - [Get|Set|Register|Unregister]-CsHybridPSTNAppliance
    - [Get|Set|New|Remove]-CsHybridPSTNSite
    - [Get|Set]-CsHybridMediationServer
    - [Get|Set|New|Remove]-CsTenantUpdateTimeWindow
    - Get-CsUserLocationStatus
    - Invoke-CsUcsRollback
    - [Get|Set|New|Remove]-CsTeamsPinnedApp
    - [Get|Set|New|Remove]-CsTenantCatalogApp
    - [Get|Set|New|Remove]-CsGlobalCatalogApp
    - [Get|Set|New|Remove]-CsDefaultCatalogApp
    - [Get|Set|New|Remove]-CsTeamsAppPreset
    - Invoke-CsUserPreferredDataLocationSync
    - [Get|Set]-CsTeamsUpgradeStatus
    - Grant-CsPolicy
    - Set-CsOnlineDirectoryUser