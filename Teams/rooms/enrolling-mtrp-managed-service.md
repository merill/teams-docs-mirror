---
layout: Conceptual
title: Accessing the Pro Management portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service
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
ms.date: 2026-09-28T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about how to access the Microsoft Teams Rooms Pro Management portal.
f1keywords: 
locale: en-us
document_id: 5f92b3e4-3b95-271d-6926-f31704caae5f
document_version_independent_id: 8089fb49-82fe-3e20-1ae6-6b98bf2b2516
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/enrolling-mtrp-managed-service.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/enrolling-mtrp-managed-service
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/enrolling-mtrp-managed-service.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ead2e6d3-99fa-3306-063d-83d3d5428766
---

# Accessing the Pro Management portal - Microsoft Teams | Microsoft Learn

To access the Teams Rooms Pro Management portal, you need to assign one or more users to the below roles:

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

1. **Microsoft Entra built-in roles:** Global Administrator, Teams Administrator, Teams Devices Administrator, Global Reader. [Assign Microsoft Entra built-in roles](/en-us/entra/identity/role-based-access-control/permissions-reference) to the users using the [Microsoft Entra Admin center](https://entra.microsoft.com/#home).
2. Direct roles assignment within the Teams Rooms Pro Management Portal.

Note

A Teams Administrator or a Teams Devices Administrator assigned to an Administrative Unit (AU), won't able to access Teams Rooms Pro Management portal, as AUs aren't yet supported. In such cases, consider assigning the users to the Teams Rooms Pro Management built-in roles (**Teams Rooms Pro Manager**, **Site Lead**, and **Site Technician**) or create a custom role. Check [Role Based Access Control](/en-us/microsoftteams/rooms/rooms-pro-rbac) for more information.

## How to assign users to the Teams Rooms Pro Manager role

Complete the following steps to assign users to the Teams Rooms Pro Manager role:

1. Log in to the [Teams Rooms Pro Management portal](https://portal.rooms.microsoft.com/) (GCC-High customers use [this link](https://devices.gov.teams.microsoft.us/)) using the administrator privileges outlined in this document.
2. Navigate to **Settings** &gt; **Roles** and then select **Teams Rooms Pro Manager**.
3. Under **Teams Rooms Pro Manager**, select the **Assignments** tab and then select **Add**.
4. Follow the wizard to name the assignment and select the users who should be added to it. The assignment will apply to all rooms and room groups.
5. At the end of the assignment wizard, select **Add assignment**.

Users who are assigned to the above-mentioned Microsoft Entra built-in roles or to the Teams Rooms Pro Manager role are responsible for the day-to-day management and monitoring of Teams Rooms and will have access to all rooms and features within the Teams Rooms Pro management portal. To assign additional roles to restrict access to specific rooms and users, see more under [Role Based Access Control](/en-us/microsoftteams/rooms/rooms-pro-rbac).

After you've assigned users to the Teams Rooms Pro Manager role, continue to the [Enroll a Teams Rooms device](enroll-a-device) to add a Teams Rooms device to the Teams Rooms Pro management portal.