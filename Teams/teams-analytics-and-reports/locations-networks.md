---
layout: Conceptual
title: Locations and Networks report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/locations-networks
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: describes the locations and networks report for Microsoft Teams
author: nomorephones
ms.author: pavellatif
manager: roykuntz
ms.service: msteams
ms.topic: article
ms.date: 2026-09-23T00:00:00.0000000Z
ms.subservice: teams-calling
locale: en-us
document_id: fd495d7d-850d-6839-0b02-d3ab39c3dcdd
document_version_independent_id: fd495d7d-850d-6839-0b02-d3ab39c3dcdd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/locations-networks.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/locations-networks
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/locations-networks.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5cf64e1f-c986-3e56-a79b-4f4c8efc3bec
---

# Locations and Networks report - Microsoft Teams | Microsoft Learn

Applies to: Microsoft Teams

The Teams Locations and Networks usage report in the Microsoft Teams admin center gives you insight into client requests for location information from the Network Configuration Service (NCS). This information can help you understand whether network topology as delivered by Teams clients matches the locations you configured in the service.

The report supports both IPv4 and IPv6 clients. IPv6 subnet matching in the Location Information Service (LIS) depends on the client-reported prefix length. For requirements and supported alternatives, see [IPv6 subnet matching](../configure-dynamic-emergency-calling#ipv6-subnet-matching).

The **Network Site** tab shows the requests coming from clients for matching subnet information to network sites that deliver emergency calling policies and network sites.

The **Network Identifier** tab shows the requests coming from clients for matching Wi-Fi access point, subnet, switch, or port information with emergency addresses.

The **Trusted IP address** tab shows the requests coming from clients for matching their external IP address with a trusted IP address record to determine whether the end-user was on the company premises or working remotely.

## View the Locations and Networks report

1. In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **Networks and Locations.**
2. Under **Date range**, select a predefined range of 7 or 28 days and then select **Run report**.

## Interpret the report

### Network Site

The table breaks down the match and no match event groupings for Network Site acquisition. The report includes the following information:

| Column Name | Description |
| --- | --- |
| Reason | Whether the grouping represents a match or no match. |
| Count | The number of events for this grouping. |
| IP Version | Whether the Subnet ID is IPv4 or IPv6. |
| Subnet ID | Subnet ID of the matching records. |
| Mask Bits | Number of subnet mask bits. |
| Network Site ID | The Network Site ID record containing the matched subnet. |
| Teams ECRP | The Teams Emergency Call Routing Policy associated with the Network Site. |
| Teams ECP | The Teams Emergency Calling Policy associated with the Network Site. |

### Network identifier

The table breaks down the match and no match event groupings for location acquisition. The report includes the following information:

| Column Name | Description |
| --- | --- |
| Reason | Whether the grouping represents a match or no match. |
| Count | The number of events for this grouping. |
| IP | IP address of records for this grouping. |
| IP version | Whether the IP address is IPv4 or IPv6. |
| Chassis ID | Ethernet switch chassis ID for LLDP matching. |
| BSSID | Wireless access point’s BSSID. |
| Port ID | Ethernet switch port ID for LLDP matching. |
| Matched Network Type | Refers to the network type that was used for matching.<br>- CLS – Commercial Location Services. Client-acquired latitude and longitude used for determining location.<br>- BSSID – Wireless access point BSSID.<br>- Port – Ethernet port.<br>- ChassisID – Ethernet switch chassis.<br>- Subnet – Network subnet range. |
| Matching Identity | Matched network device detail. |
| Location ID | Specific location acquired from matched network device. |

### Trusted IP address

The table breaks down the public IP addresses that clients use to access Microsoft Teams services and match with a trusted IP address. The report includes the following information:

| Column Name | Description |
| --- | --- |
| Reason | Whether the grouping represents a match or no match. |
| Count | The number of events for this grouping. |
| IP Version | Whether the public IP is IPv4 or IPv6. |
| Public IP | Public IP address of records for this grouping. |
| Trusted IP Address | For matching records, the trusted IP address. |
| Mask Bits | Number of mask bits for the trusted IP address. |

### Network-site match without an emergency-location match

A **Match** in the **Network Site** tab doesn't necessarily mean that the client obtained an emergency address. Network-site matching determines the applicable site and policies. Network-identifier matching determines the location associated with a network identifier.

For IPv6 subnet matching, a client reporting `/128` can match a network site configured with `/64` while failing to match the corresponding LIS subnet. In this case, network-site matching applies the configured `/64` prefix, whereas LIS calculates the network ID using the client-reported `/128` prefix. This difference can occur with IPv6 addresses assigned through stateful DHCPv6 on Windows, even when the LIS subnet and associated emergency location are configured correctly.

To investigate the prefix-length mismatch, use client diagnostic logs. In `siteMatchInfo`, `subnetLengthIPv6` is the client-reported prefix length, while `maskBits` is the configured network-site subnet prefix length. A successful network-site match alone doesn't establish that the client reported the prefix length needed for LIS subnet matching.

Review the **Network Identifier** tab, including the **Reason**, **Matched Network Type**, and **Location ID** columns, to see whether a network identifier matched and which location ID was associated with the match.

For configuration requirements and supported alternatives for dual-stack and IPv6-only endpoints, see [IPv6 subnet matching](../configure-dynamic-emergency-calling#ipv6-subnet-matching). After configuring a matching identifier, follow the guidance in [Test emergency calling](../configure-dynamic-emergency-calling#test-emergency-calling).

### Related articles

[Network settings for cloud voice features](/en-us/microsoftteams/cloud-voice-network-settings)

[Manage emergency locations](/en-us/microsoftteams/add-change-remove-emergency-location-organization)

[Configure dynamic emergency calling](/en-us/microsoftteams/configure-dynamic-emergency-calling)

[Emergency addresses for remote locations](../emergency-calling-dispatchable-location)