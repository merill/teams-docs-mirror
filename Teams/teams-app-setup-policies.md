---
layout: Conceptual
title: Manage agents and app setup policies in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-app-setup-policies
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
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 2026-05-12T00:00:00.0000000Z
ms.reviewer: mhayrapetyan
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to pin apps, install apps, and allow users to upload custom apps by creating, editing, and managing app setup policies.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
locale: en-us
document_id: 6f91604a-35b0-dfbb-55b2-b601cb0841b0
document_version_independent_id: 84bcd0d7-b4ed-f13e-c84b-2ec6a7661ae9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-app-setup-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-app-setup-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-app-setup-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: ea293c84-fa66-93a3-9cf1-2d50dc2d1c96
---

# Manage agents and app setup policies in Microsoft Teams - Microsoft Teams | Microsoft Learn

As an admin, you use setup policies to manage, install and pin agents and apps and control which users can upload custom agents and apps in personal or team contexts. Pinning helps promote adoption of agents and apps for users and it provides quick access. To learn more, see [app setup policy](app-policies).

- **[Install agents and apps in Teams client](/en-us/microsoftteams/teams-app-setup-policies):** Setup policies let you add the allowed agents and apps on behalf of users when they use Teams and during meetings. For organizations using app centric management, this functionality is available in [app centric management UI](/en-us/microsoftteams/install-teams-apps).
- **[Pin apps in Teams client](/en-us/microsoftteams/teams-app-setup-policies):** App setup policies let you choose apps to pin, set the order the apps show up for your users in the Teams app bar or the compose message area. Admins can also control whether the users can pin their own apps or not.
- **Upload custom agents and apps:** Setup policies let you control which users can upload custom agents and apps to Teams. See [Upload custom agents and apps](/en-us/microsoftteams/teams-custom-app-policies-and-settings) article.

The following built-in setup policies are available in the Microsoft Teams admin center, by default:

- **Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy. Edit the global policy to pin agents and apps that are most important for your users.
- **FirstlineWorker**: This policy is for Frontline Worker. The policy can't be customized. You can assign it to Frontline Workers in your organization.

    Note

    The user pinning setting is available in the Teams admin center in Microsoft 365 Commercial, GCC, GCC High, and DoD environments.

## Manage agent or app setup policies

You can manage the agent or app setup policies in the Microsoft Teams admin center. Use the Global (Org-wide default) policy or create and assign custom policies. Global policy applies to all users unless you assign a custom policy to some users. Custom policy overrides the global policy. A Teams Administrator or an admin with a higher role can manage these policies.

You can edit the settings in the global policy to include the apps that you want. To customize Teams for different groups of users in your organization, create and assign one or more custom policies.

[![Screenshot shows the app setup policies page with options to manage policies or add new policies.](media/teams-app-setup-policies/manage-app-setup-policies.png)](media/teams-app-setup-policies/manage-app-setup-policies.png#lightbox)

### Edit an agent or app setup policy

You can use the Microsoft Teams admin center to edit a policy, including the **Global (Org-wide default)** policy and custom policies that you create. After you edit or assign a policy, it can take a few hours for changes to take effect. To edit an agent or app setup policy, follow these steps:

1. Sign in to the Teams admin center and go to **Teams apps** &gt; [**Setup policies**](/en-us/microsoftteams/teams-app-setup-policies).
2. Choose the policy you want to edit and then select **Edit**.
3. Make the changes that you want.
4. Select **Save**.

### Assign a custom policy in agent or app setup policy to users and groups

To know how to assign policies to your users and to groups, see [how to assign policies to users and groups](/en-us/microsoftteams/assign-policies-users-and-groups) and [admin center UI for group assignments](https://admin.teams.microsoft.com/policies/app-setup/grouppolicyassignments). Groups are distribution list groups, mail-enabled security groups, security groups, and Microsoft 365 groups and are created in [teams and groups UI in admin center](https://admin.microsoft.com/Adminportal/Home#/groups).

A user can have more than one policy assigned either directly or as a part of different groups. However, only one policy is effective at a time for a user. To know what policy applies, see [precedence of applied policies](/en-us/microsoftteams/policy-assignment-overview).

### View the policies already applied to the user

You can use the Teams admin center to check the policies that are assigned to a user. To view the policies, follow these steps:

1. Sign in to the Teams admin center and go to **Users** &gt;[**Manage users**](https://admin.teams.microsoft.com/users).
2. Search for and select the user by clicking to the left of the user name.
3. Select **View policies** under the **Policies assigned** column. [![Screenshot that shows the option to view the existing policies applied to the user.](media/teams-app-setup-policies/manage-users-view-policies.png)](media/teams-app-setup-policies/manage-users-view-policies.png#lightbox)

### Change the existing policies for a user

To change the existing policies applied to a user, follow these steps:

1. Sign in to the Teams admin center and go to **Users** &gt; [**Manage users**](https://admin.teams.microsoft.com/users).
2. Search for and select the user by clicking to the left of the user name and then select **Edit settings**.
3. Select the policy you want to change, and then select **Apply**. [![Screenshot that shows the options to change the existing policies.](media/teams-app-setup-policies/edit-user-policy-settings.png)](media/teams-app-setup-policies/edit-user-policy-settings.png#lightbox)

To unassign a custom policy from a user, you can set each policy to **Global (Org-wide default)**.

You can change the existing policies for a user using PowerShell. For more information, see [assign policies to users and groups](/en-us/microsoftteams/assign-policies-users-and-groups).

### Unassign agent or app setup policies in bulk

When you unassign policies in bulk, you're removing policy assignments that were assigned to individual users through direct assignment. To unassign setup policies in bulk, follow these steps:

1. Sign in to Teams admin center and go to **Teams apps** &gt; [**Setup policies**](https://admin.teams.microsoft.com/policies/app-setup).
2. Select the policy by clicking to the left of the policy name, and then select **Bulk unassign users** from **Manage users** menu. [![Screenshot that shows the bulk unassign users option from the manage user menu.](media/teams-app-setup-policies/app-setup-policies-bulk-unassign.png)](media/teams-app-setup-policies/app-setup-policies-bulk-unassign.png#lightbox)
3. Choose the policy that you want to unassign and select **Load data** to get the number of users who are currently assigned to that policy. [![Screenshot of the bulk unassign policies page with the load data option.](media/teams-app-setup-policies/unassign-policies-bulk-users.png)](media/teams-app-setup-policies/unassign-policies-bulk-users.png#lightbox)
4. Select **Unassign**, and then select **Confirm**.

## Use app setup policy to allow agents

Developers can create agents with the [Teams SDK](/en-us/microsoftteams/platform/teams-sdk/welcome). Developers must incorporate these agents in a Teams app for use in Teams. As an admin, you govern Teams apps that contain agents.

Teams supports the following agent scenarios based on the admin center settings:

- Agents must be contained in a Teams app package. There are two methods for uploading your app: use [Developer Portal for Teams](/en-us/microsoftteams/platform/concepts/build-and-test/teams-developer-portal) or [manually create an app package](/en-us/microsoftteams/platform/concepts/build-and-test/apps-package) and upload your app. If you need to alter your app manifest and reupload your app, delete your agent before uploading your altered app package.
- Agents only work if [custom app upload is allowed](/en-us/microsoftteams/teams-custom-app-policies-and-settings).
- Any agent that is a part of a Teams app works if admin [allows the app](/en-us/microsoftteams/manage-apps#allow-or-block-apps) in the organization.

## Install agents and apps for your users on Teams

If your organization uses app centric management functionality, then [use Manage apps page to install agents and apps for users](/en-us/microsoftteams/install-teams-apps). Otherwise, continue to preinstall agents and apps using setup policies.

The below message on app setup policy page indicates that your org is using app centric management functionality.

[![Screenshot showing updated setup policy page without the app installation option.](media/teams-app-setup-policies/app-setup-policies-summary.png)](media/teams-app-setup-policies/app-setup-policies-summary.png#lightbox)

If your organization isn't using app centric management, then continue to [use app setup policy to install agents and apps](/en-us/microsoftteams/install-teams-apps).

## Pin apps

Using pinning functionality, you can highlight agents and apps that users need the most. Make these agents and apps available for users instantly and available in the user's context. Pinning promotes ease of access and improves agent and app adoption in your organization. Admins can pin agents and apps and they can allow users to pin as well. If an admin pins an agent or app, it is added and pinned in the Teams client for the allowed users only. Pinning respects other governance controls and agent and apps aren't available to users who aren't allowed to use it.

You can pin agents and apps in the following UIs for the users:

- **App bar**: Users can easily access it and use it. Pinned agents and apps show on the left side of the Teams desktop client and at the bottom of the Teams mobile client.

    | **Teams desktop client** | **Teams mobile client** |
    | --- | --- |
    | ![Screenshot of Microsoft Teams desktop app showing the app bar with Activity, Chat, Teams, Calendar, Calls, Files, and Apps icons.](media/teams-app-setup-policies/pinned-apps-teams-desktop.png) | ![Screenshot of Microsoft Teams mobile app showing the Chat screen with the app drawer open and the bottom app bar highlighted.](media/teams-app-setup-policies/teams-mobile-pinned-apps.png) |
- **Message extension**: Users can quickly use it when composing their messages.
- **Meeting extension**: Meeting attendees can view it without leaving the meeting and quickly collaborate using the app. The in-meeting bar displays only two apps and the rest of the apps, if added, display under the **More** option.

Agents and apps pinned in a meeting show at the top of the meeting window. If there are more than two apps, the other apps display in the More option.

[![Screenshot showing a meeting room and apps pinned to the top bar in the meeting room.](media/teams-app-setup-policies/meeting-pinned-apps-teams.png)](media/teams-app-setup-policies/meeting-pinned-apps-teams.png#lightbox)

- **Calling extension**: Users can quickly access personal apps in an active Public Switched Telephone Network (PSTN) or one-to-one call.

To modify the pinned agents and apps for everyone in your organization, edit the existing Global (Org-wide default) policy. To modify the pinned agents and apps for specific users, create a new app setup policy and assign it to the specific users. When apps are pinned for specific users, the meeting extension is available only in meetings organized by users assigned the app setup policy. In those meetings, the meeting extension is also available to other participants.

1. Sign in to Teams admin center and access **Teams apps** &gt; [**Setup policies**](https://admin.teams.microsoft.com/policies/app-setup).
2. Select **Add**.
3. Provide a name and description for the policy.
4. Optionally, turn on **User pinning** to allow users to pin agents and apps and change the order of the pinned agents and apps.
5. Under **Pinned apps**, select **Add apps**.
6. In the **Add pinned apps** pane, search for the agents and apps you want to add, and then select **Add**. Agents and apps get added only to the scopes that it supports.[![Screenshot shows how to add pinned apps in app setup policy.](media/teams-app-setup-policies/pinned-apps-selection.png)](media/teams-app-setup-policies/pinned-apps-selection.png#lightbox)

If you pin a calling extension, you must also assign it to users who need access during one-on-one calls.

1. Arrange the agents and apps in the order that you want them to appear in the Teams client. You can change the sequence independently under **App bar**, **Messaging extensions**, **Meeting extensions**, and **Calling extensions**. You can remove agents and apps from a scope. [![Screenshot of the pinned apps and options to change their order.](media/teams-app-setup-policies/pinned-apps-management.png)](media/teams-app-setup-policies/pinned-apps-management.png#lightbox)
2. Select **Save**.

Note

In Teams for Education, the [**Assignments app**](/en-us/microsoftteams/expand-teams-across-your-org/assignments-in-teams) is pinned by default even though you don't see it listed in the Global policy.

Tip

For the frontline workers in your organization, we recommend using the tailored frontline app experience. This feature pins the most relevant apps in Teams for users who have an [**F license**](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline). To learn more, see [**Tailor Teams apps for your frontline workers**](/en-us/microsoft-365/frontline/pin-teams-apps-based-on-license).

## Manage pinning for Copilot app

For users with a Microsoft Copilot license, Copilot app is pinned by default, even though it isn't listed in the policy. You can add it to the policy to manage its order, but it remains pinned even if you remove it from the policy.

For users without a Microsoft Copilot license, pinning Copilot app through app setup policies behaves in the same way as other apps, as described under Pin apps. You can also pin Copilot through Microsoft 365 admin center. For more information, see [How to pin Copilot Chat in the Microsoft Copilot app, Microsoft Teams, and Outlook](/en-us/copilot/manage).

If you pin Copilot only in Microsoft 365 admin center, the app is pinned in a default location. If you pin Copilot in both Microsoft 365 admin center and Teams admin center, Teams pins the Copilot according to the app setup policy for the assigned users.

## Considerations and limitations

- You can't add custom apps with configurable tabs using app setup policies.
- Users can't remove an agent or app from their client if an admin adds it. The Uninstall option for an agent or app in the app bar isn't available.
- Users can unpin an agent or app that is pinned via app setup policy if user pinning is allowed in the policy.
- Users can change the order of their pinned agents and apps on Teams desktop and mobile clients if the user pinning option is turned on. Users can't change the order of their pinned agents or apps on Teams web client.
- Admin pins always take precedence. If the user pinning option is turned on, then agents or apps pinned by the users display below those pinned by the admins. If the user pinning option is turned off, then the users lose existing pins and only the agents and apps pinned by the admins are available in the app bar.
- There's no limit on the maximum number of pinned agents and apps that you can add to a policy. However, at least two agents or apps must be pinned to the Teams mobile client (iOS and Android). If a policy has fewer than two agents or apps, the mobile client doesn't reflect the policy settings. Instead, the mobile client continues to use the existing configuration.
- After you edit or assign a policy, it can take a few hours for changes to take effect. Also, the rollback takes a few hours to take effect if you choose to roll back the policy application.
- The in-meeting bar displays only two agents and apps and the rest, if added, display under the More option.
- Not all agents and apps can be pinned to Teams through an app setup policy. Some agents and apps don't support this functionality. To find agents or apps that can be pinned, search for it in the **Add pinned apps** pane. Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these agents and apps are available in the **Add pinned apps** pane. While the Teams store lists all Teams agents and apps, the **Add pinned apps** pane includes only agents and apps that can be pinned to Teams through a policy.
- In Teams for Education, the [Assignments app](/en-us/microsoftteams/expand-teams-across-your-org/assignments-in-teams) is pinned by default even though it isn't listed in the Global policy.
- In Teams for Education, the Calling app isn't available. When you create a new custom policy in the app setup policy, the Calling app is displayed in the list of apps. However, Teams for Education users can't see the Calls app in Teams client as it isn't pinned.

## Related article

- [Assign policies to users in Teams](/en-us/microsoftteams/assign-policies-users-and-groups)
- [How to use apps in meetings](https://support.microsoft.com/office/use-apps-in-microsoft-teams-meetings-62bca572-ba7e-4e21-9190-a47c61319739)