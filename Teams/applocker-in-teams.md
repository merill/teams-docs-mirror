---
layout: Conceptual
title: AppLocker control policies - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/applocker-in-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: DivySri-RK
ms.author: divyasrirk
manager: prgholve
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.collection:
- M365-collaboration
- trust-pod
ms.reviewer: rafarhi
ms.date: 2019-04-26T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn how to enable the Teams desktop client application with AppLocker application control policies.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: c25b1616-0c23-ede5-a6d5-657c1693b0b1
document_version_independent_id: 9527060f-1870-4ddd-4578-586d636db0c7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/applocker-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: applocker-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/applocker-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2faeb5fd-64f2-223d-52bb-d9cf140fa730
---

# AppLocker control policies - Microsoft Teams | Microsoft Learn

This article explains how to enable the Teams desktop client app with AppLocker application control policies. Use of AppLocker is designed to restrict program and script execution by non-administrative users. For more information and guidance on AppLocker, see [What is AppLocker?](/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies. Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information). The AppLocker policy is saved in XML format and can be edited with any text or XML editor.

## Teams allow list with AppLocker

AppLocker rules are organized into collections of rules. AppLocker rules apply to the targeted app, and they're the components that make up the AppLocker policy.

To allow Teams, we recommend that you use the [publisher condition rules](/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.

We don't recommend the use of path rules because the Teams installation directory is user-writable. We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.

Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes. The digital signature contains information about the company that created the app file (the publisher). The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.

### Example of publisher condition rules

For the Teams client app (all files, all versions) adds the following to the Executable Rules & DLL Rules:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```