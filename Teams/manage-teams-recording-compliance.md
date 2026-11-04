---
layout: Conceptual
title: Manage compliance for Teams recordings of meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-teams-recording-compliance
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
ms.reviewer: ritikag,lisma
ms.date: 2025-04-02T00:00:00.0000000Z
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Learn how to manage compliance for Teams recordings of meetings and events.
locale: en-us
document_id: a0190915-02a4-60ca-7a0d-05a5fa3e2d5e
document_version_independent_id: a0190915-02a4-60ca-7a0d-05a5fa3e2d5e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-teams-recording-compliance.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-teams-recording-compliance
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-teams-recording-compliance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b27b7e8f-b1d0-4729-04b0-c5748f0bd2bc
---

# Manage compliance for Teams recordings of meetings and events - Microsoft Teams | Microsoft Learn

End users can modify the expiration date of any recordings they control, so you shouldn't rely on meeting expiration settings for legal protection.

### Recording expiration settings and Microsoft 365 retention policies in Microsoft Purview

#### File retention vs expiration policies

File retention takes precedence over file deletion. A Teams meeting recording expiration policy can't delete a Teams meeting recording with a Purview retention policy until after the retention period is completed. For example, if you have a Purview retention policy that says a file will be kept for five years and a Teams meeting recording expiration policy set for 60 days, the Teams meeting recording expiration policy permanently deletes the recording after five years.

Once the recording reaches the expiration date, it gets deleted from the user's OneDrive, and is copied to the organization's Preservation Hold library. Your users can't see the recording in OneDrive anymore, but as an admin, only you can find the recording in the Preservation Hold library. To learn more about the Preservation Hold library, see [Learn about retention for SharePoint and OneDrive](/en-us/purview/retention-policies-sharepoint#how-retention-works-for-sharepoint-and-onedrive).

#### Expiration vs deletion policies

If you have a Teams meeting recording expiration policy and Purview deletion policy with different deletion dates, the file is deleted at the earliest of the two dates. For example, if you have a Purview deletion policy that says a file will be deleted after one year and a Teams meeting recording expiration set for 120 days, the Teams meeting recording expiration policy will delete the file after 120 days.

#### Deleting recordings before the expiration date

Users can manually delete their recordings before the expiration date unless there's a Purview retention policy that prevents it. If a user manually deletes a recording that's still in the retention period, the recording is held in the Preservation Hold library. However, the recording shows as deleted to the end user. To find out more, see [Learn about retention for SharePoint and OneDrive](/en-us/microsoft-365/compliance/retention-policies-sharepoint).

### Deletion of recordings

On the expiration date, the recording is moved into the recycle bin and the expiration date field is cleared. If a user recovers a recording from the recycle bin, the meeting expiration setting doesn't delete it again.

Usually, the recording is deleted within a day after the expiration date but in rare instances could take as long as five days. The file owner receives an email notification when the recording expires and is directed to the recycle bin if they want to recover the recording.

### Expiration of migrated recordings from Stream (Classic)

Migrated recordings from Stream (Classic) don't come with an expiration set on them. Instead, we encourage you to only migrate recordings that they want to retain.