---
layout: Conceptual
title: What is Call Quality Dashboard (CQD)? - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cqd-what-is-call-quality-dashboard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
ms.reviewer: mikedav, siunies, gageames, jamp
ms.date: 2026-07-01T00:00:00.0000000Z
ms.topic: concept-article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Learn about Call Quality Dashboard (CQD) and how to use it to see reports on meeting and call quality in Microsoft Teams.
locale: en-us
document_id: d2651812-1f09-bb31-92f3-82c53eb05fc4
document_version_independent_id: ea2cf1a2-d045-53e6-4066-051726fd4600
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/CQD-what-is-call-quality-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cqd-what-is-call-quality-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/CQD-what-is-call-quality-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: a376d363-ee71-0236-e662-3767146d2b77
---

# What is Call Quality Dashboard (CQD)? - Microsoft Teams | Microsoft Learn

The Microsoft Call Quality Dashboard (CQD) - https://cqd.teams.cloud.microsoft - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, and Skype for Business Server.

The latest version of CQD features a [near-real-time (NRT) data feed](cqd-data-and-reports), which means that call records are typically available in CQD within 30 minutes of the end of a call.

Wherever CQD includes [end-user identifiable information (EUII) data](cqd-data-and-reports#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/en-us/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level. You can use CQD to help you **optimize your network** to drive performance quality. CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business. With CQD, overall patterns can become apparent, so network engineers can make informed assessments of call quality. CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://developer.microsoft.com/microsoft-edge/webview2/).

![Screenshot of Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

We encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building. The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users. To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](cqd-upload-tenant-building-data) in Teams admin center.

![Screenshot of Call Quality Dashboard's Location-Enhanced Reports.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.

## What's New

This section summarizes recent minor changes to the Call Quality Dashboard schema and logic.

### September 2026

- Started rolling out a new user experience for [custom Detailed Reports](cqd-data-and-reports#create-custom-detailed-reports) with improved accessibility features. This change was announced in Message Center post MC1466864.
- Improved the coverage of the `MeetingId` column for view-only and streaming attendees in live events.

### August 2026

- Revised logic for **First/Second UPN** and **First/Second Object Id** to reflect users associated with Teams Phone Mobile phone numbers in PSTN calls.
- Introduced a refreshed user interface for [creating custom reports](cqd-data-and-reports#create-custom-detailed-reports) with improved accessibility features.

### July 2026

- Added support for Public IP values when [managing building metadata files](cqd-upload-tenant-building-data).
- Added **First/Second Public IP** columns to reflect the values used in an active building file.
- Modified logic for the **First/Second Transport Protocol** columns to improve data coverage for web platforms.
- Modified **First/Second User Agent Category** from `Microsoft Teams VDI VMware` to `Microsoft Teams VDI Omnissa`.
- Modified **First/Second User Agent Category** to `Microsoft Teams VDI (VM Screenshare)` for sessions that utilize virtual machine screensharing, as announced in Message Center post MC1387528.

### April 2026

- Revised logic for **First/Second Feedback Rating** to populate "0" when a user submits a Rate My Call survey with no call rating. A "0" value indicates the survey was offered but the user either did not submit the survey or submitted the survey with no call rating.

### February 2026

- Revised logic for **Meeting Id** to align the value with the numeric Meeting Id found in Teams meeting invites. This change was announced in Message Center post MC1183608.
- Added **Thread Id** column to allow searching for meetings by the value that was previously populated under Meeting Id.

### January 2026

- Added **First/Second Is Call Throttled** and **Avg First/Second Is Call Throttled** columns to indicate when media quality may be affected by device CPU throttling.
- Added **First/Second HW Encoder Blocked** and **First/Second HW Decoder Blocked** columns to indicate when media quality may be affected by blocked hardware drivers.

## Use Power BI to analyze CQD data

[Download Power BI query templates for CQD](https://download.microsoft.com/download/f/b/f/fbf2527c-f392-410e-aeb6-1a02ac1b5dd1/CQD-Power-BI-query-templates.zip). Use customizable Power BI templates to analyze and report your CQD data.

For more information, see [Use Power BI to analyze CQD data](cqd-power-bi-query-templates).