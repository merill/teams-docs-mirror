---
layout: Conceptual
title: Direct Routing SBA - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-survivable-branch-appliance
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.date: 2026-09-23T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Learn about Direct Routing Survivable Branch Appliance (SBA).
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
locale: en-us
document_id: 183fc921-e9b1-cc74-2bcb-26d32b994919
document_version_independent_id: 1765bda3-dd62-76d7-1e2d-9f5496ac9094
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-survivable-branch-appliance.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-survivable-branch-appliance
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-survivable-branch-appliance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 8bf9c553-3bc9-2f37-9b1c-3b5aca36856f
---

# Direct Routing SBA - Microsoft Teams | Microsoft Learn

Occasionally, a customer site that uses Direct Routing to connect to Microsoft Teams Phone may experience an internet outage.

In this scenario, assume that the customer site--called a branch--temporarily can't connect to the Microsoft cloud through Direct Routing. However, the intranet inside the branch is still fully functional, and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.

This article describes how to use a Survivable Branch Appliance (SBA) with Teams Phone to support continuity of making and receiving Public Switched Telephone Network (PSTN) calls in case of an outage.

## Prerequisites

The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have the SBA run on a separate VM or hardware.

To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance, contact your SBC vendor. In addition, the following is required:

- The SBC is configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.
- TLS1.2 is enabled on the SBA VM OS.
- Ports 3443, 4444, and 8443 are used by Microsoft SBA Server to communicate with the Teams client and is allowed on the firewall.
- Port 5061 (or the one configured on the SBC) is used by Microsoft SBA Server to communicate with the SBC and is allowed on the firewall.
- UDP Port 123 is used by Microsoft SBA Server to communicate with NTP server and is allowed on the firewall.
- Port 443 is used by Microsoft SBA Server to communicate with Microsoft 365 and is allowed on the firewall.
- Azure IP Ranges and Service Tags for the Public Cloud are defined according to the guidelines described at: https://www.microsoft.com/download/details.aspx?id=56519

## Supported Teams clients

The SBA feature is supported on the following Microsoft Teams clients:

- Microsoft Teams Windows desktop
- Microsoft Teams macOS desktop
- Teams Phones

## How it works

During an internet outage, the Teams client automatically switches to the SBA, and ongoing calls continue with no interruptions. The user doesn't need to take any action.

As soon as the Teams client detects that the internet is up, and any outgoing calls are finished, the client falls back to normal operation mode, and connects to other Teams services. The SBA uploads collected Call Data Records to the cloud. Call history is updated for review by the tenant administrator.

The Teams client-side outage mechanism for the SBA is designed to ensure continuous connectivity and service availability during network disruptions.

The following conditions must be met:

- Client policy check: The user is assigned the branch survivability policy for an SBA that the Teams client connects to--only if the appliance is up.
- Network status check: The Teams client connects to the SBA when the internet is disconnected, but the user's device is still connected to the SBA appliance.

Once these conditions are met, the Teams client pings the SBA appliance, and the client checks the policy. If both of these conditions are met, the following occurs:

- Branch Survivability Policy: The branch survivability policy points to the SBA URLs assigned to the user/tenant.
- Connection to the SBA on the Teams client side: Once the Teams client is offline and the user has the required policies, the Teams client switches to Appliance mode where the user can make and receive PSTN calls. A banner is displayed to inform users of the switch to the SBA.

    The only UI indicator of the switch to Appliance mode is the banner. If the banner isn't present, the user isn't in SBA mode, and calling won't work.

SBA mode activates only on desktop clients on a physical machine. VMs and web clients aren't supported at the moment.

When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:

- Make PSTN calls through the local SBA/SBC with media flowing through the SBC.
- Receive PSTN calls through the local SBA/SBC with media flowing through the SBC.
- Hold and resume PSTN calls.
- Blind transfer.
- Call forwarding to a single phone number or Teams user.
- Unanswered call forwarding to single phone number or Teams user.
- Redirect incoming PSTN call to a call queue or auto attendant number to a local agent.
- Redirect incoming PSTN call to a call queue or auto attendant number to an alternative call queue or auto attendant number.
- VoIP fallback. If a VoIP call can't be initiated and the receiving party has a PSTN number, a PSTN call is attempted.
- VoIP calls between local users. If both users are registered behind the same SBA, a VoIP call can be initiated instead of PSTN call, and the SBA will support the call.

## Configuration

For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site. The configuration steps are as follows:

1. Create the SBAs.
2. Create the Teams branch survivability policy.
3. Assign the policy to users.
4. Register an application for the SBA with Microsoft Entra ID.

Use Teams PowerShell cmdlets for all configuration. (The Teams admin center doesn't yet support the Direct Routing SBA feature.)

For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration.

### Create the SBAs

To create the SBAs, use the New-CsTeamsSurvivableBranchAppliance cmdlet. This cmdlet has the following parameters:

| Parameter | Description |
| --- | --- |
| Identity | The identity of the SBA |
| Fqdn | The FQDN of the SBA |
| Site | The TenantNetworkSite where the SBA is located |
| Description | Free format text |
|  |  |

For example:

```powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### Create the Teams Branch Survivability Policy

To create a policy, use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet. This cmdlet has the following parameters. The policy can contain one or more SBAs.

| Parameter | Description |
| --- | --- |
| Identity | The identity of the policy |
| BranchApplianceFqdns | The FQDN of the SBA(s) in the site |
|  |  |

For example:

```powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet. For example:

```powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### Assign a policy to a user

To assign the policy to individual users, use the **Grant-CsTeamsSurvivableBranchAppliancePolicy** cmdlet. This cmdlet has the following parameters:

| Parameter | Description |
| --- | --- |
| Identity | The identity of the user |
| PolicyName | The identity of the policy |
|  |  |

For example:

```powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

You can remove a policy from a user by granting the `$Null` policy as shown in the following example:

```powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### Register an application for the SBA with Microsoft Entra ID

To allow different SBAs used within your tenant to read required data from Microsoft 365, register an application for the SBA with Microsoft Entra ID.

For more information about application registration, see the following articles:

- [Develop line-of-business apps for Microsoft Entra ID](/en-us/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)
- [Register an application with the Microsoft identity platform](/en-us/azure/active-directory/develop/quickstart-register-app).

You only need to register one application for use by all the SBAs in your tenant.

For the SBA registration, you need the following values created by the registration:

- Application (client) ID
- Client secret

For the SBA application, keep the following in mind:

- The name can be whatever you decide.
- Supported account types = Account in this organizational directory only.
- The Web Redirect Uri = `https://login.microsoftonline.com/common/oauth2/nativeclient`.
- Implicit grant tokens = Access tokens and ID tokens.
- API permissions = Skype and Teams Tenant Admin Access -&gt; Application permissions -&gt; application\_access\_custom\_sba\_appliance.
- Client secret: use any description and expiration.
- Copy the client secret immediately after creating it.
- The Application (client) ID is shown on the Overview tab.

Then follow these steps:

1. Register the application.
2. Set the implicit grant tokens.
3. Set the API permissions.
4. Create the client secret.

## Session Border Controller configuration

For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:

- [AudioCodes](https://www.audiocodes.com/library/technical-documents?query=sba)
- [Ribbon](https://support.sonus.net/pages/viewpage.action?pageId=248644034)
- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)
- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## Known issues and considerations

The following list describes known issues and considerations:

- In SBA mode

    - The SBA supports expired client authentication tokens for up to seven days from the token expiration.
    - During an internet outage, the Teams desktop client can reconnect to the SBA using locally cached authentication information, even after a Teams client restart or machine reboot. This requires the necessary authentication information to have been cached before the outage and to remain available within the supported SBA authentication period.
    - The Teams client can't validate itself with an SBA that it didn't previously connect with in the last 24 hours.
- In SBA mode, the following user actions aren't supported:

    - Switching their Teams client to another tenant.
    - Sharing location information during an emergency call (E911). Users can still make emergency call but location information won't be shared.
    - SBA does not support Emergency Call Routing Policies. EMER dial strings bypass normalization and are always sent without +. Because of this, if the customer has no pattern attached to their regular voice routing policy matching the EMER Dial strings, emergency calls will fail via SBA.
    - Reaching other Teams users with reverse number lookup against Microsoft Entra ID Contacts. A dialed number will still be processed by SBA and routed over PSTN.
- If the tenant is using Continuous Access Evaluation (CAE) tokens, the SBA will be operational only for about 30 minutes, due to the nature of continuous access evaluation. An alternative would be to disable CAE for the tenant.
- When you add new Survivable Branch Appliances, it might take time before you can use them in Survivable Branch Appliance policies.
- When you assign a Survivable Branch Appliance policy to a user, it might take time before the SBA is shown in the output of `Get-CsOnlineUser`.

## Report an issue

Report any issues to your SBC vendor's support organization. When reporting the issue, indicate that you have a configured Survivable Branch Appliance.