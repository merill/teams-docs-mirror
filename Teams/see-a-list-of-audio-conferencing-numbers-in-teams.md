---
layout: Conceptual
title: See a list of Audio Conferencing numbers - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/see-a-list-of-audio-conferencing-numbers-in-teams
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
ms.date: 2026-10-08T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
- seo-marvel-apr2020
description: Learn how to look up the dial-in conferencing numbers that are available for audio conferencing from within Microsoft Teams.
locale: en-us
document_id: da255c7a-42a3-32be-25f6-c54a45ff7903
document_version_independent_id: ccb6f5f7-b939-b7ee-2808-cf471d748eab
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/see-a-list-of-audio-conferencing-numbers-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: see-a-list-of-audio-conferencing-numbers-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/see-a-list-of-audio-conferencing-numbers-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 8ee3c2c3-610f-154c-68f5-0932c341ceea
---

# See a list of Audio Conferencing numbers - Microsoft Teams | Microsoft Learn

When you set up Audio Conferencing for your Microsoft Teams users, you can see the phone numbers that are available to them for audio conferencing. This list has all the audio conferencing phone numbers that are available to your organization.

**Looking for prices?** Review the **Audio Conferencing rates** section in [Audio Conferencing](https://www.microsoft.com/microsoft-teams/audio-conferencing).

When there's only one phone number available in your organization, it serves as the default number for all of your users. When multiple phone numbers are available, you can select the default phone number for each user. The default number is included in Microsoft Teams meeting invitations.

To change the dial-in phone number for a single user, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams).

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## See your audio conferencing phone numbers in the Teams admin center

Using the Microsoft Teams admin center:

1. In the left navigation, go to **Meetings** &gt; **Conference bridges**.
2. View the phone numbers that are available for audio conferencing.

    - You can also see the location and primary language that the audio conferencing auto attendant uses.

## See your audio conferencing phone numbers using PowerShell

To see your audio conferencing phone numbers with PowerShell, use the PowerShell [Get-CsOnlineDialInConferencingServiceNumber](/en-us/powershell/module/teams/get-csonlinedialinconferencingservicenumber) cmdlet.

To see all the audio conferencing phone numbers in your organization, use the following script:

```powershell
Get-CsOnlineDialInConferencingServiceNumber | fl
```

For more examples, see [Get-CsOnlineDialInConferencingServiceNumber](/en-us/powershell/module/teams/get-csonlinedialinconferencingservicenumber).

## Related topic

- [Change the settings for an audio conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge)