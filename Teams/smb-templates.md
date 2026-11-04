---
layout: Conceptual
title: Team templates for small and medium businesses built with Microsoft Graph - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/smb-templates
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: ITPro
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: lavenkat
ms.date: 2025-03-13T00:00:00.0000000Z
description: Use Microsoft Teams predefined templates built in Microsoft Graph to quickly and easily create teams for small and medium businesses.
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
- teams-chat-and-channels
locale: en-us
document_id: 54d947da-be38-b17b-760f-7b06c56d6cb5
document_version_independent_id: e2ef3064-4d6d-9d38-d298-c8d0528b14a6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/smb-templates.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: smb-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/smb-templates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 393ea751-a95a-bb26-bda8-7924ed037447
---

# Team templates for small and medium businesses built with Microsoft Graph - Microsoft Teams | Microsoft Learn

Team templates in Microsoft Teams allow you to quickly and easily create teams by providing a predefined team structure of settings, channels, and preinstalled apps.

For small and medium businesses, templates can be especially powerful, as they help you to quickly deploy Teams across your organization. Templates also help users to get oriented with how to effectively use Teams. This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.

We currently offer three prebuilt templates for small and medium businesses that you can use for various situations. All templates create *private* teams. After you create the teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.

Note

You can also use Microsoft Graph to create your own custom templates. To learn more, see [teamTemplate resource type](/en-us/graph/api/resources/teamtemplate).

To learn more about team templates in general, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates).

## Company-Wide template

The Company-Wide template is meant for communication and collaboration for the entire company. You can use the **General** channel for company-wide announcements, industry news or executive posts. The **Human Resources** channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development. The **Fun Stuff** channel provides a social platform for all random and fun posts.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| SMB - Company-wide | `https://graph.microsoft.com/beta/`` teamsTemplates('SmallBusinessOrgWide')` | Channels <br>- General\*<br>- Human Resources\*<br>- Fun Stuff\*<br><br> Apps<br>- Company Portal (Website pinned to the **Human Resources** channel)<br><br>Team properties <br>- Team visibility set to Private |

\*Auto-favorited channels

To create the Company-Wide team by taking default settings from the predefined template, supply the JSON representation of the team object in the request body. To learn more about how to deploy team templates, see the Microsoft Graph [article on creating a Team](/en-us/graph/api/team-post?view=graph-rest-beta&amp;preserve-view=true).

### Request

```http
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## Executive Team template

The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients. This template comes with a *private* channel to invite select users for specific topics.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| SMB - Executives Team | `https://graph.microsoft.com/beta/`` teamsTemplates('SmallBusinessExecutive')` | Channels <br>- General\*<br>- Private \*<br><br> Apps<br>- OneNote (pinned to the **Private** channel)<br>- Planner (pinned to the **Private** channel)<br><br>Team properties <br>- Team visibility set to Private |

\*Auto-favorited channels

To create the Executives team by taking default settings from the predefined template, supply the JSON representation of the team object in the request body. To learn more about how to deploy team templates, see the Microsoft Graph [article on creating a Team](/en-us/graph/api/team-post?view=graph-rest-beta&amp;preserve-view=true).

### Request

```http
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## Departmental Team template

The Departmental team template can be used for creating a team for individual departments or for projects. The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate. The template comes with a *private* channel to invite select users for specific topics.

We also provide the script below for the Finance team that can be used to extend the template to other departments or specific projects by adding, deleting from, or editing to your liking. For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| SMB - Finance | `https://graph.microsoft.com/beta/`` teamsTemplates('SmallBusinessFinance')` | Channels <br>- General\*<br>- Private \*<br><br> Apps<br>- OneNote (pinned to the **Private** channel)<br>- Planner (pinned to the **Private** channel)<br><br>Team properties <br>- Team visibility set to Private |

\*Auto-favorited channels

To create the Finance team by taking default settings from the predefined template, supply the JSON representation of the team object in the request body. To learn more about how to deploy team templates, see the Microsoft Graph [article on creating a Team](/en-us/graph/api/team-post?view=graph-rest-beta&amp;preserve-view=true).

### Request

```http
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

## Example: Finance Team template extension script

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```