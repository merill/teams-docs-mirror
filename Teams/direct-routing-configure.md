---
layout: Conceptual
title: Configure Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-configure
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: filippse
ms.date: 2026-03-16T00:00:00.0000000Z
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
- highpri
- Tier1
f1.keywords:
- NOCSH
description: Learn how to configure Microsoft Direct Routing to connect your on-premises telephony infrastructure to Teams Phone.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 0a3a97bf-5eff-61a0-9bb0-f69f712fa834
document_version_independent_id: 0fbf3b06-383b-54a3-ca13-92208ed9b4bc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-configure.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-configure
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-configure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4e396b74-3df8-fab8-66d9-3e06edcef218
---

# Configure Direct Routing - Microsoft Teams | Microsoft Learn

Direct Routing lets you connect your on-premises telephony infrastructure to Microsoft Teams Phone. This article lists the high-level steps required to connect a supported on-premises Session Border Controller (SBC) to Direct Routing, and to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN). This article links to associated articles for details.

For information about whether Direct Routing is the right solution for your organization, see [PSTN connectivity options](pstn-connectivity). For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan).

To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets. For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Before you perform the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor. For a complete list of supported SBCs, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers).

To configure Teams Phone and enable users to use Direct Routing, follow these steps:

- **Step 1.**[Connect the SBC with Teams Phone and validate the connection](direct-routing-connect-the-sbc)
- **Step 2.**[Enable users for Direct Routing, voice, and voicemail](direct-routing-enable-users)
- **Step 3.**[Configure call routing](direct-routing-voice-routing)
- **Step 4.**[Translate numbers to an alternate format](direct-routing-translate-numbers)

If you're configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants).

## Support Boundaries

Microsoft supports Teams Phone with Direct Routing only when used with certified devices. If there are issues, you must contact your SBC vendor's customer support first. If needed, the SBC vendor will escalate the issue to Microsoft through internal channels. Microsoft reserves the right to reject support cases where a noncertified device is connected to Teams Phone through Direct Routing. If Microsoft determines that a customer's Direct Routing issue is with a vendor's SBC device, the customer will need to re-engage the SBC vendor for support.