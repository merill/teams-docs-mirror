---
layout: Conceptual
title: Turn off Teams Native File Upload policy - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/turn-off-teams-native-file-upload-policy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: 
ms.date: 2024-11-12T00:00:00.0000000Z
search.appverid: 
description: Learn how to create, set, assign, and adjust the Teams Files Policy using PowerShell.
audience: admin
ms.localizationpriority: medium
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
locale: en-us
document_id: 50bf1be7-48ca-f814-687f-2ee967bfd9d9
document_version_independent_id: 50bf1be7-48ca-f814-687f-2ee967bfd9d9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/turn-off-teams-native-file-upload-policy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: turn-off-teams-native-file-upload-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/turn-off-teams-native-file-upload-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0d72f839-ee54-521f-40b5-046f8d9392de
---

# Turn off Teams Native File Upload policy - Microsoft Teams | Microsoft Learn

Microsoft Teams uses OneDrive and SharePoint to store and share content, but some organizations and users might prefer to use third-party storage providers.

If your organization chooses a third party for content storage, you need to turn off the `NativeFileEntryPoints` parameter in the Teams Files policy. This parameter is enabled by default, which shows the option to upload content from OneDrive or SharePoint to Teams chats or channels.

This article helps you create, set, assign, and remove the `NativeFileEntryPoints` parameter using PowerShell.

Note

When the Teams Files policy is turned off, users don't see access points for OneDrive and SharePoint in Teams. However, the creation of new teams and channels continue to trigger the generation of matching SharePoint libraries. The **OneDrive app** in the left navigation pane in Teams isn't affected by the Files policy being turned off.

## Prepare to update the Teams Files policy

### Set up Microsoft PowerShell

Currently, this policy can't be changed in the Teams admin center. Your organization's tenant administrator has to make the changes using the PowerShell cmdlets detailed later in this article.

- To learn how to install the PowerShell Teams module using PowerShell Gallery, see [Install Microsoft Teams PowerShell Module](teams-powershell-install).
- To install or download the Teams PowerShell module, see [PowerShell Gallery for Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).
- For more information on how to set up PowerShell for Teams management, see [Manage Teams with Microsoft Teams PowerShell](teams-powershell-managing-teams).

### Allow third-party apps in Teams admin center

This step isn't required to change the Teams Files policy, but it's required when you're ready to integrate your third-party storage provider in your users' Teams experience.

Your tenant administrator needs to enable the *Allow third-party apps* policy in the Teams admin center.

To learn how to allow third-party or custom apps, see *Manage org-wide apps settings* in [Manage your apps in the Microsoft Teams admin center](/en-us/microsoftteams/manage-apps#manage-org-wide-app-settings).

## Turn off `NativeFileEntryPoints` for your entire tenant

Setting the `-Identity` parameter to `Global` applies the policy settings to all users in your organization.

### Sample PowerShell policy cmdlet for entire tenant

The following sample PowerShell command sets the `NativeFileEntryPoints` parameter to `Disabled` for your entire tenant:

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### Check the status of your tenant

To view the current status of your tenant's Teams Files policy, use the `Get-CsTeamsFilesPolicy` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### Turn on or turn off native file upload point

To turn on or turn off the native file upload point for your entire tenant, set the `NativeFileEntryPoints` parameter to either `Enabled` or `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### Remove the policy for your users

To remove the Teams Files policy for your users, use the `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## Turn off NativeFileEntryPoints for specific users

You can also update the Teams Files policy for specific users by creating a new Teams Files policy `-Identity` string and assigning the newly created policy to users.

### Sample PowerShell policy cmdlet for specific users

This sample PowerShell command creates a new `CsTeamsFilesPolicy` with the `-Identity` named as `UserPolicy` and the `NativeFileEntryPoints` parameter set to `Disabled`.

When a user is assigned the `CsTeamsFilesPolicy` with `-Identity UserPolicy`, their native file entry points are turned off.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### Assign a policy to user

Once you create the new policy, you can assign that policy to users using the `Grant-CsTeamsFilesPolicy` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### Update the policy

If you need to change the setting of the new Teams Files Policy `UserPolicy`, use the `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### Remove the policy for the complete list of users

To remove the policy from all users assigned to the Teams Files policy `UserPolicy`, use the `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```

Note

Once you've made changes to the policy, allow up to 12 hours for the changes to show in users' Teams clients.