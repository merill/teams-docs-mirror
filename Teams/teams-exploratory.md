---
layout: Conceptual
title: Manage the Microsoft Teams Exploratory license - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-exploratory
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
audience: Admin
ms.reviewer: janebo
ms.date: 2026-07-16T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
ms.localizationpriority: high
description: Microsoft 365 or Office 365 users who aren't licensed for Microsoft Teams can initiate an Exploratory Teams license.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
- tier1
ms.custom:
- admindeeplinkMAC
locale: en-us
document_id: 28550025-fde2-9a83-a826-f7e3ccb313db
document_version_independent_id: 2a304432-b10c-220f-3453-e19e7a155c67
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-exploratory.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-exploratory
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-exploratory.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9d717a06-30e5-8c57-2dcc-60fa796a8117
---

# Manage the Microsoft Teams Exploratory license - Microsoft Teams | Microsoft Learn

The Microsoft Teams Exploratory experience lets users in your organization who have Microsoft Entra ID and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.

## What's in the Teams Exploratory experience

The service plans that an admin sees as part of the Teams Exploratory experience are:

- Exchange Online (Plan 1)
- Power Automate
- Microsoft Viva Insights
- Microsoft Forms (Plan E1)
- Microsoft Planner
- Microsoft Search
- Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs
- Microsoft Teams
- Mobile Device Management for Microsoft 365 or Office 365
- Office Mobile Apps for Office 365
- Office Online
- Power Apps for Microsoft 365 or Office 365
- SharePoint Online (Plan 1)
- Sway
- To-Do (Plan 1)
- Whiteboard (Plan 1)
- Viva Engage

## Who's eligible

Users fit the criteria for a Teams Exploratory experience if they:

- Have a managed Microsoft Entra domain email address.
- Belong to a tenant with a paid subscription.
- Don't have an active Teams license.
- Aren't in a tenant where a license assignment policy was created.

Admins must allow users to sign up for apps and trials in the Microsoft 365 admin center. For more information, see Manage the Teams Exploratory experience, later in this article.

## Who isn't eligible

Users don't fit the criteria if they:

- Currently have Teams from a paid license or trial license, or previously had a trial license.
- Are in a tenant that used or received at least one special COVID offer.

Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or Education customer.

## How users sign up for the Teams Exploratory experience

Eligible users can sign up for the Teams Exploratory experience by signing into Teams from the desktop or web at https://teams.microsoft.com. When they sign up, they're assigned this license automatically, and the tenant admin receives an email notification the first time someone in your org starts the Teams Exploratory experience.

## Manage the Teams Exploratory experience

Note

Currently, only self-service Teams Exploratory trials are available. To see if you have users with a Teams Exploratory license, you can go to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) &gt; **Billing** &gt; **Licenses** &gt; and scroll to see if **Microsoft Teams Exploratory** is listed. If listed, you have users with a Teams Exploratory license. The Teams Exploratory experience is initiated by individual end users. You can't initiate this offer on behalf of end-user employees.

Admins can turn off the ability for end users to run the Teams Exploratory experience within their organization. For more information, see Prevent users from installing trial apps and services.

### Service plan assignment

The Teams Exploratory experience comes with an Exchange Online license, but it will not be assigned to the user until the admin assigns it.

- If the user doesn't have an Exchange or Exchange Online license, the user will not be able to schedule meetings in Teams and might miss other Teams functionality.
- If the user already has an Exchange Online license assigned to them, and then signs up for the Teams Exploratory license, their Exchange Online plan will be turned off. The admin needs to turn the plan back on in the Microsoft 365 admin center.

    1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
    2. Select **Billing** from the left-side navigation.
    3. Select **Licenses** from the menu.
    4. On the **Licenses** page, find and select the users.
    5. Select **Manage apps & services** on the actions bar.
    6. On the **Manage apps & services** pane, turn on **Exchange Online** by selecting the checkbox.
    7. Select **Save**.

### Prevent users from installing trial apps and services

You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.

#### If your users have the self-service Teams Exploratory trial

If your tenant has users with the self-service Teams Exploratory trial, you need to use PowerShell to turn off a user's ability to install trial apps and services, even if trials were previously turned off.

For instructions on how to turn off and on users' ability to install trial apps and services, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](/en-us/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell), which allows you to manage your end-user settings in the admin center, or you can use the MSCommerce PowerShell script.

### Manage availability for a user with a license that includes Teams

A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is turned off, the user can't sign in, and the Teams Exploratory experience isn't available. You must have admin privileges.

To turn off access to Teams:

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Users** &gt; **Active users**.
2. Find and select the user.
3. In the user pane, select the **Licenses and apps** tab.
4. Unselect the checkbox for the **Microsoft Teams** license.
5. Select **Save changes**.

### Manage Teams availability for users who are already using the Teams Exploratory experience

If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges, and users must be on the tenant-based trial license.

To turn off the Teams Exploratory experience license:

1. In the Microsoft 365 admin center, select **Users** &gt; **Active users**.
2. Find and select the user.
3. In the user pane, select the **Licenses and apps** tab.
4. Unselect the checkbox for the Teams Exploratory license.
    1. The Teams Exploratory box will appear after the first user in the organization launches the Teams Exploratory experience.
5. Select **Save changes**.

### Manage Teams for users who have the Teams Exploratory license

You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365).

### Upgrade users from Teams Exploratory

You must have admin privileges to move users from a Teams Exploratory license to a paid Teams license. For more information, see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory).

If you have tenant-based organizational Teams Exploratory licenses, you can cancel users' Teams Exploratory licenses. For more information, see Remove a Teams Exploratory license.

Caution

If a user doesn't have separate SharePoint or OneDrive licenses and their Teams Exploratory license ends, they lose access to Teams, OneDrive, and SharePoint until a Teams license is assigned. If a OneDrive or SharePoint license is assigned after the Teams Exploratory trial ends, they will still have access to their data, even if a Teams license isn't assigned. After 30 days, associated Teams, OneDrive, and SharePoint data will be deleted if appropriate licenses aren't assigned. The user still exists in Microsoft Entra ID. If users are assigned an appropriate license within the 30 days, their content still exists and will be available to them.

### Remove a Teams Exploratory license

You can only remove users' Teams Exploratory licenses if they're tenant-based organizational licenses.

- If you would like to remove this license by using PowerShell, see [Remove licenses from user accounts with Office 365 PowerShell](/en-us/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).
- If you would like to remove this license through the admin portal, see [Delete a user from your organization](/en-us/microsoft-365/admin/add-users/delete-a-user).

## What is the data retention policy

To learn about Microsoft's data retention policy, see [Microsoft 365 subscription information](/en-us/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires).

## How long does the Teams Exploratory experience last

The Teams Exploratory trial period for Enterprise Agreement (EA) and non-Enterprise Agreement customers is 1 month.

The self-service trial period begins when a user signs up for Teams Exploratory. The expiry date is determined per-user. Each user has a unique expiry date depending on the length of trial period they qualify for and when they sign up.

### What should administrators do at the end of the trial Teams Exploratory experience

At the end of the trial period, administrators should convert all Teams Exploratory users to a paid license that includes Teams. It's vital to ensure this action is completed before the Teams Exploratory subscription expires to avoid any disruption to users' experience.

Note

Customers would be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.

For more information, see Upgrade users from Teams Exploratory, above in this article.