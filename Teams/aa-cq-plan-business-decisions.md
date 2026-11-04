---
layout: Conceptual
title: Planning - Business decisions for voice applications - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-business-decisions
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
customer-intent: As a Teams Administrator, I want to learn about the decisions I need to make in order to determine how and when to use Teams Phone Agents, Auto Attendants, or Call Queues and their various features within my organization.
description: Learn the business decisions to make before configuring voice applications, including languages, hours, agents, and compliance.
locale: en-us
document_id: 3504c3e2-6c61-d376-f295-aeb5bb301327
document_version_independent_id: 3504c3e2-6c61-d376-f295-aeb5bb301327
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-business-decisions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-business-decisions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-business-decisions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
platformId: 1333a596-cb86-083a-1d2f-1e3cc32fe456
---

# Planning - Business decisions for voice applications - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to understand the business decisions to make before you configure Teams Phone Agents, Auto Attendants, and Call Queues.

## Business decisions

### General decisions

Before you set up your Teams Phone Agents, Auto Attendants, and Call Queues, there are some decisions that you should make about how to use these features in your business.

Document your answers to these questions and provide the information to the administrator doing the configuration.

- How do callers reach you? Internally only? Externally? Click-to-call on the web?
- What languages do you need? Where are these languages needed - which department or group?
- Do you want to allow voice inputs from callers or only dialing inputs?
- Do you need separate call routing for off hours or holidays? What are the hours and holidays?
- Do you want to allow representatives (agents) in a call queue to opt out of taking calls?
- Do you want representatives in your call queues or your operator to have a specific caller ID if they dial out?
- For the voice prompts, do you want to record your own or use the system-generated voice? (The system-generated voice is easy to update.)
- Do you want to delegate certain auto attendant and call queue administrative tasks to authorized users?
- Do you want to enable Shared Call History?
- Are there any compliance recording requirements?

### Call queue decisions

#### Call queue representatives

Representatives (agents) can be added to call queues in the following ways:

- Option 1
    - Individual users (maximum 20)
    - Distribution lists
    - Microsoft 365 security groups, including mail-enabled security groups
- Option 2
    - Teams channels
- Option 3
    - [Shifts in Microsoft Teams](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6)

Tip

For Option 1, Microsoft 365 security groups are recommended.

We recommend choosing a strategy for adding representatives to queues before you start your configuration.

### Migrating phone numbers

If you have existing auto attendants and call queues that you're migrating to Teams, you need a plan to transfer your existing phone numbers to the new Teams Phone Agents, Auto Attendants, and Call Queues. You might need to create a [port order](phone-number-calling-plans/port-order-overview) to move your numbers from another provider.

Tip

We recommend that you temporarily acquire one or more new phone numbers and test your call flows in Teams before moving your numbers from another provider.