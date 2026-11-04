---
layout: Conceptual
title: Encryption in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-encryption
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how Microsoft Teams uses multiple layers of encryption to help protect business communications, including standard encryption and end-to-end encryption (E2EE).
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: v-bilchenko, willdixon
ms.date: 2026-08-28T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
ms.collection:
- M365-collaboration
- purview-compliance
ms.custom: security
search.appverid: MET150
f1.keywords: NOCSH
audience: admin
locale: en-us
document_id: 35eff1e7-d892-4dc8-d907-2a551b1673d2
document_version_independent_id: 35eff1e7-d892-4dc8-d907-2a551b1673d2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-encryption.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-encryption
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-encryption.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5cf461ba-0866-b56d-8dc1-d48eb29a412e
---

# Encryption in Microsoft Teams - Microsoft Teams | Microsoft Learn

## Overview

Microsoft Teams uses multiple layers of encryption to help protect data in transit and at rest across chats, calls, meetings, and file sharing. Standard encryption applies to Teams communications by default and requires no configuration by users or admins. End-to-end encryption (E2EE) adds a further layer for one-to-one calls and for meetings configured to require it, so that only the communicating parties can access the content.

Organizations exchange confidential information, including intellectual property, financial data, and personally identifiable information (PII). Encryption helps protect this information in transit and at rest, and supports compliance with regulatory requirements. Without encryption, this information could be vulnerable to interception and unauthorized access.

## Regulatory frameworks that require or recommend encryption

Several regulatory frameworks require or recommend encryption as a safeguard for protecting sensitive data:

- **General Data Protection Regulation (GDPR)**: Requires appropriate technical measures to help ensure data security, with encryption specifically mentioned as a recommended safeguard for protecting personal data.
- **Health Insurance Portability and Accountability Act (HIPAA)**: Includes encryption as an addressable implementation specification for electronic protected health information, which is relevant to healthcare organizations and their business associates.
- **Payment Card Industry Data Security Standard (PCI DSS)**: Requires encryption of cardholder data transmitted over open, public networks to help protect financial information.
- **California Consumer Privacy Act (CCPA) and California Privacy Rights Act (CPRA)**: Provide safe harbor provisions for encrypted data in certain circumstances, which can reduce liability in the event of a data breach.
- **NIST Special Publication 800-53**: Includes controls related to cryptographic protection of information, which many federal and commercial organizations use as a security baseline.

## Encryption layers in Microsoft Teams

Microsoft Teams uses multiple layers of encryption to protect different types of data throughout the communication process. These layers include transport layer encryption, platform-level encryption, service encryption, customer key encryption, and end-to-end encryption (E2EE).

### Standard encryption in Microsoft Teams

In addition to supporting the compliance requirements described earlier, standard encryption in Teams helps protect data in transit and at rest without additional configuration by users or admins. It includes:

- **Transport Layer Security (TLS)**: Helps secure data in transit by using TLS 1.2 or later with AES-256, protecting information as it moves between devices and Microsoft servers.
- **Data at rest encryption**: Helps protect data stored in Azure, SharePoint, OneDrive, and other Microsoft 365 services by using a combination of BitLocker disk encryption and per-file encryption.
- **Service encryption**: Adds a layer of protection by encrypting Teams data before it's sent to the data store using keys managed by Microsoft. Service encryption is available for media content, and additional services are being explored.
- **Customer Key encryption**: With Bring Your Own Key (BYOK), organizations can provide their own encryption keys for greater control over their security posture. Encrypting Teams content with customer-managed keys is supported through integration with Microsoft Purview Customer Key, and can apply to Teams files, chat messages, and other modalities.

### End-to-end encryption (E2EE) in Microsoft Teams

E2EE helps ensure that only the communicating parties can access the content. Key characteristics of E2EE in Teams include:

- **Implementation**: Encryption keys are generated on user devices and exchanged over a secure signaling session. This capability is available for one-to-one calls and for meetings when configured. The Supported modalities table later in this article lists the supported communication modalities.
- **Enabling E2EE**: Admins configure the E2EE policy at the tenant level.

    - For one-to-one calls, E2EE is disabled by default. An admin must enable E2EE, and both participants must then turn it on in their Teams client settings for the call to be end-to-end encrypted.
    - For meetings, the admin policy that allows E2EE is enabled by default, but a meeting is end-to-end encrypted only when the organizer configures the meeting to require E2EE when scheduling. E2EE for meetings requires Teams Premium.
- **Technical details**: Teams uses DTLS to encrypt peer-to-peer media for both E2EE calls and meetings.

    - For one-to-one calls, encryption keys are generated on each participant's device and exchanged over a secure signaling session.
    - For meetings, Teams uses a Group Key Manager Protocol (GKMP) to negotiate keys among all clients, and GKMP requests are distributed over channels secured with TLS 1.3.

    In both cases, media is encrypted by using GCM\_AES\_256. This encryption covers audio, video, and video-based screen sharing. It doesn't cover chat.
- **Availability and limitations**: E2EE is available for one-to-one calls and for meetings that are configured to require E2EE (meeting support is a Teams Premium feature). It provides additional protection for audio, video, and screen sharing in these experiences.

For prerequisites, policy configuration, and supported platforms and devices, see [Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls](teams-end-to-end-encryption).

#### Supported modalities

Different communication modalities within Teams have varying encryption capabilities.

| Modalities and features | Standard encryption | E2EE available |
| --- | --- | --- |
| One-to-one calls^1^ | Yes | Yes |
| Scheduled meetings | Yes | Yes^2^ |
| Screen sharing | Yes | Yes^2^ (in E2EE-enabled meetings and one-to-one calls) |
| Video | Yes | Yes^2^ (in E2EE-enabled meetings and one-to-one calls) |
| Group calls | Yes | No |
| Channel meetings | Yes | No |
| Chat messages | Yes | No |
| Shared files | Yes | No |
| Meeting recordings | Yes | No |
| Meeting transcripts | Yes | No |
| Meeting recap | Yes | No |

^1^Teams supports E2EE for eligible one-to-one VoIP calls. E2EE isn't available for calls that involve the Public Switched Telephone Network (PSTN).

^2^Users must have a Teams Premium license.

Note

Participant limits and device requirements apply to end-to-end encrypted meetings. For more information, see [Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls](teams-end-to-end-encryption).

#### E2EE availability

End-to-end encryption for one-to-one calls made through Teams is available to commercial Teams users. Customers with a Teams Premium license can also use E2EE in scheduled Teams meetings.

#### Other encrypted voice and messaging options

By default, all Teams communications, including voice calls, meetings, and chat, are encrypted by using industry-standard technologies such as Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP).

#### Impact of E2EE on product functionality and compliance

E2EE isn't compatible with certain service-side capabilities. When E2EE is in use, features such as recording, transcription, and related AI-powered capabilities like intelligent meeting recap aren't available. It also limits server-side data retention and records management capabilities, such as eDiscovery.

E2EE isn't compatible with compliance recording. If your organization uses compliance recording, a user who is subject to it can't join an end-to-end encrypted call or meeting.

#### Security concepts in Microsoft Teams

Microsoft applies security principles such as Zero Trust and least-privileged access, building on authentication provided by Microsoft Entra ID, and gives admins options to customize policies to meet their organization's needs. This includes Customer Key for data at rest in the cloud, which builds on service encryption and lets customers provide and control encryption keys for an added layer of control.

## Selecting an encryption approach

Choosing between standard encryption and E2EE involves balancing security requirements with operational needs and compliance obligations. E2EE is suited to high-sensitivity scenarios, such as executive communications and regulated industries, while standard encryption is appropriate for day-to-day operational discussions and team collaboration.

## Considerations for implementation

Certain Microsoft 365 capabilities rely on access to stored content, including search, transcription, translation, data loss prevention (DLP), retention, eDiscovery, supervisory review, and Microsoft Copilot experiences.

Organizations can define how different types of communications are protected based on sensitivity, regulatory requirements, and operational needs, as part of a broader security architecture that includes Microsoft Teams. A hybrid approach, using standard encryption for general use and E2EE for specific high-sensitivity scenarios, can help balance security and operational requirements.

A risk-based approach to encryption in Teams lets organizations protect their communications while maintaining collaboration capabilities.

For more information, see [Security and compliance in Microsoft Teams](security-compliance-overview).