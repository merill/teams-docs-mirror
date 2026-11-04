---
layout: Conceptual
title: Assign Microsoft Teams licenses for education - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-edu-licensing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: reference
ms.service: msteams
ms.subservice: teams-education
audience: admin
ms.reviewer: 
ms.date: 2020-03-05T00:00:00.0000000Z
description: Learn how to assign licenses for Microsoft Teams for Education.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- tier1
ms.custom:
- admindeeplinkMAC
locale: en-us
document_id: af87d2a8-11f7-5384-0b2e-c1825f591347
document_version_independent_id: 501c7bff-cbf6-0288-d533-8f31dfc296a6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-edu-licensing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-edu-licensing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-edu-licensing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: accb8801-dd26-df8f-9d56-34ce768a15a3
---

# Assign Microsoft Teams licenses for education - Microsoft Teams | Microsoft Learn

This article is for IT admins in education who need to assign Team licenses to their faculty, staff, and students.

To get your users ready for Teams, you'll need to:

1. [Enable Microsoft Teams for your school in the Microsoft 365 admin center](/en-us/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
2. Assign licenses to user accounts for access to Microsoft 365 services, including Teams.

## Ways to assign Teams licenses

You can assign licenses to user accounts either:

- Individually or to a small group of users in the Microsoft 365 admin center.
- Automatically through group membership using [PowerShell](/en-us/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) or [Active Directory group-based licensing](/en-us/azure/active-directory/users-groups-roles/licensing-groups-assign).

This article will walk you through how to assign licenses in the Microsoft 365 admin center.

In the Microsoft 365 admin center, you can assign licenses to users on either:

- The **Licenses** page to assign product licenses to specific users.
- The **Active Users** page to assign users' licenses to specific products.

Note

You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](/en-us/microsoft-365/admin/add-users/about-admin-roles).

## Assign licenses to users on the Licenses page

On the **Licenses** page, you see a list of all the products you have subscriptions for, the total number of licenses for each product, how many licenses are assigned, and how many are available.

1. In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to the **Billing** &gt; [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.
2. Select a product for which you want to assign licenses. Microsoft Teams is part of the free Microsoft 365 A1 for Students SKU.
3. Select **Assign licenses**.
4. In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.
5. Choose the name you're looking for from the results to add it to the list. You can add up to 20 users at a time.
6. Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams. Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.
7. When you're finished, select **Assign**, then select **Close**.

### Change the apps and services a user has access to

1. Select the row that contains the user.
2. In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.
3. When you're finished, select **Save**, then select **Close**.

## Assign licenses to users on the Active users page

1. In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to the **Users** &gt; [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.
2. Select the circles next to the name(s) of the user(s) you want to assign license(s) to.
3. At the top, select **Manage product licenses**.
4. In the **Manage product licenses** pane, select **Add to existing product license assignments** &gt; **Next**.
5. In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have. Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.

    By default, all services associated with those license(s) are automatically assigned to the user(s). You can limit which services are available to the users. Switch the toggles to the **Off** position for the services that you don't want the users to have.
6. At the bottom of the pane, select **Add** &gt; **Close**.