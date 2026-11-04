---
layout: Conceptual
title: Microsoft Teams external domain activity report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/external-domain-activity-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
audience: Admin
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: charup
ms.date: 2026-09-25T00:00:00.0000000Z
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Learn how to use the Teams external domain usage report in the Microsoft Teams admin center to get an overview of external domain activity in your organization.
locale: en-us
document_id: c9c727a5-8b06-1d35-2ecd-0d65f4dc8320
document_version_independent_id: c9c727a5-8b06-1d35-2ecd-0d65f4dc8320
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/external-domain-activity-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/external-domain-activity-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/external-domain-activity-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 29abad22-aa2e-3c27-d241-66b7aab37556
---

# Microsoft Teams external domain activity report - Microsoft Teams | Microsoft Learn

![Information icon.](../media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

The external domain activity report in the Microsoft Teams admin center shows you how you communicate with managed external organizations over chat. This report includes information for 1:1 chats, group chats, and meeting chats.

Note

We count the following events as meeting chats: When a user is invited to a meeting, when a meeting ends, and when a user leaves a meeting chat.

This report includes both a base and Teams Premium version. The base version tells you which domains you communicate with and the premium version exposes more detailed information about your communication with each domain.

Note

If you have an explicit allowed domains list, this report might include domains that aren't on your allow list. It's possible for users from an allowed organization to start a group chat with users from your organization and users from other organizations allowed by them, but not allowed by you. These domains show up in your external domain activity report.

## View the usage report

1. In the left navigation of the Teams admin center, go to **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **External domain activity**.
2. Under **Date range**, select a predefined date range.
3. Select **Run report**.

## Interpret the report

[![Screenshot of the Teams external domain activity report in the Teams admin center.](../media/external-domain-report-small.png)](../media/external-domain-report-expand.png#lightbox)

| Item | Description |
| --- | --- |
| Domain name | The domain name. **Premium:** Each domain is clickable so you can see domain-specific insights. |
| People in my org | The number of users who communicated with the organization through chat during the selected time range. |
| **Premium:** Total messages | The number of messages exchanged between your organization and the external domain during the selected time range. |
| **Premium:** Messages sent | The number of messages sent by users in your organization to conversations involving the external domain during the selected time range. |
| **Premium:** Messages received | The number of messages sent by users from the external domain into conversations involving users in your organization during the selected time range. |

- It's possible for **People in my org** to be 0 (zero). If an external domain reaches out to your organization and receives no response, the report shows 0 (zero) for **People in my org**.
- In addition to managed communication, the report looks at when anonymous users join meetings. If **Anonymous user join** is turned on, you might have unexpected domains appear on your list. The report shows the names of the domains of the users who joined meetings, rather than marking them as anonymous.
- Premium columns shouldn't be considered accurate until 7 days, 30 days, and 60 days, respectively, after a Teams Premium license is assigned. Some rows might show 0 (zero) or message counts and user counts that don't align with recent activity.
- Even if a domain has activity in just one or two, but not all three of the potential date ranges (7 days, 30 days, and 60 days), the domain still appears in the reports for all three date ranges. It shows total internal users as 0 (zero) and all premium columns as 0 (zero), if applicable. If a Teams Premium license was assigned more than 60 days ago, you can assume that a row of all 0 (zero) values in the 7-day or 30-day reports means that there was no communication with the domain during that date range, despite the domain name appearing on the list. There shouldn't be all 0 (zero) values in a 60-day report unless a Teams Premium license was assigned less than 60 days ago.

## Interpret the domain-specific report

| Item | Description |
| --- | --- |
| **Premium:** Username | The User Principal Name (UPN) of the user in your organization who communicates with the external domain. |
| **Premium:** Messages sent | The number of messages sent by the listed user to conversations involving the external domain during the selected time range. |

Note

Due to privacy concerns, it's not possible at this time to expose the messages received at a per-user basis.