---
layout: Conceptual
title: Microsoft Teams external domain anomalies report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/external-domain-anomalies-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: The External Domain Anomalies Report surfaces unusual external collaboration patterns between users in your organization and external domains in Microsoft Teams.
author: freda-freda-li
ms.author: lifreda
manager: charup
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.topic: article
ms.date: 2026-03-06T00:00:00.0000000Z
locale: en-us
document_id: 36981a05-a730-a304-2fb2-607d7809f1e9
document_version_independent_id: 36981a05-a730-a304-2fb2-607d7809f1e9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/external-domain-anomalies-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/external-domain-anomalies-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/external-domain-anomalies-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 94b3e754-d131-baa8-16cf-37911c4becda
---

# Microsoft Teams external domain anomalies report - Microsoft Teams | Microsoft Learn

## Overview

The External Domain Anomalies Report in the Microsoft Teams admin center helps administrators identify unusual external collaboration patterns between users in the organization and external domains.

This detection focuses specifically on **first-time external-to-internal contact**. Ongoing or previously established relationships are not evaluated in the same way. The signal is designed based on observations that higher-risk scenarios often correlate with sudden increases in new external contact from a domain. By emphasizing first-time interaction patterns rather than ongoing collaboration, the report highlights deviations from typical organizational behavior.

The report uses behavioral deviation analysis to identify domains exhibiting unexpected increases in new external engagement. These anomaly-based risk signals help administrators recognize external collaboration patterns that may warrant further review, taking into account their organization’s specific business context.

## View the External Domain Anomalies report

To view the External Domain Anomalies report:

[![Screenshot that shows the External Domain Anomalies report.](../media/external-domain-anomalies-report.png)](../media/external-domain-anomalies-report.png#lightbox)

- In the left navigation of the **Microsoft Teams admin center**, select **Analytics & reports** &gt; **Protection reports**.
- On the **View reports** tab, select **Communication anomalies** from the **Report** drop-down menu. Under the **Type** drop-down menu, **External domains anomalies** is selected by default.
- Under **Date range**, select a predefined time range (for example, **Last 24 hours**, **Last 3 days**, **Last 7 days**, or **Last 10 days**).
- Select **Run report**.

The report displays domains that exhibit anomalous first-time external-to-internal contact patterns within the selected time period.

## Interpret the External Domain Anomalies Report

| **Item** | **Description** |
| --- | --- |
| Domain | The external domain where anomalous communication activity was detected within the selected date range. |
| Total anomalies | The total number of anomaly events detected within the selected date range. Anomalies are evaluated daily and by activity type (e.g., 1:1 and Group). If both 1:1 and Group exceed their respective baselines on the same day, they are counted as two separate anomaly events. This value represents the number of anomaly events and should not be interpreted as anomaly days, message counts, or the total number of anomalous conversations. |
| 1:1 threads | The number of newly created 1:1 chat threads between users in your organization and the external domain within the selected time range. |
| Group threads | The number of newly created group chat or channel threads between users in your organization and the external domain within the selected time range. Each thread is counted once. |
| 1:1 threads baseline | The expected daily number of 1:1 threads calculated based on the domain’s historical communication patterns. |
| Group threads baseline | The expected daily number of group threads calculated based on the domain’s historical communication patterns. |
| 1:1 threads anomaly | When the observed daily 1:1 threads value exceeds the corresponding daily baseline threshold, the system flags that day as an anomaly and displays the observed value in the report. |
| Group threads anomaly | When the observed daily Group threads value exceeds the corresponding daily baseline threshold, the system flags that day as an anomaly and displays the observed value in the report. |

- When a specific domain is selected from the table, the chart above updates dynamically to display that domain’s communication activity trends and anomaly events within the selected date range.
- Each red dot on the chart represents a single anomaly event. An anomaly event is generated when the observed daily value exceeds the corresponding baseline threshold.

## Report structure and export behavior

The report consists of two main components: a **chart section** and a **table section**.

The chart displayed on the screen updates dynamically based on the selected table row. Selecting a specific domain in the table changes the chart view to reflect that domain’s activity within the selected date range.

The report provides two separate export options:

- **Table export** downloads the data currently displayed in the table for the selected date range.
- **Chart export** downloads data for all charts corresponding to all rows in the table within the selected date range. It is not limited to the chart currently visible based on the selected table row.

## Alert configuration and notifications

Administrators can enable alerts for external domain anomalies to receive proactive notifications when anomaly events are detected.

Once enabled, the system generates a notification when the observed activity exceeds the defined baseline threshold. Alerts may be configured to provide a daily summary of detected anomaly events.

Notifications include the affected domain, anomaly type (e.g., 1:1 or Group threads), and relevant activity metrics to support investigation and response.

## Set up alerts for External Domains Anomalies

To configure alerts for external domain anomalies:

- In the left navigation of the **Microsoft Teams admin center**, select **Notifications & alerts** &gt; **Rules**.
- On the **Rules** page, select **External domains anomalies**.
- Choose the notification channel where you would like to receive alerts.
- Set the rule status to **Enabled**, and then select **Save**.

Note

Alerts are not enabled by default. You will not receive notifications until you explicitly enable the rule.

## Notification delivery

Once the alert rule is enabled, notifications are delivered to the selected channel in the Microsoft Teams client.

When an anomaly event is detected, a notification message is posted to the configured channel. The notification includes the affected domain, a summary of the detected anomaly activity, and a **View full report** link.

Selecting **View full report** opens the External domain anomalies report in the Teams admin center, where admins can review detailed activity.