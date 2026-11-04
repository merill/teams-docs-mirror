---
layout: Conceptual
title: Teams Management Pro portal health reports - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/health-reports
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.date: 2025-02-28T00:00:00.0000000Z
ms.reviewer: obahidika
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: This article helps you in monitoring the health of your devices in the Microsoft Teams Management Pro portal.
locale: en-us
document_id: 16517818-b4c9-d014-8ee5-90925a09b6e9
document_version_independent_id: 16517818-b4c9-d014-8ee5-90925a09b6e9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/health-reports.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/health-reports
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/health-reports.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ee6354e8-3d0e-c8b8-a2fc-05925084dcbd
---

# Teams Management Pro portal health reports - Microsoft Teams | Microsoft Learn

There are reports for health and usage that are available in the **Reporting** node in the Teams Rooms Pro Management portal. The **Reporting** node contains data for the health and usage of your Microsoft Teams Rooms in the Pro Management portal. The **Overview** tab surfaces tenant-wide health trends of your rooms. The **Health** tab displays a list of rooms with their corresponding health data. Room usage based on calendar information and call quality data is visible under the **Usage** tab. This feature is available with a Teams Rooms Pro License.

Note

We updated the Teams Rooms Health reports to use the same reporting platform used across other reporting experiences in the portal.

1. The health report is now room-based instead of device-based.
2. Host names are no longer displayed directly in report columns UI because reporting is now focused on room-level insights rather than individual devices. Host names will remain available through the data export.
3. The health report includes offline tickets in health calculations.
4. The Active Tickets trend chart within the health drilldown is temporarily unavailable in the initial release of the new Health Report experience. We are improving this visualization and plan to reintroduce it with the four utilization states.

## Export tickets

The ticket export feature lets you export all active and closed ticket history information within a select date range. Exporting tickets lets you easily access and analyze your ticket history data for better decision making.

Under the **Overview** report, the **Export tickets** button provides ticket history details that include the following fields: creation date, device name, incident type, ticket state, ticket, last update, history, last resolved date, message/notes conversations, closure summary, closed by, and last closed date.

The data is generated in a JSON file that you can download and import into Power BI. The download starts after you select **Export tickets**. If you leave the portal before the download starts, you have to request the file again.

| Column | Description |
| --- | --- |
| Created | Date and time the ticket was created |
| Device | Device ID of the room mapped in room name (display name) and host name |
| Incident Type | Spread in incident type ID, incident type display name, which is a sub category in UI, the incident type category (for example, account, config) and the incident type severity (for example, critical, important) |
| State | The state/status of the ticket, which can be new, investigating, resolved, or closed and watching |
| TicketID | The ticket ID in "7B7365-EPDOLF" format |
| LastUpdate | Any updates made on the ticket with specific date and time |
| History | Detailed history of the ticket status overtime |
| SnowIncident | SNOW incident number in "INC11684776" format |
| LastResolved | Date and time when the ticket was last resolved |
| Closure Summary/Reason | The reason for ticket resolution (for example, self resolved) |
| Closure Summary/Closed By | Who is responsible for closing the ticket (for example, Managed Room Services) |
| LastClosed | The date/time the ticket was closed |

## Navigating reports

The overview section provides graphical representations of important aspects of meeting room management. The charts change depending on the time span selected or group selected. To change the time span, select the drop-down menu.

To change the group, select the group selection drop-down menu in the banner.

### Tickets by category

The donut displays the total tickets raised for the selected time span and group (default is seven days, all groups). Tickets are represented in their major categories: Audio, Display, Peripherals, Connectivity, Versioning, and Recorded issues.

A flyout for the detailed view for tickets of that category appears when selected.

In the flyout, it's possible to filter the list of tickets by the subcategory by selecting the respective part of the donut.

To navigate back, either select on the donut or select on the breadcrumb at the top left.

To navigate to a specific ticket in this list view, select on the link under the **Support ticket column**.

### Health history

This graph shows the average health (definition in Health section) for all the rooms in the tenant and the average health for all Microsoft Teams Rooms Pro customers on a day-to-day basis. You can view the average health for up to 90 days.

### Most reliable/least reliable rooms

Two tables show the most reliable and least reliable rooms based on health. For the full list view, select Health, then sort the list by the Health column.

### Rooms history

Provides a historical view of rooms enrolled in the service and provides a comparative view of rooms that were healthy or unmonitored in the same time period.

## Health

The reporting node contains data for the health and usage of your Microsoft Teams Rooms in the Pro Management portal. The Overview tab surfaces tenant-wide health trends of your rooms. The Health tab displays a list of rooms with their corresponding health data.

To navigate to the Health report for all rooms, select Reports, then select **Health**.

A room can either be healthy or unhealthy for a given day. It's considered unhealthy if a ticket or many tickets with a severity of critical or important impacted the room for more than 20 total minutes during non-maintenance hours (5AM - 12AM machine local time). For example, if a ticket is opened at 5:00 AM but closed at 5:15 AM, the room is still considered healthy because the ticket was only open for 15 min. Similarly, if a ticket occurs from 5:00 AM to 5:21 AM, it's considered unhealthy for the day. Additionally, if a second ticket occurred later that same day from 09:00 AM to 9:10 AM, the room would still be considered unhealthy for the day.

Note

Health reports are aggregated once a day at 12:00 AM UTC time. For customers near the international date line, reports may be inaccurate due to aggregation near the middle of the workday.

Note

Rooms that are onboarding are hidden from the list of rooms in the Reports &gt; Health tab. Rooms that are onboarding or unmonitored do not count towards the average health of the tenant.

Clicking on a room listed in this view displays more details.

The bar graph displays the number of tickets on each day. Tickets opened on that respective day appear in blue. Tickets opened prior to the respective day appear in orange. Clicking on a day on the graph filters the pie chart and table to the relevant tickets. To reverse the filter, navigate with the breadcrumbs or select on the graph.

Categorization of tickets is represented in the donut chart. Interacting with this filters the timeline graph and table. To reverse the filter, navigate with the breadcrumbs or select on the graph.

The meeting impact view shows scheduled meetings during which a ticket with a severity of "Important" or "Critical" was open. The purpose of this view is to provide an approximation of meetings where participants could have experienced issues.

The Settings tab displays the metadata of the room such as the hardware information, device settings, BIOS information, app settings, and location.