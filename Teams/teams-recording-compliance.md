---
layout: Conceptual
title: Microsoft Teams compliance recording (third-party) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-recording-compliance
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: yasmineh
ms.date: 2026-07-20T00:00:00.0000000Z
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
ms.reviewer: kkodali
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about Teams third-party compliance recording for calling, meetings, events, and live events.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- m365initiative-meetings
- m365initiative-voice
- purview-compliance
locale: en-us
document_id: 509f3601-ed4e-c31d-a5db-6e558b155104
document_version_independent_id: 509f3601-ed4e-c31d-a5db-6e558b155104
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-recording-compliance.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-recording-compliance
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-recording-compliance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0db78243-a4c8-2d91-01e6-bab6f1fe14ae
---

# Microsoft Teams compliance recording (third-party) - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Calls![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Call queues

## Compliance recording overview

Compliance recording is the process of recording and storing communications in a way that follows local, national, and global regulatory requirements.

Microsoft Teams is enhanced to offer compliance recording of call and meeting communications by supporting integrations with certified, third-party, compliance recording solutions.

Using a partner solution to record Teams calls, meetings, and events lets compliance officers securely capture required communications to meet regulations like MiFID II, Dodd-Frank, FDCPA, HIPAA, and GDPR.

Compliance recording partner solutions are integrated with Teams as shown in the following diagram:

[![Diagram of the flow for when a Teams meeting or call is sent and received.](media/compliance-recorder-small.png)](media/compliance-recorder-expandable.png#lightbox)

The Graph API supporting the third-party application’s recording status is available in the following national cloud deployments:

| Global Service | US Government L4 | US Government L5 (DOD) | China operated by 21Vianet |
| --- | --- | --- | --- |
| Yes | Yes | Yes | No |

This solution is designed specifically to turn on policy-based compliance recording with Teams. Any other use of this solution isn't supported.

## Supported compliance recording capabilities

As a Teams communications admin using a third-party compliance recording solution, you can set when to record calls, meetings, and events for processing and retention under corporate or regulatory policies.

From the available APIs and third-party compliance recording solutions, the following capabilities are supported:

| Persona | Capabilities |
| --- | --- |
| Recorded users | - Be notified when recording is in progress.<br>- Be informed when policy and/or recorder error is causing changes in calling behavior. |
| Communications admin | - Understand why and how to apply / enforce recording policies to Teams users / endpoints.<br>- Configure and maintain Teams recording policies for the organization.<br>- Monitor and troubleshoot recording-related issues with Teams calls and meetings.<br>- Support internal compliance officer with operational analytics on usage, quality, and reliability. |
| Compliance officer | - Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.<br>- Search for interactions based on communication-related metadata or interaction content. Common examples include:<br><br>    - **Metadata** - Participants, time, direction, dialed number, origin number, Custom business data.<br>    - **Content** – Transcription, sentiment, phonetics, related interactions.<br>- Analyze and interact with collected communications, including the ability to monitor interactions as they're being collected.<br>- Ensure security of collected communications and prevent tampering at all stages. |

For general Teams recording capabilities, see [Teams recordings.](teams-recording-policy).

#### Considerations

Compliance recording isn't supported for:

- E911 emergency calling services
- Users operating in Survivable Branch Appliance mode
- Public Switched Telephone Network (PSTN) Calls for India users

**Large meetings**

The Compliance Recording platform is optimized for meetings and tested to scale up to 750 users per meeting. However, performance might be impacted during meetings with over 750 users in paired bot mode. We're actively working on improvements in a future update to enhance the experience.

- For extra-large meetings, the guidance is to use events [optimized for large audiences](plan-events), such as town halls, as the meeting type.
- Contact your recording partner for more information.

**Call queues (Compliance Recording for Call Queues)**

Compliance Recording for Call Queues records all agent answered inbound call queue calls without the need to assign a compliance recording policy to the agents. Compliance Recording policies assigned to call queue agents are not supported.

Compliance Recording for Call Queues works with all agent routing options and conference mode must be enabled.

If there's a need to record outbound calls made by the agents in a call queue, they must have a [compliance recording policy](teams-compliance-recording-setup#create-and-manage-your-compliance-recording-policy) assigned to them. For compliance recording purposes, these calls are considered outbound user calls and won't be associated with the call queue. This will be addressed in a future release of Compliance Recording for Call Queues.

If there's a need to record a user's non-call queue inbound and outbound calls they must have a compliance recording policy assigned to them.

After verifying the correct licensing and [creating a compliance recording application instance](teams-compliance-recording-setup#create-a-compliance-recording-application-instance), see [Configure compliance recording for call queues](aa-cq-setup-call-queue-template-recording-compliance) for more information.

**Licensing**

To be eligible for compliance recording, a user account must be equipped with any one of the following licenses:

- Microsoft 365 A3/A5/E3/E5/G3/G5/Business Premium/Business Standard
- Office 365 A3/A5/E3/E5
- Microsoft Teams Room (Pro or Basic) license
- Teams Shared Device license

## Supported notification methods

Users with an assigned compliance recording policy know that their digital interactions with Teams are being recorded. Depending on the third-party recording solution and how it's configured, users might not be able to disable the recording and might not have access to the recording.

Compliance recording notifications are supported for the Teams client experiences. The experiences can be both visual and audio.

### Teams clients - visual notice

- Desktop/web
- Mobile (iOS/Android)
- Teams Phones
- Teams rooms

### Other endpoints - audio notice

- SIP phones
- Skype for Business
- Audio conferencing (audio notice in dial-in number's default or user-selected language)
- PSTN callers (audio notice in Teams user's default language)

## Recorder development

The solution for Teams compliance recording is achieved through Microsoft’s third-party partners who develop compliance recording bots, and pair the bot with their recording solution. Each partner solution varies, but each partner uses the same key Graph APIs, an application instance, and a compliance recording policy.

The recording bot has the following requirements:

- Recorder bot must run on a Windows Virtual Machine and be deployed in Azure
- Recorder bot outbound firewall destination IP address must be open to the [Azure public IP range](https://www.microsoft.com/download/details.aspx?id=56519)
- Recorder bot inbound firewall source IP address must be open to the [Teams IP range](https://www.learn.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

For a sample of developing a compliance recording bot, see [deploying and testing a sample bot](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot#bot-registration).

## Third-party compliance recording partners

Microsoft created a compliance recording for Microsoft Teams certification program while making Teams APIs available for partners to develop and integrate compliance recording solutions. This program provides customers with the assurance that each participating partner's solution is tested and verified to provide the quality, compatibility, and reliability expected from a Microsoft solution.

If you're a vendor seeking to join the certification program, fill out the calling platform intake as the next step. [Calling Platform Intake](https://aka.ms/CallingPlatformIntake).

For a list of partners certified to deliver a compliance recording solution with Microsoft Teams, see [Policy-based recording solutions certified for Microsoft Teams](https://cloudpartners.transform.microsoft.com/compliance-recording-solutions)

This list gets updated as more partners join and meet the certification criteria.

The following list includes partners certified to deliver a compliance recording solution with Microsoft Teams:

| Partner | Solution website |
| --- | --- |
| ASC Technologies | https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html |
| AudioCodes Interaction Insights | https://www.audiocodes.com/applications/interaction-insights-enterprise-compliance-call-recording |
| CallCabinet | https://www.callcabinet.com/compliance-microsoft-teams-call-recording |
| Cloud World Wide Services | https://recordia.net/microsoft-teams-call-recording/ |
| Dubber | https://www.dubber.net/call-recording/ |
| Imagicle | https://www.imagicle.com/en/products/call-recording/ |
| Insightful Technology | [https://insightfultechnology.com/teams/](https://insightfultechnology.com/market-place/) |
| Liquid Voice | https://www.liquidvoice.com/microsoft-teams-recording/ |
| Luware | https://luware.com/en/solution/microsoft-teams-recording/ |
| NUSO | https://nuso.cloud/nuso-connect-recorder/ |
| NICE Engage | [https://www.nice.com/products/recording/engage](https://www.nice.com/products/recording-management) |
| NICE NTR-X | https://www.niceactimize.com/compliance/ms-teams-recording.html |
| Numonix | https://numonix.cloud |
| Subphonic | https://www.subphonic.ai/products/focus#teams |
| Theta Lake | https://thetalake.com/integrations/microsoft/ |
| Tollring | https://tollring.com/compliance-recording-for-microsoft-teams/ |
| Touch Call Recording | https://touchcallrecording.com/teams-policy-based-recording-for-callings-and-meetings |
| Verint Verba | https://www.verba.com/solutions/microsoft-teams-recording |
| Verint EDM | https://www.verint.com/enterprise-recording-engagement-data-management/ |

The following partners are in the process of certifying their solution for Microsoft Teams:

| Partner | Solution website |
| --- | --- |
| Eleveo | https://www.eleveo.com/call-center-recording |
| Redwood Technologies | https://www.contentguru.com/solutions/needs/compliance-recording-ms-teams/ |
| Uniphore | https://www.uniphore.com/products/customer-service-ai/communication-recording-agent/ |
| Vox Solutions | https://voxsolucoes.com.br/vox-teams-recorder/ |

## Support boundaries

Microsoft only supports compliance recording solutions from the listed, certified partners. If there are enablement or operational issues, you must contact your compliance recording partner first. If the partner determines the issue is with Microsoft, they might ask you to raise a case with Microsoft, providing context of the investigation completed by the partner. If needed, the partner can bring the issue to Microsoft through their Microsoft support channel. Microsoft reserves the right to reject support cases where a non-certified Compliance Recording solution is used. If Microsoft determines that the issue is originating with a partner's compliance recording solution, the customer needs to re-engage the compliance recording partner for further support.

### Related articles

- [Introduction to Teams recording](teams-recording-policy)
- [Overview- Recording and transcription for Teams meetings and calls](recording-transcription-overview)
- [Set up compliance recording in Microsoft Teams](teams-compliance-recording-setup)
- [Configure a custom banner for compliance recording in Microsoft Teams](teams-compliance-recording-custom-banner)