---
layout: Conceptual
title: Dimensions and measurements - Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/dimensions-and-measures-available-in-call-quality-dashboard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: jamp
ms.date: 2026-07-01T00:00:00.0000000Z
ms.topic: article
ms.assetid: e97aeeee-9e43-416f-b433-9cdd63d8874b
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
- ContentFreshnessFY24
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- seo-marvel-mar2020
description: Get detailed information about the dimensions and measurements used by the Call Quality Dashboard (CQD) for Microsoft Teams.
locale: en-us
document_id: 1a455280-ea8e-2ddf-2965-60d9dcc0e21d
document_version_independent_id: 7fb320d3-fa69-23fa-113c-53e9d2e11ada
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/dimensions-and-measures-available-in-call-quality-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: dimensions-and-measures-available-in-call-quality-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/dimensions-and-measures-available-in-call-quality-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
platformId: 9f54d2f7-d317-9ae5-9445-80da94a6e338
---

# Dimensions and measurements - Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn

The Call Quality Dashboard (CQD) for Microsoft Teams allows you to understand the quality of calls made with these services. This article describes the dimensions and measurements visible through CQD. To learn more about CQD, see [Use CQD to manage call and meeting quality in Microsoft Teams](quality-of-experience-review-guide).

## Real-time media versus streaming

Microsoft Teams supports both real-time media streams (RTP) and streaming media over HTTPS (streaming) depending on the type of meeting occurring, and CQD supports displaying information about both these types of streams when present. These two media types use different underlying technology, provide different metrics, have different allowances and limitations on what telemetry is available from attendees. The methodology for troubleshooting and analyzing streaming differs from RTP. To learn more about network best practices for streaming and Teams events, see [Plan for Teams events](plan-events).

## First and Second endpoint classification

Many of the dimensions and measurements in CQD are labeled as first or second. The following logic determines which endpoint involved in the stream or call is labeled as first:

- A server endpoint (AV MCU, Mediation Server, and so on) is considered first when a server is involved in the stream or call.
- A client endpoint is considered second unless the stream is between two server endpoints.
- If both endpoints are the same type, first versus second is set based on internal ordering of the user agent category to ensure that the ordering is consistent.

In the following example, each row represents a pair of User Agents involved in a stream:

| User Agent Category of Caller | User Agent Category of Callee | First Endpoint | Second Endpoint | First Is Caller |
| --- | --- | --- | --- | --- |
| AV-MCU | OC (Skype for Business client) | AV-MCU | OC (Skype for Business client) | TRUE |
| OC (Skype for Business client) | AV-MCU | AV-MCU | OC (Skype for Business client) | FALSE |
| OC (Skype for Business client) | OC (Skype for Business client) | OC (Skype for Business client) | OC (Skype for Business client) | FALSE |
| AV-MCU | Mediation Server | Mediation Server | AV-MCU |  |
| Mediation Server | AV-MCU | Mediation Server | AV-MCU | TRUE |
| OC (Skype for Business client) | OC Phone (Skype for Business IP Phone) | OC (Skype for Business client) | OC Phone (Skype for Business IP Phone) | TRUE |
| OC Phone (Skype for Business IP Phone) | OC (Skype for Business client) | OC (Skype for Business client) | OC Phone (Skype for Business IP Phone) | FALSE |

Note

That first and second classification is separate from which endpoint is the caller or callee. The First Is Caller dimension can be used to help identify which endpoint is the caller or callee.

## Dimensions

Dimensions information is based in part on data uploaded to the CQD portal. Many Dimension values can also be used as filters.

### Dimension data types and units

#### Boolean

Boolean values are always either True or False. In some cases, True can be represented as 1, and False can be represented as 0.

#### Range

Dimensions that are provided as range or group of values are shown using the following format:

*&lt;sort order string&gt; [&lt;lower bound inclusive&gt; - &lt;upper bound exclusive&gt;*

For example, the Duration (Minutes) dimension represents the call duration in seconds with the value reported as a range of values.

| Duration (Minutes) | How to interpret |
| --- | --- |
| 062: [0 - 0) | Stream duration = 0 minutes |
| 064: [1 - 2) | 1 minute &lt; = stream duration &lt; 2 minutes |
| 065: [2 - 3) | 2 minutes &lt; = stream duration &lt; 3 minutes |
| 066: [3–4) | 3 minutes &lt; = stream duration &lt; 4 minutes |

The &lt;sort order string&gt; is used to control the sort order when presenting the data and can be used for filtering. For example, a filter on Duration (Minutes) &lt; "065" would show streams with duration less than 2 minutes. The leading '0' is needed for the filter to work as expected. The actual value of the sort order string isn't significant.

Note

You might notice ranges that seem to be invalid for a given dimension. An example is Wifi Signal Strength showing calls in the 082: [100 - 110) range when 100 is the maximum possible value. This range is due to how numbers are assigned to ranges in CQD's data model. If a whole number value is 99, it's counted in the 081: [90 - 100) range. If that value is 100, it's counted in the 082: [100 - 110) range. This doesn't indicate that there are Wifi Signal Strength values greater than 100% being reported.

#### Enumeration strings

Strings used by CQD are often derived from data files, and these strings can be any combination of character within the allowed length. Some dimensions look like strings, but since they can only be one of a short list of predefined values, they're enumerations and not true strings. Some enumerations strings are also used in pairs.

#### Enumeration pair

Dimensions that are provided as an enumeration pair are shown using the following format:

*&lt;enumeration value from one end point&gt; : &lt;enumeration value from the other endpoint&gt;*

The ordering of the enumeration values is consistent but doesn't reflect ordering of the first or second endpoints.

For example, the Network Connection Detail Pair shows the Network Connection Detail values for the two endpoints:

| Network Connection Detail Pair | How to interpret |
| --- | --- |
| Wired : Wired | First and second endpoints both used wired ethernet connections. |
| Wired : wifi | One endpoint used a wired ethernet connection and the other endpoint used a Wi-Fi connection. |
| : wifi | One endpoint used a WiFi connection and the network connection used by the other endpoint is unknown. |

#### Blank values

The table below describes why a dimension might be blank. Many dimensions and measurements are blank if the QoE Record Available dimension is false. Missing QoE typically occurs when the call isn't successfully established, or when the client fails to send its telemetry to the service.

### Available dimensions

The following table lists the dimensions currently available in CQD, in the order listed in the Query Editor used to create reports or edit previously defined reports.

| Name | Data type | Description | Possible Reasons for blank values |
| --- | --- | --- | --- |
| **Endpoint** |  |  |  |
| First CPU Name | String | Name of the CPU used by the first endpoint. **Example value:** Contoso CPU X11 @ 1.80 GHz | • The endpoint didn't report this data. |
| Second CPU Name | String | Name of the CPU used by the second endpoint. **Example value:** Contoso CPU X11 @ 1.80 GHz | • The endpoint didn't report this data. |
| First CPU Number Of Cores | Number of cores | Number of CPU cores available on the first endpoint. **Example value:** 8 | • The endpoint didn't report this data. |
| Second CPU Number Of Cores | Number of cores | Number of CPU cores available on the second endpoint. **Example value:** 8 | • The endpoint didn't report this data |
| First CPU Processor Speed | CPU speed in MHz | Speed in MHz of the CPU used by the first endpoint. **Example value:** 1800 | • The endpoint didn't report this data. |
| Second CPU Processor Speed | CPU speed in MHz | Speed in MHz of the CPU used by the second endpoint. **Example value:** 1800 | • The endpoint didn't report this data |
| First Endpoint | String | Machine name reported by the first endpoint if the endpoint is a server or a cloud service client. **Example value:** MACHINENAME | • The endpoint didn't report this data. |
| Second Endpoint | String | Machine name reported by the second endpoint if the endpoint is a server or a cloud service client. **Example value:** MACHINENAME | • The endpoint didn't report this data. |
| First OS | String | Full Operating System and architecture string reported by the first endpoint. **Example value:** Windows 10.0.14996 SP: 0.0 Type: 1(Workstation) Suite: 256 Arch: x64 WOW64: True | • The endpoint didn't report this data. |
| Second OS | String | Full Operating System and architecture string reported by the second endpoint. **Example value:** Windows 10.0.14996 SP: 0.0 Type: 1(Workstation) Suite: 256 Arch: x64 WOW64: True | • The endpoint didn't report this data |
| First OS Filtered | String | Operating System name and major and minor version reported by the first endpoint. This string can contain more than the OS name and version. **Example value:** Windows 10 | • The endpoint didn't report this information • The report from this endpoint wasn't received. |
| Second OS Filtered | String | Operating System name and major and minor version reported by the second endpoint. This string can contain more than the OS name and version. **Example value:** Windows 10 | • The endpoint didn't report this information • The report from this endpoint wasn't received. |
| First OS Architecture | String | Hardware architecture reported by the first endpoint. **Example value:** x64 | • The endpoint didn't report this information • The report from this endpoint wasn't received. • The format of the architecture wasn't recognized. |
| Second OS Architecture | String | Hardware architecture reported by the second endpoint. **Example value:** x64 | • The endpoint didn't report this information • The report from this endpoint wasn't received • The format of the architecture wasn't recognized. |
| First Virtualization Flag | Boolean **Possible values:** 0 = False  1 = True | Flag that indicates if the first endpoint is capable of supporting virtualization. To understand if virtualization was actually used, refer to the VDI dimensions. | • The endpoint didn't report this data |
| Second Virtualization Flag | Boolean **Possible values:** 0 = False  1 = True | Flag that indicates if the second endpoint is capable of supporting virtualization. To understand if virtualization was actually used, refer to the VDI dimensions. | • The endpoint didn't report this data |
| First VTC Device Name | String | The friendly name of the VTC device used by the first endpoint | • The endpoint didn't report this data • Field is EUII and 28 days has passed. |
| Second VTC Device Name | String | The friendly name of the VTC device used by the second endpoint | • The endpoint didn't report this data • Field is EUII and 28 days has passed. |
| First VTC Device Detail | String | The platform and version information of the VTC device used by the first endpoint **Example value:** Tandberg, 529 | • The endpoint didn't report this data. |
| Second VTC Device Detail | String | The platform and version information of the VTC device used by the second endpoint **Example value:** Tandberg, 529 | • The endpoint didn't report this data. |
| First Media Bypass | Boolean | Indicates if the audio stream was bypassing the Teams service endpoint and flowing directly between the session border controller and first endpoint. | • Stream wasn't destined for a PSTN endpoint.  • Stream wasn't an audio stream. |
| Second Media Bypass | Boolean | Indicates if the audio stream was bypassing the Teams service endpoint and flowing directly between the session border controller and second endpoint. | • Stream wasn't destined for a PSTN endpoint.  • Stream wasn't an audio stream. |
| First Endpoint Make | String | Device manufacturer, information is read from an Endpoint Data file EndpointMake field. | • No data file for the endpoint. |
| First Endpoint Model | String | Device model, information is read from an Endpoint Data file EndpointModel field. | • No data file for the endpoint |
| First Endpoint Type | String | Device type, information is read from an Endpoint Data file EndpointType field. | • No data file for the endpoint. |
| First Endpoint Label 1 | String | A customizable label, information is read from an Endpoint Data file. | • No data file for the endpoint. |
| First Endpoint Label 2 | String | A customizable label, information is read from an Endpoint Data file. | • No data file for the endpoint. |
| First Endpoint Label 3 | String | A customizable label, information is read from an Endpoint Data file. | • No data file for the endpoint. |
| Second Endpoint Make | String | Device manufacturer, information is read from an Endpoint Data file EndpointName field. | • No data file for the endpoint. |
| Second Endpoint Model | String | Device model, information is read from an Endpoint Data file EndpointModel field. | • No data file for the endpoint. |
| Second Endpoint Type | String | Device type, information is read from an Endpoint Data file EndpointType field. | • No data file for the endpoint. |
| Second Endpoint Label 1 | String | A customizable label, information is read from an Endpoint Data file. | • No data file for the endpoint. |
| Second Endpoint Label 2 | String | A customizable label, information is read from an Endpoint Data file. | • No data file for the endpoint. |
| Second Endpoint Label 3 | String | A customizable label, information is read from an Endpoint Data file. | • No data file for the endpoint. |
| First ASN | String | Autonomous system number for the first endpoint. **Example value:** 8069 | • Network data wasn't available to determine endpoint ASN. |
| Second ASN | String | Autonomous system number for the second endpoint. **Example value:** 8069 | • Network data wasn't available to determine endpoint ASN. |
| First ASN ISP Name | String | Name of the ASN holder—usually an internet service provider or ISP—for the autonomous system number of the first endpoint. **Example value** Microsoft Corporation | • Network data wasn't available to determine endpoint ASN. |
| Second ASN ISP Name | String | Name of the ASN holder—usually an internet service provider or ISP—for the autonomous system number of the second endpoint. **Example value:** Microsoft Corporation | • Network data wasn't available to determine endpoint ASN. |
| First ASN Country Code | String | Country code for the Autonomous System Number determined for the first endpoint. **Example value:** US | • Network data wasn't available to determine endpoint ASN |
| Second ASN Country Code | String | Country code for the Autonomous System Number determined for the second endpoint. **Example value:** US | • Network data wasn't available to determine endpoint ASN |
| First ASN Country | String | Country name for the Autonomous System Number determined for the first endpoint. **Example value:** United States | • Network data wasn't available to determine endpoint ASN |
| Second ASN Country | String | Country name for the Autonomous System Number determined for the second endpoint. **Example value:** United States | • Network data wasn't available to determine endpoint ASN |
| First ASN City | String | City name for the Autonomous System Number determined for the first endpoint. **Example value:** Redmond | • Network data wasn't available to determine endpoint ASN |
| Second ASN City | String | City name for the Autonomous System Number determined for the second endpoint. **Example value:** Redmond | • Network data wasn't available to determine endpoint ASN |
| First ASN State | String | State name for the Autonomous System Number determined for the first endpoint. **Example value:** WA | • Network data wasn't available to determine endpoint ASN |
| Second ASN State | String | State name for the Autonomous System Number determined for the second endpoint. **Example value:** WA | • Network data wasn't available to determine endpoint ASN |
| **Building** |  |  |  |
| First Network | String | Subnet used for media stream by the first endpoint if the subnet exists in subnet to tenant building data. **Example value:** 10.0.1.12.0 | • The endpoint didn't report network data • Network isn't defined in subnet-mapping data. |
| First Network Name | String | Name of network used for media stream by first endpoint. Based on mapping subnet to tenant building data. **Example value:** USA/WA/REDMOND | • The endpoint didn't report network data • Network isn't defined in subnet-mapping data |
| First Network Range | String | Network prefix/range of the subnet used for the media stream by the first endpoint, based on data-mapping subnet to tenant building. **Example value:** 24 | • The endpoint didn't report network data • Network isn't defined in subnet-mapping data |
| First Building Name | String | Name of the building where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** Main | • The endpoint didn't report network data • Network isn't defined in subnet-mapping data |
| First Ownership Type | String | Ownership type of the building where the first endpoint was located. Based on mapping subnet to tenant building data. **Example value:** Contoso-IT | • The endpoint didn't report network data • Network isn't within the corporate network or network ownership isn't defined in subnet-mapping data |
| First Building Type | String | Type of building where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** Open Office | • The endpoint didn't report network data • Network isn't within corporate network • Network building type isn't defined in subnet-mapping data |
| First Building Office Type | String | Type of building where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** Open Office | • The endpoint didn't report network data • Network isn't within corporate network • Network building type isn't defined in subnet-mapping data |
| First City | String | City where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** Redmond | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have a city defined in subnet-mapping data |
| First Zip Code | String | Zip/Postal code where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** 98052 | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have a zip code defined in subnet-mapping data |
| First Country | String | Country where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** USA | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have a country defined in subnet-mapping data |
| First State | String | State where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** WA | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have a State defined in subnet-mapping data. |
| First Region | String | Region where the first endpoint was located based on mapping subnet to tenant building data. **Example value:** North America | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have a region defined in subnet-mapping data. |
| First Express Route | Boolean | True if the subnet used for the media stream by the first endpoint is enabled for Azure ExpressRoute, based on mapping subnet to tenant building data. You can customize usage for other purposes if you decide to. | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have an ExpressRoute flag set in subnet-mapping data. |
| First Network Mapped VPN | Boolean | True if the subnet used for the media stream by the first endpoint is a VPN subnet, based on mapping subnet to tenant building data. | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have a VPN flag set in subnet-mapping data. |
| First Public IP | String | Public IP value used for media stream by the first endpoint if the Public IP exists in subnet to tenant building data. **Example value:** 203.0.113.1 | • The endpoint didn't report network data • Network isn't within corporate network |
| Second Network | String | Subnet used for media stream by second endpoint if subnet exists in subnet to tenant building data. **Example value:** 10.0.1.12.0 | • The endpoint didn't report network data • Network isn't defined in subnet-mapping data |
| Second Network Name | String | Name of the network used for the media stream by the second endpoint, based on mapping subnet to tenant building data. **Example value:** USA/ WA/ REDMOND | • The endpoint didn't report network data • Network doesn't have a network name defined in subnet-mapping data |
| Second Network Range | String | Network prefix/range of the subnet used for the media stream by the second endpoint, based on mapping subnet to tenant building data. **Example value:** 24 | • The endpoint didn't report network data • Network doesn't have a network range defined in subnet-mapping data |
| Second Building Name | String | Name of the building where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** Main | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have a building name defined in subnet-mapping data |
| Second Ownership Type | String | Ownership type of building where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** Contoso — IT | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have ownership defined in subnet-mapping data |
| Second Building Type | String | Type of building where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** Open Office | • The endpoint didn't report network data• Network isn't within corporate network • Network building type isn't defined in subnet-mapping data |
| Second Building Office Type | String | Office building type where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** Office | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have a building office type defined in subnet-mapping data. |
| Second City | String | City where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** Redmond | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have a city defined in subnet-mapping data |
| Second Zip Code | String | Zip/Postal code where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** 98052 | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have a zip code defined in subnet-mapping data. |
| Second Country | String | Country where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** USA | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have country defined in subnet-mapping data |
| Second State | String | State where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** WA | • The endpoint didn't report network data• Network isn't within corporate network • Network doesn't have a state defined in subnet-mapping data |
| Second Region | String | Region where the second endpoint is located based on mapping subnet to tenant building data. **Example value:** North America | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have region defined in subnet-mapping data. |
| Second Express Route | Boolean | True if the subnet used for the media stream by the second endpoint is enabled for ExpressRoute, based on mapping subnet to tenant building data. | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have an ExpressRoute flag set in subnet-mapping data. |
| Second Network Mapped VPN | Boolean | True if the subnet used for the media stream by the second endpoint is a VPN subnet, based on mapping subnet to tenant building data. | • The endpoint didn't report network data • Network isn't within corporate network • Network doesn't have a VPN flag set in subnet-mapping data. |
| Second Public IP | String | Public IP value used for media stream by the second endpoint if the Public IP exists in subnet to tenant building data. **Example value:** 203.0.113.1 | • The endpoint didn't report network data • Network isn't within corporate network |
| First Inside Corp | Enumeration **Possible values:** Inside, Outside | Indicates if the first endpoint is on a subnet within the corporate network, based on mapping subnet to tenant building data. By default, the endpoint is considered Outside. **Example value:** Inside |  |
| Second Inside Corp | Enumeration **Possible values:** Inside, Outside | Indicates if the second endpoint is on a subnet within the corporate network, based on mapping subnet to tenant building data. By default, the endpoint is considered Outside. **Example value:** Inside |  |
| **Deployment** |  |  |  |
| First Tenant Id | String | Tenant ID for the first endpoint. **Example value:** 00000000 — 0000 -0000 - 0000 — 000000000000 | • Tenant ID for the first endpoint couldn't be determined. A blank value here might indicate that the endpoint is signed in to an on-premises Skype for Business Server deployment. |
| Second Tenant Id | String | Tenant ID for the second endpoint. **Example value:** 00000000 — 0000 - 0000 - 0000 — 000000000000 | • Tenant ID for the second endpoint couldn't be determined. A blank value here might indicate that the endpoint is signed in to an on-premises Skype for Business Server deployment. |
| First Pool | String | Skype for Business Online pool FQDN assigned to the first endpoint. **Example value:** pool1.lync.com | • Indicates that the endpoint is signed in to a Microsoft Teams or Skype for Business. This field only populates for streams using on-premises Skype for Business Server deployments. |
| Second Pool | String | Skype for Business Online pool FQDN assigned to the second endpoint. **Example value:**pool1.lync.com | • Skype for Business Online pool couldn't be determined for the second endpoint. A blank value here might indicate that the endpoint is signed in to an on-premises Skype for Business Server deployment. |
| Is Federated | Boolean | True if streams are between two federated tenants, False otherwise. | • It couldn't be determined if the stream is federated • Some signaling data isn't collected |
| Region | String | Region where the deployment is located based on the home region of the tenant. **Example value:** North America | • Network data not reported • Network isn't within corporate network • Network doesn't have region defined in subnet-mapping data. |
| First HW Decoder Blocked | String | Values indicate if a hardware media encoding driver is blocked on the first endpoint, which may impact media quality. **Example value:** SW\_DriverBlacklisted | • First endpoint is not affected by blocked drivers or did not report any information. |
| Second HW Decoder Blocked | String | Values indicate if a hardware media encoding driver is blocked on the second endpoint, which may impact media quality. **Example value:** SW\_DriverBlacklisted | • Second endpoint is not affected by blocked drivers or did not report any information. |
| First HW Encoder Blocked | String | Values indicate if a hardware media encoding driver is blocked on the first endpoint, which may impact media quality. **Example value:** SW\_DriverBlacklisted | • First endpoint is not affected by blocked drivers or did not report any information. |
| Second HW Encoder Blocked | String | Values indicate if a hardware media encoding driver is blocked on the second endpoint, which may impact media quality. **Example value:** SW\_DriverBlacklisted | • Second endpoint is not affected by blocked drivers or did not report any information. |
| **Stream** |  |  |  |
| QoE Record Available | Boolean | True if at least one Quality of Experience report is available for call/session. Many dimensions and measurements are available only if a QoE record is available. If the call setup fails, a QoE record isn't available. |  |
| CDR Record Available | Boolean | True if at least one Call Detail Records is available for call/session. |  |
| Media Line Label | Integer | Label in SDP for media line. Use Media Type to determine if label is used for video, audio, app sharing, A/V stream, or video based screen sharing. **Example value:** 0 | • The endpoint didn't report this data. |
| Media Type | String | Type of media (video, audio, app sharing, A/V stream, or video based screen sharing). A value of "AV Stream" indicates the user is a view-only streaming attendee. **Example value:** Audio |  |
| Media Line Label Text | String | The Session Description Protocol (SDP) Label Attribute of the media line corresponding to the stream. See [RFC 4574](https://tools.ietf.org/html/rfc4574) for more detailed info. **Example values**:  main-audio main-video main-video1 main-video2 main-video3 main-video4 main-video5 main-video6 main-video7 main-video8 main-video9 panoramic-video applicationsharing-video data |  |
| First Is Server | Enumeration **Possible values:**• Client • Server | Indicates if the first endpoint is a server endpoint, or a client endpoint. Types of servers include conferencing servers and mediation servers. |  |
| Second Is Server | Enumeration **Possible values:**• Client • Server | Indicates if the second endpoint is a server endpoint, or a client endpoint. Types of servers include conferencing servers and mediation servers. |  |
| First Is Caller | Boolean | True if the first endpoint is the caller who initiated the session. |  |
| First Network Connection Detail | Enumeration **Possible values:**• Wired • WiFi • MobileBB • Tunnel • Other | Type of network used by the first endpoint. **Example value:** Wired | • The endpoint didn't report data |
| Second Network Connection Detail | Enumeration **Possible values:**• Wired • WiFi • MobileBB • Tunnel • Other | Type of network used by the second endpoint. **Example value:** Wired | • The endpoint didn't report data |
| Stream Direction | Enumeration **Possible values:**• First-to-Second • Second-to-First | Indicates the direction of a stream. • **Example value:** First-to-Second | • No data was reported to indicate the direction of the stream |
| Payload Description | String | Name of last codec used in the stream. **Example value:** SILKWide | • No data is available |
| Audio and Video Call | Boolean | True if call had both audio and video streams, False otherwise | • No data was reported to indicate the media types of the stream. |
| First QoE Record Available | Boolean | True if the QoE Record for the first endpoint is reported to CQD. |  |
| Second QoE Record Available | Boolean | True if the QoE Record for the first endpoint is reported to CQD. |  |
| Duration 5 seconds or less | Boolean | True if stream had duration of 5 seconds or less, False otherwise. |  |
| Duration 60 seconds or more | Boolean | True if stream had duration of 60 seconds of more, False otherwise. |  |
| Is Teams | Boolean | True indicates that the first or second user agent for the stream is a Microsoft Teams endpoint.  False indicates that the user agents are Skype for Business endpoints. |  |
| Duration (Minutes) | Range (minutes) | Duration of stream in minutes. Values grouped by range. **Example value:** 065: [3–4) |  |
| Duration (Seconds) | Range (seconds) | Duration of stream in seconds. Values grouped by range. **Example value:** 062: [1 -2) |  |
| **Date** |  |  |  |
| End Time | String | Time of day the call ended. Values are reported in the UTC time zone. | • Call setup failed or wasn't established (see CDR Response Reason) |
| Year | Integer | Year of the end of the stream. Values are reported in the UTC time zone. **Example value:** 2018 |  |
| Month | Integer | Month of the end of the stream. Values are reported in the UTC time zone. **Example value:** 2 |  |
| Day | Integer | Day of the end of the stream. Values are reported in the UTC time zone. **Example value:** 1 |  |
| Date | String | Date the stream ended. Values are reported in the UTC time zone. **Example value:** 2018-06-01 |  |
| Hour | Integer | Hour of the end of the stream. Values are reported in the UTC time zone. **Example value:** 1 |  |
| Minute | Integer | Minute of the end of the stream. Values are reported in the UTC time zone. **Example value:** 30 |  |
| Second | Integer | Second of the end of the stream. Values are reported in the UTC time zone. **Example value:** 12 |  |
| Day Of Year | Integer | Day of year of the end of the stream. Values are reported in the UTC time zone. **Example value:** 32 |  |
| Day Of Week | String | Day of week of the end of the stream. Values are reported in the UTC time zone. **Example value:** Wednesday |  |
| Day Number Of Week | Integer | Day number of week of the end of the stream. Values are reported in the UTC time zone. **Example value:** 3 |  |
| Week | String | Starting date of the week in which the call took place. **Example value:** 2019-09-01 | • Call setup failed or wasn't established (see CDR Response Reason) |
| Month Year | String | Month and year of the end of the stream. Values are reported in the UTC time zone. **Example value:** 2017-02 |  |
| Full Month | Date time | Full Month of the end of the stream. Values are reported in the UTC time zone. **Example value:** 2017-02-01T00:00:00 |  |
| Start time | String | Calculated time of day the media stream started based on the stream duration and session end time. Values are reported in the UTC time zone. | • Call setup failed or wasn't established (see CDR Response Reason) |
| **UserAgent** |  |  |  |
| First Domain | String | Domain of the first endpoint's user. If the first endpoint is a conference server, it uses the domain of the organizer of the meeting. Might also be the domain of service accounts used in scenario. **Example value:** contoso.com |  |
| Second Domain | String | Domain of the second endpoint's user. If the second endpoint is a conference server, it uses the domain of the organizer of the meeting. Might also be the domain of service accounts used in scenario. **Example value:** contoso.com |  |
| First User Agent Category | String | Category of the user agent of the first endpoint. **Example value:** OC | • A user agent doesn't currently have a mapping |
| Second User Agent Category | String | Category of the user agent of the second endpoint. **Example value:** OC | • A user agent doesn't currently have a mapping |
| First User Agent | String | User agent string of the first endpoint. **Example value:** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business) | • No user agent reported by first endpoint |
| Second User Agent | String | User agent string of the second endpoint. **Example value:** UCCAPI/16.0.7766.5281 OC/16.0.7766.2047 (Skype for Business) | • No user agent was reported by second endpoint |
| Conference Type | Enumeration **Possible values:**• conf:applicationsharing • conf:audio-video • conf:focus | Type of conference URI. **Example value:** conf:audio-video | • Non-conference scenario. |
| Conference ID | String | Unique identifier for a call or meeting occurrence, also known as Call Id. All calls have a Conference ID regardless of whether they're a person-to-person (P2P) call or a conference call. This dimension might have too many rows to be used as dimension in a report. It can be used a filter instead. **Example value:** 5a962ccf-b9cb-436a-a433-f28bf5404ad8 |  |
| First Client App Version | String | Version of the application used for the first endpoint. Data is parsed from the user agent string. **Example value:** 16.0.7766.2047 | • The version string couldn't be parsed • The value wasn't reported. |
| Second Client App Version | String | Version of the application used for the second endpoint. Data is parsed from the user agent string. **Example value:** 16.0.7766.2047 | • The version string couldn't be parsed • The value wasn't reported. |
| Meeting Id | String | The numeric identifier for the meeting, generated when the meeting is created. This value can be found in Teams meeting invites and is consistent across meeting occurrences. **Example value:** 123456789123 |  |
| First Client App Version Age | String | Client App Version Age indicates the age of the Teams client version (based on the Media Stack revision) in use by the first endpoint at the time the stream is established. |  |
| Second Client App Version Age | String | Client App Version Age indicates the age of the Teams client version (based on the Media Stack revision) in use by the second endpoint at the time the stream is established. |  |
| Thread Id | String | The identifier for the chat and resources associated with a meeting, generated when the meeting is created. This value is consistent across meeting occurrences. **Example value:** 19:meeting\_MzB...zIw@thread.v2 |  |
| **Network** |  |  |  |
| Transport | Enumeration **Possible values:**• UDP • TCP • Unrecognized | Network transport type used by stream. Unrecognized indicates that the system couldn't determine if the transport type is TCP or UDP. | • Transport type wasn't reported • The media path wasn't established |
| First Connectivity Ice | Enumeration **Possible values:**• DIRECT= Direct network path • RELAY = through relay • HTTP = through HTTP proxy • FAILED = connectivity failed | ICE connectivity type used by the first endpoint. | • Transport type wasn't reported • The media path wasn't established |
| Second Connectivity Ice | Enumeration **Possible values:**• DIRECT= Direct network path • RELAY = through relay • HTTP = through HTTP proxy • FAILED = connectivity failed | ICE connectivity type used by the second endpoint. | • Transport type wasn't reported • The media path wasn't established |
| First IP Address | String | IP address for first endpoint. Note this dimension might have too many rows to be used as dimension in a report. It can be used as a filter instead. **Example value:** 10.0.0.10 | • Transport type wasn't reported • The media path wasn't established |
| Second IP Address | String | IP address for second endpoint. **Note:** This dimension might have too many rows to be used as dimension in a report. It can be used as a filter instead. **Example value:** 10.0.0.10 | • Transport type wasn't reported • The media path wasn't established |
| First Link Speed | Integer | Link speed in bits per second reported by the network adapter used by the first endpoint. **Example value:** 10000000 | • Transport type wasn't reported • The media path wasn't established |
| Second Link Speed | Integer | Link speed in bits per second reported by the network adapter used by the second endpoint. **Example value:** 10000000 | • Transport type wasn't reported • The media path wasn't established |
| First Port | Port number | Network port number used by first endpoint for media. **Example value:** 50018 | • Transport type wasn't reported • The media path wasn't established |
| Second Port | Port number | Network port number used by second endpoint for media. **Example value:** 50018 | • Transport type wasn't reported • The media path wasn't established |
| First Reflexive Local IP | String | IP address of first endpoint as seen by the media relay server. This value is typically the public internet IP address associated to the first endpoint for the stream. **Example value:** 104.43.195.251 | • Transport type wasn't reported • The media path wasn't established |
| Second Reflexive Local IP | String | IP address of second endpoint as seen by the media relay server. This value is typically the public internet IP address associated to the second endpoint for the stream. **Example value:** 104.43.195.251 | • Transport type wasn't reported • The media path wasn't established |
| First Relay IP | String | IP address of the media relay server allocated by the first endpoint. **Example value:** 104.43.195.251 | • Transport type wasn't reported • The media path wasn't established |
| Second Relay IP | String | IP address of the media relay server allocated by the second endpoint. **Example value:** 104.43.195.251 | • Transport type wasn't reported • The media path wasn't established |
| First Relay Port | Integer | Media port allocated on the media relay server by the first endpoint. **Example value:** 3478 | • Transport type wasn't reported • The media path wasn't established |
| Second Relay Port | Integer | Media port allocated on the media relay server by the second endpoint. **Example value:** 3478 | • Transport type wasn't reported • The media path wasn't established |
| First Subnet | String | Subnet used for media stream by first endpoint with dashes separating each octet. **Example value:** 104.43.195.0 | •Data not reported by the endpoint • Media path wasn't established • IPv6 was used |
| Second Subnet | String | Subnet used for media stream by second endpoint with dashes separating each octet. **Example value:** 104.43.195.0 | •Data not reported by the endpoint • Media path wasn't established • IPv6 was used |
| First VPN | Boolean | True if the network adapter used by first endpoint indicated it's a VPN connection, False otherwise. Some VPNs don't correctly report this data correctly. | • Transport type wasn't reported • The media path wasn't established |
| Second VPN | Boolean | True if the network adapter used by second endpoint indicated it's a VPN connection, False otherwise. Some VPNs don't correctly report this data correctly. | • Transport type wasn't reported • The media path wasn't established |
| Applied Bandwidth Source | Enumeration **Possible values:**• Static Max • API Modality • API Modality\_All • API SendSide BWLimit • Preference Value • TURN • ReceiveSide TURN • API SDP Modality • Remote Received • Side BWLimit • API ServiceQuality • API SDP • Receive SidePDP | Identifies the source of bandwidth applied to the stream. | • Transport type wasn't reported • The media path wasn't established |
| Bandwidth Est | Integer Range | Average estimated bandwidth available between first and second endpoint in bits per second. **Example value:** 026: [260000 - 270000) | • Transport type wasn't reported • The media path wasn't established |
| Mediation Server Bypass Flag | Boolean | True if the media stream bypassed the Mediation Server and went straight between client and PSTN Gateway/PBX, False otherwise. | • Transport type wasn't reported • The media path wasn't established |
| First CDR Connectivity Type | Enumeration **Possible values:**• OS • PeerDerived • Stun • Turn | Identifies the ICE connectivity path selected by the first endpoint for use for this stream. **Example value:** OS | • Transport type wasn't reported • The media path wasn't established |
| Second CDR Connectivity Type | Enumeration **Possible values:**• OS • PeerDerived • Stun • Turn | Identifies the ICE connectivity path selected by the second endpoint for use for this stream. **Example value:** OS | • Transport type wasn't reported • The media path wasn't established |
| First BSSID | String | The Wireless LAN basic service set identifier of the First endpoint used to connect to the network. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| Second BSSID | String | The Wireless LAN basic service set identifier of the Second endpoint used to connect to the network. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| First Base Address | String | IP address of the interface that the first endpoint used for allocating media relay candidates. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 10.0.0.10 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Base Address | String | IP address of the interface that the second endpoint used for allocating media relay candidates. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 10.0.0.10 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Local Address | String | IP address that the first endpoint used for media flow at the end of media connectivity checks. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 10.0.0.10 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Local Address | String | IP address that the second endpoint used for media flow at the end of media connectivity checks. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 10.0.0.10 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Local Address Type | Enumeration **Possible Values**•IceAddrType\_Os •IceAddrType\_Stun •IceAddrType\_Turn •IceAddrType\_UPnP •IceAddrType\_ISA\_Proxy •IceAddrType\_PeerDerived •IceAddrType\_Invalid | The candidate type of First Local Address. IceAddrType\_Turn indicates a relayed call. The rest of the types indicate direct connections. | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Local Address Type | Enumeration **Possible Values**•IceAddrType\_Os •IceAddrType\_Stun •IceAddrType\_Turn •IceAddrType\_UPnP •IceAddrType\_ISA\_Proxy •IceAddrType\_PeerDerived •IceAddrType\_Invalid | The candidate type of Second Local Address. IceAddrType\_Turn indicates a relayed call. The rest of the types indicate direct connections. | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Remote Address | String | IP Address of the second endpoint to which the first endpoint sends media to at the end of media connectivity checks. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 10.0.0.10 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Remote Address | String | IP Address of the first endpoint to which the second endpoint sends media to at the end of media connectivity checks. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 10.0.0.10 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Remote Address Type | Enumeration **Possible Values**•IceAddrType\_Os •IceAddrType\_Stun •IceAddrType\_Turn •IceAddrType\_UPnP •IceAddrType\_ISA\_Proxy •IceAddrType\_PeerDerived •IceAddrType\_Invalid | Candidate type of First Remote Address. IceAddrType\_Turn indicates a relayed call. The rest of the values indicate direct connections. | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Remote Address Type | Enumeration **Possible Values**•IceAddrType\_Os •IceAddrType\_Stun •IceAddrType\_Turn •IceAddrType\_UPnP •IceAddrType\_ISA\_Proxy •IceAddrType\_PeerDerived •IceAddrType\_Invalid | Candidate type of Second Remote Address. IceAddrType\_Turn indicates a relayed call. The rest of the values indicate direct connections. | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Local Site | String | IP address of the first endpoint as seen by the media relay server. This value is typically the public internet IP address associated with the first endpoint for the stream. If for some reason the relays aren't reachable or allocations failed, this value is the IP of a local interface on the first endpoint.  This dimension is similar to First Reflexive Local IP, but this information is reported by the Transport Diagnostic event instead of QoE. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 104.43.195.251 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Local Site | String | IP Address of the second endpoint as seen by the media relay server. This value is typically the public internet IP address associated with the second endpoint for the stream. If for some reason the relays aren't reachable or allocations failed, this value is the IP of a local interface on the first endpoint.  This dimension is similar to Second Reflexive Local IP, but this information is reported by the Transport Diagnostic event instead of QoE. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 104.43.195.251 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Remote Site | String | The Local Site IP address reported by the second endpoint and exchanged with the first endpoint.  Extra information in case Transport Diagnostic event on the second endpoint isn't available for any reason. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 104.43.195.251 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Remote Site | String | The Local Site IP address reported by the first endpoint and exchanged with the second endpoint.  Extra information in case the Transport Diagnostic event on the first endpoint isn't available for any reason. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. **Example value:** 104.43.195.251 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Local Media Relay Address | String | Microsoft IP address of the media relay server allocated by the first endpoint.  This dimension is similar information to First Relay IP, but is reported by the Transport Diagnostic event instead of QoE. **Example value:** 52.114.5.237 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Local Media Relay Address | String | Microsoft IP address of the media relay server allocated by the second endpoint.  This dimension is similar information to Second Relay IP, but is reported by the Transport Diagnostic event instead of QoE. **Example value:** 52.114.5.237 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Remote Media Relay Address | String | Microsoft IP address of the media relay server allocated by the second endpoint and exchanged with the first endpoint.  Extra information in case the Transport Diagnostic event on the second endpoint isn't available for any reason. **Example value:** 52.114.5.237 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Remote Media Relay Address | String | Microsoft IP address of the media relay server allocated by the first endpoint and exchanged with the second endpoint.  Extra information in case the Transport Diagnostic event on the first endpoint isn't available for any reason. **Example value:** 52.114.5.237 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Transport Protocol | Enumeration string | The communications protocol used by the first endpoint for sending media. **Possible Values**•UDP - Multi-purpose UDP used for both TURN and host allocations •TurnTCP - TCP TURN allocation. Uses the proxy if proxy settings are specified •TCPHostPassive - TCP listen host socket for a passive connection type •TCPHostActive - TCP connection using an active connection type •CompoundTCP - A combination of upstream and downstream TCP connections. Typically over the HTTPS protocol. •MultiTCP - A connectivity model that uses multiple TCP connections and distributes packets to each using round robin. | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Transport Protocol | Enumeration string | The communications protocol used by the second endpoint for sending media. **Possible Values**•UDP - Multi-purpose UDP used for both TURN and host allocations •TurnTCP - TCP TURN allocation. Uses the proxy if proxy settings are specified •TCPHostPassive - TCP listen host socket for a passive connection type •TCPHostActive - TCP connection using an active connection type •CompoundTCP - A combination of upstream and downstream TCP connections. Typically over the HTTPS protocol. •MultiTCP - A connectivity model that uses multiple TCP connections and distributes packets to each using round robin. | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First Reflexive Local IP Network | String | IP subnet (/24) of first endpoint as seen by the media relay server. This value is typically the subnet of the public internet IP address associated to the first endpoint for the stream. **Example value:** 52.114.5.0 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| Second Reflexive Local IP Network | String | IP subnet (/24) of second endpoint as seen by the media relay server. This value is typically the subnet of the public internet IP address associated to the second endpoint for the stream. **Example value:** 52.114.5.0 | • Transport Diagnostic type wasn't reported • The media path wasn't established |
| First VPN Estimated | Boolean | Indicates high probability of a connection over a Virtual Private Network (VPN). **Possible values:** 0 or 1 |  |
| Second VPN Estimated | Boolean | Indicates high probability of a connection over a Virtual Private Network (VPN). **Possible values:** 0 or 1 |  |
| First Roaming Trigger | Enumeration (String) | Indicates the most recent cause the first endpoint performed a lightweight reconnect mid-call where signaling wasn't involved. For example, when an endpoint switches wireless access points on the same network. **Possible values:** • **Remote** - Sending packets to Peer, but Peer isn't receiving them  • **ConsentKA** - Keep-Alive Failures; 7-second timeout if no response to keep-alive packets  • **Interface** - Local Interface change or flap  • **RelayDraining** - Service maintenance (Expected) | • No roams occurred  • The endpoint didn't send data |
| Second Roaming Trigger | Enumeration (String) | Indicates number of times the second endpoint performed a lightweight reconnect mid-call where signaling wasn't involved. For example, when an endpoint switches wireless access points on the same network. **Possible values:** • **Remote** - Sending packets to Peer, but Peer isn't receiving them  • **ConsentKA** - Keep-Alive Failures; 7-second timeout if no response to keep-alive packets  • **Interface** - Local Interface change or flap  • **RelayDraining** - Service maintenance (Expected) | • No roams occurred  • The endpoint didn't send data |
| First QoS Applied | Boolean | Indicates if the streams inbound to the first endpoint were tagged with a DSCP decimal value. | • The stream is outbound from the first endpoint to the second endpoint  • The endpoint isn't a client endpoint  • The endpoint doesn't support Teams querying QoS values. |
| Second QoS Applied | Boolean | Indicates if the streams inbound to the second endpoint were tagged with a DSCP decimal value. | • The stream is outbound from the second endpoint to the first endpoint  • The endpoint isn't a client endpoint.  • The endpoint doesn't support Teams querying QoS values. |
| First QoS Value | Integer | The DSCP value assigned to the stream inbound to the first endpoint; common values are 46 for audio and 34 for video. | • A QoS value wasn't detected  • The stream is outbound from the first endpoint to the second endpoint  • The endpoint isn't a client endpoint.  • The endpoint doesn't support Teams querying QoS values. |
| Second QoS Value | Integer | The DSCP value assigned to the stream inbound to the second endpoint; common values are 46 for audio and 34 for video. | • A QoS value wasn't detected  • The stream is outbound from the second endpoint to the first endpoint.  • The endpoint isn't a client endpoint  • The endpoint doesn't support Teams querying QoS values. |
| First Roaming Count | Range (Integer) | Indicates number of times the first endpoint performed a lightweight reconnect mid-call where signaling wasn't involved. For example, when an endpoint switches wireless access points on the same network. **Example value:** 064: [1 - 2) |  |
| Second Roaming Count | Range (Integer) | Indicates number of times the second endpoint performed a lightweight reconnect mid-call where signaling wasn't involved. For example, when an endpoint switches wireless access points on the same network. **Example value:** 064: [1 - 2) |  |
| First Recv AV Sync Distance Avg | Milliseconds | The average difference between audio and video modality (video or VBSS) network delays in milliseconds for the first endpoint. A positive value would mean that audio arrived later than the video. |  |
| Second Recv AV Sync Distance Avg | Milliseconds | The average difference between audio and video modality (video orVBSS) network delays in milliseconds for the second endpoint. A positive value would mean that audio arrived later than the video. |  |
| First Recv AV Sync Distance Max | Milliseconds | The maximum difference value of how much video or VBSS is ahead of the audio for the first endpoint in milliseconds. |  |
| Second Recv AV Sync Distance Max | Milliseconds | The maximum difference value of how much video or VBSS is ahead of the audio for the second endpoint in milliseconds. |  |
| First Recv AV Sync Distance Min | Milliseconds | The minimum difference value of how much video or VBSS is ahead of the audio for the first endpoint in milliseconds. |  |
| Second Recv AV Sync Distance Min | Milliseconds | The minimum difference value of how much video or VBSS is ahead of the audio for the second endpoint in milliseconds. |  |
| First Recv AV Sync Distance Std Dev | Milliseconds | The standard deviation of the difference in audio/video sync delay for the first endpoint. Higher values are indicative of a larger variation of the offsync and can indicate burstier video transmission. |  |
| Second Recv AV Sync Distance Std Dev | Milliseconds | The standard deviation of the difference in audio/video sync delay for the second endpoint. Higher values are indicative of a larger variation of the offsync and can indicate burstier video transmission. |  |
| Outbound Bit Rate Avg | Kilobits per second (Integer) | The average bit rate of the outbound audio stream in kbps. Must be used with Stream Direction. | • The stream wasn't an audio stream. |
| Network Score | Range (Decimal) | Network Score is a value computed from network round-trip time, packet loss, and jitter. It's a ranking of the network quality for a Teams call or stream in a single number, with higher values being better. |  |
| First Web Network Receive Good Ratio | Range (Ratio) | Indicates how much of a stream's network receive quality was assessed as good on the first endpoint | • Endpoint wasn't using the Teams Web client |
| Second Web Network Receive Good Ratio | Range (Ratio) | Indicates how much of a stream's network receive quality was assessed as good on the second endpoint | • Endpoint wasn't using the Teams Web client |
| First Web Network Receive Bad Ratio | Range (Ratio) | Indicates how much of a stream's network receive quality was assessed as bad on the first endpoint | • Endpoint wasn't using the Teams Web client |
| Second Web Network Receive Bad Ratio | Range (Ratio) | Indicates how much of a stream's network receive quality was assessed as bad on the second endpoint | • Endpoint wasn't using the Teams Web client |
| First Web Network Send Good Ratio | Range (Ratio) | Indicates how much of a stream's network send quality was assessed as good on the first endpoint | • Endpoint wasn't using the Teams Web client |
| Second Web Network Send Good Ratio | Range (Ratio) | Indicates how much of a stream's network send quality was assessed as good on the second endpoint | • Endpoint wasn't using the Teams Web client |
| First Web Network Send Bad Ratio | Range (Ratio) | Indicates how much of a stream's network send quality was assessed as bad on the first endpoint | • Endpoint wasn't using the Teams Web client |
| Second Web Network Send Bad Ratio | Range (Ratio) | Indicates how much of a stream's network send quality was assessed as bad on the second endpoint | • Endpoint wasn't using the Teams Web client |
| **Device** |  |  |  |
| First Capture Dev | String | Name of the capture device used by the first endpoint. For: **Audio streams** = device used for the microphone **Video streams** = device used for the camera **Video-based-screen-sharing streams** = screen scraper **App sharing streams** = blank **Example value:** Headset Microphone (Microsoft LifeChat LX-6000) | • The endpoint didn't report the data • The media path wasn't established • The stream was video-based screen sharing or application sharing. |
| Second Capture Dev | String | Name of the capture device used by the second endpoint. **Audio streams** = device used for the microphone **Video streams** = device used for the camera **Video-based-screen-sharing streams** = screen scraper **App sharing streams** = blank **Example value:** Headset Microphone (Microsoft LifeChat LX-6000) | • The endpoint didn't report data • Media path wasn't established • The stream was video-based screen sharing or application sharing |
| First Capture Dev Driver | String | Name of the capture device driver used by the first endpoint in the form of "manufacturer : version." For: **Audio streams** = driver used for the microphone **Video streams** = driver used for the camera **Video-based-screen-sharing and app sharing streams** = blank **Example value:** Microsoft: 10.0.14393.0 | • The endpoint didn't report data • The media path wasn't established • The stream was video-based screen sharing or application sharing. |
| Second Capture Dev Driver | String | Name of the capture device driver used by the second endpoint in the form of "manufacturer : version." For: **Audio streams** = driver used for the microphone **Video streams** = driver used for the camera **Video-based-screen-sharing and app sharing streams** = blank **Example value:** Microsoft: 10.0.14393.0 | • The endpoint didn't report data • The media path wasn't established • The stream was video-based screen sharing or application sharing. |
| First Render Dev | String | Name of the render device used by the first endpoint. For:  Audio streams - device used for the speaker  Video and video-based-screen-sharing streams - device used for the display  App sharing streams - blank **Example value:** Headset Earphone (Microsoft LifeChat LX-6000) | • The endpoint didn't report this data • The media path wasn't established. • The stream was application sharing. |
| Second Render Dev | String | Name of the render device used by the second endpoint. For:  Audio streams - device used for the speaker  Video and video-based-screen-sharing streams - device used for the display  App sharing streams - blank **Example value:** Headset Earphone (Microsoft LifeChat LX-6000) | • The endpoint didn't report this data, • Media path wasn't established • The stream was application sharing |
| First Render Dev Driver | String | Name of the render device driver used by the first endpoint. For:  Audio streams - driver used for the speaker  Video and video-based-screen-sharing streams - driver used for the display  App sharing streams - blank **Example value:** Microsoft: 10.0.14393.0 | • The endpoint didn't report this data • Media path wasn't established • The stream was application sharing |
| Second Render Dev Driver | String | Name of the render device driver used by the second endpoint. For:  Audio streams - driver used for the speaker  Video and video-based-screen-sharing streams - driver used for the display  App sharing streams - blank **Example value:** Microsoft: 10.0.14393.0 | • The endpoint didn't report this data. • Media path wasn't established. • The stream was application sharing. |
| First Audio Devices Connection Type | Enumeration string | The connection interface or type of the audio device used on the first endpoint  Possible values: BlueTooth, HDAudio, Internal, Mixed, PCI, USB, Other |  |
| Second Audio Devices Connection Type | Enumeration string | The connection interface or type of the audio device used on the first endpoint  Possible values: BlueTooth, HDAudio, Internal, Mixed, PCI, USB, Other |  |
| First Audio Device General Failure | Boolean | Indicates if a general hardware failure is detected on the audio device of the first endpoint. |  |
| Second Audio Device General Failure | Boolean | Indicates if a general hardware failure is detected on the audio device of the second endpoint. |  |
| First Mic Device Failure | Boolean | Indicates if an audio capture device failure is detected on the first endpoint. |  |
| Second Mic Device Failure | Boolean | Indicates if an audio capture device failure is detected on the second endpoint. |  |
| First No Mic Devices Enumerated Failure | Boolean | Indicates that no audio capture devices were detected on the first endpoint. |  |
| Second No Mic Devices Enumerated Failure | Boolean | Indicates that no audio capture devices were detected on the second endpoint. |  |
| First Mic Is Silent | Boolean | Indicates no audio is detected from the first endpoint microphone while unmuted. |  |
| Second Mic Is Silent | Boolean | Indicates no audio is detected from the second endpoint microphone while unmuted. |  |
| First Mic Initialization Failure | Boolean | Indicates that a failure occurred during the hardware initialization of the microphone device on the first endpoint. |  |
| Second Mic Initialization Failure | Boolean | Indicates that a failure occurred during the hardware initialization of the microphone device on the second endpoint. |  |
| First Mic Connection Type | Enumeration string | The connection interface or type of the microphone device used on the first endpoint  Possible values: BlueTooth, HDAudio, Internal, PCI, USB, Virtual, Other |  |
| Second Mic Connection Type | Enumeration string | The connection interface or type of the microphone device used on the second endpoint  Possible values: BlueTooth, HDAudio, Internal, PCI, USB, Virtual, Other |  |
| First Speaker Device Failure | Boolean | Indicates if an audio render device failure is detected on the first endpoint. |  |
| Second Speaker Device Failure | Boolean | Indicates if an audio render device failure is detected on the second endpoint. |  |
| First No Speaker Devices Enumerated Failure | Boolean | Indicates that no audio render devices were detected on the first endpoint. |  |
| Second No Speaker Devices Enumerated Failure | Boolean | Indicates that no audio render devices were detected on the second endpoint. |  |
| First Speaker Initialization Failure | Boolean | Indicates that a failure occurred during the hardware initialization of the audio render device on the first endpoint. |  |
| Second Speaker Initialization Failure | Boolean | Indicates that a failure occurred during the hardware initialization of the audio render device on the second endpoint. |  |
| First Speaker Connection Type | Enumeration string | The connection interface or type of the audio render device used on the first endpoint  Possible values: USB, Wireless, Other |  |
| Second Speaker Connection Type | Enumeration string | The connection interface or type of the audio render device used on the second endpoint  Possible values: USB, Wireless, Other |  |
| First Compute Device Name | String | The detected system manufacturer and system model of the first endpoint.  Example: microsoft corporation surface pro | • System manufacturer and model weren't detected. |
| Second Compute Device Name | String | The detected system manufacturer and system model of the second endpoint.  Example: microsoft corporation surface pro | • System manufacturer and model weren't detected. |
| First Device Failure | Boolean | Indicates if an audio capture or render device failure is detected on the first endpoint. |  |
| Second Device Failure | Boolean | Indicates if an audio capture or render device failure is detected on the second endpoint. |  |
| **WiFi** |  |  |  |
| First WiFi Microsoft Driver | String | Name of Microsoft WiFi driver used reported by the first endpoint. Value might be localized based on the language used by endpoint. **Example value:** Microsoft Hosted Network Virtual Adapter | • WiFi wasn't used by the endpoint • The driver information wasn't reported |
| Second WiFi Microsoft Driver | String | Name of Microsoft WiFi driver used reported by the second endpoint. Value might be localized based on the language used by endpoint. **Example value:** Microsoft Hosted Network Virtual Adapter | • WiFi wasn't used by the endpoint • The driver information wasn't reported |
| First WiFi Vendor Driver | String | Vendor and name of WiFi driver reported by the first endpoint. **Example value:** Contoso Dual Band Wireless-AC Driver | • WiFi wasn't used by the endpoint • The driver information wasn't reported |
| Second WiFi Vendor Driver | String | Vendor and name of WiFi driver reported by the second endpoint. **Example value:** Contoso Dual Band Wireless-AC Driver | • WiFi wasn't used by the endpoint • The driver information wasn't reported |
| First WiFi Microsoft Driver Version | String | Version of Microsoft WiFi driver reported by the first endpoint. **Example value:** Microsoft:10.0.14393.0 | • WiFi wasn't used by the endpoint • The driver information wasn't reported |
| Second WiFi Microsoft Driver Version | String | Version of Microsoft WiFi driver reported by the second endpoint. **Example value:** Microsoft:10.0.14393.0 | • WiFi wasn't used by the endpoint • The driver information wasn't reported |
| First WiFi Vendor Driver Version | String | Vendor and version of WiFi driver reported by the first endpoint. **Example value:** Contoso:15.1.1.0 | • WiFi wasn't used by the endpoint • The driver information wasn't reported |
| Second WiFi Vendor Driver Version | String | Vendor and version of WiFi driver reported by the second endpoint. **Example value:** Contoso:15.1.1.0 | • WiFi wasn't used by the endpoint • The driver information wasn't reported. |
| First WiFi Channel | String | WiFi channel used by the first endpoint. **Example value:** 10 | • WiFi wasn't used • The channel wasn't reported. |
| Second WiFi Channel | String | WiFi channel used by the second endpoint. **Example value:** 10 | • WiFi wasn't used • The channel wasn't reported. |
| First WiFi Radio Type | String | Type of WiFi radio used by the first endpoint. HRDSSS is equivalent to 802.11b. **Example value:** 802.11ac | • WiFi wasn't used • The WiFi type wasn't reported |
| Second WiFi Radio Type | String | Type of WiFi radio used by the second endpoint. HRDSSS is equivalent to 802.11b. **Example value:** 802.11ac | • WiFi wasn't used • The WiFi type wasn't reported |
| First WiFi Band | String | WiFi band used as reported by the first endpoint. **Example value:** 5.0 Ghz | • The endpoint didn't compute the value • The value wasn't reported |
| Second WiFi Band | String | WiFi band used as reported by the second endpoint. **Example value:** 5.0 Ghz | • The endpoint didn't compute the value • The value wasn't reported |
| First WiFi Signal Strength | String | WiFi signal strength in percentage [0-100] reported by the first endpoint. **Example value:** 081: [90 - 100) | • The endpoint didn't compute the value • The value wasn't reported |
| Second WiFi Signal Strength | String | WiFi signal strength in percentage [0-100] reported by the second endpoint. **Example value:** 081: [90 - 100) | • The endpoint didn't compute the value • The value wasn't reported |
| First WiFi Battery Charge | Range (percentage) | Estimated remaining battery charge in percentage [0-99] reported by the first endpoint. Values grouped by range. 0 indicates that the device was plugged in. **Example value:** 081: [90 - 100) | • WiFi wasn't used • The charge value wasn't reported |
| Second WiFi Battery Charge | Range (percentage) | Estimated remaining battery charge in percentage [0-99] reported by the second endpoint. Values grouped by range. 0 indicates that the device was plugged in. **Example value:** 081: [90 - 100) | • WiFi wasn't used • The charge value wasn't reported |
| **Metrics** |  |  |  |
| First Web Max Session Bandwidth | Range (Kbps) | Displays the lower of either the default bandwidth limit or the bandwidth limit set by tenant policy for the Teams web client on the first endpoint | • Endpoint wasn't using the Teams Web client. |
| Second Web Max Session Bandwidth | Range (Kbps) | Displays the lower of either the default bandwidth limit or the bandwidth limit set by tenant policy for the Teams web client on the second endpoint | • Endpoint wasn't using the Teams Web client. |
| First Is Call Throttled | Boolean | Indicates that media may be affected by CPU throttling on the first endpoint. | • The endpoint receiving the stream reported no CPU data |
| Second Is Call Throttled | Boolean | Indicates that media may be affected by CPU throttling on the second endpoint. | • The endpoint receiving the stream reported no CPU data |
| Audio Degradation Avg | Range (Mean opinion score 0-5) | Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter impact the quality of received audio. Not for use with SATIN or WebRTC/VDI. Values grouped by range. **Example value:** 015: [0.01 - 0.02) | • The endpoint receiving the stream reported no network MOS degradation • The stream isn't an audio stream. |
| Jitter | Range (millisecond) | Average jitter for stream in milliseconds. Values grouped by range. **Example value:** 065: [2 - 3) | • The endpoint receiving the stream reported no jitter data |
| Jitter Max | Range (millisecond) | Maximum jitter for stream in milliseconds. Values grouped by range. **Example value:** 065: [2 - 3) | • The endpoint receiving the stream reported no jitter data |
| Packet Loss Rate | Range (ratio) | Average packet loss rate for stream. Values grouped by range. 0.1 indicates 10% packet loss. **Example value:** 015: [0.01 - 0.02) | • The endpoint receiving the stream reported no packet loss data |
| Packet Loss Rate Max | Range (ratio) | Maximum packet loss rate for stream. Values grouped by range. 0.1 indicates 10% packet loss. **Example value:** 023: [0.09 - 0.1) | • The endpoint receiving the stream reported no packet loss data • Packet utilization for a given stream is less than 100 packets |
| Send Listen MOS | Range (MOS) | Average MOS for stream. Values grouped by range. **Example value:** 076: [4.4 - 4.5) | • The endpoint receiving the stream reported no MOS • The stream isn't an audio stream • Codec used doesn't report MOS |
| Overall Avg Network MOS | Range (MOS) | Average Network MOS for stream. Values grouped by range. **Example value:** 076: [4.4 - 4.5) | • The endpoint receiving the stream reported no network MOS degradation • The stream isn't an audio stream • Codec used doesn't report MOS |
| Ratio Concealed Samples Avg | Range (ratio) | Ratio of the number of audio frames with samples generated by packet loss concealment to the total number of audio frames. Values grouped by range. 0.1 indicates 10% of frames contained concealed samples. **Example value:** 015: [0.01 - 0.02) | • The receiver of the stream didn't report this value • The stream wasn't an audio stream |
| Conceal Ratio Max | Range (ratio) | The maximum seen number of audio frames with samples generated by packet loss concealment to the total number of audio frames. Values grouped by range. 0.1 indicates 10% of frames contained concealed samples. **Example value:** 015: [0.01 - 0.02) |  |
| Ratio Stretched Samples Avg | Range (ratio) | Ratio of the number of audio frames with samples that are stretched to compensate for jitter or loss to the total number of audio frames. Values grouped by range. 0.1 indicates 10% audio frames contained stretched samples. **Example value:** 017: [0.03 - 0.04) | • The receiver of the stream didn't report this value • The stream wasn't an audio stream |
| Healer Packet Drop Ratio | Range (ratio) | Ratio of audio packets dropped by healer over total number of audio packets received by healer. See [2.2.1.12.1 Child Elements](/en-us/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) for more information. |  |
| Healer FEC Packet Used Ratio | Range (ratio) | Ratio of used Forward Error Correction (FEC) packets over total number of received FEC packets. See [2.2.1.12.1 Child Elements](/en-us/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5) for more information. |  |
| Round Trip | Range (milliseconds) | Average network propagation round-trip time computed as specified in RFC3550 in milliseconds. Values grouped by range. **Example value:** 070: [15 - 20) | • The value wasn't computed by the endpoint • The value wasn't reported |
| Round Trip Max | Range (milliseconds) | Maximum network propagation round-trip time computed as specified in RFC3550 in milliseconds. Values grouped by range. **Example value:** 098: [350 - 375) | • The value wasn't computed by the endpoint • The value wasn't reported |
| Packet Utilization | Range (packets) | Number of Real-Time Transport Protocol (RTP) packets sent in the session. |  |
| Jitter Buffer Size Avg | Range (number) | Average size of jitter buffer during session. |  |
| Jitter Buffer Size Max | Range (number) | Maximum size of jitter buffer during session. |  |
| Jitter Buffer Size Min | Range (number) | Minimum size of jitter buffer during session. |  |
| Relative OneWay Gap Duration | Range (number) | Duration of gaps in the relative one way delay of the peer. |  |
| Audio Post FECPLR | Number | Reports packet loss rate after FEC has been applied for audio. Value between 0.00 and 1.00. |  |
| Network Jitter Avg | Range (milliseconds) | Average of network jitter in milliseconds computed over 20-second windows during the session. Values grouped by range. **Example value:** 066: [3–4) | • The stream wasn't an audio stream • Data wasn't reported by the endpoint receiving the stream. |
| Network Jitter Max | Number of events | Maximum of network jitter computed over 20-second windows during the session. |  |
| Network Jitter Min | Number of events | Minimum of network jitter computed over 20-second window during the session. |  |
| Video Post FECPLR | Range (ratio) | Packet loss rate after FEC is applied for aggregated across all video streams and codecs. Values grouped by range. **Example value:** 014: [0 - 0.01) | • The stream wasn't a video or video-based-screen-sharing stream • The endpoint receiving the stream didn't report data |
| Video Local Frame Loss Percentage Avg | Range (percentage) | Average percentage of video frames lost as displayed to the user. Values grouped by range. This includes frames recovered from network losses. **Example value:** 160: [80 - 85) | • The stream wasn't a video or video-based-screen-sharing stream • The endpoint receiving the stream didn't report data |
| Recv Frame Rate Average | Range (frames per second) | Average frames per second received for all video streams computed over the duration of the session. Values grouped by range. **Example value:** 101: [14.5 - 15) | • The stream wasn't a video or video-based-screen-sharing stream • The endpoint receiving the stream didn't report data |
| Low Frame Rate Call Percent | Range (percentage) | Percentage of time of the call where frame rate is less than 7.5 frames per second. Values grouped by range. **Example value:** 099: [13.5 - 14) | • The stream wasn't a video or video-based-screen-sharing stream • The endpoint receiving the stream didn't report data |
| Video Packet Loss Rate | Range (ratio) | Average fraction of packets lost, as specified in RFC3550, computed over the duration of the session. Values grouped by range. **Example value:** 037: [0.75 - 0.8) | • The stream wasn't a video or video-based-screen-sharing stream • The endpoint receiving the stream didn't report data |
| Video Frame Rate Avg | Range (frames per second) | Average frames per second received for a video stream, computed over the duration of the session. Values grouped by range. **Example value:** 135: [31.5 - 32) | • The stream wasn't a video or video-based-screen-sharing stream • The endpoint receiving the stream didn't report data |
| Dynamic Capability Percent | Range (percentage) | Percentage of time that the client is running &lt; 70% expected video processing capability for this type of CPU grouped by range **Example value:** 122: [25 - 25.5) | • The stream wasn't a video or video-based-screen-sharing stream • The endpoint receiving the stream didn't report data |
| Spoiled Tile Percent Total | Range (percentage) | Percentage of tiles which are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Values grouped by range. Discarded tiles might be caused by bandwidth restrictions between client and server. **Example value:** 140: [34 - 34.5) | • The stream wasn't an application sharing stream • The endpoint sending the stream didn't report the data |
| AppSharing Relative OneWay Average | Range (seconds) | Average relative one-way delay between the endpoints in seconds for application sharing streams. Values grouped by range. **Example value:** 015: [0.01 - 0.02) | • The stream wasn't an application sharing stream • The endpoint sending the stream didn't report the data |
| AppSharing RDP Tile Processing Latency Average | Range (milliseconds) | Average latency in milliseconds processing tiles on the RDP Stack at the conferencing server. Values grouped by range. **Example value:** 103: [15.5 - 16) | • The stream wasn't an application sharing stream in a conference • The endpoint sending the stream didn't report the data |
| First Network Delay Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected the network delay was significant enough to impact the ability to have real-time two-way communication. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Network Delay Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected the network delay was significant enough to impact the ability to have real-time two-way communication. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Network Bandwidth Low Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected the available bandwidth or bandwidth policy was low enough to cause poor quality of the audio sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Network Bandwidth Low Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected the available bandwidth or bandwidth policy was low enough to cause poor quality of the audio sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Mic Glitch Rate | Number | Average glitches per 5 minutes for the microphone capture of the first endpoint. For more information, see [2.2.1.12.1 Child Elements](/en-us/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5). |  |
| Second Mic Glitch Rate | Number | Average glitches per 5 minutes for the microphone capture of the second endpoint. For more information, see [2.2.1.12.1 Child Elements](/en-us/openspecs/office_protocols/ms-qoe/56d41628-26d5-44c8-8f79-6bac4b0355a5). |  |
| First Speaker Glitch Rate | Number of events | Average glitches per 5 minutes for the first loudspeaker rendering. |  |
| Second Speaker Glitch Rate | Number of events | Average glitches per 5 minutes for the second loudspeaker rendering. |  |
| First Send Mute Percent | Range (Percentage) | Percentage of the audio stream from the first endpoint where the client was muted. | • Stream isn't an audio stream  • The first endpoint didn't report data |
| Second Send Mute Percent | Range (Percentage) | Percentage of the audio stream from the second endpoint where the client was muted. | • Stream isn't an audio stream  • The second endpoint didn't report data |
| First System CPU Resource Usage Average | Range (percentage) | The average of the system's overall CPU usage measured for the first endpoint. |  |
| Second System CPU Resource Usage Average | Range (percentage) | The average of the system's overall CPU usage measured for the second endpoint. |  |
| First Process CPU Resource Usage Average | Range (percentage) | The average of the CPU usage by the Teams process measured for the first endpoint. |  |
| Second Process CPU Resource Usage Average | Range (percentage) | The average of the CPU usage by the Teams process measured for the second endpoint. |  |
| First System Memory Resource Usage Average | Range (percentage) | The average of the system's overall memory usage measured for the first endpoint. |  |
| Second System Memory Resource Usage Average | Range (percentage) | The average of the system's overall memory usage measured for the second endpoint. |  |
| First Process Memory Resource Usage Average | Range (percentage) | The average of the memory usage by the Teams process measured for the first endpoint. |  |
| Second Process Memory Resource Usage Average | Range (percentage) | The average of the memory usage by the Teams process measured for the second endpoint. |  |
| First System CPU Resource Usage Max | Range (percentage) | The maximum value of the system's overall CPU usage measured for the first endpoint. |  |
| Second System CPU Resource Usage Max | Range (percentage) | The maximum value of the system's overall CPU usage measured for the second endpoint. |  |
| First Process CPU Resource Usage Max | Range (percentage) | The maximum value of the CPU usage by the Teams process measured for the first endpoint. |  |
| Second Process CPU Resource Usage Max | Range (percentage) | The maximum value of the CPU usage by the Teams process measured for the second endpoint. |  |
| First System Memory Resource Usage Max | Range (percentage) | The maximum value of the system's overall memory usage measured for the first endpoint. |  |
| Second System Memory Resource Usage Max | Range (percentage) | The maximum value of the system's overall memory usage measured for the second endpoint. |  |
| First Process Memory Resource Usage Max | Range (percentage) | The maximum value of the memory usage by the Teams process measured for the first endpoint. |  |
| Second Process Memory Resource Usage Max | Range (percentage) | The maximum value of the memory usage by the Teams process measured for the second endpoint. |  |
| First Web Time Muted In Client | Range (milliseconds) | The amount of time in milliseconds the user was muted in the Teams web client on the first endpoint. | • Endpoint wasn't using the Teams Web client. |
| Second Web Time Muted In Client | Range (milliseconds) | The amount of time in milliseconds the user was muted in the Teams web client on the first endpoint. | • Endpoint wasn't using the Teams Web client. |
| **Audio** |  |  |  |
| Audio FEC Used | Boolean | True indicates that audio forward error correction (FEC) is used at some point during the call. False otherwise | • The stream wasn't an audio stream • The endpoint sending the stream didn't report the data |
| First Audio Render Device In Use | String | Indicates which hardware device is used for playback of the audio stream on the first endpoint. | • The endpoint didn't report the data |
| Second Audio Render Device In Use | String | Indicates which hardware device is used for playback of the audio stream on the second endpoint. | • The endpoint didn't report the data |
| First Audio Capture Device In Use | String | Indicates which hardware device is used for capture of the audio stream on the first endpoint. | • The endpoint didn't report the data |
| Second Audio Capture Device In Use | String | Indicates which hardware device is used for capture of the audio stream on the second endpoint. | • The endpoint didn't report the data |
| First Audio Codec Average BW | Integer | Indicates the average bandwidth for the first endpoint's audio stream measured, in bytes per second. | • Stream wasn't an audio stream |
| Second Audio Codec Average BW | Integer | Indicates the average bandwidth for the second endpoint's audio stream measured, in bytes per second. | • Stream wasn't an audio stream |
| First Mic Device Is Speaker Device | Boolean | Indicates if the same audio device is used by the first endpoint for both capture and rendering. |  |
| Second Mic Device Is Speaker Device | Boolean | Indicates if the same audio device is used by the second endpoint for both capture and rendering. |  |
| First Capture Dev Name | String | Name of the audio capture device used by the first endpoint. |  |
| Second Capture Dev Name | String | Name of the audio capture device used by the second endpoint. |  |
| First Render Dev Name | String | Name of the audio playback device used by the first endpoint. |  |
| Second Render Dev Name | String | Name of the audio playback device used by the second endpoint. |  |
| First Noise Suppression Model Download Failure | Boolean | Indicates if the First endpoint successfully downloaded the noise suppression model prior to outbound audio stream establishment. | • Noise suppression model download isn't applicable to or supported by the endpoint or codec.  • Stream isn't outbound audio. |
| Second Noise Suppression Model Download Failure | Boolean | Indicates if the Second endpoint successfully downloaded the noise suppression model prior to outbound audio stream establishment. | • Noise suppression model download isn't applicable to or supported by the endpoint or codec.  • Stream isn't outbound audio. |
| **Measure** |  |  |  |
| ClassifiedPoorCall | Boolean | True if one or more streams in the call were classified as poor based on the metrics listed in [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). | • The call didn't have sufficient metrics reported to be classified as good or poor |
| Video Poor Due To VideoPostFecplr | Boolean | True if the stream is classified as poor based on the Video Post FEC PLR metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-video streams. | • The endpoint didn't report this data • The stream wasn't a video stream. |
| Video Poor Due To VideoLocalFrameLossPercentageAvg | Boolean | True if the video stream is classified as poor based on the Video Local Frame Loss Percentage Avg metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-video streams. | • The endpoint didn't report this data • The stream wasn't a video stream. |
| Video Poor Due To VideoFrameRateAvg | Boolean | True if the video stream is classified as poor based on the Video Frame Rate Avg metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-video streams. | • The endpoint didn't report this data • The stream wasn't a video stream |
| VBSS Poor Due To VideoPostFecplr | Boolean | True if the video-based screen-sharing stream is classified as poor based on the Video Post FEC PLR metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-video based screen-sharing streams. | • The endpoint didn't report this data • The stream wasn't a video-based screen sharing stream |
| VBSS Poor Due To VideoLocalFrameLossPercentageAvg | Boolean | True if the video-based screen-sharing stream is classified as poor based on the Video Local Frame Loss Percentage Avg metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-video based screen-sharing streams. | • The endpoint didn't report this data • The stream wasn't a video-based screen sharing stream |
| Video Poor Due To Freeze | Boolean | 1 if the video stream is classified as poor based on the Video Freeze instance: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard) | • The endpoint didn't report this data • The stream wasn't a video stream. This field is specific to Microsoft Teams only. |
| VBSS Poor Due To VideoFrameRateAvg | Boolean | True if the video based screen-sharing stream is classified as poor based on the Video Frame Rate Avg metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-video based screen-sharing streams. | • The endpoint didn't report this data • The stream wasn't a video-based screen-sharing stream |
| AppSharing Poor Due To SpoiledTilePercentTotal | Boolean | True if the application sharing stream is classified as poor based on the Spoiled Tile Percent Total metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-application sharing streams. | • The endpoint didn't report this data • The stream wasn't an application sharing stream. |
| AppSharing Poor Due To RelativeOneWayAverage | Boolean | True if the application sharing stream is classified as poor based on the Relative One Way Average metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-application sharing streams. | • The endpoint didn't report this data • The stream wasn't an application sharing stream |
| AppSharing Poor Due To RDPTileProcessingLatencyAverage | Boolean | True if the application sharing stream is classified as poor based on the RDP Tile Processing Latency Average metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-application sharing streams. | • The endpoint didn't report this data • The stream wasn't an application sharing stream |
| Audio Poor Due To Jitter | Boolean | True if the audio stream is classified as poor based on the Jitter metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-audio streams. | • The endpoint didn't report this data • The stream wasn't an audio sharing stream |
| Audio Poor Due To RoundTrip | Boolean | True if the audio stream is classified as poor based on the Round Trip metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-audio streams. | • The endpoint didn't report this data • The stream wasn't an audio sharing stream |
| Audio Poor Due To PacketLoss | Boolean | True if the audio stream is classified as poor based on the Packet Loss metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-audio streams. | • The endpoint didn't report this data • The stream wasn't an audio sharing stream |
| Audio Poor Due To Degradation | Boolean | True if the audio stream is classified as poor based on the Degradation metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-audio streams. Note: Degradation is deprecated in the classifier. | • The endpoint didn't report this data • The stream wasn't an audio sharing stream |
| Audio Poor Due To ConcealedRatio | Boolean | True if the audio stream is classified as poor based on the Concealed Ratio metric threshold listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Is always False for non-audio streams. Note: Concealed Ratio is deprecated in the classifier. | • The endpoint didn't report this data • The stream wasn't an audio sharing stream |
| Poor Reason | Flags **Possible values:**• Concealed Ratio • Degradation • Jitter • Packet Loss • Round Trip  Video Frame Rate Avg  Video Local Frame Loss Percentage Avg • Video Post FEC PLR • RDP Tile Processing Latency Average • Relative OneWay Average • Spoiled Tile Percent Total | List of flags that identify why the stream is marked as poor. There might be multiple flags set since there can be multiple reasons why the stream is marked as Poor. Refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard) for details. | • The stream wasn't classified as poor |
| Poor | Boolean | True if the stream has sufficient data to be classified as good or poor and stream is classified as poor. False otherwise. |  |
| Good | Boolean | True if the stream has sufficient data to be classified as good or poor and stream is classified as good. False otherwise. |  |
| Unclassified | Boolean | False if the stream has sufficient data to be classified as good or poor. True otherwise. **Example value:** 1 |  |
| OnePercent PacketLoss | Boolean | True if packet loss exceeded 1%, False otherwise. |  |
| Is Dominant Participant | Boolean | If true, indicates high confidence that the stream originated from an endpoint with a high rate of speaker participation. | • Calculated only for Conferencing participants  • PSTN participants are excluded from this model |
| Is Dominant Participant Probability | Decimal (Percentage) | The probability that the stream originated from an endpoint with a high rate of speaker participation; values closer to 1 indicate a higher probability. | • Calculated only for Conferencing participants  • PSTN participants are excluded from this model |
| Detected Inbound Network Problem | Boolean | If true, indicates high confidence that a media stream might be impacted due to the inbound network. | • This dimension only applies to streams where *Stream Direction == First-to-Second* |
| Detected Uplink Problem | Boolean | If true, indicates high confidence that a media stream might be impacted due to the network uplink. | • This dimension doesn't apply to P2P calls. |
| Detected Other User Uplink Problem | Boolean | If true, indicates high confidence that a user's media stream might be impacted due to a dominant participant's network uplink issues. | • This dimension doesn't apply to P2P calls. |
| Detected Input Device Causing Problem | Boolean | If true, indicates high confidence that the quality of sent media might be impacted due to the user's media capture device. |  |
| Detected Other User Device Problem | Boolean | If true, indicates high confidence that a media stream might be impacted due to the remote capture device. |  |
| Detected Local Input Device Problem | Boolean | If true, indicates high confidence that a media stream might be impacted due to the render device on the first endpoint. | • This dimension only applies to streams where *Stream Direction == First-to-Second* |
| Detected Leaking Echo Problem | Boolean | If true, indicates high confidence that the endpoint's outbound media stream is impacted due to echo. |  |
| Detected Hearing Echo Problem | Boolean | If true, indicates high confidence that a media stream might be impacted due to echo. |  |
| Detected Compute Device Causing Problem | Boolean | If true, indicates high confidence that the endpoint's outbound media stream might be impacted due to compute resources on the sender's side. |  |
| Detected Other User Compute Problem | Boolean | If true, indicates high confidence that a media stream might be impacted due to compute resources on the remote side. |  |
| Detected Local Compute Problem | Boolean | If true, indicates high confidence that a media stream might be impacted due to local compute resources. | • This dimension only applies to streams where *Stream Direction == First-to-Second* |
| Detected Media Modality Problem | Boolean | If true, indicates high confidence that the user's experience of the inbound media stream was poor. | • This dimension only applies to streams where *Stream Direction == First-to-Second* |
| **Rating** |  |  |  |
| First Feedback Rating | User rating (1-5) | Rating of the call associated with the stream by the first endpoint on 1-5 scale (5 = excellent). 0 indicates the user was shown the call rating survey but didn't rate their experience. **Example value:** 5 | • No survey was shown to the first endpoint |
| Second Feedback Rating | User rating (1-5) | Rating of the call associated with the stream by the second endpoint on 1-5 scale (5 = excellent). 0 indicates the user was shown the call rating survey but didn't rate their experience. **Example value:** 5 | • No survey was shown to the second endpoint |
| First Feedback Tokens | String | String containing list of feedback tokens with boolean flag that indicates if token is set by the user providing feedback from the first endpoint. **Example value:** {DistortedSpeech:1; ElectronicFeedback:1; BackgroundNoise:1; MuffledSpeech:1; Echo:1;} | • No feedback was provided by the user of the first endpoint |
| Second Feedback Tokens | String | String containing list of feedback tokens with boolean flag that indicates if token is set by the user providing feedback from the second endpoint. **Example value:** {DistortedSpeech:1; ElectronicFeedback:1; BackgroundNoise:1; MuffledSpeech:1; Echo:1;} | • No feedback was provided by the user of the second endpoint |
| First Feedback Has Audio Issue | Boolean | True if feedback tokens from first endpoint indicate stream had an audio issue, false otherwise. |  |
| Second Feedback Has Audio Issue | Boolean | True if feedback tokens from second endpoint indicate stream had an audio issue, False otherwise. |  |
| First Feedback Has Video Issue | Boolean | True if feedback tokens from first endpoint indicate stream had a video issue, False otherwise. |  |
| Second Feedback Has Video Issue | Boolean | True if feedback tokens from second endpoint indicate stream had a video issue, False otherwise. |  |
| First Feedback Has AppSharing Issue | Boolean | True if feedback tokens from first endpoint indicate stream had an app sharing issue. False otherwise. |  |
| Second Feedback Has Appsharing Issue | Boolean | True if feedback tokens from second endpoint indicate stream had an app sharing issue. False otherwise. |  |
| **Audio Signal** |  |  |  |
| First Echo Event Causes | Flags | Flags that indicate the reasons the DeviceEchoEvent is raised on the first endpoint. There might be multiple flags for a single stream. Flags include:  BAD\_TIMESTAMP - audio sample timestamps from capture or render device used were poor quality  POSTAEC\_ECHO - high level of echo remained after echo cancellation  MIC\_CLIPPING - signal level from capture device had significant instances of maximum signal level  EVENT\_ANLP - audio samples from capture contain high noise. **Example value:** BAD\_TIMESTAMP | • Stream was a non-audio stream • No event causes were reported by the first endpoint |
| Second Echo Event Causes | Flags | Flags that indicate the reasons the DeviceEchoEvent was raised on the second endpoint. There might be multiple flags for a single stream. Flags include:  BAD\_TIMESTAMP - audio sample timestamps from capture or render device used were poor quality  POSTAEC\_ECHO - high level of echo remained after echo cancellation  MIC\_CLIPPING - signal level from capture device had significant instances of maximum signal level  EVENT\_ANLP - audio samples from capture contain high noise. **Example value:** BAD\_TIMESTAMP | • Stream was a non-audio stream • No event causes were reported by the first endpoint |
| First Echo Percent Mic In | Range (percentage) | Percentage of time when echo is detected in the audio from the capture or microphone device prior to echo cancellation by the first endpoint. Values grouped by range. **Example value:** 068: [5 - 10) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Echo Percent Mic In | Range (percentage) | Percentage of time when echo is detected in the audio from the capture or microphone device prior to echo cancellation by the second endpoint. Values grouped by range. **Example value:** 068: [5 - 10) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Echo Percent Send | Range (percentage) | Percentage of time echo is detected in the audio after echo cancellation by the first endpoint. Values grouped by range. **Example value:** 068: [5 - 10) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Echo Percent Send | Range (percentage) | Percentage of time echo is detected in the audio after echo cancellation by the second endpoint. Values grouped by range. **Example value:** 068: [5 - 10) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Send Signal Level | Range (dB decibels) | Average energy level of sent audio for audio classified as mono speech, or left channel of stereo speech by the first endpoint. Values grouped by range. **Example value:** 055: [-15 - -10) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Send Signal Level | Range (dB decibels) | Average energy level of sent audio for audio classified as mono speech, or left channel of stereo speech by the second endpoint. Values grouped by range. **Example value:** 055: [-15 - -10) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Recv Signal Level | Range (dB decibels) | Average energy level of received audio for audio classified as mono speech, or left channel of stereo speech by the first endpoint. Values grouped by range. **Example value:** 056: [-10 - -5) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Recv Signal Level | Range (dB decibels) | Average energy level of received audio for audio classified as mono speech, or left channel of stereo speech by the second endpoint. Values grouped by range. **Example value:** 056: [-10 - -5) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Send Noise Level | Range (dB decibels) | Average energy level of audio classified as mono noise or stereo left channel noise sent by the first endpoint. Values grouped by range. **Example value:** 048: [-50 - -45) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Send Noise Level | Range (dB decibels) | Average energy level of audio classified as mono noise or stereo left channel noise by the second endpoint. Values grouped by range. **Example value:** 048: [-50 - -45) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Recv Noise Level | Range (dB decibels) | Average energy level of mono noise or stereo left channel noise received by the first endpoint. Values grouped by range. **Example value:** 048: [-50 - -45) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Recv Noise Level | Range (dB decibels) | Average energy level of mono noise or stereo left channel noise received by the second endpoint. Values grouped by range. **Example value:** 048: [-50 - -45) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Initial Signal Level RMS | Range (dB decibels) | The root-mean-square (RMS) of the received signal for the first 30 seconds of the call for the first endpoint. See [2.2.1.28.1 Child Elements](/en-us/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7) |  |
| Second Initial Signal Level RMS | Range (dB decibels) | The root-mean-square (RMS) of the received signal for the first 30 seconds of the call for the second endpoint. See [2.2.1.28.1 Child Elements](/en-us/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7) for more information. |  |
| First RxAGC Signal Level | Range (dB decibels) | Signal level received at the automatic gain control (AGC) for the first inbound audio stream. |  |
| Second RxAGC Signal Level | Range (dB decibels) | Signal level received at the automatic gain control (AGC) for the second inbound audio stream. |  |
| First RxAGC Noise Level | Range (dB decibels) | Noise level received at the automatic gain control (AGC) for the first inbound audio stream. |  |
| Second RxAGC Noise Level | Range (dB decibels) | Noise level received at the automatic gain control (AGC) for the second inbound audio stream. |  |
| First Render Loopback Signal Level | Range (dB decibels) | Loopback signal level for the first inbound audio stream. |  |
| Second Render Loopback Signal Level | Range (dB decibels) | Loopback signal level for the Second inbound audio stream. |  |
| **Client Event** |  |  |  |
| First Network Send Quality Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected the network was causing poor quality of the audio sent. Values grouped by range. **Example value:** 015: [0.01 - 0.02) | • Indicates a non-audio stream • The first endpoint didn't report data |
| Second Network Send Quality Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected the network was causing poor quality of the audio sent. Values grouped by range. **Example value:** 015: [0.01 - 0.02) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Network Receive Quality Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected the network was causing poor quality of the audio received. Values grouped by range. **Example value:** 015: [0.01 - 0.02) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Network Receive Quality Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected the network was causing poor quality of the audio received. Values grouped by range. **Example value:** 015: [0.01 - 0.02) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First CPU Insufficient Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected the CPU resources available were insufficient and caused poor quality of the audio sent and received. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The first endpoint didn't report data |
| Second CPU Insufficient Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected the CPU resources available were insufficient and caused poor quality of the audio sent and received. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device HalfDuplex AEC Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected issues and operated the acoustic echo canceler in half-duplex mode, which impacted the ability to have real-time two-way communication. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device HalfDuplex AEC Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected issues and operated the acoustic echo canceler in half-duplex mode, which impacted the ability to have real-time two-way communication. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Render Not Functioning Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected the render device wasn't working properly. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Render Not Functioning Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected the render device wasn't working properly. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Capture Not Functioning Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected the capture device wasn't working properly. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Capture Not Functioning Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected the capture device wasn't working properly. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Glitches Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected as glitches or gaps that caused poor quality of the audio being sent or received. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Glitches Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected as glitches or gaps in the audio that caused poor quality of the audio being sent or received. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Low SNR Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected low speech to noise level that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The first endpoint didn't report data |
| Second Device Low SNR Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected low speech to noise level that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Low Speech Level Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected low speech level that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Low Speech Level Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected low speech level that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Clipping Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected clipping in the captured audio that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The first endpoint didn't report data |
| Second Device Clipping Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected clipping in the captured audio that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Echo Event Ratio | Range (ratio) | Fraction of the call that the first endpoint detected echo that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Echo Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected echo that caused poor quality of the audio being sent. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device NearEnd To Echo Ratio Event Ratio | Range (ratio) | Fraction of the call where the first endpoint detected a ratio of near end signal to echo that caused poor quality audio. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device NearEnd To Echo Ratio Event Ratio | Range (ratio) | Fraction of the call that the second endpoint detected a ratio of near end signal to echo level that caused poor quality audio. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Render Zero Volume Event Ratio | Range (ratio) | Fraction of the call that first endpoint detected device render volume is set to 0. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Render Zero Volume Event Ratio | Range (ratio) | Fraction of the call that second endpoint detected device render volume is set to 0. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Render Mute Event Ratio | Range (ratio) | Fraction of the call that first endpoint detected device render is muted. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Render Mute Event Ratio | Range (ratio) | Fraction of the call that second endpoint detected device render is muted. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Multiple Endpoints Event Count | Range (ratio) | Number of times during the call that the first endpoint detected multiple endpoints in the same room or acoustic environment. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Multiple Endpoints Event Count | Range (ratio) | Number of times during the call that the second endpoint detected multiple endpoints in the same room or acoustic environment. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Device Howling Event Count | Range (ratio) | Number of times during the call that the first endpoint detected two or more endpoints in the same room that caused poor quality audio in the form of howling or screeching audio. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Stream was a non-audio stream • The first endpoint didn't report data |
| Second Device Howling Event Count | Range (ratio) | Number of times during the call that the second endpoint detected two or more endpoints in the same room or acoustic environment that caused poor quality audio in the form of howling or screeching audio. Values grouped by range. **Example value:** 016: [0.02 - 0.03) | • Indicates a non-audio stream • The second endpoint didn't report data |
| First Web Video Capture Device Failure Event Count | Integer | The number of times the video capture device reported a failure on the first Teams web client endpoint. | • User wasn't using the Teams Web client. |
| Second Web Video Capture Device Failure Event Count | Integer | The number of times the video capture device reported a failure on the second Teams web client endpoint. | • User wasn't using the Teams Web client. |
| **Call Diagnostic** |  |  |  |
| Error Report Sender | String | Indicates which endpoint sent the call error report for the stream. This report contains telemetry that might indicate call setup or call drop issues with the call. **Example value:** First | • Indicates no call error report was received. |
| Is Media Error | String | Indicates if the call error report for the stream was a media level error or not. This report contains telemetry that might indicate call setup or call drop issues with the call. | • Indicates no call error report was received. |
| Media Failure Type | Enumeration **Possible values:**• Midcall • CallSetup • MediaFailureUnknownType • NotMediaFailure | The type of media failure associated with the stream.  Note: "NotMediaFailure" doesn't indicate a non-media failure occurred, only that no media failures occurred. MediaFailureUnknownType indicates a media failure is detected, but doesn't fall under the MidCall or CallSetup classifications due to either being an edge case scenario, or missing telemetry. | • Indicates no call error report was received. |
| Call Classification | Enumeration | Reliability Classification assigned to the call. **Possible values**: Success, Failure, ClassificationUnavailable |  |
| Classification Reason | String | Reason the classification was assigned to the stream. |  |
| Test Call Type | Enumeration | Indicates whether this call is a regular call or a test call. If it's a test call, this indicates the type of test call. **Possible Values:** NonTest, Silent, UserInitiated, Synthetic **Meanings:** NonTest – Regular Call  Silent – Silent Test Call  UserInitiated – User initiated test call Synthetic – ST endpoint-initiated call |  |
| **Session** |  |  |  |
| RTP RTCP Mux | Boolean | True indicates that RTP and RTCP were multiplexed on the same ports. False otherwise. | • The endpoint didn't report data |
| Stun Version | Integer | Version of STUN protocol used for establishing the call. | • The endpoint didn't report data **Example value:** 2 |
| Media Relay | String | IP address for Media relay(s) used for the session. Might report a pair of relay separated by a '+' if the stream. **Example value:** "13.107.8.2 + 13.107.8.2" | • The endpoints didn't report this data |
| Is Anonymous Join Session | Boolean | True if user joining conference was anonymous, False otherwise. | • No data to determine if user was joined anonymously or not |
| Has Media Diag Blob | Boolean | True if session had media diagnostics data, False otherwise. | • Some signaling data wasn't collected for this stream |
| Call Setup Failure Reason | Enumeration | Classification of why media connection couldn't be established for a call. **Possible values:** **Missing FW Deep Packet Inspection Exemption Rule** - indicates that network equipment along the path likely prevented the media path from being established due to deep packet inspection rules, possibly due to proxy or firewall rules not being correctly configured. **Missing FW IP Block Exemption Rule** - indicates that network equipment along the path likely prevented the media path from being established to the Office 365 network, possibly due to proxy or firewall rules not being correctly configured to allow access to IP addresses and ports used for Skype for Business traffic. **Other** - indicates the media path for the call couldn't be established but the root cause couldn't be classified.  Not Media Failure - indicates no issue is detected with the establishment of the media path. | • Call setup failed due to an unknown media issue |
| Session Type | Enumeration **Possible values:** Conf, P2P | Indicates if the call session type was a meeting (Conf) or peer-to-peer call (P2P) scenario. **Example value:** Conf |  |
| CDR Response Reason | Enumeration **Possible values:** 0 or 200 = "OK"  410 = "MediaConnectivityErrors" 480 = "UserUnavailable" 487 = "PickupTimedOut"  603 = "CallDeclined"  All other CDR codes = "Other" | Provides the reason for a call session concluding, whether the call was successful or not, and allows for differentiation between incomplete calls (no answer, busy, declined) and failed calls (media establishment). 410 errors might not always correlate with a 'Failure' classification; due to identified exclusions, they might not be considered an impacting media failure. **Example value:** OK | • A value of "Other" implies response code isn't diagnostically useful outside of Microsoft's engineering teams |
| Session Id | String | Unique identifier for the session. A session represents communication between two endpoints, either user-user in peer-to-peer calls or user-server in group calls/meetings. |  |
| **DNS** |  |  |  |
| First DNS Suffix | String | DNS suffix associated with the network adapter reported by the first endpoint. Note this value might be reported for any type of network adapter. **Example value:** corp.contoso.com | • This value wasn't reported by the endpoint. |
| Second DNS Suffix | String | DNS suffix associated with the network adapter reported by the second endpoint. Note this value might be reported for any type of network adapter.**Example value:** corp.contoso.com | • This value wasn't reported by the endpoint. |
| Used DNS Resolve Cache | Boolean | True if endpoint used DNS cache to resolve media relay address, False otherwise. | • The endpoint didn't report this data. |
| First DNS Resolution Result | Boolean | The result of DNS resolution on the first endpoint during session establishment. If this value returns true, DNS resolution succeeded. | • Not all endpoints return these values. |
| Second DNS Resolution Result | Boolean | The result of DNS resolution on the second endpoint during session establishment. If this value returns true, DNS resolution succeeded. | • Not all endpoints return these values. |
| First DNS Error | String | Reports what result code (if any) was returned by the DNS lookup process on the first endpoint. **Example**: success | • Not all endpoints return these values. |
| Second DNS Error | String | Reports what result code (if any) was returned by the DNS lookup process on the second endpoint. **Example**: success | • Not all endpoints return these values. |
| **UserData** |  |  |  |
| First User ObjectId | String | The Active Directory object ID of the first endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| Second User ObjectId | String | The Active Directory object ID of the second endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| First MAC Address | String | The media access control (MAC) address of the first endpoint's network device. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| Second MAC Address | String | The media access control (MAC) address of the second endpoint's network device. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| First Sip Uri | String | The Session Initiation Protocol (SIP) URI of the first endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. | • Populated only for Skype for Business endpoints. • User doesn't have permissions to view EUII. |
| Second Sip Uri | String | The SIP URI of the first endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. | • Populated only for Skype for Business endpoints.• User doesn't have permissions to view EUII. |
| First Phone Number | String | The phone number of the first endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. The last four digits of PSTN numbers are always obfuscated in CQD irrespective of EUII viewing privileges.**Example value:** +1425555\*\*\*\* | • Populated only for PSTN endpoints. • User doesn't have permissions to view EUII. |
| Second Phone Number | String | The phone number of the second endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. The last four digits of PSTN numbers are always obfuscated in CQD irrespective of EUII viewing privileges.**Example value:** +1425555\*\*\*\* | • Populated only for PSTN endpoints.• User doesn't have permissions to view EUII. |
| First UPN | String | The user principal name (UPN) of the first endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. | • Not all UserTypes have UPNs; include the First UserType or First User ObjectId dimensions to learn more about these endpoints. |
| Second UPN | String | The user principal name (UPN) of the second endpoint's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. | • Not all UserTypes have UPNs; include the Second UserType or Second User ObjectId dimensions to learn more about these endpoints. |
| First Feedback Text | String | Verbatim feedback text, if any, provided by first endpoint's user at the end of a call. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| Second Feedback Text | String | Verbatim feedback text, if any, provided by second endpoint's user at the end of a call. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| First Client Endpoint Name | String | The machine name of the first endpoint. In VDI scenarios, this value reflects the endpoint that handled media. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| Second Client Endpoint Name | String | The machine name of the second endpoint. In VDI scenarios, this value reflects the endpoint that handled media. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. |  |
| First Endpoint Product Name | String | The product name of the first endpoint (either Skype for Business or Microsoft Teams). |  |
| Second Endpoint Product Name | String | The product name of the second endpoint (either Skype for Business or Microsoft Teams). |  |
| First UserType | Enumeration string | The type of user on the first endpoint. **Possible values:** User, Server, Anonymous, Application, PSTN, Voicemail, Unknown **Unknown** - the default value if UserType can't be determined based on the info received. **PSTN** - a PSTN User. **Anonymous** - a Teams user or Skype for Business visitor. **Application** - a bot. **User** - a Microsoft Entra User, can be either Skype for Business User or Teams User. **Server** - for conferences, at least one side is a server. **Voicemail** - the endpoint was answered by the voicemail service. |  |
| Second UserType | Enumeration string | The type of user on the second endpoint. **Possible values:** User, Server, Anonymous, Application, PSTN, Voicemail, Unknown **Unknown** - the default value if UserType can't be determined based on the info received. **PSTN** - a PSTN User. **Anonymous** - a Teams user or Skype for Business visitor. **Application** - a bot. **User** - a Microsoft Entra User, can be either Skype for Business User or Teams User. **Server** - for conferences, at least one side is server. **Voicemail** - the endpoint was answered by voicemail service. |  |
| Organizer ObjectId | String | The Active Directory object ID of the meeting organizer's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. | • User doesn't have permissions to view EUII. • Record is older than 28 days. |
| Organizer UPN | String | The user principal name (UPN) of the meeting organizer's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. | • User doesn't have permissions to view EUII. • Record is older than 28 days. |
| Organizer Sip Uri | String | The Session Initiation Protocol (SIP) URI of the meeting organizer's user. Only available for the past 28 days of data and only visible to users with roles allowing EUII access. | • Populated only for Skype for Business endpoints. • User doesn't have permissions to view EUII. • Record is older than 28 days. |
| PII Scrubbed | Boolean | Indicates if the end-user identifiable information was scrubbed from the record. This happens automatically after a record is 28 days old. |  |
| First Is VPN Combined | Boolean | Indicates if Teams determined the first endpoint was connected to a VPN when it received the stream, combining several detection criteria |  |
| Second Is VPN Combined | Boolean | Indicates if Teams determined the second endpoint was connected to a VPN when it received the stream, combining several detection criteria |  |
| **Devices** |  |  |  |
| First Capture Device Form Factor | Enumeration string | The form factor of the audio capture device (microphone) on the first endpoint. | • Not reported by the endpoint. |
| Second Capture Device Form Factor | Enumeration string | The form factor of the audio capture device (microphone) on the first endpoint. | • Not reported by the endpoint. |
| First Render Device Form Factor | Enumeration string | The form factor of the audio capture device (speakers) on the first endpoint. | • Not reported by the endpoint. |
| Second Render Device Form Factor | Enumeration string | The form factor of the audio capture device (speakers) on the first endpoint. | • Not reported by the endpoint. |
| **Video** |  |  |  |
| First Recv Resolution Height | Number (pixels) | Vertical resolution of the video stream received by the first endpoint. | • Stream isn't a video stream |
| Second Recv Resolution Height | Number (pixels) | Vertical resolution of the video stream received by the second endpoint. | • Stream isn't a video stream |
| First Recv Resolution Width | Number (pixels) | Horizontal resolution of the video stream received by the first endpoint. | • Stream isn't a video stream |
| Second Recv Resolution Width | Number (pixels) | Horizontal resolution of the video stream received by the second endpoint. | • Stream isn't a video stream |
| First Video Duration Seconds | Range (seconds) | Duration of the video stream received by the first endpoint, measured in seconds and displayed as a range. **Example value:** 254: [1000 - 1500] | • Not reported by the endpoint. |
| Second Video Duration Seconds | Range (seconds) | Duration of the video stream received by the second endpoint, measured in seconds and displayed as a range. **Example value:** 254: [1000 - 1500] | • Not reported by the endpoint. |
| First Recv Avg Freeze Duration | Range (seconds) | Average duration in seconds of received video freeze events on the first endpoint. | • Stream isn't a video stream |
| Second Recv Avg Freeze Duration | Range (seconds) | Average duration in seconds of received video freeze events on the second endpoint. | • Stream isn't a video stream |
| First Recv Rms Freeze Duration | Range (seconds) | Root-mean-square (RMS) in seconds of received video freeze events on the first endpoint. | • Stream isn't a video stream |
| Second Recv Rms Freeze Duration | Range (seconds) | Root-mean-square (RMS) in seconds of received video freeze events on the second endpoint. | • Stream isn't a video stream |
| First Recv Freeze Duration Percent | Range (percentage) | Percentage of the received video duration that was affected by freeze events on the first endpoint. | • Stream isn't a video stream |
| Second Recv Freeze Duration Percent | Range (percentage) | Percentage of the received video duration that was affected by freeze events on the second endpoint. | • Stream isn't a video stream |
| First Video Frame Rate Avg | Range (frames per second) | Average rate in frames-per-second of video on the first endpoint. | • Stream isn't a video stream |
| Second Video Frame Rate Avg | Range (frames per second) | Average rate in frames-per-second of video on the second endpoint. | • Stream isn't a video stream |
| First Video Bit Rate Avg | Range (kbps) | Average bit rate in kilobytes-per-second of video on the first endpoint. | • Stream isn't a video stream |
| Second Video Bit Rate Avg | Range (kbps) | Average bit rate in kilobytes-per-second of video on the second endpoint. | • Stream isn't a video stream |
| First Time To First Frame | Range (milliseconds) | The number of milliseconds between the video subscription and the first frame of the stream received by the first endpoint. | • Stream isn't a video stream |
| Second Time To First Frame | Range (milliseconds) | The number of milliseconds between the video subscription and the first frame of the stream received by the second endpoint. | • Stream isn't a video stream |
| First Video Bitrate Max | Range (kbps) | The maximum inbound video bitrate as received by the first endpoint at any point of the call. | • Stream isn't a video stream |
| Second Video Bitrate Max | Range (kbps) | The maximum inbound video bitrate as received by the second endpoint at any point of the call. | • Stream isn't a video stream |
| **PSTN** |  |  |  |
| First PSTN Country Region | String | If FirstIsCaller is true, First PSTN Country Region is the caller's country. If it's false, then Second PSTN Country region is the caller's country.**Example:** US |  |
| Second PSTN Country Region | String | If FirstIsCaller is false, Second PSTN Country Region is the caller's country. If it's true, then First PSTN Country region is the caller's country.**Example:** US |  |
| PSTN Trunk FQDN | String | FQDN is the fully qualified domain name (FQDN) of the Session Border Controller (SBC).**Example:** sbcgw.contoso.com |  |
| PSTN Carrier Name | String | The company that is authorized by regulatory agencies to operate a telecommunications system.**Example:** Colt | Direct Routing doesn't have a carrier. Only a calling plan has a carrier. |
| PSTN Call Type | String | This string combines the service type and call type.Service type:user -&gt; calling planbyot -&gt; direct routingconf -&gt; audio conferencingucap -&gt; voice appemergency -&gt; emergency numberCall type:In -&gt; inbound callOut -&gt; outbound callOut\_transfer -&gt; outbound call gets transferred to third personOut\_forward -&gt; outbound call gets forwarded to third personOut\_conf -&gt; outbound call with ad-hoc PSTN participant**Example:** ByotIn |  |
| PSTN Connectivity Type | String | PSTN connectivity type includes Direct Routing, Calling Plan, Operator Connect, or Teams Phone Mobile.**Example:** Direct Routing |  |
| PSTN Final SIP Code Phrase | String | The reason phrase corresponding to the SIP response code and Microsoft response code.**Example:** BYE |  |
| PSTN Call End Sub Reason | Int | A response code sent out from the Microsoft component that indicates specific actions that occurred.**Example:** 540000 |  |
| PSTN Event Type | String | An event type that provides telemetry.**Example:** End |  |
| PSTN Event Info Time | Date | The time in UTC format when an outbound call starts from the Microsoft network or an inbound call reaches the Microsoft network.**Example:** 2020-02-06 20:57:53.1750000 |  |
| PSTN MP Location | String | The Media Processor location shows the media path when in non-bypass mode.**Example:** USWE |  |
| PSTN Trunk Call Id | String | The SIP Call ID between the PSTN SIP Trunk and the SIP Proxy. Direct Routing customers can use this value to troubleshoot PSTN calling scenarios. Cross-reference the Trunk Call ID with the logs of the Session Border Controller or Media Gateway. |  |
| PSTN Trunk User Agent | String | The manufacturer, device type, and software revision for the PSTN SIP trunk's Session Border Controller or Media Gateway.**Example:** Cisco-SIPGateway/IOS-17.9.4a |  |
| PSTN Trunk SBC Version | String | The manufacturer, model name, and software revision for the PSTN SIP trunk's Session Border Controller or Media Gateway. **Example:** Cisco UBE/ISR4331/IOS-17.9.4a |  |
| PSTN Call End Reason | Int | A three-digit integer response code shows the final status of the call.  For more information about SIP call end reasons, see the [List of SIP response codes](https://www.wikipedia.org/wiki/List_of_SIP_response_codes). **Example:** 404 |  |
| Is PSTN Conferencing | Boolean | Indicates if a call or stream was involved in a PSTN conferencing scenario |  |
| Connectivity |  |  |  |
| First Reconnect Count | Range (Integer) | Indicates if the first endpoint was required to involve signaling to re-establish stream connectivity during a call. |  |
| Second Reconnect Count | Range (Integer) | Indicates if the second endpoint was required to involve signaling to re-establish stream connectivity during a call. |  |
| First Reconnect Success Count | Range (Integer) | Indicates the number of times the first endpoint successfully re-established media after a loss in connectivity requiring signaling. |  |
| Second Reconnect Success Count | Range (Integer) | Indicates the number of times the second endpoint successfully re-established media after a loss in connectivity requiring signaling. |  |
| First Transport Reconnected Count | Range (Integer) | Indicates if the first endpoint was required to re-establish transport layer connectivity. | • Shown for WebRTC-based endpoints only |
| Second Transport Reconnected Count | Range (Integer) | Indicates if the second endpoint was required to re-establish transport layer connectivity. | • Shown for WebRTC-based endpoints only |
| **Voice Apps (Preview)** |  | For this category, see [Auto Attendant & Call Queue Historical Report](aa-cq-report-historical) for more information.) |  |
| Auto Attendant Identity | String | Name of the resource account attached to the Auto Attendant. | • User doesn't have permissions to view EUII. • Record is older than 28 days. |
| Auto Attendant Chain Index | Integer | Order of the Auto Attendant in the call. |  |
| Auto Attendant Chain Start Time | String | The Auto Attendant call start time and date. |  |
| Auto Attendant Chain Duration Seconds | Integer | The duration of the call in the Auto Attendant, measured in seconds. |  |
| Auto Attendant Caller Action Count | Integer | Count of actions selected by the caller in an Auto Attendant during the call. |  |
| Auto Attendant Call Flow | String | Encapsulates the different states of the Auto Attendant call. |  |
| Auto Attendant Transfer Action | Enumeration | The call transfer target type. |  |
| Auto Attendant Call Result | Enumeration | Final call result with the Auto Attendant. |  |
| Auto Attendant Directory Search Method | Enumeration | The last address book search method used. |  |
| Auto Attendant Count | Integer | Number of Auto Attendants involved in the call. |  |
| Call Queue Identity | String | Name of the resource account attached to the Call Queue. | • User doesn't have permissions to view EUII. • Record is older than 28 days. |
| Call Queue Is Conference Mode | Boolean | If True, Call Queue is configured to use conference mode otherwise Call Queue is configured to use transfer mode. |  |
| Call Queue Agent Count | Integer | Number of agents configured in the queue. |  |
| Call Queue Agent Opt In Count | Integer | Number of configured agents that have opted into the queue. |  |
| Call Queue Target Type | Enumeration | The call redirection target type. |  |
| Call Queue Call Result | Enumeration | The Call Queue call final state. |  |
| Call Queue Final State Action | Enumeration | The Call Queue final action. |  |
| Call Queue Timed Out Time | Integer | The configured timed out value for the Call Queue. |  |
| Transferred from Call Queue Identity | String | Name of the resource account attached to the Call Queue that transferred the call. | • User doesn't have permissions to view EUII. • Record is older than 28 days. |
| Is Auto Attendant Involved | Boolean | If True, an Auto Attendant was involved in a given call or stream. |  |
| Is Call Queue Involved | Boolean | If True, a Call Queue was involved in a given call or stream. |  |
| **Meeting** |  |  |  |
| Scheduling Source App Id | String | The AppID of the first or third-party scheduling client that booked the meeting. | The scheduling client hasn't provided this parameter through its telemetry. |
| Total User Count | Integer | Total number of unique users associated with a query. |  |
| **Common** |  |  |  |
| First ACS Resource ID | String | Immutable resource identifier of the Azure Communication Service associated with the first endpoint. **Example:** 00000000-0000-0000-0000-000000000000 | Endpoint isn't using Azure Communication Services APIs |
| Second ACS Resource ID | String | Immutable resource identifier of the Azure Communication Service associated with the second endpoint. **Example:** 00000000-0000-0000-0000-000000000000 | Endpoint isn't using Azure Communication Services APIs |
| **Teams Events** |  |  |  |
| Teams Events Meeting Role | String | Identifies if the user was an Attendee in a Teams Event |  |
| Teams Events Attendee ECDN Name | String | Identifies the Enterprise Content Delivery Network (eCDN) to which the attendee was connected when viewing the event |  |
| Teams Events Attendee ECDN Script Load Error | String | Provides the reason and relevant URL for when script load errors are encountered by attendees. |  |
| Teams Events Attendee Stream Retry Count | Integer | The number of retries per minute that occurred while an attendee was watching an event stream. |  |
| Meeting Type | Enumeration string **Possible values:** Regular Meeting  TLE  TownHall  Webinar | Indicates whether a meeting was a regular Teams meeting, live event, event [optimized for a large audience](plan-events) (such as a town hall), or event with up to 1,000 attendees (such as a webinar). |  |
| Teams Events Time To Connect Media | Integer | The amount of time required for playback to begin after signaling has completed. |  |
| Teams Events Attendee Stream Buffering Rate | Range (Ratio) | Indicates the ratio of the stream spent waiting for video buffering versus the overall stream playback time. |  |
| Teams Events Attendee Average Stream Download Bit Rate | Integer (bits/second) | The length of the stream viewed by the user, in seconds. |  |
| **VDI** |  |  |  |
| First Client VDI Desktop Version | String | The VDI Teams client version of the first endpoint. **Example:** 24165.1414.2987.41 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI Desktop Version | String | The VDI Teams client version of the second endpoint. **Example:** 24165.1414.2987.41 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| First Client VDI Mode | String | The vdiMode value of the first endpoint, which communicates the virtualization provider and media optimization configuration. **Example:** 3100  First digit = `[1,2 for Citrix]``[3 for Omnissa]``[5 for AVD/Windows 365]``[7 for Amazon Workspaces]` Second digit = `[0 not configured for optimization]``[1 configured for WebRTC optimization]``[2 configured for Slimcore optimization]` | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI Mode | String | The vdiMode value of the second endpoint, which communicates the virtualization provider and media optimization configuration. **Example:** 3100  First digit = `[1,2 for Citrix]``[3 for Omnissa]``[5 for AVD/Windows 365]``[7 for Amazon Workspaces]` Second digit = `[0 not configured for optimization]``[1 configured for WebRTC optimization]``[2 configured for Slimcore optimization]` | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| First Client VDI Connected State | String | Indicates the connection status of VDI media optimization. A value of "connected" indicates media is successfully optimized on the client. **Example:** Connected | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI Connected State | String | Indicates the connection status of VDI media optimization. A value of "connected" indicates media is successfully optimized on the client. **Example:** Connected | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| First Client VDI Provider Version | String | The VDI provider client version of the first endpoint. **Example:** 24.2.0.187 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI Provider Version | String | The VDI provider client version of the second endpoint. **Example:** 24.2.0.187 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| First Client VDI Is Optimized | String | Indicates if the first endpoint's VDI client is operating in optimized mode. **Example:** VDI 2.0 Optimized | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI Is Optimized | String | Indicates if the second endpoint's VDI client is operating in optimized mode. **Example:** VDI 2.0 Optimized | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| First Client VDI OS Version | String | Version of the operating system running on the first VDI client endpoint. **Example:** 10.0.19045 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI OS Version | String | Version of the operating system running on the second VDI client endpoint. **Example:** 10.0.19045 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| First Client VDI Media Stack Version | String | Version of the SlimCore media engine running on the first VDI client endpoint. **Example:** 2024.14.1.1 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI Media Stack Version | String | Version of the SlimCore media engine running on the second VDI client endpoint. **Example:** 2024.14.1.1 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| First Client VDI Plugin Version | String | Version of the Teams plugin for the first VDI client endpoint. **Example:** 2024.15.1.1 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| Second Client VDI Plugin Version | String | Version of the Teams plugin for the second VDI client endpoint. **Example:** 2024.15.1.1 | • Endpoint isn't running on VDI.  • Data wasn't provided by the endpoint |
| **Datapair** |  |  |  |
| Network Connection Detail Pair | Enumerated pair **Possible values:** wifi : wifi  wifi : wired  Wired : wifi  Wired : Wired  MobileBB : MobileBB  MobileBB : Other  MobileBB : Tunnel  MobileBB : wifi  MobileBB : Wired  Other : Other  Other : wifi  Other : Wired  Tunnel : Tunnel  Tunnel : wifi  Tunnel : Wired  : MobileBB  : Other  : Tunnel  : wifi  : Wired  : | Pair of network connection detail for the first and second endpoint. | • Endpoint network connectivity type was unknown. This might happen if the call couldn't be established. |
| User Agent Category Pair | Enumerated pair | Pair of User Agent Category for first and second endpoint. **Example value:** AV-MCU : OC | • Endpoint user agent wasn't a known type |
| Is Server Pair | Enumerated pair **Possible values:** Client : Client  Client : Server  Server : Server | Pair of identification of first and second endpoints as either Client or Server. | no Blank values |
| Connectivity Ice Pair | Enumerated pair **Possible values:** DIRECT : DIRECT  DIRECT : FAILED  DIRECT : HTTP  FAILED : FAILED  FAILED : RELAY  HTTP : RELAY  :  : DIRECT  : FAILED  : HTTP  : RELAY | Pair of type of ICE connectivity used by each endpoint. | • ICE connectivity used by endpoint wasn't known or reported |
| OS Pair | Enumerated pair | Pair of the OS name and version for first and second endpoint. **Example value:** Windows 10 : Windows 10 | • OS name couldn't be parsed or wasn't reported by endpoint. |
| Tenant Id Pair | Enumerated pair | Pair of the tenant IDs for first and second endpoint. **Example value:** 00000000 — 0000 - 0000 - 0000 — 000000000000 : 00000000 — 0000 - 0000 - 0000 — 000000000000 | • The tenant identifier couldn't be determined. This might happen if endpoint is signed in to an on-premises Skype for Business Server deployment. |
| Building Name Pair | Enumerated pair | Pair of the building name for the first and second endpoint. | • The building name for an endpoint couldn't be determined. Missing values could be because the endpoint is located outside the corporate network, or is accessing the network from a site without a subnet mapping. **Example value:** Main Building : Branch Site Building |
| Inside Corp Pair | Enumerated pair **Possible values:** Inside : Inside  Inside : Outside  Outside : Outside | Pair showing if the endpoints were located inside or outside the corporate network based on the subnet mapping. |  |
| **Scenario** |  |  |  |
| Scenario Pair | Enumerated pair | Pair showing if the endpoints were located inside or outside the corporate network based on the subnet mapping and the network connection detail. **Note:** The pairs are separated by '--'. **Example value:** Client-Inside--Client-Inside-wifi | • The network connectivity type was unknown for either or both endpoints. |

## Measurements

Many Measurement values can also be used as filters. The following table lists the measurements currently available in CQD, shown in the order listed in the Query Editor

| Measure Name | Units | Description |
| --- | --- | --- |
| Total Stream Count | Number of streams | Number media streams regardless of type of media, including reliability/diagnostics streams that might not have a media type. |
| Total CDR Available Stream Count | Number of streams | Number of media streams with reliability/diagnostics information available. See [Call detail recording (CDR) in Skype for Business Server](/en-us/skypeforbusiness/manage/health-and-monitoring/call-detail-recording-cdr) |
| Total Media Failed Stream Count | Number of streams | Number of streams where either media path couldn't be established or didn't terminate normally. |
| Total Call Setup Failed Stream Count | Number of streams | Number of streams where media path couldn't be established between the endpoints at the start of the call. |
| Total Call Dropped Stream Count | Number of streams | Number of streams where media path didn't terminate normally. |
| Total Media Succeeded Stream Count | Number of streams | Number of streams where media path was established and terminated normally. |
| Total Call Setup Succeeded Stream Count | number of streams | Number of streams where media path could be established between the endpoints at the start of the call. |
| Total Call Setup Failure Percentage | Percentage | Percentage of all streams where media path couldn't be established between the endpoints at the start of the call. |
| Total Call Dropped Failure Percentage | Percentage | Percentage of successfully established streams where media path didn't terminate normally. |
| Total Short Call Count | Number of streams | Number of calls with a duration equal to or less than five seconds. |
| Total Answer Seizure Ratio | Ratio | Ratio of calls with duration less than 5 seconds over the total number of calls. |
| Total Short Call Percentage | Percentage | Percentage of total calls less than 1 minute long. |
| Total Media Failure Percentage | Percentage | Percentage of all streams where either media path couldn't be established or didn't terminate normally. |
| Media Failed Due To Firewall DPI Stream Count | Number of streams | Number of streams that failed to be established due to network equipment blocking access due to deep packet inspection not allowing Skype for Business traffic. These failures typically indicate a proxy, firewall, or other network security device isn't correctly configured. These devices might be blocking access to the IP address and ports that are used by Skype for Business in Microsoft 365 or Office 365. |
| Firewall DPI Media Failure Percentage | Percentage | Percentage of streams that failed to be established due to network equipment blocking access due to deep packet inspection not allowing Skype for Business traffic. These failures typically indicate a proxy, firewall, or other network security device isn't correctly configured. These devices might be blocking access to the IP address and ports that are used by Skype for Business in Microsoft 365 or Office 365. |
| Media Failed Due To Firewall IP Blocked Stream Count | Number of streams | Number of streams that failed to be established due to network equipment blocking access to Skype for Business servers. These failures typically indicate a proxy, firewall, or other network security device isn't correctly configured. These devices might be blocking access to the IP address and ports that are used by Skype for Business in Microsoft 365 or Office 365. |
| Firewall IP Blocked Media Failure Percentage | Percentage | Percentage of streams that failed to be established because network equipment blocked access to Skype for Business servers. These failures typically indicate a proxy, firewall, or other network security device isn't correctly configured. These devices might be blocking access to the IP address and ports that are used by Skype for Business in Microsoft 365 or Office 365. |
| Media Failed Due To Other Stream Count | Number of streams | Number of streams where media path couldn't be established between the endpoints due to an undetermined/unclassified reason. |
| Other Media Failure Percentage | Percentage | Percentage of streams where media path couldn't be established between the endpoints due to an undetermined/unclassified reason. |
| Total Call Count | Number of calls | Number of distinct calls, either as peer-to-peer calls or call legs within a conference. |
| Total CDR Available Call Count | Number of streams | Total number of calls with reliability/diagnostics information available. There's an up to 0.2% error for this measure. See note below for details. |
| Total Media Failed Call Count | Number of streams | Number of calls where media path couldn't be established between the endpoints. There's an up to 0.2% error for this measure. See note below for details. |
| Audio Stream Count | Number of streams | Number of audio streams. |
| Audio Poor Stream Count | Number of streams | Number of audio streams classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Good Stream Count | Number of streams | Number of audio streams classified as good based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Unclassified Stream Count | Number of streams | Number of audio streams that didn't have sufficient data to be classified as good or poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Unclassified streams are omitted from 'Poor Percentage' calculations. |
| Audio Poor Percentage | Percentage | Percentage of classified audio streams that were classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio OnePercent PacketLoss Count | Number of streams | Number of audio streams with packet loss greater than 1%. |
| Audio OnePercent PacketLoss Percentage | Percentage | Percentage of all audio streams with packet loss greater than 1%. |
| Audio Poor Due To Jitter Count | Number of streams | Number of audio streams where the jitter metric exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Poor Due To PacketLoss Count | Number of streams | Number of audio streams where the packet loss metric exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard) |
| Audio Poor Due To Degradation Count | Number of streams | Number of audio streams where the degradation metric exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Poor Due To RoundTrip Count | Number of streams | Number of audio streams where the round trip exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Poor Due To ConcealedRatio Count | Number of streams | Number of audio streams where the concealed ratio exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio SLA Good Call Count | Number of calls | Number of audio calls within scope of the Skype for Business Voice Quality SLA ([Volume Licensing for Microsoft Products and Online Services](https://go.microsoft.com/fwlink/?linkid=2102975)) classified as meeting the network performance targets. |
| Audio SLA Poor Call Count | Number of calls | Number of audio calls within scope of the Skype for Business Voice Quality SLA ([Volume Licensing for Microsoft Products and Online Services](https://go.microsoft.com/fwlink/?linkid=2102975)) classified as not meeting the network performance targets. |
| Audio SLA Call Count | Number of calls | Number of audio calls within scope of the Skype for Business Voice Quality SLA ([Volume Licensing for Microsoft Products and Online Services](https://go.microsoft.com/fwlink/?linkid=2102975)). |
| Audio SLA Good Call Percentage | Percentage | Percentage of audio calls within scope of the Skype for Business Voice Quality SLA ([Volume Licensing for Microsoft Products and Online Services](https://go.microsoft.com/fwlink/?linkid=2102975)) that were classified as meeting the network performance targets. |
| Audio Good Call Stream Count | Number of streams | Number of audio streams where both audio streams in the call (call-leg) aren't classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Poor Call Stream Count | Number of streams | Number of audio streams where at least one audio stream in the call (call-leg) was classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Unclassified Call Stream Count | Number of streams | Number of audio streams where both audio streams in the call (call-leg) couldn't be classified due to missing network metrics. |
| Audio Poor Call Level Percentage | Percentage | Percentage of all audio streams where at least one audio stream in the call (call-leg) was classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Call Count | Number | Number of calls involving audio. There's an up to 0.2% error for this measure. See note below for details. |
| Audio Poor Call Count | Number | Number of calls involving audio classified as poor. There's an up to 0.2% error for this measure. See note below for details. |
| Audio Good Call Count | Number of calls | Number of calls involving audio classified as good. There's an up to 0.2% error for this measure. See notes below for details. |
| Audio Unclassified Call Count | Number of calls | Number of calls involving audio that couldn't be classified Good or Poor. Unclassified calls are omitted from 'Poor Call Percentage' calculations. There's an up to 0.2% error for this measure. See note below for details. |
| Audio Poor Call Percentage | Percentage of calls | Percentage of classified calls involving audio classified as poor. There's an up to 0.2% error for this measure. See note below for details. |
| First Noise Suppression Model Download Failure Count | Number of streams | Number of outbound audio streams where First endpoints failed to download the noise suppression model successfully. |
| Second Noise Suppression Model Download Failure Count | Number of streams | Number of outbound audio streams where Second endpoints failed to download the noise suppression model successfully. |
| First Noise Suppression Model Download Failure Percentage | Percentage of streams (Decimal) | Percentage of outbound audio streams where First endpoints failed to download the noise suppression model successfully. |
| Second Noise Suppression Model Download Failure Percentage | Percentage of streams (Decimal) | Percentage of outbound audio streams where Second endpoints failed to download the noise suppression model successfully. |
| AppSharing Stream Count | Number of streams | Number of RDP-based application sharing streams. |
| AppSharing Poor Due To SpoiledTilePercentTotal Count | Number of streams | Number of application sharing streams where the spoiled tile percent total metric exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| AppSharing Poor Due To RelativeOneWayAverage Count | Number of streams | Number of application sharing streams where the relative one-way average metric exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| AppSharing Poor Due To RDPTileProcessingLatencyAverage Count | Number of streams | Number of application sharing streams where the RDP tile processing latency average exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| AppSharing Poor Stream Count | Number of streams | Number of application sharing streams classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| AppSharing Good Stream Count | Number of streams | Number of application sharing streams classified as good based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| AppSharing Unclassified Stream Count | Number of streams | Number of application sharing streams that didn't have sufficient data to be classified as good or poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Unclassified streams are omitted from 'Poor Percentage' calculations. |
| AppSharing Poor Percentage | Percentage | Percentage of classified application sharing streams that were classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Video Stream Count | Number of streams | Number of video streams. |
| Video Poor Due To VideoPostFecplr Count | Number of streams | Number of video streams where the Video Post Fec plr exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Video Poor Due To VideoLocalFrameLossPercentageAvg Count | Number of streams | Number of video streams where the Video Local Frame Loss Percentage Avg exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Video Poor Due To VideoFrameRateAvg Count | Number of streams | Number of Video streams where the Video Frame Rate Avg exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Video Poor Due to Freeze Count | Number of streams | Number of main video streams where the Video Freeze metric exceeds thresholds listed here. [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). This field is specific to Microsoft Teams only |
| Video Poor Stream Count | Number of streams | Number of video streams classified as poor based on network metrics listed here [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Video Good Stream Count | Number of streams | Number of video streams classified as good based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Video Unclassified Stream Count | Number of streams | Number of video streams that didn't have sufficient data to be classified as good or poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Unclassified streams are omitted from 'Poor Percentage' calculations. |
| Video Poor Percentage | Percentage | Percentage of classified video streams that were classified as poor based on network metrics listed here [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Video Call Count | Number of calls | Number of calls involving video. There's an up to 0.2% error for this measure. See note below for details. |
| Video Poor Percentage Due to Freeze | Percentage | Percentage of main video streams that were classified as poor based on the Video Poor metric Due to Freeze listed here [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). This field is specific to Microsoft Teams only |
| VBSS Stream Count | Number of streams | Number of video-based-screen sharing streams. |
| VBSS Poor Due To VideoPostFecplr Count | Number of streams | Number of video-based-screen-sharing streams where the Video Post Fec plr exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| VBSS Poor Due To VideoLocalFrameLossPercentageAvg Count | Number of streams | Number of video-based-screen-sharing streams where the Video Local Frame Loss Percentage Avg exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| VBSS Poor Due To VideoFrameRateAvg Count | Number of streams | Number of video-based-screen-sharing streams where the Video Frame Rate Avg exceeds thresholds listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| VBSS Poor Stream Count | Number of streams | Number of video-based-screen-sharing streams classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| VBSS Good Stream Count | Number of streams | Number of video-based-screen-sharing streams classified as good based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| VBSS Unclassified Stream Count | Number of streams | Number of video-based-screen-sharing streams that didn't have sufficient data to be classified as good or poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). Unclassified streams are omitted from 'Poor Percentage' calculations. |
| VBSS Poor Percentage | Percentage | Percentage of classified video-based-screen-sharing streams that classified as poor based on network metrics listed here: [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). |
| Audio Device Failure Percentage | Percentage | Percentage of all audio streams in which an audio capture or render device failure is detected. |
| Audio Device General Failure Percentage | Percentage | Percentage of all audio streams in which a general hardware failure on an audio device is detected. |
| No Mic Device Enumerated Failure Count | Number of streams | Total number of audio streams in which no audio capture devices were detected. |
| No Mic Device Enumerated Failure Percentage | Percentage | Percentage of all audio streams in which no audio capture devices were detected. |
| Mic Initialization Failure Count | Number of streams | Total number of audio streams in which a failure occurred during the hardware initialization of the microphone device. |
| Mic Initialization Failure Percentage | Percentage | Percentage of all audio streams in which a failure occurred during the hardware initialization of the microphone device. |
| Speaker Initialization Failure Count | Number of streams | Total number of audio streams in which a failure occurred during the hardware initialization of the audio render device. |
| Speaker Initialization Failure Percentage | Percentage | Percentage of all audio streams in which a failure occurred during the hardware initialization of the audio render device. |
| No Speaker Device Enumerated Failure Count | Number of streams | Total number of audio streams in which no audio render devices were detected. |
| No Speaker Device Enumerated Failure Percentage | Percentage | Percentage of all audio streams in which no audio render devices were detected. |
| Mic Is Silent Failure Count | Number of streams | Total number of audio streams in which no audio is detected from the microphone while unmuted. |
| Mic Is Silent Failure Percentage | Percentage | Percentage of all audio streams in which no audio is detected from the microphone while unmuted. |
| Audio Device Failure Count | Number of streams | Number of streams with either a mic or speaker failure. |
| First Audio Device General Failure Rate | Percentage | Percentage of all audio streams with a general audio hardware failure on the first endpoint. |
| Second Audio Device General Failure Rate | Percentage | Percentage of all audio streams with a general audio hardware failure on the second endpoint. |
| First Mic Device Failure Rate | Percentage | Percentage of all audio stream in which an audio capture device failure is detected on the first endpoint. |
| Second Mic Device Failure Rate | Percentage | Percentage of all audio stream in which an audio capture device failure is detected on the second endpoint. |
| First Speaker Device Failure Rate | Percentage | Percentage of all audio stream in which an audio render device failure is detected on the first endpoint. |
| Second Speaker Device Failure Rate | Percentage | Percentage of all audio stream in which an audio render device failure is detected on the second endpoint. |
| Avg Call Duration | Seconds | Average duration of streams in seconds. |
| Total Audio Stream Duration (Minutes) | Minutes | Total audio stream duration in minutes in the selected time range. |
| Total Stream Duration (Minutes) | Minutes | The total duration of streams as measured in minutes based on the selected filters. Can be filtered to specific Media Types and Stream Directions for increased precision. |
| First Feedback Rating Avg | User rating (1-5) | Average rating of streams reported by the user using the first endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| Second Feedback Rating Avg | User rating (1-5) | Average rating of streams reported by the user using the second endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| First Feedback Rating Count | Number of rated streams | Number of streams rated by the user using the first endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| Second Feedback Rating Count | Number of rated streams | Number of streams rated by the user using the second endpoint. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| First Feedback Rating Poor Count | Number of rated streams | Number of streams rated by the user using the first endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| Second Feedback Rating Poor Count | Number of rated streams | Number of streams rated by the user using the second endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| First Feedback Rating Poor Percentage | Number of rated streams | Percentage of all rated streams that are rated by the user using the first endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| Second Feedback Rating Poor Percentage | Number of rated streams | Percentage of all rated streams that are rated by the user using the second endpoint as either 1 or 2. Calls are rated from 1-5 and the rating is applied to all streams of the call. |
| First Feedback Token Audio Issue Count | Number rated streams | Number of streams where user using the first endpoint indicated an issue with audio. |
| Second Feedback Token Audio Issue Count | Number rated streams | Number of streams where user using the second endpoint indicated an issue with audio. |
| First Feedback Token Video Issue Count | Number of rated streams | Number of streams where user using the first endpoint indicated an issue with video. |
| Second Feedback Token Video Issue Count | Number of rated streams | Number of streams where user using the second endpoint indicated an issue with video. |
| Avg First Echo Percent Mic In | Percentage | Average percentage of time during the stream that the first endpoints detected echo in the audio from the capture or microphone device prior to echo cancellation. |
| Avg Second Echo Percent Mic In | Percentage | Average percentage of time during the stream that the second endpoints detected echo in the audio from the capture or microphone device prior to echo cancellation. |
| Avg First Echo Percent Send | Percentage | Average percentage of time during the stream that the first endpoints detected echo in the audio from the capture or microphone device after echo cancellation. |
| Avg Second Echo Percent Send | Percentage | Average percentage of time during the stream that the second endpoints detected echo in the audio from the capture or microphone device after echo cancellation. |
| Avg First Initial Signal Level RMS | Range (Decibels) | Average of the root-mean-square (RMS) of the received signal for the first 30 seconds of the call for the first endpoint. See [2.2.1.28.1 Child Elements](/en-us/openspecs/office_protocols/ms-qoe/3c78f383-73fe-49f6-89cb-614e7aa8b2e7) for more information |
| Avg Second Initial Signal Level RMS | Range (Decibels) | Average of the root-mean-square (RMS) of the received signal for the first 30 seconds of the call for the second endpoint. |
| Avg First RxAGC Signal Level | Range (Decibels) | Average signal level received at the automatic gain control for the first inbound audio stream. |
| Avg Second RxAGC Signal Level | Range (Decibels) | Average signal level received at the automatic gain control for the second inbound audio stream. |
| Avg First RxAGC Noise Level | Range (Decibels) | Average noise level received at the automatic gain control for the first inbound audio stream. |
| Avg Second RxAGC Noise Level | Range (Decibels) | Average noise level received at the automatic gain control for the second inbound audio stream. |
| Avg First Render Loopback Signal Level | Range (Decibels) | Average level of first speaker loopback signal (after any device offload effects are applied). |
| Avg Second Render Loopback Signal Level | Range (Decibels) | Average level of second speaker loopback signal (after any device offload effects are applied). |
| Avg First Audio Send Signal Level | Decibels | Average energy level of sent audio for audio classified as mono speech, or left channel of stereo speech sent by first endpoints. |
| Avg Second Audio Send Signal Level | Decibels | Average energy level of sent audio for audio classified as mono speech, or left channel of stereo speech sent by second endpoints. |
| Avg First Audio Received Signal Level | Decibels | Average energy level of received audio for audio classified as mono speech, or left channel of stereo speech by the first endpoints. |
| Avg Second Audio Received Signal Level | Decibels | Average energy level of received audio for audio classified as mono speech, or left channel of stereo speech by the second endpoints. |
| Avg First Audio Send Noise Level | Decibels | Average energy level of sent audio for audio classified as mono noise or left channel of stereo noise by the first endpoints. |
| Avg Second Audio Send Noise Level | Decibels | Average energy level of sent audio for audio classified as mono noise or left channel of stereo noise by the second endpoints. |
| Avg First Audio Received Noise Level | Decibels | Average energy level of received audio for audio classified as mono noise or left channel of stereo noise by the first endpoints. |
| Avg Second Audio Received Noise Level | Decibels | Average energy level of received audio for audio classified as mono noise or left channel of stereo noise by the second endpoints. |
| First Audio Echo BAD\_TIMESTAMP Count | Number of streams | Number of streams where the echo is caused by bad device timestamps from the first endpoints that limited echo cancellation in audio sent. |
| First Audio Echo POSTAEC\_ECHO Count | Number of streams | Number of streams where the high echo is detected after echo cancellation for audio sent by the first endpoints. |
| First Audio Echo EVENT\_ANLP Count | Number of streams | Number of streams where the first endpoints detected noise in the captured audio that limited echo cancellation in audio sent. |
| First Audio Echo EVENT\_DNLP Count | Number of streams | Number of streams where the first endpoints detected noise in the captured audio that limited echo cancellation in audio sent. |
| First Audio Echo MIC\_CLIPPING Count | Number of streams | Number of streams where the first endpoints detected clipping in the captured audio that limited echo cancellation in audio sent. |
| First Audio Echo BAD\_STATE Count | Number of streams | Number of streams where the first endpoints detected issues with the internal state that limited echo cancellation in audio sent. |
| Second Audio Echo BAD\_TIMESTAMP Count | Number of streams | Number of streams where the echo is caused by bad device timestamps from the second endpoints that limited echo cancellation in audio sent. |
| Second Audio Echo POSTAEC\_ECHO Count | Number of streams | Number of streams where the high echo is detected after echo cancellation for audio sent by the second endpoints. |
| Second Audio Echo EVENT\_ANLP Count | Number of streams | Number of streams where the second endpoints detected noise in the captured audio that limited echo cancellation in audio sent. |
| Second Audio Echo EVENT\_DNLP Count | Number of streams | Number of streams where the second endpoints detected noise in the captured audio that limited echo cancellation in audio sent. |
| Second Audio Echo MIC\_CLIPPING Count | Number of streams | Number of streams where the second endpoints detected clipping in the captured audio that limited echo cancellation in audio sent. |
| Second Audio Echo BAD\_STATE Count | Number of streams | Number of streams where the second endpoints detected issues with the internal state that limited echo cancellation in audio sent. |
| Avg Audio Degradation | Mean Opinion Score (0-5) | Average Network Mean Opinion Score degradation for streams. Represents how much the network loss and jitter impact the quality of received audio. |
| Avg Jitter | Milliseconds | Average network jitter for streams in milliseconds. This jitter metric is inter-arrival jitter as reported in the generic network payload, and is reported for all stream types. |
| Avg Jitter Max | Milliseconds | Maximum network jitter for streams in milliseconds. This jitter metric is inter-arrival jitter as reported in the generic network payload, and is reported for all stream types. |
| Avg Packet Loss Rate | Ratio | Average of average percentage of packets lost computed using 5 second interval for streams. 0.1 indicates 10% packet loss. |
| Avg Packet Loss Rate Max | Ratio | Average of maximum percentage of packets lost during any 5 second interval for streams. 0.1 indicates 10% packet loss. |
| Avg Send Listen MOS | Number | Average of the prediction of the Wideband Listening Quality Mean Opinion Score (MOS-LQ) of the audio stream that is being sent from the user. |
| Avg Overall Avg Network MOS | Mean Opinion Score (0-5) | Average or average network Mean Opinion Score for streams. Represents the average predicted quality of received audio factoring in network loss, jitter, and codec. |
| Avg Ratio Concealed Samples | Ratio | Average of average ratio of the number of audio frames with samples generated by packet loss concealment to the total number of audio frames for streams. 0.1 indicates 10% of frames contained concealed samples. |
| Avg Conceal Ratio Max | Ratio | Average of the maximum ratios of the number of audio frames with samples generated by packet loss concealment to the total number of audio frames for streams. 0.1 indicates 10% of frames contained concealed samples. |
| Avg Ratio Stretched Samples | Ratio | Average of average ratio of the number of audio frames with samples that are stretched to compensate for jitter or loss to the total number of audio frames for streams. 0.1 indicates 10% audio frames contained stretched samples. |
| Avg Healer Packet Drop Ratio | Range (Ratio) | Average ratio of audio packets dropped by healer over total number of audio packets received by healer. |
| Avg Healer FEC Packet Used Ratio | Range (Ratio) | Average ratio of used FEC packets over total number of received FEC packets. |
| Avg Round Trip | Milliseconds | Average of average network propagation round-trip time computed as specified in RFC3550 in milliseconds for streams. |
| Avg Round Trip Max | Milliseconds | Average of maximum network propagation round-trip time computed as specified in RFC3550 in milliseconds for streams. |
| Avg Packet Utilization | Number of packets | Average number of Real-Time Transport Protocol (RTP) packets sent per second in the session. |
| Avg Network Jitter | Milliseconds | Average of network jitter computed over 20-second windows during the session. This metric is contained in the audio payload of the QoE. Stream types other than audio don't report a value for this measurement. |
| Avg Network Jitter Max | Milliseconds | Average of maximum network jitter in milliseconds computed over 20-second windows during the session. This metric is contained in the audio payload of the QoE. Stream types other than audio don't report a value for this measurement. |
| Avg Network Jitter Min | Milliseconds | Average of minimum network jitter values in milliseconds computed over 20-second windows during the session for streams. This metric is contained in the audio payload of the QoE. Stream types other than audio don't report a value for this measurement. |
| Avg Jitter Buffer Size | Milliseconds | Average size of jitter buffer during session. This metric is contained in the audio payload of the QoE. Stream types other than audio don't report a value for this measurement. |
| Avg Jitter Buffer Size Max | Milliseconds | Maximum size of jitter buffer during session. This metric is contained in the audio payload of the QoE. Stream types other than audio don't report a value for this measurement. |
| Avg Jitter Buffer Size Min | Milliseconds | Minimum size of jitter buffer during session. This metric is contained in the audio payload of the QoE. Stream types other than audio don't report a value for this measurement. |
| Avg Relative OneWay | Milliseconds | Average computed relative one way delay of the peer. |
| Avg Relative OneWay Max | Milliseconds | Average of the maximum relative one-way delay of the peer. |
| Avg Relative OneWay Gap Occurrences | Milliseconds | Average number of instances of gaps in the relative one way delay of the peer. |
| Avg Relative OneWay Gap Density | Milliseconds | Average density of gaps in the relative one way delay of the peer. |
| Avg Relative OneWay Gap Duration | Number (Milliseconds) | Average duration of gaps in the relative one way delay of the peer. |
| Avg Audio Post FECPLR | Ratio | Average of packet loss rate after FEC is applied for aggregated across all audio streams and codecs for streams. |
| Avg Video Post FECPLR | Ratio | Average of packet loss rate after FEC is applied for aggregated across all video streams and codecs for streams. |
| Avg Video Local Frame Loss Percentage | Percentage | Average percentage of video frames lost as displayed to the user for streams. This includes frames recovered from network losses. |
| Avg Video Received Frame Rate Average | Frames per second | Average of average frames per second received for all video streams computed over the duration of the session for streams. |
| Avg Video Low Frame Rate Call Percent | Percentage | Average of percentage of time of the call where frame rate is less than 7.5 frames per second for streams. |
| Avg Video Packet Loss Rate | Ratio | Average of average fraction of packets lost, as specified in [RFC3550](https://tools.ietf.org/html/rfc3550), computed over the duration of the session for streams. |
| Avg Video Frame Rate | Frames per second | Average frames per second received for a video stream, computed over the duration of the session. Values grouped by range. |
| Avg Video Dynamic Capability Percent | Milliseconds | Average of percentage of time that the client is running &lt; 70% expected video processing capability for this type of CPU for streams. |
| Avg AppSharing Spoiled Tile Percent Total | Milliseconds | Average of percentage of tiles which are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer) for streams. Discarded tiles might be caused by bandwidth restrictions between client and server. |
| Avg AppSharing Relative OneWay | Seconds | Average of average relative one-way delay between the endpoints in seconds for application sharing streams. |
| Avg AppSharing RDP Tile Processing Latency | Milliseconds | Average of average latency in milliseconds processing tiles on the RDP Stack at the conferencing server for streams. |
| Avg First Device Capture Not Functioning Event Ratio | Ratio | Average of the fraction of the call that the first endpoint detects the capture device isn't working properly. |
| Avg Second Device Capture Not Functioning Event Ratio | Ratio | Average of the fraction of the call that the second endpoint detects the capture device isn't working properly. |
| Avg First Device Render Not Functioning Event Ratio | Ratio | Average of the fraction of the call that the first endpoint detects the render device isn't working properly. |
| Avg Second Device Render Not Functioning Event Ratio | Ratio | Average of the fraction of the call that the second endpoint detects the render device isn't working properly. |
| Avg First Mic Glitch Rate | Number of glitches | Average First Mic Glitch Rate (glitches per 5 minutes for the endpoint microphone) for the stream. |
| Avg Second Mic Glitch Rate | Number of glitches | Average Second Mic Glitch Rate (glitches per 5 minutes for the endpoint microphone) for the stream. |
| Avg First Speaker Glitch Rate | Number of glitches | Average First Speaker Glitch Rate (glitches per 5 minutes for the endpoint loudspeaker) for the stream. |
| Avg Second Speaker Glitch Rate | Number of glitches | Average Second Speaker Glitch Rate (glitches per 5 minutes for the endpoint loudspeaker) for the stream. |
| Avg First Send Mute Percent | Percentage | Average of the percentage of the audio stream that's muted from the first endpoint. |
| Avg Second Send Mute Percent | Percentage | Average of the percentage of the audio stream that's muted from the second endpoint. |
| Avg First System CPU Resource Usage Average | Percentage | The average of the system's average overall CPU usage measured for the first endpoint. |
| Avg Second System CPU Resource Usage Average | Percentage | The average of the system's average overall CPU usage measured for the second endpoint. |
| Avg First Process Memory Resource Usage Average | Percentage | The average of the average memory usage by the Teams process measured for the first endpoint. |
| Avg Second Process Memory Resource Usage Average | Percentage | The average of the average memory usage by the Teams process measured for the second endpoint. |
| Avg First System CPU Resource Usage Max | Percentage | The average of the maximum values of the system's overall CPU usage measured for the first endpoint. |
| Avg Second System CPU Resource Usage Max | Percentage | The average of the maximum values of the system's overall CPU usage measured for the second endpoint. |
| Avg First Process Memory Resource Usage Max | Percentage | The average of the maximum value of the memory usage by the Teams process measured for the first endpoint. |
| Avg Second Process Memory Resource Usage Max | Percentage | The average of the maximum value of the memory usage by the Teams process measured for the second endpoint. |
| Avg First System Memory Resource Usage Average | Percentage | The average of the system's average overall memory usage measured for the first endpoint. |
| Avg Second System Memory Resource Usage Average | Percentage | The average of the system's average overall memory usage measured for the second endpoint. |
| Avg First System Memory Resource Usage Max | Percentage | The average of maximum values of the system's overall memory usage measured for the first endpoint. |
| Avg Second System Memory Resource Usage Max | Percentage | The average of maximum values of the system's overall memory usage measured for the second endpoint. |
| Avg First Process CPU Resource Usage Average | Percentage | The average of the average CPU usage by the Teams process measured for the first endpoint. |
| Avg Second Process CPU Resource Usage Average | Percentage | The average of the average CPU usage by the Teams process measured for the second endpoint. |
| Avg First Process CPU Resource Usage Max | Percentage | The average of the maximum values of the CPU usage by the Teams process measured for the first endpoint. |
| Avg Second Process CPU Resource Usage Max | Percentage | The average of the maximum values of the CPU usage by the Teams process measured for the second endpoint. |
| First User Count | Number | Number of unique or distinct first endpoint users. Only available for the past 28 days of data. There's an up to 0.2% error for this measure. See note below for details. |
| Second User Count | Number | Number of unique or distinct second endpoint users. Only available for the past 28 days of data. There's an up to 0.2% error for this measure. See note below for details. |
| Avg First Device Glitches Event Ratio | Percentage | Average fraction of the calls that the first endpoint detected glitches or gaps in the media played or captured that caused poor quality of the media being sent or received. |
| Avg Second Device Glitches Event Ratio | Percentage | Average fraction of the call that the second endpoint detected glitches or gaps in the media played or captured that caused poor quality of the media being sent or received. |
| First Device Glitches Event Count | Number | Number of streams where the first endpoint detected significant glitches or gaps in the media played or captured that caused poor quality of the media being sent or received. |
| Second Device Glitches Event Count | Number | Number of streams where the second endpoint detected significant glitches or gaps in the media played or captured that caused poor quality of the media being sent or received. |
| PSTN Total Attempts Count | Number of calls | Total attempted calls, including successful calls and failed calls in the selected time range. There's an up to 0.2% error for this measure. See note below for details. |
| PSTN Total Connected Count | Number of calls | Total successfully connected calls in the selected time range. There's an up to 0.2% error for this measure. See note below for details. |
| PSTN Inbound Attempts Count | Number of calls | Total inbound attempted calls, including successful calls and failed calls in the select time range. There's an up to 0.2% error for this measure. See note below for details. |
| PSTN Inbound Connected Count | Number of calls | Total inbound successfully connected calls in the selected time range. There's an up to 0.2% error for this measure. See note below for details. |
| PSTN Outbound Attempts Count | Number of calls | Total outbound attempted calls, including successful calls and failed calls in the selected time range. There's an up to 0.2% error for this measure. See note below for details. |
| PSTN Outbound Connected Count | Number of Calls | Total outbound successfully connected calls in the selected time range. There's an up to 0.2% error for this measure. See note below for details. |
| PSTN Total Minutes | Minutes | Total minute usage in the selected time range. |
| PSTN Inbound Total Minutes | Minutes | Total inbound minute usage in the selected time range. |
| PSTN Outbound Total Minutes | Minutes | Total outbound minute usage in the selected time range. |
| PSTN Active User Count | Number of users | The number of users who made at least one connected call during that day. |
| PSTN Average Call Duration | Minutes | The average duration of all connected calls in the selected time range. Normally, a 1:1 PSTN call is four to five minutes. However, this average can differ for each company. |
| PSTN Total Inbound Concurrent Call Count | Number of calls | Maximum number of simultaneous active inbound calls in a minute. |
| PSTN Total Outbound Concurrent Call Count | Number of calls | Maximum number of simultaneous active outbound calls in a minute. |
| P50 Latency | Milliseconds | 50% of the requests should be faster than given latency. |
| P50 Jitter | Milliseconds | 50% of the requests should be faster than given Jitter. |
| P50 Packet Loss Rate | Percentage | 50% of the requests should have lower than the given Packet Loss Rate. |
| PSTN Outgoing Post Dial Delay | Milliseconds | The delay that occurs on outgoing calls measured from the time a number has been dialed until the caller or called party hears ringing. |
| PSTN Incoming Post Dial Delay | Milliseconds | The time or delay that occurs on incoming calls measured from the time a number has been dialed until the caller or called party hears ringing. |
| PSTN Calls Affected By NER | Number of calls | Number of PSTN calls considered unsuccessful according to the Network Effectiveness Ratio (NER). |
| PSTN NER Good Percentage | Percentage | The NER measures the ability of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.NER = (Answered calls + User Busy + Ring no Answer + Terminal Reject Seizures) / Total Attempt Calls x 100. There's an up to 0.2% error for this measure. See note below for details. |
| Avg Auto Attendant Chain Duration Seconds | Integer | The average duration that users spend in the Auto Attendant, measured in seconds. |
| Avg Call Queue Duration Seconds | Integer | The average duration that users are waiting for a Call Queue to be answered by an agent, measured in seconds. |
| Total Teams Events Stream Count | Integer | The total number of Teams Events streams. |
| Teams Events ECDN Error Stream Count | Integer | The total number of Teams Events streams that failed to establish due to eCDN errors. |
| Teams Events Setup Failure Stream Count | Integer | The number or Teams Events streams that failed to establish during media setup. |
| Teams Events Setup Succeeded Stream Count | Integer | The number or Teams Events streams that successfully established. |
| Teams Events Stream Setup Failure Percentage | Percentage | The percentage of Teams Events streams that failed to establish during media setup. |
| Detected Inbound Network Problem True Count | Integer | Number of instances that there's high confidence that a First-to-Second media stream might be impacted due to the inbound network. |
| Detected Inbound Network Problem False Count | Integer | Number of instances that there isn't high confidence that a First-to-Second media stream might be impacted due to the inbound network. |
| Detected Inbound Network Problem Null Count | Integer | Number of instances that the Detected Inbound Network Problem model returned a null value. See Detected Inbound Network Problem dimension for explanation. |
| Detected Inbound Network Problem Rate | Percentage | Percentage of streams for which there's high confidence that a First-to-Second media stream might be impacted due to the inbound network. |
| Avg First Is Call Throttled | Integer | Average number of streams where media quality may be affected by CPU throttling on the first endpoint. |
| Avg Second Is Call Throttled | Integer | Average number of streams where media quality may be affected by CPU throttling on the second endpoint. |
| Avg First Healed Data Ratio Value | Percentage (Decimal) | Percentage of the audio stream in which the audio healer on the first endpoint is invoked, averaged across the number of streams in a given row. High HDR indicates that the client expected audio but Teams didn't have any content to play back. High healer usage is experienced by end-users as choppy audio. This measurement isn't currently calculated for WebRTC-based clients. |
| Avg Second Healed Data Ratio Value | Percentage (Decimal) | Percentage of the audio stream in which the audio healer on the second endpoint is invoked, averaged across the number of streams in a given row. High HDR indicates that the client expected audio but Teams didn't have any content to play back. High healer usage is experienced by end-users as choppy audio. This measurement isn't currently reported by WebRTC-based clients. |
| Avg First Received Audio Seconds | Seconds (Decimal) | Amount of active audio received by the first endpoint in seconds, excluding silence. This measurement isn't currently reported by WebRTC based clients. |
| Avg Second Received Audio Seconds | Seconds (Decimal) | Amount of active audio received by the second endpoint in seconds, excluding silence. This measurement isn't currently reported by WebRTC based clients. |
| Avg First Roaming Count | Integer | Average of instances where the first endpoint performed a lightweight reconnect mid-call where signaling wasn't involved. For example, when an endpoint switches wireless access points on the same network. |
| Avg Second Roaming Count | Integer | Average of instances where the second endpoint performed a lightweight reconnect mid-call where signaling wasn't involved. For example, when an endpoint switches wireless access points on the same network. |
| Avg First Recv Avg Freeze Duration | Milliseconds | Average of the average duration in seconds of received video freeze events on the first endpoint. |
| Avg Second Recv Avg Freeze Duration | Milliseconds | Average of the average duration in seconds of received video freeze events on the second endpoint. |
| Avg First Recv AV Sync Distance Avg | Milliseconds | The average of the average difference between audio and video modality (video or VBSS) network delays in milliseconds for the first endpoint. A positive value would mean that audio arrived later than the video. |
| Avg Second Recv AV Sync Distance Avg | Milliseconds | The average of the average difference between audio and video modality (video or VBSS) network delays in milliseconds for the second endpoint. A positive value would mean that audio arrived later than the video. |
| Avg First Recv AV Sync Distance Max | Milliseconds | The average of the maximum difference value of how much video or VBSS is ahead of the audio for the first endpoint in milliseconds. |
| Avg Second Recv AV Sync Distance Max | Milliseconds | The average of the maximum difference value of how much video or VBSS is ahead of the audio for the second endpoint in milliseconds. |
| Avg First Recv AV Sync Distance Min | Milliseconds | The average of the minimum difference value of how much video or VBSS is ahead of the audio for the first endpoint in milliseconds. |
| Avg Second Recv AV Sync Distance Min | Milliseconds | The average of the minimum difference value of how much video or VBSS is ahead of the audio for the second endpoint in milliseconds. |
| Avg First Recv AV Sync Distance Std Dev | Milliseconds | The average of the standard deviation of the difference in audio/video sync delay for the first endpoint. Higher values are indicative of a larger variation of the offsync and can indicate burstier video transmission. |
| Avg Second Recv AV Sync Distance Std Dev | Milliseconds | The average of the standard deviation of the difference in audio/video sync delay for the second endpoint. Higher values are indicative of a larger variation of the offsync and can indicate burstier video transmission. |
| Avg First Input Noise Level | dBFS (Decimal) | The RMS noise level of the audio signal Teams receives from the first capture device as measured in dBFS. |
| Avg Second Input Noise Level | dBFS (Decimal) | The RMS noise level of the audio signal Teams receives from the second capture device as measured in dBFS. |
| Avg First Input Speech Level | dBFS (Decimal) | The RMS level of the speech detected in the audio signal Teams receives from the first capture device as measured in dBFS. |
| Avg Second Input Speech Level | dBFS (Decimal) | The RMS level of the speech detected in the audio signal Teams receives from the second capture device as measured in dBFS. |

### Notes on measurements

#### Accuracy limitations

Certain user and call count measurements rely on performing a distinct countif operation on the data set to compute the count. There's currently an up to 0.2% error inherent with the distinct countif operation depending on the number of rows the operation is performed on. For the most accurate volume, use stream count measures, which don't rely on this distinct countif operation. Filtering to reduce the data volume might reduce the error, but might not eliminate the source of the error in distinct call and user counts. More information about this limitation can be found here [dcount aggregate function](/en-us/azure/data-explorer/kusto/query/dcount-aggfunction).

## Filters

You can use many Dimension and Measurement values as filters. You can use filters in your query to eliminate information in the same way you'd select a Dimension or Measurement to add or include information in the query.