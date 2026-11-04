---
layout: Conceptual
title: Overview of AI in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/copilot-ai-agents-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: sophiapeng
ms.date: 2025-04-02T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: overview
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
- magic-ai-copilot
- teams-copilot
ms.custom: 
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Discover which AI features are available in Microsoft Teams for your organization and how to set them up.
locale: en-us
document_id: f5f739fd-c98f-1ffa-5444-63588f32d556
document_version_independent_id: f5f739fd-c98f-1ffa-5444-63588f32d556
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/copilot-ai-agents-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-ai-agents-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/copilot-ai-agents-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: 8cc92a6f-889e-f8a8-95f4-d7ebaf4ae5fb
---

# Overview of AI in Microsoft Teams - Microsoft Teams | Microsoft Learn

Microsoft has introduced an ever-growing catalog of AI tools and features for Microsoft Teams, starting with features like voice isolation and suggested replies. Today, this catalog includes a powerful, personal AI assistant called Copilot in Teams and task-tailored agents like Facilitator and Channel Agent.

This article is for IT admins and discusses the AI tools and features available in Teams along with links to their related documentation.

In this article, learn about:

- Standard AI features in Microsoft Teams
- Microsoft Copilot features in Teams
- Microsoft Copilot app in Teams
- Microsoft Copilot in Teams
- Microsoft 365 agents in Teams
- AI features included with Teams Premium

## Standard AI features in Microsoft Teams

*Required licenses:*

- *Microsoft Business (Basic, Standard, and Premium) or Microsoft 365 (E3/E5/F1/F3/A3/A5/G3/G5)*
- *Teams Enterprise or Teams Enterprise (EEA)*

Microsoft Teams includes some AI features that don’t require any extra licenses, just a Microsoft 365 subscription and a Teams license. These features enhance your users’ Teams experience in their workflow, chats, and meetings, including:

- **Microsoft Copilot Chat app**: The Copilot Chat app in Teams allows users to ask Copilot open-ended questions, request help creating new content, and use [Copilot Pages](https://support.microsoft.com/topic/6674bd51-9ff5-42c4-9256-44d9428a726f). Without a Microsoft Copilot license, Copilot’s responses are only grounded in public web data.
- **Suggested replies**: Teams can suggest replies to users based on the previous conversation in 1:1 and group chats.
- **Video optimization**: Teams can optimize users’ video feeds through AI-assisted adjustments, like auto-brightness and facial recognition.
- **Voice isolation for calls and meetings**: Teams can use AI to separate a user's voice from other sounds and voices in Teams calls and meetings, displaying the user’s name when they speak and identifying them as the speaker in a transcript. Voice isolation is also used to reduce background noise.
- **Intelligent media quality classifiers in Call Quality Dashboard (CQD)**: Teams can monitor call quality using Machine Learning (ML) algorithms with intelligent media quality classifiers in CQD, which provide advanced analysis into causality, media degradation, and root cause to address and prevent call quality issues.

| Feature | Admin articles | End-user articles |
| --- | --- | --- |
| Microsoft Copilot Chat app | [Overview of Microsoft Copilot Chat](/en-us/copilot/overview) | [Microsoft Copilot Chat](https://support.microsoft.com/copilot-microsoft365-chat) |
| Suggested replies | None | [Use suggested replies to respond to messages](https://support.microsoft.com/office/010c54e1-a613-4771-94ed-76d7fb77cba5) |
| Facial recognition | [Create Recognition profiles for Microsoft IntelliFrame](rooms/voice-recognition) | [Create Recognition profiles for Microsoft IntelliFrame](https://support.microsoft.com/office/f0084478-52a7-4c52-bcdc-9063ed0e0bc0) |
| Voice isolation for calls and meetings | [Manage voice isolation for your users' Microsoft Teams calls and meetings](voice-isolation) | [Voice isolation in Microsoft Teams calls and meetings](https://support.microsoft.com/office/a9756ea9-4cec-44c4-aefb-6f5d17c89427)[Reduce background noise in Microsoft Teams meetings](https://support.microsoft.com/office/reduce-background-noise-in-microsoft-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d) |
| Intelligent media quality classifiers in CQD | [Intelligent media quality classifiers in Call Quality Dashboard (CQD)](cqd-intelligent-media-quality-classifiers) | None |

## Microsoft Copilot features in Teams

*Required licenses:*

- *Microsoft Business (Basic, Standard, and Premium) or Microsoft 365 (E3/E5/F1/F3/A3/A5/G3/G5)*
- *Teams Enterprise or Teams Enterprise (EEA)*
- *Microsoft Copilot*

Important

All prompts, files, and responses using Microsoft Copilot, including the Microsoft Copilot Chat app and the Microsoft Copilot app, never leave your organization’s Microsoft 365 service boundary. This includes prompts and responses that access public web data. Your data is always secured and private within your service boundary.

Microsoft Copilot and Microsoft Copilot Chat are ISO/IEC 42001:2023 certified to further ensure that we develop, deploy, and use AI systems responsibly. For more information, see [Microsoft Copilot Achieves ISO/IEC 42001:2023 Certification](https://techcommunity.microsoft.com/blog/microsoft365copilotblog/microsoft-365-copilot-achieves-isoiec-420012023-certification/4397144).

The Microsoft Copilot license is the foundation for many AI tool sets in Teams, like Copilot in Teams, Facilitator, and Channel Agent. If you want your users to access a robust set of AI features, purchase and assign Microsoft Copilot licenses to them.

Review the following resources for more information about Microsoft Copilot:

- [What is Microsoft Copilot?](/en-us/microsoft-365/copilot/microsoft-365-copilot-overview)
- [Which Copilot is right for me or my organization?](/en-us/microsoft-365/copilot/which-copilot-for-your-organization)
- [Set up Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-setup)
- [Copilot Prompt Gallery](https://copilot.cloud.microsoft/prompts?)

### Microsoft Copilot app in Teams

The Microsoft Copilot license upgrades your users’ Microsoft Copilot Chat app experience. The Microsoft Copilot app is like the Microsoft Copilot Chat app, where users can ask open-ended questions, get help creating new content, and explore ideas. However, The Microsoft Copilot app is also grounded in users’ work data. Users can then toggle between whether they want their prompts grounded in work data or public web data.

### Microsoft Copilot in Teams

Microsoft Copilot in Teams is your users’ personal Copilot, helping them in their workflows with skills like file and chat summarization, open-ended question and answer, task generation, and intelligent feedback and suggestions.

- **Copilot in Teams chats and channels**: Copilot in your users’ chats and channels helps them catch up on conversations quickly and help contribute intelligently.
- **Copilot in Teams meetings and events**: Copilot in meetings and events uses recording, transcription, and meeting chat data to ensure participants get the most out of meetings.
- **Copilot in Teams Phone**: Copilot in Teams Phone empowers your users to have more productive calls or catch up on ones they missed.
- **Copilot in Teams Rooms**: Copilot enhances Teams Rooms experiences with features like responding to open-ended questions, recapping what was discussed in the room, and providing meeting insights.
- **Copilot in Teams for multitenant organizations** - B2B members who are licensed with Microsoft Copilot can access Copilot in Teams across their multitenant organization.
- **Custom dictionaries for Teams meetings and events**: You can upload a custom dictionary in the Microsoft 365 admin center to improve the quality of transcription for Teams meetings and events.

| Feature | Admin articles | End-user articles |
| --- | --- | --- |
| Copilot in Teams chats and channels | None | [Use Copilot in Microsoft Teams chat and channels](https://support.microsoft.com/office/cccccca2-9dc8-49a9-ab76-b1a8ee21486c) |
| Copilot in Teams meetings and events | [Manage Microsoft Copilot in Teams meetings and events](copilot-teams-transcription) | [Use Copilot in Microsoft Teams meetings](https://support.microsoft.com/office/0bf9dd3c-96f7-44e2-8bb8-790bedf066b1) |
| Copilot in Teams Phone | [Manage Microsoft Copilot in Teams calls](copilot-teams-calling-transcription) | [Get started with Copilot in Microsoft Teams Phone](https://support.microsoft.com/office/97c55ffb-1499-4b0a-8caa-980ebb4b697b) |
| Copilot in Teams Rooms | [Teams Rooms and Copilot overview](rooms/copilot-admin-mtr) | None |
| Copilot in Teams for multitenant organizations | [Manage Copilot access for B2B members within multitenant organizations (MTO) in Teams](copilot-mto) | None |
| Custom dictionaries for Teams meetings and events | [Manage custom dictionaries for Microsoft Teams meetings and events](copilot-custom-dictionary) | None |

### Microsoft 365 agents in Teams

Microsoft 365 agents are designed to help your users with unique work tasks, grounded in scoped knowledge, like extending a project plan or capturing unanswered questions during a meeting. With a Microsoft Copilot license, users can access the following agents in Teams:

- **Facilitator**: Facilitator is a Teams collaboration agent in meetings where all users can interact with Facilitator like it’s another team member.
- **Facilitator for Teams Rooms**: Facilitator can also aid collaboration during in-person, unscheduled meetings via Teams Rooms.
- **Channel Agent**: Channel Agent is a collaboration agent in channels that helps users manage and keep track of channel conversations. The agent can help with common tasks like flagging important deadlines that are buried in conversations, summarizing progress with succinct status reports, assigning tasks and due dates, and answering questions asked in natural language.

| Feature | Admin articles | End-user articles |
| --- | --- | --- |
| Facilitator | [Set up Facilitator in Microsoft Teams](facilitator-teams)[Use Microsoft Purview to manage data security & compliance for Microsoft Facilitator](/en-us/purview/ai-teams-facilitator) | [Keep track of chats with AI-generated notes in Microsoft Teams](https://support.microsoft.com/office/0b7efbd0-fd3e-48e7-9a4b-4ea22cdc12c0)[Automate notetaking in Microsoft Teams meetings](https://support.microsoft.com/office/37657f91-39b5-40eb-9421-45141e3ce9f6) |
| Facilitator for Teams Rooms | [Facilitator in Microsoft Teams Rooms](rooms/facilitator-teams-rooms) | None |
| Channel Agent | [Set up Channel Agent in Microsoft Teams](set-up-channel-agent-teams)[Use Microsoft Purview to manage data security & compliance for Channel Agent in Teams](/en-us/purview/ai-teams-channel-agent) | [Get started with Channel Agent in Microsoft Teams](https://support.microsoft.com/office/b85945cf-deef-4f1e-9db1-66e1a23b6a65)[How Channel Agent works](https://support.microsoft.com/office/fda632c9-9d3c-4e05-8e54-7f400d29ec75)[How to create a Channel Agent for a Teams channel](https://support.microsoft.com/office/b35afb49-1789-4809-9658-bddc0a5695cb)[How to add Channel Agent to other Teams conversations](https://support.microsoft.com/office/01cb288b-4822-47a6-a6a7-48ac61232b99)[How to remove Channel Agent](https://support.microsoft.com/office/68e4f464-7205-411b-97bb-087f6992c3ac)[How to approve and reject summaries from Channel Agent](https://support.microsoft.com/office/651983ae-356b-4734-8ed9-d38b68870623)[How to manage Channel Agent's settings](https://support.microsoft.com/office/868a2a50-8797-40b7-b3a8-84524e463ffd)[How to generate a status report using Channel Agent](https://support.microsoft.com/office/e3a57145-d5c0-49d2-894f-ab2f298e5362)[How to schedule channel meetings using Channel Agent](https://support.microsoft.com/office/2a408119-8b8d-4f82-8166-3f816d86417b)[How to get answers to questions using Channel Agent](https://support.microsoft.com/office/1d47a619-2837-4cce-8eca-bfeca1ca6d1c)[How to create project tasks using Channel Agent](https://support.microsoft.com/office/1bfb6721-dc8d-4be5-966a-89e7d1a3ae81)[How to create and send emails using Channel Agent](https://support.microsoft.com/office/fc597ed9-4de7-4f36-a532-0887b8577494) |

## AI features included with Teams Premium

*Required licenses:*

- *Microsoft Business (Basic, Standard, and Premium) or Microsoft 365 (E3/E5/F1/F3/A3/A5/G3/G5)*
- *Teams Enterprise or Teams Enterprise (EEA)*
- *Teams Premium*

Some AI features in Teams can be acquired through the [Teams Premium add-on license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams). Teams Premium enhances users’ Teams experience through intelligent, customizable, and secured collaboration scenarios.

- **Decorate my background**: Your users can use AI to decorate their backgrounds.
- **Intelligent call and meeting recap**: Provide your users with AI-powered insights and recaps of Public Switched Telephone Network (PSTN) calls (if they're [connected to the PSTN](pstn-connectivity)), 1:1 Teams calls, and meetings.
- **Live translated captions**: Allow your users to see captions translated into the language they’re most comfortable with.
- **Live translated transcription**: Your users can understand each other better during a meeting or event by translating the meeting transcript into the language they're most comfortable with.

| Feature | Admin articles | End-user articles |
| --- | --- | --- |
| Decorate my background | None | [Change your background in Microsoft Teams meetings](https://support.microsoft.com/office/f77a2381-443a-499d-825e-509a140f4780) |
| Intelligent call recap, intelligent meeting recap, and audio recap | [Intelligent recap for Teams calls and meetings](intelligent-recap-calls-meetings) | [Recap in Microsoft Teams](https://support.microsoft.com/office/c2e3a0fe-504f-4b2c-bf85-504938f110ef#bkmk_intelligent_meeting_recap) |
| Live translated captions | [Manage transcription and captions for Teams meetings](meeting-transcription-captions) | [Use live captions in Microsoft Teams meetings](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260) |
| Live translated transcription | [Manage transcription and captions for Teams meetings](meeting-transcription-captions) | [View live transcription in Microsoft Teams meetings](https://support.microsoft.com/office/dc1a8f23-2e20-4684-885e-2152e06a4a8b) |