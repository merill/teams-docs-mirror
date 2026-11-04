---
layout: Conceptual
title: Manage teams in the Microsoft Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-teams-in-modern-portal
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
audience: admin
search.appverid: MET150
ms.reviewer: jastark
ms.date: 2026-02-26T00:00:00.0000000Z
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
- essentials-manage
description: Learn how to view or update the teams that your organization has set up for collaboration in the Microsoft Teams admin center.
locale: en-us
document_id: 3b51b67a-d89c-723f-3520-87cb2dc93b90
document_version_independent_id: 78d10cbc-d75b-2b02-d49c-2c3fe1579807
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-teams-in-modern-portal.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-teams-in-modern-portal
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-teams-in-modern-portal.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b93f22ad-73dd-cdfb-d5d3-9d9671de9201
---

# Manage teams in the Microsoft Teams admin center - Microsoft Teams | Microsoft Learn

This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.

As an admin, you may need to view or update the teams in your organization, or you might need to perform remediation actions such as assigning owners for ownerless teams. You can manage teams through both the Teams PowerShell module and the Teams admin center. You can access the admin center at https://admin.teams.microsoft.com. For full administration capabilities using these two toolsets, you should make sure that you're assigned one of the following roles:

- Global administrator
- Teams administrator
- Teams Reader (Read-Only View, Note: Currently this role will need a Teams license to be assigned to access the Manage Teams & Channel Section)

You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/en-us/powershell/teams/).

## Teams overview grid

Management tools for teams are under the **Teams** node in the Microsoft Teams admin center. (In the admin center, select **Teams** &gt; **Manage teams**.) This page provides a view of all the teams in your organization.

![Screenshot of the Teams overview grid.](media/manage-teams-in-modern-portal-grid.png)

The grid displays the following properties:

- **Team name**
- **Standard channels** - a count of the standard channels in the team.
- **Private channels** - a count of the private channels in the team.
- **Shared channels** - a count of the shared channels in the team.
- **Team members** - a count of total users, including owners, members, and guests for the team.
- **Owners** - a count of owners for this team.
- **Guests** - a count of Microsoft Entra B2B guests who are members of this team.
- **Privacy** - whether the team is public or private.
- **Status** - the [Archived](https://support.office.com/article/dc161cfd-b328-440f-974b-5da5bd98b5a7) or Active status or Expiring status for this team.
- **Description** - the description of the team.
- **Sensitivity** - the sensitivity label associated with the team. (This column may be called *classification* if you haven't set up sensitivity labels.)
- **GroupID** - the unique ID for the Microsoft 365 group associated with the team.
- **Expiration date** - the date the team is scheduled to expire if the team has an [expiration policy](/en-us/microsoft-365/solutions/microsoft-365-groups-expiration-policy).

If you don't see all these properties in the grid, select the **Edit columns** icon. In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid. When you're finished, select **Apply**.

### Add a team

To add a new team, click **Add**. In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the sensitivity if needed.

This video shows the steps to create a new team and a channel for them.

### Edit a team

To edit team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**. To edit the membership (or) channel setup, clicking on the team will navigate you to the Team's Profile (details) page.

This video shows the steps to view and edit the details of an existing team.

### Archive a team

[Archiving a team](archive-or-delete-a-team) puts the team into read-only mode within Teams. To archive a team, select the team by clicking to the left of the team name, and then select **Archive**.

### Restore deleted teams

![Screenshot of the Manage teams page in the Teams admin center, showing the View deleted teams option.](media/manage-teams-in-modern-portal/image.png)

To restore a deleted team in the Teams admin center, do the following:

1. Go to the **[Teams Admin center](https://admin.teams.microsoft.com/)** &gt; **Teams** &gt; **Manage teams** and click on the View deleted team option on the top right corner.
2. Select the team that you want to restore from the list, and then click **Restore**. You can also select multiple teams and restore them.

Note

It might take some time for the team to appear in the **Manage Teams** list. Select **Refresh** to refresh the list.

### Renew an expiring team

To renew an expiring team in the Teams admin center, do the following:

1. Go to the **[Teams Admin center](https://admin.teams.microsoft.com/)** &gt; **Teams** &gt; **Manage teams**.
2. Select **Filter**, and in the **Filter** section, do the following:

    1. Select **Match all these conditions**.
    2. Choose the **Expiration Date** and select one of values from the list (for example: in the next 7 days, in the next 14 days, or in the next 30 days).
    3. Click **Apply**.
3. Select the expiring team that you want to renew, select **Renew**, and then select **Confirm**.

Note

If you do not find the team's detail updated immediately, select **Refresh**. Note that it might take some time for the team's details and expiration date to get updated.

## Team profiles

You can navigate to the team profile page (Team details page) of any team from the main teams overview grid by clicking on the team name. The team profile page shows the Membership details (members, owners, and guests) that belong to the team, as well as the team's channels (Each channel has it's own profile page to view the list of all members & shared team) and settings. From the team profile page, you can:

- Add or remove members and owners to the team (or) each individual channel.
- Add or remove channels (note that you can't remove the General channel or update the membership for standard channels).
- Change team settings.

On the team's profile page, you can select **Edit** and change the following elements of a team:

- **Team name**
- **Description**
- **Privacy** - set whether the team is public or private.
- **Sensitivity** - set the sensitivity label for the team.
- **Member permissions** - set how members interact with messages, channels, and apps.
- **Guest permissions** - set whether guests can add or remove channels.
- **Fun settings** - set whether team members can use giphys, stickers, and memes.

The changes that you make to a team are logged. If you're modifying Microsoft 365 group settings (changing the name, description, photo, privacy, sensitivity, or team members), the changes are attributed to you through the audit pipeline. If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.