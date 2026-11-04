---
layout: Conceptual
title: Microsoft Teams Monitoring and Alerting - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/alerts/teams-admin-alerts
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: snchatur
ms.date: 2026-05-26T00:00:00.0000000Z
f1.keywords: 
ms.localizationpriority: medium
search.appverid: 
ms.collection:
- M365-collaboration
description: Learn about the Teams alerts and notifications capabilities available in the Microsoft Teams admin center.
ms.custom: 
locale: en-us
document_id: ff254bd5-0d45-79c1-db9e-77768bbf1292
document_version_independent_id: ad980209-879d-5ca1-03b4-178cdc6e3548
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/alerts/teams-admin-alerts.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: alerts/teams-admin-alerts
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/alerts/teams-admin-alerts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 5e4c2e98-b385-4c3c-df6f-d2c3b8f364c7
---

# Microsoft Teams Monitoring and Alerting - Microsoft Teams | Microsoft Learn

Monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center. Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts. For example, you can actively monitor the health of Teams devices such as IP Phones, Teams Rooms on Android, and others if they unexpectedly go offline.

You can use Teams monitoring and alerting to do the following items:

- Automatically manage Teams capabilities
- Be alerted if they show something unexpected.
- Take corrective actions to get things back on-track.

Note

The alert functionality in the Teams admin center is only available in commercial and GCC cloud environments.

## How to manage monitoring and alerting

You must be a Teams service admin to configure alerting rules. See [Use Teams administrator roles to manage Teams](../using-admin-roles) to learn more about Teams admin roles and which reports each admin role can access.

1. Sign in to the Teams admin center.
2. From the left navigation, select **Notifications & alerts**.
3. Choose the rule you want to configure from **Rules**.

## Teams monitoring rules reference

The following is a list of the Teams monitoring rules available in the Teams admin center.

| Rule | Monitoring capability | What's monitored? |
| --- | --- | --- |
| [App submissions](../submit-approve-custom-apps) | Teams Apps | Proactively monitor Teams apps if they're submitted for approval. |
| [Device state rule](device-health-status) | Teams Devices | Proactively monitor Teams devices if they go offline. |
| [Audio quality for in-progress meetings](alerts-in-progress-meeting-audio) | Teams meetings | Specified users' audio quality for in-progress meetings |
| [Video quality for in-progress meetings](alerts-in-progress-meeting-video) | Teams meetings | Specified users' video quality for in-progress meetings |
| [Screen sharing quality for in-progress meetings](alerts-in-progress-meeting-screen-sharing) | Teams meetings | Specified users' app sharing quality for in-progress meetings |