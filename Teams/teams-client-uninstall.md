---
layout: Conceptual
title: Uninstall the Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-uninstall
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.topic: article
ms.date: 2025-01-31T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- m365initiative-deployteams
ms.reviewer: 
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about how to uninstall the Microsoft Teams client.
ms.localizationpriority: medium
locale: en-us
document_id: 643ecd92-15ef-25bc-ba64-f811ef9f9713
document_version_independent_id: 643ecd92-15ef-25bc-ba64-f811ef9f9713
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-uninstall.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-uninstall
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-uninstall.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 14272d61-9a0f-3cf5-d2f8-2145791ab12c
---

# Uninstall the Teams client - Microsoft Teams | Microsoft Learn

## Remove new Teams for all users

To remove Teams from all users' computers, use the following PowerShell command:

```powershell

Remove-AppxPackage 
```

PowerShell cmdlet to remove new Teams from all users on all computers:

```powershell
Get-AppxPackage *MSTeams* -AllUsers |Remove-AppxPackage -AllUsers
```

PowerShell cmdlet for an individual user without administrator privilege:

```powershell
Get-AppxPackage *MSTeams*|Remove-AppxPackage
```

Command to uninstall teams machine-wide: teamsbootstrapper.exe -x -m