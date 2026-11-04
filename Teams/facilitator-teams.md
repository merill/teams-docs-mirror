---
layout: Conceptual
title: Set up Facilitator in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/facilitator-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: solomon.alex, grace.culver
ms.date: 2026-08-13T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: install-set-up-deploy
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
- magic-ai-copilot
- teams-copilot
ms.custom:
- admindeeplinkTEAMS
- admindeeplinkMAC
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Learn about how Facilitator in Microsoft Teams enables group collaboration powered by Copilot.
locale: en-us
document_id: 345955eb-0e31-0cc3-a4bf-2f23668f3dea
document_version_independent_id: 345955eb-0e31-0cc3-a4bf-2f23668f3dea
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/facilitator-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: facilitator-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/facilitator-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: e9b6de00-ab36-9d32-5aef-6e4b84c30f2d
---

# Set up Facilitator in Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

There are Facilitator capabilities generally available and certain capabilities in public preview.

> 
> The following Facilitator capabilities are currently generally available:
> 
> - Collaborative, real-time notes editable by all participants via the *Notes* tab
> - AI-powered Q&A from meeting and web content
> - Visual timeline markers to track topics and time, with reminders at midway and wrap-up
> - Word document creation in meeting or post meeting, for example "@Facilitator, create a BRD based on this meeting for the executive review"
> - Enhanced Teams Rooms experience with chat, notes, and timers
> - Mobile capture of ad-hoc discussions and action items
> - Licensed users can interact with the agent by mentioning it in the chat, for example "@Facilitator add these topics to the agenda…"
> 
> 
> The following Facilitator capabilities are currently in public preview:
> 
> - Task tracking integration with Planner
> 

Note

We are migrating to a new back-end system that provides greater flexibility and enables higher-quality document creation experiences going forward. As part of this migration, two changes will take effect: Word document generation will be enhanced, Loop file generation will no longer be supported by Jul 31, 2026. There is no impact on Facilitator live note.

> 
> Features in preview might not be complete and could undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. For more information about Teams features in public preview, see [Microsoft Teams Public preview](public-preview-doc-updates).

Facilitator is an AI-powered agent that helps keep meetings focused, organized, and action-oriented by surfacing agendas, tracking progress, and capturing key highlights in real time. It supports collaboration through a conversational interface and integrates with tools like Planner, Word, Loop, and Teams Rooms. Use Facilitator in:

- Meetings
- [Teams Rooms](rooms/facilitator-teams-rooms)

## How Facilitator behaves in Teams

Facilitator behaves differently than Copilot in Teams.

A user's prompts to Copilot in Teams and Copilot's responses are private to that individual user. Copilot in Teams also has its own set of features and use cases.

However, Facilitator acts like an assistant sitting in your users' meetings. If a user prompts Facilitator, all users can view that communication, just like if the user was talking with another person in the meeting chat. Facilitator then displays its response within the meeting's conversation for everyone to see.

## Security, Compliance, and Privacy

Facilitator, Copilot, and Microsoft 365 are built on Microsoft's comprehensive approach to security, compliance, and privacy.

To learn how Microsoft Purview supports your security and compliance management for Facilitator and some recommended getting started steps, see [Use Microsoft Purview to manage data security & compliance for Microsoft Facilitator](/en-us/purview/ai-teams-facilitator).

For more information about the security and privacy standards used to develop Microsoft Copilot and AI agents like Facilitator, see the following articles:

- [Data, Privacy, and Security for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-privacy) for Microsoft Copilot in your organization (work or school).
- [Microsoft Purview data security and compliance protections for generative AI apps](/en-us/purview/ai-microsoft-purview).
- [Copilot Pro: Microsoft 365 apps and your privacy](https://support.microsoft.com/office/copilot-pro-microsoft-365-apps-and-your-privacy-6f0d8d80-f4bb-4c9f-989e-64a4adfd62e5) for Microsoft Copilot apps at home.

## Facilitator licensing and permission requirements

Facilitator is included with a Microsoft Copilot license and subject to available capacity. The following list contains the prerequisites for users to be able to access Facilitator features in Teams meetings. Users must meet all of the following requirements:

### Licensing requirements

- An eligible *Microsoft 365*base license.
    - For the list of eligible base licenses, see [Understand licensing requirements for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing).
- Have an eligible *Microsoft Teams*license.
    - Teams licenses might be included in your *Microsoft 365* subscription. If you have *Microsoft 365 (no Teams)* licenses, you need to purchase separate Teams licenses.
- Have a *Microsoft Copilot*license.
    - For information on how to acquire *Microsoft Copilot* licenses, see [Where can I get Microsoft Copilot?](https://support.microsoft.com/topic/where-can-i-get-microsoft-copilot-40a622db-6d25-4266-b008-4bbcb55cf52f).

### User requirements

- To use preview experiences, be a Microsoft Teams Public preview participant.
- For information on how to access Teams Public preview features, see [Microsoft Teams Public preview](/en-us/microsoftteams/public-preview-doc-updates).
- Have Loop experiences in Teams for Facilitator in meetings turned on.

## Facilitator data storage

Facilitator data in meetings is stored as a `.loop` file in a OneDrive folder titled **Meetings** of the user who initiated Facilitator in Teams. This data is treated as meeting transcript data. To learn more about how this data is handled, see [Summary of governance, lifecycle, and compliance capabilities for Loop experiences](/en-us/microsoft-365/loop/loop-compliance-summary).

## Allow Facilitator for meetings

As an admin, you control whether Facilitator is available to your entire organization or to a certain group of users.

Facilitator is allowed by default. However, if all apps are blocked for your organization, Facilitator is also blocked.

To allow or block Facilitator for users, complete the following steps:

### 1. Allow Facilitator in the Teams admin center

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com/dashboard) with your Teams admin credentials.
2. In the left rail navigation, select **Teams apps** &gt; **Manage apps**.
3. In the apps list's search box, search for **Facilitator**.
4. Select **Facilitator** from the app list.
5. In the actions menu, select **Allow** or **Block**.
6. In the pop-up, select the **Allow** or **Block** button.

You can also use [app centric management](/en-us/microsoftteams/app-centric-management) to allow and block, create policies, and assign users.

For more information about managing apps in Teams, see [Manage apps](manage-apps).

### 2. Allow Facilitator for a group of users

To allow Facilitator for users, a new app policy needs to be created and then assigned to users.

Follow the instructions at [Use app permission policies to control user access to apps](teams-app-permission-policies) to create a new app policy for Facilitator.

You can then assign the policy to your entire tenant or to a select group of users. Follow the instructions at [Add or modify app availability for users](/en-us/microsoftteams/app-centric-management#add-or-modify-app-availability-for-users) to assign the policy to users using app-centric management.

### 3. Turn on Loop experiences in Teams for Facilitator in meetings

*Loop experiences in Teams* need to be turned on in order for Facilitator to be used in meetings.

To turn on Loop experiences in Teams, follow the instructions at [Settings management for Loop functionality in Teams](/en-us/microsoft-365/loop/loop-components-configuration#settings-management-for-loop-functionality-in-teams).

## Manage users' access to Facilitator skills

If there are certain Facilitator skills you would like to manage for your users, review the following details.

### Turn off AI-generated notes for meetings

*Loop experiences in Teams* control AI-generated notes for meetings, which are enabled by default.

You can manage this control using the `IsCollabMeetingNotesFluidEnabled` setting in PowerShell. This setting applies to your entire tenant and can't be configured at the user level. This means that if you disable this setting, AI-generated notes for meetings is turned off for all users in your organization.

For instructions on managing this setting, see [Settings management for Loop functionality in Teams](/en-us/microsoft-365/loop/loop-components-configuration#settings-management-for-loop-functionality-in-teams).

## Facilitator limitations

Facilitator currently has the following limitations:

- Only licensed userscan initiate Facilitator.
    - Unlicensed users can't prompt Facilitator, but they can see others' prompts to Facilitator and Facilitator's responses.
    - Unlicensed users can see Facilitator's notes in meetings.
- Currently, Facilitator isn't supported in 1:1 chats, group chats, or [external chats and meetings](trusted-organizations-external-meetings-chat).
- Retention labels aren't supported for cloud attachments in AI-generated notes.
- Facilitator only supports the languages listed at [Supported languages for Microsoft Copilot](https://support.microsoft.com/office/supported-languages-for-microsoft-copilot-94518d61-644b-4118-9492-617eea4801d8).

### Facilitator for meetings limitations

- Facilitator's AI-generated notes for meetings aren't automatically collected as cloud attachments in [Microsoft Purview eDiscovery](/en-us/purview/ediscovery-cloud-attachments) because it isn't currently supported.
- When a user turns on Facilitator during a meeting, they're prompted to select the language participants are speaking during the meeting. The language selected must match the spoken language during the meeting, or notes aren't generated.
- Currently, AI-generated notes for meetings only support meetings where a single language is spoken. If multiple languages are spoken during the meeting, notes are only taken for the portions of the meeting that are spoken in the selected meeting language.
- Meeting settings like [Prevent copy and paste](manage-chat-sensitive-meetings#prevent-copying-or-forwarding-chat-captions-and-transcripts) and [Watermarks](watermark-meeting-content-video) aren't applied to Facilitator's responses or AI-generated notes in meetings.
- AI-generated notes for meetings don't inherit the meeting's sensitivity label; however, a sensitivity label can be applied to the notes' Loop component in the [Loop app or OneDrive](/en-us/purview/sensitivity-labels-loop). If a sensitivity label is applied to the notes outside of Teams, the note's file can't be accessed in Teams.