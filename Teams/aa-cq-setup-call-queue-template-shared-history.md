---
layout: Conceptual
title: Setup - Shared Call History template for Call Queue - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-call-queue-template-shared-history
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
customer-intent: As a Teams Administrator, I want to learn how to set up a shared call queue history template and apply it to call queues so representatives and authorized users can view missed, answred, and outbound call activity.
description: Learn how to set up Shared Call History for a call queue so representatives and authorized users can view missed, answered, and outbound call activity.
locale: en-us
document_id: 0aac0b6b-2a0b-af50-5fe4-f02b4674b8cc
document_version_independent_id: 0aac0b6b-2a0b-af50-5fe4-f02b4674b8cc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-call-queue-template-shared-history.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-call-queue-template-shared-history
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-call-queue-template-shared-history.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 7c67d5b3-6c3d-24f8-2ab9-f95aead4d734
---

# Setup - Shared Call History template for Call Queue - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to use **Shared Call History** to show missed, answered, and outbound call activity.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Shared call history](aa-cq-plan-shared-call-history#shared-call-history-for-call-queues)
- [Getting started](aa-cq-reference-getting-started)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

None.

## Prerequisites

- [Conference mode](aa-cq-setup-call-queue#conference-mode) is enabled on the call queue.

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

## Shared Call History template

The Shared Call History template is used for both call queues and auto attendants.

This Shared Call History for Call Queue article describes the call queue options highlighted in the following image:

![Screenshot showing the Shared Call History template and highlighting the Call queue portion.](media/aa-cq/aa-cq-setup-call-queue-shared-history.png)

See [Shared Call History for Auto Attendant](aa-cq-setup-auto-attendant-template-shared-history) for details on configuring Shared Call History for auto attendants.

## Shared Call History for Call Queue

Important

Users require [Queues App](manage-queues-app) to access the features described in this article. See [Queues App licensing](aa-cq-reference-prerequisites-licensing#queues-app).

Representatives (agents) and supervisors are able to see an evolving history of missed calls, calls that are returned, and voicemails that are listened to. Shared Call History for call queues enables representatives to ensure that every call that takes place within a call queue is handled efficiently. It also enables supervisors to better track and manage the activities of their representatives.

When enabled, Shared Call History for call queues allows authorized users and representatives to see the following activity for the queue:

- Missed calls.
- Shared voicemails.
- Status of each call log, whether it's in progress, resolved, or unresolved.
- Call times and duration.
- Call participants.

With Shared Call History for call queues, representatives are able to:

- Call back customers whose calls they missed.
- Call back customers who left voicemails.

## Incoming missed calls

Incoming missed calls include:

- **Abandoned calls** - the caller hangs up before being answered or before timing out.
- **Call exceptions** - calls that receive the timeout, overflow, or no agents treatment where the destination is Shared voicemail.

## Answered and outbound

Answered and outbound calls include calls answered by representatives in the queue, and outbound calls made by representatives on behalf of the queue.

## Call queue nesting

If a call arrives in call queue A and exception handling (overflow, timeout, no agents) redirects it to call queue B, the missed and answered call history is associated with call queue B.

## Shared Call History templates

A Shared Call History template defines the type of call queue history that's available and who can see it.

The same Shared Call History template can be used across multiple call queues.

When a Shared Call History template is changed, all the call queues that reference the template are also changed.

### Create the Shared Call History template

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Templates and resources**.
2. Select **Templates**.
3. Select **Shared call history** as the template type.
4. Select **Add** to create a new Shared Call History template.
5. Enter a name for the template.
6. Enter a description for the template.
7. Select the appropriate **Incoming missed calls permission** level.
8. Select the appropriate **Answered and outbound calls permission** level.
9. Select **Save**.

### Assign the template to the call queue

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Call queues**.
2. Select the call queue you want to have shared call history for.
3. On the **General info** tab, scroll to find the **Shared call history template** section.
4. Select the appropriate Shared Call History template from the dropdown.
5. Select **Submit**.