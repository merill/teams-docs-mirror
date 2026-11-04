---
layout: Conceptual
title: Planning - Teams Phone Agent - Usage-based-billing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-teams-phone-agent-ubb
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-11-03T00:00:00.0000000Z
ms.topic: concept-article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams administrator, I want to learn about usage-based billing and how it applies to Teams Phone Agent so I can configure spending policies.
description: Learn how usage-based billing applies to Teams Phone Agent.
locale: en-us
document_id: c075dc4f-c237-1c24-0e3f-6ffef400b873
document_version_independent_id: c075dc4f-c237-1c24-0e3f-6ffef400b873
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-teams-phone-agent-ubb.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-teams-phone-agent-ubb
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-teams-phone-agent-ubb.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: 9ab966d6-02b6-1f4c-03d9-3350d0445ac5
---

# Planning - Teams Phone Agent - Usage-based-billing - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

This article is for IT pros and Teams administrators who want to learn about usage-based billing and how it applies to Teams Phone Agent.

## Usage-based billing overview

Microsoft's usage-based billing model charges customers based on actual usage, measured in Copilot Credits.

Depending on the service, organizations can use fixed licensing, the Copilot Credit Pre-purchase Plan (P3), pay-as-you-go billing, prepaid capacity packs, or supported combinations of these billing methods. Administrators use the Cost management dashboard in the Microsoft 365 admin center to govern access, establish spending controls, manage credit requests, and monitor consumption.

## Copilot credits

Copilot Credits are a common currency for eligible Microsoft services with usage-based billing.

For more information about licensing details for Copilot Credits and services, see the [Copilot Credits Guide.](https://go.microsoft.com/fwlink/?LinkId=2383615)

For more information, see [Understand usage-based billing and cost management for Copilot Credits](/en-us/microsoft-365/copilot/usage-based-billing-overview-copilot-credits).

Use the [Copilot Credit Estimator](https://nptnlopcost-ppe-h8b6dtchacfcgqhk.b02.azurefd.net/#/estimator) to understand Teams Phone Agent costs.

## Teams Phone Agent and Copliot credits

Teams Phone Agent requires an assigned, funded Copilot spending policy.

Teams Phone Agent checks the spending policy at the start of each incoming call. **If no policy exists or the policy isn't funded, Teams Phone Agent acts as an auto attendant.**

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)

## Known issues

None.