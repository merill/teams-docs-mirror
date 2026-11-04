---
layout: Conceptual
title: Planning - Nested Call Flows - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-nesting
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
customer-intent: As a Teams Administrator, I want to learn how to nest Teams Phone Agents, Auto Attendants, and Call Queues within my organization, and the implications of the various methods.
description: Learn how to nest Teams Phone Agents, auto attendants, and call queues to build multi-level call flows, with or without resource accounts.
locale: en-us
document_id: 8c9acdb2-1fea-fa50-72e2-22c8eebc3b44
document_version_independent_id: 8c9acdb2-1fea-fa50-72e2-22c8eebc3b44
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-nesting.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-nesting
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-nesting.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 02345430-8b3a-1621-5c1f-8c11f13bab89
---

# Planning - Nested Call Flows - Microsoft Teams | Microsoft Learn

This article is for IT pros and administrators who want to link Teams Phone Agents, Auto Attendants, and Call Queues to build multi-level call flows.

## Nested call flows

A nested call flow is when a parent auto attendant or call queue routes calls to another auto attendant or call queue. The second auto attendant or call queue is *nested* behind the first one.

In this example, the Travel call queue is nested behind an auto attendant:

![Call flow diagram showing a Travel Support call queue nested behind an auto attendant.](media/aa-cq/aa-cq-call-priorities-scenario-2.svg)

## How to nest call flows

You can nest Teams Phone Agents, Auto Attendants, and Call Queues in two ways: directly reference the voice application you want nested, or reference the resource account assigned to it. Each method is described in the following sections.

### Directly reference the Teams Phone Agent, Auto Attendant, or Call Queue

The first Teams Phone Agent, Auto Attendant, or Call Queue that answers the calls requires a resource account and associated licensing. Nested Teams Phone Agents, Auto Attendants, or Call Queues that receive calls from the Teams Phone Agent, Auto Attendant, or Call Queue that already answered the call don't need a resource account, even if they end up transferring calls externally.

When you nest Teams Phone Agents, Auto Attendants, or Call Queues this way, license the resource account on the first auto attendant or call queue receiving the call.

Nesting without resource accounts is the recommended approach. This method removes the need to create and license extra resource accounts. It also makes routing flows easier to understand and manage.

However, there might be times when you need to nest with resource accounts. For example, when representatives (agents) in a call queue receive a call, how the call arrived in the queue determines the information in the toast. If the call was transferred to the queue without a resource account, the representative receives the name of the call queue in the toast. If the call was transferred to the queue through a resource account, the representative receives the display name of the resource account.

### Reference the resource account assigned to the Teams Phone Agent, Auto Attendant, or Call Queue

Each resource account must have a Teams Phone Resource Account license.

Important

Nesting without a resource account isn't supported for [Authorized users](aa-cq-plan-authorized-users) in Queues App. If you nest a Teams Phone Agent, Auto Attendant, or Call Queue without a resource account, authorized users can't edit them.

Make sure to review the next article that outlines how your choice of nesting affects historical reporting.