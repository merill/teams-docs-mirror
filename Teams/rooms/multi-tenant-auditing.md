---
layout: Conceptual
title: Audit logging in the MTR Pro Portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/multi-tenant-auditing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: kimmatlock
ms.date: 2025-01-27T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Audit logging for the MTR Pro Portal.
f1keywords: 
locale: en-us
document_id: 94a0c6f6-5838-f9ee-3276-570d211d86ed
document_version_independent_id: 94a0c6f6-5838-f9ee-3276-570d211d86ed
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/multi-tenant-auditing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/multi-tenant-auditing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/multi-tenant-auditing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 8f4ac41a-d619-e4e0-5df1-23369bb84f4e
---

# Audit logging in the MTR Pro Portal - Microsoft Teams | Microsoft Learn

Audit logs from the Teams Rooms Pro management portal let you search for audit records for activities performed by users and admins. This feature is enabled by default. Only Teams Rooms Pro Managers have permission to export and then view the logs.

Note

Actions performed in the Teams Rooms Pro management portal are not logged in Microsoft 365 or Office 365 auditing.

## Exporting logs

When you export all results for an audit log search, the raw data from the unified audit log is copied to a comma-separated value (CSV) file that is downloaded to your local computer.

**To download logs**

1. Go to **Settings &gt; General &gt; Audit Logs**.
2. To define the date range for logs of interest, enter the **Start date** and **End date.**

    Note

    Logs are only available for up to 180 days.
3. Select **Download logs.**

    ![Audit log date range](../media/multi-tenant-auditing.png)

    A message displayed at the bottom of the window prompts you to open or save the CSV file.
4. Select **Save** &gt; **Save as**, and save the CSV file to your local computer.
5. It takes a while to download many search results when searching for all activities, or on a broad date range. When the CSV file is finished downloading, a message at the bottom of the window is displayed.

## Detailed properties in the audit log

The following table describes the properties that are included in the CSV.

| Property | Description |
| --- | --- |
| activity.category | The category of the object on which the was action performed. Possible values:<br><br>**User, Assignment, PartnerInvitation, Role** |
| activity.objectName | The name of the object that was modified. |
| activity.operation | The type of operation performed. Possible values are: **Create, Update, Delete** |
| activity.resultStatus | Indicates whether the action (specified in the **activity.operation** property) was successful or not.<br><br>The value is either **Successful** or **Failed**. |
| activity.tenantId | The GUID of the tenant on which the action was performed |
| creationTime | The date and time in Coordinated Universal Time (UTC) in the ISO format when the user performed the activity. |
| user.userId | The user who performed the action that resulted in the record being logged. |
| user.userTenantId | The GUID of the tenant for the user who performed the action |