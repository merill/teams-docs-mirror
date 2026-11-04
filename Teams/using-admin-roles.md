---
layout: Conceptual
title: Use Microsoft Teams administrator roles to manage Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/using-admin-roles
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.date: 2026-02-26T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- essentials-manage
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
description: Learn how to use the administrative roles to designate administrators who need different levels of access to manage Teams.
locale: en-us
document_id: 6b434530-6bf2-6e00-6eae-6fa043d022ce
document_version_independent_id: caab785f-e3a4-831a-87d8-26934a9f834f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/using-admin-roles.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: using-admin-roles
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/using-admin-roles.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6176ae09-d4f5-8f95-124b-8f525f08a146
---

# Use Microsoft Teams administrator roles to manage Teams - Microsoft Teams | Microsoft Learn

Using Microsoft Entra ID, you can designate administrators who need different levels of access for managing Microsoft Teams. Administrators can manage the entire Teams workload, or they can have delegated permissions for troubleshooting call quality problems or managing your organization's telephony needs.

## Teams roles and capabilities

There are several Teams admin roles available: Teams Administrator, Teams Communications Administrator, Teams Communications Support Specialist, Teams Communications Support Engineer, Teams Communications Support Specialist, Teams Device Administrator, Teams Reader and Teams Telephony Administrator. Review the following table to understand what each role can do and which tools the admin can use in the Microsoft Teams admin center and PowerShell.

To follow along, you must be an admin. The instructions for getting the permissions are in this article.

| Role | Can do these tasks | Can access the following tools |
| --- | --- | --- |
| Teams Administrator | Manage the Teams service, and manage and create Microsoft 365 Groups. | Everything in the Microsoft Teams admin center and associated PowerShell controls, including:<br>- Manage meetings, including meeting policies, configurations, and conference bridges.^1,2^<br>- Manage voice, including calling policies, phone number inventory and assignment, and voice application policies.^1,3^<br>- Create and manage resource accounts with both a Teams Administrator and User Administrator role assigned. For more information, see [Assign permissions for managing a resource account](aa-cq-manage-resource-accounts).^1,3^<br>- Manage messaging, including messaging policies.^1,2^<br>- Manage all org-wide settings, including federation, teams upgrade, and teams client settings.^1,2^<br>- Manage the teams in the organization and their associated settings, including membership (group management supported via PowerShell, team management in the Teams admin center).^1,2^<br>- Manage Teams-certified devices and set up and assign configuration policies.^1^<br>- View user profile page and troubleshoot user call quality problems using advanced troubleshooting toolset.^2^<br>- Access all reports in the Microsoft Teams admin center<br>- Access, monitor and troubleshoot tenant's call quality and reliability using data exposed in Call Quality Dashboard (CQD) down to the users impacted by poor call quality. Create new call quality reports, update and remove call quality reports as needed. Upload and update CQD building data.<br>- [Publish apps to the tenant app catalog in the Microsoft Teams admin center](manage-apps) |
| Teams Communications Administrator | Manage calling and meetings features within the Teams service. | Manage meetings, including meeting policies, configurations, and conference bridges.^1,2^ Manage voice, including calling policies, phone number inventory and assignment, and resource account creation and management.^1,3^Create and manage resource accounts with both a Teams Communications Administrator and User Administrator role assigned. For more information, see [Assign permissions for managing a resource account](aa-cq-manage-resource-accounts).^1,3^ View user profile page and troubleshoot user call quality problems using the advanced troubleshooting toolset.^2^ Access, monitor, and troubleshoot tenant's call quality and reliability using data exposed in Call Quality Dashboard (CQD) down to the users who are impacted by poor call quality. Create new call quality reports, update and remove call quality reports as needed. Upload and update CQD building data. |
| Teams Communications Support Engineer | Troubleshoot communications issues within Teams by using **advanced** tools. | View user profile page and troubleshoot user call quality problems using advanced troubleshooting toolset.^2^ Access, monitor, and troubleshoot tenant's call quality and reliability using data exposed in Call Quality Dashboard (CQD) down to the users who are impacted by poor call quality. |
| Teams Communications Support Specialist | Troubleshoot communications issues within Teams by using **basic** tools. | Access user profile page for troubleshooting calls in Call Analytics. Can only view user information for the specific user being searched for.^2^ Access, monitor, and troubleshoot tenant's call quality and reliability using data exposed in Call Quality Dashboard (CQD). |
| Teams Device Administrator | Manage devices configured for use with the Teams service. | Manage device configuration and updates, review device health and status of connected peripherals, set up and apply configuration profiles, and restart devices.<br>The Teams Device Administrator role doesn't provide access to call quality data or call analytics. To view call quality data or call analytics, you need to be assigned the Teams Communications Administrator role. |
| Teams Reader | Read everything in the Teams admin center, but not update anything | Manage entirety of Teams admin center with READ only view. Users assigned this role **cannot** do the following tasks:<br>- Cannot view Teams management<br>- Cannot access Meetings & Calls details of users<br>- Cannot access Notifications & Rules management<br>- Cannot access Frontline worker deployment management<br>- Cannot access the advanced collaboration insights dashboard |
| Teams Telephony Administrator | Manage Telephony features in Teams services | Manage voice and telephony, including calling policies, phone number management and assignment, voice applications, and resource account creation and management. Create and manage resource accounts with both a Teams Telephony Administrator and User Administrator role assigned. For more information, see [Assign permissions for managing a resource account](aa-cq-manage-resource-accounts).^1,3^Access to Public Switched Telephone Network (PSTN) usage reports from Teams admin center. View user profile page. Create and manage support tickets in Azure and the Microsoft 365 admin center. |

^1^[PowerShell - Microsoft Teams module](https://www.powershellgallery.com/packages/MicrosoftTeams/)^2^[Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center)^3^ Teams administrator account must have a valid Teams license.

For more information about scoping these admin roles to select users/ groups within your organization, see [Administrative units for Microsoft Teams](/en-us/microsoftteams/teams-administrative-units)

For more information about the admin tools available for managing Microsoft Teams, see [Managing Microsoft Teams](manage-teams-skypeforbusiness-admin-center).

For more information about limits, specifications, and other requirements that apply to Teams, see [Limits and specifications for Microsoft Teams](limits-specifications-teams).

For information about Microsoft 365 admin center roles, such as Global Reader and Global Administrator, see [About admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles). Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Assign users to each role

You can assign users or groups to these roles in Microsoft Entra ID. To learn how to assign administrative roles to a user in Microsoft Entra ID, see [Assign user roles with Microsoft Entra ID](/en-us/entra/fundamentals/users-assign-role-azure-portal).

## Cmdlets available for each role

Most of the PowerShell tools for these admin roles live in the Teams PowerShell module.

To view the full list of cmdlets:

```powershell
Get-Command -Module MicrosoftTeams
```

### Related articles

- [Microsoft Teams PowerShell Overview](teams-powershell-overview)
- [Microsoft Teams PowerShell](/en-us/powershell/module/teams/)
- [Assign team owners and members in Microsoft Teams](assign-roles-permissions)