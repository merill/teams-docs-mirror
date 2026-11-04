---
layout: Conceptual
title: Planning - Recording voice applications calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-recording
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
customer-intent: As a Teams Administrator, I want to learn about the options available to record Teams Phone Agent, Auto Attendant, and Call Queue calls.
description: Learn the options for recording Teams Phone Agent, Auto Attendant, and Call Queue calls, including automatic and compliance recording.
locale: en-us
document_id: 1804836c-2056-4d38-955c-71db66007432
document_version_independent_id: 1804836c-2056-4d38-955c-71db66007432
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-recording.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-recording
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-recording.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3e7e5a80-51ff-20d2-9a14-67b6aadb7a52
---

# Planning - Recording voice applications calls - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

This article is for IT pros and Teams administrators who want to learn about the options available to record Teams Phone Agent, Auto Attendant, and Call Queue calls.

## Automatic Recording for Teams Phone Agent

**Automatic Recording for Teams Phone Agent** is a first-party Microsoft Teams solution that enables administrators to configure automatic recording and transcription of inbound Teams Phone Agent calls. When enabled, all inbound Teams Phone Agent calls are automatically recorded.

Key capabilities:

- Admins can enable/disable automatic recording and transcription per Teams Phone Agent.
- Recording starts automatically when Teams Phone Agent answers a call and stops when the call leaves Teams Phone Agent.
- Configurable announcements.
- Authorized users have access to view recordings and transcriptions.

All recordings are stored in and accessed through SharePoint.

## Automatic Recording for Call Queue

**Automatic Recording for Call Queue** is a first-party Microsoft Teams solution that enables administrators to configure automatic recording and transcription of inbound call queue calls. When enabled, all inbound call queue calls are automatically recorded when a representative (agent) answers.

Key capabilities:

- Admins can enable/disable automatic recording and transcription per call queue.
- Recording starts automatically when a representative answers a call queue call and stops when the call ends.
- Configurable announcements.
- Access controls:
    - Authorized users have access to view recordings and transcriptions.
    - Representatives can be given permission to view the queue's recordings and transcriptions.
    - Queues App is required for authorized users and representatives.

All recordings are stored in SharePoint.

Shared Call History must also be enabled on the call queue so that authorized users and representatives can access the recordings in Queues App.

## Compliance Recording for Call Queue

Compliance Recording for Call Queue records all representative-answered inbound call queue calls without the need to assign a compliance recording policy to the representatives. Any compliance recording policy assigned to the representative is ignored for inbound call queue calls where compliance recording for call queues is enabled.

If there's a need to record outbound calls made by the representatives in a call queue, they must have a [compliance recording policy](teams-compliance-recording-setup#create-and-manage-your-compliance-recording-policy) assigned to them. For compliance recording purposes, these calls are considered outbound user calls and aren't associated with the call queue. This restriction will be addressed in a future release of Compliance Recording for Call Queue.

If there's a need to record a user's non-call queue inbound and outbound calls, they must have a [compliance recording policy](teams-compliance-recording-setup#create-and-manage-your-compliance-recording-policy) assigned to them.

For more information on compliance recording, see [Introduction to Microsoft Teams third-party compliance recording](teams-recording-compliance).

A [compliance recording application instance](teams-compliance-recording-setup#create-a-compliance-recording-application-instance) is required to create a compliance recording for call queue template.

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Queues App](aa-cq-reference-prerequisites-licensing#queues-app)

[Compliance recording partners](teams-recording-compliance#third-party-compliance-recording-partners) have their own licensing requirements.

## Prerequisites

- [Compliance Recording for Call Queue](aa-cq-reference-prerequisites-licensing#compliance-recording-for-call-queue)

## Known issues

### Automatic Recording for Teams Phone Agent

- Changes to the SharePoint site structure, file names, or permissions can cause access issues, permission errors, or automatic recording failures.
- To assign an automatic recording template to a Teams Phone Agent or manage its authorized users list, the Teams administrator must also be a SharePoint site administrator for the site used by the template. See [Teams Phone Agent management and SharePoint interaction](aa-cq-setup-teams-phone-agent-template-recording-automatic#teams-phone-agent-management-and-sharepoint-interaction) on how to avoid this issue.

### Automatic Recording for Call Queue

- Changes to the SharePoint site structure, file names, or permissions can cause access issues, permission errors, or automatic recording failures.
- To assign an automatic recording template to a call queue or manage its authorized users list, the Teams administrator must also be a SharePoint site administrator for the site used by the template. See [Call queue management and SharePoint interaction](aa-cq-setup-call-queue-template-recording-automatic#call-queue-management-and-sharepoint-interaction) on how to avoid this issue.
- [Explicit recording consent](participant-agreement-recording-transcription) must be **Off**.

### Compliance Recording for Call Queue

None.