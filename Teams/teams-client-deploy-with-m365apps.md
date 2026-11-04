---
layout: Conceptual
title: Deploy the Microsoft Teams client with Microsoft 365 Apps - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-deploy-with-m365apps
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MicrosoftHeidi
ms.author: heidip
manager: jtremper
ms.topic: article
ms.date: 2025-06-30T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: 
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about how to install Microsoft Teams with Microsoft 365 Apps.
ms.localizationpriority: medium
locale: en-us
document_id: 8c4b2e24-2292-b29d-7f1f-675a087025e8
document_version_independent_id: 8c4b2e24-2292-b29d-7f1f-675a087025e8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-deploy-with-m365apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-deploy-with-m365apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-deploy-with-m365apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e2c9f30c-00ec-44c0-846c-b20dbfb3283f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/702271fe-87d7-4493-828b-2d6fde3de8ab
platformId: b6902afc-897e-90c2-880c-bcf986297c23
---

# Deploy the Microsoft Teams client with Microsoft 365 Apps - Microsoft Teams | Microsoft Learn

The Teams app automatically installs with new and existing installations of Microsoft 365 Apps on Windows. Administrators may exclude the Teams client from automatically installing with Microsoft 365 Apps on Windows.

## Prerequisites for target computers

See [Teams system requirements](teams-client-system-requirements) for information on requirements for the Teams client.

Note

Learn more: [**Update History for Microsoft 365 Apps**](/en-us/officeupdates/update-history-microsoft365-apps-by-date#supported-versions).

## How to exclude Teams from new installations

Admins who don't want Teams included with Microsoft 365 Apps on devices running Windows can follow these steps to opt out.

1. Sign in to the Microsoft 365 Apps admin center (https://config.office.com) with an admin account.
2. Go to **Customization &gt; Device Configuration &gt; Modern Apps Settings**.
3. Select **Microsoft Teams (work or school)**, then clear the **Enable automatic installation of new Microsoft Teams** check box.

Note

For the best Teams experience, we recommend leaving the setting as is.

Note

If you set Teams update policy to **Not enabled**, but users still receive the Teams client with Microsoft 365 Apps, follow the instructions in our [How to uninstall the Teams client](teams-client-uninstall) article to uninstall it for your users.

## Office 365 plans that don't include Microsoft Teams

Some Office 365 plans include Microsoft 365 Apps, but don't include the Teams service. Teams is still installed with Microsoft 365 Apps even if a plan doesn't have the Teams service.

For Office 365 plans that don't include the Teams service, a free trial version of Teams, valid for one year, is available. Your users can start using it when they sign in to Teams. For more information about this free trial version and providing your users access, see the [Manage the Microsoft Teams Commercial Cloud Trial offer](teams-exploratory).