---
layout: Conceptual
title: Mask phone numbers in Microsoft Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/ptsn-mask-phone-numbers
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
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to mask phone numbers in Microsoft Teams.
locale: en-us
document_id: b9fb3d9f-f423-3612-cd8c-2c2450c8b574
document_version_independent_id: c4f5717f-3c0b-0491-ca3f-3ab0add94ebc
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/ptsn-mask-phone-numbers.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: ptsn-mask-phone-numbers
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/ptsn-mask-phone-numbers.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 923d96b2-ddf9-3511-3750-2f329ce722bc
---

# Mask phone numbers in Microsoft Teams meetings - Microsoft Teams | Microsoft Learn

When participants dial in to a Teams meeting using Audio Conferencing, only internal participants can see their full phone number. By default, participants outside of your organization can't see other participants' phone numbers. Here's an example of how external participants see phone numbers:

![an example of a masked phone number.](media/hiddenphonenum.png)

For specific industry use cases, as an admin, you can choose how the Audio Conferencing participants' phone numbers appear in meetings organized in their tenant. You can choose from three options:

- Phone numbers are masked only from external participants. The participants who belong to the meeting organizer's tenant still see the full phone number.
- Phone numbers are masked from everyone in the meeting except the organizer.
- Phone numbers are unmasked, which makes them visible to everyone in the meeting.

This setting is applied in the meeting where phone numbers are visible.

## Use Teams admin center to set phone-number masking

To change the Public Switched Telephone Network (PSTN) masking setting in the Teams admin center, log into the Teams admin center as an administrator, select **Meetings** &gt; **Conference Bridges** in the navigation pane, and then select **Bridge settings**. **Display masked caller IDs** is a dropdown at the bottom of the Bridge settings pane, and allows you to choose the following:

1. Sign in to the Microsoft Teams admin center.
2. In navigation pane, expand **Meetings** &gt; **Conference Bridges**.
3. Select **Bridge settings**.
4. For the **Masked phone numbers** dropdown, select one of the following options:

    - From participants outside your organization
    - From all meeting participants (except the organizer)
    - Turned off
5. Select **Apply**.

## Use Microsoft PowerShell to set phone-number masking

To change the PSTN masking setting in PowerShell, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) cmdlet to one of the available options.

To mask phone numbers only from external participants, run the following command:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

To mask phone numbers from all participants in the meeting (except the organizer), run the following command:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

To disable phone number masking, run the following command:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```