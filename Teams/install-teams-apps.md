---
layout: Conceptual
title: Preinstall Teams apps for your org users - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/install-teams-apps
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
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.date: 2026-02-27T00:00:00.0000000Z
ms.collection:
- M365-collaboration
- tier2
- highpri
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: How IT professionals preinstall Teams apps for users, in channels, and in meetings and manage the installation options of apps.
ms.localizationpriority: medium
locale: en-us
document_id: 06c05cda-5654-a3b6-c7de-02dbbaa36633
document_version_independent_id: 06c05cda-5654-a3b6-c7de-02dbbaa36633
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/install-teams-apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: install-teams-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/install-teams-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 8852d111-f5e1-56b6-d204-9702b10fd8c1
---

# Preinstall Teams apps for your org users - Microsoft Teams | Microsoft Learn

Admins can install Microsoft Teams apps that work on Microsoft Outlook and the Microsoft 365 app (formerly known as Office.com) for some or all users in their organization. You can easily preinstall the apps on the supported hosts so that your users receive the apps easily. Alternately, users install apps on their own if you [make apps available to users for use](manage-apps#allow-or-block). You can proactively install apps for users so that you help them discover apps easily, ensure app retention, and save user's effort to install. For example, you can install IT helpdesk or ticketing app for all new employees to provide an easy and quick way for the new joiners to seek IT support.

## Preinstall apps in user's Teams client

Unified app management changes a few app governance methods. Previously, you used app setup policy to preinstall apps for users. If your organization is now migrated to use app centric management feature, then you use it to preinstall apps. Follow the applicable method to provide apps to your users, without them having to install apps on their own.

You can't preinstall certain apps for users because many of these apps do not support the scopes required for admin installation. You can't select these apps in the **Setup policies** page and are denoted as -- in the **Manage apps** page when migrated to app centric management.

### Install apps using app setup policy

Note

- Once app centric management is generally available, any installs using app setup policy will be in read only mode. For more information about availability of app centric management, see [Microsoft 365 roadmap ID 394274](https://www.microsoft.com/microsoft-365/roadmap?filters=&amp;searchterms=394274), [Microsoft 365 roadmap ID 500637](https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=&amp;searchterms=500637) and for timeline, see [Message Center post MC795355](https://admin.microsoft.com/Adminportal/Home?ref=MessageCenter/:/messages/MC795355).
- Existing installed apps using app setup policies will remain intact. However, no new additions are permitted, and only deletions are allowed. Instead, you can install Teams apps for selected users, groups, or all users directly from the respective app. Other settings in app setup policies, including Pinned apps, will remain unchanged.

If you aren't using app centric management, then you preinstall apps using app setup policy. To know more, see [overview of app setup policy](teams-app-setup-policies). Ensure that the following prerequisites are met.

- Allow use of apps in your org using the options in the [Org-wide app settings](manage-apps#manage-org-wide-app-settings).
- Allow the required apps. [Admins can block an app](manage-apps#allow-or-block) or [Developers can block their app by default](/en-us/microsoftteams/platform/concepts/deploy-and-publish/add-default-install-scope#block-apps-by-default-for-users-until-an-admin-approves).
- If an app requires permission to access organization information, [grant consent to the app permissions](manage-consent-app-permissions#grant-and-manage-consent-to-teams-app-permissions).
- Make the app available to the required users and groups using app permission policies.

To install apps using the policy, follow these steps:

1. Sign in to Teams admin center, access **Teams apps** &gt; **[Setup policies](https://admin.teams.microsoft.com/policies/app-setup)**.
2. Edit the existing global policy if your change applies to all users. Otherwise, select **Add** to create a new custom policy that you can apply to some users. Provide a name and description of the policy.
3. Under **Installed apps**, select **Add apps**.
4. In the **Add installed apps** pane, search the apps that you want to add in the Teams client of the allowed users. Select **Add**.

    [![Screenshot showing how admins preinstall apps using app setup policy.](media/admin-installed-apps.png)](media/admin-installed-apps-large.png#lightbox)

### Install apps using app centric management

If your organization is using app centric management, then you preinstall apps using its UI. For more information about availability of app centric management, see [Microsoft 365 roadmap ID 394274](https://www.microsoft.com/microsoft-365/roadmap?filters=&amp;searchterms=394274), [Microsoft 365 roadmap ID 500637](https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=&amp;searchterms=500637) and for timeline, see [Message Center post MC795355](https://admin.microsoft.com/Adminportal/Home?ref=MessageCenter/:/messages/MC795355). To start using app centric management, see [use and migrate to app centric management](app-centric-management).

Note

If you previously used app setup policies to install apps and now migrate to app centric management, then your policy settings will not be automatically migrated to the new experience.

Before you preinstall apps using app centric management, ensure that the following prerequisites are met.

- Allow use of apps in your org using the options in the [Org-wide app settings](manage-apps#manage-org-wide-app-settings).
- Allow the required apps. Individual apps can be [blocked by an admin](manage-apps#allow-or-block) or can be [blocked by the developer](/en-us/microsoftteams/platform/concepts/deploy-and-publish/add-default-install-scope#block-apps-by-default-for-users-until-an-admin-approves).
- [Grant consent to the app permissions](manage-consent-app-permissions#grant-and-manage-consent-to-teams-app-permissions) if an app requires permission to access organization information.

To install apps using the app centric management UI, follow these steps:

1. Log into Teams admin center and access **Teams apps** &gt; [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps/) page. Do one of the following tasks:

    - Select an app, and click **Edit installs**. Select whom to install the app for and select **Apply**.

        [![Screenshot showing app installation option for admins on the Manage apps page.](media/app-install-manage-apps-page.png)](media/app-install-manage-apps-page.png#lightbox)
    - Alternately, you can install an app from the app details page.

        1. Select **Users and groups** &gt; **Installs** &gt; **Install app**.
        2. Select whom to install the app for and select **Apply**. The app is made available to the selected users and groups and there's no need to separately make the app available for the same users and groups.

        [![Screenshot showing app installation option for admins on the app details page.](media/app-install-app-details-page.png)](media/app-install-app-details-page.png#lightbox)

## Install apps in an existing team

Apps in teams allow better collaboration for the users. You can also install an app in a team to improve app discovery and usage. To add apps in teams that will be created in the future, [add apps to a teams template](/en-us/microsoftteams/get-started-with-teams-templates-in-the-admin-console). To add apps in the existing teams, follow these steps.

1. On Manage apps page, search for an app and select it.
2. Select **Add to team**.

    [![Screenshot showing the option for admins to add an app to specific teams.](media/add-app-team.png)](media/add-app-team.png#lightbox)
3. In the **Add to team** pane, search for the team you want to add the app to, select the team, and then select **Apply**.

## Preinstall apps in a new team using team creation template

You can create a new team for your users using a team template. Team template lets you, as an admin, to add apps in template so that the new teams that are created, have these apps available from the beginning, for the users of the team. For more info, see [add apps when creating a team template](create-a-team-template) and [get started with team templates](get-started-with-teams-templates-in-the-admin-console).

## Understand how users install apps

If the app installation prerequisites are met, [users can install apps](https://support.microsoft.com/office/add-an-app-to-microsoft-teams-b2217706-f7ed-4e64-8e96-c413afd02f77) on their own. If an app is blocked, then the users can [request admin approval](user-requests-approve-apps).

From the store in their Teams client, users install apps for their personal use by selecting **Add** option or install apps in their teams and channels by selecting **Add to team** option. Option to add an app to a team is available for only those apps that can work in a team scope.