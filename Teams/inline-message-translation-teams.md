---
layout: Conceptual
title: Turn on inline message translation - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/inline-message-translation-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.date: 2019-06-21T00:00:00.0000000Z
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
ms.collection:
- M365-collaboration
ms.reviewer: salilda
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to turn on inline translation in Microsoft Teams using the Microsoft Teams admin center or PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
locale: en-us
document_id: 19e91f77-0c01-5d38-0bd4-65ee44aab5cb
document_version_independent_id: 08ea83b3-c241-979c-3afb-3355ab322489
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/inline-message-translation-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: inline-message-translation-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/inline-message-translation-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f612d3e6-e2c8-dd32-27f0-fb69ed83fcbf
---

# Turn on inline message translation - Microsoft Teams | Microsoft Learn

Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.

Inline message translation is rolled out by default for your organization. You don't need to make changes if you want to allow users to use this feature within the Teams client.

Note

This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.

## Use PowerShell to turn off inline message translation

You can use the messaging policy to turn off the inline message translation.

Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/en-us/powershell/module/teams/set-csteamsmessagingpolicy) cmdlet. The policy takes a few minutes to apply. Users might need to sign out and sign back in to Teams.

## Use the Microsoft Teams admin center to turn off inline message translation

In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.

Note

The service does the translation and delivers it to the client with no effect on the content captured in the compliance records. To learn more about translation, see [What is Microsoft Translator?](/en-us/azure/cognitive-services/translator/translator-info-overview)