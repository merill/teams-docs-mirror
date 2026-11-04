---
layout: Conceptual
title: Set up Microsoft Teams meeting add-on for Google Workspace - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/google-workspace-addon-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
ms.reviewer: jason.hochstadt
ms.date: 2024-10-31T00:00:00.0000000Z
manager: pamgreen
ms.topic: install-set-up-deploy
audience: admin
ms.service: msteams
ms.subservice: meetings
search.appverid: MET150
description: Learn how to Set up Microsoft Teams meeting add-on for Google Workspace.
ms.localizationpriority: medium
ms.custom:
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
locale: en-us
document_id: 00c3be94-d640-a20c-ac06-2653f443b74e
document_version_independent_id: 4760af98-c4e9-ab6a-6745-1381ffc068cc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/google-workspace-addon-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: google-workspace-addon-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/google-workspace-addon-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7275b6f0-2884-0896-63a1-20b4bd3d8928
---

# Set up Microsoft Teams meeting add-on for Google Workspace - Microsoft Teams | Microsoft Learn

The Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace. These get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.

The Microsoft Teams meeting add-on for Google Workspace is on by default. To learn about how your users use the Microsoft Teams meeting add-on for Google Workspace, see [Install the Microsoft Teams meeting add-on for Google Workspace](https://support.microsoft.com/office/install-the-microsoft-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60).

## Turn the Microsoft Teams meeting add-on for Google Workspace on or off in the Azure portal

As an admin, you can turn the Microsoft Teams meeting add-on for Google Workspace on or off using the Azure portal.

1. Sign in to the Azure portal.
2. Select **Enterprise applications** &gt; **All applications**.
3. Search for **Microsoft Teams meeting add-on for Google Workspace**.

    ![Azure portal showing all applications.](media/aad-add-google-workspace.png)
4. Select **Yes**.

    ![Azure portal showing the google workspace properties.](media/google-workspace-properties.png)
5. (Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.

## Turn the Microsoft Teams meeting add-on for Google Workspace off using PowerShell

```powershell
Connect-MgGraph -Scopes "Application.ReadWrite.All"

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'
```

## Check if a service principal already exists for the app

```powershell
$ServicePrincipalUpdate =@{
  "accountEnabled" = "false"
}

$servicePrincipal = Get-MgServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Update-MgServicePrincipal -ServicePrincipalId $servicePrincipal.Id -BodyParameter $ServicePrincipalUpdate
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    $servicePrincipal = New-MgServicePrincipal -AppId $appId -DisplayName $displayName
    Update-MgServicePrincipal -ServicePrincipalId $servicePrincipal.Id -BodyParameter $ServicePrincipalUpdate
    Write-Host "Created and disabled the Service Principal \n"
}
```

For more information, see [Create a service principal with Microsoft Graph PowerShell](/en-us/powershell/module/microsoft.graph.applications/new-mgserviceprincipal).

## Allow add-on authentication within your Google Workspace environment

If you are unable to sign-in to the Microsoft Teams meeting add-on for Google Workspace, check that your Google Workspace security settings allow access to the add-on. Check that the allow list for URLs accessed from Google Apps Script includes the URL for add-on authentication: `https://login.microsoftonline.com/*`

## Delete the Microsoft Teams meeting add-on for Google Workspace

See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.

## Create the Microsoft Teams meeting add-on for Google Workspace using PowerShell

In case the Microsoft Teams meeting add-on isn't present in your tenant, you can create it using PowerShell:

```powershell
Connect-MgGraph -Scopes "Application.ReadWrite.All"

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-MgServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-MgServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```