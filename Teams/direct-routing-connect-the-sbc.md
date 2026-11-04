---
layout: Conceptual
title: Connect your Session Border Controller (SBC) to Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-connect-the-sbc
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: filippse
ms.date: 2026-04-26T00:00:00.0000000Z
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- NOCSH
description: Learn how to configure and connect your SBC to Teams Phone Direct Routing.
locale: en-us
document_id: ad7d5051-1177-c5cf-bf28-8639d7b6fbd1
document_version_independent_id: 2a9aa4e1-3767-cd46-50fe-f9dd8b0997be
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-connect-the-sbc.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-connect-the-sbc
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-connect-the-sbc.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
platformId: c712bff2-8e97-a314-ad30-6a30e7ed44c4
---

# Connect your Session Border Controller (SBC) to Direct Routing - Microsoft Teams | Microsoft Learn

This article describes how to configure a Session Border Controller (SBC) and connect it to Direct Routing. This is step 1 of the following steps to configure Direct Routing:

- **Step 1. Connect your SBC with Phone System and validate the connection** (This article)
- Step 2. [Enable users for Direct Routing](direct-routing-enable-users)
- Step 3. [Configure call routing](direct-routing-voice-routing)
- Step 4. [Translate numbers to an alternate format](direct-routing-translate-numbers)

For information on all the steps required to set up Direct Routing, see [Configure Direct Routing](direct-routing-configure).

To configure and connect an SBC to Direct Routing, you can use the Microsoft Teams admin center or PowerShell.

Note

For GCC High and DoD clouds, you must use PowerShell. The option to connect the SBC isn't available in the Teams admin center.

## Use the Microsoft Teams admin center

1. In the left navigation, go to **Voice** &gt; **Direct Routing**, and then select the **SBCs** tab.
2. Select **Add**.
3. Enter an FQDN for the SBC. Make sure the domain name portion of the FQDN matches a domain that's registered in your tenant. Keep in mind that the `*.onmicrosoft.com` domain name isn't supported for the SBC FQDN domain name. For example, if you have two domain names, `contoso.com` and `contoso.onmicrosoft.com`, use `sbc.contoso.com` as the SBC name. If using a subdomain, make sure this subdomain is also registered in your tenant. For example, if you want to use `sbc.service.contoso.com`, then `service.contoso.com` needs to be registered.
4. Configure the settings for the SBC, based on your organization's needs. For details on each of these settings, see SBC settings.
5. When you're done, select **Save**.

## Use PowerShell

To connect your SBC to Direct Routing, you need to do the following steps:

1. Connect to Teams by using PowerShell.
2. Connect the SBC to the tenant.
3. Verify the SBC connection.

### Connect to Teams by using PowerShell

To pair the SBC to the Direct Routing interface, use a Teams PowerShell module session connected to the tenant. To open a PowerShell session, follow the steps outlined in [Set up your computer for Windows PowerShell](/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

After you establish a remote PowerShell session, verify that you can see the commands to manage the SBC. To verify the commands, type or copy and paste the following command in the PowerShell session, and then press Enter:

```PowerShell
Get-Command *onlinePSTNGateway*
```

The command returns the four functions shown in the following table that lets you manage the SBC.

```

CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
```

### Connect the SBC to the tenant

To connect the SBC to the tenant, use the [New-CsOnlinePSTNGateway](/en-us/powershell/module/teams/new-csonlinepstngateway) cmdlet. In a PowerShell session, type the following, and then press Enter:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

#### Considerations

- Microsoft recommends that you set a maximum call limit in the SBC using information that can be found in the SBC documentation. If the SBC is at maximum capacity level, the limit triggers a notification.
- You can only connect the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com. Using \*.onmicrosoft.com domain names isn't supported for the SBC FQDN name. For example, if you have two domain names, **contoso**.com and **contoso**.onmicrosoft.com, you can use sbc.contoso.com for the SBC name. If you try to connect the SBC with a name such as sbc.contoso.abc, the system doesn't let you, as the domain isn't owned by this tenant.

    In addition to the domain registered in your tenant, it's important that there's a user with that domain and an assigned E3 or E5 license. If not, you'll receive the following error:`Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
- To assign a user with that domain, the configured authentication type of the domain must be "Managed".
- Multiple IPs mapped with the same FQDN on the SBC side aren't supported.
- To provide the best-in-class encryption to our customers, Microsoft forces TLS1.2 usage for the Direct Routing SIP interface. To avoid any service impact, ensure that your SBCs are configured to support TLS1.2 and can connect using one of the following cipher suites:

    - TLS\_ECDHE\_RSA\_WITH\_AES\_256\_GCM\_SHA384 i.e. ECDHE-RSA-AES256-GCM-SHA384
    - TLS\_ECDHE\_RSA\_WITH\_AES\_128\_GCM\_SHA256 i.e. ECDHE-RSA-AES128-GCM-SHA256
    - TLS\_ECDHE\_RSA\_WITH\_AES\_256\_CBC\_SHA384 i.e. ECDHE-RSA-AES256-SHA384
    - TLS\_ECDHE\_RSA\_WITH\_AES\_128\_CBC\_SHA256 i.e. ECDHE-RSA-AES128-SHA256
- SIP OPTIONS pings MUST NOT exceed a frequency of one transaction every 60 seconds and MUST NOT be more or less frequent than one transaction every 180 seconds for each configured trunk for each endpoint.
- A new option, IPAddressVersion, has been added for SBC configuration via the New-CsOnlinePSTNGateway cmdlet. Possible values are "IPv4" and "IPv6." When "IPv6" is set, the SBC must use IPv6 for both signaling and media. Please note the following are not supported:

    - Media bypass when using IPv6 SIP or media or the IPv6 Teams client
    - Mixed mode SIP and media (IPv6/IPv4).

For details on how to configure IPv6 for Direct Routing consult with your SBC vendor. Refer to the [Plan Direct Routing](/en-us/microsoftteams/direct-routing-plan) page for FQDN and IP details regarding IPv6.

The following example shows only the minimum required parameters. There are additional parameters that you can set with the [New-CsOnlinePSTNGateway](/en-us/powershell/module/teams/new-csonlinepstngateway) cmdlet during the connection process. For more information, see SBC settings.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

This example returns the following information:

```

Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
```

### Verify the SBC connection

To verify the connection, do the following steps:

- Check whether the SBC is on the list of paired SBCs.
- Validate SIP options.

#### Check whether the SBC is on the list of paired SBCs

After you connect the SBC, use the [Get-CsOnlinePSTNGateway](/en-us/powershell/module/teams/get-csonlinepstngateway) cmdlet to verify that the SBC is present in the list of paired SBCs. In a remote PowerShell session, type the following and then press **Enter**:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

The paired gateway should appear in the list as shown in the example below, and the **Enabled** parameter should display a value of **True**.

This example returns the following information:

```

Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com
SipSignalingPort     : 5067
FailoverTimeSeconds   : 10
ForwardCallHistory    : False
ForwardPai            : False
SendSipOptions        : True
MaxConcurrentSessions : 100
Enabled               : True
```

#### Validate SIP options

To validate the pairing using outgoing SIP options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.

When Direct Routing sees incoming OPTIONS, it starts sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.

To validate the pairing using incoming SIP options, use the SBC management interface. Check to see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing, and that the response code it sends is 200 OK.

## SBC settings

This table lists the options that you can set for the SBC in the Microsoft Teams admin center and by using the [New-CsOnlinePSTNGateway](/en-us/powershell/module/teams/new-csonlinepstngateway) cmdlet.

| Required? | Teams admin center setting | PowerShell parameter | Description | Default | Possible values | Type and restrictions |
| --- | --- | --- | --- | --- | --- | --- |
| Yes | **Add an FQDN for the SBC** | FQDN | None | FQDN name, limit 63 characters | String, see the list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264) |  |
| No | **Enabled** | Enabled | Use to turn on the SBC for outbound calls. You can use this to temporarily remove the SBC from service while it's being updated or during maintenance. | False | TrueFalse | Boolean |
| Yes | **SIP signaling port** | SipSignalingPort | This is the listening port that's used to communicate with Direct Routing by using the Transport Layer (TLS) protocol. | None | Any port | 0 to 65535 |
| No | **Send SIP options** | SendSIPOptions | Defines whether the SBC sends SIP options messages. We highly recommend that you turn on this setting. When this setting is off, the SBC is excluded from the Monitoring and Alert system. | True | TrueFalse | Boolean |
| No | **Forward call history** | ForwardCallHistory | Indicates whether call history information is forwarded through the trunk. When you turn this on, the Microsoft 365 proxy sends a History-info and Referred-by header. | False | TrueFalse | Boolean |
| No | **Forward P-Asserted-identity (PAI) header** | ForwardPAI | Indicates whether the PAI header is forwarded along with the call. The PAI header provides a way to verify the identity of the caller. If this setting is on, the Privacy:ID header is also sent. | False | TrueFalse | Boolean |
| No | **Concurrent call capacity** | MaxConcurrentSessions | When you set a value, the alerting system notifies you when the number of concurrent sessions is 90 percent or higher than this value. If you don't set a value, alerts aren't generated. However, the monitoring system still reports the number of concurrent sessions every 24 hours. | Null | Null1 to 100,000 |  |
| No | **Failover response codes** | FailoverResponseCodes | Specifying a failover response code forces Direct Routing to attempt connection with another SBC (if another one exists in the user's voice routing policy) upon receiving any of the specified response codes from the SBC on an SBC-terminated initial INVITE request. A retry only occurs in the absence of prior non-100 provisional responses. For more information, see [Failover of specific SIP codes received from the Session Border Controller (SBC)](direct-routing-trunk-failover-on-outbound-call). | 408, 503, 504 |  | Int |
| No | **Failover times (seconds)** | FailoverTimeSeconds | When you set a value, outbound calls that aren't answered by the gateway within the time that you set are routed to the next available trunk. If there are no additional trunks, the call is automatically dropped. The default value is 10 seconds. In an organization with slow networks and gateway responses, this could potentially result in calls being dropped unnecessarily. | 10 | Number | Int |
| No | **SBC supports PIDF/LO for emergency calls** | PidfloSupported | Specify whether the SBC supports Presence Information Data Format Location Object (PIDF/LO) for emergency calls. |  |  |  |

For information about Location-Based Routing and media optimization settings, see [Plan for Location-Based Routing](location-based-routing-plan) and [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass).