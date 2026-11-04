---
layout: Conceptual
title: Start Audio Conference over the phone without a PIN in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams
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
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Teams admin center. '
locale: en-us
document_id: 72b4d417-8a1f-daca-381a-b1beed2dbdac
document_version_independent_id: d3e59d94-b0b7-fdfc-3a04-00dc4188e63d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: start-an-audio-conference-over-the-phone-without-a-pin-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 090fa74f-60fe-0b38-d361-23faeb8af43c
---

# Start Audio Conference over the phone without a PIN in Teams - Microsoft Teams | Microsoft Learn

Users dialing into a meeting might feel frustrated as they wait in the lobby, listening to music, because the Microsoft Teams meeting organizer hasn't started the meeting.

If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the admin center to enable or disable this setting for a single user.

A PIN isn't required for the meeting organizer if someone starts the meeting from the Microsoft Teams app. A PIN is only required when a meeting organizer joins their meeting over a phone. The PIN for meetings is sent to the audio user when they're assigned the **Audio Conferencing** license and are enabled for Audio Conferencing. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams).

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Enable or disable anonymous callers from joining a meeting

### Using the Microsoft Teams admin center

1. In the left navigation, select **Users**.
2. Select a user in the list, and then select **Edit** at the top of the page.
3. Next to **Audio Conferencing**, select **Edit**.
4. In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.
5. Select **Apply**.

### Using Windows PowerShell

For more information, see [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams).

## What else should you know?

- If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams).
- If anonymous access, or the option to start a meeting without requiring a PIN, is disabled:

    - **If the meeting hasn't started (there's no one in the meeting yet):** A caller is prompted if they're the organizer; if they say yes, they're prompted for their PIN. After they enter the PIN, the meeting starts and the user joins the meeting.
    - **If the meeting already started (someone else is already in the meeting):** A caller isn't be prompted if they're the organizer and they're never prompted for the PIN. The meeting is already started, and the caller joins it.
- If anonymous access, or not requiring a PIN to start a meeting, is enabled:

    - **If the meeting hasn't started (there's no one in the meeting yet):** A caller isn't be prompted if they're the organizer, and they're never prompted for the PIN. Because the organizer's setting is off, the meeting starts and the anonymous callers join the meeting.
    - **If the meeting already started (someone else is already in the meeting):** A caller isn't be prompted if they're the organizer, and they're never prompted for the PIN. The meeting is already started, and the caller joins it.

## Want to know more about Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these articles:

- [Why you need to use Office 365 PowerShell](/en-us/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
- [Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/en-us/previous-versions//dn568025%28v=technet.10%29)

For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams).

## Related article

- [Try or purchase Audio Conferencing in Microsoft 365 for Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams)