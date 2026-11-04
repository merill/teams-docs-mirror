---
layout: Conceptual
title: Get started with team templates using Microsoft Graph - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/get-started-with-teams-templates
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: Admin
ms.topic: get-started
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: yinchang
ms.date: 2025-03-13T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- tier2
- highpri
description: Learn about the team templates that are available only with Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
- teams-chat-and-channels
locale: en-us
document_id: 24d884cb-c126-b5dc-ff90-1a31aa61bf5b
document_version_independent_id: ed5054d7-d679-7fad-fd5d-9cd393644b9d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/get-started-with-teams-templates.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: get-started-with-teams-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/get-started-with-teams-templates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4efe33d7-8f25-f446-6fb2-d414010ed7d1
---

# Get started with team templates using Microsoft Graph - Microsoft Teams | Microsoft Learn

Note

Team templates don't support creating private channels. Private channel creation isn't included in template definitions.

A team template in Microsoft Teams is a definition of a team's structure designed around a business need or project. With team templates, you can quickly and easily create rich collaboration spaces with predefined settings, channels, and apps. Team templates can help you to deploy consistent teams across your organization.

With Microsoft Graph, you can [create your own templates](/en-us/graph/api/resources/teamtemplate?view=graph-rest-beta&amp;preserve-view=true) or use the prebuilt team templates that are included with Teams to create teams. In this article, you'll learn about the properties that can be defined in templates and the prebuilt templates that are available only with Microsoft Graph.

This article is for you if you're:

- Responsible for planning, deploying, and managing multiple teams across your organization.
- A developer wanting to programmatically create a team with predefined channels and apps.

## Team template capabilities

Most properties in a team are included and supported by templates. But there are a few properties and features that aren't currently supported. Here's a quick summary of what's included and what's not included in team templates.

| Team properties supported by team templates | Team properties not yet supported by team templates |
| --- | --- |
| Template type | Team membership |
| Team name | Team picture |
| Team description | Channel settings |
| Add channels | Pin tabs |
| Show channel by default | Files and content |
| Add apps | Team settings (for example, member, guest, @ mentions) |

## Prebuilt templates

Prebuilt team templates are templates that we created for specific industries. Here are the prebuilt templates available only with Microsoft Graph.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Standard | `https://graph.microsoft.com/v1.0/``teamsTemplates('standard')` | No extra apps and properties |
| Education -Class Team | `https://graph.microsoft.com/v1.0/``teamsTemplates('educationClass')` | Apps:<br>- OneNote Class Notebook (pinned to the **General** tab)<br>- Assignments app (pinned to the **General** tab)<br><br> Team properties:<br>- Team visibility set to **HiddenMembership** (can't be overridden) |
| Education -Staff Team | `https://graph.microsoft.com/v1.0/``teamsTemplates('educationStaff')` | Apps:<br>- OneNote Staff Notebook (pinned to the **General** tab) |
| Education -PLC team | `https://graph.microsoft.com/v1.0/``teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<br>- OneNote PLC Notebook (pinned to the **General** tab) |

Note

For a list of prebuilt templates that you can use in the Teams client and with Microsoft Graph, see [Get started with team templates in the Teams admin center](get-started-with-teams-templates-in-the-admin-console).