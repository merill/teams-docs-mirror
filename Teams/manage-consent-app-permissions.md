---
layout: Conceptual
title: Grant and manage consent to Teams app permissions - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-consent-app-permissions
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: NickWalk
ms.author: nickwalk
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
ms.date: 2026-09-07T00:00:00.0000000Z
ms.reviewer: Orion.OMalley
description: Manage consent to Teams apps permissions to access the required org information.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: bf5cd6bd-409d-109e-b928-7d69b265e2ad
document_version_independent_id: bf5cd6bd-409d-109e-b928-7d69b265e2ad
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-consent-app-permissions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-consent-app-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-consent-app-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c86aba17-452e-4de2-e1e5-dc92a9e45fe3
---

# Grant and manage consent to Teams app permissions - Microsoft Teams | Microsoft Learn

Using Teams apps can provide an incredible boost to the productivity of and collaboration between your organization's users. Teams apps bring information to your users without any context switching and help them do great work. As an admin, you play a critical role in empowering your users with the right type of apps while balancing your company's need for security and compliance. Once you decide to approve the use of an app, ensure that the app adoption is smooth for the users.

A crucial part of the process is granting consent to the permissions that an app needs to work. Your consent for approved apps is critical so that each user in your organization doesn't have to review permissions and consent individually when they start the app. A few examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users. To learn more about permissions and consent, see [Permissions and consent in the Microsoft identity platform endpoint](/en-us/azure/active-directory/develop/v2-permissions-and-consent).

To safeguard company's needs and adhere to its policies, only Global Administrators can grant consent to apps permissions on behalf of all users in your organization. The option to view details and requirement to grant consent applies to custom and third-party apps, and not to the [apps provided by Microsoft](apps-in-teams#types-of-teams-apps).

## View Microsoft Graph permissions requested by an app

On the [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps) page, the **Permissions** column indicates whether an app has permissions that need consent. Select the **View details** link for an app to view the various permissions and access to organization's information that the app requests. The option to view details and grant consent applies to custom and third-party apps, and not to the [apps provided by Microsoft](apps-in-teams#types-of-teams-apps).

## Grant org-wide admin consent to an app's permissions

When you grant consent to these permissions, you allow an app to access your organization's information. Carefully review the permissions the app requests before you grant consent. For more information, see [Teams apps permissions and consent](app-permissions). Only Global Administrators can grant consent to the Graph permissions that an app requests. Teams Administrators can view the required permissions in admin center. The option to view details and grant consent applies to custom and third-party apps, and not to the [apps provided by Microsoft](apps-in-teams#types-of-teams-apps).

To view and grant consent for all users in your organization, follow these steps:

1. In Teams admin center, access **Teams apps** &gt; **[Manage apps](https://admin.teams.microsoft.com/policies/manage-apps)**.
2. Search for the required app and then perform one of the following actions:

    - Select the **View details** link in the Permissions column of the app, to open the **Permissions** tab.
    - Select the app name to go to the app details page and select the **Permissions** tab.

    ![Screenshot showing the option to grant consent to Graph permissions requested an app.](media/app-grant-consent-option.png)
3. Review the permissions requested by the app in the dialog box that opens.

    ![Screenshot showing the dialog that accepts consent for the permissions requested by an app.](media/app-grant-consent-dialog.png)
4. Select **Accept** to grant consent, if you agree with the permissions requested by the app. A confirmation message lets you know that consent is available for the app. The app now has access to the specified resources for all users in your organization for whom the app is allowed. Users aren't prompted now to review the permissions.

    ![Screenshot showing the granted consent to app permissions.](media/success-message-granted-permissions.png)

Note

In the new version of the app, if the developer adds extra permissions that require admin consent, users can't use the app until you grant consent to the updated app.

## Let users grant consent to low risk Graph permissions

You can configure user consent settings to let users consent to selected permissions (recommended approach) and use apps that require only these specific permissions without needing admin consent.

This approach works together with permissions classification in Microsoft Entra ID portal. The classification let admins define some Delegated Graph permissions as low risk permissions within their organization. Admins decide which low risk permissions based on their organization's risk posture. As a safety measure, you can't categorize application permissions as low risk.

You can configure user consent settings in way that lets users to:

- Not be able to consent to any apps and hence use only admin-approved apps.
- Consent to selected permissions (recommended approach) and use app that required only these specific permissions.

The recommended approach works together with permissions classification. The classification let admins define some or all of the Delegated Graph permissions as low risk permissions within their organization. Admins decide low risk permissions based on their organization's risk posture. As a safety measure, you can't categorize Application permissions as low risk. Application permissions require only an admin to consent. For more information, see [configure how users consent to applications](/en-us/azure/active-directory/manage-apps/configure-user-consent?pivots=portal) and [how to classify permissions as low or high risk](/en-us/azure/active-directory/manage-apps/configure-permission-classifications?pivots=portal).

The roles that can accomplish this configuration are Global Administrator, Application Administrator, or Cloud Application Administrator. We recommend using a lower privilege role such as Application Administrator.

## Check and verify granted consent to permissions

After you grant consent to an app's permissions, the **Permissions** tab shows a confirmation that consent is available for the app permissions. If you want to view details for each app permission, follow these steps:

1. Sign in to [Microsoft Entra admin center](https://entra.microsoft.com).
2. Select **Applications** &gt; [**Enterprise applications**](https://entra.microsoft.com/#view/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/%7E/AppAppsPreview).
3. Select an application to view its permissions. Select **Permissions** in the applications page.

    [![Screenshot showing Microsoft Entra UI used to view and manage the granted consent to an app's permissions.](media/consented-perms-entra.png)](media/consented-perms-entra-large.png#lightbox)
4. Select a permission to see more details about it.

    ![Screenshot showing details of a selected permission.](media/graph-permission-details.png)

## Revoke granted consent to permissions

To revoke the consent that you granted to an app, follow these steps:

1. In the **Permissions** tab, select the **Microsoft Entra ID** link to open the app's permissions in Microsoft Entra admin center.
2. In the **Admin consent** tab, choose the permission you want to revoke and then select the ellipses `...`.
3. Select **Revoke Permission** and then select **Yes, revoke** in the confirmation dialog.

    ![Screenshot showing the option to revoke a Graph permission of an app from the Microsoft Entra admin center.](media/consented-perms-entra-revoke.png)

After you revoke consent to some permissions, you can grant consent again. For more information, see Grant org-wide admin consent to an app's permissions.

## Grant consent to new Graph permissions after an app update

Developers update apps to add new functionality, enhance existing functionality, or fix bugs. Some app updates add new permissions that weren't part of the previous version of the app. If the developer adds any new permissions that require admin consent, you must consent to the new permissions. The reconsent flow is the same as described in Grant org-wide admin consent to an app's permissions.

To learn about app changes that require consent from a user or an admin, see [conditions when an app update requires consenting](apps-update-experience). Depending on your organization's configuration, users might be able to grant consent to some types of permissions.

## View resource-specific consent permissions of an app

Resource-specific consent (RSC) permissions let an app access and modify a team's or a user's data. RSC permissions are granular and specific to the Teams team in which an app is added. A few examples of RSC permissions are the ability to create and delete channels in a team, get the settings for a team, and create and remove channel tabs.

You define RSC permissions in the app manifest, not in Microsoft Entra admin center. Team owners can grant consent for these permissions when they add the app to a team or a chat. For more information, see [Resource-specific consent (RSC)](/en-us/microsoftteams/platform/graph-api/rsc/resource-specific-consent).

You can view RSC permissions for an app in the **Permissions** tab of the app details page. The RSC permissions are listed along with the other permissions under the sections of Application and Delegated permissions.