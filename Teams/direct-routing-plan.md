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
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 32c82af6-0bf7-908c-6b0f-2fe82660f4ca
---

# Plan Direct Routing - Microsoft Teams | Microsoft Learn

Direct Routing enables organizations to connect their own telephony infrastructure to Microsoft Teams Phone by using a supported, customer-provided Session Border Controller (SBC). This allows organizations to use existing PSTN carriers, integrate third-party telephony systems, and maintain greater control over their voice infrastructure.

Planning your Direct Routing deployment is essential for a successful implementation. This article provides planning guidance for infrastructure, licensing, networking, Session Border Controller (SBC), and connectivity requirements before you begin deployment.

For configuration instructions, see [Configure Direct Routing](direct-routing-configure).

Tip

If you're evaluating Microsoft Teams Phone connectivity options, compare Direct Routing with Microsoft Calling Plan, Operator Connect, and Teams Phone Mobile before choosing your deployment model.

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

## Onboarding

Follow the recommended onboarding sequence below.

| Step | Action |
| --- | --- |
| 1 | Review infrastructure, networking, and licensing requirements. |
| 2 | Select a Microsoft-certified SBC. |
| 3 | Configure DNS, certificates, firewall rules, and connectivity. |
| 4 | Connect the SBC to Microsoft Teams. |
| 5 | Configure voice routing and dial plans. |
| 6 | Assign Teams Phone licenses and voice routing policies. |
| 7 | Validate user calling and expand deployment. |

## Quick links

| Resource | Description |
| --- | --- |
| **Configure Direct Routing** | Complete Direct Routing deployment after planning. |
| **PSTN connectivity options** | Compare Direct Routing with Calling Plan, Operator Connect, and Teams Phone Mobile. |
| [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers) | View Microsoft-certified SBCs. |
| **Plan your Teams voice solution** | Understand Teams Phone deployment options. |
| **Manage Teams phone numbers** | Assign and manage phone numbers. |
| **Assign Teams Phone licenses** | Assign required licenses before deployment. |
| **Teams admin center** | Manage Teams Phone users and voice settings. |
| **Teams PowerShell** | Automate Direct Routing administration. |

## Why choose Direct Routing?

Direct Routing is a good fit for organizations that:

- Have an existing PSTN carrier relationship.
- Require integration with third-party PBXs or analog devices.
- Need advanced voice routing capabilities.
- Want greater control over their telephony infrastructure.
- Support complex or multinational voice deployments.

Organizations can also deploy Direct Routing alongside Microsoft Calling Plan, Operator Connect, and Teams Phone Mobile within the same Microsoft Teams tenant.

## Direct Routing architecture

The following diagram shows how Direct Routing connects Microsoft Teams Phone to your existing telephony infrastructure.

```text
                Microsoft Teams

        +---------------------------+
        |        Teams Phone        |
        +-------------+-------------+
                      |
               Direct Routing
                      |
      +---------------+---------------+
      |   Certified SBC               |
      +---------------+---------------+
                      |
    +-----------------+------------------+
    |                                    |
 Existing PSTN Carrier             Existing PBX
                                   Analog Devices
                                   SIP Trunks
```

## Infrastructure requirements

The following infrastructure is required to deploy Direct Routing.

| Infrastructure requirement | Requirement |
| --- | --- |
| Session Border Controller (SBC) | A Microsoft-certified SBC. |
| Telephony trunks | One or more PSTN trunks connected to the SBC. |
| Microsoft 365 organization | Microsoft 365 tenant hosting Teams users. |
| User registrar | Users must be homed online in Microsoft 365. |
| Domains | One or more verified Microsoft 365 domains (not \*.onmicrosoft.com). |
| Public IP | Public IP address reachable by Microsoft Teams. |
| SBC FQDN | FQDN registered within your Microsoft 365 tenant. |
| Public DNS | Public DNS entry for the SBC FQDN. |
| Public certificate | Trusted certificate for secure TLS communication. |
| Direct Routing connection points | sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com, sip3.pstnhub.microsoft.com |
| Firewall | Required Microsoft Teams signaling and media ports. |
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

## Direct Routing with Calling Plan and Operator Connect

Organizations can combine Direct Routing with Microsoft Calling Plan or Operator Connect.

A common deployment pattern is:

- Microsoft Calling Plan or Operator Connect for PSTN calling.
- Direct Routing for calls to third-party PBXs.
- Direct Routing for analog devices.
- Direct Routing for specialized routing scenarios.

This hybrid deployment allows organizations to optimize call routing while maintaining existing telephony investments.

## Supported endpoints

Direct Routing supports:

- Microsoft Teams desktop and mobile clients
- Teams-certified phones
- Common Area Phones

For Common Area Phones, a Calling Plan license isn't required when Direct Routing is used.

## SBC domain names

The SBC FQDN must belong to a verified domain within your Microsoft 365 tenant.

You can't use the default \*.onmicrosoft.com domain.

Examples include:

| DNS Domain | Supported | Example |
| --- | --- | --- |
| contoso.com | Yes | sbc1.contoso.com |
| contoso.onmicrosoft.com | No | Not supported |

If you create a new subdomain such as **sip.contoso.com**, you must first register that domain in Microsoft 365 before pairing the SBC.

## Public trusted certificate for the SBC

Microsoft recommends requesting a certificate by generating a Certificate Signing Request (CSR) directly from your SBC.

The certificate should:

- Use the SBC FQDN as the Common Name (CN) or Subject Alternative Name (SAN).
- Be signed by a Certificate Authority included in the Microsoft Trusted Root Program.
- Include the Server Authentication EKU.

Wildcard certificates are supported when they comply with RFC 2818.

For Direct Routing in Office 365 GCCH and DoD environments, the following root certificate authorities are currently supported:

- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- DigiCert Global Root G2

Customers can request addition CA be added to the supported list via their regular support channel.

If Mutual TLS (MTLS) is enabled, install all required Microsoft Trusted Root certificates on the SBC.

Continue with:

- SIP signaling
- Media traffic
- Supported Session Border Controllers (SBCs)
- Support boundaries

## SIP signaling

Direct Routing supports Microsoft 365, Office 365, Office 365 GCC, GCC High, and DoD environments. Each environment uses dedicated SIP connection points to establish secure signaling between your Session Border Controller (SBC) and Microsoft Teams.

The following sections describe the required Fully Qualified Domain Names (FQDNs), ports, and failover behavior used for Direct Routing.

### SIP signaling: FQDNs

For Microsoft 365, Office 365, and Office 365 GCC, configure the following connection points in priority order.

| Priority | FQDN | Purpose |
| --- | --- | --- |
| Primary | `sip.pstnhub.microsoft.com` | Primary global connection point. |
| Secondary | `sip2.pstnhub.microsoft.com` | Secondary regional failover endpoint. |
| Tertiary | `sip3.pstnhub.microsoft.com` | Tertiary regional failover endpoint. |

FQDNs in case SBC uses IPv6

| Priority | IPv6 FQDN | Purpose |
| --- | --- | --- |
| Primary | `sip.ipv6.pstnhub.microsoft.com` | Primary global connection point. |
| Secondary | `sip2.ipv6.pstnhub.microsoft.com` | Secondary regional failover endpoint. |
| Tertiary | `sip3.ipv6.pstnhub.microsoft.com` | Tertiary regional failover endpoint. |

These FQDNs provide:

- Geographic routing to the nearest Microsoft datacenter.
- Automatic failover during service interruptions.
- High availability for SIP signaling.

The FQDNs resolve to Microsoft IP ranges:

- 52.112.0.0/14
- 52.120.0.0/14

In the case of IPv6 the FQDNs resolve to Microsoft IP range:

- 2603:1063:400::/40

Important

Configure your firewall to allow signaling traffic to and from all Microsoft Teams IP ranges, not only the addresses returned from DNS queries.

### SIP signaling: GCC High

For Office 365 GCC High, use:

`sip.pstnhub.gov.teams.microsoft.us`

### SIP signaling: DoD

For Office 365 DoD, use:

`sip.pstnhub.dod.teams.microsoft.us`

Because these environments operate within dedicated Microsoft Government clouds, secondary and tertiary FQDNs aren't required.

## SIP signaling ports

Direct Routing requires the following SIP/TLS ports.

| Traffic | From | To | Destination Port |
| --- | --- | --- | --- |
| SIP/TLS | SBC | Microsoft SIP Proxy | 5061 |
| SIP/TLS | Microsoft SIP Proxy | SBC | Configured on the SBC |

## SIP signaling failover

Microsoft automatically directs the SBC to the nearest healthy datacenter.

If the primary region becomes unavailable:

1. Microsoft redirects traffic to the secondary region.
2. If necessary, traffic is redirected to the tertiary region.
3. Existing resiliency mechanisms help maintain service continuity.

No manual administrator intervention is required.

## Media traffic

Media traffic uses Microsoft Media Processors unless Media Bypass is enabled.

For Media Bypass planning guidance, see [Plan for Media Bypass with Direct Routing](direct-routing-plan-media-bypass).

## Media processor IP ranges

### Microsoft 365 / Office 365

Allow media traffic for:

- 52.112.0.0/14
- 52.120.0.0/14

In case of IPv6 allow media traffic for:

- 2603:1063:400::/40
- 2603:1063:100::/40

### GCC High

- 52.127.88.0/21

### DoD

- 52.127.64.0/21

## Media ports

The following ports are used for media.

| Traffic | From | To | Ports |
| --- | --- | --- | --- |
| UDP/SRTP | Media Processor | SBC | 3478–3481, 49152–53247 |
| UDP/SRTP | SBC | Media Processor | 3478–3481, 49152–53247 |

Tip

Microsoft recommends allocating at least two media ports per concurrent call on the SBC.

## Media processor locations

Microsoft media processors are deployed globally to optimize call quality and reduce latency.

Regions include:

- North America
- Europe
- Asia
- Japan
- Australia
- Latin America

Media is routed to the closest available Microsoft datacenter whenever possible.

## Supported codecs

Direct Routing supports the following codecs between Microsoft Teams and the SBC.

- SILK
- G.711
- G.722
- G.729
- AMR-WB (non-bypass only)

Administrators can prioritize or restrict codecs on the SBC according to organizational requirements.

Note

Microsoft doesn't support media re-targeting during an active Direct Routing call.

## Supported Session Border Controllers (SBCs)

Only Microsoft-certified SBCs are supported with Direct Routing.

Microsoft validates certified SBCs through interoperability testing to ensure compatibility with Microsoft Teams Phone.

For the latest list of certified devices, see:

[Session Border Controllers certified for Direct Routing](direct-routing-border-controllers)

## Support boundaries

Microsoft supports Teams Phone with Direct Routing only when certified SBCs are used.

If issues occur:

1. Contact your SBC vendor.
2. The vendor investigates the issue.
3. If necessary, the vendor escalates the issue to Microsoft through established support channels.

Customers should provide the vendor investigation report when opening Microsoft support requests.

Microsoft may decline support requests involving non-certified SBCs.

## Best practices

For the best Direct Routing experience, Microsoft recommends that you:

- Deploy certified SBCs.
- Configure redundant SIP connectivity.
- Use trusted public certificates.
- Configure all Microsoft-required firewall rules.
- Monitor call quality after deployment.
- Test failover scenarios before production rollout.
- Review Microsoft Teams network planning guidance before deployment.

## Verify your deployment

After completing configuration:

- Verify that the SBC reports a healthy connection to Microsoft Teams.
- Validate inbound PSTN calling.
- Validate outbound PSTN calling.
- Verify emergency calling functionality if configured.
- Test failover between SIP connection points.
- Confirm voice routing policies are assigned correctly.
- Validate call quality across representative user scenarios.

## Example deployment

Many organizations deploy Direct Routing alongside other Microsoft Teams PSTN connectivity options.

For example:

| User type | PSTN connectivity |
| --- | --- |
| Knowledge workers | Operator Connect |
| Frontline and mobile workers | Teams Phone Mobile |
| Contact centers | Direct Routing |
| Analog devices and legacy PBXs | Direct Routing |
| Small satellite offices | Microsoft Calling Plan |

This flexible approach allows organizations to optimize PSTN connectivity for different user populations while maintaining a single Microsoft Teams tenant.