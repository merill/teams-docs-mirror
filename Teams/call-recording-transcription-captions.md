---
layout: Conceptual
title: Configure call recording, transcription, and captions in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/call-recording-transcription-captions
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.reviewer: jastark
ms.date: 2026-06-19T00:00:00.0000000Z
audience: admin
search.appverid: MET150
description: Learn how to enable users to record, transcribe, and turn on captions for calls in Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- CSH
locale: en-us
document_id: d149966d-f418-1e85-d4ef-dd9cea05e708
document_version_independent_id: d149966d-f418-1e85-d4ef-dd9cea05e708
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/call-recording-transcription-captions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: call-recording-transcription-captions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/call-recording-transcription-captions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fb24f854-d6ec-a786-ca29-cd136f7c1183
---

# Configure call recording, transcription, and captions in Teams - Microsoft Teams | Microsoft Learn

Users can record, transcribe, and view captions in Teams calls. This article explains how to configure these features for your users. For an overview of recording and transcription policies for Teams calls and meetings, see [Overview: Recording and transcription for Teams meetings, events, and calls](recording-transcription-overview).

For information on managing transcription for Microsoft Copilot in Teams calls, see [Manage Microsoft Copilot in Teams calls](copilot-teams-calling-transcription).

For optimal accessibility, see [Accessibility guide for Microsoft Teams admins](accessibility-guide-admin) to configure Teams.

## Enable call recording

Use the Microsoft Teams admin center or PowerShell to set a Teams calling policy to control whether a user's 1:1 Teams call or Public Switched Telephone Network (PSTN) call can be recorded.

Many users use calls and meetings interchangeably depending on their needs. We recommend you check your meeting recording policy settings as well. If the settings are different for calls and meetings, it might cause confusion for your users.

### Using the Teams admin center

To allow call recordings:

1. In the Microsoft [Teams admin center](https://admin.teams.microsoft.com/), select **Voice** &gt; **Calling policies**.
2. Select the policy that you want to edit.
3. Turn **Cloud recording for calling** to **On**.
4. Select **Save**.

### Using PowerShell

With PowerShell, you can configure the `-AllowCloudRecordingForCalls` parameter and manage the resulting policy with the following cmdlets:

- [Get-CsTeamsCallingPolicy](/en-us/powershell/module/teams/get-csteamscallingpolicy)
- [New-CsTeamsCallingPolicy](/en-us/powershell/module/teams/new-csteamscallingpolicy)
- [Set-CsTeamsCallingPolicy](/en-us/powershell/module/teams/set-csteamscallingpolicy)
- [Remove-CsTeamsCallingPolicy](/en-us/powershell/module/teams/remove-csteamscallingpolicy)
- [Grant-CsTeamsCallingPolicy](/en-us/powershell/module/teams/grant-csteamscallingpolicy)

For example, this script enables call recording for the global policy:

```powershell
Set-CsTeamsCallingPolicy -Identity Global -AllowCloudRecordingForCalls $true
```

For information on Teams compliance recording, see [Introduction to Teams recording](teams-recording-policy) and [Third-party compliance recording for Microsoft Teams calls and meetings](teams-recording-compliance).

To allow or prevent meeting recordings, see [Teams meeting recording](meeting-recording).

## Enable call transcription

Transcription is automatically generated, recorded text of what was said in a call. When turned on, the transcript is available to users to review after a call ends. This setting is off by default.

### Using the Teams admin center

To turn on call transcription for users:

1. In the Microsoft Teams admin center, select **Voice** &gt; **Calling policies**.
2. Select the policy you want to modify.
3. Turn **Transcription** to **On**.
4. Select **Save**.

### Using PowerShell

With PowerShell, you can configure the `-AllowTranscriptionForCalling` parameter and manage the resulting policy with these cmdlets:

- [Get-CsTeamsCallingPolicy](/en-us/powershell/module/teams/get-csteamscallingpolicy)
- [New-CsTeamsCallingPolicy](/en-us/powershell/module/teams/new-csteamscallingpolicy)
- [Set-CsTeamsCallingPolicy](/en-us/powershell/module/teams/set-csteamscallingpolicy)
- [Remove-CsTeamsCallingPolicy](/en-us/powershell/module/teams/remove-csteamscallingpolicy)
- [Grant-CsTeamsCallingPolicy](/en-us/powershell/module/teams/grant-csteamscallingpolicy)

For example, this script enables transcription for the global policy:

```powershell
Set-CsTeamsCallingPolicy -Identity Global -AllowTranscriptionForCalling $true
```

## Enable call captions

Captions are real-time automatically generated text of what is said in a call. They appear a few lines at a time for a user who turns them on. Captions aren’t saved. This setting is on by default.

### Using the Teams admin center

To enable real-time captions for calls:

1. In the Microsoft Teams admin center, select **Voice** &gt; **Calling policies**.
2. Select the policy you want to modify.
3. Turn **Real-time captions in Teams calls** to **On**.
4. Select **Save**.

### Using PowerShell

Use PowerShell to configure the `-LiveCaptionsEnabledTypeForCalling` parameter and manage the resulting policy with the following cmdlets:

- [Get-CsTeamsCallingPolicy](/en-us/powershell/module/teams/get-csteamscallingpolicy)
- [New-CsTeamsCallingPolicy](/en-us/powershell/module/teams/new-csteamscallingpolicy)
- [Set-CsTeamsCallingPolicy](/en-us/powershell/module/teams/set-csteamscallingpolicy)
- [Remove-CsTeamsCallingPolicy](/en-us/powershell/module/teams/remove-csteamscallingpolicy)
- [Grant-CsTeamsCallingPolicy](/en-us/powershell/module/teams/grant-csteamscallingpolicy)

For example, this script lets users turn on real-time captions in the global policy:

```powershell
Set-CsTeamsCallingPolicy -Identity Global -LiveCaptionsEnabledTypeForCalling DisabledUserOverride
```

In this example, the script prevents users from turning on real-time captions in the global policy:

```powershell
Set-CsTeamsCallingPolicy -Identity Global -LiveCaptionsEnabledTypeForCalling Disabled
```

## Require participant agreement for recording and transcription

When the call recording agreement policy is turned on, once a user starts recording, transcription, or both, the other call participant is muted, with their camera and content-share turned off. The user who initiates recording or transcription is considered to have given consent and remains unmuted. When a participant decides to un-mute, turn on their camera, or share content, they’re asked to respond **'Yes'** or **'No'** to consent to be included in the recording and transcription. If a participant responds **'No'** to the question, they have a view-only experience for the call and cannot unmute or turn on their camera. View-only participants can't start recording or transcription for any meetings that require explicit consent.

The consent choice for each participant is visible by the admin and is included in the Purview audit log for the call.

Note

Explicit consent is not supported for call queue calls.

### Manage recording consent

Use the Teams admin center or the **`-ExplicitRecordingConsent`** parameter in the [New-CsTeamsCallingPolicy](/en-us/powershell/module/teams/new-csteamscallingpolicy) cmdlet to manage recording consent for Teams calls. This parameter manages recording consent for Teams 1:1 VoIP and PSTN calls. Audio conferencing and group calls are managed by Teams Meeting Policy. To learn about recording consent for Audio Conferencing, see [Explicit recording consent for Audio Conferencing](/en-us/microsoftteams/conferencing-recording-consent). To learn about recording consent for Teams meetings, see [Manage Teams recording policies for meetings and events](/en-us/microsoftteams/meeting-recording).

### View consent data

You can view consent data using the **Added information about call participants** filter in the Teams calling audit logs in Purview. To learn more about audit logs in Purview, see [Audit log activities](/en-us/purview/audit-log-activities).

### Supported and unsupported endpoints and platforms

For information on supported endpoints, platforms, and auto consent endpoints, see [Supported and unsupported endpoints and platforms.](/en-us/microsoftteams/meeting-recording)