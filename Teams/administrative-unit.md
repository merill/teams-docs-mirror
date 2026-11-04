---
layout: Conceptual
title: Manage devices with administrative units - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/administrative-unit
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: ayerragangu
ms.date: 2026-07-15T00:00:00.0000000Z
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: itpro-devices
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
search.appverid: MET150
description: Learn how to use administrative units in Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
locale: en-us
document_id: 8a9a93a3-9abf-814a-909e-c6ab2575496b
document_version_independent_id: 3a1fcd15-d9d5-370b-9658-f95563c2d6f7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/administrative-unit.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: administrative-unit
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/administrative-unit.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 353e8d5e-85e9-a716-4c13-1cf0173a9f50
---

# Manage devices with administrative units - Microsoft Teams | Microsoft Learn

Important

Monitoring, managing, and updating Teams devices is moving to the Pro Management Portal. Review the transition guide [here](/en-us/microsoftteams/rooms/aboutunifieddevicemanagement-pmp1) to learn more and begin using the Pro Management Portal.

Administrative units in the Teams admin center provide detailed, role-based access for managing Teams devices. Administrative units grant Teams admin access to specific resources but limit that admin's access to other resources. This is especially helpful if you have local Teams admins in different countries or regions.

For example, Contoso has operations around the globe. Alice is a global IT admin based in London, while Prashant is a local IT admin based in Bengaluru (Bangalore), India. Today, when Prashant signs into the Teams admin center as a device administrator, he can see Teams devices around the globe. Alice wants to limit Prashant's access to Teams devices only in Bengaluru (Bangalore). Administrative units let her do this. To learn more, see [Administrative units in Microsoft Entra ID](/en-us/azure/active-directory/roles/administrative-units).

Note

Administrative Units can be managed using the Teams Administrator or Teams Device Administrator roles. Administrative units are currently available in the Teams admin center only for the Teams devices administrator role.

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Add administrative units

You need to be a global admin to add administrative units. To learn how, see [Add an administrative unit](/en-us/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## Assign admins to administrative units

You'll also need to be global admin to assign administrative units. You can assign administrative units using Azure portal, PowerShell, or the Microsoft Graph API. To learn more, see [Assign Microsoft Entra roles with administrative unit scope](/en-us/azure/active-directory/roles/admin-units-assign-roles).

## Select administrative units

If you're a Teams devices admin, after a global admin assigns you to an administrative unit, you can sign into the Teams admin center to manage devices. If you're assigned to only one administrative unit, you'll see only the devices that are assigned to that administrative unit. If you're assigned to multiple administrative units, you can switch between those administrative units without signing out from the Teams admin center.

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. In the **Your administrative units** dialog box, follow one of these steps:

    - Select the administrative unit that you want to manage, or
    - Select **All devices** if you have permission to manage all devices for your organization.
3. Select **Save**.

## Switch administrative units

If you're a Teams devices admin, you can switch between administrative units if you're signed into the Teams admin center. To switch to a different administrative unit:

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. In the left navigation, select **Teams devices**.
3. On the right pane, at the upper left, select the administrative unit shown.
4. In the **Your administrative units** dialog box, follow one of these steps:

    - Select the administrative unit that you want to manage, or
    - Select **All devices** if you have permission to manage all devices for your organization.
5. Select **Save**.