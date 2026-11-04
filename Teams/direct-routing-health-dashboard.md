---
layout: Conceptual
title: Health dashboard for Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-health-dashboard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: mshaikh
ms.date: 2026-04-29T00:00:00.0000000Z
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.topic: article
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
description: Learn how to use health dashboard to monitor the connection between your Session Border Controller (SBC) and Direct Routing.
locale: en-us
document_id: edf8b00d-17dc-7655-abc6-34ef14f00ecc
document_version_independent_id: 08606d75-3213-6a5c-ebc4-6b902bff86df
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-health-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-health-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-health-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 12e7bb03-219e-8852-b3f5-14b527849418
---

# Health dashboard for Direct Routing - Microsoft Teams | Microsoft Learn

The health dashboard for Direct Routing lets you monitor the connection between your Session Border Controller (SBC) and the Direct Routing interface.

You can monitor the overall health of connected SBCs and view detailed information for a given SBC. This information can help you identify issues, such as the reason for dropped calls. For example, the SBC might stop sending calls if a certificate on the SBC expired or if there are network issues.

## View the health dashboard for Direct Routing

To view the dashboard, in the left navigation of the Teams admin center, go to **Voice** &gt; **Direct Routing**.

## Overall health

The dashboard provides the following information related to the overall health of connected SBCs.

[![Screenshot of the dashboard on the Direct Routing page in the Teams admin center.](media/direct-routing-dashboard.png)](media/direct-routing-dashboard.png#lightbox)

### Direct Routing summary

The Direct Routing summary shows the total number of SBCs, voice routes in the system, and SBCs with issues in the system.

- **Total SBCs**: The total number of SBCs enrolled in the system, where enrolled means that the tenant administrator added an SBC by using the [New-CsOnlinePSTNGateway](/en-us/powershell/module/microsoftteams/new-csonlinepstngateway) command.
- **Voice routes**: The total number of voice routes configured in the system.
- **SBCs with issues**: The total number of SBCs with current issues. Issues can include low network effectiveness, certificate expiration, inactivity, no SIP options, and capacity constraints. If an SBC was added by using PowerShell, but never connected, the dashboard shows its status as unhealthy with issues.

### The SBCs tab

The **SBCs** tab in the table shows the following information about your SBCs.

- **SBC**: The FQDN of the paired SBC.
- **Network effectiveness**: The network effectiveness ratio measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.

    It measures the ability of networks to deliver calls to the far-end terminal, excluding user actions resulting in call rejections. If the recipient rejected a call or sent the call to voicemail, the call is counted as a successful delivery. This means that an answer message, a busy signal, or a ring with no answer are all considered successful calls.

    For example, assume Direct Routing sent a call to the SBC and the SBC returns SIP code "504 Server Time-out - The server attempted to access another server in attempting to process the request and didn't receive a prompt response". This response indicates an issue on the SBC side and decreases the network effectiveness ratio in the dashboard for this SBC.

    Because the action you take might depend on the number of calls affected, the dashboard shows how many calls were analyzed to calculate a parameter. If the number of calls is less than 100, the network effectiveness ratio might be low, but still be normal.

    The formula used to calculate the network effectiveness ratio is:

    Network effectiveness ratio = 100 x (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures)/Total Calls.
- **Average call duration**: Average call duration is an indicator of the quality of end user experience. A decrease of the average call duration value often indicates problems with calling experience (noise, glitches, delays, and mid-call and other failures). If users experience issues with voice, they can redial the numbers several times or, after a short call, switch to a mobile device.

    We recommend establishing a baseline for the average call duration for your company. If this parameter goes significantly below the baseline, it might indicate that your users are having issues with call quality or reliability and are hanging up earlier than usual. If you start seeing extremely low average call duration, for example 15 seconds, callers might be hanging up because your service isn't performing reliably.

    Because the action you take might depend on the number of calls affected, the dashboard shows how many calls were analyzed to calculate a parameter.
- **TLS connectivity status**: Transport Layer Security (TLS) connectivity shows the status of the TLS connections between Direct Routing and the SBC. The dashboard also analyzes the certificate expiration date and warns if a certificate is set to expire within 30 days so that admins can renew the certificate before service is disrupted.

    Select the Warning message for a detailed issue description and recommendations for how to fix the issue.
- **SIP options status**: By default, the SBC sends options messages every minute. This configuration can vary for different SBC vendors. Direct Routing warns if the SIP options aren't sent or aren't configured.

    For more information about SIP options monitoring, and conditions when an SBC can be marked as not functional, see [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot).

    In addition to showing that there's an issue with SIP options flow, the dashboard also provides detailed descriptions of the errors. Select the "Warning" message to view the details. Possible values for SIP options status messages are as follows:

    - Active: The SBC is active. Microsoft Direct Routing service sees the options flowing on a regular interval.
    - Warning, no SIP options: The SBC exists in the database (your admin created it using the [New-CsOnlinePSTNGateway](/en-us/powershell/module/microsoftteams/new-csonlinepstngateway) command). It's configured to send SIP options, but the Direct Routing service never saw the SIP options coming back from this SBC.
    - Warning, SIP Messages aren't configured: Trunk monitoring using SIP options isn’t turned on. Microsoft Calling System uses SIP options and Transport Layer Security (TLS) handshake monitoring to detect the health of the connected SBCs at the application level. You’ll have issues if this trunk can be reached at the network level (by ping), but the certificate has expired or the SIP stack doesn’t work. To help identify such problems early, we recommend enabling sending SIP options. Check your SBC manufacturer documentation for more information about how to configure sending SIP options.
- **Concurrent calls capacity**: You can specify the limit of concurrent calls that an SBC can handle by using the [New-CsOnlinePSTNGateway](/en-us/powershell/module/microsoftteams/new-csonlinepstngateway) or [Set-CsOnlinePSTNGateway](/en-us/powershell/module/microsoftteams/set-csonlinepstngateway) command with the `-MaxConcurrentSessions` parameter.

    This parameter calculates how many calls were sent or received by Direct Routing using a specific SBC and compares it with the limit set. If the SBC also handles calls to different PBXs, this number won't show the actual concurrent calls.

## Detailed information for each SBC

You can also view detailed information for a specific SBC, as shown in the following screenshot.

[![Screenshot showing detailed information for a specific SBC.](media/direct-routing-dashboard-sbc-detail.png)](media/direct-routing-dashboard-sbc-detail.png#lightbox)

The detailed view shows the following additional parameters:

- **TLS connectivity status**: The same metric as on the Overall health dashboard.
- **TLS connectivity last status**: Shows the time when the SBC made a TLS connection to the Direct Routing service.
- **SIP options status**: The same metric as on the Overall health dashboard.
- **SIP options last checked**: Time when the SIP options were received last time.
- **SBC status**: Overall status of the SBC, based on all monitored parameters.

    - **Active**: The SBC is healthy and taking traffic.
    - **Inactive**: The SBC has no recent calls or health checks.
- **Concurrent calls**: Shows how many concurrent calls the SBC handled. This information is useful to predict the number of concurrent channels you need and see the trend. You can slide the data by number of days and call direction (inbound, outbound, or all streams).
- **Network parameters**: All network parameters are measured from the Direct Routing interface to the Session Border Controller. For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network), and look at the Customer Edge to Microsoft Edge recommended values.

    - **Jitter**: The millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).
    - **Packet Loss**: A measure of packets that failed to arrive. It's computed between two endpoints.
    - **Latency** (also known as round trip time): The length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received. This time delay consists of the propagation times between the two points of a signal.

    You can slide the data by number of days and call direction (inbound, outbound, or all streams).
- **Network effectiveness**: The same parameter that appears on the Overall health dashboard, but with the option to slice the data by time series or call direction.
- **Average call duration**: The average call duration by time series and call direction (inbound, outbound, or all streams).