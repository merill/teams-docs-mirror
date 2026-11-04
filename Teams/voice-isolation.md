---
layout: Conceptual
title: Manage voice isolation for your users' Microsoft Teams calls and meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/voice-isolation
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: tonysmit
author: MSTonySmith
manager: pamgreen
ms.reviewer: elaineho
ms.date: 2026-04-16T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- m365initiative-meetings
- teams-rooms-devices
- highpri
- Tier1
- magic-ai-copilot
description: Learn how to manage whether users can use voice isolation for IT Admins in Microsoft Teams.
locale: en-us
document_id: 842c9bfa-1282-e6c8-3f2f-c9cbcf517d6a
document_version_independent_id: 842c9bfa-1282-e6c8-3f2f-c9cbcf517d6a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/voice-isolation.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: voice-isolation
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/voice-isolation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d4daa8f7-4c1d-719e-5e32-cfc5935b21ac
---

# Manage voice isolation for your users' Microsoft Teams calls and meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Calls

Voice isolation reduces noise and uses the personalized deep voice quality enhancement artificial intelligence (AI) model to separate the user's voice from other sounds and voices in Microsoft Teams calls and meetings. As an admin, you can control whether your users can use voice isolation in calls and meetings.

The voice isolation feature relies on the voice profile, stored on the user's local device, to remove any sounds or voices during a call or meeting that don't match the profile. Your users' voice profiles are only used for the reason they gave their permission for; Microsoft doesn't use their voice profiles for anything else. To use the voice isolation feature, your users must have a voice profile. To learn about how your users can set up a voice isolation profile, see [Create your Microsoft Teams recognition profile](https://support.microsoft.com/office/create-recognition-profiles-for-microsoft-intelliframe-f0084478-52a7-4c52-bcdc-9063ed0e0bc0).

To learn about enrollment, see [Overview of voice and face enrollment](/en-us/microsoftteams/rooms/voice-and-face-recognition).

To learn more about voice isolation troubleshooting, setup, and the experience for your users, see [Voice isolation in Microsoft Teams calls and meetings](https://support.microsoft.com/office/voice-isolation-in-microsoft-teams-calls-and-meetings-a9756ea9-4cec-44c4-aefb-6f5d17c89427).

## Manage whether your users can use voice isolation

You must set the **`-VoiceIsolation`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) and **`-EnrollVoice`** and/or the **`-PassiveVoiceEnrollment`** parameter within the [CsTeamsAIPolicy](/en-us/powershell/module/teams/set-csteamsaipolicy) cmdlet to manage whether your users can use voice isolation.

| **`-VoiceIsolation`**parameter value | Behavior |
| --- | --- |
| Enabled | **This is the default value.** Users with this policy can use voice isolation in Teams calls and meetings. |
| Disabled | Users with this policy can't use voice isolation in Teams calls and meetings. |

| **`-EnrollVoice`**parameter value | Behavior |
| --- | --- |
| Enabled | **This is the default value.** Users with this policy can set the voice profile capture and enrollment through the **Recognition** tab in their Teams client settings. |
| Disabled | Users with this policy can't use or access the voice profile capture or enrollment. |

| **`-PassiveVoiceEnrollment`**parameter value | Behavior |
| --- | --- |
| Enabled | **This is the default value.** Users with this policy can set the voice profile capture and enrollment via Express enrollment or through the **Recognition** tab in their Teams client settings. |
| Disabled | Users with this policy can't use or access the voice profile capture or enrollment. |

Before you can run these cmdlets, you must be connected to Microsoft Teams PowerShell. For more information, see [Manage Teams with Microsoft Teams PowerShell](/en-us/microsoftteams/teams-powershell-managing-teams).

For more information on PowerShell cmdlets for Teams meetings, see the Related topics section.

### Allow users to use voice isolation

To allow users with this policy to use voice isolation, use the following scripts:

```powershell
Set-CsTeamsAIPolicy -Identity <policy name> -EnrollVoice Enabled
```

```powershell
Set-CsTeamsAIPolicy -Identity <policy name> -PassiveVoiceEnrollment Enabled
```

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -VoiceIsolation Enabled
```

### Prevent users from using voice isolation

To prevent users with this policy from using voice isolation, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -VoiceIsolation Disabled
```