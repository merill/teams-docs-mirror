---
layout: Conceptual
title: Manage - Resource accounts for voice applications - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-manage-resource-accounts
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-08-31T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to learn how to manage resource accounts.
description: Learn how to manage resource accounts for voice applications, including licensing changes, deletion, and hiding accounts from Teams users.
locale: en-us
document_id: 81fa6268-92b2-546f-9200-f323bb48e90e
document_version_independent_id: 6ce89bc0-ae69-b6f1-df50-532e46b2e67b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-manage-resource-accounts.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-manage-resource-accounts
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-manage-resource-accounts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: f97e19fb-5f9d-47d0-0beb-0af3f1218e4f
---

# Manage - Resource accounts for voice applications - Microsoft Teams | Microsoft Learn

In Microsoft Teams, a resource account is required for each auto attendant or call queue. Resource accounts may also be assigned telephone numbers. This article describes how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.

Note

Resource accounts used for auto attendants and call queues are disabled for sign in and must remain so. Chat and presence aren't available and won't work for these accounts. Even though presence still appears, it won't change. This article covers how to create resource accounts and ready them for use with auto attendants and call queues.

Before you start the procedures in this article, ensure completion of the following steps:

- Obtain Microsoft Teams Phone Resource Account licenses
- Obtain phone numbers
- Assign permissions for managing a resource account

### Obtain Microsoft Teams Phone Resource Account licenses

Each resource account requires a license in order to work with auto attendants and call queues, known as a **Microsoft Teams Phone Resource Account** license. Subscriptions with Teams Phone have access to a zero-cost allocation of **Microsoft Teams Phone Resource Account** licenses, and if more are needed, extra **Microsoft Teams Phone Resource Account** licenses can be purchased at a cost. For details on how to obtain these licenses, see [Microsoft Teams Phone Resource Account licenses](teams-add-on-licensing/virtual-user).

We cover how to assign the license to a resource account later in this article.

If you purchased **Teams Phone Standard**, **Teams Phone with Calling Plan**, or **Teams Shared Devices** licenses, you still need to complete the purchasing process for your allocation of **Teams Phone Resource Account** licenses, but your allotment of licenses is zero cost at checkout.

To see if you already have **Teams Phone Resource Account** licenses in your tenant, sign into the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) using an account with Global admin permissions. Then, go to [Billing &gt; Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions). If you have **Teams Phone Resource Account** licenses, they appear as **Microsoft Teams Phone Resource Account**.

1. Open the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and sign in with a user that is a Global admin. This is usually the account you used to sign up for Microsoft 365.
2. In the left navigation pane, go to [**Billing** &gt; **Purchase services**](https://admin.microsoft.com/Adminportal/Home#/catalog) &gt; **Add-ons**.
3. Scroll to find the **Microsoft Teams Phone Resource Account** license.
4. Select the **Details** button.
5. Choose the number of licenses you want to purchase and a billing frequency.
    1. You need one license for each auto attendant and call queue you plan to set up. We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.
6. Select the **Buy** button.
7. Fill in the purchasing details.
8. Confirm your order details, and then select the **Place order** button.

There's zero cost for your allotment of licenses, but you still need to follow these steps to acquire the licenses.

### Obtain phone numbers

Phone numbers are optional for auto attendants and call queues. For any auto attendant or call queue that you want to be reachable directly by a phone number, you must have a resource account with an associated phone number.

Resource accounts can use either toll or toll-free phone numbers. You can request new numbers or port existing numbers from another carrier.

Acceptable phone numbers that can be applied to resource accounts include:

- **Calling Plans service numbers:** To acquire service numbers with Calling Plans, see [Getting service phone numbers](getting-service-phone-numbers).
- **Direct Routing numbers:** To acquire Direct Routing numbers, see [Enable users for Direct Routing](/en-us/microsoftteams/direct-routing-enable-users#configure-the-phone-number-and-enable-enterprise-voice).
- **Operator Connect numbers:** To acquire Operator Connect numbers, see [Configure Operator Connect](/en-us/microsoftteams/operator-connect-configure#set-up-phone-numbers).

Note

Resource accounts with Direct Routing phone numbers with or without extensions are supported. Currently, the Teams admin center only supports assigning Direct Routing phone numbers without extensions. To assign a Direct Routing phone number with an extension to a resource account, use the Teams PowerShell cmdlet [Set-CsPhoneNumberAssignment](/en-us/powershell/module/teams/set-csphonenumberassignment).

To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams).

## Assign permissions for managing a resource account

Important

Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role. To learn more, see [About Admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles).

To create and manage a resource account, admins must have two roles - a **Teams administrator** role and the **User Administrator** role.

An admin needing to create resource accounts needs one of the following Teams administrator roles:

- Teams Telephony Administrator
- Teams Communications Administrator
- Teams Administrator

Note

Currently, when *editing* a resource account, the admin must be assigned either the Global Admin role or the Skype for Business Administrator and User Administrator roles.

You can edit a resource account in the Teams admin center or with PowerShell.

The User Administrator role is a built-in role in Microsoft 365 that grants permissions to create and manage user accounts. For more information, see [Assign admin roles in Microsoft 365](/en-us/microsoft-365/admin/add-users/assign-admin-roles).

If a user has a Teams administrator role without the User Administrator role, you must assign the User Administrator role to provide the necessary permissions to create user accounts.

A Global Administrator also has the necessary Teams and User permissions to create and manage resource accounts, but we recommend using roles with the fewest permissions.

For more information about Teams administrator roles, see [Use Microsoft Teams administrator roles to manage Teams](/en-us/microsoftteams/using-admin-roles).

Note

Currently, Teams administrators can create and manage resource accounts *without* requiring **user administrator** permissions in Microsoft 365. As part of our commitment to deliver secure solutions that meet the highest standards, we are implementing changes to the management of resource accounts. Going forward, Teams administrators will need to have user management permissions in Microsoft 365 to create and manage resource accounts. This change will start to roll out to customers in the 4th quarter of 2024 and continue through the 1st quarter of 2025.

## Create a resource account

Before creating a resource account, you must assign permissions for creating and managing a resource account.

### Teams admin center

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Expand **Voice**, and then select **Resource accounts**.
3. Select **Add**.
4. In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**. The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.
5. Select **Save**.

### PowerShell

You can create a resource account with the PowerShell cmdlet, [New-CsOnlineApplicationInstance](/en-us/powershell/module/teams/new-csonlineapplicationinstance).

## Edit a resource account

Before editing a resource account, you must assign permissions for creating and managing a resource account.

Note

Currently, when *editing* a resource account, the admin must be assigned either the Global Admin role or the Skype for Business Administrator and User Administrator roles.

### Teams admin center

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Expand **Voice**, select **Resource accounts**, and select the resource account.
3. Select **Edit**.
4. In the **Edit resource account** pane, you can edit **Display name**, **Resource account type**, and **Voice routing policy**. By choosing a Voice routing policy, you're assigning that policy to the resource account. For more information on call routing policies, see [Managing call routing policies for direct routing](manage-voice-routing-policies)
5. Select **Save**.

### PowerShell

You can edit a resource account with the PowerShell cmdlet, [Set-CsOnlineApplicationInstance](/en-us/powershell/module/teams/set-csonlineapplicationinstance).

## Assign a license

For each resource account, you must assign a **Microsoft Teams Phone Resource Account** license.

Nested auto attendants and call queues that transfer calls externally don't require resource accounts or respective licensing. When nesting auto attendants or call queues, license the resource account on the first auto attendant or call queue receiving the call.

1. Sign into the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Expand **Users**, then select **Active users**.
3. Select the resource account to which you want to assign a license. The resource account's user pane will appear.
4. On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft Teams Phone Resource Account**.
5. Select **Save changes**.

Note

If the resource account requires a phone number, check that the **Select location** dropdown list in the **Licenses and Apps** tab matches the intended country code.

## Assign a phone number

If you're planning to use the resource account with an auto attendant or call queue that requires a phone number, assign a number to the resource account.

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Expand **Voice**, and then select **Resource accounts** page.
3. Select the resource account to which you want to assign a phone number, and then select **Assign/unassign**.
4. In the **Phone number type** dropdown, choose the type of number that you want to use.
5. In the **Assigned phone number** box, search for the number you want to use and select **Add**. Be sure to include the country code (for example, +1 250 555 0012).
6. Select **Save**.