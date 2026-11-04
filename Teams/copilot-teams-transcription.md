---
layout: Conceptual
title: Manage Microsoft Copilot in Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/copilot-teams-transcription
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: elederman
ms.date: 2026-08-11T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
- teams-copilot
- magic-ai-copilot
description: Manage Microsoft Copilot in Teams meetings and events using admin policies. Learn how to manage transcripts and transcription, configure Copilot settings, and apply policies.
locale: en-us
document_id: 84008eda-32cc-9b82-c9e9-38afc746f42b
document_version_independent_id: 84008eda-32cc-9b82-c9e9-38afc746f42b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/copilot-teams-transcription.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-teams-transcription
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/copilot-teams-transcription.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9e10e7ab-ab42-b97d-6c44-e427bcebf4ef
---

# Manage Microsoft Copilot in Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Microsoft Copilot in Teams meetings and events is an artificial intelligence (AI) tool that captures important conversation points.

Each participant with a Microsoft Copilot license in a meeting or in an event with up to 1,000 attendees can ask prompts that are only visible to them. Participants and organizers can learn things like who said what and where people agree or disagree. Microsoft Copilot in Teams can also recommend follow-up tasks, all in real time during a meeting. In events [optimized for large audiences](plan-events), only organizers, co-organizers, and presenters can use Copilot during the event.

As an admin, you can manage how users in your organization use Copilot for Teams meetings and events.

## Overview

There are two ways for users in your organization to use Copilot in meetings and events:

- During and after the meeting
- Only during the meeting

Important

When organizers turn off Copilot for their meeting or event, recording and transcription are also turned off.

### During and after the meeting

When organizers create a meeting or event, they can set Copilot's value to **During and after the meeting** from the dropdown list in their meeting options. Once someone starts transcription, licensed users can select the Copilot button for use during, and after the meeting or event.

To learn more about how organizers can use Copilot during and after the meeting, see [Get started with Microsoft Copilot in Teams in Microsoft Teams meetings](https://support.microsoft.com/office/get-started-with-copilot-in-microsoft-teams-meetings-0bf9dd3c-96f7-44e2-8bb8-790bedf066b1).

### Only during the meeting

When organizers create a meeting or event, they can set Copilot's value to **Only during the meeting** from the dropdown list in their meeting options. Once someone with a Microsoft Copilot license selects the Copilot button during the meeting or event, Copilot runs for all licensed users. This option relies on speech-to-text audio processing data that isn't saved after the meeting or event ends.

Depending on your organization's Microsoft Purview retention policies, Copilot prompts and responses during meetings might be retained for compliance purposes, even if recording and transcription are turned off. This applies to Commercial and GCC cloud environments but not to DoD.

To learn more about how organizers can use Copilot only during the meeting, see [Use Microsoft Copilot in Teams without recording a Teams meeting](https://support.microsoft.com/office/use-copilot-without-recording-a-teams-meeting-a59cb88c-0f6b-4a20-a47a-3a1c9a818bd9).

Meeting or event organizers can also set Copilot's value to **Off** to prevent anyone in the meeting from using Copilot. This option disables recording and transcription for the meeting. You have a policy to set the default to **Off**, but your organizers can manage this setting on a per-meeting basis.

For information about using Copilot only during Teams *calls*, see [Manage Microsoft Copilot in Teams calls](copilot-teams-calling-transcription).

Important

Microsoft Copilot in Teams meetings and events isn't available in end-to-end encrypted meetings. For more information on end-to-end encryption, see [Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls](teams-end-to-end-encryption).

Note

Microsoft Copilot in Teams isn't currently available for GCC High.

## Prerequisites

- An add-on Microsoft Copilot license for intended users. To learn more about the Microsoft Copilot license, see [Microsoft Copilot documentation](/en-us/microsoft-365-copilot).

## Transcription

You can use the **Recording & Transcription** section in the Teams admin center or the **`-AllowTranscription`** parameter in the [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) PowerShell cmdlet to manage your transcription policy. This setting's value affects how, or if, Copilot works for your users. The following table shows how the transcription policy works with the organizer's Copilot in Teams meeting options:

| Admin's transcription policy value | Organizer's Copilot meeting option | Behavior |
| --- | --- | --- |
| On | Only during the meeting | Licensed users can select the Copilot button for use only during this meeting with temporary speech-to-text data. To use Copilot during, and after the meeting, these users can start a transcript. |
| Off | Only during the meeting | Licensed users can select the Copilot button for use during this meeting or event with temporary speech-to-text data. If another participant who can transcribe enables transcription, Copilot is available during, and after the meeting for the portion that is transcribed. |
| On | During and after the meeting | Once licensed users turn on transcription, they can select the Copilot button for use during, and after this meeting or event. |
| Off | During and after the meeting | Licensed users can't interact with Copilot unless another participant with permission to transcribe turns on transcription for this meeting. |
| Any | Off | Licensed users can't interact with Copilot in Teams. No one can record or transcribe. |

To learn more about managing transcription, see [Configure transcription and captions for Teams meetings](meeting-transcription-captions).

## Manage Copilot for Teams meetings and events

You can use the Teams admin center or PowerShell to manage how users in your org use Copilot in Teams meetings and events.

The following table shows the behaviors of the settings for the **`-Copilot`** parameter:

| Teams admins center policy value | PowerShell setting value | Behavior |
| --- | --- | --- |
| On | Enabled | When organizers with this policy create meetings and events, Copilot's default value in their meeting options is **Only during the meeting**. Organizers can change this value to **During and after the meeting**, and **Off**. |
| On with saved transcript required | EnabledWithTranscript | **This is the default value**. When organizers with this policy create meetings and events, Copilot's default value in their meeting options is **During and after the meeting**. This option is enforced; organizers can't change this value. |
| On with transcript saved by default | EnabledWithTranscriptDefaultOn | When organizers with this policy create meetings and events, Copilot's default value in their meeting options is **During and after the meeting**. Organizers can change this value to **Only during the meeting**, and **Off**. |
| Off | Disabled | When organizers with this policy create meetings and events, Copilot's default value in their meeting options is **Off**. Organizers can change this value to **Only during the meeting** or **During and after the meeting**. |

### Manage Copilot for Teams meetings and events in the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one.
3. Go to the **Recording & transcription** section and find the **Copilot** setting.
4. In the dropdown list, choose **On**, **On with saved transcript required**, **On with transcript saved by default**, or **Off**.
5. Select **Save**.

You can apply your Copilot meeting policies to groups or individual users. You can also add Copilot to your meeting templates. To learn how to apply Copilot to meeting templates, see [IT admins - Create a custom meeting template in Microsoft Teams](create-custom-meeting-template).

### Manage Copilot for Teams meetings and events using PowerShell

To manage how users in your org use Copilot in Teams meetings and events, use the **`-Copilot`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

To allow users to use Copilot **Only during the meeting** in meetings and events created by organizers with this policy:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -Copilot Enabled
```

To set the organizer's default Copilot option to **During and after the meeting** and allow them to change it, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -Copilot EnabledWithTranscriptDefaultOn
```

To set the organizer's default Copilot option to **Off** and allow them to change it, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -Copilot Disabled
```