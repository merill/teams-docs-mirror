---
layout: Conceptual
title: Set the PIN length for Audio Conferencing meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-the-pin-length-for-audio-conferencing-meetings-in-teams
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
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Microsoft Teams.
locale: en-us
document_id: cc5cd429-26dc-1108-8b62-159ca32a9b87
document_version_independent_id: 9a06f1b9-8554-2016-a9e3-178f8b1f5227
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-the-pin-length-for-audio-conferencing-meetings-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-the-pin-length-for-audio-conferencing-meetings-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-the-pin-length-for-audio-conferencing-meetings-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 39aaf15a-afb6-b78e-ec00-979406f919b4
---

# Set the PIN length for Audio Conferencing meetings - Microsoft Teams | Microsoft Learn

When you set up Audio Conferencing for Microsoft Teams, you get an Audio Conferencing bridge. A conferencing bridge can contain one or more phone numbers. The phone number you set is included on the meeting invites for the Microsoft Teams app.

The Audio Conferencing bridge answers a call for users who dial-in to a meeting using a phone. It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.

As an admin, you can use **Microsoft bridge settings** to change the settings for meeting notifications and the meeting join experience. You can also set the length of the PINs that are used by meeting organizers. Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## What's a PIN?

- PINs can be from 4 to 12 digits; the default is 5. Numbers are only used when creating PINs. Letters and special characters aren't used.
- A PIN is only required for the meeting organizer when a Microsoft Teams user doesn't start the meeting. If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.
- PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They're applied to all meetings that use the phone numbers associated with a given bridge.

Note

A PIN and a conference ID serve different purposes in a meeting. Callers use the conference ID to join the meeting and identify it. On the other hand, a meeting organizer uses a PIN to authenticate themselves and start the meeting when dialing in.

## Set the PIN length

Using the Microsoft Teams admin center:

1. In the navigation pane, expand **Meetings** &gt; **Conference Bridges**.
2. Select **Bridge Settings**.
3. In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.
4. Select **Save**.