---
layout: Conceptual
title: Overview- Recording and transcription for Teams meetings, events, and calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/recording-transcription-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: lisma, harinlee, wanqincao, yujin1
ms.date: 2025-03-19T00:00:00.0000000Z
ms.topic: article
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.service: msteams
ms.subservice: meetings
ms.custom: intro-overview
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- m365initiative-voice
- enabler-strategic
- highpri
ms.localizationpriority: medium
search.appverid: MET150
description: Understand recording and transcription policies available for meetings, events, and calls in Microsoft Teams.
locale: en-us
document_id: 62a61816-d706-1d2d-7865-78b919d03c6a
document_version_independent_id: 62a61816-d706-1d2d-7865-78b919d03c6a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/recording-transcription-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: recording-transcription-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/recording-transcription-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 58b8b64d-d72e-7361-b488-9ead6d42b77c
---

# Overview- Recording and transcription for Teams meetings, events, and calls - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Group and 1:1 calls

In Microsoft Teams, your users can record and transcribe their meetings, events, and calls. Transcription automatically turns spoken dialogue into written text, making it easy to review or share key discussions later. Recording captures audio, video, and screen-sharing activities, allowing users to revisit or share the full meeting experience as needed. The user's ability to manage the recording of their meetings, events, and calls is referred to as convenience recording. To understand the different types of recordings in Teams, see [Introduction to recording Microsoft Teams calls and meetings](teams-recording-policy).

As an admin, you can manage convenience recording and transcription for meetings and calls in your organization through policy settings. This article explains which policy types control recording and transcription, where each policy applies, and where to configure settings.

- **Convenience recording**: User-initiated recording of Teams meetings, events, and calls.
- **Transcription**: Automatic conversion of spoken audio into text.
- **Explicit recording consent**: A policy setting that requires participants to consent before they can be included in recording/transcription.
- **Intelligent recap**: AI-generated meeting or call recap features that depend on transcript availability and licensing.

## Meeting, events, and calling policies

- **Meeting policies:** These policies control user permissions for recording and transcription in Teams meetings and group calls.
- **Events policies:** These policies control user permissions for recording and transcription in Teams events. Events have their own separate recording and transcription policies.
- **Voice calling policies:** These policies control user permissions for 1:1 calls, including both internal and external native Teams calls and Public Switched Telephone Network (PSTN) calls.

If your users use Teams meetings, events, and calls, it’s important to align policy settings across these scenarios.

For example, let’s say your organization’s finance team shouldn’t record or transcribe calls, meetings, or events. You turn off recording and transcription in the calling policy and assign it to users in the finance team. However, because you didn’t update or assign a specific meeting or events policy to those users, they default to the global policies. In the global policy for both meetings and events, recording and transcription are on by default.

The finance team can record and transcribe meetings, group calls, and events, but not 1:1 calls, because you didn't assign a custom meeting or event policy. For a consistent recording and transcription experience across all call, events, and meeting types, configure and assign the appropriate policies.

To learn more about assigning policies to both users and groups in your organization, see [Assign policies to users and groups](assign-policies-users-and-groups).

The following sections outline the policy settings and features you can use to manage recording and transcription in your organization.

Note

When you make changes to the Global policy, they apply to everyone in your organization, except for users with an assigned custom meeting or calling policy.

## Manage recording and transcription for meetings, events, and group calls

| Feature/setting | Admin controls | Documentation |
| --- | --- | --- |
| Recording for meetings | Allow or prevent meeting and group call recording for users, groups, or your entire organization. | [Manage Teams recording policies for meetings and events](meeting-recording#meetings) |
| Record an event | Allow or prevent event recording for users, groups, or your entire organization. | [Manage Teams recording policies for meetings and events](meeting-recording) |
| Transcription for meetings | Allow or prevent meeting and group call transcription for users, groups, or your entire organization. | [Admins- Manage transcription and captions for Teams meetings](meeting-transcription-captions#meetings) |
| Transcription for events | Allow or prevent transcription for events for users, groups, or your entire organization. | [Admins- Manage transcription and captions for Teams meetings](meeting-transcription-captions) |
| Auto recording | Control whether organizers have the **Record and transcribe automatically** setting in their **Meeting options** for meetings and events. If you allow auto recording, your users’ **Record and transcribe automatically** setting is **Off** by default for meetings and **On** for events. When organizers want their meetings to be recorded and transcribed automatically, they must switch the toggle to **On** for each meeting. With a Teams Premium license, you can use [Meeting templates or Sensitivity labels](manage-teams-auto-recording) to enforce a value for this setting. | [Manage Teams recording policies for meetings and events](manage-teams-auto-recording) |
| Real-Time-Text (RTT) | Manage whether your users can use RTT in Teams meetings and group calls. | [Manage Real-Time Text (RTT) in Teams for users in your organization](teams-real-time-text) |
| Explicit recording consent | Control whether meeting participants must provide consent to be recorded. | [Manage Teams recording policies for meetings and events](participant-agreement-recording-transcription) |
| Recording and transcript expiration | Manage when recordings and transcripts expire for your organization. | [Manage Teams recording policies for meetings and events](manage-teams-recording-expiration-policy) |
| Privacy and security URL | Replace the default Teams meeting recording and transcription privacy statement with URL to your organization’s legal website. | [Manage Teams recording policies for meetings and events](meeting-recording#set-a-custom-privacy-policy-url) |
| Microsoft Copilot in Teams meetings and events | Manage how transcripts are used in Microsoft Copilot in Teams meetings and events. | [Manage Microsoft Copilot in Teams meetings and events](copilot-teams-transcription) |
| Shared mailbox meeting recordings | Understand storage and permissions for meetings scheduled through a shared mailbox. | [Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change#shared-mailbox-scheduled-meetings) |
| Block or allow download of channel recording and transcript files | Control whether your users can download channel meeting recordings and transcripts. | [Manage Teams recording policies for meetings and events](meeting-recording#block-or-allow-download-of-channel-meeting-recordings) |
| Block download of meeting recording and transcript files from SharePoint or OneDrive | Prevent users from downloading meeting recording and transcript files saved in SharePoint and OneDrive. | [Block the download of Teams meeting recording files from SharePoint or OneDrive](block-download-meeting-recording) |
| Verify transcription requirements | Verify if a user’s account meets the requirements to transcribe a Teams meeting. | [Admins- Manage transcription and captions for Teams meetings](meeting-transcription-captions#check-users-transcription-permissions) |
| Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcript | Control whether organizers can restrict participants from copying or forwarding meeting chat messages, live captions, transcripts, and AI-generated insights in the meeting recaps. | [Manage chat for sensitive Teams meetings](manage-chat-sensitive-meetings) |
| Custom dictionaries for Teams **(Microsoft Copilot)** | You can upload a custom dictionary in the Microsoft 365 admin center to improve the quality of transcription for Teams meetings and events. | [Manage custom dictionaries for Microsoft Teams meetings and events](copilot-custom-dictionary) |
| Intelligent recap for meetings **(Teams Premium and Microsoft Copilot)** | Licensing and the transcription policy control this feature. Users with a Teams Premium or Microsoft Copilot license automatically have access to this feature. | [Intelligent recap for Teams calls and meetings](intelligent-recap-calls-meetings) |
| eDiscovery Search for recordings and transcripts | View meeting recordings video and transcription text. | [Manage Teams recording policies for meetings and events](meeting-recording#ediscovery-search-for-recordings-and-transcripts) |
| Recording and transcript storage | Manage where meeting recordings and transcripts are stored. | [Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change) |
| Who can record and transcribe **(Teams Premium)** | Use sensitivity labels or a meeting template to control who can record and transcribe meetings created by organizers with a Teams Premium license. | [Manage Microsoft Teams meeting recording and transcription options for sensitive meetings](manage-meeting-recording-options) |

## Manage recording and transcription for 1:1 calls

| Feature/setting | Admin controls | Documentation |
| --- | --- | --- |
| Recording | Allow or prevent 1:1 and PSTN call recording for users, groups, or your entire organization. | [Configure call recording, transcription, and captions in Teams](call-recording-transcription-captions#enable-call-recording) |
| Transcription | Allow or prevent 1:1 and PSTN call transcription for users, groups, or your entire organization. | [Configure call recording, transcription, and captions in Teams](call-recording-transcription-captions#enable-call-transcription) |
| Intelligent recap for calls | Licensing and the transcription policy control this feature. Users with a Teams Premium or Microsoft Copilot license automatically have access to this feature. | [Intelligent recap for Teams calls and meetings](intelligent-recap-calls-meetings) |
| Real-Time-Text (RTT) | Manage whether your users can use RTT in Teams 1:1 VoIP calls. | [Manage Real-Time Text (RTT) in Teams for users in your organization](teams-real-time-text) |

## Teams Premium

If you have a Teams Premium license, you can use meeting sensitivity labels and templates to manage and enforce different recording and transcription settings for your organization. To learn more, see [Manage Microsoft Teams meeting recording and transcription options for sensitive meetings](manage-meeting-recording-options).

## Troubleshooting and diagnostics

If you or your users are having any issues or errors with recordings and transcripts, check out the following troubleshooting and end user articles:

| If users reports | Reference |
| --- | --- |
| I can’t record a meeting | [I can't record a meeting in Microsoft Teams](https://support.microsoft.com/office/i-can-t-record-a-meeting-in-microsoft-teams-f35329c2-57b1-487f-b5e3-70a7efb0945b) |
| Meeting recording failures or missing recordings | [Issues that affect meeting recordings](/en-us/microsoftteams/troubleshoot/meetings/troubleshoot-meeting-recording-issues) |
| I can’t transcribe a meeting | [I can't transcribe a meeting in Microsoft Teams](https://support.microsoft.com/office/i-can-t-transcribe-a-meeting-in-microsoft-teams-61f4c8e4-f2d1-4aeb-9b20-244c20fc3faa) |