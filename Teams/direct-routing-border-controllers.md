---
layout: Conceptual
title: Session Border Controllers certified for Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-border-controllers
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
ms.reviewer: FilippSe
ms.date: 2026-09-28T00:00:00.0000000Z
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- NOCSH
description: Learn about which Session Border Controllers (SBCs) are certified for Microsoft Direct Routing.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 1b1a1c01-10a9-7f69-1c7b-1a566b0f5112
document_version_independent_id: 329ee759-40fc-98fb-b91e-87786c63024b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-border-controllers.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-border-controllers
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-border-controllers.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/eea02214-631d-404a-92d1-5a3357c32a26
- https://authoring-docs-microsoft.poolparty.biz/devrel/5287f575-02f0-405f-92b7-800456526b0c
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/f42c31d7-eed9-43b7-9757-54caffb53cdc
- https://authoring-docs-microsoft.poolparty.biz/devrel/06e86142-34c2-4b94-ab9c-9477c21f7152
platformId: e87c4086-b652-1c22-a1eb-5ae706d4d8f6
---

# Session Border Controllers certified for Direct Routing - Microsoft Teams | Microsoft Learn

Microsoft partners with selected Session Border Controllers (SBC) vendors to certify that their SBCs work with Direct Routing.

Microsoft works with each vendor to:

- Jointly work on the SIP interconnection protocols.
- Perform intense tests using a third-party lab. Only devices that pass the tests are certified.
- Run daily tests with all certified devices in production and preproduction environments. Validating the devices in preproduction environments guarantees that new versions of Direct Routing code in the cloud work with certified SBCs.
- Establish a joint support process with the SBC vendors.

    Note

    Microsoft only supports Phone System with Direct Routing when used with certified devices. If you encounter an issue, you must contact your SBC vendor's customer support first. If needed, the SBC vendor escalates the issue to Microsoft via internal channels.

    To escalate SBC related issues to Microsoft support, customers must present an SBC vendor investigation report. This document, containing the vendor's ticket reference number, will be supplied by their certified SBC vendor.

    Microsoft reserves the right to reject support cases where a non-certified device is connected to Phone System through Direct Routing. If Microsoft determines that a customer's Direct Routing issue is with a vendor's SBC device, the customer needs to re-engage the SBC vendor for support.

    The certification is granted to specific SBC firmware versions. Any SBC firmware version documented in this article is both certified and supported. Firmware versions that are higher than what is documented are supported as long as the major.minor version is the same.

> 
> Example:
> 
> - Supported 6.10.258 - In this case, Microsoft supports firmware versions 6.10.(258 or higher).
> - Recommended 6.20.100 - In this case, Microsoft recommends firmware versions 6.20.(100 or higher).
> - For supportability questions about specific version, reach out to your SBC vendor.
> 

The tables that follow list devices certified for Direct Routing. (For information about which SBC vendors support Local Media Optimization, see [Configure Local Media Optimization for Direct Routing](direct-routing-media-optimization-configure).)

For more information about Direct Routing, see [Plan Direct Routing](direct-routing-plan).

We're not accepting new nominations for certification until further notice.

## Certified SBC vendors

| Vendor | Product | Non-media bypass | Media bypass | Software version | 911 Service Provider Capable\* | ELIN capable |
| --- | --- | --- | --- | --- | --- | --- |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) | Mediant 500 SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Mediant 500 Li SBC | ✔ | ✔ | Supported 7.2x.xxx (Recommended 7.40A.400) | ✔ | ✔ |
|  | Mediant 800 SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Mediant 2600 SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Mediant 4000 SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Mediant 1000B SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Mediant 7000 SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.600) | ✔ | ✔ |
|  | Mediant 9000 SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Virtual Edition SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Mediant Cloud Edition SBC | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
|  | Mediant 3100 | ✔ | ✔ | Supported 7.40A.600 (Recommended 7.40A.500) | ✔ | ✔ |
| [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business) | SBC 5400 | ✔ | ✔ | Supported on available versions of 11.1 and later, 10.1, 9.2, and 7.2 (Recommended latest version) | ✔ |  |
|  | SBC 7000 | ✔ | ✔ | Supported on available versions of 11.1 and later, 10.1, 9.2, and 7.2 (Recommended latest version) | ✔ |  |
|  | All SBC SWe variants, including hosted offers | ✔ | ✔ | Supported on available versions of 11.1 and later, 10.1, 9.2, and 7.2 (Recommended latest version) | ✔ |  |
|  | SBC 1000 | ✔ | ✔ | Supported on available versions of 12.x and later, 11.x, or 9.x (Recommended latest version) | ✔ | ✔ |
|  | SBC 2000 | ✔ | ✔ | Supported on available versions of 12.x and later, 11.x, or 9.x (Recommended latest version) | ✔ | ✔ |
|  | SBC SWe Edge (formerly SWe Lite) | ✔ | ✔ | Supported on available versions of 12.x and later, 11.x, or 9.x (Recommended latest version) | ✔ | ✔ |
|  | Edge 8000 (w/SBC SWe Edge) | ✔ | ✔ | 23.06 or higher | ✔ | ✔ |
|  | EdgeMarc Series | ✔ | ✔ | 16.3.2 |  |  |
| [Thinktel](https://thinktel.ca/services/complete-your-microsoft-teams-voice-solution-with-think365-cloud-voice/) | Think 365 SBC | ✔ |  | 1.4 |  |  |
| [Oracle](https://www.oracle.com/communications/partner-microsoft/) | AP 1100 | ✔ | ✔ | Supported 9.x and 10.x. Recommended latest version. | ✔ | ✔ |
|  | AP 3900 | ✔ | ✔ | Supported 9.x and 10.x. Recommended latest version. | ✔ | ✔ |
|  | AP 4600 | ✔ | ✔ | Supported 9.x and 10.x. Recommended latest version. | ✔ | ✔ |
|  | AP 6300 | ✔ | ✔ | Supported 9.x. Recommended latest version. | ✔ | ✔ |
|  | AP 6350 | ✔ | ✔ | Supported 9.x and 10.x. Recommended latest version. | ✔ | ✔ |
|  | VME | ✔ | ✔ | Supported 9.x and 10.x. Recommended latest version. | ✔ | ✔ |
|  | AP 3950 | ✔ | ✔ | Supported 9.x and 10.x. Recommended latest version. | ✔ | ✔ |
|  | AP 4900 | ✔ | ✔ | Supported 9.x and 10.x. Recommended latest version. | ✔ | ✔ |
|  | AP 6400 | ✔ | ✔ | Supported 10.x. Recommended latest version. | ✔ | ✔ |
|  | Cloud Native SBC | ✔ |  | Supported 1.26.0.1.0 or higher Recommended latest version. | TBC | TBC |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) | anynode | ✔ | ✔ | Supported 3.20 (Recommended 4.0) | ✔ | ✔ |
| [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc) | Perimeta SBC | ✔ | ✔ | 4.7 (4.9 for Media Bypass) | ✔ | ✔ |
| [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html) | Cisco Unified Border Element (CUBE) for 1000 Series Integrated Services Routers | ✔ | ✔ | Supported IOS XE Amsterdam 17.2.1r (Recommended 17.6.1a) | ✔ |  |
|  | Cisco Unified Border Element (CUBE) for 4000 Series Integrated Services Routers | ✔ | ✔ | Supported IOS XE Amsterdam 17.2.1r (Recommended 17.6.1a) | ✔ |  |
|  | Cisco Unified Border Element (CUBE) for 1000 V Series Cloud Services Router | ✔ | ✔ | Supported IOS XE Amsterdam 17.2.1r (Recommended 17.3.3) | ✔ |  |
|  | Cisco Unified Border Element (CUBE) for 1000 Series Aggregation Services Routers | ✔ | ✔ | Supported IOS XE Amsterdam 17.2.1r (Recommended 17.6.1a) | ✔ |  |
|  | Cisco Unified Border Element (CUBE) for Catalyst 8000 Edge Platforms | ✔ | ✔ | Supported IOS XE Amsterdam 17.3.2 (Recommended 17.6.1a) | ✔ |  |
| [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x) | Avaya Session Border Controller for Enterprise (ASBCE) | ✔ | ✔ | Release 8.1.1 or higher (8.1.2 or higher for Media Bypass, 10.2.0.2 for ELIN) | ✔ | ✔ |
| [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip) | Nokia Session Border Controller | ✔ | ✔ | 25.7 | ✔ |  |
| [Italtel](https://www.italtel.com/italtels-sbc-obtains-microsoft-teams-direct-routing-certification/) | NetMatch-S CI | ✔ | ✔ | Supported 5.8 (Recommended latest version) | ✔ | ✔ |
| [Ericsson](https://www.ericsson.com/portfolio/cloud-software-and-services/cloud-core/communication-services-udm-and-exposure/communication-services--udm/cloud-ims/enterprise-communication/sip-trunking) | vSBC 2.16 | ✔ |  |  |  |  |
| [Cataleya](https://cataleya.com/cataleya-launches-orchid-cloud-revolutionary-cloud-based-wholesale-voice-business-platform/) | Orchid Link | ✔ |  | 3.1 |  |  |
| [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc) | Teams SBC | ✔ | ✔ | 1.6 |  |  |
| [Mitel](https://www.mitel.com/products/openscape-session-border-controller) | Unify OpenScape Session Border Controller | ✔ | ✔ | V10R2.2.0 or higher |  |  |
|  | Mitel Session Border Controller | ✔ | ✔ | Supported v1.0.127 (Recommended v1.0.127) |  |  |
| [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/) | vmVSXi | ✔ | ✔ | 10.5.1.354-vm-S-x64 | ✔ |  |
| [Enghouse Networks](https://www.enghousenetworks.com/products/infrastructure-security/enghouse-bordernet-sbc/) | Dialogic BorderNet SBC | ✔ | ✔ | 3.9.x |  |  |
| [Patton Electronics Co.](https://www.patton.com/microsoft/) | Patton SmartNode eSBC | ✔ |  | 3.19.x |  |  |
| [M5 Technologies (previously known as Media5 Corporation)](https://www.m5technologies.com/pages/gateways-sbcs-for-microsoft-teams-1) | Mediatrix Sentinel Series | ✔ |  | DGW 48.0.2340 (Recommended DGW 48.5.2718) |  |  |
| [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc) | Ekinops Session Border Controller (ONeSBC) | ✔ | ✔ | Supported 6.12.x (Recommended 6.14.x) |  |  |
|  | Ekinops Virtual Session Border Controller (ONEvSBC) | ✔ | ✔ | Supported 6.12.x (Recommended 6.14.x) |  |  |
| [46 Labs LLC](https://46labs.atlassian.net/wiki/spaces/peeredge/pages/61603842/Microsoft+Teams+Implementation+Guide+v1.0) | Peeredge Orchestrator | ✔ | ✔ | 1.0.6 |  |  |
| [Frafos](https://www.frafos.com/ms-teams-abc-sbc) | ABC SBC | ✔ |  | 4.6 |  |  |
| [Nuera](https://www.nuera.com/sbc-media-gateway) | GX-500 SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-500 Li SBC | ✔ | ✔ | Supported 7.2x.xxx (Recommended 7.40A.400) | ✔ | ✔ |
|  | GX-800 SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-2600 SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-4000 SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-1000B SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-9000 SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-VE SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-CE SBC | ✔ | ✔ | Supported 7.20A.258 (Recommended 7.40A.500) | ✔ | ✔ |
|  | GX-3100 | ✔ | ✔ | Supported 7.20A.250 (Recommended 7.40A.500) | ✔ | ✔ |
| [Telnyx LLC](https://telnyx.com/resources/direct-routing-overview) | Telnyx MS Teams SBC | ✔ | ✔ | v2024.0315.18.37.f2c7869 | ✔ |  |
| [Vodia Networks Inc.](https://web.vodia.com/microsoft-teams) | Vodia PBX | ✔ |  | v69.4 |  |  |
| [Brekeke Software, Inc.](https://docs.brekeke.com/pbx/integration-with-microsoft-teams) | Brekeke PBX | ✔ |  | 3.17.1.5 or higher |  |  |
| [Nextgen, Inc.](https://www.nextgen.co.jp/english/solution/carrier/border_solutions/sbc/directrouting_for_microsoftteams.html) | NX-B5000 | ✔ | ✔ | 7.3 or higher |  |  |
| [8x8](https://www.8x8.com/products/8x8-for-microsoft-teams) | 8x8 SBC | ✔ | ✔ | v1.2 |  |  |

\* **911 service providers**

Microsoft certifies and supports the following emergency services providers. If a non-certified provider is used, Microsoft may reject support cases.

- [Bandwidth Dynamic Location Routing](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado Emergency Routing Service (ERS)](https://www.intrado.com/enterprise-solutions/e911/microsoft-teams)
- [Inteliquent](https://sinch.com/news/inteliquent-launches-microsoft-teams-certified-e911-calling/)

## Support for Local Media Optimization

The following table describes which SBC vendors support [Local Media Optimization](direct-routing-media-optimization).

| Vendor | Product | Software version |
| --- | --- | --- |
| [AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) | Mediant 500 SBC | 7.20A.256 |
|  | Mediant 800 SBC | Supported 7.20A.258 (Recommended 7.40A.100) |
|  | Mediant 2600 SBC | Supported 7.20A.258 (Recommended 7.40A.100) |
|  | Mediant 4000 SBC | Supported 7.20A.258 (Recommended 7.40A.100) |
|  | Mediant 1000B SBC | Supported 7.20A.258 (Recommended 7.40A.100) |
|  | Mediant 9000 SBC | Supported 7.20A.258 (Recommended 7.40A.100) |
|  | Mediant Virtual Edition SBC | Supported 7.20A.258 (Recommended 7.40A.100) |
|  | Mediant Cloud Edition SBC | Supported 7.20A.258 (Recommended 7.40A.100) |
| [Ribbon SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization) | SBC 5110 | 8.2 or higher SW version |
|  | SBC 5210 | 8.2 or higher SW version |
|  | SBC 5400 | 8.2 or higher SW version |
|  | SBC 7000 | 8.2 or higher SW version |
|  | SBC SWe | 8.2 or higher SW version |
| [Ribbon SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization) | SBC SWe Edge (formerly SWe Lite) | 8.1.5 or higher SW version |
|  | SBC 1000 | 8.1.5 or higher SW version |
|  | SBC 2000 | 8.1.5 or higher SW version |
|  | SBC 8000 (w/SBC SWe Edge) | 23.06 or higher SW version |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) | anynode | 4.0.1+ |
| [Oracle](https://www.oracle.com/communications/partner-microsoft/) | AP 1100 | 9.x and 10.x |
|  | AP 3900 | 9.x and 10.x |
|  | AP 4600 | 9.x and 10.x |
|  | AP 6300 | 9.x |
|  | AP 6350 | 9.x and 10.x |
|  | VME | 9.x and 10.x |
|  | AP 3950 | 9.x and 10.x |
|  | AP 4900 | 9.x and 10.x |
|  | AP 6400 | 10.x |
| [Avaya](https://documentation.avaya.com/en-US/bundle/WorkingWithAvayaSBCEandMicrosoftTeams_r81x/page/About_Avaya_SBCE_and_MS_Teams.html) | Avaya Session Border Controller for Enterprise (ASBCE) | 10.1.2 or higher |
| [Italtel](https://www.italtel.com/italtels-sbc-obtains-microsoft-teams-direct-routing-certification/) | NetMatch-S CI | 5.7 or higher SW version |
| [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/) | Enghouse BorderNet | 3.9.2-XY or higher SW version |

## Direct Routing and analog devices interoperability

The following table lists devices that are verified for interoperability between Direct Routing and Analog Devices.

| Vendor | Product | Verified |
| --- | --- | --- |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) | [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf) | ✔ |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) | [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf) | ✔ |
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) | ATA 191 Multiplatform Analog Telephone Adapter | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 1100 Software Version 9.x and 10.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 3900 Software Version 9.x and 10.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 4600 Software Version 9.x and 10.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 6300 Software Version 9.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 6350 Software Version 9.x and 10.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | VME Software Version 9.x and 10.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 3950 Software Version 9.x and 10.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 4900 Software Version 9.x and 10.x. Recommended latest version. | ✔ |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) | AP 6400 Software Version 10.x. Recommended latest version. | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [SBC 1000. Software version: 8.1.1 (build 527) or higher SW version](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices) | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [SBC 2000. Software version: 8.1.1 (build 527) or higher SW version](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices) | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [EdgeMarc 302. Software version: 16.1.1 or higher SW version](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances) | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [EdgeMarc 304. Software version: 16.1.1 or higher SW version](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances) | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [EdgeMarc 2900A. Software version: 16.1.1 or higher SW version](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances) | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [EdgeMarc 4806. Software version: 16.1.1 or higher SW version](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances) | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [EdgeMarc 4808. Software version: 16.1.1 or higher SW version](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances) | ✔ |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) | [EdgeMarc 6000. Software version: 16.1.1 or higher SW version](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances) | ✔ |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) | anynode with Grandstream GXW42xx (V1.0.7.10) | ✔ |

Note the certification is granted to a major version. That means that firmware with any number in the SBC firmware following the major version is supported.

To provide feedback about Teams, such as ideas for new features, see the [Microsoft feedback portal](https://feedbackportal.microsoft.com/).

Note

Media re-targeting isn't supported. During a Direct Routing call, if the SBC sends a new media IP to Teams Direct Routing, although it's negotiated in the SIP signaling, the media is never sent to the new IP address from Teams Direct Routing.