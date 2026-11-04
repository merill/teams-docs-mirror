---
layout: Conceptual
title: Microsoft 365 Groups and Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/office-365-groups
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: rahulnayak
ms.date: 2026-02-26T00:00:00.0000000Z
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: concept-article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- m365-groups
description: Learn about how Microsoft 365 groups and group memberships work with Microsoft Teams.
locale: en-us
document_id: 3d86301b-ce9c-388c-e563-9e5e5c27132e
document_version_independent_id: 07e4ae23-0966-e8f3-9b7c-4f6c02569eb0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/Office-365-groups.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: office-365-groups
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/Office-365-groups.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: a02581f5-bfd0-beed-b996-76a1c662c5b6
---

# Microsoft 365 Groups and Microsoft Teams - Microsoft Teams | Microsoft Learn

Microsoft 365 Groups is the cross-application membership service in Microsoft 365. At a basic level, a Microsoft 365 group is an object in Microsoft Entra ID with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner, and OneNote notebook. You can add or remove people to the group just as you would any other group-based security object in Active Directory.

![Diagram showing Microsoft 365 Groups and related services.](/en-us/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

By default, users in Microsoft 365 can create and manage groups. For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters#groups-in-microsoft-365) poster.

## How Microsoft 365 Groups work with Teams

When you create a team, a Microsoft 365 group is created to manage team membership. The group's related services, such as a SharePoint site, mailbox, etc. are created at the same time.

People who create teams can choose to use an existing Microsoft 365 group if they're an owner of that group. Each channel in the team has a separate folder in the document library. Creating folders directly in the document library doesn't create channels in the team.

When creating a Microsoft 365 group in the Teams admin center, Outlook, or SharePoint, the group mailbox is visible in Outlook. When creating a team in Teams, the group mailbox is hidden by default. You can use the [Set-UnifiedGroup](/en-us/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.

## Group membership

If you remove a member of a team, they are removed from the Microsoft 365 group as well. Removal from the group immediately removes the team and channels from the Teams client. If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Viva Engage group, or shared OneNote. However, they will still have access to the team's chat functionality for approximately two hours.

As a best practice for managing team members, add and remove them from Teams to ensure that permissions updates for other group-connected workloads occur quickly. If you add or remove team members outside of Teams (by using the Microsoft 365 admin center, Microsoft Entra ID, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.

## Deleting groups and teams

Deleting a Microsoft 365 group removes the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and marks the SharePoint site for deletion. It takes approximately 20 minutes between the removal of a team and its effect on Outlook. Deleting a team from Teams removes it immediately from view to all who are members of the team. If you remove members of a Microsoft 365 group that is connected to Teams, there could be a delay of approximately two hours before the team is removed from view in Teams for the affected people who were removed.

For details about groups and teams end of lifecycle options, see [End of lifecycle options for groups, teams, and Viva Engage](/en-us/microsoft-365/solutions/end-life-cycle-groups-teams-sites-viva-engage) and [Archive or delete a team in Microsoft Teams](archive-or-delete-a-team).