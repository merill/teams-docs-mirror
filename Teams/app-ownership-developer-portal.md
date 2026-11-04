---
layout: Conceptual
title: Ownership of apps in Developer Portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/app-ownership-developer-portal
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: serdars
ms.author: SerdarSoysal
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 2024-10-21T00:00:00.0000000Z
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: 
f1keywords: 
description: Manage ownership of Teams app in Developer Portal for your entire organization and its developers
ms.localizationpriority: medium
locale: en-us
document_id: 63ecb2cf-7d6a-add3-760e-000a3cfc9694
document_version_independent_id: 63ecb2cf-7d6a-add3-760e-000a3cfc9694
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/app-ownership-developer-portal.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-ownership-developer-portal
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/app-ownership-developer-portal.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1932348a-fe6c-8ac5-e07f-c833579fc86c
---

# Ownership of apps in Developer Portal - Microsoft Teams | Microsoft Learn

App developers use [Developer Portal](/en-us/microsoftteams/platform/concepts/build-and-test/teams-developer-portal) to configure, distribute, and manage their Teams apps. Developers who create or import an app in Developer Portal becomes the owner of the app. An app owner can add other org users as owners as well.

An owner may leave the organization or can delete the app from the portal after the app is published. In such cases, a Global Administrator can help in the following ways:

- Take over the ownership of an app and add other developers as owners.
- Import the app if it was created outside of Developer Portal or was deleted from the portal.

The above tasks help admins to let another developer work on the app and manage it, hence maintaining business continuity.

## Admin takes ownership of a custom app

Your organization can use a custom app that is available just within your org and not on the Teams store. It's created for and managed within your org. Admins can take ownership of a custom app in the following scenarios:

- Custom app that is available in the portal.
- Custom app that wasn't created in or is removed from the portal.

### Take ownership of custom app available in the portal

If a custom app exists in the portal, then taking ownership isn't possible for a user. Admins can either import the zip archive or take ownership in the following ways.

| Role | Available option | Outcome on app ownership |
| --- | --- | --- |
| Admin | Import &gt; Replace | Recommended approach if you have the app zip archive. Retains app ID of previous app so the app remains the same. The portal overwrites ownership making you the sole owner. You can add new org users as owners. |
| Admin | Take ownership | Recommended approach if you know the app ID. The portal adds you as yet another app owner. You can add other users as developers. |
| Admin | Import &gt; Replace | Creates a new app ID and makes the admin as owner. No relation to the previous app. |
| User | Import | Creates a new app ID so no relation to the previous app. Uploader is the owner and can add other developers. |

Tip

To know the app ID, use the app details page in the Teams admin center. If the app is deleted from admin center, then import the zip archive of the app.

### Take ownership of custom app not available in the portal

It is possible to create a custom app without using the Developer Portal or to delete it after creation. In this case, your org doesn't have the app available in the portal. You can import or take ownership in the following ways.

| Role | Available option | Outcome on app ownership |
| --- | --- | --- |
| Admin | Import | Provide app ID in the import dialog. The portal makes you the sole owner and you can add other users as owners. There's no impact on the app as it doesn't exist in the portal. |
| Admin | Take ownership | If app was created in the portal, admin can provide app ID and take ownership as the sole owner. It doesn't work if app was created outside the portal. |
| User | - | Not possible for a user to either import or to take ownership. |

## Admin takes ownership of a Store app

An org can publish its app to [Microsoft AppStore](https://appsource.microsoft.com) using Partner Center UI.

In the above cases, you as an admin can reclaim the ownership of the app in Developer Portal by contacting Microsoft Support. To ascertain the ownership, provide the following details to Microsoft Support:

- Proof of ownership of the app: Provide a screenshot of the email approval from Microsoft app validation team. When an org submits a Teams app in Partner Center, Microsoft validates the app and contacts from `teamsubm@microsoft.com` email ID. Microsoft app validation team lets your org know that the app is approved for publishing to the AppStore.
- Your tenant ID.
- Your app's ID.