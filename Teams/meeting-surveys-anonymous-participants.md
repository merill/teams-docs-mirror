---
layout: Conceptual
title: Manage feedback surveys for anonymous participants in Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-surveys-anonymous-participants
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: anahitab
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: jewilcze
ms.date: 2026-07-06T00:00:00.0000000Z
search.appverid: MET150
audience: admin
description: Learn how to control whether anonymous participants who join Teams meetings and events hosted by your organization receive surveys to provide feedback to Microsoft about their meeting or event experience.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
- m365initiative-meetings
- m365-virtual-appointments
locale: en-us
document_id: 103564e7-a982-f195-9e3a-016f5ebeeb05
document_version_independent_id: 103564e7-a982-f195-9e3a-016f5ebeeb05
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-surveys-anonymous-participants.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-surveys-anonymous-participants
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-surveys-anonymous-participants.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 299dba8e-a9fa-7c81-7fa7-31e1f29d2f38
---

# Manage feedback surveys for anonymous participants in Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

## Overview

[Anonymous participants](anonymous-users-in-meetings) who join Teams meetings (including virtual appointments) and events hosted by your organization can rate their meeting experience and send us feedback about the rating they give through surveys. We’re continually improving the Teams meeting and event experience and we use this feedback to help make it better.

By default, this feature is turned on for your organization and anonymous participants receive surveys. When a meeting or event ends, anonymous participants see a prompt on the screen that gives them the option to provide feedback. When they choose **Give feedback**, the survey is displayed for them to complete and send to Microsoft.

Here’s an example of a survey that anonymous meeting participants might receive.

![Screenshot of a survey that anonymous meeting participants receive to provide feedback about their Teams meeting experience.](media/meeting-surveys-anonymous-participants.png)

## Set whether anonymous meeting participants receive surveys

As an admin, you can control whether anonymous participants receive surveys to provide feedback about their meeting experience.

You turn off or turn on this feature for your organization through a policy that you set by using the [Set-CsTeamsMeetingConfiguration](/en-us/powershell/module/teams/set-csteamsmeetingconfiguration) PowerShell cmdlet.

- To allow anonymous meeting participants to receive surveys, set the `FeedbackSurveyForAnonymousUsers` parameter to `Enabled`. This is the default value.
- If you don’t want anonymous meeting participants to receive surveys, set the `FeedbackSurveyForAnonymousUsers` parameter to `Disabled`.

    Important

    To turn off this feature, the value must be set to `Disabled`. Setting the value to `$disabled` won't work.

For example, to turn off feedback surveys for anonymous participants in Teams meetings (including virtual appointments) and events, run the following command:

```PowerShell
Set-CsTeamsMeetingConfiguration -FeedbackSurveyForAnonymousUsers Disabled
```

Note

You can access and get insights into feedback collected from Net Promoter Score (NPS) survey responses in the Microsoft 365 admin center. To learn more, see [Microsoft product NPS feedback and insights for your organization](/en-us/microsoft-365/admin/manage/manage-feedback-product-insights).