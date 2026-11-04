---
layout: Conceptual
title: What's New Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-whats-new
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: teddygyabaah
ms.date: 2026-03-09T00:00:00.0000000Z
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.topic: whats-new
audience: admin
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
description: Article describes what's new in Direct Routing. Check back often for updates.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
locale: en-us
document_id: e18d7c72-cd78-c0fe-42d4-d08275b68793
document_version_independent_id: e18d7c72-cd78-c0fe-42d4-d08275b68793
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-whats-new.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-whats-new
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-whats-new.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 50cfef19-9e32-8491-41c7-cac1159a79ae
---

# What's New Direct Routing - Microsoft Teams | Microsoft Learn

Article describes what's new in Direct Routing. Check back often for updates.

## Validation test that switches Microsoft Teams Direct Routing SIP endpoints to certificates issued by a new CA (June 30, 2026)

A validation test that transitions Microsoft Teams Direct Routing SIP endpoints to certificates issued by a new **Certificate Authority (CA) is planned for June 30, 2026**, at 9:00 AM UTC. This effort strengthens certificate lifecycle management and ensures continued secure connectivity. The test helps organizations validate their readiness for future certificate updates and reduces the risk of unexpected service disruption.

- During the test the new certificate rollout happens gradually and in a staged manner in different Geos over several days. The connections to and from the SBCs gradually move over to the new certificate with periods where some connections will still use the old certificate and some connections with the new one.
- If the test isn't terminated prematurely, then it continues over 2-4 days with traffic gradually moving over to the new certificates.
- If the SBCs aren't able to establish outbound TLS connections or start rejecting inbound connections during the timeframe of the test, then this is an indication of possible trust issues with the new certificate. Please follow your SBC vendor documentation to resolve such issues.
- Comms about further actions is planned after the test is completed. No individual per customer comms planned.

## Testing endpoint for upcoming certificate changes (February 16, 2026)

Warning

This testing endpoint has been discontinued. The certificates issued by a new CA were rolled out in production at the end of July 2026.

A new deadline for Certificate Authority (CA) change for MS SIP interface for SBC side changes is end of March. Microsoft starts implementing server side changes from April.

To validate your SBC TLS configuration prior to the upcoming root Certificate Authority (CA) change, Microsoft has provided a dedicated testing endpoint designed to confirm that SBC appliances recognize certificates issued by the new root CA. This endpoint is intended exclusively for SIP OPTIONS ping messages and must not be used for voice traffic. Successful establishment of a TLS connection to this endpoint should indicate that your SBC trusts certificates issued from the new CA and connectivity to Teams services remains unaffected by the update. Consult your SBC vendor how to best set up such a test on your equipment.

Test endpoint FQDN: **sip.g1.pstnhub.microsoft.com**

Port: **5061**

## Clarification on Client Authentication Extended Key Usage (EKU)

Microsoft SIP endpoints currently trust SBC certificates that don't include the Client Authentication Extended Key Usage (EKU). This behavior is expected to continue for the foreseeable future. If this requirement changes in the future, Microsoft will communicate it in advance.

## AMR-WB is enabled for Direct Routing trunks on non bypass calls

AMR-WB is enabled for Direct Routing trunks on non bypass calls, which means: 

- For outbound calls from Teams to the SBC, the offer includes the AMR-WB codec and DTMF/1600. 

    Before: 

    *...*

    *t=0 0*

    *m=audio 49886 RTP/SAVP 104 9 103 111 18 0 8 97 101 13 118*

    *c=IN IP4 52.113.142.x*

    *...*

    *a=crypto:1 AES\_CM\_128\_HMAC\_SHA1\_80 inline:{redacted}*

    *a=sendrecv*

    *a=rtpmap:104 SILK/16000*

    *...*

    *a=fmtp:101 0-16*

    *...*

    After (difference is in **Bold**):

    ...

    *t=0 0*

    *m=audio 51592 RTP/SAVP 104 **121** 9 103 111 18 0 8 97 101 **106** 13 118*

    *c=IN IP4 52.113.21.x*

    *...*

    *a=crypto:1 AES\_CM\_128\_HMAC\_SHA1\_80 inline:{redacted}*

    *a=sendrecv*

    *a=rtpmap:104 SILK/16000*

    ***a=rtpmap:121 AMR-WB/16000***

    *...*

    *a=rtpmap:101 telephone-event/8000*

    *a=fmtp:101 0-16*

    ***a=rtpmap:106 telephone-event/16000***

    ***a=fmtp:106 0-16***

    *a=rtpmap:13 CN/8000*

    *a=rtpmap:118 CN/16000*

    *...*
- For inbound calls from the SBC to Teams, if the offer includes AMR-WB, it will be selected.

## Update on upcoming certificate changes (December 12, 2025)

### Background

TLS connectivity between Microsoft SIP endpoints and customer/partner SBCs uses mutual TLS (mTLS), requiring client certificates with the Client Authentication Extended Key Usage (EKU) property. In February 2025, Google updated its Chrome Root Program Policy (v1.6), deprecating the use of the Client Authentication EKU in TLS server certificates trusted by Google Chrome. Effective June 2026, certificates must exclusively include the Server Authentication EKU to maintain trust from major browsers such as Chrome and Mozilla. While certain public Certificate Authorities (CAs) continue to issue certificates containing the Client Authentication EKU, they might not be recognized by leading browsers but can still be natively accepted by operating systems like Windows, macOS, and Linux. One of supported CAs will provide Microsoft Teams SIP interface TLS client certificates and retain the Client Authentication EKU. 

### Changes and call to action

The outlined changes apply to Direct Routing and Operator Connect and will be implemented by the end of February. Microsoft Teams SIP interface certificates will come from one of the CAs listed under the 'Root Certificate Authorities' section in Azure Certificate Authority details page. 

The list of supported CAs: 

- Certificate Authority: DigiCert Global Root CA

    Thumbprint (SHA1): A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436
- Certificate Authority: DigiCert Global Root G2

    Thumbprint (SHA1): DF3C24F9BFD666761B268073FE06D1CC8D4F82A4
- Certificate Authority: DigiCert Global Root G3

    Thumbprint (SHA1): 7E04DE896A3E666D00E687D33FFAD93BE83D349E
- Certificate Authority: DigiCert TLS ECC P384 Root G5

    Thumbprint (SHA1): 17F3DE5E9F0F19E98EF61F32266E20C407AE30EE
- Certificate Authority: DigiCert TLS RSA 4096 Root G5

    Thumbprint (SHA1): A78849DC5D7C758C8CDE399856B3AAD0B2A57135
- Certificate Authority: Microsoft ECC Root Certificate Authority 2017

    Thumbprint (SHA1): 999A64C37FF47D9FAB95F14769891460EEC4C3C5
- Certificate Authority: Microsoft RSA Root Certificate Authority 2017

    Thumbprint (SHA1): 73A5E64A3BFF8316FF0EDCCC618A906E4EAE4D74

Ensure that all Certificate Authorities (CAs) are included in the SBC trust store and that the SBC is configured to trust both client and server certificates with trust chains anchored in these CAs. SBCs lacking the updated Root CAs in their list of accepted CAs might experience certificate validation errors, which can affect service availability or functionality. For guidance on updating the accepted certificate list, consult your SBC vendors documentation. 

### Summary

- SBCs must trust all root CAs on the supported list, and MS Teams SIP interface client and server certificates trust chain will be anchored in any one of these CAs.
- The mTLS client certificate for MS Teams SIP interface will continue to contain the TLS Client Authentication EKU. Presently the MS Teams SIP interface accepts SBC client certificates even if they lack the Client Authentication EKU. In the future, Microsoft will require all SBC certificates to include the Client Authentication EKU. At that time, a list of publicly trusted CAs capable of issuing such certificates will become available. However, some TLS libraries and SBCs might not permit outbound connections with client certificates missing the Client Authentication EKU.
- Additionally, if a certificate issuer discovers the certificate being used for unapproved purposes, they can revoke it. To ensure compatibility, work directly with your CA to obtain a suitable certificate. Regardless, SBC certificates will still need to be issued from CAs that are part of the 'Microsoft Trusted Root Program'.

## IPv6 with non media bypass is now supported for Teams Phone

We have introduced support for IPv6 non media bypass in addition to previously available IPv4 support in Teams Phone.

Supported:

- All existing IPv4 based calls (SBC SIP and media all IPv4).
- New IPv6-only calls without media bypass: SBC SIP and media both using IPv6.

Not supported:

- Media bypass when using IPv6 SIP or media or IPv6 Teams client.
- Mixed mode SIP and media (IPv6/IPv4).

A new option IPAddressVersion was added for SBC configuration via New-CsOnlinePSTNGateway cmdlet. Possible values are 'IPv4' and 'IPv6'. When 'IPv6' is set, the SBC must use IPv6 for both signaling and media.

IPv6 is supported only for non media bypass scenarios.