---
layout: Conceptual
title: Share to Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-outlook-share-teams
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
ms.date: 2021-03-10T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about the Share to Teams feature, which allows users to share emails and email attachments from Outlook to any chat or channel in Teams.
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
locale: en-us
document_id: 311beaec-73aa-da96-6793-c8750597b1fa
document_version_independent_id: c730e71d-45e8-d912-85b8-0556daa3a57c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-outlook-share-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-outlook-share-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-outlook-share-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
platformId: d8a13e2f-89b3-d594-0aad-c9d9139b61af
---

# Share to Teams - Microsoft Teams | Microsoft Learn

Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.

## Outlook add-in for Share to Teams

The Share to Teams feature requires an add-in for Outlook. This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.

Note

Be sure to review [Add-ins for Outlook in Exchange Online](/en-us/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/en-us/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly. Also, disabling connected experiences can prevent add-ins for Outlook from working properly. See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information. Shared mailboxes are not supported by the add-in.

Share to Teams uses the same transport mechanism as when a user emails a channel. For sharing to chats, emails (including email attachments) are copied to the sender's OneDrive. For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.

The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/en-us/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Outlook add-in API requirement set 1.7](/en-us/javascript/api/requirement-sets/outlook/requirement-set-1.7/outlook-requirement-set-1.7), which include details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.

Note

Share to Teams isn't available for Government Community Cloud (GCC) High and Department of Defense (DOD) environments.

## Enabling or disabling Share to Teams

The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.

Note

Disabling the add-in is only possible after the add-in has been installed. If you would like to enforce disabling for all users in your tenant, run a script periodically.

To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/en-us/powershell/module/exchange/disable-app).

To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/en-us/powershell/module/exchange/enable-app).

## Browsers and Single Sign-on

Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView. See [Browsers used by Office Add-ins](/en-us/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.

Important

Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.

Share to Teams uses Single Sign-on (SSO), which means users don't need to provide their credentials when using the add-in via Share to Teams. SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default. For vanity domains, administrators need to add the appropriate Microsoft Entra ID reply URL.