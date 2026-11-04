---
layout: Conceptual
title: Prepare your organization's network for Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/prepare-network
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: snchatur
ms.date: 2026-05-26T00:00:00.0000000Z
audience: admin
description: Learn about preparing your organization's network for Microsoft Teams, including network requirements, network optimization, and bandwidth requirements.
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar2020
locale: en-us
document_id: 1d996cf7-9f48-2b30-7759-afaf3fe82caa
document_version_independent_id: 24dd6cdf-d35f-53b2-06c2-0a27891825d4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/prepare-network.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: prepare-network
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/prepare-network.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/6ab06385-661e-4214-8870-bbe4071c960d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/131ba09e-4280-4ae7-8622-1f9f1c0daad1
platformId: 69a76b9d-2c57-bd1d-d55f-c6e0ae6b09e5
---

# Prepare your organization's network for Teams - Microsoft Teams | Microsoft Learn

## Network requirements

If you have already [optimized your network for Microsoft 365 or Office 365](/en-us/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams. In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:

1. Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)? In addition to normal web traffic, make sure you open the TCP ports and IP addresses listed for Teams in [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges#microsoft-teams).

    Important

    If you need to federate with Skype for Business (on-premises), you need to configure an additional DNS record.

    | DNS record | Service | Protocol | Priority | Weight | Port | Target |
    | --- | --- | --- | --- | --- | --- | --- |
    | SRV | sipfederationtls | TCP | 100 | 1 | 5061 | sipfed.online.lync.com |
2. Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?

    - If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/en-us/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/en-us/microsoft-365/admin/setup/domains-faq).
3. Has your organization deployed Exchange Online and SharePoint Online?

    - If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact).
    - If your organization doesn't have SharePoint Online, see [Overview of Teams and SharePoint integration](sharepoint-onedrive-interact).

Once you verify that you meet these network requirements, you might be ready to [Roll out Teams](deploy-overview). If you're a large multinational enterprise, or if you know you have some network limitations, read on to learn how to assess and optimize your network for Teams.

Important

**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/en-us/schooldatasync/) before you roll out Teams.

**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Microsoft Entra Connect](/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.

### Best practice: Monitor your network by using CQD and Teams admin center

The [Best practice configurations dashboard](/en-us/microsoftteams/best-practice-dashboard) for Microsoft Teams meetings helps you manage and monitor your environment for seamless collaboration. This dashboard provides you with best practice configurations, the effect of your current settings, and actions you can take to follow Microsoft’s recommendations. The dashboard highlights locations that don’t follow Microsoft's recommended best practices.

Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard) to gain insight into the quality of calls and meetings in Teams. CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience. CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation. Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.

You can use the [Teams admin center](monitor-troubleshoot-teams-meetings-calls) to investigate call and meeting problems for an individual user. You can also use the [Best practice configurations dashboard](best-practice-dashboard) to monitor the state of network configurations across your organization.

## Network optimization

The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you already rolled out Microsoft 365 or Office 365. Use this guidance to optimize your network and Teams performance or if you know you have some network limitations.

You might want to do other network optimization if:

- Teams runs slowly (maybe you have insufficient bandwidth).
- Calls keep dropping (might be due to firewall or proxy blockers).
- Calls have static and cut out, or voices sound like robots (could be jitter or packet loss).

For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, see [Microsoft 365 and Office 365 Network Connectivity Principles](/en-us/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).

| Network optimization task | Details |
| --- | --- |
| Network planner | For help with assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the [Network Planner](/en-us/microsoftteams/network-planner) tool, in the [Teams admin center](https://admin.teams.microsoft.com). When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.<br><br>For an example scenario, see [Using Network Planner - example scenario](/en-us/microsoftteams/tutorial-network-planner-example). |
| Advisor for Teams | [Advisor for Teams](/en-us/microsoftteams/use-advisor-teams-roll-out) is part of the [Teams admin center](https://admin.teams.microsoft.com). It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you might need to update or modify before you can successfully roll out Teams. |
| External Name Resolution | Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls aren't preventing access. For information about configuring firewall ports, go to [Microsoft 365 and Office 365 URLs and IP ranges](/en-us/microsoftteams/office-365-urls-ip-address-ranges). |
| Maintain session persistence | Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP. |
| Validate NAT pool size | Validate the network address translation (NAT) pool size required for user connectivity. When multiple users and devices access Microsoft 365 or Office 365 using [Network Address Translation (NAT) or Port Address Translation (PAT)](/en-us/office365/enterprise/nat-support-with-office-365), you need to ensure that the devices hidden behind each publicly routable IP address don't exceed the supported number. Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion. Port exhaustion contributes to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service. |
| Routing to Microsoft data centers | [Implement the most efficient routing to Microsoft data centers](/en-us/office365/enterprise/client-connectivity). Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible. |
| Intrusion Detection and Prevention Guidance | If your environment has an [Intrusion Detection](/en-us/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools) or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs. |
| Configure split-tunnel VPN | We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as [split-tunnel VPN](/en-us/windows/security/identity-protection/vpn/vpn-routing). Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365. Bypassing your VPN has a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network. To implement a split-tunnel VPN, work with your VPN vendor.<br><br>Other reasons why we recommend bypassing the VPN: <br><br>- VPNs are typically not designed or configured to support real-time media.<br>- Some VPNs might also not support UDP (which is required for Teams).<br>- VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.<br>- Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.<br>- Traffic might be routed to a service front door location that is further away from the end user, introducing extra latency and jitter. |
| Implement QoS | [Use Quality of Service (QoS)](/en-us/microsoftteams/qos-in-teams) to configure packet prioritization. This improves call quality in Teams and help you monitor and troubleshoot call quality. QoS should be implemented on all segments of a managed network. Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events. With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality. |
| Optimize WiFi | Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media. Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment. Consider these factors:<br><br>- Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is prioritized appropriately over your WiFi networks.<br>- Plan and optimize the WiFi bands and access point placement. The 2.4-GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range. The 5-GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage. Endpoints also need to support that range and be configured to use those bands accordingly.<br>- If you're using dual-band WiFi networks, consider implementing band steering. *Band steering* is a technique implemented by WiFi vendors to influence dual-band clients to use the 5-GHz range.<br>- When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user. Ensure that access points that are next to each other are on channels that don't overlap.<br><br><br>Each wireless vendor has its own recommendations for deploying its wireless solution. Consult your WiFi vendor for specific guidance. |
| Allow WebSocket protocol | Teams uses long-living bidirectional WebSocket connections to efficiently deliver chat updates, call notifications and signaling, presence status changes, and other real-time notifications from cloud services to the client. If establishing WebSocket connections isn't possible, a traditional HTTP long-polling transport is used as a fallback, resulting in increased bandwidth and latency. We recommend that you enable WebSocket traffic for optimal operation. |

## Bandwidth requirements

Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions. That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.

Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30 fps (frames per second) for video and content.

This table describes how Teams uses bandwidth. Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5 Mbps. The actual bandwidth consumption in each audio/video call or meeting varies based on several factors, such as video layout, video resolution, and video frames per second. When more bandwidth is available, quality and usage increases to deliver the best experience.

**Modality**

**Bandwidth requirements (bitrate kilobit/s up/down)**

**Minimum**

**Recommended**

**Best performance**

**Audio**

One-to-one

10/10

58/58

76/76

Meetings

10/10

58/58

76/76

**Video**

One-to-one

150/150

1,500/1,500

4,000/4,000

Meetings

150/200

2,500/4,000

4,000/4,000

**Screen sharing**

One-to-one

200/200

1,500/1,500

4,000/4,000

Meetings

250/250

2,500/2,500

4,000/4,000

**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage. Typically, there's one endpoint per user, such as a computer or mobile device. However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.

- **Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875fps to 7.5fps, and Large Gallery video up to 540p resolution.
- **Recommended** Bandwidth requirements for video calls are up to 1080p resolution^\*^, screen sharing content frame rates adaptive 7.5fps to 30fps, and Large Gallery video up to 1080p resolution^\*^.
- **Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15fps to 30fps.

^\*^Expect up to 1080p quality but depending on your network conditions, video resolution, and quality will be optimized accordingly.

**Teams events bandwidth considerations**

When hosting a Teams event [optimized for a large audience](plan-events) with live streaming, it’s important to plan for sufficient network bandwidth at each viewing location. Without an Enterprise Content Delivery Network (eCDN), bandwidth requirements can be approximated at 2 Mbps per viewer at each location. (Update to 3 Mbps for 1080p).

For physical locations with a large number of attendees or dense network environments, we recommend implementing an eCDN solution to optimize bandwidth usage and ensure a smooth streaming experience. For more information, see [Plan for Teams events](plan-events).