---
layout: Conceptual
title: Reference - Voice applications prerequisites and licensing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-reference-prerequisites-licensing
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
ms.topic: reference
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
customer-intent: As a Teams Administrator, I want to learn about the prerequisites and licensing requirements for voice applications so I can plan my purchasing.
description: Reference the licensing and technical prerequisites for voice applications, including outbound PSTN calling and Queues App.
locale: en-us
document_id: 5d110b99-f220-6b65-17e9-da82dac97051
document_version_independent_id: 5d110b99-f220-6b65-17e9-da82dac97051
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-reference-prerequisites-licensing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-reference-prerequisites-licensing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-reference-prerequisites-licensing.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 099ad31d-9e12-4b9b-1828-d23a3e00d5a9
---

# Reference - Voice applications prerequisites and licensing - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to understand the technical prerequisites and licensing requirements for Teams Phone Agent, Auto Attendant, and Call Queue features.

## Licensing

### Base licensing

#### Auto Attendant and Call Queue

- At least one Teams Phone license to enable Teams Phone Agent, Auto Attendant, and Call Queue services.
- A free [Microsoft Teams Phone Resource Account](teams-add-on-licensing/virtual-user) license for each resource account.

Note

Resource accounts are disabled for sign in and must remain so. Chat and presence aren't available for these accounts.

A **User Administrator** or higher role is required to create and license resource accounts. For more information, see [Using Microsoft Teams administrator roles to manage Teams](using-admin-roles).

#### Teams Phone Agent

- At least one Teams Phone license to enable Teams Phone Agent, Auto Attendant, and Call Queue services.
- A free [Microsoft Teams Phone Resource Account](teams-add-on-licensing/virtual-user) license for each resource account.
- Copilot credits and spending polices.

Note

Resource accounts are disabled for sign in and must remain so. Chat and presence aren't available for these accounts.

A **User Administrator** or higher role is required to create and license resource accounts. For more information, see [Using Microsoft Teams administrator roles to manage Teams](using-admin-roles).

#### Teams Phone Agent with Microsoft Bookings

- [Microsoft Bookings](/en-us/office365/servicedescriptions/microsoft-bookings-service-description)

##### Teams Phone Agent with Microsoft Copilot Studio

- [Microsoft Copilot Studio](/en-us/microsoft-copilot-studio/billing-licensing)and funding and access to:
    - **Copilot Studio tenant license**: These entitlements are needed to run agents and publish them to a channel.
    - **Copilot Studio user license**: Required for creating and using Copilot Studio applications.

##### Teams Phone Agent with Power Automate

- [Power Automate](/en-us/power-platform/admin/power-automate-licensing/types)

### Outbound calls from Teams Phone Agent, Auto Attendant, or Call Queue

If your Teams Phone Agents, Auto Attendants, or Call Queues perform any of the following actions:

- Transfer calls to an external phone number.
- Use the Call Queue Callback feature.
- Use resource accounts for representative on-behalf-of outbound calling line ID control in call queues.

Then, in addition to the **Teams Phone Resource Account** license, the resource account must also have one of the following assigned:

For Microsoft-provided numbers:

- A funded [pay-as-you-go](calling-plans-for-office-365#pay-as-you-go-calling-plan) license assigned or [Communications credits](what-are-communications-credits), or
- Telco pay-as-you-go overage for [New Commerce](/en-us/partner-center/new-commerce-telco-payg) customers.

For Direct Routing numbers:

- An [online voice routing policy](manage-voice-routing-policies).
- Phone number assignment is optional when using Direct Routing.

For Operator Connect numbers:

- There are no other requirements when an [Operator Connect](operator-connect-plan) phone number is assigned.

### Queues App

- All [Queues App](manage-queues-app) users require a [Teams Premium](teams-add-on-licensing/licensing-enhance-teams) license.

### Automatic Recording for Teams Phone Agent

- No extra Teams Phone licensing is required.
- See [SharePoint service description](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

### Automatic Recording for Call Queue

- No extra Teams Phone licensing is required.
- See [SharePoint service description](/en-us/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

### Compliance Recording for Call Queue

- Third party licensing - For more information on compliance recording, see [Introduction to Microsoft Teams third-party compliance recording](teams-recording-compliance)

## Prerequisites

### Authorized users

- All authorized users must be Enterprise Voice enabled. For more information, see [Assign, change, or remove a phone number for a user](/en-us/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) or [Enable users for Direct Routing](/en-us/microsoftteams/direct-routing-enable-users).

### Automatic Recording for Call Queue

- Conference mode must be enabled on the call queue.
- Use Microsoft 365 security groups to assign representatives to the queue.
- Not supported with Shifts.
- SharePoint Site Admin required for Teams admin center admins to change the authorized users.

### Call queue representatives

Representatives (agents) who receive calls from a call queue must be Enterprise Voice enabled online or on-premises users. For more information, see [Assign, change, or remove a phone number for a user](/en-us/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) or [Enable users for Direct Routing](/en-us/microsoftteams/direct-routing-enable-users).

In addition, if the resource account assigned to the call queue is using Direct Routing numbers, representatives who need to conference or transfer calls also require:

- An [online voice routing policy](manage-voice-routing-policies) assigned if the call queue uses transfer mode.
- An [Audio Conferencing license](set-up-audio-conferencing-in-teams) or [online voice routing policy](manage-voice-routing-policies).

If your representatives are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.

### Compliance Recording for Call Queue

- Conference mode must be enabled.

### Inbound calls

In order for Teams Phone Agents, Auto Attendants, and Call Queues to receive inbound calls from callers outside of Teams:

- At least one [Microsoft service number](getting-service-phone-numbers), [Operator Connect number](operator-connect-plan), or [Direct Routing number](direct-routing-plan), or a hybrid number for each resource account that you want callers outside of Teams to be able to call.
- The service number can also be a toll or toll-free number.
- Web click-to-call:
    - [Contact centers with Azure Communication Services](/en-us/azure/communication-services/tutorials/contact-center)
    - [Quickstart: Join your calling app to a Teams auto attendant](/en-us/azure/communication-services/quickstarts/voice-video-calling/get-started-teams-auto-attendant)
    - [Quickstart: Join your calling app to a Teams call queue](/en-us/azure/communication-services/quickstarts/voice-video-calling/get-started-teams-call-queue)

Note

Direct Routing service numbers for auto attendants and call queues are supported for Microsoft Teams users and representatives (agents) only.

Transfers between Calling Plan, Operator Connect, and Direct Routing trunks aren't supported.

In a Hybrid scenario, the resource account must be created on-premises. For more information, see [Plan Cloud call queues](/en-us/skypeforbusiness/hybrid/plan-call-queue).