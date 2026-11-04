---
layout: Conceptual
title: Manage Teams meeting auto recording - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-teams-auto-recording
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Manage Teams meeting auto recording
author: dj1298
manager: adam
ms.author: djball
ms.service: msteams
ms.topic: how-to
ms.date: 2026-05-06T00:00:00.0000000Z
locale: en-us
document_id: ad9e7c28-8a7c-2dd2-c7c5-2f50f82ccd66
document_version_independent_id: ad9e7c28-8a7c-2dd2-c7c5-2f50f82ccd66
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-teams-auto-recording.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-teams-auto-recording
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-teams-auto-recording.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 942fe3a7-7734-df33-2883-9a55f91e4b3e
---

# Manage Teams meeting auto recording - Microsoft Teams | Microsoft Learn

You can control whether organizers have access to the **Record and transcribe automatically** setting in meeting options, webinars, and town halls. You can only apply this policy setting to users and groups.

When you turn on the auto recording policy for an organizer, the meeting option for **Record and transcribe automatically** is **Off** by default. Organizers must manually enable **Record and transcribe automatically** setting for each meeting they want recorded and transcribed automatically. If you turn off auto recording, organizers don't see **Record and transcribe automatically** in meeting options and can’t set meetings to record automatically.

For webinars and town halls, the setting is **On** by default.

Note

This setting doesn't apply to transcripts.

You must use PowerShell or a meeting template to manage this setting for organizers.

To manage this setting with meeting templates, see [IT admins - Create a custom meeting template in Microsoft Teams](create-custom-meeting-template). Only organizers with a Teams Premium license can use assigned meeting templates. If you prefer to prevent the organizers from changing your settings, you can lock the value you selected. Once the template is activated, users see it when scheduling meetings. If they choose to use this template, recording and transcription starts automatically without any user interaction.

To manage this setting using PowerShell, use the **`-AutoRecording`** parameter in [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy). For details, see the PowerShell section in this article.

### Manage auto recording in PowerShell

To give organizers with this policy the option to record their meetings, webinars, and town halls automatically, follow this script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AutoRecording Enabled
```

To prevent organizers with this policy from recording their meetings, webinars, and town halls automatically, follow this script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AutoRecording Disabled
```