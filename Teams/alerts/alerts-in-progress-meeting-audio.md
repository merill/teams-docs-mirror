---
layout: Conceptual
title: Alerts for in-progress meeting audio quality issues - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/alerts/alerts-in-progress-meeting-audio
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: jtremper
author: jacktremper
manager: pamgreen
ms.reviewer: vapati
ms.date: 2024-12-04T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: 
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier2
description: Learn how to set up alerts for audio quality issues detected in in-progress meetings.
locale: en-us
document_id: 1eb049c6-9520-4249-57da-a0a033d6778e
document_version_independent_id: 1eb049c6-9520-4249-57da-a0a033d6778e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/alerts/alerts-in-progress-meeting-audio.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: alerts/alerts-in-progress-meeting-audio
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/alerts/alerts-in-progress-meeting-audio.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 3d26a601-2c9b-acc9-093a-7776c9b0e24f
---

# Alerts for in-progress meeting audio quality issues - Microsoft Teams | Microsoft Learn

![Information icon.](../media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

Connectivity issues in Microsoft Teams can significantly impact audio, video, and screen sharing experiences. As an admin, you can set up alerts for in-progress meeting audio issues and be informed immediately when the users you specify experience issues.

Notifications are available for packet loss, jitter, local healed ratio, and round trip time. You can customize the threshold for each parameter and set the frequency of notifications to suit your needs.

These alerts will help diagnose symptoms such as dropped calls, call disconnects, choppy audio, video freezing and lag.

Notifications can be sent to a Teams channel or a web hook URL.

To be monitored, meeting attendees must have a Teams Premium or Teams Rooms Pro license.

## Set up alerts for audio quality issues

1. In the left navigation of the Microsoft Teams admin center, select **Notifications & alerts** &gt; **Rules**.
2. In the **Rules** Page, select **Audio quality for in-progress meetings**.
3. Select the options as described in the following table, and then select **Save**.

    | Field | Description |
    | --- | --- |
    | **Audio conditions** | Choose the audio issues that you want to monitor for. |
    | **Monitoring settings** | Choose the **Notification threshold** and **Monitoring window** to specify how long the condition should exist before an alert is sent.Choose the **Notification waiting period** to specify how often an alert is sent. |
    | **Scope** | Choose the users whose meeting audio quality you want to monitor. |
    | **Subnet notifications** | Select which networks you want to get alerts for. You can select either 'Internal subnets' or 'Internal and external subnets'. If 'Internal subnets' is selected, some [common](../quality-of-experience-review-guide#common-subnets) external subnets for homes, hotels, and similar areas are excluded. |
    | **Actions** | Choose if you want to send alerts to a specific channel or to a web hook URL. |
    | **Status** | Choose if the rule is active and alerts should be sent. |

## Platform support

To view the list of platforms that support this feature, see [Microsoft Teams Premium - Overview for admins](../enhanced-teams-experience#).