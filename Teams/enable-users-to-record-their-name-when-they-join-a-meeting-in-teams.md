---
layout: Conceptual
title: Allow users to record their name for a meeting - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams
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
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-collaboration
- Tier1
- m365initiative-meetings
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Learn how to manage whether your users can record their names when they join a meeting in Microsoft Teams.
locale: en-us
document_id: fd82ee8d-23b6-ce9a-1c37-3839f4359dca
document_version_independent_id: 4120f4d3-3f8c-290f-3dfc-c56338dcce95
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enable-users-to-record-their-name-when-they-join-a-meeting-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6015480e-947c-ef47-d2ec-889829e38363
---

# Allow users to record their name for a meeting - Microsoft Teams | Microsoft Learn

When you set up Audio Conferencing in Microsoft 365 or Office 365, you get phone numbers for your users through an audio conferencing bridge. A conferencing bridge can have one or more phone numbers that are included at the bottom of the meeting invite. These phone numbers allow users to join Microsoft Teams meetings by dialing in.

As an admin, you can manage whether callers who dial in can record their name before joining a meeting.

## Allow callers to record their name in the Teams admin center

Using the Microsoft Teams admin center:

1. In the left navigation, select **Meetings** &gt; **Conference Bridges**.
2. At the top of the **Conference Bridges** page, select **Bridge settings**.
3. Toggle **Meeting entry and exit notifications** to on.
4. For **Entry/exit announcement type** select **Names or phone numbers** from the dropdown.
5. Toggle **Ask callers to record their name before joining a meeting** to **On**.
6. Select **Save**.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Manage whether callers can record their names with PowerShell

To manage whether callers can record their names with PowerShell, use the **`-EnableNameRecording`**. **`-EntryExitAnnouncementsType`**, and **`-EnableNameRecording`** parameters, within the PowerShell [Set-CsOnlineDialInConferencingTenantSettings](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) cmdlet. For script examples, see [Set-CsOnlineDialInConferencingBridge](/en-us/powershell/module/teams/Set-csonlinedialinconferencingtenantsettings).