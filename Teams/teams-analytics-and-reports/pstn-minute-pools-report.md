---
layout: Conceptual
title: Microsoft Teams PSTN minute pools report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/pstn-minute-pools-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
ms.date: 2026-03-30T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: How to use the Teams PSTN minute pools report in the Microsoft Teams admin center to view the minutes consumed within your organization during the current month.
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
locale: en-us
document_id: 8107d4a3-a55e-4891-ee72-27f79f647a1e
document_version_independent_id: b71f24c6-b54d-8a0f-ea0e-8839ff5481a4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/pstn-minute-pools-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/pstn-minute-pools-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/pstn-minute-pools-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 18d603d7-5e33-8f5c-2238-d135a95d6bb5
---

# Microsoft Teams PSTN minute pools report - Microsoft Teams | Microsoft Learn

The Teams PSTN minute pools report in the Microsoft Teams admin center gives you an overview of audio conferencing and calling activity in your organization by showing you the number of minutes consumed during the current month. You can see a breakdown of activity including the license used for calls, total minutes available, used minutes, and license usage by location.

## View the PSTN minute pools report

In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **PSTN minute pools**, and then select **Run report**.

![Screenshot of the Teams PSTN minute pools report in the Teams admin center.](../media/teams-reports-pstn-minute-pools-with-callouts.png)

## Interpret the report

| Callout | Description |
| --- | --- |
| **1** | Each report has a date for when it was generated. The reports usually reflect a 24 to 48 hour latency from time of activity. |
| **2** | Select a capability (license) to view activity for that capability. |
| **3** | The X axis is country or region. The Y axis is number of minutes. Hover over a bar on the chart to see the activity for that usage location. |
| **4** | You can filter what you see on the chart by selecting an item in the legend. For example, select **Unused**, **Domestic used**, **No data**, or **International used** to see only the info related to each one. |
| **5** | The table gives you a breakdown of minute pools by capability and usage location. <br>- **Country or region** is the usage location.<br>- **Capability description**is the description of the license used for the call. The capability descriptions you might see in this report include:<br>    - Domestic and international calling plan (1,200 domestic minutes)<br>    - Domestic and international calling plan (3,000 domestic minutes)<br>    - Domestic and international calling plan (600 international minutes)<br>- **Total minutes** is the total number of minutes available for the month.<br>- **Minutes used** is the number of minutes used each month<br>- **Minutes available** is the number of minutes remaining for the month.<br>- **Capability**is the license used for the call. The licenses you might see include:<br>    - **MCOPSTN1** - Domestic Calling Plan (3,000 min US / 1,200 min EU plans)<br>    - **MCOPSTN2** - International Calling Plan<br>    - **MCOPSTN5** - Domestic Calling Plan (120 min calling plan)<br>    - **MCOPSTN6** - Domestic Calling Plan (240 min calling plan)<br>    - **MCOMEETADD** - Audio Conferencing<br><br> To see the information that you want in the table, make sure to add the columns to the table. |
| **6** | Select **Edit columns** to add or remove columns in the table. |
| **7** | Select **Full screen** to view the report in full screen mode. |