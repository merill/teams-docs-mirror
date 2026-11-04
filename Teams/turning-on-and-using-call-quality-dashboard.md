---
layout: Conceptual
title: Call Quality Dashboard (CQD) setup - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/turning-on-and-using-call-quality-dashboard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
ms.reviewer: mikedav, siunies, gageames, jamp
ms.date: 2025-09-15T00:00:00.0000000Z
ms.topic: how-to
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Learn about how to turn on and use the Call Quality Dashboard (CQD) and get summary reports of quality of calls.
locale: en-us
document_id: cb8d8b48-561b-6817-1ce0-4b2aedc261a8
document_version_independent_id: dfd5cf4a-509a-3ed1-0267-6281c251fbef
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/turning-on-and-using-call-quality-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: turning-on-and-using-call-quality-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/turning-on-and-using-call-quality-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: d976bb9d-6041-2d02-379a-3ae5a8021d8a
---

# Call Quality Dashboard (CQD) setup - Microsoft Teams | Microsoft Learn

Open the Microsoft Call Quality Dashboard (CQD) at https://cqd.teams.cloud.microsoft (sign in with your admin credentials). Or go to the Teams admin center and select **Analytics & reports** &gt; **Call Quality Dashboard**.

On the page that opens, select **Sign in** and enter the credentials for an administrator account that has "Activate CQD" privileges. This must be done only the first time your tenant accesses CQD in order to allow users holding less privileged admin roles to log in. CQD shows call and meeting quality at an org-wide level for Microsoft Teams and Skype for Business Server 2019.

Important

To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/en-us/skypeforbusiness/hybrid/configure-call-data-connector). See [Plan Call Data Connector](/en-us/skypeforbusiness/hybrid/plan-call-data-connector) before you start.

## Assign admin roles for access to CQD

Assign [roles](/en-us/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.

If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.

Important

Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role. To learn more, see [About Admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles).

| - | View reports | View EUII fields | Create reports | Upload building data | Activate CQD |
| --- | --- | --- | --- | --- | --- |
| Global Administrator | Yes | Yes | Yes | Yes | Yes |
| Teams Administrator | Yes | Yes | Yes | Yes | Yes |
| Teams Communications Administrator | Yes | Yes | Yes | Yes | Yes |
| Teams Communications Support Engineer | Yes | Yes | Yes | No | No |
| Teams Communications Support Specialist | Yes | No | Yes | No | No |
| Skype for Business Administrator | Yes | Yes | Yes | Yes | Yes |
| Global Reader | Yes | Yes | Yes | No | No |
| Reports Reader^1^ | Yes | No | Yes | No | No |

^1^ In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/77ff780d-ab19-4553-adea-09cb65ad0f1f).

Note

If you're not seeing [EUII (end-user identifiable information)](cqd-data-and-reports#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days. Anything older than 28 days is deleted. Additionally, users assigned to one or more [Administrative Units](/en-us/azure/active-directory/roles/administrative-units) don't see EUII even if their role would ordinarily allow it.

For more information about these roles, see [About Office 365 admin roles](/en-us/office365/admin/add-users/about-admin-roles).

After the first time you sign in with a role that can activate CQD, CQD will become accessible to admins with the lesser privileged roles as shown in the table.

### Limitations

- CQD does not currently support [delegated administration for Microsoft Partners](/en-us/office365/admin/add-users/about-admin-roles?view=o365-worldwide#delegated-administration-for-microsoft-partners).
- Users assigned to one or more [Administrative Units](/en-us/azure/active-directory/roles/administrative-units) don't see end-user identifying information (EUII) even if their role would ordinarily allow it.

## Use Power BI to analyze CQD data

[Download Power BI query templates for CQD](https://www.microsoft.com/download/details.aspx?id=102291). These are customizable Power BI templates you can use to analyze and report your CQD data.

Read [Use Power BI to analyze CQD data](cqd-power-bi-query-templates) to learn more.