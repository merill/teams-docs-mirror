---
layout: Conceptual
title: SIP call flow for Direct Routing in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-monitor-sip-ladder
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: teddygyabaah
ms.date: 2026-03-25T00:00:00.0000000Z
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- NOCSH
description: Analyze Microsoft Teams Direct Routing calls with SIP call flow feature
locale: en-us
document_id: 35edbabb-bec1-2a60-4f54-0560bf8ac3a1
document_version_independent_id: 35edbabb-bec1-2a60-4f54-0560bf8ac3a1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-monitor-sip-ladder.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-monitor-sip-ladder
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-monitor-sip-ladder.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 59320ce7-1d51-56c3-9c59-750e79eff0de
---

# SIP call flow for Direct Routing in Microsoft Teams - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Direct Routing

This article describes the **SIP call flow** feature and is intended for Teams telephony admins and IT Pros who are diagnosing call flow issues between your organization's Session Border Controller (SBC) and Microsoft's Session Initiation Protocol (SIP) Proxy in Direct Routing deployments.

By using the SIP call flow in the Teams admin center, you can see a visual, chronological sequence of the SIP signaling messages exchanged between SBC and SIP Proxy.

## Prerequisites

Access to the Teams admin center is required using one of the following [Teams administrator roles](using-admin-roles):

- Teams Administrator
- Teams Telephony Administrator

Your [Direct Routing](direct-routing-plan) environment must be correctly configured, with a properly connected and functioning SBC. For more information, see [Configure Direct Routing](direct-routing-configure).

## Access SIP call flow

To access the SIP call flow, do the following steps:

1. In the Teams admin center, go to the left side rail and select **Analytics & reports**.
2. Select **Usage reports**.
3. Generate a **PSTN usage** report.
4. From the report drop-down, select **PSTN Usage** report, select a desired date range, and select **Run Report**.
5. In the generated report, select the **Direct Routing** tab.
6. In the displayed records of Direct Routing calls, identify and select the desired call to audit.
    1. From the list heading, select **SIP call flow**, or
    2. From the available columns, find the **Final SIP code** column header and select the Final SIP Code of the selected call.
7. From the SIP call flow in the displayed SIP events, identify and select the SIP event to review.
8. View the protocol details that pop out in the right-hand view.

Note

Allow up to 30 minutes for the SIP call data to be processed and uploaded to the Teams admin center for reporting. Call records older than 30 days aren't available for SIP call flow.

## Understanding the SIP call flow view

The SIP call flow visually represents the call as a series of interactions between your organization’s SBC and Microsoft SIP Proxy. The visual representation is known as a *ladder diagram*.

Each "rung" of the ladder represents a SIP message.

The direction of the arrow indicates the sender and receiver of the message. Messages are displayed in chronological order from top to bottom, allowing you to follow the sequence of protocol events during the call.

Each SIP message in the call flow has corresponding details, indicating what was contained in the SIP message.

Selecting the SIP event for any SIP message will bring more details for that event into view in the right-hand side bar.

For more information on SIP messages, see [Direct Routing protocols](direct-routing-protocols-sip).

## Troubleshooting with the SIP call flow

For guidance in diagnosing issues, see [Diagnose issues with Direct Routing](/en-us/microsoftteams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

For referencing SIP response codes, see [Microsoft and SIP response codes](/en-us/microsoftteams/troubleshoot/phone-system/direct-routing/microsoft-sip-response-codes).