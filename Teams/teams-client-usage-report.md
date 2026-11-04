---
layout: Conceptual
title: Usage report for the Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-usage-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.topic: article
ms.date: 2025-06-30T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: daro
search.appverid: MET150
f1.keywords:
- NOCSH
description: Information about the Teams client usage report, what it does and how to make the best use of it.
ms.localizationpriority: medium
locale: en-us
document_id: 34056df4-3e24-871d-fc61-105ed28933fe
document_version_independent_id: 34056df4-3e24-871d-fc61-105ed28933fe
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-usage-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-usage-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-usage-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 513454d5-22f5-4216-3550-d21a151bcb47
---

# Usage report for the Teams client - Microsoft Teams | Microsoft Learn

The Microsoft Teams desktop client usage report gives you an overview of the Teams desktop clients in use within your organization. It highlights platform, version, and user type to help you better understand the current state of your user’s desktop clients.

## How to get to the Microsoft Teams desktop client usage report

1. In the Teams admin center, go to the **Analytics & Reports** &gt; **Usage Reports** page.
2. From the Usage Reports page, choose the **Teams desktop client usage report**, choose a date range selection, and select **Run report**.

## Interpret the Microsoft Teams client usage report

The graph in the Teams desktop client usage report shows the usage of Teams as a percentage within your tenant. These numbers are directly related, so if one number increases the other decreases. Take note of the important characteristics of this data:

- This data represents Windows or Mac Teams desktop clients and not web or mobile clients, but some Room devices may also show up. Filter out these devices with the **Export** functionality of the report, if needed. We're investigating ways to filter out these devices in a future version.
- This data may also contain Guest users if you allow, and use, Guest Access within your tenant. These users display with #EXT#, which you can use the **Export** functionality of the report to filter them out. We're investigating ways to filter out these users in a future version.
- This data is dependent on a user’s Teams desktop client being actively used. When a user isn't active on their desktop client or their data can't be reported in for any reason, their data isn't reported for that period. There's no data reported if no data was available. This missing information can result in fluctuations in the data, for example during weekends or when users go on vacation.
- A user's data comes from their most recent usage when the snapshot is taken for each platform, Windows or Mac. If a user has multiple machines they use regularly on any single platform, whichever machine they used last is represented for that day. For most people who have multiple machines, they usually have a primary device that gets the most use.

The data in the table columns below the graph allow a more granular look at individual users and the state of their Teams desktop client. You can export this data using the Export to Excel function in the top right corner. Columns can be shown or hidden using the Edit columns function, also in the top right corner.

| Column | Description |
| --- | --- |
| Username | UPN of the user. |
| Display name | Display name of the user. |
| Classic or new (Windows) | Whether or not a Windows user is using the classic Teams or new Teams application. |
| App version (Windows) | The version number of the Windows Teams application for the user. |
| Classic or new (Mac) | Whether or not a Mac user is using the classic Teams or new Teams application. |
| App version (Mac) | The version number of the Mac Teams application for the user. |
| User type | What deployment ring a user is assigned to. Differences between users in this column can explain why they may have different versions of the Teams application. The values that may display are:  - **TAP Admin**: Administrators who participate in the Microsoft Teams TAP program. Sometimes referred to as R1.5.  - **Developer Preview**: Developers who opt into early preview of developer focused functionality for Teams app development. Sometimes referred to as R1.6.  - **TAP**: Users who participate in the Microsoft Teams TAP program. Sometimes referred to as R3.  - **Public Preview**: Users who participate in the [Public Preview](public-preview-doc-updates) program. Sometimes referred to as R3.6.  - **Production**: Regular users who don't have access to early preview functionality. Sometimes referred to as R4.  - **GCC Production**: Regular GCC users who don't have access to early preview functionality. |

## Example Scenario for the Teams desktop client usage report

Using the export capability of the report, you can identify any Teams desktop clients in your organization stuck on an older version and that aren't automatically updating as they should. Becoming stuck and not automatically updating is often a result of some sort of network or machine issue or a configuration change. Identifying these users with this report allows you to proactively identify and engage with these users to investigate and resolve the issue.