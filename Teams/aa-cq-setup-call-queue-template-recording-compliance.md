---
layout: Conceptual
title: Setup - Compliance Recording for Call Queues template - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-call-queue-template-recording-compliance
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
ms.date: 2026-08-31T00:00:00.0000000Z
ms.topic: how-to
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
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to set up a compliance recording for call queues template that I can apply to my call queues so that representative (agent)-answered inbound calls are recorded without assigning a recording policy to each representative.
description: Learn how to set up compliance recording on a call queue template so agent-answered calls are recorded without per-agent policies.
locale: en-us
document_id: 5a37741f-c469-7f46-4f97-1c23959e5b31
document_version_independent_id: 5a37741f-c469-7f46-4f97-1c23959e5b31
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-call-queue-template-recording-compliance.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-call-queue-template-recording-compliance
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-call-queue-template-recording-compliance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: e1a66597-c7b9-c566-201f-dc8c34046376
---

# Setup - Compliance Recording for Call Queues template - Microsoft Teams | Microsoft Learn

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Recording calls](aa-cq-plan-recording#compliance-recording-for-call-queue)
- [Getting started](aa-cq-reference-getting-started)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

None.

## Prerequisites

- [Conference mode](aa-cq-setup-call-queue#conference-mode) is enabled on the call queue.
- A [compliance recording application instance](teams-compliance-recording-setup#create-a-compliance-recording-application-instance) is required to create a compliance recording for call queue template.

## Unsupported calling scenarios

- If a call queue representative (agent) adds a second call queue to the call that has compliance recording for call queues enabled, the system ignores the compliance recording settings on the second queue.

## What's new in Call Queues (last six months)

- October 19, 2026
    - Monitor, Whisper, Barge, Takeover for authorized users now supports outbound calls.
- September 30, 2026
    - [Automatic Recording for Call Queue](aa-cq-setup-call-queue-recording-automatic) can be configured in Teams admin center.
- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) updated.
- August 17, 2026
    - Assigning templates to a call queue has moved to the new **Templates** step.
    - [Compliance Recording for Call Queues](aa-cq-setup-call-queue-template-recording-compliance) configuration is now available in Teams admin center.
- August 13, 2026
    - Automatic Recording for Call Queue can be configured via PowerShell.

## Compliance recording for call queue templates

A call queue compliance recording template defines which recording bot to use and whether the bot must be present for the call to continue (strict recording).

The same compliance recording for call queue template can be used across multiple call queues.

Up to two compliance recording for call queue templates can be assigned to a single call queue.

When a compliance recording for call queue template is changed, all the call queues that reference the template are also changed.

Each call queue configures the compliance recording **Default greeting** and **Default failure greeting** individually. Changing the compliance recording call queue template doesn't affect these greetings.

### Create the compliance Recoding for call queue template

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Templates and resources**.
2. Select **Templates**.
3. Select **Compliance Recording for Call Queue** as the template type.
4. Select **Add** to create a new Compliancde Recording for Call Queue template.
5. Enter a **Name** for the template.
6. Enter a **Description** for the template.
7. Select the **Compliance Recording Bot** resource account from the drop-down list.
8. Select the **Paired Compliance Recording Bot** resource account from the drop down list (optional).
9. (Strict Recording) - If the recording bot must join the call before the agent answers, turn on **Required before call**.
10. (Strict Recording) - If the recording bot must be present for the duration of the call, turn on **Required during call**.
11. For compliance-critical call queues, set the **Concurrent invitation count**to 2.
    - Sending multiple invites in parallel reduces join delays.
12. Select **Save**.

### Assign the template to the call queue

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Call queues**.
2. Select the call queue you want to have compliance recording for.
3. On the **Templates** tab, scroll to find the **Compliance recording for Call queue template** section.
4. Select up to two Compliance Recording for Call Queue templates from the dropdown.
5. Select **Submit**.

#### Recording announcement

The recording announcement is played to all callers arriving at the call queue when compliance recording for call queues is enabled.

A custom greeting audio file or text-to-speech prompt can be configured.

The default greeting is:

`This call will be recorded for compliance purposes.`

#### Recording failure announcement

The recording failure announcement is played to all callers when compliance recording for call queues is enabled and either of the following occurs:

- **Required before call** is **on** and the compliance recording bot isn't able to join the call.
- **Required during call** is **on** and the compliance recording bot leaves before the call is finished.

A custom failure greeting audio file or text-to-speech prompt can be configured.

The default failure greeting is:

`We're sorry, but your call is being disconnected because of an issue with the compliance recording solution. Thank you for your understanding.`

#### Play an audio file

For more information on audio file requirements, see [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).