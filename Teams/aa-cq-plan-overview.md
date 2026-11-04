---
layout: Conceptual
title: Planning - Overview of voice applications - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-overview
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
customer-intent: As a Teams Administrator, I want to learn about Teams Phone Agent, Auto Attendant, and Call Queues so I know when and how to use them within my organization.
description: Learn what Teams Phone Agent, auto attendants, and call queues are, the features each offers, and how to plan the right call-routing experience.
locale: en-us
document_id: 16cb9db1-adf3-65fb-5d89-b2915730872b
document_version_independent_id: 16cb9db1-adf3-65fb-5d89-b2915730872b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-overview.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ddc9922d-966d-5d10-0619-87306a2c8b8f
---

# Planning - Overview of voice applications - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

This **Planning and design** series of articles is for IT pros and Teams administrators who want to learn about voice applications, including Teams Phone Agent, Auto Attendant, and Call Queue.

This **Overview** article explains the basics of each of these voice applications. Other articles in the series cover specific features within these voice applications.

If you're new to Teams Phone Agent, Auto Attendant, and Call Queue, review the articles in the order they appear.

By the end of this series, you learn what voice applications are, the features they offer, and what you need to configure them to create the right call-routing experience.

## Teams Phone Agent

Teams Phone Agents extend auto attendants with AI-driven, human-like conversations that screen calls, answer questions, manage appointments, and route callers without fixed menus.

Teams Phone Agent automates workflows for answering common questions and managing appointments to enable callers to self-service and deflect calls, allowing your people to focus on their tasks at hand.

Teams Phone Agent seamlessly integrates with [Microsoft Copilot Studio](/en-us/microsoft-copilot-studio/) to handle specialized workflows like billing, order status, or inventory checks. This unlocks deeper automation, tailored experiences, and extensibility across business scenarios.

Together, Teams Phone Agent and Microsoft Copilot Studio offer a scalable, customizable voice solution that reduces operational overhead, improves customer experience, and supports end-to-end task completion across Teams Phone.
[![Open in New Tab](media/aa-cq/teams-phone-agent-demo.png)](https://go.microsoft.com/fwlink/?LinkId=2373040)
## What's new in Teams Phone Agent (last six months)

- October 21, 2026
    - [Spam detection](aa-cq-setup-teams-phone-agent-template-spam-detection) can be configured in Teams admin center.
- October 19, 2026
    - [Copilot Credit Estimator](https://nptnlopcost-ppe-h8b6dtchacfcgqhk.b02.azurefd.net/#/estimator) now supports Teams Phone Agent.
- October 14, 2026
    - Teams Phone Agent now supports 42 voices, including 33 new ones.
- September 30, 2026
    - Teams Phone Agent is now generally available to all customers.
    - [Appointments integration with Microsoft Bookings](aa-cq-setup-teams-phone-agent-tools-appointments) can be configured in Teams admin center.
    - [Automatic Recording for Teams Phone Agent](aa-cq-setup-teams-phone-agent-template-recording-automatic) can be configured in Teams admin center.
    - [Maximum call length with configurable disconnect message](aa-cq-setup-teams-phone-agent#configurable-call-length) can be configured in Teams admin center.
    - Question and Answers URLs are refreshed daily.
- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent updated.
- September 1, 2026
    - Appointments integration with Microsoft Bookings can be configured via PowerShell.
- August 31, 2026
    - [AI disclaimer](aa-cq-setup-teams-phone-agent#ai-disclaimer-customization) can be configured in Teams admin center.
    - [Maximum call length](aa-cq-setup-teams-phone-agent#configurable-call-length) can be configured in Teams admin center.
- August 17, 2026
    - Automatic Recording for Teams Phone Agent can be configured via PowerShell.
- August 12, 2026
    - Spam detection can be configured via PowerShell.
    - AI disclaimer customization can be configured via PowerShell.
    - Maximum call length can be configured in PowerShell.
- July 20, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent is now available.
- June 15, 2026
    - Entered Frontier Public Preview

## Auto Attendant

The primary purpose of an auto attendant is to direct a caller to an appropriate person or department based on the caller's input to the provided menu options. Callers can be directed to:

- Specific people within your organization.
- Call queues where they wait to talk to the next available representative (agent).
- External phone numbers.
- Other auto attendants.
- Shared or personal voicemail.

Different call-routing options can be specified for business hours, after hours, and holidays.

Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading a recorded audio file. Speech recognition accepts voice commands for hands-free navigation, but people calling in can also use the phone keypad to navigate menus.

Each auto attendant has a specific language and time zone. If you do business in multiple languages or multiple parts of the world, you can create as many different auto attendants as you need to accommodate your callers.

For each auto attendant, you can configure an operator. While you can configure operator calls to go to various destinations, the operator feature is designed to allow callers to talk to a specific person in your organization who can help them.

Auto attendants can be configured to allow callers to search your organization's directory, either by name or by extension number. In an auto attendant, you can choose which users show up in the directory by selecting which groups to include or leave out by setting the *dial scope*.

Internal callers, using their Teams client, can reach an auto attendant by calling the resource account assigned to the auto attendant. External callers can reach an auto attendant by dialing the phone number assigned to the resource account or via the web if click-to-call is configured.

## What's new in Auto Attendant (last six months)

- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) updated.

## Call Queue

A call queue is analogous to a waiting room in a physical building. Callers wait on hold while calls are routed to the representatives in the queue. Call queues are commonly used for sales and service functions. However, call queues can be used for any situation where the number of calls exceeds your internal capacity, such as a receptionist in a busy facility.

Call queue exception handling allows you to redirect calls to specific people, voicemail, other call queues, auto attendants, or Teams Phone Agents in the following situations:

- There are no agents logged in.
- The total number of callers waiting in queue exceeds the limit that you specify.
- The caller's wait time in queue exceeds the limit that you specify.

Like auto attendants, call queues each have a language setting. You can use different call queues if you do business in multiple languages. Representatives (agents) can be members of more than one queue if they're multi-lingual.

For each call queue, you can choose whether representatives (agents) can opt out of calls and whether routing uses their Teams presence status.

Internal callers, using their Teams client, can reach a call queue by calling the resource account assigned to the call queue. External callers can reach a call queue by dialing the phone number assigned to the resource account or via the web if click-to-call is configured.

Call queues don't provide separate call routing for off hours and holidays. Even if your call queue is staffed 24/7, we recommend using an auto attendant to direct calls to the call queue.

## What's new in Call Queue (last six months)

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

## Summary

Use Teams Phone Agent to provide a conversational, multi-lingual experience that lets callers get answers, book appointments, find people, manage hours, and interact with workflows using [Microsoft Copilot Studio](/en-us/microsoft-copilot-studio/). It can transfer callers to call queues or people when needed.

Use auto attendants to allow callers to select the service they need, to find users in your organization and to control hours of operation. Callers interact with auto attendants by pressing keys on their telephone or through a set of predetermined basic voice commands that you can configure.

Use call queues when you have callers who need to hold for one or more representatives to answer their calls.

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)