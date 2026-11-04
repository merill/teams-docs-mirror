---
layout: Conceptual
title: Prerequisites and environmental dependencies for upgrading to Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/upgrade-plan-journey-prerequisites
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: landerl
ms.date: 2018-05-30T00:00:00.0000000Z
audience: admin
description: Use this guidance to learn about the prerequisites and the environmental dependencies for deploying Teams in your organization
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
locale: en-us
document_id: 36c8eb24-9ef2-da1f-50fd-a881ed72a7bb
document_version_independent_id: 04542574-e4af-d2d3-eeb0-61fd4a07e481
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/upgrade-plan-journey-prerequisites.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: upgrade-plan-journey-prerequisites
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/upgrade-plan-journey-prerequisites.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ed63f162-496f-ecc9-ebea-fa94d57c8c39
---

# Prerequisites and environmental dependencies for upgrading to Teams - Microsoft Teams | Microsoft Learn

![Upgrade journey diagram, emphasizing the Technical Readiness stage.](media/upgrade-banner-tech-readiness.png)

This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage. Before proceeding, confirm that you've completed these activities from previous stages:

- [Enlisted your project stakeholders](upgrade-enlist-stakeholders)
- [Defined your project scope](upgrade-define-project-scope)
- [Understood coexistence and interoperability of Skype for Business and Teams](teams-and-skypeforbusiness-coexistence-and-interoperability)
- [Chosen your upgrade journey](upgrade-and-coexistence-of-skypeforbusiness-and-teams)

Teams uses multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services. These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.

Although not all services are required, we highly recommend that you implement all of them. If you choose not to implement certain services, it affects the functionality that Teams can offer your organization. For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service reduces the functionality offered through the client.

See the following articles to learn about prerequisites and how Teams interacts with other technologies:

- If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).
- If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).
- If your organization hasn't synchronized identities to Microsoft Entra ID, see [Identity models and authentication in Microsoft Teams](identify-models-authentication).
- If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact).
- If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact).
- To learn how [Microsoft 365 groups and Microsoft Teams interact](office-365-groups).
- If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/en-us/schooldatasync) before deploying Microsoft Teams.
- If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page), [Which Calling Plan is right for you](calling-plan-landing-page), and [Phone System Direct Routing](direct-routing-landing-page).
- To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network).
- If you're currently using Skype for Business Online Connector to manage your services, you need to move to the Teams PowerShell module and update your existing PowerShell scripts. See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo) for more information.

After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment).