---
layout: Conceptual
title: Teams Management Pro portal usage reports - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/usage-reports
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
description: This article helps you in monitoring the usage of your devices in the Microsoft Teams Management Pro portal.
locale: en-us
document_id: f4102b83-0869-4ff8-aca6-50f62aff744d
document_version_independent_id: f4102b83-0869-4ff8-aca6-50f62aff744d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/usage-reports.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/usage-reports
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/usage-reports.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 628da079-4211-e4b2-ea9a-ac2f48c74022
---

# Teams Management Pro portal usage reports - Microsoft Teams | Microsoft Learn

There are reports for health and usage that are available in the **Reporting** node in the Teams Rooms Pro Management portal. The **Reporting** node contains data for the health and usage of your Microsoft Teams Rooms in the Pro Management portal. The **Overview** tab surfaces tenant-wide health trends of your rooms. The **Health** tab displays a list of rooms with their corresponding health data. Room usage based on calendar information and call quality data is visible under the **Usage** tab.

Note

This feature is available with a Teams Rooms Pro license.

## Usage

The reporting node contains data for the health and usage of your Microsoft Teams Rooms in the Pro Management portal. The Usage tab contains Room usage based on calendar information and call quality data.

To view the Usage report for all rooms, select **Reports-&gt;Usage**.

The headlines provide a few insights:

- Total rooms in your tenant
- How many don't have any booked meetings, either offline or online
- Percentage of utilization of rooms across the tenant
- Total number of booked meetings through exchange
- Percentage of booked meetings that included a Skype or Teams link
- Total calls with room participation
- Aggregate call performance score from all calls classified with "Good" quality to all calls.

Below the headline **Metrics** is a table of rooms with corresponding metrics. Select a room to view more usage details. The metrics in the table are described in the following table.

| Column | Description |
| --- | --- |
| Utilization | This represents percentage of time the room was used during business hour (Max of 8hours per day) in the selected period. The utilization is based on rooms reservations (bookings) and occupancy (devices signal usage). To learn more, please go to [Utilization metric definition](/en-us/microsoftteams/rooms/shared-spaces-insights#space-utilization-metric-definition). |
| Booked online | Of the booked meetings, the percentage of which were enabled with Teams. Ex. 10 meetings were booked. Of that, 8 had a Teams link. Booked Online = 80% |
| Scheduled meetings | Absolute number of meetings scheduled in the room. |
| Total calls | Absolute number of calls with the room as a participant. |
| Call performance | Percentage of calls with a "Good" rating. Each call is evaluated and receives a Good, Poor, Unknown rating. This metric is calculated from Good calls/Total calls. |
| Capacity | Maximum number of seats that the room can accommodate. |
| Average people count | Average number of individuals present in the room during a meeting. This data is coming from OEM cameras which support people count **but also from CloudIntelliFrame.** **Please Note**: To access the new people count data, you must enable the New Report Toggle located under Settings. **OEM cameras which support people count include**: Poly Studio E70 Video, Jabra PanaCast 50, Polycom Studio Video, AVer VC520 Pro2, AVer CAM550, Yealink UVC84 Camera, Poly Studio P15 Video, Poly Studio R30 Video, Yealink UVC86 Camera, Jabra PanaCast 50 Composite, Bose Videobar VB1, Poly Studio V52 Video, AVer VB342 Pro. This feature is first available for Teams Rooms on Windows. |

Usage is calculated at the end of each day at midnight (00:00) local time of the meeting room device.

Note

The metrics for Panels that aren't sharing an account with Microsoft Teams Rooms aren't showing yet in the usage report.

## Usage details of a room

Clicking on a room in the list view prompts a flyout with more in-depth information.

The **Calls** table shows meetings in which the room participated in a Teams call. The Room Audio Quality is evaluated for only the room, not all participants. To view call quality for all participants of a specific call, select a call by selecting the Start Time.

To view stream details for the room, select the Session Start Time.

Note

### New usage report available

The new reporting experience provides more accurate and reliable data, along with new capabilities. While the layout remains familiar, you may notice some differences in metrics due to improvements in how time zones, people count, business hours, and utilization are calculated.

- Events are now calculated using the device’s local time zone instead of UTC.
- Usage reports now focus on room-level rather than individual devices. In this case, the Host names are no longer displayed in report columns UI as rooms based rather than devices but it available under the CSV export for reference.
- Utilization now reflects both room reservations and actual occupancy, instead of reservations only.
- The usage trend chart in the Usage Details view has been temporarily removed while we enhance the chart to include both reservation and occupancy insights. It will return in following update.
- People Count is now powered by Cloud IntelliFrame in addition to OEM camera the support people count.
- Exports are now delivered as compressed files with the metadata row removed to improve performance.
- The Video Duration column has been temporarily removed due to a known issue and will return in future release.

## Insight report

The Insight report is located under the Report section of the pro-management portal. It provides a detailed overview of all the activities completed by our services during a specific time range, including the types of actions performed, such as detection, remediation, and updates. This report highlights the value we provide through actions to resolve rooms issues and how much time and money we help you save by doing that.

To view the Insight report for all rooms, select **Report** &gt; **Insight Report**.

## Actions

The Actions section of the report shows a timeline view and aggregate count of all actions completed each day by the service. Action types include detection, remediation, and updates. Details on the actions can be viewed by selecting **See details**. Once you have selected **See details**, a new panel appears with two sections; Tickets and Updates. The Tickets section shows a list of tickets with corresponding hours saved. Select the Tickets section to show an expanded view of each action taken on the respective ticket and the hours saved. The Updates section shows a list of each update applied and the corresponding tally of devices that successfully completed the update.

## Detection, investigation, and remediation

The Detection, investigation, and remediation section displays two counts respective of the specified time range: Meeting issues prevented and Incidents remediated.

## Updates

The Updates section provides a count of total updates either scheduled, in progress, or completed across the devices enrolled in the service.

## Estimated savings

The estimated hours saved from the actions completed are converted to a monetary amount based on a default rate of $50 USD/hour for IT professionals. To customize the rate, select *See details* in this section. The Detail pane allows you to input a custom hourly rate and corresponding currency to get a better monetary estimate.

## User experience

This section provides the average call rating by end-users on a scale of 1 to 5 (5 being the best).