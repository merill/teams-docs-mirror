---
layout: Conceptual
title: Manage who can start instant meetings and schedule meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-who-can-schedule-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: bryannyce
ms.date: 2025-04-30T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- Tier1
- m365initiative-meetings
f1.keywords:
- CSH
ms.custom: 
description: Learn how to use Teams meeting policy settings to control who can start instant meetings and schedule meetings.
locale: en-us
document_id: d18063c1-af3b-f636-c8c4-a7c5efbf2b59
document_version_independent_id: d18063c1-af3b-f636-c8c4-a7c5efbf2b59
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-who-can-schedule-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-who-can-schedule-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-who-can-schedule-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f2d8924c-d9d5-4a2e-d0ae-9ff084a649b0
---

# Manage who can start instant meetings and schedule meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events

As an admin, you can control which users can start instant meetings and schedule meetings in Teams. Managing who can schedule meetings can be useful for privacy and compliance reasons, allowing you to prevent certain users from setting up meetings.

The meeting scheduling policy settings are all turned on by default. These settings are per-user policies and they apply before a meeting starts. These settings can be found in the **Meeting scheduling** section of **Meeting policies** in the Teams admin center or in the PowerShell [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

- **Private meeting scheduling**: Controls whether a user can schedule a private meeting in Teams.
- **Meet now in private meetings**: Controls whether a user can start an instant private meeting.
- **Channel meeting scheduling**: Controls whether a user can schedule a meeting in a channel.
- **Meet now in channel meetings**: Controls whether a user can start an instant meeting in a channel.
- **Outlook add in**: Controls whether a user can schedule a private meeting from Outlook.

Note

When a delegate authorized to send meeting invitations for someone else sends a meeting, the meeting policy applies to the person who granted the delegate permission.

To learn about meeting registration, see [Manage registration for Microsoft Teams meetings](set-up-meeting-registration).

To learn about managing the attendance and engagement report, see [Manage the attendance and engagement report for meetings and events in Microsoft Teams](/en-us/microsoftteams/teams-analytics-and-reports/meeting-attendance-report).

## Channel meetings

If you need to restrict the ability to start instant channel meetings and schedule channel meetings to specific people, you can create or update your meeting policy to restrict these settings. You can then create a separate policy attributed to users who you want to start instant channel meetings and schedule channel meetings.

### Manage channel meetings in the Teams admin center

1. In the Teams admin center, expand **Meetings** &gt; **Meeting policies** and choose the policy you want to update. To create a new policy, select **Add**.
2. Under **Meeting scheduling**, toggle the following:
    - To restrict who can start instant meetings in a channel, toggle **Meet now in channel meetings** to **Off**.
    - To restrict who can schedule meetings in a channel, toggle **Channel meeting scheduling** to **Off**. If this setting is turned off, users can't create new channel meetings, but the event organizer can edit existing channel meetings.
3. Select **Save**

### Manage channel meetings using PowerShell

To prevent users with this assigned policy from starting and scheduling channel meetings, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetNow $False
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowChannelMeetingScheduling $False
```

Set the parameters to `$True` for policies where you want to allow users to start channel meetings.

## Private meetings

A meeting is private when it isn't published to a channel in a team. You can use your policies to prevent specific users from starting instant meetings and scheduling private meetings. To allow other users to start instant meetings and schedule private meetings, you can use a separate policy.

### Configure private meetings in the Teams admin center

1. From the Teams admin center, expand **Meetings** &gt; **Meeting policies** and choose the policy you want to update. To create a new policy, select **Add**.
2. Under **Meeting scheduling**, toggle the following:
    - To restrict who can start instant private meetings, toggle **Meet now in private meetings** to **Off**.
    - To restrict who can schedule private meetings in a channel, toggle both **Private meeting scheduling** and **Outlook add-in** to **Off**.
3. Select **Save**

### Configure private meetings using PowerShell

To restrict who can start and schedule private meetings, run the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowPrivateMeetNow $False
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowPrivateMeetingScheduling $False
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowOutlookAddIn $False
```

## Turning off meeting policy settings

After any of the meeting policy settings are turned off, any user assigned to the policy can't start or schedule meetings of that type. The meeting join links and conference IDs of all existing meetings of that type that the user previously started or scheduled don't work. The conversations, files, whiteboards, recordings, transcripts, and other content related to the meeting are retained and users can still access them.

If a meeting policy setting is turned off and then turned on again for a user, all previously scheduled meetings organized by the user become active and people can join them using the meeting join link or by phone.

## Outlook add-in

This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).

When you turn off this setting, users can't schedule Teams meetings when they create a new meeting in Outlook. For example, in Outlook on Windows, the **New Teams Meeting** option doesn't show up in the ribbon. To learn more, see [Admin - authentication requirements and functionality of the Teams Meeting add-in in Outlook](outlook-add-in-authentication-policy-requirements).