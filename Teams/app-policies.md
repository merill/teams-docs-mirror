---
layout: Conceptual
title: Overview of app policies to manage apps in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/app-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: SerdarSoysal
ms.author: serdars
manager: prkosh
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-apps
ms.date: 2026-05-22T00:00:00.0000000Z
ms.reviewer: mhayrapetyan
search.appverid: 
description: Learn about app permission policies and setup policies that are used to manage apps in Microsoft Teams.
audience: admin
ms.localizationpriority: high
ms.collection:
- M365-collaboration
locale: en-us
document_id: dcb5cdf7-9a02-cdf2-e152-38db69f0ae79
document_version_independent_id: d8e429a0-296d-1bf9-fb21-1ce13a6a59c3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/app-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/app-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ff5a0d1f-99b6-5386-f629-895353834980
---

# Overview of app policies to manage apps in Teams - Microsoft Teams | Microsoft Learn

Microsoft Teams uses app policies to govern access to and use of all apps and upload of custom apps. App policies help Teams Administrator control the following app behavior:

- Configure the access of apps for each individual user or for a group of users. You control the apps that each user can use.
- Pin the allowed apps for the desired users. Also, admins can install apps for users without user intervention. It helps users easily get started with the relevant apps.
- Allow or disallow upload and use of custom apps for a few or all the users.

As an alternate, you can use [app centric management](app-centric-management) to configure the access to apps on a per-app basis. The app centric management feature let admins specify the users and group in their organization who can add Teams apps on a per-app basis, instead of relying on permission policies.

## App permission policies

Important

If your organization is using app centric management feature to manage access to apps, see [Manage access to Teams apps using app centric management](app-centric-management). Permission policies don't apply and you may see this message on the policy page.

![Screenshot showing the permissions policy change for organization that are using app centric management.](media/acm-policy-page.png)

With app permission policies, Teams admin control what apps are available to each user in their organization. You can allow a few apps for all users, you can allow a few apps for a specific group of users, or you can allow specific apps for specific users. App permission policies work in tandem with Org-wide app settings and allow or block status of each individual app.

The app permission policies apply to all the [types of apps available in Teams](apps-in-teams). Some example scenarios in which you use app permission policies are:

- Gradually roll out an app to some users initially and to all users eventually.
- Allow a custom app for recruiting and talent management for only members of your HR department and block it for all other organization users.

![Screenshot of app permission policy.](media/app-permission-policy-trimmed.png)

To learn more, see [how to manage app permission policies](teams-app-permission-policies).

## App setup policies

App setup policies let you configure how and where are apps available for users in their Teams client. You choose the apps that you want to pin to the app bar in the Teams clients and define the order in which apps are displayed.

Pinning or installing apps helps drive awareness and adoption of the desired apps in your organization. The changes apply to web, desktop, and mobile Teams clients.

Some example scenarios in which you use app setup policies are:

- Pin a custom recruiting and talent management app for members of your HR team.
- Change the order of the [Core apps](apps-in-teams#core-apps) using pinning for your organization's users.

[![Screenshot of app setup policy in Teams admin center.](media/app-setup-policy-trimmed.png)](media/app-setup-policy.png#lightbox)

To know more, see [how to manage app setup policies](teams-app-setup-policies).

### Option to upload custom apps

Your organization may commission the creation of custom apps for org-specific requirements. Developers within your organization can build, test, and deploy custom apps for organization's internal users of Teams. You use app setup policy to control who in your organization can upload custom apps. You use Org-wide app settings to allow users to use custom apps. You use permission policies to allow only specific users to use a custom app.

[![Screenshot that shows how to allow custom apps in your organization in the Org-wide app settings panel.](media/custom-app-policy-trimmed.png)](media/custom-app-policy.png#lightbox)

To know more, see [how to manage custom apps](teams-custom-app-policies-and-settings).