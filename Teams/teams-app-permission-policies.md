---
layout: Conceptual
title: Manage app permission policies in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-app-permission-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal
ms.author: vikasalmal
manager: prkosh
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 2026-02-27T00:00:00.0000000Z
ms.reviewer: mhayrapetyan
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to control availability of Teams apps for users by using permission policies and how to create, edit, assign, and unassign the policies.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
locale: en-us
document_id: b51eda6c-168c-7d99-7cc1-992b3d8feef2
document_version_independent_id: 118a1b8f-f4b7-a778-70b1-d3161fc548ab
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-app-permission-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-app-permission-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-app-permission-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 2adf5f3a-11a5-641e-6236-20bcb1c9164f
---

# Manage app permission policies in Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

If your organization is moved to app centric management feature to manage access to apps, see [Manage access to Teams apps using app centric management](app-centric-management). Permission policies will no longer apply and you may see this message on the policy page. If policies are available, you can continue to use those. We will soon let you migrate to app centric management on your own.

![Screenshot showing the permissions policy change for organizations that are using app centric management.](media/acm-policy-page.png)

As an admin, you can use app permission policies to control the apps that are available to each user in your organization. The permissions you set to allow or block all apps or specific apps are applicable to all [types of apps in Teams](apps-in-teams). To understand policies, see [app permission policies](app-policies). You must be a Teams Administrator or have a higher role to manage these policies.

To let your org users use a Teams app or a copilot agent, you must allow it in:

- [Org-wide app settings](manage-apps#manage-org-wide-app-settings).
- [Individual app's setting](manage-apps#allow-or-block).
- App permission policy.
- Teams admin center and Microsoft 365 admin center.

The first two settings just allow an app for use in your organization, the permission policies lets you control which users can use a specific app. You control the access on a per-user and per-app basis by creating and applying the policy to specific users. To make any apps or Copilot agents available in your organization, ensure the following:

- If your organization isn't migrated to unified app management, allow apps and agents in Teams admin center and under the **Integrated apps** page in [Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).
- If your organization is migrated to unified app management, allow apps and agents in Teams admin center or under the **Integrated apps** page in [Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).

Teams admin center lets you create two types of permissions policies:

- **Global (Org-wide default)** policy exists by default and applies to all users. Any changes made to this policy affect all users.
- **Custom policy** apply only to those users that you apply it to. You create and use custom policies to allow apps to specific users.

    ![Screenshot showing custom and default app permission policies.](media/app-permission-policy-trimmed.png)

If your organization is already on Teams, the app settings you configured in **Tenant-wide settings** in the Microsoft 365 admin center are reflected in **Org-wide app settings** on the [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) page in Teams admin center. If you're new to Teams and just getting started, by default, all apps are allowed in the org-wide global setting. It includes apps published by Microsoft, third-party software providers, and your organization.

Alternately, you can use [app centric management](app-centric-management) to configure the access to apps on a per-app basis. It offers an easier method to configure access to apps. The app centric management functionality replaces app permissions policies. The feature makes it easier for you to specify the users in their organization who can add or install Teams apps on a per-app basis. You can use only one method to define access to apps in your organization. If you choose to, you can migrate from app permission policies to app centric management using our migration UI.

Note

To know about third-party app settings in Microsoft 365 Government Community Cloud High (GCCH) and Department of Defense (DoD) environment, see [Manage org-wide app settings for Microsoft 365 Government](manage-apps#manage-org-wide-app-settings-for-microsoft-365-government).

## Create an app permission policy

Use one or more custom app permission policies, if you want to control the apps that are available to different users. You can create and assign separate custom policies based on whether apps are published by Microsoft, third parties, or your organization. After you create a custom policy, you can't change it if third-party apps are disabled in org-wide app settings. To create an app permission policy, follow these steps:

1. Sign in to the Teams admin center and go to **Teams apps** &gt; **[Permission policies](https://admin.teams.microsoft.com/policies/app-permission)**.
2. Select **Add**.
3. Provide a name and description for the policy.
4. Under **Microsoft apps**, **Third-party apps**, and **Custom apps**, select one of the following options:

    - Allow all apps or copilot agents
    - Allow specific apps or copilot agents and block all others
    - Block specific apps or copilot agents and allow all others
    - Block all apps or copilot agents
5. If you selected **Allow specific apps and block all others**, add the apps that you want to allow:

    1. Select **Allow apps**.
    2. Search for the apps that you want to allow, and then select **Add**. The search results are filtered to the app developer (**Microsoft apps**, **Third-party apps**, or **Custom apps**).
    3. After choosing one or more apps, select **Allow**.
6. If you selected **Block specific apps and allow all others**, similarly, search and choose the apps that you want to block, and then select **Block**.
7. Select **Save**.

## Edit an app permission policy

You can use the Teams admin center to edit the global policy or any custom policies that you've created. To edit, follow these steps:

1. Sign in to the Teams admin center and access **Teams apps** &gt; **[Permission policies](https://admin.teams.microsoft.com/policies/app-permission)**.
2. Select the policy by clicking to the left of the policy name, and then select **Edit**.
3. Make the changes to allow or block specific apps in each of the three categories.
4. Select **Save**.

## Assign a custom policy for app permissions to users

App permission policies take effect only when you apply a policy to a user. See the different ways to [assign the policy to users](policy-assignment-overview#ways-to-assign-policies).

Teams doesn't support group policy assignments for app permission policies.

## View the policies already applied to a user

You can use the Teams admin center to check the policies that are assigned to a user. To view the policies, follow these steps:

1. Sign in to the Teams admin center and go to **Users** &gt; **[Manage users](https://admin.teams.microsoft.com/users)**.
2. Search for and select the user by clicking the user name.
3. Select **View policies** under the **Policies assigned** column.

    ![Screenshot that shows the option to view the existing policies applied to the user.](media/manage-users-view-policies.png)

## Change the existing policies for an individual user

To change existing policies, follow these steps:

1. Sign in to the Teams admin center and go to **Users** &gt; **[Manage users](https://admin.teams.microsoft.com/users)**.
2. Search for and select the user by clicking to the left of the user name and then select **Edit settings**.
3. Select the policy you want to change, and then select **Apply**.

    ![Screenshot that shows the options to change the existing policies.](media/manage-users-edit-settings.png)

Note

To unassign a custom policy from a user, you can set each policy to **Global (Org-wide default)**.

You can also change existing policies for an individual user using PowerShell. For more information, see [assign policies to users](assign-policies-users-and-groups).

## Unassign app permission policies in bulk

When you unassign policies in bulk, you're removing policy assignments that were assigned to individual users through direct assignment. To unassign permission policies in bulk, follow these steps:

1. Sign in to the Teams admin center and go to **Teams apps** &gt; **[Permission policies](https://admin.teams.microsoft.com/policies/app-permission)**.
2. Click on the policy's name and then select **Bulk unassign users** from the **Manage users** menu.

    ![Screenshot that shows the bulk unassign users option from the manage user dropdown menu.](media/app-permission-policy-manage-users.png)
3. Choose the policy that you want to unassign and select **Load data** to get the number of users who are currently assigned to that policy.

    ![Screenshot of the bulk unassign policies page with the load data option.](media/unassign-policies-load-data.png)
4. Select **Unassign**, and then select **Confirm**.

After you unassign policies, you can review operation details in the [Activity log](https://admin.teams.microsoft.com/activity-log).

## Considerations when using app permission policies

The following are a few considerations when using app permissions policies to grant access or to disallow access to apps:

- Teams doesn't support group policy assignments for app permission policies.
- App permission policies take effect only when you apply a policy to a user.
- After you edit or assign a policy, it can take a few hours for changes to take effect.
- A user can't interact with any functionality of an app that the user isn't allowed to use.
- Users can search for blocked apps and request admin approval. Admins retain complete control to [approve or ignore user requests](user-requests-approve-apps).
- App setup policies work together with app permission policies. You select apps to pin in setup policy from a set of allowed apps. However, if a user has an app permission policy that blocks the use of a pinned app, then the user can't use the app.
- App policies apply to users using Teams on web, mobile, or desktop clients.