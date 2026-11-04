---
layout: Conceptual
title: Manage real-time text (RTT) in Teams for users in your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-real-time-text
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: csano, harinlee
ms.date: 2025-06-24T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-voice
- highpri
- Tier1
description: Learn how to manage real-time text (rtt) for your users’ meetings and calls.
locale: en-us
document_id: 574821e7-60c4-fd5e-7dcf-aff4d8fb9e72
document_version_independent_id: 574821e7-60c4-fd5e-7dcf-aff4d8fb9e72
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-real-time-text.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-real-time-text
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-real-time-text.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: de54ca0c-44db-dce3-5998-d16d4a264b97
---

# Manage real-time text (RTT) in Teams for users in your organization - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) 1:1 and group VoIP calls

## Overview

Real-Time Text (RTT) in Microsoft Teams allows participants to instantly send and see written messages on the screen during calls and meetings. RTT displays each character while participants type, which is beneficial for participants with accessibility needs and in situations where voice communication isn’t practical. Unlike chat, RTT messages are sent and received immediately, without participants taking any extra action to send. As an admin, you can manage whether your users can use RTT in Teams meetings, group calls, and 1:1 VoIP calls.

[![Screenshot of a Teams meeting where participants are using RTT.](media/real-time-text-meetings-small.png)](media/real-time-text-meetings-expand.png#lightbox)

## How it works

RTT messages are transmitted over dedicated data channels, allowing each character to be sent and received instantly. This real-time flow is essential for maintaining conversational fluidity. These data channels remain active throughout a call or meeting, ensuring continuous delivery of text. The user interface displays RTT content on the meeting screen, manages the message list, and handles input interactions based on when messages are finalized. When a call is placed on hold, the data channel is paused and resumes once the call continues. This setup ensures RTT messages are always visible and delivered in real time to all participants.

## Manage whether your users can use RTT in Teams meetings and group calls

You can use the Teams admin center or PowerShell to manage whether your users can use RTT in Teams meetings and group calls. **This policy setting is on by default.**

### Teams admin center for meetings and group calls

1. Open the Teams admin center.
2. Expand **Meetings** from the navigation pane.
3. Under **Meetings**, select **Meeting policies**.
4. Either select an existing policy or create a new one.
5. Navigate to the **Recording and transcription** section.
6. Toggle the **Real-time-text (RTT)** setting **On** (default) or **Off** .
7. Select **Save**

### PowerShell

To manage how users in your org use RTT in Teams meetings and group calls, use the **`- RealTimeText`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet. To prevent users with this policy from using RTT in Teams meetings and group call, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -RealTimeText Disabled
```

## Manage whether your users can use RTT in Teams 1:1 VoIP calls

You can use the Teams admin center or PowerShell to manage whether your users can use RTT in Teams 1:1 VoIP calls. **This policy setting is on by default.**

### Teams admin center for 1:1 VoIP calls

1. Open the Teams admin center.
2. Expand **Voice** from the navigation pane.
3. Under **Voice**, select **Calling policies**.
4. Either select an existing policy or create a new one.
5. Toggle the **Real-time-text (RTT)** setting **On**(default) or **Off** .
6. Select **Save**

### PowerShell for 1:1 VoIP calls

To manage how users in your org use RTT in Teams meetings and group calls, use the **`- RealTimeText`** parameter within the PowerShell [**CsTeamsCallingPolicy**](/en-us/powershell/module/teams/set-csteamscallingpolicy) cmdlet. To prevent users with this policy from using RTT in Teams 1:1 VoIP calls, use the following script:

```PowerShell
Set-CsTeamsCallingPolicy -Identity <policy name> -RealTimeText Disabled
```

## User experience

- To see RTT in recordings, users must turn on captions.
- Users joining meetings from Microsoft Teams Rooms, can see, but can’t send RTT on the screen.

To learn more about the RTT experience for your users, see [Real-Time Text (RTT) In Microsoft Teams](https://support.microsoft.com/office/real-time-text-rtt-in-microsoft-teams-bd56f3ce-1ed6-4521-94a1-7244304b67f6).

## Feature support

### Supported

RTT is supported on the following platforms and types of meetings and calls:

- Meetings
- Group calls
- 1:1 VoIP calls
- Microsoft Teams Rooms meetings (Windows and Android)
- Mobile devices (iOS and Android)
- Compliance recordings
- Teams phone devices only in read-only mode.

### Not supported

RTT isn’t supported on the following platforms and types of meetings and calls:

- PSTN calls
- Emergency calling
- Events
- End to end encrypted meetings

## Data storage

RTT follows the same storage as transcription. To learn more, see [Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change).