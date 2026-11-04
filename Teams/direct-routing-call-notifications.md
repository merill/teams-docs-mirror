---
layout: Conceptual
title: Manage call notifications for Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-call-notifications
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.date: 2026-09-28T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Direct Routing call notification
ms.localizationpriority: medium
locale: en-us
document_id: 12597063-548f-8e0c-dcdc-11b98ea1601e
document_version_independent_id: 3c864a67-3a57-c810-7c75-cfddefc84bc7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-call-notifications.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-call-notifications
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-call-notifications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7c06a993-fec1-b641-4c6f-9223c9fb77d1
---

# Manage call notifications for Direct Routing - Microsoft Teams | Microsoft Learn

This article describes how to manage call notifications for your Direct Routing users. You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC). This setup is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.

In the following diagram, user Irena has two endpoints:

- A Teams endpoint
- A SIP phone connected to a third-party SBC

When a call arrives, the SBC forks the call between Direct Routing and the third-party SBC.

![Diagram showing forked Teams endpoints.](media/direct-routing-call-notification-1.png)

If the call is accepted on Fork 2 (by the third-party SBC), Teams generates a “Missed Call” notification.

You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:

```console
Reason: SIP;cause=200;text="Call completed elsewhere"
```

The call isn't registered in the call detail records of Microsoft Teams Phone System as a successful call. The call is registered as an “Attempt” with Final SIP Code “487,” Final Microsoft subcode “540200,” and Final SIP Code Phrase “Call completed elsewhere.” (To view the call detail records, go to the Teams Admin center -&gt; **Analytics and Reports** -&gt; **Usage Reports**, and select **PSTN Usage.**)

The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.

![Diagram shows forked Teams endpoints.](media/direct-routing-call-notification-2.png)