---
layout: Conceptual
title: Microsoft Teams events usage report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/teams-events-usage-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
audience: admin
ms.topic: article
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: absri
ms.date: 2026-07-06T00:00:00.0000000Z
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Learn how to use the Teams events usage report in the Microsoft Teams admin center to get an overview of Teams events hosted in your organization.
locale: en-us
document_id: 6ef01b13-a81c-edb1-fa90-a7dae0f91e48
document_version_independent_id: 6ef01b13-a81c-edb1-fa90-a7dae0f91e48
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/teams-events-usage-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/teams-events-usage-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/teams-events-usage-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 91db0f52-f8f4-6240-87d3-7a35c747ab0f
---

# Microsoft Teams events usage report - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

The Teams events usage report in the Microsoft Teams admin center provides an activity overview of events created in your organization.

As an admin, you can view usage information, including the event title, event ID, start time, end time, event access type, total number of attendees, recording information, whether RTMP was used, and the names of the organizers, presenters, and co-organizers for each event.

Use the report to gain insight into usage trends and see who in your organization schedules and hosts events.

## View the Teams events usage report

1. In the left navigation of the Teams admin center, go to **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **Teams events usage reports**.
2. Under **Date range**, select a predefined range of 7 days or 28 days, or set a custom range. You can set a range to show data up to 90 days before and after the current date.
3. You can choose to show events by participant and their role. To do this:
    1. Under **Search by participant (optional)**, search for and choose a specific person.
    2. Under **Role of participant**, specify whether that person is an organizer or co-organizer, presenter, or attendee.
4. Select **Run report**.

## Interpret the report

[![Screenshot of the Teams events usage report in the Teams admin center with callouts.](../media/teams-events-usage-report.png)](../media/teams-events-usage-report.png#lightbox)

| Callout | Description |
| --- | --- |
| **1** | Each report has a date for when it's generated. The report reflects near real-time activity when you refresh the page. |
| **2** | - The X axis on the chart is the selected date range for the report.<br>- The Y axis shows the following data:<br>    - Total number of in org events<br>- Total number of in public events<br>- Total number of attendees<br><br> To show or hide this data on the graph, select the item. To see the total number of in org events, public events, and attendees on a specific date, hover over the dot on that date. |
| **3** | The table gives you a breakdown of each event. <br>- **Event ID** is the unique ID of the event.<br>- **Event Title** is the name that the organizer created for the event.<br>- **Status** shows whether the event is scheduled or completed .<br>- **Start Time (UTC)** refers to the start date and time of the event.<br>- **End Time (UTC)** refers to the end date and time of the event.<br>- **Organizer** is the name of the organizer.<br>- **Co-Organizers** is the name of the event co-organizers.<br>- **Presenters** is the name of the event presenters.<br>- **Event Access Type** specifies whether event access was in org or public.<br>- **Total Attendees** is the unique number of users that attended the event.<br>- **Registration Enabled** indicates whether registration was enabled for the event.<br>- **Discoverable** indicates whether the event was discoverable.<br>- **Recording** shows whether the event was recorded irrespective of the organizer's settings.<br>- **Recording views** is the total number of views for the recording.<br>- **RTMP** shows whether RTMP was **On** or **Off** for the event. When **On**, the organizer used an external application or device to produce the event.<br><br>If a user account no longer exists in Microsoft Entra ID, their user name is displayed as "--" in the table. |

Note

- The report shows up to 100 events that match the current report criteria. To see more events, apply date filters to reduce the list size.
- Visibility of specific report columns—including Recording, Recording Views, Total Attendees, and RTMP—is subject to the following criteria:
    - The event must have started.
    - There must be a minimum of three participants (that is, participant count ≥ 3).
    - The event must run for at least 900 seconds (15 minutes).
    - These columns might take up to 28 hours after the event ends to appear in the usage report.