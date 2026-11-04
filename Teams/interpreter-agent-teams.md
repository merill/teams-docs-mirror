---
layout: Conceptual
title: Manage Interpreter agent for your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/interpreter-agent-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: wlibebe
ms.author: wlibebe
manager: pamgreen
ms.reviewer: harinlee
ms.date: 2026-09-21T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.collection:
- m365initiative-meetings
- magic-ai-copilot
ms.custom:
- admindeeplinkTEAMS
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to manage Interpreter agent in Microsoft Teams to provide translation during meetings and calls.
locale: en-us
document_id: 2c2cd421-990d-1226-5e07-8ccece067f33
document_version_independent_id: 2c2cd421-990d-1226-5e07-8ccece067f33
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/interpreter-agent-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: interpreter-agent-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/interpreter-agent-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: 971b2bc9-bb26-c979-e087-967a597e9066
---

# Manage Interpreter agent for your organization - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Calls ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events

Interpreter agent acts as a translator in Microsoft Teams meetings, allowing participants with a Microsoft Copilot license to listen to the meeting in their chosen language. Interpreter listens to the spoken language in the meeting and translates it into another language in real-time, allowing participants who speak different languages to understand each other and collaborate effectively. To represent their voices, participants can choose to have Interpreter **simulate their own voice** when translating to others or select one of the following **preset automated voices**: Ava (female), Andrew (male), Fable Turbo (neutral). If an automated voice is selected, **Ava is the default.**

As an admin, you can control whether your organization can use Interpreter and select the default voice option for how users' speech is heard by others.

To learn more about the Interpreter experience in meetings, see [Interpreter in Microsoft Teams meetings](https://support.microsoft.com/office/interpreter-in-microsoft-teams-meetings-c7efe2bb-535d-42ab-a5c4-d2d91619b46d).

## Supported languages

Interpreter supports the following languages for speaking and listening: Chinese (Mandarin), English, French, German, Italian, Japanese, Korean, Portuguese, Spanish.

## Prerequisites and licensing

The following list contains the prerequisites for users to access Interpreter in Teams meetings. Users must meet all the following requirements:

Important

Interpreter agent is available as part of the Microsoft Copilot license. **A Microsoft M365 license is required** to listen to others’ speech through the Interpreter agent. 20 hours of interpretation is included per user per month with a Microsoft Copilot license. Access beyond the hours included is subject to available capacity.

- An eligible *Microsoft 365*base license.
    - For the list of eligible base licenses, see [Understand licensing requirements for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing).
- An eligible *Microsoft Teams*license.
    - Teams licenses might be included in your *Microsoft 365* subscription, or you might need to purchase a separate Teams license if you have *Microsoft 365 (no Teams)* licenses.
- A *Microsoft Copilot*license.
    - 20 hours of interpretation is included per user per month with a Microsoft Copilot license. Access beyond the hours included is subject to available capacity.
    - For information on how to acquire *Microsoft Copilot* licenses, see [Where can I get Microsoft Copilot?](https://support.microsoft.com/topic/where-can-i-get-microsoft-copilot-40a622db-6d25-4266-b008-4bbcb55cf52f)
- Or a *Teams Rooms Pro*license.
    - For Teams Rooms devices, a *Teams Rooms Pro* license is required in place of the *Microsoft Copilot* license.
    - 20 hours of interpretation is included per user per month with a *Microsoft Teams Rooms Pro* license.
    - For more information on *Microsoft Teams Rooms Pro* licensing, see [Teams Rooms licensing](/en-us/microsoftteams/rooms/rooms-licensing).

## Data, security, and privacy

When your users allow Interpreter to simulate their voice, their voice sample isn’t stored.

### How Interpreter works

Interpreter performs real-time speech-to-speech (STS) translation using Azure Cognitive Services, supporting multi-speaker, mixed-language conversations in Teams meetings. Here's how it works:

1. Speech Recognition (ST)- Converts spoken language into English text.
2. Machine translation (MT)- Translates English text into the selected languages.
3. Text-to-speech (TTS)- Produces translated speech in the chosen language. TTS can simulate the speaker’s voice or use a predefined voice based on user preference and the admin policy.
4. A bot transmits meeting audio for cloud-based processing and returns translations instantly.

### How Interpreter uses your users' voices

Voice simulation generates translated speech in your user's voice, allowing other participants to hear translations as if they're speaking their language directly. When a user turns on this feature in Interpreter, the system briefly analyzes short segments of their speech on the fly (in real-time) to simulate their unique tone, style, and voice characteristics. **Voice samples or biometric data are never stored.** AI instantly creates a natural-sounding voice in the selected language, preserving their authentic tone, pitch, and speaking style without exaggerating emotions. This ensures a familiar and seamless multilingual conversation experience.

#### Real-time processing without storing voice data

Voice data is processed immediately, entirely on the fly, without ever storing your users' voice samples or biometric information. The following diagram illustrates this real-time and secure processing:

- Original audio streams are briefly analyzed by the system in real-time.
- ACS Speech services instantly provide translated speech simulation.
- No voice samples or biometric data are retained after processing.

[![Architecture diagram of language media processing to ACS speech.](media/interpreter-agent-diagram-small.png)](media/interpreter-agent-diagram-expand.png#lightbox)

## Manage Interpreter using PowerShell

You must use PowerShell to manage Interpreter for your entire organization.

To manage Interpreter for your entire organization, you can use the **`-AIInterpreter`** and **`-VoiceSimulationInInterpreter`** parameters in the following PowerShell cmdlets:

| Scenario | Cmdlet |
| --- | --- |
| Teams meetings | [CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) |
| 1:1 Teams VoIP calls | [CsTeamsCallingPolicy](/en-us/powershell/module/microsoftteams/set-csteamscallingpolicy) |

### Manage Interpreter in meetings

#### Turn Interpreter on or off

The org-wide **`-AIInterpreter`** parameter controls whether your users with a Microsoft Copilot license can use Interpreter during meetings in your organization. **This parameter is enabled by default.**

To turn off Interpreter for your entire organization, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AIInterpreter Disabled
```

To turn on Interpreter for your entire organization, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AIInterpreter Enabled
```

#### Set the default value for how users can set their preference for how others hear their speech via Interpreter

The org-wide **`-VoiceSimulationInInterpreter`** parameter controls your users' default value for **Choose your voice when interpreted** in **Interpreter settings**. The **Choose your voice when interpreted** setting controls how a user's voice is represented to other participants. **By default, this parameter is set to enabled.**

Here's the user experience for Interpreter depending on the value you choose:

- **Enabled**: Sets the default value for **Choose your voice when interpreted** to **Simulate my voice**. When users with a Microsoft Copilot license turn on Interpreter, it automatically simulates their voices when translating to others in meetings. All participants in an Interpreter-enabled meeting can also select an automated voice. **This is the default value.**
- **Disabled**: Sets the default value for **Choose your voice when interpreted** to **Automated voice**. When users with a Microsoft Copilot license turn on Interpreter, by default, Ava (female) option is selected by default among the automated voices. All participants in an Interpreter-enabled meeting can select another automated voice or choose to have Interpreter simulate their own voice.

To set the org-wide default value for the **Choose your voice when interpreted** setting to **Simulate my voice**, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -VoiceSimulationInInterpreter Enabled
```

To set the org-wide default value for the **Choose your voice when interpreted** setting to **Automated voice**, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -VoiceSimulationInInterpreter Disabled
```

Important

It's highly recommended to confirm **VoiceSimulationInInterpreter** is set to **Enabled** to deliver the best listening experience for interpretation.

### Manage Interpreter in calls

Use [CsTeamsCallingPolicy](/en-us/powershell/module/microsoftteams/set-csteamscallingpolicy) to configure Interpreter for supported 1:1 Teams-to-Teams VoIP calls.

#### Turn Interpreter on or off

The **`-AIInterpreter`** parameter controls whether your users with a Microsoft Copilot license can use Interpreter during 1:1 VoIP calls in your organization. **This parameter is enabled by default.**

To turn off Interpreter for your entire organization, use the following script:

```PowerShell
Set-CsTeamsCallingPolicy -Identity <policy name> -AIInterpreter Disabled
```

To turn on Interpreter for your entire organization, use the following script:

```PowerShell
Set-CsTeamsCallingPolicy -Identity <policy name> -AIInterpreter Enabled
```

## Supported platforms and clients

### Supported

Interpreter is supported on the following platforms and clients:

- 1:1 Teams-to-Teams VoIP calls
- Teams desktop (Windows and Mac)
- Teams mobile (iOS and Android)
- Teams web (Chrome, Microsoft Edge, Safari, and Firefox)
- Teams Rooms on Windows
- Scheduled meetings
- Channel meetings
- Virtual Desktop Infrastructure (VDI)

### Not supported

Interpreter isn't supported on the following platforms and clients:

- 1:1 PSTN calls (Public Switched Telephone Network)
- Teams events
- Microsoft Teams Rooms on Android
- Using personal peripherals with Microsoft Teams Rooms
- Microsoft Teams free