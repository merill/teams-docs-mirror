---
layout: Conceptual
title: Planning - Reporting Considerations - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-reporting
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
ms.topic: concept-article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.date: 2026-11-03T00:00:00.0000000Z
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
customer-intent: As a Teams Administrator, I want to learn how to get historical reports on the number of calls my Teams Phone Agents, Auto Attendants, and Call Queues processed, and how nesting might affect those reports.
description: Learn the historical reporting options for voice applications, and how nesting with or without resource accounts affects reports.
locale: en-us
document_id: ad6d2508-b053-c988-7735-80f4c89e3eed
document_version_independent_id: ad6d2508-b053-c988-7735-80f4c89e3eed
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-reporting.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-reporting
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-reporting.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: ab1b1c31-9e44-02f2-7153-e152befecddf
---

# Planning - Reporting Considerations - Microsoft Teams | Microsoft Learn

This article is for IT pros and administrators who want to learn about historical reporting for voice applications (Teams Phone Agents, Auto Attendants, and Call Queues).

## Reporting and nesting

There are several reporting options for voice applications. The reporting option you choose determines whether call flows that are nested without resource accounts are included, as described in the following sections.

### Teams admin center usage reports

The **Auto Attendant Usage** and **Call Queue Usage** reports in the Teams admin center only provide a count of the number of calls received. These reports also don't support the following:

- Reporting on auto attendants or call queues that are nested without resource accounts.
    - Nest with resource accounts if you need to use the Teams admin center reports.
- More than 28 days of reporting.
    - Use the [Teams Phone Agent, Auto Attendant and Call Queue historical reports](aa-cq-report-historical) in Power BI and in Queues App to get up to 45 days.
- Access by authorized users.
    - Authorized users don't have access to the Teams admin center.

### Power BI historical reports

[Voice applications historical reports](aa-cq-report-historical) support nesting with or without resource accounts.

In addition:

- Authorized users see only the applications, and the associated representatives (agents) they're authorized for.
- They can be authorized to see every applications and representative if needed.
- Administrators see all the applications and representatives configured in the tenant.

### Queues App historical reporting

For information about reporting in Queues App, see [Use the Queues App for Microsoft Teams](https://support.microsoft.com/office/370ad83e-c2c1-4a9f-8a59-16c98be102e9).

**Queues app users require a Teams Premium license.**