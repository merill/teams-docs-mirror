---
layout: Conceptual
title: Manage reactions in Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-reactions-meetings
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
ms.reviewer: defnea
ms.date: 2026-07-06T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- Tier2
- m365initiative-meetings
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Learn to manage meeting reactions in Teams meetings and events.
locale: en-us
document_id: 772c3528-cca4-3007-6a61-2c086ac17be7
document_version_independent_id: 772c3528-cca4-3007-6a61-2c086ac17be7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-reactions-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-reactions-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-reactions-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 485a391f-0c1b-5b03-8fe0-10e91fc342fb
---

# Manage reactions in Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

## Overview

Reactions in Microsoft Teams meetings and events enhance communication and engagement by allowing participants to express their feedback in real time.

As an admin, you can use the Teams admin center or PowerShell to set the default value for reactions in your organizers' **Meeting options**. Organizers can change the setting for each meeting and event they create.

For more information about how users can use reactions, see [Express yourself in Microsoft Teams meetings with live reactions](https://support.microsoft.com/office/express-yourself-in-microsoft-teams-meetings-with-live-reactions-a8323a40-3d07-4129-934b-305370a36e21).

## Manage reactions

By default, meeting reactions are set to **On** in your organizers' **Meeting options**.

### Using the Teams admin center

To manage the default value for meeting reactions, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy that you want to edit.
3. Under **Meeting engagement**, turn the **Reactions** toggle **On** or **Off**.
4. Select **Save**.

### Using PowerShell

To manage the default value for meeting reactions, use the **`-AllowMeetingReactions`** parameter within the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

To set the default value for meeting reactions to **Off** for organizers with the policy, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingReactions Disabled
```