---
layout: Conceptual
title: Explicit recording and transcription consent for Audio Conferencing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/conferencing-recording-consent
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: simonibssa
ms.date: 2026-10-06T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- m365initiative-meetings
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing
description: Learn how to manage Explicit recording and transcription consent for Audio Conferencing in Microsoft Teams. Learn how to require participants to require consent to being recorded and transcribed when dialing into Microsoft Teams meetings.
locale: en-us
document_id: f8bd365c-9281-b561-ed53-37580e042e63
document_version_independent_id: f8bd365c-9281-b561-ed53-37580e042e63
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/conferencing-recording-consent.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: conferencing-recording-consent
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/conferencing-recording-consent.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: 5681488f-1a0f-732f-d161-92d0cc54126b
---

# Explicit recording and transcription consent for Audio Conferencing - Microsoft Teams | Microsoft Learn

Explicit recording and transcription consent for Microsoft Teams Audio Conferencing lets you, as an admin, control whether meetings created by organizers with this policy can require participants to explicitly consent to being recorded and transcribed.

When the explicit recording and transcription policy is enabled, all participants are muted once the meeting recording or transcription starts. Once a participant decides to un-mute, they’re prompted to provide consent. To consent to be recorded and transcribed, participants can select controls on their dial pad.

## Recording types

Explicit recording consent includes two recording types:

**Compliance recording:** Compliance recording is a policy-based feature that requires users with an assigned admin recording policy to have all their calls and meetings recorded. To learn more about compliance recording, see [Introduction to Teams policy-based recording for calling and meetings](teams-recording-policy).

**Convenience recording:** Users initiate convenience recording, which is the regular meeting recording. To learn more about convenience recording, see [Record a meeting in Microsoft Teams](https://support.microsoft.com/office/record-a-meeting-in-microsoft-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24).

## Configure explicit recording and transcription consent for Audio Conferencing

You must use PowerShell to configure explicit recording and transcription consent for users or groups in your organization. PowerShell must be installed on your machine to manage this policy. For instructions on installing PowerShell on Windows, Mac, or Linux for the first time, see [Install PowerShell on Windows, Linux, and macOS - PowerShell](/en-us/powershell/scripting/install/installing-powershell).

For scripts to enable explicit recording and transcription consent for Audio Conferencing, see [Manage explicit recording and transcription consent through PowerShell](meeting-recording#manage-whether-meetings-require-participant-agreement-for-recording-and-transcription).

## Recording consent dial pad controls

To select their recording and transcription preferences, your users can use the following selections on their dial pad:

**1** - Give consent to being recorded and transcribed in a call and un-mute their microphone.

**2** – Deny recording and transcription, and remain muted.

\***5** – Raise Hand in Meeting

\***6** – Unmute themselves

### Example scenarios

This list provides examples of how your users can apply the recording and transcription consent dial pad controls, depending on their scenario:

**Scenario 1:** Recording or transcription starts before the user joins the meeting (as a participant or meeting organizer)

- The user can press **1** to consent to being recorded or transcribed and join the meeting unmuted, or press **2** to decline consent and join the meeting muted.

**Scenario 2:** Recording or transcription starts after the user joins the meeting (as a participant or meeting organizer)

- The user becomes muted and can press **1** to consent to being recorded or transcribed and become unmuted, or press **2** to decline consent and remain in the meeting while muted.

**Scenario 3:** Recording or transcription starts before or after joining the meeting (as a participant or meeting organizer)

- If the user previously declined consent but later wants to unmute and speak, they can press \***6** to unmute. They are prompted to provide consent before they can speak.

Note

If you use a policy to mute all participants upon joining a meeting, participants must press \*5 to raise hand before providing consent again.