---
layout: Conceptual
title: Reference - Getting Started - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-reference-getting-started
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
ms.topic: reference
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
customer-intent: As a Teams Administrator, I want to get started designing and implementing my call flows in Teams Phone Agent, Auto Attendant, and Call Queue.
description: Get started with voice applications, from designing call flows and resource accounts to creating holidays and provisioning.
locale: en-us
document_id: d094c938-d577-f1bf-60e0-690d94df3933
document_version_independent_id: d094c938-d577-f1bf-60e0-690d94df3933
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-reference-getting-started.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-reference-getting-started
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-reference-getting-started.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: d3ba1bcc-65c0-fdd4-e7cb-2e88002ee7ab
---

# Reference - Getting Started - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who are ready to start setting up their Teams Phone Agents, auto attendants, and call queues.

## Getting started

Once you complete the planning tasks in this series, follow these steps to get your auto attendants and call queues set up:

1. [Design call flows](aa-cq-design-call-flows) to identify the number of resource accounts, Teams Phone Agents, auto attendants, call queues, and associated configuration items you need.
2. [Plan for Auto Attendant and Call Queue authorized users](aa-cq-plan-authorized-users) who can be responsible for administrative changes to auto attendants or call queues.
3. Get a [Teams Phone Resource Account license](teams-add-on-licensing/virtual-user) for each resource account that you plan to create. These licenses are free, so we suggest getting a few extra in case you decide to make changes to your resource accounts in the future.
4. [Create a resource account](aa-cq-manage-resource-accounts) for each Teams Phone Agent, auto attendant, and call queue that directly answers calls.
5. Assign a Teams Phone Resource Account license to each resource account.
    - If the resource account is used to transfer calls externally, assign a pay-as-you-go license or communications credits to the resource account.
6. Get service numbers for the Teams Phone Agents, auto attendants, and call queues that you want phone callers from outside your organization to call.
    - For more information about service numbers, see [transferring numbers from another provider](phone-number-calling-plans/transfer-phone-numbers-to-teams) or [requesting new service numbers](getting-service-phone-numbers).
7. Create click-to-call configurations for the [Teams Phone Agent/Auto Attendant](/en-us/azure/communication-services/quickstarts/voice-video-calling/get-started-teams-auto-attendant) and [Call Queues](/en-us/azure/communication-services/quickstarts/voice-video-calling/get-started-teams-call-queue) that you want users on your website or in your mobile applications to call.
8. [Create the holidays](aa-cq-setup-holidays) for which you want to have separate call routing in your auto attendants.
9. Create the groups, Teams channels, or Shifts scheduling groups that you want to use to contain the representatives (agents) for the call queues.
10. If you plan to enable dial by extension, ensure that you add your users' extension numbers to their Microsoft Entra ID profiles.

Once you complete these steps, you're ready to create your Teams Phone Agents, auto attendants, and call queues. Refer to the workflow diagram that you created to determine what should be created first.

In the example diagram, we recommend creating the sales and support call queues before the Contoso main auto attendant, because the auto attendant needs to direct callers to the queues.

See the following articles for information on how to create Teams Phone Agents, auto attendants, and call queues:

- [Teams Phone Agent](aa-cq-setup-teams-phone-agent)
- [Auto Attendant](aa-cq-setup-auto-attendant)
- [Call Queue](aa-cq-setup-call-queue)

Important

A user's Microsoft Entra ID GUID token is stored as part of the auto attendant or call queue configuration when the user is configured as:

- an auto attendant or call queue **Authorized user**.
- an auto attendant **Operator**.
- a **Person in Organization** transfer point.
- an individual member of a call queue.

The Teams Phone Agent, auto attendant, and call queue configurations aren't synchronized with Microsoft Entra ID lifecycle events. Teams administrators need to manually update configurations to remove this personal data when a user included in the configuration leaves the organization.

This doesn't apply to call queue representative memberships that are configured via distribution lists or channels. It also doesn't apply to users who are reached through the **Dial by Name** or **Dial by Number** feature of auto attendants.

## Alternate provisioning tools

[Auto Attendant and Call Queue Backup and Bulk Provisioning Tools](https://github.com/MicrosoftDocs/Teams-Auto-Attendant-and-Call-Queue-Backup-and-Bulk-Provisioning-Tools/) are a set of tools that provide a way to configure auto attendants, call queues, and authorized users through Excel spreadsheets and PowerShell scripts.

## Previous planning articles

- [Overview](aa-cq-plan-overview)
- [Questions and Answers tools (Teams Phone Agent)](aa-cq-plan-teams-phone-agent-tools-questions-answers)
- [Appointments tools (Teams Phone Agent)](aa-cq-plan-teams-phone-agent-tools-appointments)
- [Agents and Queues (Teams Phone Agent)](aa-cq-plan-teams-phone-agent-agents-queues)
- [Spam detection (Teams Phone Agent)](aa-cq-plan-teams-phone-agent-spam-detection)
- [Usage-based billing (Teams Phone Agent)](aa-cq-plan-teams-phone-agent-ubb)
- [Third-party voice agents](aa-cq-plan-third-party-voice-agents)
- [Holidays](aa-cq-plan-holidays)
- [Authorized users](aa-cq-plan-authorized-users)
- [Shared Call History](aa-cq-plan-shared-call-history)
- [Call priorities for call queues](aa-cq-plan-call-queue-priorities)
- [Recording calls](aa-cq-plan-recording)
- [Templates and resources](aa-cq-plan-templates-resources)
- [Business decisions for Teams Phone Agents, Auto Attendants, and Call Queues](aa-cq-plan-business-decisions)
- [Nested call flows](aa-cq-plan-nesting)
- [Reporting considerations](aa-cq-plan-reporting)
- [Technical prerequisites and licensing requirements](aa-cq-reference-prerequisites-licensing)
- [Design call flows](aa-cq-design-call-flows)
- [Supported configurations](aa-cq-reference-limits-supported-configurations)