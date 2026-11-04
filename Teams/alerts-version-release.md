---
layout: Conceptual
title: Alerts for new Teams desktop client releases - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/alerts-version-release
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: This feature gives Teams admins the ability to receive an alert when a new Teams desktop client version is rolling out in their tenant.
ms.date: 2026-04-28T00:00:00.0000000Z
author: dascottmsft
ms.author: danielscott
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
locale: en-us
document_id: 9027b44c-ff6d-4dc5-f7d5-3ae500b680b1
document_version_independent_id: 9027b44c-ff6d-4dc5-f7d5-3ae500b680b1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/alerts-version-release.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: alerts-version-release
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/alerts-version-release.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d7cd2965-1d2e-24ae-050b-18c5d6cfe1f2
---

# Alerts for new Teams desktop client releases - Microsoft Teams | Microsoft Learn

Adopting the latest updates is critical to keeping the Teams desktop client running in a healthy state. This feature allows admins to stay informed on when a new desktop client version is released, and helps them identify and mitigate any issues that impact the version rollout.

When this alert is active, notifications are sent to admins when the desktop client version begins to release in their tenant. Admins can choose to receive these alerts in a Teams channel, or integrate with other tools using a provided webhook URL.

### Set up alerts for Teams client version rollout

1. In the left navigation in Microsoft Teams admin center, select **Notifications and alerts** then **Rules.**
2. From the rules page, select the Teams client update rollout alert rule.
3. Select the preferred options as described in the following table, and then select **Save.**

    | Field | Description |
    | --- | --- |
    | **Conditions** | Choose the **Ring** to specify which ring the alert monitors for a new client version release.Choose the **Platform** to specify which platforms you want to monitor for a new client version release. |
    | **Scope** | This rule is evaluated daily, and an alert is sent if the selected conditions are met. |
    | **Actions** | Choose if you want to send alerts to a specific Teams channel or to a webhook URL. |
    | **Status** | Choose if the rule is active and alerts should be sent. |