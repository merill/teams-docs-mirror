---
layout: Conceptual
title: Change the settings for an Audio Conferencing bridge - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/change-the-settings-for-an-audio-conferencing-bridge
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
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- m365initiative-meetings
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Change audio conferencing bridge settings, including entry and exit notifications, play names or phone numbers, tones, and prompt callers to record their name.
locale: en-us
document_id: 95ca1eb6-710d-5b82-e5e3-13eb1e29c28f
document_version_independent_id: 62ac8be2-18a6-b13a-4cb9-60727e05c0e7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/change-the-settings-for-an-audio-conferencing-bridge.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-the-settings-for-an-audio-conferencing-bridge
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/change-the-settings-for-an-audio-conferencing-bridge.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6074b7e3-cdb5-e786-e83b-2a9902c1e4c4
---

# Change the settings for an Audio Conferencing bridge - Microsoft Teams | Microsoft Learn

When you set up Audio Conferencing in Microsoft 365 or Office 365, you get phone numbers for your users through an audio conferencing bridge. A conferencing bridge can have one or more phone numbers that are included at the bottom of the meeting invite. These phone numbers allow users to join Microsoft Teams meetings by dialing in.

When a user dials in to a meeting using a phone, the conferencing bridge answers the call with voice prompts from the meeting auto attendant. Depending on your settings, the conferencing bridge can also play notifications, ask callers to record their name, and control the PIN settings. A PIN is assigned to meeting organizers to allow them to start their meetings if they can't use the Microsoft Teams app.

Important

The meeting organizer only needs a PIN when a Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Manage audio conferencing bridges in the Teams admin center

1. Go to **Meetings** &gt; **Conference bridges**.
2. At the top of the **Conference bridges** page, select **Bridge settings**.
3. In the **Bridge settings** pane, select:

    - **Meeting entry and exit notifications** - If you turn off this setting, users in the meeting aren't notified when someone enters or leaves the meeting.
    - When you turn on **Meeting entry and exit notifications**, you can select one of these options:

        - **Names or phone numbers** - When users join a meeting by dialing in, their phone number is played.

            - Toggle **Ask callers to record their name before joining the meeting** **On** or **Off**. If you turn this off, callers aren't asked to record their name before they join a meeting.
        - **Tones** - When users join a meeting by dialing in, an audio tone is played.
4. To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.
5. To control whether to send an email to your users when their settings are changed, toggle **Automatically send emails to users if their audio conferencing configuration changes** **On** or **Off**. For more information, see [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams).
6. Select **Save**.

Note

By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).

## Manage audio conferencing bridges with PowerShell

To manage audio conferencing bridges with PowerShell, use the following parameters, within the PowerShell [Set-CsOnlineDialInConferencingTenantSettings](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) cmdlet:

- **`-EnableNameRecording`**
- **`-EntryExitAnnouncementsType`**
- **`-EnableNameRecording`**
- **`-PinLength`**