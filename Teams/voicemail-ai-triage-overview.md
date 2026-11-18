---
layout: Conceptual
title: Automatic voicemail triage with AI - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/voicemail-ai-triage-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Overview of automatic voicemail triage with AI, including behavior, requirements, processing flow, and billing for personal and shared voicemail.
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-11-13T00:00:00.0000000Z
ms.topic: overview
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
locale: en-us
document_id: 8ec398df-2713-6ce4-334e-3ccd4d401d55
document_version_independent_id: 8ec398df-2713-6ce4-334e-3ccd4d401d55
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/voicemail-ai-triage-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: voicemail-ai-triage-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/voicemail-ai-triage-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
platformId: 9d563e90-314b-4b6a-bfdb-59396fa96493
---

# Automatic voicemail triage with AI - Microsoft Teams | Microsoft Learn

Automatic voicemail triage uses a compliant and secure Large Language Model (LLM) to help users interpret and prioritize voicemail messages through transcript analysis.

When enabled, the system can generate:

- A concise summary of the message.
- Categories and priority indicators.
- Suggested follow-up actions.
- Highlighted key terms for quick review.

Important

This feature is available only through the Microsoft Frontier Program. General availability (GA) timing hasn't been announced yet.

## How voicemail triage works

Voicemail triage runs after a message is recorded and before it's delivered to Exchange.

The service analyzes the voicemail transcript and can generate these outputs:

- **Summary**: A concise, natural-language paragraph that starts with the caller's intent and includes key details (for example, dates, times, requested actions, or contact information).
- **Category**: A topic label for the voicemail. Some categories are system-defined (for example, junk and harmful content), and other categories are generated from transcript content.
- **Suggested actions**: Recommended follow-up tasks derived from the voicemail content. System-defined action labels include callback, set appointment, reschedule appointment, cancel appointment, and email reply, followed by other requested actions generated from the transcript.
- **Importance flag (urgency)**: A priority signal for time-critical messages, which can mark the voicemail as important in Outlook.

Generated triage insights are stored with the voicemail in Exchange and can be used by downstream automations such as Outlook rules, agent-based workflows, and other LLM-powered processes.

If AI-generated content doesn't appear for a voicemail, audio or transcript clarity might be insufficient for reliable triage output.

## Scope

- **Shared voicemail triage** applies to missed calls handled by Auto Attendants, Call Queues, and Teams Phone Agents.
- **Personal voicemail triage** applies to a user's personal Teams voicemail.

For shared voicemail, AI triage data is also shown in the Teams Queues app experience. This Queues app experience isn't generally available (GA) yet. The Queues app requires a Teams Premium license.

## Admin controls

Admins can control which AI outputs are generated:

- For **personal voicemail**, configure user settings in the Teams admin center (**Manage users** &gt; **Voicemail** &gt; **Personal voicemail AI triage**) or by using PowerShell.
- For **shared voicemail**, configure settings in the **AI triage of shared voicemails** template used by Auto Attendants, Call Queues, and Teams Phone Agents in the Teams admin center or by using PowerShell.

## Requirements

### Personal voicemail triage

Personal voicemail triage requires all of the following:

- A Microsoft 365 Copilot license for the user.
- A spending policy for **AI Triage for Personal Voicemail** configured in the Microsoft 365 admin center.
- Voicemail AI triage enabled in [Voicemail policies](manage-voicemail-policies) in the Teams admin center.

If any requirement isn't met, AI triage isn't performed and no usage-based billing charges are incurred.

### Shared voicemail triage

Shared voicemail triage requires both of the following:

- A spending policy for **AI Triage for Shared Voicemail** configured for the applicable resource account in the Microsoft 365 admin center.
- A **Voicemail AI triage template** selected for the specific Auto Attendant, Call Queue, or Teams Phone Agent in the Teams admin center.

If no template is selected, AI triage isn't performed and no usage-based billing charges are incurred, even when a spending policy is configured.

## Billing summary

Billing is per voicemail processed:

- **Personal voicemail triage**: Charged per voicemail processed. For configuration details, see [Personal voicemail AI triage billing](personal-voicemail-ai-triage-billing).
- **Shared voicemail triage**: Charged once per voicemail processed, even when the same voicemail is delivered to multiple users. For configuration details, see [Shared voicemail AI triage billing](shared-voicemail-ai-triage-billing).

For shared voicemail, cost is attributed to the resource account associated with the Auto Attendant, Call Queue, or Teams Phone Agent. If an Auto Attendant or Call Queue doesn't have its own resource account, billing uses the root resource account associated with the phone number.

## Availability

During TAP and early GA, voicemail AI triage is available only for tenants whose tenant language is set to English.

Additional languages and organization-defined custom categories and suggested actions might be introduced based on customer demand and feedback.