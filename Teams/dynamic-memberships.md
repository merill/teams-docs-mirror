---
layout: Conceptual
title: Overview of dynamic membership for teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/dynamic-memberships
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: arnavgupta
ms.date: 2026-06-15T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
search.appverid: MET150
description: Learn how Microsoft Teams supports teams associated with Microsoft 365 groups by using dynamic membership.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.collection:
- M365-collaboration
locale: en-us
document_id: 6a578ddb-6494-9bda-529e-0156e5ab7c30
document_version_independent_id: 57d519c9-90f0-873d-ffef-589f0b3b3ac9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/dynamic-memberships.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: dynamic-memberships
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/dynamic-memberships.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
platformId: 6a4b446f-2764-5f76-e50d-b7c690e829d7
---

# Overview of dynamic membership for teams - Microsoft Teams | Microsoft Learn

Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*. Dynamic membership defines membership of a team by one or more rules that check for certain user attributes in Microsoft Entra ID. Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.

With dynamic membership, you can set up teams for certain cohorts of users in your organization. Possible scenarios include:

- A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications. This feature is especially important if the hospital relies on temporary employees.
- A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.
- An airline wants to create a team for each flight (like a Tuesday afternoon nonstop from Chicago to Atlanta) and has a frequently changing flight crew automatically assigned or removed as needed.

Dynamic membership allows a team's members to update automatically based on a specific set of criteria, instead of manually managing membership. Using dynamic membership requires Microsoft Entra ID P1 licenses. [Tenant admins assign team membership](/en-us/azure/active-directory/users-groups-roles/groups-dynamic-membership) to a user's Microsoft Entra properties.

Microsoft Teams might take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.

When using teams with dynamic groups:

- Rules can define who is a team member, but not who is a team owner.
- Owners can't add or remove users as members of the team since dynamic group rules define members.
- Teams clients don't allow member management for the team. Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.

To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/en-us/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

You can change an existing team to have a dynamic membership. See [Change static group membership to dynamic in Microsoft Entra ID](/en-us/azure/active-directory/users-groups-roles/groups-change-type) for information.