---
layout: Conceptual
title: Use retail team templates - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/get-started-with-retail-teams-templates
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
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: yinchang
ms.date: 2019-02-01T00:00:00.0000000Z
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to manage and use the retail team templates in the Teams admin center and with Microsoft Graph to quickly and easily create teams for your retail organization.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
locale: en-us
document_id: bc242a3d-356e-de35-6b05-76b6d8ed19cd
document_version_independent_id: 63e4b610-7b5c-c157-7bb7-97c19756aee7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/get-started-with-retail-teams-templates.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: get-started-with-retail-teams-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/get-started-with-retail-teams-templates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: dc9f43d8-7409-5d4c-9089-e85d8ae87438
---

# Use retail team templates - Microsoft Teams | Microsoft Learn

## Overview

Team templates in Microsoft Teams allow you to quickly and easily create teams by providing a predefined team structure of settings, channels, and pre-installed apps.

For retailers, team templates can be especially powerful, as they help you to quickly deploy consistent teams across your organization. Templates also help staff to get oriented with how to effectively use Teams.

Teams includes templates designed specifically for retailer needs. Use these pre-built templates to quickly create teams for staff to communicate and collaborate. In this article, we introduce you to each of these templates and recommend how to use them.

How you manage and work with team templates depends on whether you're an admin or developer.

| If you're: | Then, you: |
| --- | --- |
| An admin or IT pro | Manage team templates in the Teams admin center. View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| A developer | Use Microsoft Graph to create teams from team templates. |

## Manage team templates in the Teams admin center

As an admin, you can manage team templates in the Microsoft Teams admin center. Here, you can view details about each template. You can also [create and assign templates policies](templates-policies) to your staff to control which templates they see in Teams for [creating teams](https://support.microsoft.com/teams).

To learn more about team templates in general, see [Get started with team templates in the Teams admin center](get-started-with-teams-templates-in-the-admin-console).

We currently offer the following pre-built retail team templates. To view them, in the left navigation of the Teams admin center, go to **Teams** &gt; **Team templates**.

Note

An asterisk (\*) indicates that the template is a *Microsoft 365 connected template*. When users create a team using the template, the connected SharePoint template is applied to the site and the team. SharePoint components such as pages, lists, and Power Platform integrations are automatically added and pinned as tabs to the General channel in the team. Users can edit these pages and lists right from within Teams.

To learn more about SharePoint templates, see [Apply and customize SharePoint site templates](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### Manage a Store\*

Bring your retail employees together in one central experience to manage tasks, share documents, and resolve customer issues. Integrate additional applications to streamline shift start and end processes.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Manage a Store | `retailStore` | Channels: <br>- General<br>- Shift Handoff<br>- Store Readiness<br>- Learning<br><br> Apps: <br>- Approvals<br>- Inspection<br>- Lists<br>    - Inventory list<br>- SharePoint Pages<br>    - Our store<br>- Shifts<br>- Planner<br>- Wiki |

### Retail for Managers\*

Create a team for a set of managers to collaborate across stores or regions. For example, if your organization has regions, you might create a team for the California region and include all the store managers in that region, along with the regional manager for that region.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Retail for Managers | `retailManagerCollaboration` | Channels: <br>- General<br>- Operations<br>- Learning<br><br> Apps: <br>- Approvals<br>- Inspection<br>- SharePoint Pages<br>    - Our store<br>- Planner<br>- Wiki |

## Use team templates with Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates), [Microsoft Teams API overview](/en-us/graph/teams-concept-overview), and [teamsTemplate resource type](/en-us/graph/api/resources/teamstemplate).

Here are the pre-built retail team templates.

Note

An asterisk (\*) indicates that the template is a *Microsoft 365 connected template*. When users create a team using the template, the connected SharePoint template is applied to the site and the team. SharePoint components such as pages, lists, and Power Platform integrations are automatically added and pinned as tabs to the General channel in the team. Users can edit these pages and lists right from within Teams.

To learn more about SharePoint templates, see [Apply and customize SharePoint site templates](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### Manage a Store\*

Use this template to create a team for each retail store location in your organization.

| Template type | TemplateId | Template channels |
| --- | --- | --- |
| Retail - Store | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')` | Channels <br>- General<br>- Shift Handoff<br>- Store Readiness<br>- Learning<br><br>Team properties <br>- Team visibility set to Public<br><br>Member permissions <br>- Can't create, update, or delete channels<br>- Can't add or remove apps<br>- Can't create, update, or remove tabs<br>- Can't create, update, or remove connectors |

Recommended ways to customize the Store template for your organization:

- If your organization has departments within each store, add a channel for each department. Adding a channel facilitates communication and collaboration within the department.
- If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.

### Retail for Managers\*

Use this template to create a team for a set of managers to collaborate across stores or regions. For example, if your organization has regions, you might create a team for the California region and include all the store managers in that region, along with the regional manager for that region.

| Template type | TemplateId | Template channels |
| --- | --- | --- |
| Retail - Manager Collaboration | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')` | Channels <br>- General<br>- Operations<br>- Learning<br><br>Team properties <br>- Team visibility set to Private<br><br>Member permissions <br>- Can create, update, and delete channels<br>- Can add and remove apps<br>- Can create, update, and remove tabs<br>- Can create, update, and remove connectors |

Recommended ways to customize the Manager Collaboration template for your organization:

- If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.

### How to use team templates with Microsoft Graph

To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIds above. For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a team](/en-us/graph/api/team-post).

Note

The channels in the template will automatically be created under the **General** tab.

### Example: Store template extension script

```PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```

Note

If you're using Microsoft Graph to create a team from an existing Microsoft 365 group or team using a Microsoft 365 connected template, the connected SharePoint template isn't automatically applied to the site or team. You'll need to manually apply the SharePoint site template after the team is created. In Teams, go to the team, select **More options** in the upper-right corner &gt; **Open in SharePoint**. Then choose **Settings** &gt; **Apply a site template** and select the corresponding site template.