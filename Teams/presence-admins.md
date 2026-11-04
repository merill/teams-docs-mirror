---
layout: Conceptual
title: User presence in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/presence-admins
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: petrhudecek
ms.date: 2026-07-16T00:00:00.0000000Z
description: Learn the Presence states in Teams and the administrative settings for the Presence feature.
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
locale: en-us
document_id: a162ef5c-3099-7f58-4178-d29e3ec2b5a7
document_version_independent_id: 6ca31e56-052d-6c62-1323-b5aaaae1f04a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/presence-admins.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: presence-admins
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/presence-admins.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d2e63e05-f5a7-3bb0-b313-1e20ecb37362
---

# User presence in Teams - Microsoft Teams | Microsoft Learn

Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365). Presence indicates the user's current availability and status to other users. By default, anyone in any organization using Teams can see (in nearly real time) if other users are available online.

For details about Teams user profiles on different platforms, see also [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## Presence states in Teams

| User-configured | App-configured |
| --- | --- |
| ![Solid green check mark, indicates Presence Available.](media/presence_available.png) Available | ![Solid green check mark, indicates Presence Available](media/presence_available.png) Available |
|  | ![Open green check mark, indicates available oof.](media/presence_available_oof.png) Available, Out of Office. Note: Out of office is automatically set for the periods of time where the user sets "automatic replies." If the user is using Teams during these periods of time, the user's presence is shown alongside the Out of Office indicator. |
| ![Solid red circle, indicates Busy.](media/presence_busy.png) Busy | ![Solid red circle, indicates Busy](media/presence_busy.png) Busy |
|  | ![Solid red circle, indicates Busy in a call.](media/presence_busy.png) In a call |
|  | ![Solid red circle, indicates Busy in a meeting.](media/presence_busy.png) In a meeting |
|  | ![Open red circle, indicates Busy.](media/presence_busy_oof.png) In a call, out of office |
| ![Red circle with white line, indicates Do Not Disturb.](media/presence_dnd.png) Do not disturb |  |
|  | ![Red circle with white line, indicates Presenting.](media/presence_dnd.png) Presenting |
|  | ![Red circle with white line, indicates Focusing.](media/presence_dnd.png) Focusing. Focus occurs when users schedule focus time in MyAnalytics/Insights in their calendars. |
| ![Yellow clock icon, indicates away.](media/presence_away.png) Away | ![Yellow clock icon, indicates away.](media/presence_away.png) Away |
|  | ![Yellow clock icon, indicates away](media/presence_away.png) Away Last Seen *time* |
| ![Yellow clock icon, indicates away, be right back.](media/presence_away.png) Be right back |  |
| ![Gray circle with x, indicates Offline.](media/presence_offline.png) Appear offline | ![Gray circle with x, indicates Offline](media/presence_offline.png) Offline. When users aren't logged in on any of their devices for a few minutes, they appear offline. |
|  | ![Open gray circle, indicates status unknown.](media/presence_unknown.png) Status unknown |
|  | ![Purple circle with arrow, indicates Out of office.](media/presence_oof.png) Out of Office. Out of Office is used when an automatic reply is set or your calendar has an event set to show as "Out of Office." |

The order of statuses, from most available to least available, is:

1. Available
2. Busy
3. In a meeting
4. In a call
5. Do not disturb
6. Be right back
7. Away
8. Offline

Note

For users whose mailbox is hosted on-premises, presence delays of one hour (maximum) are expected.

## Automatic status settings

Normally, a user's status is based on user activity (whether they're **Available** or **Away**); on the state of the Teams app (for example, whether they're **In a call** or **Presenting**); and on their Outlook calendar (for example, whether they're **In a meeting**).

A user who isn't logged in to Teams on any device is **Offline**. Otherwise, their presence depends on whether they're logged in on a computer or on a mobile device:

- On a computer, a user's presence becomes **Away** automatically if they're inactive for a few minutes or if the computer is locked; and it becomes Offline when the computer enters sleep mode.
- On a mobile device, a user's presence becomes Away whenever the Teams app is in the background, and then becomes **Offline** after 24 hours of inactivity.

If a user is logged in to Teams on two or more devices (for example, on both a desktop computer and on a phone), then the device where they were active most recently determines their presence. Imagine a user is on both a computer and a mobile device, and they're currently working on the computer. Their presence comes from the computer. When they disconnect on the computer, their presence then comes from the status of the mobile device.

Call queues can use presence to route calls to agents. For more information, see [Create a Call Queue in Microsoft Teams](aa-cq-setup-call-queue).

## Manual status settings by users

Users can manually select a status as follows:

- Users in a call or in a meeting can select any status, and it lasts during the call or the meeting.
- Otherwise, users can select any status that is less available than the automatically calculated status. (For example, if a user's calculated status is **Do not disturb**, they could choose a status of **Away** but not **Available**.)

Users can set a duration for the presence that they set manually. If a user doesn't set a duration, their presence remains manually set as follows:

- Indefinitely if it's **Appear offline**
- For 1 day if it's **Busy** or **Do not disturb**
- For 7 days if it's any other status

## Notifications and Do not disturb

Users receive all chat messages regardless of their presence. If a user is offline when someone sends them a message, the chat message appears in Teams the next time they come online. If a user is in a **Do not disturb** state, they still receive chat messages, but banner notifications aren't displayed.

Users receive calls in all presence states except for Do not disturb, in which case incoming calls go to voicemail.

Users can add people to a priority access list by going to **Settings** &gt; **Privacy** in Teams. If they do, messages from these people display banner notifications as normal for that user. Even if the user is in a **Do not disturb** state, the user still receives calls from these people.

## Privacy settings

By default, your presence status is visible to all users globally.

You can customize [external access settings](trusted-organizations-external-meetings-chat) to control whether users can collaborate and share presence information with all external organizations, only specific organizations, or no external organizations.

Additionally, you can enable privacy mode. When privacy mode is enabled, presence is never shared outside your organization, regardless of your external access settings.

Privacy mode can be managed using the [Microsoft Teams PowerShell Module](teams-powershell-overview). To enable privacy mode, run the following command:

```powershell
Set-CsPrivacyConfiguration -Identity global -EnablePrivacyMode $True
```

To disable privacy mode, use the following command:

```powershell
Set-CsPrivacyConfiguration -Identity global -EnablePrivacyMode $False
```

Changes to privacy mode settings may take several hours to propagate.

## Admin settings in Teams compared to Skype for Business

The following admin settings Skype for Business are different in Teams:

- Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.
- Calendar integration (includes out of office and other calendar information) is always enabled for users when Teams is integrated with Outlook.
- The *Last seen* or *Away since* indicator is always enabled for users in Teams if the organization also uses Skype for Business.

Note

The ability of a Teams admin to customize these settings isn't currently supported.

## Admin settings in Teams compared to Microsoft Outlook

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later for contacts in the same organization.

If the upgrade mode policy of the user account is set to TeamsOnly, Outlook talks to Teams to get presence. If the user account isn't set to TeamsOnly, then Outlook talks to Skype for Business.

## Coexistence with Skype for Business

See [Coexistence with Skype for Business](coexistence-chat-calls-presence) for details on how Teams presence functions when your organization also uses Skype for Business.