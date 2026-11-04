---
layout: Conceptual
title: Manage the Avatars app for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-avatars
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal0201
ms.author: vikasalmal
manager: tyadams
audience: ITPro
ms.reviewer: sekerawa
ms.date: 2026-10-09T00:00:00.0000000Z
ms.topic: quickstart
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- teams-1p-app-admin
description: Learn how to set up the avatars for Microsoft Teams app.
locale: en-us
document_id: 122d9ead-09d3-f605-1bfb-6ae0fce81636
document_version_independent_id: 122d9ead-09d3-f605-1bfb-6ae0fce81636
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-avatars.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-avatars
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-avatars.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c4bf5559-f9c6-03d2-d00d-e2f67c9ba9ed
---

# Manage the Avatars app for Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

Avatars in Teams will retire on April 2, 2027. Avatars will remain available and supported until that date, including security updates and necessary fixes. More information will be shared as it becomes available.

The Avatars app is enabled by default for all organizations.

As an admin, you can control whether avatars for Teams is available in your organization and who can use Avatars using [Teams Admin Center](manage-apps) policies, Microsoft 365 service plans, or [App centric management](app-centric-management) of Teams apps.

To set up avatars in Teams, you should:

1. Allow endpoints.
2. Manage user access to the Avatars app using one of the following options:
    1. Use app centric management for Avatars in Teams
    2. Manage Avatars in the Teams admin center
    3. Use service plans in the Microsoft 365 Admin Center to allow the Avatars app
3. (Optional) Block Avatars app in the Teams Admin Center

Note

Users currently need to manually install and pin the Avatars app. For more information, see [Use app setup policies to pin and auto-install apps for users](/en-us/microsoftteams/teams-app-setup-policies).

Note

The Avatars for Teams app has minimum and recommended hardware requirements. For more information, see [Teams client system requirements](teams-client-system-requirements).

Teams users can access this feature if they have one of the following licenses: Teams Essentials, Microsoft 365 Business Basic, Microsoft 365 Business Standard, Microsoft 365 Business Premium, Microsoft 365 E3/E5, and Office 365 E1/E3/E5.

## What is the Avatars app?

The Avatars for Microsoft Teams app lets your users connect with presence in Teams without having to turn on their cameras. Your users can represent themselves the way they want to show by choosing the avatar that fits their specific meeting. To learn more about using avatars in Microsoft Teams, see how to [Join a meeting as an avatar](https://support.microsoft.com/office/5384e7b7-30c7-4bcb-8065-0c9e830cc8ad).

## Allow endpoints

To ensure the avatars for Teams app works properly, access to the following endpoints must be allowed through your firewall or proxy server. All endpoints need to allow traffic on TCP ports 80 and 443.

- `*.microsoft.com`
- `*.cloud.microsoft`
- `*.static.microsoft`
- `*.office.com`
- `*.office.net`

If these endpoints aren't properly allowed, you will run into issues when running the Avatars for Teams app.

## Use app centric management for Avatars in Teams

Important

App centric management of Teams apps is a new feature. For more info on this rollout see [Use app centric management to manage apps | Microsoft Learn](app-centric-management).

## Manage Avatars in the Teams admin center

Note

It may be more complicated if the tenant already has different app permission policies for users or groups.

### Allow the Avatars app

1. In the [Teams admin center](https://admin.teams.microsoft.com/policies/manage-apps), in the left-navigation bar, go to **Teams apps** &gt; **Manage apps**.
2. In the **Search by name** text box, search for and select **Avatars** and then select **Allowed**. ![Screenshot showing the toggle with the Avatars app state set to Allowed.](media/avatars-allowed-new.png)

### Create or edit a setup policy to preinstall the Avatars app for users

1. In the [Teams admin center](https://admin.teams.microsoft.com/policies/manage-apps), go to **Teams apps** &gt; **Setup policies**.
2. Select the policy you want to edit, such as **Global (Org-wide default)** or **Add** a policy. If you add a new policy, make sure to give it a descriptive name.
3. Under **Installed apps**, select **Add apps**.
4. Under **Search based on this app permission policy**, select **Global**.
5. Search for **Avatars**, and then select **Add**. [![Screenshot with the menu showing the Avatars app selected from an app search box.](media/avatars-add-app-new.png)](media/avatars-add-app-new.png#lightbox)
6. Confirm by selecting **Add** at the bottom.
7. Select **Save** to save the changes to your app setup policy.

If you created a new app setup policy, remember to assign it the users you want it to apply to. For more information, see [Ways to assign policies](policy-assignment-overview#ways-to-assign-policies).

### Enable user pinning or pin app for users

1. In the [Teams admin center](https://admin.teams.microsoft.com/policies/manage-apps), go to **Teams apps** &gt; **Setup policies**.
2. Select the policy you want to edit, such as **Global (Org-wide default)**.
3. Set **User pinning** to **On**.
4. [Optional] In the **Setup** policy page, go to **Pinned apps**, and **Add** the avatars for Teams app.

Now users can see the Avatars app when they search through their apps, and will be able to pin it. If you add the avatars for Teams app to the **Pinned apps** list, the app will be pinned for users.

[![Screenshot with Setup Policies showing User Pinning toggle in the On state, and the installed Avatar app.](media/avatars-app-pinning-new.png)](media/avatars-app-pinning-new.png#lightbox)

### Block Avatars app in the Teams Admin Center

Blocking users is important when you don't want certain users to access the avatars for Teams app. You can also block users if there's a report of an inappropriate avatar that violates company policy and needs to be disabled.

If you want to block the avatars for Teams app available from a set of users, you need to add it to the app permissions policy assigned to those users.

### Create a policy to block the Avatars app for specific users

1. In the [Teams admin center](https://admin.teams.microsoft.com/policies/manage-apps), go to **Teams apps** &gt; **Permission policies**.
2. In **App permissions policies**, select **Add**.
3. Provide a name and description for the policy.
4. Under **Microsoft apps**, select **Block specific apps and allow all others**, and then select **Block apps**.
5. Search for and select the **Avatars** app, then select **Block**.
6. Enter a policy name and description and then **Save.**

### Add users to policy to block them from the Avatars app

Important

Users need to restart their Teams client for new policies or policy updates to take effect.

1. In the left navigation of the Microsoft Teams admin center, go to the **Permission policy** page.
2. Select the policy you created and then select **Assign users** to assign this policy to the users you want to block.
3. In the **Manage users** pane, search for the user using their display name or username.
4. Select the user you want to block and then select **Add**.
5. Repeat steps 2 and 3 for each user that you want to block.
6. When you're finished adding users that you want to block, select **Apply**.

### Manage avatars for user profiles in the Teams Admin Center

Global or User admins can view, export, or remove a user's avatar profile from within the Teams Admin Center. This is useful if an incident of an offensive avatar is reported and needs to be removed or investigated for further action.

1. Select **Manage users** in the left nav.
2. Search for and select a user.
3. At the bottom of their user profile, you'll see their avatar(s).
4. Select **Export profiles** to generate a JSON file of the user's avatar configurations (up-to three).
5. Select **Remove profile** for a specific avatar profile you wish to remove entirely. The avatar profile you removed won't be visible to the user.

## Use service plans in the Microsoft 365 Admin Center to allow the Avatars app

1. Sign into [Microsoft 365 Admin Center](https://admin.microsoft.com/) with an admin account with at least Global, License, or User level permissions and open the left navigation panel to the Users section.
2. Select the user or user group and go to **Licenses and apps** to manage the active licenses and service plans.
3. Ensure that you enabled the appropriate licenses for Avatars for Teams.

For more guidance for assigning licenses in Microsoft 365, see [Assign or unassign licenses for users in the Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/assign-licenses-to-users).

For more complex and larger group license management, see [What is group-based licensing in Microsoft Entra ID?](/en-us/entra/fundamentals/concept-group-based-licensing).

## Where avatars can be used

Avatars for Teams can be used in any Teams meeting that includes the option to use a real-world camera.

Guests invited to meetings can only to use avatars for Teams if the app is enabled on their tenant for their account.

If you're invited to a meeting outside your tenant, you'll be able to use avatars for Teams if enabled on your tenant for your account.

To learn how to use avatars in Teams, see [Join a meeting as an avatar in Microsoft Teams](https://support.microsoft.com/office/5384e7b7-30c7-4bcb-8065-0c9e830cc8ad).