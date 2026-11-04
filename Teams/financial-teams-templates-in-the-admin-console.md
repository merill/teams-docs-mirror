---
layout: Conceptual
title: Use financial team templates - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/financial-teams-templates-in-the-admin-console
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
ms.date: 2025-03-13T00:00:00.0000000Z
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to manage and use financial team templates in the Teams admin center and with Microsoft Graph to quickly and easily create teams for your financial services organization.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
- teams-chat-and-channels
locale: en-us
document_id: e551a2a9-95b6-1ab1-b210-8ec82d55da39
document_version_independent_id: c46f35cc-ee5c-3370-82df-3f9efc7a37ad
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/financial-teams-templates-in-the-admin-console.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: financial-teams-templates-in-the-admin-console
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/financial-teams-templates-in-the-admin-console.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fced3e59-04af-917a-e9a7-77576a9921d9
---

# Use financial team templates - Microsoft Teams | Microsoft Learn

Team templates in Microsoft Teams allow you to quickly and easily create teams by providing a predefined team structure of settings, channels, and preinstalled apps.

For financial services organizations, team templates can be especially powerful, as they help you to quickly deploy consistent teams across your organization. Templates also help staff to get oriented with how to effectively use Teams.

Teams includes templates designed for financial services organizations. Use these prebuilt templates to quickly create teams for staff to communicate and collaborate. In this article, we introduce you to each of these templates and recommend how to use them.

How you manage and work with team templates depends on whether you're an admin or developer.

| If you're: | Then, you: |
| --- | --- |
| An admin or IT pro | Manage team templates in the Teams admin center. View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| A developer | Use Microsoft Graph to create teams from team templates. |

## Manage team templates in the Teams admin center

As an admin, you can manage team templates in the Microsoft Teams admin center. Here, you can view details about each template. You can also [create and assign templates policies](templates-policies) to your staff to control which templates they see in Teams for [creating teams](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

To learn more about team templates in general, see [Get started with team templates in the Teams admin center](get-started-with-teams-templates-in-the-admin-console).

We currently offer the following prebuilt team templates for financial services organizations. To view them, in the left navigation of the Teams admin center, go to **Teams** &gt; **Team templates**.

### Bank Branch

Centralize collaboration for your bank branch employees across huddles, customer meetings, business processes such as mortgage collaboration, and keep everyone in the loop with announcements and kudos.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Bank Branch | `com.microsoft.teams.template.CollaborateWithinABankBranch` | Channels: <br>- General<br>- Announcements<br>- Huddles<br>- Customer Meetings<br>- Approvals Request<br>- Coaching<br>- Skills Development<br>- Loan Processing<br>- Customer Complaints<br>- Kudos<br>- Fun Stuff<br>- Compliance<br><br>Apps:<br>- Approvals<br>- Bulletins<br>- Channel calendar<br>- Employee ideas<br>- Issue reporting<br>- Praise<br>- Shifts<br>- Wiki |

## Use team templates with Microsoft Graph

Developers can use Microsoft Graph to create teams from prebuilt team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates), [Microsoft Teams API overview](/en-us/graph/teams-concept-overview?view=graph-rest-1.0&amp;preserve-view=true), and [teamsTemplate resource type](/en-us/graph/api/resources/teamstemplate?view=graph-rest-1.0&amp;preserve-view=true).

### Bank Branch

Centralize collaboration for your bank branch employees across huddles, customer meetings, business processes such as mortgage collaboration, and keep everyone in the loop with announcements and kudos.

| Template type | TemplateId | Template channels |
| --- | --- | --- |
| Bank Branch | `https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')` | GeneralAnnouncementsHuddlesCustomer MeetingsApprovals RequestCoachingSkills DevelopmentLoan ProcessingCustomer ComplaintsKudosFun StuffCompliance |

Note

For more team templates that apply to financial services organizations, see [Team templates built in Microsoft Graph for small and medium businesses](smb-templates).