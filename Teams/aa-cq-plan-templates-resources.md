---
layout: Conceptual
title: Planning - Templates and resources - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-templates-resources
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
customer-intent: As a Teams Administrator, I want to learn about templates and resources so I can reuse configurations across multiple Teams Phone Agents, Auto Attendants, and Call Queues, and save time when making changes.
description: Learn how templates and resources let you define shared configurations, such as recording and Shared Call History, and reuse them across voice applications.
locale: en-us
document_id: 4c871e71-2d73-81b9-ef90-88eadf1171cb
document_version_independent_id: 4c871e71-2d73-81b9-ef90-88eadf1171cb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-templates-resources.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-templates-resources
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-templates-resources.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ae92aa38-ad01-8044-c9eb-df4238c11ff5
---

# Planning - Templates and resources - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

This article is for IT pros and Teams administrators who want to learn how to create configurations that can be shared across multiple Teams Phone Agents, Auto Attendants, and Call Queues.

## Templates

**Templates and resources** define a set of common Teams Phone Agent, Auto Attendant, or Call Queue configuration options. Once defined, the templates can be associated with multiple Teams Phone Agents, Auto Attendants, and Call Queues, which then share the same configuration.

When a template is changed, all the Teams Phone Agents, Auto Attendants, or Call Queues that reference the template are updated with the new configuration.

The following templates are currently available:

### Automatic Recording for Teams Phone Agent

**Automatic Recording for Teams Phone Agent** is a first-party Microsoft Teams solution that enables administrators to configure automatic recording and transcription of inbound Teams Phone Agent calls. When enabled, all inbound Teams Phone Agent calls are automatically recorded.

Key capabilities:

- Admins can enable/disable automatic recording and transcription per Teams Phone Agent.
- Recording starts automatically when Teams Phone Agent answers a call and stops when the call leaves Teams Phone Agent.
- Configurable announcements.
- Authorized users have access to view recordings and transcriptions.

All recordings are stored in and accessed through SharePoint.

### Automatic Recording for Call Queue

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

### Compliance Recording for Call Queue

Compliance Recording for Call Queue records all representative-answered inbound call queue calls without the need to assign a compliance recording policy to the representatives. Any compliance recording policy assigned to the representative is ignored for inbound call queue calls where compliance recording for call queues is enabled.

If there's a need to record outbound calls made by the representatives in a call queue, they must have a [compliance recording policy](teams-compliance-recording-setup#create-and-manage-your-compliance-recording-policy) assigned to them. For compliance recording purposes, these calls are considered outbound user calls and aren't associated with the call queue. This restriction will be addressed in a future release of Compliance Recording for Call Queue.

If there's a need to record a user's non-call queue inbound and outbound calls, they must have a [compliance recording policy](teams-compliance-recording-setup#create-and-manage-your-compliance-recording-policy) assigned to them.

For more information on compliance recording, see [Introduction to Microsoft Teams third-party compliance recording](teams-recording-compliance).

A [compliance recording application instance](teams-compliance-recording-setup#create-a-compliance-recording-application-instance) is required to create a compliance recording for call queue template.

### Shared Call History for Auto Attendants

Authorized users and shared voicemail members can see a history of actions on shared voicemails.

### Shared Call History for Call Queues

Representatives (agents) and supervisors can see an evolving history of missed calls, calls that are returned, and voicemails that are listened to. Shared Call History for call queues enables representatives to ensure that every call that takes place within a call queue is handled efficiently. It also enables supervisors to better track and manage the activities of their representatives.

When enabled, Shared Call History for call queues allows authorized users and representatives to see the following activity for the queue:

- Missed calls (callers who abandon or callers sent to shared voicemail when they time out, overflow, or receive the no-agents treatment).
- Shared voicemails.
- Status of each call log, whether it's in-progress, resolved, or unresolved.
- Call times and duration.
- Call participants.

With Shared Call History for call queues, representatives can:

- Call back customers whose calls they missed.
- Call back customers who left voicemails.

### Spam detection templates

**SPAM DETECTION TEMPLATE**

### Tags

Tags are a way to pass dynamic transfer information from Teams to Microsoft Copilot Studio (MCS) and third-party interactive voice response (IVR) systems. Using Tags simplifies your MCS or IVR applications and makes them more scalable.

#### Sample use case

Contoso Pharmacy has locations all over the world and uses Teams as their phone system in all locations. Each location has its own local phone number and Teams Phone Agent that provides unique information for that location. Contoso provides every location with a centralized prescription renewal MCS agent that allows customers to renew their prescriptions 24 hours a day, 7 days a week. Once a prescription is renewed, the caller can request to speak to their local pharmacist. The system then transfers the call back to the local pharmacy department for handling.

##### Implementation methods without Tags

One option is to hard code all the local pharmacy transfer points into the MCS application, driving significant coordination between the MCS application development team and the Teams administrators. This approach doesn't scale well; every time a store closes or a new store opens, the MCS application must be updated. Ad hoc changes, driven by conditions at the local stores, such as having one local store cover for another, are also not easy to accommodate.

A second option is to have the MCS application look up this information in an external database or in Teams through the Graph API. While more flexible than hard coding the transfer points, this option creates a dependency that could affect the reliability of the application.

##### Implementation with Tags

Tags allow passing the variable pharmacy transfer information that already exists in Teams to the MCS application. The MCS application doesn't have to be changed anytime a store closes or opens, local store-driven changes can be accommodated by a Teams admin, and there's no dependency on other systems.

In the Contoso Pharmacy example, when a call comes into the local store, a tag can be passed into the MCS application. The tag contains the pharmacist transfer point for that local store.

Now the MCS application only needs to know there's a pharmacist transfer point and that it receives this information as part of the inbound call information.

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Queues App](aa-cq-reference-prerequisites-licensing#queues-app)