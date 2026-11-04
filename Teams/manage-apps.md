---
layout: Conceptual
title: Manage your apps in the Microsoft Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-apps
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
ms.date: 2026-07-05T00:00:00.0000000Z
ms.collection:
- M365-collaboration
- tier2
- highpri
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Learn how to manage Teams apps. Learn to allow or block apps, check org-level status and app properties, upload custom apps, and manage app settings.
ms.localizationpriority: high
locale: en-us
document_id: fbbcabee-fa96-2878-e983-3c966f84ee15
document_version_independent_id: 02fa4fd8-77e0-5cb2-a4af-576cbb68322f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: bd3d3e03-7233-6946-67eb-97c3ed794168
---

# Manage your apps in the Microsoft Teams admin center - Microsoft Teams | Microsoft Learn

The Teams admin center includes dedicated pages and UI experiences for managing agents and apps. You can view and manage all agents and apps that are available in Teams for your organization from the [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps) and [Built-in Teams agents](https://admin.teams.microsoft.com/policies/built-in-teams-agents) pages.

Microsoft 365 agents and apps can be managed from both the Teams admin center and the Microsoft 365 admin center.

From the **Manage apps** page, you can review agents and apps before allowing them, access support information, and control their availability across your organization, either per user or per app. Starting from April 2025, tenants are automatically migrated to [app centric management](app-centric-management).

[![Screenshot showing the Manage apps page in Teams admin center.](media/manage-apps-policy-org.png)](media/manage-apps-policy-org.png#lightbox)

The Teams admin center now includes **Apps to consider allowing** tile on the Manage apps page. This tile displays counts of **Microsoft 365 certified** and **publisher-attested** agents and apps, helping admins quickly identify trusted agents and apps. Select a count to filter the list and simplify management.

A new **Security and Compliance** tab on each app’s details page displays its certification status, publisher attestation, and key security attributes etc. For more information, see [App compliance program for security, data handling, and privacy](overview-of-app-certification).

To use Teams admin center, you must have a Teams Administrator role. Some admins with a higher privilege role can accomplish agent and app governance tasks but we recommend using the lower privilege role where possible. For details, see [Teams administrator roles](using-admin-roles) and [Microsoft 365 administrator roles](/en-us/microsoft-365/admin/add-users/about-admin-roles).

Note

You can only view and manage agents and apps that are deployed in the same release channel as your tenant is. For example, if your tenant is in the general release then you can't manage agents and apps that are deployed in the private or public preview channels. This isn't an issue for agents and apps that are released to the general release channel.

## Agent and app management use cases and the available interfaces

Management tasks that are supported in admin center are tabulated as follows.

| **Management use cases** | **Link to the interface** | **Documentation** |
| --- | --- | --- |
| Control which agents and apps are available to users in your organization by allowing and blocking them. You can also upload and approve custom agents and apps. After managing agents and apps on this page, you can use app permission and setup policies to configure what agents and apps are available for specific users in your organization's agent and app store. | [Manage apps in Teams admin center](https://admin.teams.microsoft.com/policies/manage-apps) | Current article |
| Specific users and groups that you select can access the agent or app. Supported group types include Security groups, Microsoft 365 groups, Dynamic user membership groups, Nested groups, and Distribution lists. Guest users can't access the agent or app, even if they’re assigned to it. | [TAC-Dashboard](https://admin.teams.microsoft.com/dashboard) | [Access Control for Apps](/en-us/microsoftteams/app-centric-management) |
| You can customize the Teams agent and app store with your organization's logo, custom background, or color. | [Customize store](https://admin.teams.microsoft.com/policies/customize-appstore) | [Customize your organization's app store](/en-us/microsoftteams/customize-your-app-store) |
| The Teams agent and app usage report provides information about which agents and apps in use, active users, and other usage information. | [Usage reports](https://admin.teams.microsoft.com/analytics/reports) | [Teams app usage report](/en-us/microsoftteams/teams-analytics-and-reports/app-usage-report) |
| Your users can add agents and apps when they host meetings or chats with guests. They can also use agents and apps shared by guests when they join meetings or chats hosted externally. The data policies of the hosting user's organization, and the data sharing practices of any third-party agents and apps shared by that user's organization, are applied. | [External access](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [App behavior depending on types of users](/en-us/microsoftteams/apps-external-users) |
| With guest access, you can provide access to applications and other Teams functionality to people outside your organization, while maintaining control over your corporate data. | [Guest access](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Guest access in Teams](/en-us/microsoftteams/guest-access) |
| Teams update policies are used to manage Teams and Office preview users who can see prerelease or preview features in the Teams app. | [Teams update policies](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams public preview](/en-us/microsoftteams/public-preview-doc-updates) |

## Agent and app governance

### Manage org-wide app settings

Use org-wide agent and app settings to control whether users with an [F license](https://www.microsoft.com/en-in/microsoft-365/enterprise/frontline) get the tailored frontline agent and app experience. Check if users can install third-party agents and apps, or upload custom agents and apps in your organization. If there are no admin configured agent or app settings, then org-wide settings are the default.

1. On [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps) page, under the **Actions** menu, select **Org-wide app settings**. You can then configure the settings in the pane. [![Screenshot of Teams admin center Org-wide app settings showing toggles for tailored, Microsoft, third-party, and custom apps.](media/manage-apps/org-wide-app-settings-teams.png)](media/manage-apps/org-wide-app-settings-teams.png#lightbox)
2. Under **Tailored apps**, turn off or turn on **Show tailored apps**. When this setting is on, users with an [F license](https://www.microsoft.com/en-in/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt&amp;preserve-view=true) get the tailored frontline agent and app experience. This experience pins the most relevant agents and apps in Teams for frontline workers. To learn more, see [Tailor Teams apps for your frontline workers](/en-us/microsoft-365/frontline/pin-teams-apps-based-on-license). This feature is available for F licenses.
3. Under **Microsoft apps**, a single control automatically enables users to install and use any available agents and apps by default.

    Note

    Built-in Teams agents are embedded directly into core Teams experiences and don't require installation from the app store. Examples include Channel Agent, Facilitator, and other built-in agents. These agents are no longer controlled by the Microsoft apps setting. You now manage them from the dedicated **Built-in Teams agents** page in the Teams admin center.
4. Under **Third-party apps**, a single control manages the bulk availability of both the new and existing third-party agents and apps.
5. Under **Custom apps**, turn off or turn on **Let users install and use available apps by default** option. This setting controls whether users can install and use the custom agents and apps that you make available to them. To learn more about custom agents and apps, see [how to manage custom apps](/en-us/microsoftteams/teams-custom-app-policies-and-settings).
6. Select **Save**. The settings take effect after a few hours.

Admin center settings might allow your users to collaborate with users from other organizations. To understand how agents and apps work with external users in meetings, see [Teams apps for external attendees](/en-us/microsoftteams/apps-external-users).

#### Install or allow users to install and uninstall

IT admins can install Teams agents and apps for some or all users in their organization. Developers might create some Teams agents or apps to work on Outlook and Microsoft 365 Apps (formerly office.com). You can easily preinstall them on all the supported hosts. Alternately, you can let users install agents and apps on their own. A few supported agents and apps can also be auto installed if a user uses it outside Teams. For details, see how to preinstall apps.

### Manage org-wide app settings for Microsoft 365 Government

In a Microsoft 365 Government - GCC, GCCH and DoD deployment of Teams, all third-party agents and apps are blocked by default. In GCC, you see the following note about managing third-party agents and apps on the app permission policies page in the Microsoft Teams admin center.

[![Screenshot of Teams admin center App permission policies page with a warning about third-party apps and policy options.](media/manage-apps/app-permission-policies-teams.png)](media/manage-apps/app-permission-policies-teams.png#lightbox)

### Manage apps in 21Vianet and air-gapped cloud environments

In Microsoft 365 operated by 21Vianet and air-gapped cloud environments, you get an overview of the apps on the **Teams apps** &gt; **Manage apps** page.

To view more details of an agent or app, select the agent or app's name to access the app details page. You can allow or block the agent or app for your users.

### Allow or block

As an admin, you control access to all types of agents and apps that are used across your organization. Know the different Types of Apps, which you can access. Teams provides granular controls to configure access for each agent and app and for each user. To allow an agent or app, you must do all of the following settings. To block an agent or app, use any one of the following settings:

| **Method** | **Scope** | **Use case** |
| --- | --- | --- |
| [Org-wide app settings](/en-us/microsoftteams/manage-apps) | Org-level | Use this setting to allow use of relevant apps in your org. |
| [App centric managemen](/en-us/microsoftteams/app-centric-management) | User-level | Let all users or let specific users use an app. |

You can allow or block specific agents and apps on either the **Manage apps** page or in the app details page. If your organization isn't migrated to unified app management, allow or block the agent or app in Teams admin center and under the **Integrated apps** page in [Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?view=o365-worldwide&amp;preserve-view=true). If your organization is migrated to unified app management, allow or block the agent or app in Teams admin center or under the **Integrated apps** page in [Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?view=o365-worldwide&amp;preserve-view=true). See [Unified agent and app management](/en-us/microsoftteams/uam-tac-mac)to understand how you can unify agents, apps availability across both the admin centers.

The [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps) page displays all the available agents and apps and the current org-level app status. To allow or block an agent or app in TAC, follow these steps:

1. Sign in to the Teams admin center and access **Teams apps** &gt; **Manage apps**.
2. Select the app on the **Manage apps** page and select **Allow** or **Block** option. [![Screenshot of Manage apps in Teams admin center with two apps selected and Allow or Block options highlighted.](media/manage-apps/manage-apps-allow-block-options.png)](media/manage-apps/manage-apps-allow-block-options.png#lightbox)
3. Alternately, click on the agent or app name to open its details page. Change status between **Allowed** and **Blocked**. [![Screenshot of Viva Engage app details in Teams admin center with Status toggle set to Allowed.](media/manage-apps/manage-apps-viva-engage.png)](media/manage-apps/manage-apps-viva-engage.png#lightbox)

Use agent and app assignment through [app centric management](/en-us/microsoftteams/app-centric-management) to define user access for agents and apps. The previous [App permission](/en-us/microsoftteams/teams-app-permission-policies) policies is deprecated.

When a developer publishes an agent or app to the Teams store, some may need an admin to configure it. Before an admin allows an agent or app, it shows as Blocked by publisher in the admin center. Before you allow it for users, follow the publisher's guidance to configure it.

To block all third-party agents and apps, open the **Org-wide app settings** on the [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps) page and disallow the use of third-party apps. With app centric assignment you can also block [apps created by Microsoft](/en-us/microsoftteams/apps-in-teams).

Note

From within the Teams client, your users can request you to allow the agents and apps that aren't available for them. You receive notifications and can allow it. For details, see [**View and manage user requests**](/en-us/microsoftteams/user-requests-approve-apps). If your organization is migrated to unified app management, you can allow agents and apps in Teams admin center or under the **Integrated apps** page in [Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?view=o365-worldwide&amp;preserve-view=true). For more information, see [Unified agent and app management](/en-us/microsoftteams/uam-tac-mac). Until your tenant is migrated to unified app management, ensure that the settings in both admin centers, such as blocked apps or org-wide app settings, remain synchronized. This measure prevents unexpected disruptions or issues with agent and app functionality.

## Export agent and app catalog as CSV

As an admin, you can export the entire agent and app catalog for your org from the Teams admin center. It can help you to coordinate with admin and security teams to evaluate agents and apps, verify availability, verify status, and more.

[![Screenshot of Teams admin center app catalog with search bar, export CSV button, and app list with status and availability columns.](media/manage-apps/manage-apps-export-csv.png)](media/manage-apps/manage-apps-export-csv.png#lightbox)

[![Screenshot of exported CSV file showing columns for app name, status, availability, publisher, and certification.](media/manage-apps/exported-app-catalog-columns.png)](media/manage-apps/exported-app-catalog-columns.png#lightbox)

## Manage built-in Teams agents

Built-in Teams agents like Channel Agent, Facilitator, and other built-in agents available across chats, channels, and meetings are managed from the **Built-In Teams agents** page, not the **Manage apps** page. To view and manage built-in agents:

1. Sign in to the **Teams admin center** and go to **Teams apps** &gt; **Built-in Teams agents**.
2. To change who can use an agent, select one or more agents and choose **Edit availability**. You can make an agent available to everyone, to specific users or groups, or to no one.

    [![Screenshot of the Built-in Teams agents page highlighting Edit availability.](media/manage-apps/built-in-teams-agents.png)](media/manage-apps/built-in-teams-agents.png#lightbox)

## Support information for agents and apps

You might have queries about admin settings or configuration, user flows and agent and app features, troubleshooting, and more. You can receive support information about agents and apps from the following two different sources:

- We don't provide direct customer support for Teams agents and apps but we provide the following safeguards, health checks, and certification methods for apps:

    - We proactively check Teams agents and apps for issues and inform the developer to update their agent or app. Scenarios covered are related to agent or app health, functional issues reported by users to Microsoft, security issues, and so on. For details, see [Microsoft enforcement actions for published apps](/en-us/microsoftteams/platform/concepts/deploy-and-publish/appsource/post-publish/overview).
    - For Publisher Attested and Microsoft 365 certified agents and apps, Microsoft offers [security and compliance information](/en-us/microsoftteams/overview-of-app-certification). If app developers consent, Microsoft provides admins with the option to [download the detailed evidence submitted by developers](/en-us/microsoftteams/overview-of-app-certification) during the certification audits for agents or apps.
    - We test all agents and apps as part of its [app validation program](/en-us/microsoftteams/overview-of-app-validation) to ensure that all agents and apps work as advertised. If they don't work as suggested in the store listing, then we contact app developers to request an update to the agent or app. If app developers don't make the requested updates after a few reminders, we proactively remove the agent or app from Teams.
    - Certification of agents or apps using [Microsoft 365 app compliance program](/en-us/microsoftteams/overview-of-app-certification) ensures that agents and apps are compliant with the industry-standard frameworks.

## Developer-provided agent and app information, support, and documentation

- App developers provide customer support, publish updates and fixes, and share security, compliance, and service agreement details through the admin center app page. For direct support requests and inquiry about agent or app updates, contact the app developer at their website address available at the following two places:

    - **App details** page of the app in [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) page in Teams admin center.

    [![Screenshot that shows documentation links in the admin center for an app in its details page.](media/app-details-summary.png)](media/app-details-large.png#lightbox)

    - **Details + support** tab of the agent or app's [AppSource](https://appsource.microsoft.com/) page.

    [![Screenshot that shows help and support link for a Teams app in AppSource.](media/appsource-help-link.png)](media/appsource-help-link.png#lightbox)
- **Privacy and data access considerations**: In the terms of use and privacy policy of any agent or app, the app developer discloses what data their agent or app uses and how it handles the data. This information is available on app developer's website and you can access the URLs in the app details page in Teams admin center. Many app developers choose to undergo the Microsoft 365 app compliance program. The program checks and audits an agent or app against controls that are derived from leading industry-standard frameworks. The detailed information about each such agent or app is available at [Teams Apps Security and Compliance](/en-us/microsoft-365-app-certification/teams/teams-apps).
- App developers can provide their contact information that you can use to chat with them. It helps you quickly evaluate an agent or app and get the needed information from the app developers before you adopt and roll it out. Examples include compliance information, certifications, data handling practices, pricing details for paid apps, and setup instructions. You can start a chat with app developers by selecting **Start a Teams chat** but only if the app developer provided their contact information. We recommend that you don't share personal and sensitive information in the chat [![Screenshot showing the option in the app details page that lets you chat with app developer.](media/chat-with-app-dev.png)](media/chat-with-app-dev-large.png#lightbox)