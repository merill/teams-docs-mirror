---
layout: Conceptual
title: Get started with team templates in the Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/get-started-with-teams-templates-in-the-admin-console
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
ms.date: 2024-10-30T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- tier2
- highpri
description: Learn about team templates and how to manage them in the Microsoft Teams admin center.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- chat-teams-channels-revamp
- teams-chat-and-channels
locale: en-us
document_id: ef94e9a3-a0a5-11da-f27b-627ac4fa6186
document_version_independent_id: e49db873-ed77-de53-e4dd-be4fc571d734
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/get-started-with-teams-templates-in-the-admin-console.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: get-started-with-teams-templates-in-the-admin-console
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/get-started-with-teams-templates-in-the-admin-console.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: aad08231-b2f9-c844-0b62-aab3554b0d94
---

# Get started with team templates in the Teams admin center - Microsoft Teams | Microsoft Learn

Note

- Private and shared channels are currently not supported in team templates. Private and shared channel creation is not included in template definitions.
- Sensitivity labels are not supported in team templates in GCC environments. The sensitivity label option in the Create team from template flow will not be applied to the team.

## Overview

A team template in Microsoft Teams is a definition of a team's structure designed around a business need or project. As an admin, you can use templates to easily deploy consistent teams across your organization. With templates, your users can quickly create rich collaboration spaces with predefined settings, channels, and apps.

You can manage team templates in the Microsoft Teams admin center or by using PowerShell. You can use the prebuilt templates that we provide and you can also create your own custom templates. You can also apply template policies to control which templates are available to your users in Teams.

This article gives you an overview of working with team templates in the Teams admin center. You'll learn about the properties that are supported in templates, the prebuilt templates that we provide, template size limits, how to create and manage templates, and more.

Note

Your users can [create teams from prebuilt or custom team templates](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) in the Teams app. Developers can also programmatically create teams from prebuilt or custom team templates using Microsoft Graph. To learn more, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates).

## Team template capabilities

Most properties in a team are included and supported by team templates. But there are a few properties and features that aren't currently supported. Here's a summary of what's included and what's not included in team templates.

| Team properties supported by team templates | Team properties not yet supported by team templates |
| --- | --- |
| Template type | Team membership |
| Team name | Team picture |
| Team description | Channel settings |
| Team visibility (public or private) | Connectors |
| Team settings (for example, member, guest, @ mentions) | Files and content |
| Autofavorite channel |  |
| Installed app |  |
| Pinned tabs |  |

Note

We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.

## Prebuilt team templates in the Teams admin center

Here are the prebuilt team templates that are available in the Teams admin center. Prebuilt templates are templates that we created for specific industries. To view these templates, in the left navigation of the Teams admin center, go to **Teams** &gt; **Team templates**.

You can duplicate prebuilt templates but you can't edit them. If you want to change the properties in a prebuilt template, you can create a new template from an existing one, and then add or remove the properties that you want. Keep in mind that certain properties in some templates can't be changed.

Note

An asterisk (\*) indicates that the template is a *Microsoft 365 connected template*. When users create a team using the template, the connected SharePoint template is applied to the site and the team. SharePoint components such as pages, lists, and Power Platform integrations are automatically added and pinned as tabs to the General channel in the team. Users can edit these pages and lists right from within Teams.

To learn more about SharePoint templates, see [Apply and customize SharePoint site templates](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Manage a Project\* | `com.microsoft.teams.template.ManageAProject` | Channels: <br>- General<br>- Announcements<br>- Resources<br>- Planning<br><br> Apps:<br>- Approvals<br>- Bulletins<br>- Lists<br>    - Project tracker<br>    - Issue tracker<br>- Milestones<br>- OneNote<br>- Power Automate<br>- SharePoint Pages<br>    - Our site<br>- Planner<br>- Wiki |
| Manage an Event\* | `com.microsoft.teams.template.ManageAnEvent` | Channels: <br>- General<br>- Announcements<br>- Budget<br>- Content<br>- Logistics<br>- Planning<br>- Marketing and PR<br><br> Apps:<br>- Approvals<br>- Bulletins<br>- Employee ideas<br>- Lists<br>    - Content scheduler<br>- Milestones<br>- OneNote<br>- Power Automate<br>- SharePoint Pages<br>    - Our site<br>    - About our event<br>- Planner<br>- Wiki |
| Onboard Employees\* | `com.microsoft.teams.template.OnboardEmployees` | Channels: <br>- General<br>- Announcements<br>- Employee Chat<br>- Training<br><br>Apps:<br>- Bulletins<br>- Employee ideas<br>- Lists<br>    - Onboarding checklist<br>- Milestones<br>- Power Automate<br>- SharePoint Pages<br>    - Get started<br>    - Training<br>- Planner<br>- Viva Engage<br>- Wiki |
| Adopt Office 365 | `com.microsoft.teams.template.AdoptOffice365` | Channels: <br>- General<br>- Announcements<br>- Champions Corner<br>- Team Forms<br>- Calendar<br><br> Apps: <br>- Bulletins<br>- Channel calendar<br>- Milestones<br>- Wiki |
| Organize Help Desk\* | `com.microsoft.teams.template.OrganizeHelpDesk` | Channels:<br>- General<br>- Announcements<br>- FAQ<br><br>Apps:<br>- Issue reporting<br>- Lists<br>    - Devices<br>    - Tickets<br>- OneNote<br>- Power Automate<br>- SharePoint Pages<br>    - Our site<br>    - FAQs<br>- Planner<br>- Wiki |
| Incident Response | `com.microsoft.teams.template.CoordinateIncidentResponse` | Channels: <br>- General<br>- Announcements<br>- Logistics<br>- Planning<br>- Recovery<br>- Urgent<br><br> Apps: <br>- Approvals<br>- Bulletins<br>- Excel<br>- Inspection<br>- Milestones<br>- OneNote<br>- Power Automate<br>- SharePoint<br>- Planner<br>- Wiki |
| Crisis Communications\* | `com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` | Channels: <br>- General<br>- Announcements<br>- Executive Update<br>- Planning<br>- Logistics<br><br>Apps: <br>- Approvals<br>- Issue reporting<br>- Lists<br>    - Content scheduler<br>    - Project plan<br>- OneNote<br>- Power Automate<br>- SharePoint Pages<br>    - Our site<br>    - Latest update<br>- Planner |
| Manage a Store\* | `com.microsoft.teams.template.retailStore` | Channels: <br>- General<br>- Shift Handoff<br>- Store Readiness<br>- Learning<br><br> Apps: <br>- Approvals<br>- Inspection<br>- Lists<br>    - Inventory list<br>- SharePoint Pages<br>    - Our store<br>- Shifts<br>- Planner<br>- Wiki |
| Bank Branch | `com.microsoft.teams.template.CollaborateWithinABankBranch` | Channels: <br>- General<br>- Announcements<br>- Huddles<br>- Customer Meetings<br>- Approvals Request<br>- Coaching<br>- Skills Development<br>- Loan Processing<br>- Customer Complaints<br>- Kudos<br>- Fun Stuff<br>- Compliance<br><br>Apps:<br>- Approvals<br>- Bulletins<br>- Channel calendar<br>- Employee ideas<br>- Issue reporting<br>- Praise<br>- Shifts<br>- Wiki |
| Patient Care | `com.microsoft.teams.template.healthcareWard` | Channels:<br>- General<br>- Announcements<br>- Huddles<br>- Rounds<br>- Staffing<br>- Training<br><br> Apps: <br>- Approvals<br>- Bulletins<br>- Inspection<br>- Lists<br>- Shifts<br>- Planner<br>- Wiki |
| Hospital | `com.microsoft.teams.template.healthcareHospital` | Channels: <br>- General<br>- Announcements<br>- Compliance<br>- Custodial<br>- Human Resources<br>- Pharmacy<br><br> Apps: <br>- Approvals<br>- Bulletins<br>- Employee ideas<br>- Inspection<br>- Lists<br>- Shifts<br>- Planner<br>- Wiki |
| Quality and Safety | `com.microsoft.teams.template.QualitySafety` | Channels: <br>- General<br>- Leadership<br>- Maintenance<br>- Production Line 1<br>- Production Line 2<br>- Production Line 3<br>- Health and Safety<br>- Training<br>- Fun Stuff<br><br> Apps: <br>- Approvals<br>- Inspection<br>- Issue reporting<br>- Shifts<br>- Planner<br>- Wiki |
| Retail for Managers\* | `com.microsoft.teams.template.retailManagerCollaboration` | Channels: <br>- General<br>- Operations<br>- Learning<br><br> Apps: <br>- Approvals<br>- Inspection<br>- SharePoint Pages<br>    - Our store<br>- Planner<br>- Wiki |
| Manage Volunteers | `com.microsoft.teams.template.ManageVolunteers` | Channels: <br>- General<br>- Announcements<br>- Reporting<br>- Volunteer Management<br>- Engagement Opportunities<br>- Volunteer Onboarding<br><br> Apps: <br>- OneNote<br>- Power Apps<br>- Power BI<br>- SharePoint<br>- Planner<br>- Website<br>- YouTube |
| Frontline Collaboration | `com.microsoft.teams.template.Frontline` | Channels: <br>- General<br>- Announcements<br>- Shift Handoff<br>- Operations<br>- Learning<br><br> Apps: <br>- Approvals<br>- Issue reporting<br>- Lists<br>- Praise<br>- Shifts<br>- Planner |

### Team templates by category and industry

For more information about ways to use the prebuilt templates in your industry, see:

- [General team templates](general-teams-templates-in-the-admin-console)
- [Financial team templates](financial-teams-templates-in-the-admin-console)
- [Government team templates](government-teams-templates-in-the-admin-console)
- [Healthcare team templates](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console)
- [Manufacturing team templates](manufacturing-teams-templates-in-the-admin-console)
- [Nonprofit team templates](team-templates-nonprofit)
- [Retail team templates](get-started-with-retail-teams-templates)

## Team template size limits

Templates are limited to a specific number of channels, tabs, and apps.

Note

You can add more channels, tabs, and apps to the team after it's created from a template.

| Feature | Limit |
| --- | --- |
| Channels per template | 15 |
| Tabs per channel in a template | 20 |
| Apps per template | 50 |

For more information, see [Limits and specifications of Teams](limits-specifications-teams).

## Manage team templates

### Manage team templates in the Teams admin center

#### View team templates

To view team templates, in the left navigation of the Teams admin center, go to **Teams** &gt; **Team templates**. Select a template to see more details, including the channels and apps it contains.

#### Create your own team templates

You can create your own custom templates from scratch, from an existing team, and from an existing template. To learn more, see:

- [Create a custom team template](create-a-team-template)
- [Create a template from an existing team](create-template-from-existing-team)
- [Create a team template from an existing team template](create-template-from-existing-template)

#### Apply team template policies

To control the templates that users see in Teams for [creating teams](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b), you can set templates policies and assign them to users and groups in your organization. To learn more, see [Manage team templates in the Teams admin center](templates-policies).

### Manage team templates using PowerShell

Use the following cmdlets to manage your templates in PowerShell.

- [Get-CsTeamTemplate](/en-us/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/en-us/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/en-us/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/en-us/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/en-us/powershell/module/teams/update-csteamtemplate)