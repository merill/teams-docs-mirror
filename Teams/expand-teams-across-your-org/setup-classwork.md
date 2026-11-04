---
layout: Conceptual
title: Set up Classwork in Teams for Education - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/expand-teams-across-your-org/setup-classwork
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: teams-education
audience: admin
ms.collection:
- M365-collaboration
- tier3
search.appverid: MET150
ms.date: 2026-10-21T00:00:00.0000000Z
f1.keywords: 
description: The Classwork feature in Teams for Education allows educators to create and organize class resources.
ms.localizationpriority: medium
locale: en-us
document_id: 7e5df196-c530-3b7c-b014-225a3c5bf39a
document_version_independent_id: 7e5df196-c530-3b7c-b014-225a3c5bf39a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/expand-teams-across-your-org/setup-classwork.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: expand-teams-across-your-org/setup-classwork
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/expand-teams-across-your-org/setup-classwork.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: cbf9b1d4-cd62-8f74-3db7-a11a4b845a6a
---

# Set up Classwork in Teams for Education - Microsoft Teams | Microsoft Learn

The Classwork feature in Teams for Education allows educators to create and organize class resources, including Assignments, OneNote Class Notebook pages, web links, files, and Teams channels. With Classwork, educators can curate a view of content and resources that will help students navigate a class and see everything in one place.

### Permission support

For details about delegated and application permissions, see [Permission types](/en-us/graph/permissions-overview). To learn more about these permissions, see the [permissions reference](/en-us/graph/permissions-reference).

#### EduCurricula.Read

| Category | Application | Delegated |
| --- | --- | --- |
| Identifier | - | 484859e8-b9e2-4e92-b910-84db35dadd29 |
| DisplayText | - | Read the user's class modules and resources |
| Description | - | Allows the app to read the user's modules and resources on behalf of the signed-in user. |
| AdminConsentRequired | - | Yes |

#### EduCurricula.Read.All

| Category | Application | Delegated |
| --- | --- | --- |
| Identifier | 6cdb464c-3a03-40f8-900b-4cb7ea1da9c0 | - |
| DisplayText | Read all class modules and resources | - |
| Description | Allows the app to read all modules and resources, without a signed-in user. | - |
| AdminConsentRequired | Yes | - |

#### EduCurricula.ReadWrite

| Category | Application | Delegated |
| --- | --- | --- |
| Identifier | - | 4793c53b-df34-44fd-8d26-d15c517732f5 |
| DisplayText | - | Read and write the user's class modules and resources |
| Description | - | Allows the app to read and write user's modules and resources on behalf of the signed-in user. |
| AdminConsentRequired | - | Yes |

#### EduCurricula.ReadWrite.All

| Category | Application | Delegated |
| --- | --- | --- |
| Identifier | 6a0c2318-d59d-4c7d-bf2e-5f3902dc2593 | - |
| DisplayText | Read and write all class modules and resources | - |
| Description | Allows the app to read and write all modules and resources, without a signed-in user. | - |
| AdminConsentRequired | Yes | - |

### Remove Classwork for a specific user or your entire tenant

To remove Classwork for an individual user, go to the **Teams Admin Center** and navigate to **Teams apps** &gt; **Permission policies** to create a new app permission policy definition. When creating the new policy definition, set the **Microsoft apps** policy to **Block specific apps and allow all others** and add **Classwork** to the list of blocked applications. Once your new policy definition is saved, assign it to the appropriate users.

To remove Classwork for your entire tenant, go to **Teams Admin Center**, navigate to **Teams apps** &gt; **Manage apps**, and search for and select **Classwork** from the application list. Change the status setting within the application's settings page to **Blocked**.