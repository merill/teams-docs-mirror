---
layout: Conceptual
title: Upgrade from the Teams Exploratory trial - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/upgrade-from-teams-exploratory
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
audience: admin
ms.reviewer: 
ms.date: 2025-02-27T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
ms.localizationpriority: high
description: Upgrade users from a Teams Exploratory trial to a paid license.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
- tier1
ms.custom:
- admindeeplinkMAC
locale: en-us
document_id: 1d0c5469-4130-dde1-c1f3-15e8f27404b8
document_version_independent_id: 6ed3741e-4af5-1c2d-374a-1a19e57b3862
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/upgrade-from-teams-exploratory.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: upgrade-from-teams-exploratory
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/upgrade-from-teams-exploratory.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4eba0ec2-17e2-1883-7e3f-0b7feac165f9
---

# Upgrade from the Teams Exploratory trial - Microsoft Teams | Microsoft Learn

This article provides an overview of how to upgrade your users from a Teams Exploratory trial to paid Teams licenses.

- Step 1: When to upgrade
- Step 2: Choose an upgrade path
- Step 3: Assign paid licenses

Note

Currently, only self-service Teams Exploratory trials are available.

To see if you have users with a Teams Exploratory license, you can go to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) &gt; **Billing** &gt; **Licenses** &gt; and scroll to see if **Microsoft Teams Exploratory** is listed. If it's listed, you have users with a Teams Exploratory license.

## Step 1: When to upgrade

To check when your organization’s Teams Exploratory trial is expiring and how many active users it has, sign into the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and go to **Billing** &gt; [**Your products**](https://go.microsoft.com/fwlink/p/?linkid=842054). You're also notified before the Teams Exploratory trial expires.

Caution

You should make a plan to upgrade your users to paid licenses before the expiration date, so users don’t lose access to Teams.

If a user doesn't have separate SharePoint or OneDrive licenses and their Teams Exploratory license ends, they lose access to Teams, OneDrive, and SharePoint until a Teams license is assigned. If a OneDrive or SharePoint license is assigned after the Teams Exploratory trial ends, they will still have access to their data, even if a Teams license is not assigned. After 30 days, associated Teams, OneDrive, and SharePoint data will be deleted if appropriate licenses are not assigned. The user will still exist in Microsoft Entra ID. If users are assigned an appropriate license within the 30 days, their content will still exist and will be available to them.

For more information, see [What happens to my data and access when my subscription ends?](/en-us/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires).

## Step 2: Choose an upgrade path

Tip

We recommend Teams Essentials as the primary option for customers looking to upgrade their expiring Teams Exploratory trials. For more information, see [Compare Microsoft Teams Essentials to other plans](get-started-with-teams-essentials#how-does-microsoft-teams-essentials-compare-to-other-microsoft-teams-plans).

Depending on the subscriptions your organization currently has, there are several ways to upgrade from a Microsoft Teams Exploratory trial to a paid license:

- **Upgrade an existing Microsoft 365 subscription.** Use this option if your organization has subscriptions to other Office products that don’t include Teams. For more information, see [Upgrade to a different business plan](/en-us/microsoft-365/commerce/subscriptions/upgrade-to-different-plan).

    - To see active users for an existing subscription, sign into the [Microsoft admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and go to **Users** &gt; [**Active users**](https://go.microsoft.com/fwlink/p/?linkid=834822).
- **Add users to an existing Microsoft 365 subscription.** Use this option if your organization doesn’t have enough paid Teams licenses to cover the Teams Exploratory users. For more information, see [Buy or remove licenses](/en-us/microsoft-365/commerce/licenses/buy-licenses).

    - To add users to an existing subscription that already has enough available licenses, see [Move users to a different subscription](/en-us/microsoft-365/commerce/subscriptions/move-users-different-subscription).
    - To see active users for an existing subscription, sign into the [Microsoft admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and go to **Users**[**Active users**](https://go.microsoft.com/fwlink/p/?linkid=834822).
- **Buy a new Microsoft 365 subscription.** Use this option if your organization doesn’t have any existing subscriptions to Office products, or if your organization wants to buy a subscription that’s different from their existing subscription to cover Teams Exploratory users. For more information, see [Buy a different Microsoft 365 for business subscription](/en-us/microsoft-365/commerce/try-or-buy-microsoft-365#buy-a-different-subscription).
- **Move users to a new license.** Only customers who have users with the self-service Teams Exploratory trial can use this method.

    - Sign in to the [Microsoft admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and go to **Billing** &gt; **Your products** &gt; **Microsoft Teams Exploratory Trial**. Choose the users you need to move. Select the **Move** button in the actions bar, and then select a subscription to move those users to.

If you’re not sure which Microsoft 365 subscription to upgrade to, see [Microsoft 365 for Business](https://www.microsoft.com/microsoft-365/business#coreui-heading-hiatrep). If you need more help choosing a subscription, or if your organization needs more than 300 licenses, contact your [Microsoft partner](https://www.microsoft.com/solution-providers/home) or Microsoft account representative.

## Step 3: Assign paid licenses

Important

Before you unassign any Teams Exploratory licenses, assign the new licenses to all the users you’re upgrading. Otherwise, they lose access to Teams until you assign a paid license.

To assign your newly acquired licenses, see [Assign licenses to users](/en-us/microsoft-365/admin/manage/assign-licenses-to-users).

After you assign the new licenses, unassign the Teams Exploratory licenses. For more information, see [Unassign licenses from users](/en-us/microsoft-365/admin/manage/remove-licenses-from-users).

### Auto-claim policies

Next time you upgrade, use auto-claim policies to automatically assign licenses from paid subscriptions to new users without a Teams license. For more information, see [Manage auto-claim policies](/en-us/microsoft-365/commerce/licenses/manage-auto-claim-policies).