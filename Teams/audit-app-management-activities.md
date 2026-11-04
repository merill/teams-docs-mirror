---
layout: Conceptual
title: Search the audit logs of app management events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/audit-app-management-activities
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal0201
ms.author: vikasalmal
manager: prkosh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 2026-06-01T00:00:00.0000000Z
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: 
description: Learn how to audit Teams app activities of users and administrators in your organization.
ms.localizationpriority: medium
locale: en-us
document_id: 2bc431d8-32c4-957d-9b3b-84bee4778ca5
document_version_independent_id: 2bc431d8-32c4-957d-9b3b-84bee4778ca5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/audit-app-management-activities.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: audit-app-management-activities
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/audit-app-management-activities.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 2e3b0160-8f3a-3f41-452f-970df9ab6e32
---

# Search the audit logs of app management events - Microsoft Teams | Microsoft Learn

Microsoft Purview Audit (Standard) in Microsoft 365 lets you log and search the audited activities performed in the various Microsoft 365 services by users and administrators.

Before you can search the audit records, ensure that you complete the following prerequisites:

- [Obtain organization's subscription and user licensing](/en-us/purview/audit-standard-setup#step-1-verify-organization-subscription-and-user-licensing).
- [Turn on auditing in the Microsoft Purview](/en-us/purview/audit-log-enable-disable) portal.
- [Assign permissions to search the audit log](/en-us/purview/audit-standard-setup#step-2-assign-permissions-to-search-the-audit-log).

## Search the audit logs for app events in Teams

The audit logs for app events in Teams help you investigate specific actions related to app management by admins. While you can search the logs for a wide-range of actions, the following table lists some such actions that are logged.

| Teams app action | Activity name in the Portal | Description |
| --- | --- | --- |
| **Installed app** | `AppInstalled` | An app is installed or added to a Teams client. |
| **Upgraded app** | `AppUpgraded` | An app is upgraded to its latest version in the catalog. |
| **Uninstalled app** | `AppUninstalled` | An app is uninstalled or removed from a Teams client. |
| **Published app** | `AppPublishedToCatalog` | An app is added to the catalog. |
| **Updated app** | `AppUpdatedInCatalog` | An app is updated in the catalog. |
| **Deleted app** | `AppDeletedFromCatalog` | An app is deleted from the catalog. |
| **Deleted all organization apps** | `DeletedAllOrganizationApps` | Deleted all organization apps from the catalog. |

For a complete list of Teams activities that are audited, see [Teams activities](audit-log-events#teams-activities) and [Shifts in Teams activities](audit-log-events#shifts-in-teams-activities).

Note

App events from private channels are also logged as those events are accomplished in Teams and in the standard channels.

To search the audit logs of Teams app activities, follow these steps:

1. Sign in to Microsoft Purview and go to **Solutions** &gt; **[Audit](https://compliance.microsoft.com/auditlogsearch)**.
2. On the **Audit** page, update the following fields as required:

    - **Date and time range**: Select the start and end dates of the time period for which you want to check the audit logs.
    - **Activities**: Enter Microsoft Teams activities. From the list, select one or more app activities. To quickly find the Teams activities, you can search for the word `Teams activities` in the **Activities** search field.
    - **File, folder, or site**: Enter file name or a URL or a part of it.
    - **Users**: Add the users whose audit log you want to search.
3. Select **Search**.

    [![Screenshot that shows how to search for Teams activities in the Microsoft Purview to audit for Teams events.](media/compliance-search-teams-activities-trimmed.png)](media/compliance-search-teams-activities.png#lightbox)

You can export the searched audit records as a CSV file. For more information, see [Export, configure, and view audit logs](/en-us/purview/audit-log-export-records).

Note

When one of the above activities is performed by a user or admin, Teams generates and stores an audit record. In Audit (Standard), records are retained for 90 days, which means you can search for activities that occurred within the past three months.

Tip

You can commission the custom development of a per-user report to know if a user has blocked or muted a bot. For more information, see [Understand who blocked, muted, or uninstalled a bot](/en-us/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages#understand-who-blocked-muted-or-uninstalled-a-bot).