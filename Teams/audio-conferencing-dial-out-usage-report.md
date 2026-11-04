---
layout: Conceptual
title: Audio Conferencing dial-out usage report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/audio-conferencing-dial-out-usage-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: oscarr
ms.date: 2024-10-24T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- m365initiative-meetings
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Learn which countries/regions have dial-in conferencing numbers, and how they're automatically assigned.
locale: en-us
document_id: dd11fb28-8f91-2734-c885-a65801b7eef1
document_version_independent_id: dd11fb28-8f91-2734-c885-a65801b7eef1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/audio-conferencing-dial-out-usage-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: audio-conferencing-dial-out-usage-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/audio-conferencing-dial-out-usage-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 813cbc73-d846-06f5-2ba3-0f1e72b95386
---

# Audio Conferencing dial-out usage report - Microsoft Teams | Microsoft Learn

The Audio Conferencing dial-out usage report in the Teams admin center provides an overview of usage and expenses for the audio conferencing dial-out service. As an admin, this report allows you to analyze user-level data, including communication credits spent and dial-out minutes used. This insight helps you accurately estimate future communication credit requirements.

## View the Audio Conferencing dial-out usage report

1. In the Microsoft Teams admin center, expand **Analytics & reports** &gt; **Usage reports**. In the **View reports** tab, for the **Report** dropdown, select the **Audio Conferencing dial-out usage report**.
2. In the **Date range** dropdown, you can select a predefined range of 7 or 28 days, or set a custom range.
3. In the **Country or region provisioned** dropdown, select a preferred country/region, or select all, and then select **Run report**.

## Report details

The Audio Conferencing dial-out usage report has three main tabs that display information in a chart format based on the range selected in the dropdowns above it:

- The **Cost** tab shows the communication credits spent over the selected period and the table provides user level detail.
- The **Call duration** tab shows the total dial-out minutes over the selected period and the table provides user level detail.
- The **Dial-out calls** tab shows the total number of dial-out calls over the selected period and the table provides user level detail.

Each report has a date for when it was generated. The reports usually reflect a 24 to 48 hour latency from the activity time.

Note

All dial-out minutes/calls/credit spent will be counted under the meeting organizer. It's not necessarily the same person who dialed out.

### Cost tab

The top of this tab section has a chart that displays a line showing cost information over the date range and for the country/region or countries/regions selected.

There's a **Cost** section underneath the chart showing a price, which is the total cost per minutes of calls within the select time range.

### Call duration tab

The top of this tab section has a chart that displays a line that showing call duration over the date range and for the country/region or countries/regions selected.

There's a **Call duration** section underneath the chart showing the total minutes of calls used within the select time range.

### Dial-out calls

The top of this tab section has a chart that displays a line showing dial-out calls over the date range and for the country/region or countries/regions selected.

There's a **Dial-out calls** section underneath the chart showing the total number of dial-out calls within the select time range.

## Using the report

The bottom of the page has a table, which shows user level breakdowns with the following headings:

- Meeting organizer
- Username
- Total minutes
- Credit spent
- Currency
- Country or region provisioned

If you need to search for usage for a specific user, there's a search bar on the right above the report. The meeting organizer names are all selectable hyperlinks that take you to a more detailed usage report for the user. This user view has the same three tabs as the main report, however the chart at the top of the page shows details for that specific user.

You can export any report shown in this table to a CSV file for offline analysis. Select **Export to Excel**, and then on the **Downloads** tab, select **Download** to download the report when it's ready.