---
layout: Conceptual
title: Planning - Call priorities for Call Queues - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-call-queue-priorities
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
ms.topic: concept-article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.date: 2026-11-03T00:00:00.0000000Z
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
customer-intent: As a Teams Administrator, I want to learn about call priorities for call queues so I can prioritize important callers or callers with time-critical issues to the front of the queue.
description: Learn how call priorities move high-priority callers to the front of a call queue, with scenarios for dialed number, menu choice, and transferred calls.
locale: en-us
document_id: e029bf5f-deaa-e110-78d0-1049bf3c4393
document_version_independent_id: e029bf5f-deaa-e110-78d0-1049bf3c4393
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-call-queue-priorities.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-call-queue-priorities
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-call-queue-priorities.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: ad72f5a3-c9bb-5013-7b30-7236d3f31d6f
---

# Planning - Call priorities for Call Queues - Microsoft Teams | Microsoft Learn

This article is for IT pros and administrators who want to implement **call priorities** for call queues.

## Call priorities

**Call priorities** ensure high-priority calls are at the front of the queue and presented to representatives (agents) first, while lower-priority calls are presented later.

When a representative becomes available to take a call, they receive the highest-priority call that has been waiting the longest. If there are multiple calls with the same priority level, the one that has been waiting the longest is presented to the representative first.

There are five different levels of call priority, 1 to 5, with 1 being the highest priority and 5 being the lowest priority:

1. Very High
2. High
3. Normal (default priority)
4. Low
5. Very Low

## Call priority call flow scenarios

### Scenario 1: Priority to callers based on dialed number

In this scenario, Contoso Support has a single Technical Support call queue that's open 24/7. Contoso's website and documentation provide their customers with the general number for all support requests. Customers who sign up for "enhanced support" are given a dedicated number to call. The enhanced support customers are given priority over other customers based on the level of enhanced support purchased.

Contoso Support defines the following call priorities for their resource accounts:

- **Priority 4** - Any customer calling the general support phone number.
- **Priority 3** - Customers calling the Bronze level support phone number.
- **Priority 2** - Customers calling the Silver level support phone number.
- **Priority 1** - Customers calling the Gold level support phone number.

Customers in the call queue are presented to representatives in the order of their priority. The Gold level customers are all presented first, followed by Silver, Bronze, and finally general support customers.

![Call flow diagram for Scenario 1: callers to the general, Bronze, Silver, and Gold support numbers are assigned priorities 4, 3, 2, and 1 in the Technical Support call queue.](media/aa-cq/aa-cq-call-priorities-scenario-1.svg)

### Scenario 2: Priority to callers based on auto attendant menu choices

In this scenario, Contoso Travel has a single Travel Support call queue for all travel inquiries. This call queue is associated with an auto attendant that provides callers with the following options:

> 
> Thank you for calling Contoso Travel. If you are currently traveling and need immediate assistance, press 1. If you are calling to inquire about an existing booking, press 2. To make a new booking, press 3. For all other inquiries, press 4.

Callers who press 1 get top priority and connect to representatives first, followed by callers who press 2, 3, and 4 in decreasing order of priority.

![Call flow diagram for Scenario 2: an auto attendant routes callers to the Travel Support call queue with priority set by the menu option pressed, 1 through 4.](media/aa-cq/aa-cq-call-priorities-scenario-2.svg)

### Scenario 3: Priority to representatives transferring calls to another call queue

In this scenario, Contoso Finance Customer Service representatives triage calls and often transfer them to Tier 2 Support groups. Tier 2 Support groups can also take calls directly from customers. Contoso wants calls transferred from Customer Service to take priority over calls dialed directly into Tier 2 Support, as these callers have already waited and spoken with a representative.

![Call flow diagram for Scenario 3: calls transferred from Customer Service receive higher priority in the Tier 2 Support call queue than calls dialed in directly.](media/aa-cq/aa-cq-call-priorities-scenario-3.svg)

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

None.