---
layout: Conceptual
title: Purchase third-party apps and manage subscriptions and licenses - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/purchase-third-party-apps
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: SerdarSoysal
ms.author: serdars
manager: prkosh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 2024-09-19T00:00:00.0000000Z
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: shruti.dhir
f1keywords: 
description: Learn how to purchase paid app licenses in Teams store using a credit card, a debit card, or via invoice billing.
ms.localizationpriority: medium
locale: en-us
document_id: 238a2222-3d53-dfa2-6d06-e69bc16daaa0
document_version_independent_id: 65bc6c34-447b-72dc-2155-eaa44a4aba00
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/purchase-third-party-apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: purchase-third-party-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/purchase-third-party-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 96040d18-7d54-33de-ca3f-bd61a11aadef
---

# Purchase third-party apps and manage subscriptions and licenses - Microsoft Teams | Microsoft Learn

Some Teams apps require purchasing a service subscription to use app functionality. These service subscriptions are called Software as a Service (SaaS) offers. A license is available for purchase from [AppSource](https://appsource.microsoft.com) and in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).

Paid apps require users to authenticate to prevent unwarranted access. Also, user sign-in is required to check for entitlement and to make the corresponding app functionality available for the logged-in user. For authentication, app developers can use single sign-on (SSO) using Microsoft Entra ID or use third-party OAuth Identity Provider. The authentication mechanism is similar for Teams or web apps. For more information, see [How apps authenticate users](/en-us/microsoftteams/platform/concepts/authentication/authentication).

You can purchase licenses for services offered by third-party apps from the Manage apps page in the Teams admin center. The **Licenses** column in the table indicates if an app offers a SaaS subscription for purchase. You can purchase apps using a credit card, debit card, or with invoice billing.

[![Screenshot showing the purchase licenses option on the manage apps page in Teams admin center.](media/manage-apps-new-page.png)](media/manage-apps-new-page-large.png#lightbox)

## Purchase apps in the Teams admin center

To purchase an app in Teams admin center, follow these steps:

1. Sign in to the Teams admin center and access **Teams apps** &gt; **[Manage apps](https://admin.teams.microsoft.com/policies/manage-apps)**. You must be a Teams Administrator to access the page.
2. You can search for an app by its name. To check if an app offers a paid SaaS subscription, see the **Licenses** column. Each app has one of the following values:

    - **Purchase**: The app offers a SaaS subscription and is available to purchase.
    - **Purchased**: The app offers a paid SaaS subscription and you have the licenses for the app.
    - **- -**: The app doesn't offer a SaaS subscription.
3. Select **Purchase** on the Manage apps page to open the **Plans and pricing** tab on the app details page. You can review the plans and pricing information available in admin center. You can select **Learn more** link to go to the app's page on [AppSource](https://appsource.microsoft.com/).

    ![Screenshot showing paid plans of an app in the Teams admin center.](media/app-plans-pricing.png)
4. To subscribe to an app, choose the plan you want, and select **Buy**. The checkout dialog opens.

    Note

    Some apps may have a **Private plan**. Private plans are special pricing that your organization can separately negotiate with an app developer.
5. On the checkout screen, select the number of user licenses that you want to buy.

    ![Screenshot showing the checkout dialog to select the number of licenses when an admin purchases an app.](media/subscription-quantity.png)
6. Under **Billing account**, provide the name and billing details and select **Next**.

    ![Screenshot showing the billing account name and address when admins purchase an app.](media/app-purchase-billing-details.png)
7. Under **Verify your address**, select the address and select **Next**.

    ![Screenshot showing the billing address verification dialog when admins purchase an app.](media/app-purchase-verify-address.png)
8. Under **Add a credit or debit card**, add the required details and select **Next**. By default, the **Same as billing address** checkbox is selected to use the billing account’s address for the card. To add a new address, clear the checkbox and enter the address.

    ![Screenshot showing the payment dialog with credit card details when admins purchase an app.](media/app-purchase-credit-card.png)
9. Under **Review**, verify the details and select **Place order**.
10. Select **Set up subscription** to activate your subscription on the app developer's website. If you don't set up your subscription after your purchase, you can do it later.

After you purchase the SaaS offer associated with a Teams app, you can view the following purchase details on the **Plans and subscriptions** tab of the app details page.

- **License activation date**: Date on which your license was activated.
- **Licenses**: Number of licenses you have.

Select **Manage subscriptions** to view and manage the licenses you already have.

Global Administrators can view the subscriptions purchased by anyone in the organization. They can add more licenses, remove licenses, and cancel subscriptions for purchases made by anyone in their billing account. Teams Administrators can perform the same actions for purchases made by them but not for the purchases made by other admins.

Note

If a Global Administrator wants to manage a subscription purchased by another Global Administrator, they need to be in the same billing account. You can give another Global Administrator access to a subscription you purchased by selecting the app in the [Microsoft 365 admin center](https://admin.microsoft.com). In admin center, access **View billing profile** &gt; **Select billing account** &gt; **Assign roles** &gt; **Add other Global admins**.

Important

When you enable app purchasing, it also turns on in-app purchasing. Users may see in-app purchase offers that app developer control. To prevent users from making in-app purchases, you can block the app.

### Invoice billing

- Invoice billing is available as a payment option for some transactions.
- A credit review is required the first time you use invoice billing, which can take up to 24 to 48 hours for approval. Invoice billing isn't available until the credit check is complete. You can place your order with a credit card or try again later after your credit review is approved.
- Invoice billing is only available for an admin account that has Teams Administrator and Billing Administrator role.
- Invoice billing isn't available when purchasing a plan with a 30-day free trial.

## Manage subscriptions in Teams admin center

In Teams admins center, you can manage the app subscriptions and licenses you purchased. You can view the list of app subscriptions and their details and perform the following actions:

- Change a plan
- Buy or remove license
- Update a payment method
- Cancel a subscription
- View your invoice

[![Screenshot of subscription details of an app.](media/manage-existing-subscriptions-actions.png)](media/manage-existing-subscriptions-all.png#lightbox)

To manage subscriptions, follow these steps:

1. Sign in to Teams admin center and access **Teams apps** &gt; [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps).
2. Select the **Subscriptions** tab to view the subscriptions you purchased.

    [![Screenshot of subscription option for an app in the manage apps page.](media/subscription-options-in-manage-apps.png)](media/manage-app-subscriptions-manage-apps.png#lightbox)

Note

In Teams admin center, you can manage the app subscriptions purchased by you or other admins who are part of the same billing account. To view all the app subscriptions purchased for the same tenant by other admins or purchased using different billing accounts, visit the [Microsoft 365 admin center](https://admin.microsoft.com/adminportal/home#/homepage).

## List and sell a SaaS offer for a Teams app

Developers can create SaaS offers associated with their Teams apps. These offers are published through [Partner Center](https://partner.microsoft.com) and are available for organizations to purchase through [AppSource](https://appsource.microsoft.com/) and the Microsoft Teams admin center.

For more information for third-party app developers, see [Create a SaaS offer](/en-us/azure/marketplace/partner-center-portal/create-new-saas-offer).

## Manage app licenses in Teams admin center

Microsoft Teams lets admins manage licenses for SaaS app offers. It enables admins to easily buy, assign, track, and remove SaaS app licenses purchased in Teams. It helps utilizing the available resources effectively.

As an administrator, it's important to understand how licenses work and how to manage them effectively. For apps that are purchased with a set number of subscription licenses, you have to ensure that these licenses are being utilized properly.

You can perform the following tasks to manage the licenses:

- **Assign license to users** to assign an app subscription license to an individual or multiple users.
- **Assign license to a team** when you need to assign an app subscription license to a team.

### Assign a license to a user

You can assign a license to one or more users in your tenant. To view and assign the licenses for an app:

1. Sign in to the Teams admin center and go to **Teams apps** &gt; **[Manage apps](https://admin.teams.microsoft.com/policies/manage-apps)**.
2. To view the licenses, select an app. The app details page shows the number of licenses available for the app on the **Licenses** tab.

    ![Screenshot that shows the purchased licenses of an app.](media/purchased-licenses.png)
3. To view the license utilization and assign licenses, select **Assign licenses**. The assign licenses window appears.

    [![Screenshot that shows the Assign licenses dialog to select the user name.](media/assign-licenses.png)](media/assign-licenses1.png#lightbox)
4. Search and select the users and select **Assign**.

### Assign a license to a team

To manage licenses across multiple users who are part of the same team, you can select a team from the list of available options. The number of members in the team must be smaller than the number of licenses available for the app. To assign a license to a team, follow these steps:

1. Sign in to the Teams admin center and go to **Teams apps** &gt; **[Manage apps](https://admin.teams.microsoft.com/policies/manage-apps)**.
2. Under **All apps**, select the app to assign its licenses to a team.
3. In the **Licenses** tab, select **Assign licenses**.

    [![Screenshot that shows the Assign licenses dialog with the list of teams to assign license.](media/assign-licenses-group.png)](media/assign-licenses-group1.png#lightbox)
4. Search and select the team, and select **Assign**.

    After you assign licenses to the users or team, you can view the list of assigned users. This list allows you to view a mapping of licenses and assigned users.

    [![Screenshot that shows list of assigned users to remove the licenses.](media/remove-licenses.png)](media/remove-licenses1.png#lightbox)

## Disable app purchases in Teams admin center

To prevent users from purchasing third-party apps, you can disable purchases using the MSCommerce PowerShell module. You can view a list of applicable apps and whether self-service purchase is enabled or disabled, using `AllowSelfServicePurchase` parameter. For more information, see [Use AllowSelfServicePurchase to disable Teams app purchases](/en-us/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell). The change applies to all users in your organization.