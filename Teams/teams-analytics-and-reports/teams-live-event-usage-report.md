---
layout: Conceptual
title: Microsoft Teams live event usage report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/teams-live-event-usage-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: anahitab
audience: admin
ms.topic: article
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: chbalaki, cmunden
ms.date: 2024-09-18T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Learn how to use the Teams live event usage report in the Microsoft Teams admin center to get an overview of Teams live events activity in your organization.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: d5372edb-6ffe-34a3-0839-587e48f66f6b
document_version_independent_id: 43903b13-37de-7dde-5b8c-739586cc2d87
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/teams-live-event-usage-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/teams-live-event-usage-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/teams-live-event-usage-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3a658f38-ab8f-c8a4-326d-c0d90cd87271
---

# Microsoft Teams live event usage report - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

The Teams live event usage report in the Microsoft Teams admin center shows you the activity overview for live events held in your organization. As an admin, you can view usage information, including event status, start time, views, and production type for each event. You can gain insight into usage trends and see who in your organization schedules, presents, and produces live events.

## View the live event usage report

1. In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **Teams live event usage**.
2. Under **Date range**, select a predefined range or set a custom range. You can set a range to show data up to a year, six months before and after the current date.
3. (Optional) Under **Organizer**, you can choose to show only live events organized by a specific user.
4. Select **Run report**.

## Interpret the report

[![Screenshot of the Teams live event usage report in the Teams admin center with callouts.](../media/teams-live-event-usage-report-with-callouts.png)](../media/teams-live-event-usage-report-with-callouts.png#lightbox)

| Callout | Description |
| --- | --- |
| **1** | The Teams live event report can be viewed for trends over the last 7 days, 28 days, or a custom date range that you set. |
| **2** | Each report has a date for when it was generated. The report reflects near real time activity when the page is refreshed. |
| **3** | - The X axis on the chart is the selected date range for the report.<br>- The Y axis is the total view count.<br><br>Hover over the dot on a given date to see the number of views across all live events on that date. |
| **4** | The table gives you a breakdown of each live event. <br>- **Event** is the display name of the live event. Select the event name to get more details about the event.<br>- **Start Time** refers to the start date and time of the event.<br>- **Event Status** shows whether the event took place.<br>- **Organizer** is the name of the event organizer.<br>- **Presenters** are the names of the event presenters.<br>- **Producers** are the names of the event producers.<br>- **Views** is the number of unique views after the event is completed.<br>- **Recording** shows whether the recording setting is on or off.<br>- **Production Type** shows whether the event is produced in Teams or by an external application or device.<br><br>If a user account no longer exists in Microsoft Entra ID, the user name is displayed as "--" in the table. To see the information that you want in the table, make sure to add the columns to the table. |
| **5** | Select **Edit columns** to add or remove columns in the table. |

## Notes

- We show a maximum of up to 100 live events that match the current report criteria. To see more live events, apply date filters to reduce the list size.
- Anonymous presenters aren't included in the report.
- Users who watch the event recording or the event on demand aren't included in the view count.

## View event details

The live event details page gives you a summary of the details of a live event and lists all the files, including transcripts and recordings, associated with the event. Select a file name to view or download the file.

[![Screenshot showing details of a live event.](../media/teams-live-event-usage-report-event-detail.png)](../media/teams-live-event-usage-report-event-detail.png#lightbox)

If your organization uses Microsoft eCDN, advanced analytics can be viewed and exported from the [eCDN Dashboard](https://admin.ecdn.microsoft.com). If your organization is enabled for [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN or [Kollective](https://kollective.com) eCDN, you can get more attendee analytics by clicking the partner report link.