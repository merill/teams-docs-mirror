---
layout: Conceptual
title: Report suspicious Teams Calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/end-user-reporting-teams-calling
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how users can report suspicious or scam calls in Microsoft Teams
author: smahadevan
ms.author: smahadevan
manager: charup
ms.service: msteams
ms.subservice: msteams-admin
ms.topic: how-to
ms.date: 2026-03-04T00:00:00.0000000Z
ms.custom:
- Security
locale: en-us
document_id: 6c12d870-94a5-bedc-574b-011c604bfba3
document_version_independent_id: 6c12d870-94a5-bedc-574b-011c604bfba3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/end-user-reporting-teams-calling.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: end-user-reporting-teams-calling
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/end-user-reporting-teams-calling.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b77befa0-0c28-78f8-35b7-388efbe6998f
---

# Report suspicious Teams Calls - Microsoft Teams | Microsoft Learn

In organizations with Microsoft Defender for Office 365 Plan 2 or Microsoft Defender XDR, admins can decide whether users can report malicious or suspicious calls in Microsoft Teams. Security admins can also get visibility into the Teams calls that users are reporting.

Users can report calls in Teams for security concern and calls that are not a security concern.

## User experience in Teams – Report Security Concern

Users who see a concerning call in Teams can report it as a security risk. To report a call:

1. Go to call history or post call experience in Teams and select **… &gt; Report call**.
2. **Security concern.** is already selected as the reason. Enter additional explanation as required.
3. Review the selections and select **Report**.

Users can report suspected scam calls directly from the call details screen.

## User reporting settings for Teams Calling – Security Concern

'Report call' reporting of calls in Teams is made of two separate settings:

- **In the Teams admin center**: 'On' by default and controls whether users are able to report calls from Teams. When this setting is turned off, users can't report calls within Teams, so the corresponding setting in the Microsoft Defender portal is irrelevant.
- **In the Microsoft Defender portal**: 'On' by default for new tenants. Existing tenants need to enable it. If user reporting of calls is turned on in the Teams admin center, it also needs to be turned on in the Defender portal for user reported calls to show up correctly.

## Turn off or turn on user reporting for calling in Teams admin center

1. Sign in to the Teams Admin Center at [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com/).
2. In the left navigation of the Teams Admin Center, go to **Voice &gt; Calling policies**.
3. Select a policy.
4. Turn on the setting: **Report call**.
5. Select **Save** to apply the changes.

## User experience in Teams – Report Not a Security Concern

Users can report calls in Teams that are incorrectly flagged as a security risk.

To report a call as not a security concern:

1. In the Teams call history, locate the call that incorrectly flagged as "Scam Suspected".
2. Hover over the call without selecting it.
3. Select **...** &gt; **Report as not a security concern**.
4. In the report dialog that opens, provide an explanation.
5. Select **Report** to submit your feedback.