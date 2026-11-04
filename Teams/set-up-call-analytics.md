---
layout: Conceptual
title: Set up call analytics for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-call-analytics
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
ms.reviewer: mamcgrath
ms.date: 2025-09-15T00:00:00.0000000Z
ms.topic: install-set-up-deploy
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Set up per-user call analytics to identify and troubleshoot Microsoft Teams call quality problems.
locale: en-us
document_id: d8e804b9-4194-26d7-59db-92a57ce33ee7
document_version_independent_id: 82951bb2-df67-c1f2-7153-f207357ef077
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-call-analytics.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-call-analytics
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-call-analytics.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 921c6ed7-d572-b4b8-98b6-d8a84140d7a4
---

# Set up call analytics for Microsoft Teams - Microsoft Teams | Microsoft Learn

Note

This article describes an earlier meeting and call quality troubleshooting experience in the Teams admin center. The experience has been updated and enhanced. For the latest experience and guidance, see [Monitor and troubleshoot Teams meetings and calls from the Teams admin center](monitor-troubleshoot-teams-meetings-calls).

As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**. To take full advantage of call analytics, set up the following:

- Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users. These support roles can't access the rest of the Teams admin center.
- Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.

When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality).

## Give permission to support and helpdesk staff

As the Teams admin, you have full access to call analytics information for all users. We've created some specialized Microsoft Entra roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center). Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support). Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support). Neither role has access to the rest of the Teams admin center.

To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality#what-does-each-teams-support-role-do)?

For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles). To learn how to assign admin roles in Microsoft Entra ID, see [View and assign roles in Microsoft Entra ID](/en-us/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

To learn how to assign administrative roles in Microsoft Entra ID, see [View and assign roles in Microsoft Entra ID](/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## Upload a .tsv or .csv file to add building, site, and tenant information

You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file. With this information, call analytics can map IP addresses to physical locations. Admins and helpdesk agents can use this information to help spot trends in call problems. For example, *why are users in the same building having similar call quality problems?*

You can view and manage your building files with the [Building and endpoint data](cqd-upload-tenant-building-data) page in Teams admin center.