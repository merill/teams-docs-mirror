---
layout: Conceptual
title: Use nonprofit team templates - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/team-templates-nonprofit
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
ms.date: 2025-08-08T00:00:00.0000000Z
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to manage and use the Manage volunteers team template to easily and quickly create teams for staff in your nonprofit organization to communicate and collaborate on volunteer management activities.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
- teams-chat-and-channels
locale: en-us
document_id: ac6f2c65-9f7f-8ec3-351a-f353c08d5e64
document_version_independent_id: ac6f2c65-9f7f-8ec3-351a-f353c08d5e64
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/team-templates-nonprofit.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: team-templates-nonprofit
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/team-templates-nonprofit.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 82467a63-1ed3-2337-4dff-bdfc489cdb8b
---

# Use nonprofit team templates - Microsoft Teams | Microsoft Learn

Team templates in Microsoft Teams allow you to quickly and easily create teams by providing a predefined team structure of settings, channels, and preinstalled apps.

For nonprofit organizations, team templates can be especially powerful, as they help you to quickly deploy consistent teams across your organization. Templates also help staff to get oriented with how to effectively use Teams.

Teams includes a Manage Volunteers team template designed to streamline volunteer management activities. Use this prebuilt template to quickly create teams for staff to communicate and collaborate on volunteer management tasks and activities.

In this article, you learn about the Manage Volunteers team template and how to use it to create a team. This article also gives you an overview of how to manage team templates in the Teams admin center.

## Manage Volunteers team template

Bring your staff together to communicate and collaborate on volunteer management tasks and activities.

This template includes channels and apps designed to streamline volunteer management activities. Staff can organize and share onboarding materials and frequently used documents, view reporting, stay up to date on important team and event announcements, and more. The template also integrates with [Volunteer Management](/en-us/industry/nonprofit/volunteer-management-deploy), an app that's part of [Microsoft for Nonprofits](/en-us/industry/nonprofit/), enabling staff to manage volunteer engagement opportunities within Teams.

Here's the channels and apps that come with the Manage Volunteers team template.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Manage Volunteers | `com.microsoft.teams.template.ManageVolunteers` | Channels: <br>- General<br>    - Website¹<br>- Announcements<br>- Reporting<br>    - Power BI¹<br>- Volunteer Management<br>    - Power Apps¹<br>- Engagement Opportunities<br>    - Planner¹<br>- Volunteer Onboarding<br>    - SharePoint¹<br>    - OneNote¹<br><br>Apps: <br>- OneNote<br>- Power Apps<br>- Power BI<br>- SharePoint<br>- Planner<br>- Website<br>- YouTube |

¹App added to the channel as a tab.

## Create a team using the Manage volunteers team template

### Create the team

It takes only a few quick steps to create a team from the Manage volunteers template.

1. In Teams, go to **Chat** &gt; **New team** &gt; **Create** &gt; **More create team options**.
2. Choose the **Manage Volunteers** team template.
3. Select **Use this template**.
4. Give your team a name and add a description. You can also rename channels to customize the team.
5. Choose a sensitivity label and sublabel.
6. Choose a privacy level:
    - **Private**: People need permission from the team owner to join the team.
    - **Public**: Anyone in your organization can join the team.
7. Select **Create**.

To learn more, see [Create a team with a team template](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

### Add the Volunteer Management app to the Power Apps tab

To use the Volunteer Management app in Teams, add it to the Power Apps tab in the Volunteer Management channel.

1. In Teams, go to the team you created, choose the Volunteer Management channel, and then select the **Power Apps** tab.
2. In the drop-down list, select **Model-driven apps**, and then search for and select **Volunteer Management**.
3. Select **Save**.

To learn more, see [Embed a model-driven app as a tab app in Teams](/en-us/powerapps/teams/embed-model-driven-teams-tab).

## View and manage team templates in the Teams admin center

If you're an admin, you can view and manage team templates in the Microsoft Teams admin center. To view the Manage volunteers template, in the left navigation of the Teams admin center, go to **Teams** &gt; **Team templates**.

You can also [create and assign templates policies](templates-policies) to your users to control which templates they see in Teams for creating teams.

To learn more about team templates in general, see [Get started with team templates in the Teams admin center](get-started-with-teams-templates-in-the-admin-console).