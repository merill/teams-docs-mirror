---
layout: Conceptual
title: App centric management to manage user access to Teams apps - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/app-centric-management
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal0201
ms.author: vikasalmal
manager: prkosh
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- m365initiative-voice
- M365-collaboration
- Tier1
search.appverid: MET150
ms.date: 2026-04-14T00:00:00.0000000Z
ms.reviewer: mhayrapetyan
description: Manage access to Teams apps using app centric management.
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 4f0f6177-da44-cc08-d8d3-ca1d90bd4d2d
document_version_independent_id: 4f0f6177-da44-cc08-d8d3-ca1d90bd4d2d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/app-centric-management.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-centric-management
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/app-centric-management.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: 4118d5db-812b-add1-59b4-6479208facc3
---

# App centric management to manage user access to Teams apps - Microsoft Teams | Microsoft Learn

Important

All organizations don't have the app centric management feature available. If you're migrated to app centric management, you can see the following message on the permission policy page:

![Screenshot showing the permissions policy change for organizations that are using app centric management.](media/acm-policy-page.png)

For timelines, see [Message Center post MC688930](https://admin.microsoft.com/Adminportal/Home#/MessageCenter/:/messages/MC688930) or [Microsoft 365 roadmap item 151829](https://www.microsoft.com/en-US/microsoft-365/roadmap?filters=&amp;searchterms=151829).

If you see policies on the [permission policies page](https://admin.teams.microsoft.com/policies/app-permission), continue to [use app permission policies](teams-app-permission-policies) or migrate to this feature on your own.

With the introduction of app centric management functionality, admins have two methods to control the access and availability of apps and copilot agents.

- Continue to [use permission policies](teams-app-permission-policies).
- Use the feature if already auto-migrated or manually migrate to app centric management. It replaces app permission policies.

This functionality lets you specify which users and groups can use each app or a copilot agent and you can control it on a per-app basis.

Whatever method you use, you can manage access to apps for individual users, supported groups, or everyone in the organization. You have complete control over who can or can't add apps in your organization. You can also control the access to new apps that we publish to Teams app store.

## How is app centric management different than permission policy

Previously, when using permission policies, you determined access to apps using the following three settings:

- Org-wide app setting for third-party apps: It applies at an org-level and controls if all third-party apps are available for every user or not.
- App status: It applies at an app-level as allow or block and controls if it's available to any user or not.
- Permission policy: It applies at a user-level and controls if a specific user is allowed to use an app or not.

App centric management feature simplifies these settings. Each app contains its access definition using a list of users and groups that you assign to it. It lets you manage each app individually based on your user's needs and organization's compliance and risk posture.

When using this functionality, you determine access to apps using one of the following options for each app:

| New option | Who gets the app | How does it map with previous settings |
| --- | --- | --- |
| `Everyone` | Available to all org users, new users, and guests. | Same effect as allowing an app and global (Org-wide default) app permission policy allowing all users to use it. |
| `Specific users or groups` | Only the users and groups that you select can use the app. The supported group types are security groups, Microsoft 365 groups, dynamic user membership groups, nested groups, and the distribution lists. Guests can't use the app if this option is selected and even if guests are assigned to the app. | Same as using a custom app permission policy to restrict the use of app to selected users or groups. |
| `No one` | Not available to any user | Same as a blocked app. |

The method to allow users access to an app changes with this functionality. In the past, to allow access to a user, you'd add the app as an allowed app in a policy and assign that policy to the user. Using this functionality, you just modify the availability of an app to let selected users use it. Also, you don't have to create multiple policies for different combinations of apps and allowed users.

## Migrate to app centric management

Important

Starting from April 2025, your tenant is automatically migrated to app centric management. After the migration, you can't access the migration wizard. However, until the migration is complete, you can use the wizard and opt to complete the migration manually. For more information, see understand the auto-migration process.

Previously, we automatically migrated organizations that weren't using any custom policies. Admins can now do an on-demand migration. Understand the difference between the two types of migration.

| Type of migration | Who does it | Requirement | How is it done |
| --- | --- | --- | --- |
| Assisted | Administrator | Org uses one or more custom policies | Guided UI in admin center. This is transitioned to automatic migration. See [Message Center post MC688930](https://admin.microsoft.com/Adminportal/Home#/MessageCenter/:/messages/MC688930) for timelines. |
| Automatic | Microsoft | Org uses only the default global policy | Automatic, without admin intervention. One or more custom policies are being rolled out. See [Message Center post MC688930](https://admin.microsoft.com/Adminportal/Home#/MessageCenter/:/messages/MC688930) for timelines. |

To migrate your organization, follow these steps:

1. Log into Teams admin center and access Teams apps &gt; [Permission policies](https://admin.teams.microsoft.com/policies/app-permission) page. Take inventory of the apps in the permission policies and identify the users and groups that the apps are allowed or blocked for. During the migration, you might have to manually edit the availability for some apps for the existing users and groups. For details, see step 5.
2. On the permission policies page, select **Get started**.

    ![Screenshot showing the policy page with prompt to migrate to app centric management.](media/acm-start-prompt.png)
3. Select policies that you want to migrate and select **Next**. The page displays only those policies that are assigned to users or groups. Also, we migrate only those apps and their availability that are part of the policies that you choose to migrate. Apps in the unselected policies aren't part of the migration and can’t be migrated later. However, you can manually edit the availability for any app after the migration.

    [![Screenshot showing the app centric management migration UI to select policies.](media/acm-migration-select-policies.png)](media/acm-migration-select-policies-large.png#lightbox)
4. Verify the app availability for the users on the next page. In the following three tabs, it shows a list of apps from your Org-wide app settings and the app permission policies that you choose to migrate.

    - Available to everyone: List of apps allowed for everyone in your organization.
    - Available to specific users and groups: List of apps that are selectively allowed for at least one org user or a supported group.
    - Available to no one: List of apps that nobody in the org can use.
5. In each tab, you can modify the app availability to one of the three app availability types, as necessary. Edit availability option appears in **Available to specific users and groups** tab if the app availability isn't clear and admin input is needed to proceed. Either the apps aren't present in the policies that you selected to migrate or selected policies contain conflicting availability. You must assign such apps to one of the availability types before you can proceed.

    [![Screenshot showing three tabs during migration that help you review and modify the app availability.](media/acm-migration-availability.png)](media/acm-migration-availability.png#lightbox)

    Tip

    If you see many apps in this tab, you likely have policies that have conflicting apps availability. For example, a policy that allows an app and another policy that blocks the same app. In such a scenario, we recommend that you uncheck the policy that leads to a conflict or you edit the availability in this tab.
6. You can validate the changes on a per-app or a per-user basis. Select a tab and type the name of the app or the user.

    [![Screenshot showing the option to verify available for each user and users who receive a particular app.](media/acm-verify-per-app.png)](media/acm-verify-per-app-large.png#lightbox)
7. On the final review UI, you can see the apps, their availability, and the Org-wide app settings that apply after the migration. You can download this information as a CSV file to evaluate further. For example, you can use the inventory mapping from Step 1 to ensure that the app availability is as intended. Once assured, select **Start migration** and follow the prompts.

    Note

    The migration completes in minutes, but it might take up to 24 hours for the changes to reflect for all users. After the migration is complete, you can start making changes to app availability through the new UI. You can also use PowerShell cmdlets to update app availability at any time after the migration. UI or PowerShell changes take up to 24 hours to apply to all users, consistent with anytime UI or PowerShell updates occur, not just immediately after migration completion.

    [![Screenshot showing the last UI to review all settings.](media/acm-migration-review.png)](media/acm-migration-review-large.png#lightbox)

During migration, you can save a draft of the migration progress using the **Finish later** option. You can cancel the migration and delete the saved draft using the **Reset all changes** option.

Note

While migrating, you can't make changes to app assignments. The existing UI gets disabled when you start the migration. If you aren't ready to proceed or want to make change to the existing permission policies, open the migration wizard and select the Reset all changes option. You'll lose the progress and can restart the migration later.

After migration, your blocked apps continue to remain unavailable to users. The statuses of such apps show as `unblocked` now, but the apps are assigned to `No one` in the `Available to` column on the Manage apps page. It means that org user can't use the app, just as you intended before. Users can view the apps in store and [request access to apps](user-requests-approve-apps).

After migration, any admin consent to app permissions that was previously granted is retained. App permissions are a different concept from permission policies, which app centric management is replacing. For more information, see [grant and manage consent to Teams app permissions](manage-consent-app-permissions).

### Understand the auto-migration process

Auto-migration maintains the same access defined in app permission policies when there's no conflict between a user’s assigned policies. If a user is assigned to a custom app permission policy that blocks an app, while the Global permission policy allows the same app, Microsoft auto-migrates the app as allowed for that user. During the auto migration, one security group is created for each custom app permission policy. All users currently assigned to an app permission policy are then added to the corresponding security group for that policy. These groups are assigned to each app they're allowed in their respective policy, maintaining their app access. Administrators manage these groups like any others to customize the app centric management assignments, such as adding and removing users or removing the group and replacing it with another group.

For more information on best practices before and after migration, see [best migration practices for app centric management](pre-and-post-migration).

## Add or modify app availability for users

To allow users to add and use an app or a Copilot agent, you must assign users or groups to an app. To make any app or Copilot agent available in your organization, ensure the following points:

- If your organization isn't migrated to unified app management, allow apps and Copilot agents in Teams admin center and under the **Integrated apps** page in [Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).
- If your organization is migrated to unified app management, allow apps and Copilot agents in Teams admin center or under the **Integrated apps** page in [Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).

Note

It takes up to 24 hours for the availability changes to take effect. In rare cases, it might take up to six days for the changes to reflect in the client.

To make any app or Copilot agent available to your organization in Teams admin center, follow these steps:

1. Go to the [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) page.
2. Search for the required app and select the app name to open its app details page.
3. Select the **Users and groups** tab.
4. Under **Select to manage who this app is installed for or available to in your organization**, select **Availability**.
5. Select **Edit availability**.
6. Select the required option from **Available to** menu. When assigning users or groups, search for the user or the group from the **Search for users or groups** menu. Select **Apply**.

    [![Screenshot shows how to define the app availability from the app details page.](media/acm-add-modify-access.png)](media/acm-add-modify-access.png#lightbox)
7. To remove one or more users or groups from an app, select the rows and select **Remove**.

    [![Screenshot shows how to remove the existing availability of an app from the app details page.](media/acm-remove-access.png)](media/acm-remove-access.png#lightbox)

Note

Apps and agents are available in both the Teams admin center and Teams, depending on the assigned tenant ring. For example, if a TAP tenant is assigned in Teams ring 1.2, the apps and agents from ring 1.2 are accessible to admins in the Teams admin center and to users in Teams.

## Default settings for app availability

In addition to defining the availability of an app, you can also control the default app availability of any new apps. You can control it for each type of app. For new organizations, the default setting is set to let users install apps by default. For existing organizations, old settings are mapped to new access settings.

To change this default setting, access [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) page, select **Actions** &gt; **Org-wide app settings**, and modify the required settings.

The Org-wide app settings apply to:

- All the new apps made available in Teams app store.
- All the existing apps that you didn't actively manage, that is, you didn't change the availability of.

Note

- Before app-centric management migration, org-wide settings had two separate controls for third-party apps—one for bulk-managing new apps and another for existing ones
- After migrating to app-centric management, a single control now manages bulk availability for both new and existing third-party apps. Toggle on to enable all new and existing third-party apps across the tenant; toggle off to disable all. App-level settings stay intact.

**Pre-ACM**

![Screenshot showing the pre acm third-party org-wide app settings in an organization.](media/pre-acm-third-party-app.jpg)

**With-ACM**

![Screenshot showing acm third-party org-wide app settings in an organization.](media/with-acm-third-party-app.jpg)

Pre app centric management, org-wide settings included two separate controls for third-party apps; one for managing availability of new apps in bulk, and another for existing apps.

Post app centric management migration, these are unified into a single control that governs bulk availability for both new and existing third-party apps. When you toggle ON, all apps are enabled and when you toggle OFF, all apps are disabled. This control doesn't override app-level configurations.

The Org-wide app settings don’t apply to:

- All apps that have user assignment set to Specific users and groups and saved by you.
- All apps that were assigned to Everyone or to No one and saved individually.
- Any blocked apps.

Consider a scenario where you started using the feature and all apps were assigned to everyone. Now, you changed an app's availability to a specific group or some users. After you save this change, if you change the Org-wide app setting titled **Let users install and use available apps by default**, then this particular app continues to be assigned to the specific group or users. Your change to the org-wide app setting applies only to those apps for which you didn't change the availability. Further, if you again change the **Let users install and use available apps by default** setting, the availability of all other apps is again impacted, except the app that you actively managed.

## View apps in your organization

You can view all apps in the catalog and easily access the app availability from the [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) page. You can sort and filter using all three types of app availability. To know about the Microsoft-provided apps, see [list of Microsoft created apps](apps-in-teams#list-of-apps-created-by-microsoft).

![Screenshot showing how to filter apps by combining various criteria such as app availability, app type, and app status.](media/acm-app-filter.png)

### View all apps available to a specific user

On the **[Manage users](https://admin.teams.microsoft.com/users)** page, select a user to open the user details page, and select the **Apps** tab. The tab lists the apps that the user has access to. To easily locate the type of access for an app, you can search for the name of the app.

![Screenshot showing how to view all the apps that a user has access to, from the Manage users page.](media/acm-manage-user-apps-tab.png)

Each app displays the type of its availability, which indicates how the user is assigned to the app: through availability to everyone, direct availability to a user, or through a group. The list shows only those apps that are assigned to the user and that are allowed in the organization for use. Apps assigned to no one and app that are blocked in the organization don't appear in this list.

You can remove app availability for a user. Select an app that is directly assigned to the user and select **Remove**. You can’t remove availability for a user if the app is available to everyone or to a group.

## View top apps insights to increase adoption

In Teams admin center, the **Popular apps in your org** widget on the **Manage apps** page displays two of the most-used third-party apps, that aren't already available or installed for everyone in the organization. These apps are in the top 40% of usage in the last 90 days and are displayed in descending order by usage.

If your tenant is migrated to the unified agent and app management experience, you can see the **Popular apps in your org** widget to analyze and install relevant apps. For more information, see [View top apps in tenants with unified agents and apps](uam-tac-mac#view-top-apps-in-tenants-with-unified-agents-and-apps). The widget doesn't appear if there are no top apps.

This widget helps you:

- Analyze app availability and improve adoption across your tenant
- Take recommended actions to install relevant apps for your users

To view the **Popular apps in your org** widget and analyze two of the most-used apps:

1. Sign in to [Teams admin center](https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=2ddfbe71-ed12-4123-b99b-d5fc8a062a79&amp;redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com%2fsignin-oidc&amp;response_type=code+id_token&amp;scope=openid+profile&amp;response_mode=form_post&amp;nonce=638917658808672430.YWRiYzMxZGItZjEzNC00NWI3LWJiYzEtNWY4NzZkODIyYWY2NGRjMzExMmEtNmIzNS00ODUzLTljNjYtZTM4NTQyNGIyN2U4&amp;post_logout_redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com&amp;msafed=0&amp;state=CfDJ8IHoJtwqQy9LlMNbw5zXYQhIf4GeP5tAJy87P-1rWtCUKdBuDZv0d5_iEc4tXqKavemC71QDLfznNlzL7Cnp7glApqFO9WBHkOLTvs9hTN3WCnysRBqygBnOp1iDtx_IjqNXxS8sBksi61bg2O8OBStOzw7BIH8fTF-JfbLH99OYna3UEUAJlAwhnqIWZhifubxj-jP9pz3A00vbtdNxOkz1f_jPlV8pNMuDlGh2pG3KIsKOQWRm80pDqmZG35FYXHVoyoPDNpWX4lisjZIFNag0gi5YCM5GmU7DydmIx96fDbcOciqeYxLF2t5EgnZ-177bfvEEFu7gS_lekvPqAaorvTnN6h2Hzl2ACgVc_plpIDiHQAHzb0YkAbGlNUbwlw&amp;x-client-SKU=ID_NET8_0&amp;x-client-ver=8.5.0.0&amp;sso_nonce=AwABEgEAAAADAOz_BQD0__1wpMWjufmyGkDH4GfzvQ4v-3Qrr5oR_7Roaasgh0cU3usNuIyMYV_sI4mfF88fPF8jL8ZPfH0qp7qgCr5M57UgAA&amp;client-request-id=118a4361-3ebe-4a41-ab17-0c7552b1c7dc&amp;mscrid=118a4361-3ebe-4a41-ab17-0c7552b1c7dc).
2. Go to **Teams apps** &gt; **Manage apps** to view the **Popular apps in your org** widget. It shows two of the most-used third-party apps in your organization based on random selection, the number of users using the app, and the **Allow for others** option.

    [![Screenshot showing the widget on the Manage apps page.](media/top-apps-widget-manage-apps.png)](media/top-apps-widget-manage-apps.png#lightbox)
3. *Optional*: Select the **information** icon on the widget and choose the **Apps usage report** link.

    [![Screenshot showing the Apps usage report link.](media/apps-usage-reports.png)](media/apps-usage-reports.png#lightbox)

    The **Usage reports** page opens and automatically generates a report for all the third-party apps, including two of the most-used apps shown on the widget, as per usage in the last 90 days.

    [![Screenshot showing analytical report on apps usage for all the apps.](media/apps-usage-report-analytics.png)](media/apps-usage-report-analytics.png#lightbox)

    Important

    The **Usage reports** data is sourced from the `Ideas`API and covers app usage beyond Teams.
4. Select **Allow for others** on the widget.

    [![Screenshot showing the Allow for others option on the widget.](media/allow-for-others-widget.png)](media/allow-for-others-widget.png#lightbox)

    The **Users and groups** tab opens, which shows the number of users for whom the selected app is available, and the actual number of users using the app. For example, if the selected app is available for eight users only but six users are already using it, this means it's popular and might be enabled for more users.

    [![Screenshot showing the Users and groups tab to edit app availability.](media/users-and-groups-tab-manage-apps.png)](media/users-and-groups-tab-manage-apps.png#lightbox)
5. Select **Edit availability** to make the app available for selected users or allow it for everyone to increase adoption.
6. Select **Apply** for the changes to reflect.

Alternatively, go to the **Dashboard** in Teams admin center, to view the **Popular apps in your org** widget, which shows three of the most-used third-party apps. These apps on the widget match those on the **Manage apps** page and appear in the same order, except for the third app. Select **Allow** to open the **Users and groups** tab, where you can view and analyze the number of users for whom the app is available and edit availability accordingly.

[![Screenshot showing the widget on the dashboard in Teams admin center.](media/dashboard-top-apps.png)](media/dashboard-top-apps.png#lightbox)

Note

To move or remove the widget, select the **More options (…)** menu in the top-right corner of the widget.

## Mapping between old permission policies and new app availability

When your tenant's admin center receives this feature, the following updates are made to the app access. The access to apps doesn't change and the update only maps your existing permission policies to new availability.

| App permission policy and org settings earlier | Org-wide app settings while using this feature |
| --- | --- |
| Global permission policy for Microsoft apps was `Allow all` or Global permission policy for Microsoft apps was `Block an app(s), allow all others` | `Allow users install available apps by default` for Microsoft apps is set to on |
| Global permission policy for Microsoft apps was `Block all` or Global permission policy for Microsoft apps was `Allow app(s), Block all others` | `Allow users install available apps by default` for Microsoft apps is set to off |
| Third-party app setting in the Org-wide app settings was set to on; New third-party app setting in the org-wide app setting was set to on; Global permission policy for third- party apps was `Allow all`; or Global permission policy for third-party apps was `Block an app(s), allow all others` | `Allow users install available apps by default` for third- party apps is set to on |
| Third-party app setting in the Org-wide app settings was set to off; New third-party app setting in the org-wide app setting was set to off; Global permission policy for third-party apps was `Block all`; or Global permission policy for third-party apps was `Allow app(s), Block all others` | `Allow users install available apps by default` for third-party apps is set to off |
| Third-party app setting in the Org-wide app settings was set to on; New third-party app setting in the org-wide app setting was set to off; Global permission policy for third party apps was `Block all`; or Global permission policy for third-party apps was `Allow app(s), Block all others` | `Allow users install available apps by default for third party apps` is set to off |
| Third-party App Setting is off; permission policy is `Block an app(s), allow all others` | `Allow users install available apps by default for third party apps` is set to off |
| Global permission policy for Custom apps was `Allow all` or Global permission policy for Custom apps was `Block an app(s), allow all others` | `Allow users install available apps by default` for custom apps is set to on |
| Global permission policy for custom apps was `Block all` or Global permission policy for custom apps was `Allow app(s), Block all others` | `Allow users install available apps by default` for custom apps is set to off |

| App status earlier | Permission policy applied earlier | App availability when using this feature |
| --- | --- | --- |
| Blocked | Blocked | No one can install |
| Blocked | Allowed | No one can install |
| Allowed | Blocked | No one can install |
| Allowed | Allowed | Everyone |

## Considerations and known limitations

- You can add up to 99 users or groups at a time to an app.
- When searching for users or groups to add, the UI displays only 20 results. If you don't find the expected results, refine your search query to use the exact name.
- After migration, your blocked apps continue to remain unavailable to users. The status of such apps is `unblocked` now but the apps are available to `No one` in the `Available to` column on the Manage apps page. It means that no org user can use the app as you intended before.
- After you switch to this feature, you can't access, edit, or use permission policies. Once your organization migrates, you can't revert the migration.
- You can't update app availability in bulk in Teams admin center, but you can do so through PowerShell. For more information on PowerShell cmdlets for app availability, see [Update-M365TeamsApp](/en-us/powershell/module/teams/update-m365teamsapp?view=teams-ps&amp;preserve-view=true).

Details of automatic migration for app permission policies:

- During the migration, [create one security group](/en-us/microsoft-365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide&amp;preserve-view=true) per custom app permission policy. All users assigned to the app permission policy are assigned to the corresponding groups.
- After the migration, you can view and manage the groups.
- There's no change of app permissions during the migration, except where an app is allowed in the global policy but blocked in the custom app permission policy. Here, the app is available to all users of the tenant, except for EDU customers, for whom it will be available to none. This is the only instance where there's a change in app permissions in the tenant. Admins can modify this behavior as desired post migration.