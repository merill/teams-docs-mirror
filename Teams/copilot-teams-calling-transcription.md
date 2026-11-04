---
layout: Conceptual
title: Manage Microsoft Copilot in Teams calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/copilot-teams-calling-transcription
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
ms.reviewer: emkirby
ms.date: 2026-09-30T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- m365initiative-voice
- highpri
- Tier1
- teams-copilot
- magic-ai-copilot
description: Learn how to manage Microsoft Copilot in Teams for calls with calling policies in the Teams admin center. Learn how to manage transcripts and transcription for Copilot in Microsoft Teams for calls.
locale: en-us
document_id: cd939532-4f54-39ea-9b87-e1e41215517c
document_version_independent_id: cd939532-4f54-39ea-9b87-e1e41215517c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/copilot-teams-calling-transcription.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-teams-calling-transcription
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/copilot-teams-calling-transcription.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ade0f1f1-eeaf-3956-ae8b-842709c9c7f1
---

# Manage Microsoft Copilot in Teams calls - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) 1:1 Teams calls ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Public Switched Telephone Network (PSTN) calls

## Overview

Microsoft Copilot is a secure, AI-powered assistant that helps users stay productive by providing real-time insights and summaries for Teams calls. Each call participant with a Microsoft Copilot license can privately engage with Copilot using natural language prompts. Copilot identifies who said what, highlights shared perspectives with differing viewpoints, and suggests follow-up tasks—all during the call. As an admin, you can configure how users in your organization access and use Copilot in Teams calls.

There are two modes for users in your organization to use Copilot in calls:

- During and after the call
- Only during the call

The following table describes the differences between these two modes and how they work with call recording and transcription:

| Copilot setting in Calling Policy | Transcription started during call | Copilot available during call | Transcription available after call |
| --- | --- | --- | --- |
| Enabled | Yes | Available | Available |
| Enabled | No | Available | Not available |
| EnabledWithTranscript | Yes | Available | Available |
| EnabledWithTranscript | No | Not available | Not available |
| Disabled | Yes | Not available | Available |
| Disabled | No | Not available | Not available |

### During and after the call

As an admin, if you enable both transcription and Copilot for Teams for your users via calling policy, once a licensed user starts transcription (or recording) during a call, licensed users can select the Copilot button for use during and after the call.

After the call ends, licensed users can access the Copilot insights, summaries, and recap that were generated during the call. Depending on your organization's retention settings, users can return to access the transcript or recording. After the call, users can view the information exchanged with Microsoft 365 during the call and can ask Microsoft Copilot to generate new insights or summaries.

To learn more about how your users can use Copilot during and after the call, see [Get started with Copilot in Microsoft Teams Phone](https://support.microsoft.com/office/97c55ffb-1499-4b0a-8caa-980ebb4b697b).

Important

Teams calling policies control Copilot in one-to-one and group calls. Teams meeting policies control Copilot in scheduled meetings and Meet now.

If a one-to-one call becomes a group call by adding another participant, the recording, transcript, and related content remain associated with the original one-to-one chat. Participants added to the call can't access this content after the call. This is a known limitation.

### Only during the call

You can limit licensed users to use Copilot only during a call. In this mode, after a call ends, transcription or Copilot content generated during a call isn't retained. To enable this mode, you must use the Teams calling policy to turn on Copilot and turn off transcription for calls. Some organizations might prefer to only have Microsoft Copilot available during the call due to compliance and eDiscovery considerations.

By turning on Copilot for calls and turning off calling transcription, once a user with a Microsoft Copilot license selects the Copilot button during a call, Copilot runs for all licensed users. This option relies on speech-to-text audio processing data that isn’t saved after the call ends. The information exchanged between the user and Microsoft Copilot during the call isn't saved after the call ends, either. As shown later in this article, you can configure Copilot for Teams calls in the Teams admin center and via PowerShell.

This policy is only available for Teams *calls*. It’s not available for Teams meetings or events. For more information about Copilot in Teams meetings and events, see [Manage Microsoft Copilot in Teams meetings and events](/en-us/microsoftteams/copilot-teams-transcription).

To learn more about how call participants can use Copilot during and after a call, see [Get started with Copilot in Microsoft Teams Phone](https://support.microsoft.com/office/97c55ffb-1499-4b0a-8caa-980ebb4b697b).

As an IT admin, you can also set Copilot's value to **Off** for calling to prevent anyone in a call from using Copilot.

Important

Microsoft Copilot in Teams calls isn’t available in end-to-end encrypted calls. For more information on end-to-end encryption, see [Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls](/en-us/microsoftteams/teams-end-to-end-encryption).

## Prerequisites

### Licensing

- Assign your users a Microsoft 365 subscription that includes Teams or a Microsoft 365 (no Teams) subscription with a separate Teams license.
- For 1:1 Teams calls, assign an add-on Microsoft Copilot license for your intended users. To learn more about the Microsoft Copilot license, see [Microsoft Copilot documentation](/en-us/microsoft-365/copilot/).
- For Public Switched Telephone Network (PSTN) calls, also assign a Teams Phone license and have a calling plan for your users. For information on Teams Phone licensing, see [Microsoft Teams add-on licenses](/en-us/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing). To learn more about PSTN connectivity options, see [PSTN connectivity options](/en-us/microsoftteams/pstn-connectivity).

### Policies

#### Transcription

To allow your users to use Copilot with Teams calls *after* a PSTN or 1:1 peer-to-peer Voice over Internet Protocol (VoIP) call, turn on transcription via Teams calling policy. To turn on transcription, see [Configure call recording, transcription, and captions in Teams](/en-us/microsoftteams/call-recording-transcription-captions#enable-call-transcription). Otherwise, depending on your Copilot setting, Copilot is only available during the call.

To learn more about managing transcription, see [Configure call recording, transcription, and captions in Teams calls](/en-us/microsoftteams/call-recording-transcription-captions).

## Configure Copilot for Teams calls

As an admin, you can manage how users in your organization use Copilot for Teams calls. You can set the preferred method for Copilot with or without a saved transcript of the call. You can turn off the ability for users to transcribe Teams calls, but still allow them to use Copilot for other purposes.

Use the Teams admin center or PowerShell to manage how users in your organization use Copilot in Teams calls. You can apply your Copilot calling policies to groups or individual users.

The following table shows the behaviors of the settings for the `-Copilot` parameter used with [**Set-CsTeamsCallingPolicy**](/en-us/powershell/module/teams/set-csteamscallingpolicy) PowerShell cmdlet:

| Teams admins center policy value | PowerShell setting value | Behavior |
| --- | --- | --- |
| On | Enabled | **This is the default value**. Call participants can use Copilot with or without transcription during calls. If a licensed user doesn't start transcription during the call, users can't access a transcript after the call ends. |
| On with saved transcript required | EnabledWithTranscript | Users assigned this policy can only use Copilot when a licensed user starts transcription during a call. If transcription isn't enabled, then users can't see the Copilot option for the call and there isn't a transcript available after the call ends. |
| Off | Disabled | Copilot is off for calls. |

### Using the Teams admin center

To configure Copilot in Teams calls for your users from the Teams admin center, follow these steps:

1. Open the Teams admin center.
2. Expand **Voice** from the navigation pane.
3. Under **Voice**, select **Calling policies**.
4. Either select an existing policy or create a new one.
5. From the dropdown for the **Copilot** setting, select **On**, **On with saved transcript required**, or **Off**.
    - **On**: Call participants can use Copilot with or without transcription during calls.
    - **On with saved transcript required**: Users assigned this policy can only use Copilot when transcription is enabled during calls. If transcription isn't enabled, then users can't see the Copilot option for the call.
    - **Off**: Copilot is off for calls.
6. Select **Save**.

### Using PowerShell

To manage how users in your org use Copilot in Teams calls with PowerShell, use the `-Copilot` parameter within the [**SetCs-TeamsCallingPolicy**](/en-us/powershell/module/teams/set-csteamscallingpolicy) PowerShell cmdlet.

To allow licensed users to use Copilot during calls without requiring transcription, use the following command:

```PowerShell
Set-CsTeamsCallingPolicy -Identity <policy name> -Copilot Enabled
```

To turn off Copilot for calls, use the following command:

```PowerShell
Set-CsTeamsCallingPolicy -Identity <policy name> -Copilot Disabled
```

To require transcription for Copilot in calls and turn on call transcription, use the following command:

```PowerShell
Set-CsTeamsCallingPolicy -Identity <policy name> -Copilot EnabledWithTranscript -AllowTranscriptionForCalling $true
```