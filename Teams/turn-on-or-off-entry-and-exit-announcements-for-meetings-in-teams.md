---
layout: Conceptual
title: Turn on or off entry and exit announcements for meetings in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams
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
ms.date: 2026-10-06T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Admin can learn about how to turn entry and exit announcements on or off in a Microsoft Teams meeting.
locale: en-us
document_id: 07eca314-7a40-c7ee-1d31-7a858adff741
document_version_independent_id: dede6892-d7e3-d44d-f8f6-eb4bd50c07f0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1c9c49cf-1393-a513-a298-5483f8cc61ef
---

# Turn on or off entry and exit announcements for meetings in Teams - Microsoft Teams | Microsoft Learn

When you set up Audio Conferencing in Microsoft 365 or Office 365, you provide users with phone numbers through an audio conferencing bridge. This bridge can have one or more phone numbers, which are included at the bottom of the meeting invite. These numbers allow users to join Microsoft Teams meetings by dialing in.

As an admin, you can control whether an entry and exit announcement is played when participants who dialed into the meeting join or leave.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Setting meeting join options using the Microsoft Teams admin center

1. Expand **Meetings** &gt; **Conference Bridges**.
2. At the top of the **Conference Bridges** page, select **Bridge Settings**.
3. In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**. This setting is enabled by default. If you disable it, participants in the meeting aren't notified when someone enters or leaves.
4. Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.

    Note

    By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).
5. If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.
6. Select **Save**.

## Turn on or off entry and exit announcements with PowerShell

To turn entry and exit announcements on or off with PowerShell, use the **`-EnableEntryExitNotifications`** parameter within the PowerShell [CsOnlineDialInConferencingTenantSettings](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) cmdlet.

### Turn off entry and exit announcements

To turn off entry and exit announcements, use the following script:

```powershell
Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $false 
```

### Turn on entry and exit announcements

To turn on entry and exit announcements, use the following script:

```powershell
Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true 
```

## Related topic

- [Audio Conferencing common questions](audio-conferencing-common-questions)