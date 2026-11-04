---
layout: Conceptual
title: Disabling toll-free numbers for specific Teams users - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/disabling-toll-free-numbers-for-specific-teams-users
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
ms.topic: article
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
description: Learn how to control how organizers can use toll-free numbers for their Audio Conferencing Bridge meetings.
locale: en-us
document_id: 7cb497f5-f5f5-50d6-5c58-cdd525143b5b
document_version_independent_id: 68fbf64d-8054-de90-18f6-b8e3734e1997
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/disabling-toll-free-numbers-for-specific-teams-users.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: disabling-toll-free-numbers-for-specific-teams-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/disabling-toll-free-numbers-for-specific-teams-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6cd98e32-e581-eee3-7f5c-2ede08756990
---

# Disabling toll-free numbers for specific Teams users - Microsoft Teams | Microsoft Learn

If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, as an admin, you can manage whether meeting organizers can use toll-free numbers.

By default, all users in your organization can use toll-free numbers. If available, participants can use those numbers to join their meetings. If this isn't the desired behavior for some users in your organization, you can prevent specific users from using those numbers in their meetings

When you turn toll-free numbers off for a meeting organizer:

- A toll-free number is no longer included in their meeting invites.
- Toll-free numbers are no longer listed on the "Find a local number" page that's referenced in their meeting invites.
- Participants can't dial any of your organization's toll-free numbers to join the meeting.
- Participants can continue joining meetings of the organizer using toll numbers.

## Turn off toll-free numbers for specific users

You can use the Teams admin center or PowerShell to turn off toll-free numbers for specific users.

### Teams admin center

1. In the navigation pane, expand **Meetings** &gt; **Audio Conferencing**.
2. Select an existing policy or add a new one.
3. Toggle **Include toll-free numbers in meeting invites created by users of this policy** to **Off**.
4. Select **Save**.

### PowerShell

You can turn off toll-free numbers for specific users by changing the setting for **`-AllowTollFreeDialIn`** to **Off** within the *TeamsAudioConferencingPolicy* assigned to those users. Once turned off, any new meetings these users organize don't include any toll free numbers. To learn more, see [Audio Conferencing policy settings for toll and toll-free numbers](audio-conferencing-toll-free-numbers-policy).

Important

Old and previously scheduled recurring meetings may still show toll-free numbers and participants won't be able to join such meetings using a toll-free number. You can reschedule all old and recurring meetings for these users and remove toll-free numbers from them using MMS.