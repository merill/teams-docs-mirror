---
layout: Conceptual
title: Limit who users can see when searching the directory in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-scoped-directory-search
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: Admin
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: 
ms.date: 2024-12-12T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Learn how to limit who users can see when searching the directory in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
locale: en-us
document_id: 84066c98-38a4-e59a-893f-da38a4a11bf3
document_version_independent_id: 890a4978-0e9b-2691-a2ab-8b5512e5e76f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-scoped-directory-search.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-scoped-directory-search
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-scoped-directory-search.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
platformId: 2b51c8fd-6c40-2152-980a-a68b9afa58d0
---

# Limit who users can see when searching the directory in Teams - Microsoft Teams | Microsoft Learn

Microsoft Teams lets organizations provide custom views of the directory to their users. These views can be useful if:

- Your organization has multiple companies within its tenant that you want to keep separate.
- Your business policies require that you prevent certain groups within your organization from communicating with each other.
- Your school wants to limit chats between faculty and students.

There are two options for limiting who users can see when they search the directory in Teams:

- [Information barriers in Microsoft Teams](/en-us/MicrosoftTeams/information-barriers-in-teams)
- [Address book policies in Exchange Online](/en-us/exchange/address-books/address-book-policies/address-book-policies)

If using either option, you must turn on search by name in the Teams admin center.

We recommend using information barriers if your organization meets the [required licenses and permissions](/en-us/microsoft-365/compliance/information-barriers#required-licenses-and-permissions).

Note

Information barriers V1 and address book policies are automatically respected for people search in all people search entry points in the Teams client when configured. There's no need to enable this setting to hide users in search.

To turn on search by name:

1. In the Microsoft Teams admin center, select **Teams** &gt; **Teams settings**.
2. Under **Search by name**, next to **Scope directory search using an Exchange address book policy**, turn the toggle **On**.

Note

It may take a few hours for this change to take effect.

Turning on search by name hides the **Search teams** box and public teams listing in **Join or create a team** in Teams. It will also disable joining a team by typing `/join` in the command box at the top of Teams.

When **Scope directory search using an Exchange address book** policy is turned on, most accounts that are marked as hidden in Exchange don't show up in Teams searches. Personal contacts show up regardless of the Search by Name setting.