---
layout: Conceptual
title: Manage actionable activity emails - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-outlook-email-integration
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
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: 
ms.date: 2019-12-13T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about enabling and disabling actionable activity emails of Microsoft Teams conversations
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
locale: en-us
document_id: 4f34a4f9-bb6f-03e9-9c11-bb2f43dd9aeb
document_version_independent_id: a6e1ee45-8ce4-96b4-21ad-90ca8af646c4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-outlook-email-integration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-outlook-email-integration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-outlook-email-integration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
platformId: cf0ab5de-6db5-2466-888d-4573be9743b5
---

# Manage actionable activity emails - Microsoft Teams | Microsoft Learn

Actionable activity emails are enabled by default and notify users in your organization of missed conversations on Microsoft Teams.

A missed activity email shows the latest replies to a conversation, including messages sent after the missed message. This feature lets users reply directly from Outlook by selecting **Reply**.

## Disable actionability in missed activity emails

While this feature is set to enable by default, you can turn off actionability in activity emails across your organization by running the following command:

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

Once the feature is disabled, the **Reply** option is replaced by **Reply in Teams** making the missed activity emails no longer considered actionable. Users will no longer be able to respond directly from Outlook and are directed to continue the conversation on Teams.

Note

This feature isn't supported in Outlook for Mac or some older versions of Outlook for Windows. For more information, see [Actionable messages in Outlook and Office 365 Groups](/en-us/outlook/actionable-messages/).