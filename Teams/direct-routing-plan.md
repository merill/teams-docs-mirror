---
layout: Conceptual
title: Plan Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-plan
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
audience: ITPro
ms.reviewer: filippse
ms.date: 2026-09-10T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
f1.keywords:
- NOCSH
ms.custom: 
description: Learn how Microsoft Direct Routing lets you connect a supported customer-provided Session Border Controller (SBC) to Microsoft Teams Phone.
locale: en-us
document_id: 3d964547-6b38-cc5f-6b2b-7a50a1c7dae9
document_version_independent_id: fa5850f9-1b92-9727-c344-bcffc227cbd6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-plan.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 32c82af6-0bf7-908c-6b0f-2fe82660f4ca
---

# Plan Direct Routing - Microsoft Teams | Microsoft Learn

Direct Routing enables organizations to connect their own telephony infrastructure to Microsoft Teams Phone by using a supported, customer-provided Session Border Controller (SBC). This allows organizations to use existing PSTN carriers, integrate third-party telephony systems, and maintain greater control over their voice infrastructure.

Planning your Direct Routing deployment is essential for a successful implementation. This article provides planning guidance for infrastructure, licensing, networking, Session Border Controller (SBC), and connectivity requirements before you begin deployment.

For configuration instructions, see [Configure Direct Routing](direct-routing-configure).

Tip

If you're evaluating Microsoft Teams Phone connectivity options, compare Direct Routing with Microsoft Calling Plans, Operator Connect, and Teams Phone Mobile before choosing your deployment model.

## Why choose Direct Routing?

Direct Routing is a good fit for organizations that:

- Have an existing PSTN carrier relationship.
- Require integration with third-party PBXs or analog devices.
- Need advanced voice routing capabilities.
- Want greater control over their telephony infrastructure.
- Support complex or multinational voice deployments.

Organizations can also deploy Direct Routing alongside Microsoft Calling Plans, Operator Connect, and Teams Phone Mobile within the same Microsoft Teams tenant.

## Deployment overview

Planning a Direct Routing deployment typically includes the following steps.

| Step | Description |
| --- | --- |
| 1 | Review infrastructure and licensing requirements. |
| 2 | Select a Microsoft-certified Session Border Controller (SBC). |
| 3 | Configure networking, DNS, certificates, and connectivity. |
| 4 | Connect the SBC to Microsoft Teams. |
| 5 | Configure voice routing and assign users. |
| 6 | Validate inbound and outbound calling before production rollout. |

## Direct Routing architecture

The following diagram shows how Direct Routing connects Microsoft Teams Phone to your existing telephony infrastructure.

```text
                Microsoft Teams

               +-------------+
               | Teams Phone |
               +------+------+
                      |
               Direct Routing
                      |
             +--------+--------+
             |  Certified SBC  |
             +--------+--------+
                      |
             +--------+----------------+
             |                         |
 +-----------+-----------+     +-------+--------+
 | Existing PSTN Carrier |     |  Existing PBX  |
 +-----------+-----------+     | Analog Devices |
                               |   SIP Trunks   |
                               +-------+--------+
```

## Infrastructure requirements

The following infrastructure is required to deploy Direct Routing.

| Infrastructure requirement | Requirement |
| --- | --- |
| Session Border Controller (SBC) | A supported SBC. For more information, see Supported SBCs. |
| Telephony trunks | One or more telephony trunks connected to the SBC. On one end, the SBC connects to Teams Phone through Direct Routing. The SBC can also connect to third-party telephony entities, such as PBXs, Analog Telephony Adapters, and so on. Any PSTN connectivity option connected to the SBC will work. (For configuration of the PSTN trunks to the SBC, refer to the SBC vendors or trunk providers.) |
| Microsoft 365 organization | Microsoft 365 tenant hosting Teams users. |
| User registrar | Users must be homed online in Microsoft 365. |
| Domains | One or more domains added to your Microsoft 365 or Office 365 organizations.You can't use the default domain, \*.onmicrosoft.com, which is automatically created for your tenant.To view the domains, you can use the following Teams PowerShell cmdlet:`Get-CsTenant | fl Domains`For more information about domains and Microsoft 365 or Office 365 organizations, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a). |
| Public IP | A public IP address that can be used to connect to the SBC. Based on the type of SBC, the SBC can use NAT. |
| SBC FQDN | An FQDN for the SBC, where the domain portion of the FQDN is one of the registered domains in your Microsoft 365 or Office 365 organization. For more information, see SBC domain names. |
| Public DNS | Public DNS entry for the SBC FQDN. |
| Public certificate | A supported certificate for the SBC to be used for all communication with Direct Routing. For more information, see Public trusted certificate for the SBC. |
| Direct Routing connection points | The connection points for Direct Routing are the following three FQDNs:`sip.pstnhub.microsoft.com` – Global FQDN, must be tried first.`sip2.pstnhub.microsoft.com` – Secondary FQDN, geographically maps to the second priority region.`sip3.pstnhub.microsoft.com` – Tertiary FQDN, geographically maps to the third priority region.For information on configuration requirements, see SIP Signaling: FQDNs. |
| Firewall | The SBC communicates to the following services in the cloud:- SIP proxy: handles signaling- Media processor: handles media except when Media Bypass is enabledThese two services have separate IP addresses in Microsoft Cloud, described later in this document.For more information, see the [Microsoft Teams section](/en-us/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [URLs and IP address ranges](/en-us/office365/enterprise/urls-and-ip-address-ranges). |
| Media transport | TCP/RTP/SAVP and UDP/RTP/SAVP |

## Licensing requirements

Direct Routing users require:

- Microsoft Teams
- Teams Phone

Additional licensing may be required depending on your deployment.

For Audio Conferencing scenarios, see Direct Routing with Audio Conferencing.

For licensing information, see:

- [Microsoft Teams licensing](user-access)
- [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing)

Note

Direct Routing isn't supported in Islands mode.

## Direct Routing with Audio Conferencing

When users participate in scheduled meetings, dial-in numbers are provided through Microsoft Audio Conferencing.

If a user doesn't have an Audio Conferencing license assigned, outbound conference calls route through Direct Routing.

For GCC High and DoD environments, Microsoft recommends completing Direct Routing deployment before assigning Audio Conferencing licenses.

For additional guidance, see [Audio Conferencing with Direct Routing for GCC High and DoD](audio-conferencing-with-direct-routing-for-gcch-and-dod).

### Unplanned call escalation and Audio Conferencing license

A Teams user can start a one-on-one Teams-to-PSTN or Teams-to-Teams call and add a PSTN participant to it. The path that the call takes depends on whether the user who escalates the call has a Microsoft Audio Conferencing license assigned or not:

- **If the Teams user who escalates the call has a Microsoft Audio Conferencing license assigned**, the escalation happens through the Microsoft Audio Conferencing service. The remote PSTN participant who is invited to the existing call receives a notification about the incoming call, and sees the number of the Microsoft bridge assigned to the Teams user who initiated the escalation.
- **If the Teams user who escalates the call doesn't have the Microsoft Audio Conferencing license assigned**, the escalation happens through a Session Border Controller connected to the Direct Routing interface. The remote PSTN participant who is invited to the call receives a notification about the incoming call and sees the number of the Teams user who initiated the escalation. The specific SBC used for the escalation is defined by the routing policy of the user.

You must ensure the following:

- CsOnlineVoiceRoutingPolicy is assigned to the user.
- Allow Private Calling is enabled at the tenant level for Microsoft Teams.

## Direct Routing with Calling Plans and Operator Connect

Direct Routing also supports users who are licensed for Microsoft Calling Plans or assigned an Operator Connect phone number. Teams Phone users with a Calling Plan or Operator Connect can route some calls through Direct Routing.

Mixing Calling Plans or Operator Connect and Direct Routing connectivity for the same user is optional, but could be useful. For example, when the user is assigned a Microsoft Calling Plan or Operator Connect number but wants to route some calls internally using the SBC.

Call routing follows a defined order of evaluation. Teams first evaluates Direct Routing voice routes associated with the user’s Online Voice Routing Policy. When no applicable Direct Routing route matches the called number, Teams checks whether the user has Calling Plan or Operator Connect available and attempts to complete the call using that connectivity.

A common deployment pattern is:

- Microsoft Calling Plans or Operator Connect for PSTN calling.
- Direct Routing for calls to third-party PBXs.
- Direct Routing for analog devices.
- Direct Routing for specialized routing scenarios.

This hybrid deployment allows organizations to optimize call routing while maintaining existing telephony investments.

For more information about Teams Phone licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing).

## Supported endpoints

Direct Routing supports:

- Microsoft Teams desktop and mobile clients
- Teams-certified phones
- Common Area Phones

For Common Area Phones, a Calling Plans license isn't required when Direct Routing is used. For more information, see [Set up common area phones for Microsoft Teams](set-up-common-area-phones).

## SBC domain names

The SBC FQDN must belong to a verified domain within your Microsoft 365 tenant.

You can't use the default \*.onmicrosoft.com domain.

Examples include:

| DNS Domain | Supported | Example |
| --- | --- | --- |
| contoso.com | Yes | sbc1.contoso.com |
| contoso.onmicrosoft.com | No | Not supported |

If you create a new subdomain, you must first register that domain in Microsoft 365 before pairing the SBC. For example, if contoso.com is registered in your tenant and you want to use sbc1.sip.contoso.com , first register sip.contoso.com .

Before you can pair an SBC with the name sbc1.sip.contoso.com, you must register the domain name sip.contoso.com in Domains in your tenant. If you try pairing an SBC with sbc1.sip.contoso.com before registering the domain name, you'll get the following error: `Can't use the "sbc1.sip.contoso.com" domain as it wasn't configured for this tenant.`

After you add the domain name, you need to create a user with UPN user@sip.contoso.com and assign a Teams license. It may take up to 24 hours to fully provision the domain name after it's added to Domains of your tenant, to create a user with a new name, and to assign a license to the user.

It's possible that a company might have several SIP address spaces in one tenant. For example, a company might have contoso.com as a SIP address space and fabrikam.com as the second SIP address space. Some users have addresses such as user@contoso.com ; others have addresses such as user@fabrikam.com .

The SBC only needs one FQDN and can service users from any address space in the paired tenant. For example, an SBC with the name sbc1.contoso.com can receive and send the PSTN traffic for users with addresses user@contoso.com and user@fabrikam.com as long as these SIP address spaces are registered in the same tenant.

Note

SBC FQDN in Azure Communication Services direct routing must be different from SBC FQDN in Teams Direct Routing.

## Public trusted certificate for the SBC

Microsoft recommends requesting a certificate by generating a Certificate Signing Request (CSR) directly from your SBC. For specific instructions on generating a CSR for an SBC, see the interconnection instructions or documentation provided by your SBC vendors.

The certificate should:

- Use the SBC FQDN as the Common Name (CN) or Subject Alternative Name (SAN).
- Be signed by a Certificate Authority included in the Microsoft Trusted Root Program.
- Include the Server Authentication EKU.

Note

Most Certificate Authorities (CAs) require the private key size to be at least 2048 bits. Keep this in mind when generating the CSR.

Wildcard certificates are supported when they comply with [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1). An example would be using \*.contoso.com, which would match the SBC FQDN sbc.contoso.com, but wouldn't match with sbc.test.contoso.com.

Direct Routing SIP interface will only trust certificates that are signed by Certificate Authorities (CAs) that are part of the Microsoft Trusted Root Certificate Program. Make sure that a CA that is part of the program signs your SBC certificate. Also make sure that the Extended Key Usage (EKU) extension of your certificate includes Server Authentication. For more information, see [Program Requirements - Microsoft Trusted Root Program](/en-us/security/trusted-root/program-requirements).

For Direct Routing in Office 365 GCCH and DoD environments, the following root certificate authorities are currently supported:

- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- DigiCert Global Root G2

Customers can request that additional CAs be added to the supported list through their regular support channel.

Note

If Mutual TLS (MTLS) support is enabled for the Teams connection on the SBC, then you must install all the CAs listed under the 'Root Certificate Authorities' section in the Azure Certificate Authority details page in the SBC Trusted Root Store of the Teams TLS context. (This is because the Microsoft service certificates use these root certificates.) To download the root certificates, see [Microsoft 365 Encryption chains](/en-us/microsoft-365/compliance/encryption-office-365-certificate-chains). For more information, see [Office TLS Certificate Changes](/en-us/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

To verify that the MTLS connection originates from Teams infrastructure, the SBC should be configured to implement the following checks on the Teams server-side certificate:

- Verify that the certificate chain leads to one of the listed root CAs under the 'Root Certificate Authorities' section in [Azure Certificate Authority details page](/en-us/azure/security/fundamentals/azure-ca-details?tabs=root-and-subordinate-cas-list).
- Check that the certificate "Subject Alternative Name" includes "sip.pstnhub.microsoft.com".

## SIP signaling

Direct Routing is offered in the following environments:

- Microsoft 365 or Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

For more information about government environments, such as GCC, GCC High, and DoD, see [Office 365 and US Government environments](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government).

The following sections describe the required Fully Qualified Domain Names (FQDNs), ports, and failover behavior used for Direct Routing.

### SIP signaling: FQDNs

For Microsoft 365, Office 365, and Office 365 GCC, configure the following connection points in priority order.

| Priority | FQDN | Purpose |
| --- | --- | --- |
| Primary | `sip.pstnhub.microsoft.com` | Global FQDN – must be tried first. When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC. The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC. The IP address returned corresponds to the primary FQDN. |
| Secondary | `sip2.pstnhub.microsoft.com` | Geographically maps to the second priority region. |
| Tertiary | `sip3.pstnhub.microsoft.com` | Geographically maps to the third priority region. |

If your SBC uses IPv6, configure the following FQDNs:

| Priority | IPv6 FQDN | Purpose |
| --- | --- | --- |
| Primary | `sip.ipv6.pstnhub.microsoft.com` | Global FQDN – must be tried first. When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC. The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC. The IP address returned corresponds to the primary FQDN. |
| Secondary | `sip2.ipv6.pstnhub.microsoft.com` | Geographically maps to the second priority region. |
| Tertiary | `sip3.ipv6.pstnhub.microsoft.com` | Geographically maps to the third priority region. |

These FQDNs provide:

- Geographic routing to the nearest Microsoft datacenter.
- Automatic failover during service interruptions. For more information, see Failover mechanism.
- High availability for SIP signaling.

The FQDNs resolve to Microsoft IP ranges:

- 52.112.0.0/14
- 52.120.0.0/14

In the case of IPv6 the FQDNs resolve to Microsoft IP range:

- 2603:1063:400::/40

Important

Configure your SBC and firewall to allow signaling traffic to and from all Microsoft Teams IP ranges, not only the addresses returned from DNS queries.

Note

Inbound SIP traffic to the SBCs from Teams SIP endpoints can originate from any IPs in these subnets--not only from IPs that resolve from the previously mentioned FQDNs. For more information on how to set up SIP peering, see your SBC documentation.

### SIP signaling: GCC High

For Office 365 GCC High, use:

`sip.pstnhub.gov.teams.microsoft.us`

The FQDN sip.pstnhub.gov.teams.microsoft.us is resolved to an IP address from the following subnet: 52.127.88.0/21 To allow incoming and outgoing traffic to and from the addresses for signaling, you need to open ports for all these IP addresses in your firewall.

### SIP signaling: DoD

For Office 365 DoD, use:

`sip.pstnhub.dod.teams.microsoft.us`

The FQDN sip.pstnhub.dod.teams.microsoft.us is resolved to an IP address from the following subnet: 52.127.64.0/21 To allow incoming and outgoing traffic to and from the addresses for signaling, you need to open ports for all these IP addresses in your firewall.

Because these environments operate within dedicated Microsoft Government clouds, secondary and tertiary FQDNs aren't required.

## SIP signaling ports

Direct Routing requires the following SIP/TLS ports.

| Traffic | From | To | Source port | Destination port |
| --- | --- | --- | --- | --- |
| SIP/TLS | SIP Proxy | SBC | 1024 – 65535 | Defined on the SBC (For Office 365 GCC High/DoD only port 5061 must be used) |
| SIP/TLS | SBC | SIP Proxy | Defined on the SBC | 5061 |

## SIP signaling failover

To resolve sip.pstnhub.microsoft.com, the SBC makes a DNS query. Based on the SBC location and the datacenter performance metrics, the primary datacenter is selected.

If the primary datacenter experiences an issue, the SBC tries sip2.pstnhub.microsoft.com, which resolves to the second assigned datacenter. In the rare case that datacenters in two regions aren't available, the SBC retries the last FQDN (sip3.pstnhub.microsoft.com), which provides the tertiary datacenter IP.

The following table summarizes the relationships between primary, secondary, and tertiary datacenters:

| The primary datacenter (sip.pstnhub.microsoft.com) | EMEA | NOAM | APAC | OCEA |
| --- | --- | --- | --- | --- |
| The secondary datacenter (sip2.pstnhub.microsoft.com) | NOAM | EMEA | NOAM | APAC |
| The tertiary datacenter (sip3.pstnhub.microsoft.com) | APAC | APAC | EMEA | NOAM |

## Media traffic

Media traffic uses Microsoft Media Processors unless Media Bypass is enabled.

For Media Bypass planning guidance, see [Plan for Media Bypass with Direct Routing](direct-routing-plan-media-bypass).

## Media processor IP ranges

### Microsoft 365 / Office 365 / Office 365 GCC environments

Allow media traffic for:

- 52.112.0.0/14 (IP addresses from 52.112.0.0 to 52.115.255.255)
- 52.120.0.0/14 (IP addresses from 52.120.0.0 to 52.123.255.255)

In case of IPv6 allow media traffic for:

- 2603:1063:400::/40
- 2603:1063:100::/40

### Office 365 GCC High environment

- 52.127.88.0/21

### Office 365 DoD environment

- 52.127.64.0/21

## Media ports

The following ports are used for media.

| Traffic | From | To | Source port | Destination port |
| --- | --- | --- | --- | --- |
| UDP/SRTP | Media Processor | SBC | 3478-3481 and 49152 – 53247 | Defined on the SBC |
| UDP/SRTP | SBC | Media Processor | Defined on the SBC | 3478-3481 and 49152 – 53247 |

Tip

Microsoft recommends allocating at least two media ports per concurrent call on the SBC.

## Media processor locations

Media traffic flows through components called media processors. Media processors are placed in the same datacenters as SIP proxies as follows:

- NOAM (US South Central, two in US West and US East datacenters)
- Europe (UK South, France Central, Amsterdam, and Dublin datacenters)
- Asia (Singapore datacenter)
- Japan (JP East and West datacenters)
- Australia (AU East and Southeast datacenters)
- LATAM (Brazil South)

Media is routed to the closest available Microsoft datacenter whenever possible.

## Supported media codecs

### Leg between SBC and Microsoft Cloud Media Processor

Applies with and without Media Bypass.

The Direct Routing interface supports the following codecs on the leg between the Session Border Controller (SBC) and Microsoft Cloud Media Processor:

- SILK
- G.711
- G.722
- G.729
- AMR-WB (non-bypass only)

Administrators can force use of a specific codec on the Session Border Controller by excluding undesirable codecs from the offer.

### Leg between Microsoft Teams client and Cloud media processor

Applies only when Media Bypass is disabled. With Media Bypass, the media flows directly between the Teams client and the SBC.

On the leg between the Cloud media processor and the Teams client, either SILK or G.722 is used. The codec choice on this leg is based on Microsoft algorithms, which take into consideration multiple parameters.

Note

Media re-targeting isn't supported. During a call, if a SIP re-INVITE offer from the Direct Routing SBC contains a new media IP address, port, or transport, media isn't sent from PSTN Hub to the new target. Per RFC 3264 8.3.1, media re-target support is optional (not required).

## Supported Session Border Controllers (SBCs)

Microsoft only supports certified SBCs to pair with Direct Routing. Because Enterprise Voice is critical for businesses, Microsoft runs intensive tests with the selected SBCs, and works with the SBC vendors to ensure the two systems are compatible.

Devices that are validated are listed as Certified for Teams Direct Routing. The certified devices are guaranteed to work in all scenarios.

For more information about supported SBCs, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers).

## Support boundaries

Microsoft only supports Teams Phone with Direct Routing when used with certified devices. If there are issues, you must contact your SBC vendor's customer support first. If needed, the SBC vendor escalates the issue to Microsoft through internal channels.

To escalate SBC-related issues to Microsoft support, customers must present an SBC vendor investigation report. This document, containing the vendor's ticket reference number, will be supplied by their certified SBC vendor.

Microsoft reserves the right to reject support cases where a non-certified device is connected to Teams Phone through Direct Routing. If Microsoft determines that a customer's Direct Routing issue is with a vendor's SBC device, the customer needs to re-engage the SBC vendor for support.

## Best practices

For the best Direct Routing experience, Microsoft recommends that you:

- Deploy certified SBCs.
- Configure redundant SIP connectivity.
- Use trusted public certificates.
- Configure all Microsoft-required firewall rules.
- Monitor call quality after deployment.
- Test failover scenarios before production rollout.
- Review Microsoft Teams network planning guidance before deployment.