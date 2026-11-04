---
layout: Conceptual
title: Planning - Third-party voice agents - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-third-party-voice-agents
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
customer-intent: As a Teams Administrator, I want to learn about third-party voice agents so I know when and how to use them within my organization.
description: Learn how third-party voice agents extend Teams Phone and pass full caller context to auto attendants, call queues, and users as calls are routed.
locale: en-us
document_id: 0660bef7-7b4b-b7ed-349e-6ef52e505bb9
document_version_independent_id: 0660bef7-7b4b-b7ed-349e-6ef52e505bb9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-third-party-voice-agents.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-third-party-voice-agents
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-third-party-voice-agents.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c513a3b7-eb7f-d168-d349-0e381c1cf039
---

# Planning - Third-party voice agents - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to learn about third-party voice agent integration with Teams.

## Third-party voice agents

The [Teams Phone Unify Integration model (Teams Phone extensibility)](/en-us/azure/communication-services/concepts/interop/tpe/teams-phone-extensibility-overview) integration model for third-party voice agents enables organizations to extend Teams Phone with third-party conversational voice agents, whether built in-house or delivered by a partner.

With this integration, these third-party voice agents can answer calls, provide information, authenticate callers, capture intent, and more. Those voice agents can also seamlessly route the call to the right Teams Phone destination, such as auto attendants, call queues, or individual users, handing off the full caller context to whoever picks up next.

Through the Context Pane in the Teams call client, end-to-end context is preserved as the call routes to different destinations. Structured call metadata, including caller identity, intent, call topic, conversation summary, and sentiment, flows automatically between an auto attendant, third-party voice agent, and the receiving call queue representatives (agents) or Teams user, so context is never lost on a handoff and the next person in the chain answers callers fully informed.

There are multiple places where this voice agent integration can be used:

1. Teams Phone Agent or auto attendant routing.
2. Call queue via exception handling routing.
3. Directly to a third-party voice agent.

Through [Tags](aa-cq-plan-templates-resources#tags), third-party voice agents can redirect a live call to any Teams Phone destination (Teams Phone Agent, auto attendant, call queue, or user) the moment the caller asks for it, with no manual transfer required.

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

Third-party voice agent partners have their own licensing requirements.

## Third-party voice agent partners

Microsoft partners with a growing ecosystem of third-party voice agent providers that deliver solutions based on this extensibility model. This approach lets organizations bring their existing third-party voice agent solutions into Teams Phone without building solutions from scratch.

See [Teams Unify Integration Model for Voice Agent](teams-voice-agents) for more information.