---
layout: Conceptual
title: Manage the Meeting Recaps app for your organization in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-meeting-recaps-app
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.date: 2026-08-05T00:00:00.0000000Z
ms.author: v-lanchin
author: LanaChin8
ms.reviewer: chenanqi
manager: v-jesserowe
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
audience: admin
f1.keywords:
- NOCSH
search.appverid: MET150
description: Learn how to manage the Meeting Recaps app in Microsoft Teams for users in your organization.
locale: en-us
document_id: 02214fc4-5c8a-760a-39e4-4a69717d2c0a
document_version_independent_id: 02214fc4-5c8a-760a-39e4-4a69717d2c0a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-meeting-recaps-app.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-meeting-recaps-app
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-meeting-recaps-app.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4dbf3540-0ae6-ebd1-33f9-72975cc2593c
---

# Manage the Meeting Recaps app for your organization in Microsoft Teams - Microsoft Teams | Microsoft Learn

## Overview

The Meeting Recaps app in Microsoft Teams provides a centralized view of meeting recaps, making it easier for users to find, filter, and catch up on their recent meetings. The app supports multiple recap modalities, including intelligent text recap, video recap, and audio recap. Audio recap can combine content from multiple meetings into a single podcast-style summary, helping users stay up to date across meetings.

To learn more about the user experience, see [Get started with the Meeting Recaps app](https://support.microsoft.com/teams/meetings/meeting-recap-app-teams).

[![Screenshot of the Meeting Recaps app homepage.](media/manage-meeting-recaps-app.png)](media/manage-meeting-recaps-app.png#lightbox)

The app is preinstalled in Teams but isn't pinned by default. Users can pin the app themselves, or admins can pin the app for users through an app setup policy in the Teams admin center.

## Key considerations

- Only recorded or transcribed meetings appear in the Meeting Recaps app.
- The Meeting Recaps app displays recaps for meetings that occurred within the previous 30 days.
- The app is available in Teams desktop for Windows and Mac and Teams web clients. Mobile support is coming soon.
- All Teams users can access the Meeting Recaps app homepage. Users can view meetings in a list or grid layout and use search and filters to find meeting recaps.

    Some recap experiences require additional licenses. For more information, see Licensing in this article.
- The accuracy of the **Missed** status on the Meeting Recaps homepage depends on the availability and completeness of Teams meeting attendance report data. If attendance reporting is disabled by policy or for a meeting, or if an attendee isn't included in the report, the status might be inaccurate.

    To learn more about attendance reports, see [Manage the attendance and engagement report for meetings and events in Microsoft Teams](teams-analytics-and-reports/meeting-attendance-report) (admins) and [Manage meeting attendance reports](https://support.microsoft.com/teams/meetings/manage-meeting-attendance-reports-in-microsoft-teams) (meeting organizers).

## Licensing

- AI-generated recap experiences, including audio recap and video recap, require a Microsoft Copilot license.
- Intelligent text recap requires a Teams Premium or Microsoft Copilot license.
- Users without a Microsoft Copilot license can still access meeting transcripts that they have permission to view.

## Pin the Meeting Recaps app for your users

By using [app setup policies](teams-app-setup-policies), you can customize Teams to pin apps for users in your organization. The apps you add to a policy are pinned to the Teams app bar, where users can quickly access them.

You can edit the global (Org-wide default) policy or create and assign a custom app setup policy.

To pin the Meeting Recaps app for users, follow these steps:

1. In the left navigation of the Teams admin center, go to **Teams apps** &gt; **Setup policies**.
2. Select the **Global (Org-wide default)** policy or select **Add** to create a new policy.
3. Under **Pinned apps**, select **Add apps**.
4. Search for and select **Meeting Recaps**, and then select **Add**.

    [![Screenshot showing how to add the Meeting Recaps app to an app setup policy in the Teams admin center. ](media/manage-meeting-recaps-app-pin.png)](media/manage-meeting-recaps-app-pin-expand.png#lightbox)
5. Select **Save**.