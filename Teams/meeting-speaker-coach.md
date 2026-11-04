---
layout: Conceptual
title: Speaker Coach in Microsoft Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-speaker-coach
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: bryannyce
ms.date: 2026-07-06T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier2
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
description: IT admins - Learn how to manage whether users in your organization can use Speaker Coach during meetings and events.
locale: en-us
document_id: 8bb68af0-cd33-c0c8-f689-b2aa21d953b0
document_version_independent_id: 8bb68af0-cd33-c0c8-f689-b2aa21d953b0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-speaker-coach.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-speaker-coach
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-speaker-coach.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b592d11a-a6cb-1b23-c723-5ef67a387543
---

# Speaker Coach in Microsoft Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

## Overview

Speaker Coach in Teams meetings and events processes a user's audio while they present, as well as the audio of all unmuted participants, providing private real-time feedback and suggestions for improvement. The user who turns on Speaker Coach receives a summary report of the feedback after the meeting or event, which only they can view. You don't have access to this data.

Note

In Teams events, Speaker Coach applies only to organizers, co-organizers, and presenters.

As an admin, you can manage whether users in your organization can use Speaker Coach during meetings and events.

To learn more about how your users use Speaker Coach, see [Speaker Coach in Microsoft Teams meetings](https://support.microsoft.com/teams/meetings-events/speaker-coach-in-microsoft-teams-meetings).

## Manage Speaker Coach by using PowerShell

You use PowerShell to manage Speaker Coach through the **`-AllowMeetingCoach`** parameter within the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet. Or, you can create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/new-csteamsmeetingpolicy) cmdlet and assign it to users.

Speaker Coach is on by default. To turn off Speaker Coach, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingCoach False
```