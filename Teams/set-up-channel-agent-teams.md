---
layout: Conceptual
title: Set up a Channel Agent for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-channel-agent-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
ms.reviewer: jeanniewang
ms.date: 2025-09-17T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: 
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- Tier1
- teams-copilot
- magic-ai-copilot
description: Learn how to set up Channel Agents for Microsoft Teams for your organization in the Teams admin center. This article provides steps to allow the app, enable it for specific users or groups, and manage automatic agent creation in Teams channels.
locale: en-us
document_id: 3e1fd684-ce86-40e9-6edf-1046cf1814b4
document_version_independent_id: 3e1fd684-ce86-40e9-6edf-1046cf1814b4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-channel-agent-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-channel-agent-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-channel-agent-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 86fbf780-fb89-4733-738e-8ace204ed668
---

# Set up a Channel Agent for Microsoft Teams - Microsoft Teams | Microsoft Learn

## Overview

Important

The following feature is currently in public preview. Features in preview might not be complete and could undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.

For more information about Teams features in public preview, see [Microsoft Teams Public preview](public-preview-doc-updates).

**An agent for every channel**: Teams channels provide an organized space for teams to manage workstreams and communicate with stakeholders. Now, each channel can have a dedicated agent that draws on its conversations and meetings to act as a domain expert for the team. These agents adopt the channel’s name and help with common tasks—such as flagging important deadlines that are buried in conversations, summarizing progress with succinct status reports, assigning tasks and due dates, and answering questions asked in natural language like *What’s the latest on our budget?* Your users can even invite these agents into meetings when they need expert insights into their discussion.

For more information on how your users can use a Channel Agent, see [Get started with Channel Agent in Microsoft Teams](https://support.microsoft.com/office/b85945cf-deef-4f1e-9db1-66e1a23b6a65).

## Security, compliance, and privacy

Channel Agents, Teams channels, Microsoft Copilot, and Microsoft 365 are built on Microsoft's comprehensive approach to security, compliance, and privacy.

- Channel Agent follows the App compliance model for events such as:

    - Adding an agent to a channel, meeting chat, or group chat
    - Removing an agent from a channel, meeting chat, or group chat
    - Bot messages
- Channel Agents share status reports in Loop.

    - Once created, user edits in the Loop follow Loop’s existing compliance model.
- Channel Agents can use their knowledge to answer questions about the project.

    - In a channel, any licensed and admin-enabled user can ask the agent questions.
    - In meetings and group chats that the agent is added to, only licensed, admin-enabled, and channel members can ask questions.
    - The agent will not use file content to answer a user’s question if the user does not have access to the file.
    - If the user has access to the file but other members of the conversation do not, the agent will ask the user if they would like to share the response to the broader audience. The user will have the opportunity to review the response and decide whether to share the response.

To learn how Microsoft Purview supports your security and compliance management for Channel Agents and some recommended getting started steps, see [Use Microsoft Purview to manage data security & compliance for a Channel Agent](/en-us/purview/ai-teams-channel-agent).

For more information about the security and privacy standards used to develop Microsoft Copilot and AI agents like Channel Agents, see the following articles:

- [Data, Privacy, and Security for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-privacy) in your organization (work or school).
- [Microsoft Purview data security and compliance protections for generative AI apps](/en-us/purview/ai-microsoft-purview).
- [Copilot Pro: Microsoft 365 apps and your privacy](https://support.microsoft.com/office/6f0d8d80-f4bb-4c9f-989e-64a4adfd62e5) for Microsoft Copilot apps at home.

## Prerequisites

The following list contains the prerequisites for users to be able to access a Channel Agent. Users must meet all of the following requirements:

### Licensing requirements

- An eligible *Microsoft 365*base license.
    - For the list of eligible base licenses, see [Understand licensing requirements for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing).
- Have an eligible *Microsoft Teams*license.
    - Teams licenses might be included in your *Microsoft 365* subscription. If you have *Microsoft 365 (no Teams)* licenses, you need to purchase separate Teams licenses.
- Have a *Microsoft Copilot*license.
    - For information on how to acquire *Microsoft Copilot* licenses, see [Where can I get Microsoft Copilot?](https://support.microsoft.com/topic/where-can-i-get-microsoft-copilot-40a622db-6d25-4266-b008-4bbcb55cf52f).

### User requirements

- Be a Microsoft Teams Public preview participant.
    - For information on how to access Teams Public preview features, see [Microsoft Teams Public preview](/en-us/microsoftteams/public-preview-doc-updates).
- Have Loop experiences in Teams for Channel Agents turned on.

Channel Agents are built on Teams App Platform. They respect existing platform settings, such as:

- [Teams apps for external attendees or guests from outside an organization](apps-external-users)
- [Roles in Teams Meetings](https://support.microsoft.com/office/c16fa7d0-1666-4dde-8686-0a0bfe16e019)

## Allow Channel Agents

As an IT admin, you control whether Channel Agents are available to your entire organization or to a certain group of users.

Channel Agents are allowed by default. However, if all apps are blocked for your organization, Channel Agents are also blocked.

To allow or block Channel Agents for users, complete the following steps:

### 1. Allow Channel Agents in the Teams admin center

In addition to licensing and user prerequisites, Channel Agents should also be made available in Teams admin center to enable users.

1. Sign in to the Teams admin center.
2. In the left rail navigation, select **Teams apps** &gt; **Manage apps**.
3. In the apps list's search box, search for **Channel Agent**.
4. Select **Channel Agent** from the app list.
5. In the Actions menu, select **Allow** or **Block**, to allow or block the overall app. To turn off access to Channel Agent from your users, **Block** the overall app.

Note

If the **Allow** button is not present, check to see if the availability of the app is set to **No one.** If it is, the availability needs to be changed to **Everyone** or a selected group of users to make the app available.

You can also use [app centric management](/en-us/microsoftteams/app-centric-management) to allow and block, create policies, and assign users.

For more information about managing apps in Teams, see [Manage apps](manage-apps).

### 2. Enable Channel Agents for specific users or groups

Users who are enabled for Channel Agents can fully utilize the app in their Teams channels. This means they can:

- Create or remove the agent from a Teams channel.
- Configure agent settings (including the status report).
- Add or remove the agent from a Teams channel meeting chat.

Users who aren't enabled for Channel Agents can view the agent’s presence and messages, but they can't interact with the agent.

To enable Channel Agents for users, a new app policy needs to be created and then assigned to users.

Follow the instructions at [Use app permission policies to control user access to apps](teams-app-permission-policies) to create a new app policy for Channel Agents.

You can then assign the policy to your entire tenant or to a select group of users. Follow the instructions at [Add or modify app availability for users](/en-us/microsoftteams/app-centric-management#add-or-modify-app-availability-for-users) to assign the policy to users using app-centric management.

In order for licensed and enabled users to use a Channel Agent *within a meeting chat*, the user must be a member of the channel that the agent is created in. These users may also need additional permissions for chat history and transcription access.

### 3. Turn on Loop experiences in Teams for Channel Agents

*Loop experiences in Teams* need to be turned on in order for Channel Agents to be used in meetings.

To turn on Loop experiences in Teams, follow the instructions at [Settings management for Loop functionality in Teams](/en-us/microsoft-365/loop/loop-components-configuration#settings-management-for-loop-functionality-in-teams).

### 4. Manage automatically created Channel Agents (optional)

By default, for any new channel that an eligible user creates, a Channel Agent is automatically added to the channel. If you would like to change this behavior, you can update this in the Teams admin center using the following steps:

1. Sign in to the Teams admin center.
2. In the left rail navigation, select **Teams apps** &gt; **Agent settings**.
3. Toggle auto-creation to **On** or **Off**.
4. Select **Save**.

This setting is generally available for admins to manage this feature for their users in public preview.

Note

Auto-creation will be default **Off** for EDU tenants. If you would like to have auto-creation, follow the steps above and toggle auto-creation from **Off** to **On**.

## Information access and knowledge management for a Channel Agent

The information a Channel Agent can access is currently limited to searching the web, channel messages, channel files, channel meetings, standard meetings, and meeting transcription. Additional data sources may be added in the future.

### Gathering knowledge with a Channel Agent

In the agent’s channel, the agent automatically uses the channel’s messages and the channel's SharePoint files as its knowledge. Channel Agent doesn’t use any files shared in links or files outside of the channel’s SharePoint.

Channel Agents can be added to both standard meetings and channel meetings to gather knowledge. In these meetings, after the transcript is generated, the agent sends a message telling users that it will create a summary from the transcript. Users have 24 hours to either approve or reject the created summary. If no action is taken after the 24-hour window, the agent automatically adds the summary to its knowledge. Users can still choose to remove the summary after the 24-hour window. If a user removes the information after the 24-hour window, the information may be used in agent responses prior to its removal but the information isn't used again after its removal.

If the agent is added to a reoccurring meeting series, the agent has access to up to one transcript prior to its addition and up to 28 days of chat history. After its addition, the agent continues to follow the chat’s progress and can access new transcripts.

In group chats that the agent is added to, the agent doesn't absorb any chat messages; however, users in the chat can ask the agent questions and the agent uses its knowledge base to answer them.

The agent can’t access files shared in meetings or group chats. The agent also doesn’t read or incorporate summaries from group chats into its knowledge base.

### Sharing knowledge with a Channel Agent

Channel Agents use knowledge in its responses\*—for example when it generates a status report or answers a question directed to it in a channel or meeting message. When a meeting summary is shared with the agent, it can use the summary to help any member of the channel, including people who didn't attend the meeting or don't have access to the chat or transcript.

When an agent determines that a file will be the best resource to answer a question, it will check the permissions of the requesting user. It won't use files that the requesting user doesn't have access to, files whose sensitivity labels prevent extractions, or files with DLP policies that prevent AI-usage. If the agent is unable to check whether or not all users that will receive the message have access to the files used, it will ask the requesting user if they would like to share the response with the group.

When an agent is asked questions outside the channel—such as in group chats or meetings where non-channel members may be present—it will only share responses after confirming with the requester and obtaining permission to share the information.

Channel Agents use the files in the Channel SharePoint as grounding information. When doing this, it checks the access of the user prompting the agent and allows the user to share the response with others in chats / channels.

Note

Channel Agents may gather context that crosses [Information Barriers](/en-us/purview/information-barriers-teams).

> 
> Channel Agents use sensitivity labeled information to answer user questions, including channel messages, files in the channel SharePoint, channel meetings, and standard meetings. The agent visually indicates the sensitivity label above its response; however, the output doesn't inherit the controls of the sensitivity label itself and doesn't prevent the information from being further shared. For more information about sensitivity labels, see [Sensitivity labels for Microsoft Teams](sensitivity-labels).

### Removing knowledge from a Channel Agent

If a Channel Agent is removed from a meeting or meeting series, it foregoes any knowledge gathered from it. If the agent is re-added to the meeting source, knowledge collection starts from a zero state.

If the agent is removed from a channel, it foregoes all knowledge gathered—whether from the channel or meeting chats. Recreating the agent results in a zero state.

### Accessing knowledge from the web with a Channel Agent

A Channel Agent can search the web if the user asks it to. However, you can choose to turn off this feature. If you choose to turn off web search for users, this action also turns off web search for all Copilot features in Microsoft products that can search the web.

For more information about how web search works and the different types of web controls that exist, and how to manage them, see Data, privacy, and security for web search in [Microsoft Copilot and Microsoft Copilot Chat](/en-us/microsoft-365/copilot/manage-public-web-access).

### Status report data

Channel Agents create status reports that are stored in Loop as a `.loop` file. This file is stored in the Channel folder within the channel's SharePoint site. The author of the Loop file is the user who created the Channel Agent. For more information on Loop files and how they are stored, see [Overview of Loop storage](/en-us/microsoft-365/loop/loop-storage).

## Limitations

Currently, the following limitations apply to a Channel Agent:

- Only one Channel Agent can be supported in a Teams channel.
- Channel Agents can’t be added to additional channels – only the one it is created in.
- Private channels don't currently support Channel Agents.
- In a standard or shared channel, the user must be an owner or member of the team and channel to create an agent.
- If a Team owner has turned off the default setting **Allow members to add and remove apps**, only Team owners can create and delete a Channel Agent; however, the agent will still be auto-created if a member creates a channel and admins allow for auto-creation.
- Group chats aren't currently supported to add to the agent’s knowledge.
- Scheduling skill will only schedule channel meetings in the agent’s channel.
- Response quality may differ across languages.
- Channel Agents with external users aren't functional. Channel Agents and chats with external users can't answer questions about the channel.
- Channel Agents aren't supported in tenants that use [Customer Key](/en-us/purview/customer-key-overview).
- Processing data from previews can happen outside of the EU Data Boundaries.