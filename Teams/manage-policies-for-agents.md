---
layout: Conceptual
title: Manage Teams policies for Microsoft Agent 365 agents - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-policies-for-agents
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: mabond
ms.date: 2025-11-14T00:00:00.0000000Z
ms.topic: reference
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- Tier1
- m365initiative-voice
- m365initiative-meetings
- teams-rooms-devices
- ContentFreshnessFY24
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: This reference describes the key policy settings in Microsoft Teams that apply to agents, helping you configure their collaboration, meetings, and messaging behavior securely.
locale: en-us
document_id: 94dfadff-2314-0006-a1d2-ef4f2227c18a
document_version_independent_id: 94dfadff-2314-0006-a1d2-ef4f2227c18a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-policies-for-agents.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-policies-for-agents
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-policies-for-agents.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/302444b9-4a43-4841-8014-3d9e4251ff15
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bebd8809-dac1-4c22-83e2-66d98af8a94d
platformId: 513f8691-e289-ee6c-2e8f-443330bb3f4f
---

# Manage Teams policies for Microsoft Agent 365 agents - Microsoft Teams | Microsoft Learn

Agents created as part of Agent 365 are governed by the same policy framework used for new end users in Microsoft Teams. However, some settings require special attention due to security reasons. When an agent is created from an Agent Blueprint, it receives the default user policies that are automatically applied to new users in the organization.

You can view and update these agents’ policy assignments in Teams Admin Center, using the same experience and controls available for other users. Read more on [Teams settings and policies reference](settings-policies-reference).

## How policies apply to Microsoft Agent 365 agents

- All existing Teams user policies apply to agents.
- Agents inherit the organization’s default policy assignments when they are created.
- You can reassign or customize policy settings for each agent as needed.

To review or update these agents’ policies:

**Navigation:** Teams admin center &gt; Users &gt; Manage users &gt; Policies

[![Screenshot of a list of policies for selected user or agent.](media/policies.png)](media/policies.png#lightbox)

Important

- The policy areas listed here highlight key settings related to agent behavior, with a focus on external collaboration. This list is not exhaustive.
- Carefully review all applicable user policies to ensure agents are configured appropriately for your organization’s security and collaboration requirements.

## Key policy areas to review for Microsoft Agent 365 agents

While agents follow the same policy model as normal end users, some settings require special attention. These settings can affect how agents interact with external participants, schedule meetings, send messages, and access shared content.

### External collaboration

External collaboration settings span several policy areas. They control how agents can communicate or interact outside your organization. These settings are important for data security and help ensure agents stay within the intended collaboration boundaries.

#### External access and guest access

These settings control whether agents can:

- Start chats with external users.
- Join external tenants’ meetings.
- Invite guests or external participants to shared channels.
- Interact with external organizations through Teams chat or channels.

[![Screenshot that shows the External access policies.](media/external-access-policies.png)](media/external-access-policies.png#lightbox)

##### Related articles for external access and guest access

- [Use guest access and external access to collaborate with people outside your organization](communicate-with-users-from-other-organizations)
- [Collaborate with external participants in a shared channel](/en-us/microsoft-365/solutions/collaborate-teams-direct-connect?view=o365-worldwide&amp;preserve-view=true)

#### Meeting policies

Meeting policies can also impact external collaboration. You can control whether:

- Agents can schedule meetings that allow anonymous participants.
- Anonymous or external users can interact with apps in meetings organized by an agent.
- Agents themselves can join meetings hosted by another organization.

[![Screenshot of settings that keep agents secure and within collaboration limits.](media/join-lobby-small.png)](media/join-lobby-small.png#lightbox)

These settings help ensure agents operate securely within intended collaboration boundaries.

#### Related articles for meeting policies

[Meeting policies](settings-policies-reference#meetings)

#### Messaging

Agents may participate in ongoing conversations or channels to support business workflows, review that the allowed messaging capabilities match the agent’s intended role. Messaging policies determine what chat and channel features an agent can use such as:

- Whether an agent can delete sent messages.
- Whether it can start group chats.
- Whether rich media features (for example, Giphy) are available.

[![Screesnhot that shows the messaging policy settings.](media/messaging-tac.png)](media/messaging-tac.png#lightbox)

#### Related articles for messaging policies

[Messaging policies](settings-policies-reference#messaging-policies)