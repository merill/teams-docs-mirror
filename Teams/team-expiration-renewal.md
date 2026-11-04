---
layout: Conceptual
title: Team expiration and renewal in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/team-expiration-renewal
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
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
ms.reviewer: 
ms.date: 2026-10-01T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
ms.custom:
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.collection:
- M365-collaboration
description: Learn about team expiration and renewal and how to use Microsoft 365 group expiration policy to automatically cleanup unused teams in Microsoft Teams.
f1.keywords:
- NOCSH
locale: en-us
document_id: b41d63bc-26f4-fd50-adc4-f665c1a4cd88
document_version_independent_id: 24248b2d-79a1-98a7-86dd-f6dbcf9e2ab3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/team-expiration-renewal.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: team-expiration-renewal
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/team-expiration-renewal.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fa4d8ced-e839-7546-df82-b4fcbe56b988
---

# Team expiration and renewal in Microsoft Teams - Microsoft Teams | Microsoft Learn

Organizations with a large number of teams often have teams that are never used. This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization. Over time, such teams can accumulate and create a burden on tenant resources.

To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](/en-us/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically cleanup unused teams. Because teams are backed by groups, group expiration policies automatically apply to teams as well.

When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date. When the team owner receives the notification, they can select **Renew now** in team settings to renew the team.

![Screenshot of the Renew Now button to renew a team in team settings.](media/team-expiration.png)

If the team owner doesn't renew the team and there's no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.

## Team auto-renewal

There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due. In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.

To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy. When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.

## Known issues

**Expiration date of team and underlying group don't match**

Before a team is renewed, the group that backs the team is renewed first. As part of renewal, a new expiry date is set on the group for a future date. This new date might not be immediately visible in Teams. It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.