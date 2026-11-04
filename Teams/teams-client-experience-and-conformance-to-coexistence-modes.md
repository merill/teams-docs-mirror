---
layout: Conceptual
title: Teams client experience and conformance to coexistence modes - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-experience-and-conformance-to-coexistence-modes
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
ms.reviewer: bjwhalen
ms.date: 2019-02-12T00:00:00.0000000Z
audience: admin
description: Learn about Teams client experience and conformance to coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
locale: en-us
document_id: 4b0bac0e-750f-8ed9-b200-7d3f4f6b5259
document_version_independent_id: aae49dad-0257-3f7f-8a8e-76b9c9b340c1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-experience-and-conformance-to-coexistence-modes.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-experience-and-conformance-to-coexistence-modes
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-experience-and-conformance-to-coexistence-modes.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: 53198aee-a84f-ba85-18e7-c5df30549e27
---

# Teams client experience and conformance to coexistence modes - Microsoft Teams | Microsoft Learn

The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams. For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time. Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.

When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client. To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes. Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.

Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.

## How the available functionality in Teams client changes based on mode

The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy. The following table summarizes the behavior:

| User's effective mode | Experience in Teams client |
| --- | --- |
| Any Skype for Business mode | Calling, Chat, and self-presence are disabled. |
| SfBWithTeamsCollabAndMeetings | Meeting scheduling is available |
| SfBWithTeamsCollab or SfBOnly^1^ | Meeting scheduling isn't available |
|  |  |

The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes. The chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):

![A side-by-side comparison of Teams modes.](media/teams-mode-comparison.png)

In addition, self presence isn't available in the other modes, as shown here.

![Screenshot of self presence in Meetings First.](media/meetings-first-no-self-presence-general.png)

**Note:**^1^ At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams. In the interim, Channels can be hidden using the App Permissions policy.

## Impact of Mode on other policy settings

As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client. This means that the value of mode can take precedence over the value of other policy settings, depending on the mode. Specifically, coexistence mode impacts whether the following policy settings are honored:

| **Modality (App)** | **Policy.Setting** |
| --- | --- |
| Chat | TeamsMessagingPolicy.AllowUserChat |
| Calling | TeamsCallingPolicy.AllowPrivateCalling |
| Meeting scheduling | TeamsMeetingPolicy.AllowPrivateMeetingSchedulingTeamsMeetingPolicy.AllowChannelMeetingScheduling |
|  |  |

Administrators need *not* explicitly set these policy settings when using coexistence mode, but it's important to understand that these settings effectively behave as follows for a given mode.

| Mode | AllowUserChat | AllowPrivateCalling | AllowPrivateMeetingScheduling | AllowChannelMeetingScheduling |
| --- | --- | --- | --- | --- |
| TeamsOnly or Islands | Enabled | Enabled | Enabled | Enabled |
| SfBWithTeamsCollabAndMeetings | Disabled | Disabled | Enabled | Enabled |
| SfBWithTeamsCollab or SfBOnly | Disabled | Disabled | Disabled | Disabled |
|  |  |  |  |  |

When you're using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell. As noted above, is no longer necessary to set these other policy settings. The following is an example of what the PowerShell warning looks like:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`