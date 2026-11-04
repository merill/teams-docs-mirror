---
layout: Conceptual
title: Overview of app validation and app testing by Microsoft - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/overview-of-app-validation
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn about Teams app validation guidelines based on marketplace certification policies. Understand how Microsoft ensures that Teams apps adhere to high standards of privacy and security.
ms.topic: concept-article
author: vikasalmal0201
ms.author: vikasalmal
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.reviewer: sujai
ms.date: 2026-05-22T00:00:00.0000000Z
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 667936ab-077e-3bdb-679e-9f0e487f5c8c
document_version_independent_id: 667936ab-077e-3bdb-679e-9f0e487f5c8c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/overview-of-app-validation.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: overview-of-app-validation
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/overview-of-app-validation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d73df706-4e30-e406-12a1-3113da5ca484
---

# Overview of app validation and app testing by Microsoft - Microsoft Teams | Microsoft Learn

Microsoft requires an app to pass mandatory and strict validation tests before listing it in the [AppStore](https://appsource.microsoft.com/marketplace/apps) for users to use. The testing applies to all apps in the Teams app store. In addition, Microsoft strongly encourages app developers to participate in an optional certification of apps that indicates enhanced compliance, security, and privacy controls.

All the apps are mandatorily required to adhere to the Microsoft App Certification policies. The Teams store team performs more than 400 tests to ensure that the apps are usable and adhere to high standards of privacy and security.

To know the detailed validation guidelines that app developers adhere to, see [Validation guidelines for developers](/en-us/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). The guidance is based on the [Certification policies for Teams apps](/en-us/legal/marketplace/certification-policies#1140-teams).

Note

Validation and checks by Microsoft are available only for app available in the app store and are not available for custom apps. App developers submit these apps within for use in their organization or provide these app to be used in a customer's tenant.

## App validation and testing

We execute 400+ test cases for every app before it's made available on the Teams Store. The tests ensure appropriate functionality, user experience, and security, and ensure that all apps comply with the publicly listed CMO policies. Following are some of the tests carried out by Microsoft App Validation team for every app before it's published:

- Ensure that Graph permissions requested by the app are really the ones that the app functionality needs and not any extra permissions. Graph permissions for existing apps are regularly checked to ensure that apps don't require extra permissions.
- Apps that require users to sign in have a sign-out option.
- Developers of all apps undergo a detailed verification process on Microsoft Partner Center. The verification includes email verification, business verification and more. To know more about app publishing, see [How developers create a Partner Center account](/en-us/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Submission guide for developers](/en-us/office/dev/store/add-in-submission-guide), and [How developers publish apps](https://aka.ms/PublishToTeamsStore).
- Only apps from verified developers can seek Graph permissions from users.
- No app can download an executable file.
- Apps are tested to not contain ads, promotion for other apps.
- Apps are tested to be work appropriate with no offensive language, cyber-attack bots, spam, or scam content.
- All links in an app are functional and related only to the app offering.
- We test and evaluate all the published Teams app regularly as part of app store health checks.
- Privacy policy and Terms of use that cover Teams apps are provided by the app developer.
- The contact details of the app developer are available in the store listing and on their respective [Publisher attestation pages](/en-us/microsoft-365-app-certification/teams/teams-apps).

In addition, Microsoft encourages the app developers to participate in its compliance program that is a rigorous, two-tier approach to ensure app quality, security, and compliance. Teams store has hundreds of apps that go beyond fulfilling the already detailed validation guidelines and comply with these programs.

## Related article

- [Overview for admins of Microsoft 365 app compliance program](overview-of-app-certification)