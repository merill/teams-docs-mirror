---
layout: Conceptual
title: Reference - Answer voice applications calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-reference-answer-calls
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: colongma
author: CLYVR
ms.author: colongma
manager: roykuntz
audience: Admin
ms.date: 2026-08-31T00:00:00.0000000Z
ms.topic: reference
ms.service: msteams
ms.subservice: teams-calling
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
ms.custom: seo-marvel-mar2020
customer-intent: As a Teams Administrator, I want to understand how Teams Phone Agent, Auto Attendant, and Call Queue calls are presented to users and agents.
description: Learn how voice application calls are presented in the Teams client, and how to answer, transfer, and conference them.
locale: en-us
document_id: e94dd85e-2ca7-23a6-90be-022ef5e08915
document_version_independent_id: 59cd2a22-f1bb-0702-149a-f672e7878d71
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-reference-answer-calls.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-reference-answer-calls
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-reference-answer-calls.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c34b151c-22fd-0598-03b9-055ebf78ccc8
---

# Reference - Answer voice applications calls - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

Teams users can receive and answer calls from Teams Phone Agent, Auto Attendant, and Call Queue directly in their Teams client.

Users can differentiate incoming calls from a Teams Phone Agent, Auto Attendant, or Call Queue before they answer the call.

## Handling a Teams Phone Agent call

When users receive a call from a Teams Phone Agent, the information in the toast contains the name or number of the caller, the display name of the resource account assigned to the Teams Phone Agent that answered the call, and the caller's intent.

![Screenshot showing an incoming call toast from a Teams Phone Agent.](media/aa-cq/aa-cq-reference-answer-calls-teams-phone-agent.png)

Note

Calls from Teams Phone Agents are forwarded based on the user's call answering rules configuration.

## Handling an Auto Attendant call

When users receive a call from an auto attendant, the information in the toast contains the name or number of the caller and the display name of the resource account assigned to the auto attendant that answered the call.

![Screenshot showing an incoming call toast from an Auto Attendant.](media/aa-cq/aa-cq-reference-answer-calls-auto-attendant.png)

Note

Calls from Auto Attendants are forwarded based on the user's call answering rules configuration.

## Handling a Call Queue call

When representatives (agents) receive a call from a call queue, the toast displays information based on how the representatives received the call.

- If the call was transferred to the call queue without a resource account, the representative receives the name of the call queue in the toast.
- If the call was transferred to the call queue through a resource account, the representative receives the display name of the resource account.

![Screenshot showing an incoming call toast from a Call Queue.](media/aa-cq/aa-cq-reference-answer-calls-call-queue.png)

Note

Call queue calls aren't forwarded based on the user's call answering rules configuration. This ensures that callers remain in the queue until a representative can answer the call and that the caller isn't forwarded unexpectedly.

Representatives receiving calls from call queues are only presented with the name of the caller if it's provided from the Public Switched Telephone Network (PSTN) or if the caller's number matches the target representative's local Teams client contacts.

By default, representatives aren't notified of any missed calls or voicemails for call queue calls. For more information, see [Shared Call History](aa-cq-plan-shared-call-history).

## Transferring and conferencing

Once a Teams Phone Agent, Auto Attendant, or Call Queue call is answered, the user can handle the call like any other call. They can conference in another user or transfer the call to another party.

## Supported clients

Support for Teams Phone Agent, Auto Attendant, and Call Queue calls is available in the following clients:

- Microsoft Teams Windows client (32-bit and 64-bit versions)
- Microsoft Teams Mac client
- Microsoft Teams iPhone app
- Microsoft Teams Android app

The Teams client is only supported with a [coexistence mode of Teams Only](/en-us/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## Known issues

When a call queue representative receives a call on their mobile device, the call might go on hold if the device is locked. The representative must unlock the device first, and then answer the call.