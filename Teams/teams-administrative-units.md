---
layout: Conceptual
title: Using administrative units in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-administrative-units
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: andrewklutz
ms.date: 2026-10-06T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use administrative units to manage groups of users or other entities in Microsoft Teams.
locale: en-us
document_id: 038d1287-8fea-c3f7-5c33-35a6c7d62924
document_version_independent_id: 038d1287-8fea-c3f7-5c33-35a6c7d62924
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-administrative-units.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-administrative-units
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-administrative-units.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 6a7e130c-67fe-8b2a-10ff-cb7072a094b0
---

# Using administrative units in Microsoft Teams - Microsoft Teams | Microsoft Learn

This article describes the highlights of Administrative Units for Teams administration using the Teams admin center and the Teams PowerShell module. Administrative Units are a way to delegate administrative tasks to a subset of users, groups, or devices using the Microsoft Entra Admin Portal.

You could previously manage Devices via Administrative Units, but only for the Teams Administrator role, as outlined in this article: [Manage devices with administrative units](administrative-unit).

With more capabilities enabled to be managed via Administrative Units, there's a need to cover the following usages:

## Set up Administrative Units

### Scenario One: Creation of Administrative Units in the Microsoft Entra admin center (AAD)

Full details on how to create Administrative Units can be found here (Administrative Unit administrators need a Microsoft Entra ID P1 or P2 license): [Create or delete Administrative Units - Entra ID](/en-us/entra/identity/role-based-access-control/admin-units-manage?tabs=ms-powershell).

### Scenario Two: Assignment and unassignment of RBAC roles to Administrative Units in the Microsoft Entra admin center (AAD)

Global Administrators can assign any of the following RBAC roles using the method in the adjacent column:

| RBAC Role | Assignment method | Documentation |
| --- | --- | --- |
| Teams administrator | Microsoft Entra admin center (UI)Teams PowerShellTeams Graph APIs | [Learn more](/en-us/graph/api/rbacapplication-post-roleassignments?view=graph-rest-1.0&amp;tabs=powershell#example-2--create-a-role-assignment-with-administrative-unit-scope) |
| Teams device administrator | Microsoft Entra admin center (UI)Teams PowerShellTeams Graph APIs | [Learn more](/en-us/graph/api/rbacapplication-post-roleassignments?view=graph-rest-1.0&amp;tabs=powershell#example-2--create-a-role-assignment-with-administrative-unit-scope) |
| Teams communication administrator | Microsoft Entra admin center (UI)Teams PowerShellTeams Graph APIs | [Learn more](/en-us/graph/api/rbacapplication-post-roleassignments?view=graph-rest-1.0&amp;tabs=powershell#example-2--create-a-role-assignment-with-administrative-unit-scope) |
| Teams communication support engineer | Microsoft Entra admin center (UI)Teams PowerShellTeams Graph APIs | [Learn more](/en-us/graph/api/rbacapplication-post-roleassignments?view=graph-rest-1.0&amp;tabs=powershell#example-2--create-a-role-assignment-with-administrative-unit-scope) |
| Teams communication support specialist | Microsoft Entra admin center (UI)Teams PowerShellTeams Graph APIs | [Learn more](/en-us/graph/api/rbacapplication-post-roleassignments?view=graph-rest-1.0&amp;tabs=powershell#example-2--create-a-role-assignment-with-administrative-unit-scope) |
| Teams telephony administrator | Microsoft Entra admin center (UI)Teams PowerShellTeams Graph APIs | [Learn more](/en-us/graph/api/rbacapplication-post-roleassignments?view=graph-rest-1.0&amp;tabs=powershell#example-2--create-a-role-assignment-with-administrative-unit-scope) |
| Teams Reader | Microsoft Entra admin center (UI)Teams PowerShellTeams Graph APIs | [Learn more](/en-us/graph/api/rbacapplication-post-roleassignments?view=graph-rest-1.0&amp;tabs=powershell#example-2--create-a-role-assignment-with-administrative-unit-scope) |

The role assignments listed in the table can also be applied directly to the intended users or groups. Learn more at [Use Microsoft Entra groups to manage role assignments - Microsoft Entra ID](/en-us/entra/identity/role-based-access-control/groups-concept).

## Roles and capabilities

| Management types | Teams Administrator | Device administrator | Teams Communication administrator | Teams Telephony administrator | Teams Communication support engineer | Teams Communication support specialist |
| --- | --- | --- | --- | --- | --- | --- |
| Teams management | NA | NA | NA | NA | NA | NA |
| User management | -Manage users list page-User details page--Account tab--Meetings and calls--Policies--Devices tab | NA | -Manage users list page-User details page--Account tab--Meetings and calls--Policies | -Manage users list page-User details page--Account tab--Meetings and calls-Policies | -Manage users list page-User details page--Meetings and calls | -Manage users list page-User details page--Meetings and calls |
| Devices management | The entire devices section (seven options) | The entire devices section (seven options) | NA | NA | NA | NA |
| Policy management | Option to only perform user or group policy assignments for the following policies:-Audio conferencing-Meeting-Customization-Live events-Events-Messaging-Calling-Call hold-Call park-Caller ID-Dial Plans-Emergency Calling & Call Routing-Shared Calling-Mobility-Voice routing-Voicemail-Voice applications | NA | Option to only perform user or group policy assignments for the following policies:-Audio conferencing-Meeting-Customization-Live events-Events-Calling-Call hold-Call park-Caller ID-Dial Plans-Emergency Calling & Call Routing-Shared Calling-Mobility-Voice routing-Voicemail-Voice applications | Option to only perform user or group policy assignments for the following policies: -Calling-Call Hold-Call park-Caller ID-Dial Plans-Emergency Calling & Call Routing-Shared Calling-Mobility-Voice routing-Voice mail-Voice applications | NA | NA |
| Voice management | Phone Number assignment – From User Details Page (Only Direct Routing numbers) | NA | Phone Number assignment – From User Details Page (Only Direct Routing numbers) | Phone Number assignment - From User Details Page (Only Direct Routing numbers) | NA | NA |
| Analytics and reporting management | -Usage reports (only PSTN reports)-Call quality dashboard (UII info redacted) | NA | -Usage reports (only PSTN reports)-Call quality dashboard (UII info redacted) | -Usage Reports (only PSTN reports) | Call quality dashboard (UII info redacted) | Call quality dashboard (UII info redacted) |
| Apps management | NA | NA | NA | NA | NA | NA |

## Individual feature areas

### Device management

As a scoped administrator with the Teams device admin or Teams administrator role, you can:

- Access the Devices section in Teams admin center and view the list of devices assigned to the users in the Administrative unit
- Filter, sort, and search the devices by various criteria.
- Select a device and view its details, configuration, and status.
- Perform actions on the device, such as restart, reset, update, or assign to a user.

Note

Export of devices isn’t available for scoped admin roles, you need to have tenant-wide permissions to export devices.

To learn more, see [Manage devices with administrative units](administrative-unit).

### User management

As a scoped administrator with the Teams administrator role or any of the Teams communication roles, you can:

- Filter, sort, and search the users by various criteria.
- Select a user and view their details, meetings, policies, and devices.
- Assign or unassign a Direct Routing phone number to a user in your Administrative Unit.
- Assign or unassign policies to a user in your Administrative Unit.
- Perform real-time or past meetings troubleshooting for a user in your Administrative Unit.

Note

Export of users isn’t available for scoped admin roles, you need to have tenant-wide permissions to export users.

### Policy management

As a scoped administrator with the Teams administrator role or any of the Teams communication roles, you can:

- Access the Policy sections in the Teams admin center and view the list of policies available in the tenant.
- Assign or unassign policies to a user or a group in your Administrative Unit.
- View the policy assignments and the effective policy for a user or a group in your Administrative Unit. Batch policy assignments are also enabled.

Note

For Teams group policy assignments, scoped administrators can assign policies to a nested group when a parent group is a member of their administrative unit. This permission does not change how policies propagate: a policy assigned to a group applies only to its direct user members, not to users in nested groups.

### Phone number management

As a scoped administrator with the Teams administrator role or any of the Teams communication roles, you can:

- Assign or unassign Direct Routing phone numbers to users in your Administrative Unit from the User Details page in the Teams admin center.

### Analytics and reporting management

As a scoped administrator with the Teams administrator role or any of the Teams communication roles, you can:

- Access the Usage reports section in the Teams admin center and view the reports (Only PSTN) scoped to the users in your Administrative Unit.
- Filter, sort, and export the reports by various criteria.
- Access the Call Quality Dashboard section in the Teams admin center and view the call quality data for the users in your Administrative Unit.

## Limitations for Administrative Units

Tasks that aren't available in this phase for a scoped administrator (regardless of the RBAC role), in either the Teams admin center or through the Teams PowerShell module:

- Teams and channel settings
- Audio conferencing, voice, and voicemail settings
- Auto Attendants, Call Queues & Resource Accounts
- Guest access
- External access
- Calling plan and Operator Connect number assignments
- Emergency addresses
- Teams apps
- Tenant level settings and conference bridges
- Policy packages
- Emergency addresses, network topology, networks, and locations
- Frontline teams and apps
- Teams advisor and network planner
- Rules

## Teams PowerShell and Administrative Units

The functionality outlined in this article is available for the RBAC roles using Teams PowerShell. The differences in PowerShell are:

- An admin assigned with multiple Admin units is able to manage all the users across each admin unit simultaneously.
- In the Teams admin center, the scoped admin would have to select the particular Administrative Unit and manage those users within the Administrative Unit at any given time.

An example of using Teams PowerShell and Administrative Units is:

- An organization has three branches: North, South, and East. North and South branches are assigned to a single admin, and East is assigned to another admin.
- The scoped admin assigned with North and South branches is able to manage all the users across both North and South simultaneously using Teams PowerShell.
- In the Teams admin center, the scoped admin can either manage the North or South branch in turn, but not both at the same time.