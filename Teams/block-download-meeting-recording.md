---
layout: Conceptual
title: Block the download of Teams meeting recording and transcript files from SharePoint or OneDrive - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/block-download-meeting-recording
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: samust
ms.author: wlibebe
author: wlibebe
manager: pamgreen
audience: Admin
f1.keywords: NOCSH
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.localizationpriority: medium
ms.date: 2024-09-18T00:00:00.0000000Z
ms.collection:
- Tier1
- Highpri
- Tier1
- m365initiative-meetings
search.appverid:
- SPO160
- MET150
- BSA160
description: Learn how administrators can block the download of Teams meeting recording and transcript files from SharePoint and OneDrive.
locale: en-us
document_id: ec2a2a69-7449-abb7-54bd-09991d5ec3f6
document_version_independent_id: ec2a2a69-7449-abb7-54bd-09991d5ec3f6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/block-download-meeting-recording.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: block-download-meeting-recording
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/block-download-meeting-recording.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
platformId: 3074733d-8323-dab5-e453-c8a7821534fb
---

# Block the download of Teams meeting recording and transcript files from SharePoint or OneDrive - Microsoft Teams | Microsoft Learn

![Information icon](media/info.png)**Some features in this article require [Microsoft Syntex - SharePoint Advanced Management](/en-us/sharepoint/advanced-management)**

As an admin, you can block the download of Teams meeting recording and transcript files from SharePoint or OneDrive. Blocking the download of Teams meeting recording and transcript files allows users to remain productive while addressing the risk of accidental data loss. Users have browser-only access to play the meeting recordings or view transcripts with no ability to download or sync files or access them through apps.

This org-wide policy applies to new meeting recordings and transcripts across your entire organization. When the policy is on, any new Teams meeting recording and transcript files saved in SharePoint and OneDrive are blocked from download. You can exempt people who are members of specified security groups from the policy. Exempting specific security group members allows you to specify governance or compliance specialists who should have download access to meeting recordings and transcripts.

Because this policy affects meeting recordings stored in OneDrive and SharePoint, you must be a SharePoint Administrator to configure it. To learn more about meeting recording in OneDrive and SharePoint, see [Teams meeting recording storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change). To learn more about how your users use transcripts, see [View live transcription in Microsoft Teams meetings](https://support.microsoft.com/office/view-live-transcription-in-microsoft-teams-meetings-dc1a8f23-2e20-4684-885e-2152e06a4a8b).

This policy doesn't apply to manually uploaded meeting recording and transcript files.

Important

This feature doesn't prevent the download of files that were uploaded by Teams prior to turning the policy on. If you would like to prevent download of these files, you can open a support ticket.

## Prerequisites

- You must have a Microsoft Syntex - SharePoint Advanced Management license.

## Turn on the policy for your organization

Open the SharePoint Online Management Shell and connect to SharePoint as a SharePoint Administrator. To learn how, see [Get started with SharePoint Online Management Shell](/en-us/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

Run the following command:

```PowerShell
Set-SPOTenant -BlockDownloadFileTypePolicy <$true/$false(default)>  -BlockDownloadFileTypeIds  TeamsMeetingRecording
```

To block the download of Teams meeting recording files from SharePoint or OneDrive, run this script:

```PowerShell
Set-SPOTenant -BlockDownloadFileTypePolicy $true  -BlockDownloadFileTypeIds TeamsMeetingRecording
```

## Exempt users in specified security groups from the policy

The **`-ExcludedBlockDownloadGroupIds`** parameter exempts users in the specified security groups from this policy so that they can download meeting recording and transcript files.

To allow users in specified security groups to download meeting and recording files, use the following script:

`-ExcludedBlockDownloadGroupIds <comma separated security group IDs>`

## App effect

Blocking the download of Teams meeting recording and transcript files might affect the user experience in some apps, including some Office apps. We recommend that you enable the policy for some users and test the experience with the apps used in your organization.

Note

Apps that run in "app-only" mode, like antivirus apps and search crawlers, are exempted from the policy.

## Need more help?

- [SharePoint Q&A](/en-us/answers/topics/office-sharepoint-online.html)