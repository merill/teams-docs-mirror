---
layout: Conceptual
title: Admin settings for file drag-drop to third-party storage - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/admin-settings-for-file-drag-drop-to-third-party-storage
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
ms.reviewer: shkarri,sasood
ms.date: 2024-04-18T00:00:00.0000000Z
manager: odocspr
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: 
description: Learn how to change the default storage backend of Teams (for OneDrive and SharePoint).
ms.localizationpriority: medium
f1.keywords: 
ms.collection: 
locale: en-us
document_id: 9564b8e4-0997-73a5-9ce5-f2aa397f696b
document_version_independent_id: 9564b8e4-0997-73a5-9ce5-f2aa397f696b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/admin-settings-for-file-drag-drop-to-third-party-storage.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: admin-settings-for-file-drag-drop-to-third-party-storage
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/admin-settings-for-file-drag-drop-to-third-party-storage.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0977565b-e2cf-be23-c754-fb28db87e9d5
---

# Admin settings for file drag-drop to third-party storage - Microsoft Teams | Microsoft Learn

To help Teams become an open platform, Teams admins can change the default storage backend of Teams (for OneDrive and SharePoint) to a third-party storage-provider app of their choice. This change gives you:

- **For Teams admins** The ability to change the default storage app for drag-drop when uploading files on the Teams desktop.
- **For Teams app developers (third party)** The ability to use this capability for Teams apps using the Teams SDK.

This functionality works only for Teams apps built to support this configurability. This article explains policy names, syntax, and how tenants can change the default drag-drop storage destination to a third-party storage provider.

## Check the status of your tenant

To view the current status of your tenant's Teams Files policy, use the *Get-CsTeamsFilesPolicy* Cmdlet:

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

## Configure the third-party app

Admins can use the following PowerShell command to set a third-party cloud storage to handle drag-drop files.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -DefaultFileUploadAppId  "<appId>"
```

Admins can use the following PowerShell command to revert this setting.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -DefaultFileUploadAppId  ""
```

## Remove the policy for your users

To remove the Teams Files policy for your users, use the *Remove-CsTeamsFilesPolicy* Cmdlet:

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

### User side-error conditions

A user side error could occur due to the following reasons:

- The app is configured but not installed
- The configured app doesn't support drag-drop

### Remove the policy for the complete list of users

To remove the policy for the complete list of users, use the *Remove-CsTeamsFilesPolicy* Cmdlet:

```powershell
Remove-CsTeamsFilesPolicy
```

### Out of scope

Teams Mobile support for the *DefaultFileUploadAppId* policy isn't applicable. Also note that image or media copy and paste is today treated as part of the Teams message payload and not as a cloud file. This policy doesn't impact the image or media copy and paste.

## Documentation for admins

Admins should refer to the app description or third-party app documentation for information about App ID for this policy.

- For new app support, contact your desired third-party storage provider for the compatible app.

## Documentation for developers (third-party storage apps)

For the Teams app developers to implement third-party cloud storage app for the drag-dropped files, see [third-party cloud storage app](/en-us/microsoftteams/platform/concepts/device-capabilities/third-party-storage-capability).

- For more API information, see [thirdPartyCloudStorage module](/en-us/javascript/api/@microsoft/teams-js/thirdpartycloudstorage).
- For more Teams SDK information, see [@microsoft/teams-js package](/en-us/javascript/api/@microsoft/teams-js).