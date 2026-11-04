---
layout: Conceptual
title: Set Audio Conferencing auto attendant languages - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-auto-attendant-languages-for-audio-conferencing-in-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: oscarr
ms.date: 2026-10-09T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Learn how to select the audio conferencing auto attendant languages for an audio conferencing number in Microsoft Teams.
locale: en-us
document_id: ca018d38-e559-ba14-c8c5-ad9635094c09
document_version_independent_id: 0c75b5f1-2680-0b87-02a9-8e111c68dd85
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-auto-attendant-languages-for-audio-conferencing-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-auto-attendant-languages-for-audio-conferencing-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-auto-attendant-languages-for-audio-conferencing-in-teams.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2959e052-7040-a526-6f91-ea5f7afe6b92
---

# Set Audio Conferencing auto attendant languages - Microsoft Teams | Microsoft Learn

The Audio Conferencing auto attendant for Microsoft Teams can greet audio callers in different languages when they join a meeting.

As an admin, you can choose one default and up to four alternate languages. The auto attendant uses your chosen default language first, followed by the alternate languages in the order that you picked.

Note

You only have the option to change the languages of Dedicated audio conferencing numbers. You can't change the languages for Shared audio conferencing numbers.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Set the conferencing auto attendant languages

Using the Microsoft Teams admin center:

1. Navigate to **Meetings** &gt; **Conference Bridges**.
2. Select a **Dedicated** audio conferencing phone number from the list, and at the top of the page, select **Edit**. The **Edit** option is only shown when a Dedicated audio conferencing number is selected.
3. In the pane on the right, choose the default language you want and any alternate languages.

    Note

    The supported default and alternate languages are listed. The order of alternate languages that you choose in the dropdowns is the order of the languages presented to callers.
4. Select **Save**.

## What else should I know?

- To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/en-us/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).
- Languages can be set for dedicated but not for shared phone numbers.
- To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing-in-teams).

## Manage auto attendant languages using PowerShell

To manage auto attendant languages with PowerShell, use the PowerShell [CsOnlineDialInConferencingServiceNumber](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) cmdlet.

For examples, see [CsOnlineDialInConferencingServiceNumber](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings).

## Related topic

- [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](/en-us/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)