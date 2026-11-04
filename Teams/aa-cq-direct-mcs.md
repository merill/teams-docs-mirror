---
layout: Conceptual
title: Setup - Voice enable Microsoft Copilot Studio agents - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-direct-mcs
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: iris-su
ms.author: irisasu
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-10-22T00:00:00.0000000Z
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
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want learn about voice enabling my Microsoft Copilot Studio agents through Microsoft Teams Phone so I know when and how to use them within my organization.
description: Setup - Voice enable Microsoft Copilot Studio agents through Teams Phone
locale: en-us
document_id: 6873e8c6-7bcd-1509-0394-a60c8f2666e4
document_version_independent_id: 6873e8c6-7bcd-1509-0394-a60c8f2666e4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-direct-mcs.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-direct-mcs
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-direct-mcs.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c389ea6b-b6a0-46df-93a1-1e21f25e19e7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/19ada1b6-705b-4ed7-aad0-bffd1bd03dfa
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: b395d135-7481-fe0b-75df-942e41400b1a
---

# Setup - Voice enable Microsoft Copilot Studio agents - Microsoft Teams | Microsoft Learn

## Planning and licensing review

### Planning

- [Manage Teams resource accounts](aa-cq-manage-resource-accounts)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

None.

## What's new in voice enabling Microsoft Copilot Studio agents (last six months)

- October, 22, 2026
    - Entered public preview
- June 15, 2026
    - Entered Frontier Public Preview

## Overview

Voice enabling Microsoft Copilot Studio voice agents through Microsoft Teams Phone allow you to create conversational AI bots and attach them directly to a phone number via Teams Phone's resource accounts. By using these first-party conversational voice agents, you can significantly enhance your current Interactive Voice Response experiences or upgrade your current call flows.

Copilot Studio provides a powerful platform to build custom workflows tailored to your business. Key capabilities include:

- Custom Workflows: Build specialized voice workflows and conversational topics.
- Extensible Integrations: Connect your voice agents with CRM systems, internal knowledge bases, and more.
- Routing: Route calls efficiently to Teams Phone destinations using [Tags](aa-cq-plan-templates-resources#tags), including Call Queue, Auto Attendants, specific users, and more.

By front-ending your call flow with a Copilot Studio voice agent, you unlock deep automation and tailored experiences. You can design custom workflows to handle common inquiries, such as billing, order status, and inventory checks. The agent acts as an intelligent first point of contact, resolving issues independently before seamlessly routing the call to a human representative using traditional Teams Phone routing systems if needed.

## Teams Admin Center setup and configuration

### Make a Copilot Studio voice agent:

1. For detailed steps on how to make a Microsoft Copilot Studio voice agent, see [Integrate voice agents with Teams Phone](/en-us/microsoft-copilot-studio/voice-teams-phone-agent).

### Create an AI Agent Resource account:

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), expand **Voice**, select **Resource accounts**, and then select **Add**.
2. Enter a **Display name**, **Unique Username** and select a **Domain name**.
3. Select your **Resource account type** as **AI Agent**.
4. Save your changes.

### License your AI Resource account:

1. Go to Microsoft Admin Center, navigate Users / Active users, and select your Resource account.
2. Add the Teams Phone Resource Account license under Licenses and Apps.
3. Save your changes.
4. Wait for the changes to propagate.

### Link your AI Agent Resource account and Copilot Studio voice agent:

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), expand **Voice**, and select **Resource accounts**.
2. select your **AI Agent Resource account** and select **Edit**.
3. (optional) Select a **Voice routing policy**.
4. (optional) Assign a **phone number**. If you don't assign a phone number, only users in your tenant can call this resource account over VOIP via Teams Client.
    1. Select your **Phone number type**: **Calling Plans**, **Operator Connect**, or **Direct Routing**.
    2. Select a phone number.
    3. Save your changes.
5. Under **Agents**, select your **Agent Source** and select your **Copilot Studio voice agent**.
6. (optional) Select a **Tag template** to be able to route to different Teams Phone destinations via your Copilot Studio voice agent. For information, see [Tags](aa-cq-plan-templates-resources#tags).
7. Save your changes.

## PowerShell setup and configuration

To set up a Copilot Studio voice agent through Teams Phone through PowerShell, see [these cmdlets](/en-us/powershell/module/microsoftteams/new-csagent).

## Related Teams Phone Agent setup and configuration articles

- [Third-party voice agents](aa-cq-setup-third-party-voice-agents)
- [Teams Phone Agents](aa-cq-setup-teams-phone-agent)