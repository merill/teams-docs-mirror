---
layout: Conceptual
title: Manage meeting templates in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-meeting-templates
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: idilates
ms.date: 2024-11-19T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
description: Learn how Microsoft Teams Administrators can specify which meeting templates are available to their users.
locale: en-us
document_id: c5f2f82e-38d0-a35c-67a8-81c843de760a
document_version_independent_id: c5f2f82e-38d0-a35c-67a8-81c843de760a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-meeting-templates.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-meeting-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-meeting-templates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0ac557a9-6662-ca92-1c97-643539796a25
---

# Manage meeting templates in Microsoft Teams - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

As an admin, you can use meeting template policies in Microsoft Teams to determine which meeting templates are available to users in your organization.

## Specify which meeting templates are available to users

By default, the **Global (Org-wide default)** meeting template policy allows users to see all available templates, including default templates and any custom templates that you've created. If you want to limit which templates are available for different people or groups, you can create policies specifying this.

To create a meeting template policy, follow these steps:

1. In the Teams admin center, expand **Meetings** and select **Meeting template policies**.
2. Select **Add**.
3. Type a name and description for the policy.
4. In the **Viewable templates** list, select any templates that you don't want users with this policy to see, and then select **Hide**.
5. Select **Save**.

    Once you've created the policy, you need to assign it to users or groups. See [Assign policies to users and groups](assign-policies-users-and-groups) for more information.

## Change which meeting templates are visible to users

You can update a meeting template policy if you want to change which templates are available to the users with that policy.

To edit a meeting template policy, follow these steps:

1. In the Teams admin center, expand **Meetings** and select **Meeting template policies**.
2. Select the policy you want to change, and then select **Edit**.
3. To make a viewable template hidden, select the template in the **Viewable templates** list and then select **Hide**.
4. To make a hidden template viewable, select the template in the **Hidden templates** list and then select **Show**.
5. Select **Save**.