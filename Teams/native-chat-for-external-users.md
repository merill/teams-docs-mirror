---
layout: Conceptual
title: Microsoft Teams chat experience when communicating with people outside the organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/native-chat-for-external-users
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.custom:
- chat-teams-channels-revamp
- guest-access-external-collab
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: manish.jaisinghani
ms.date: 2025-02-09T00:00:00.0000000Z
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Learn about the native Teams chat experience for external access users in Microsoft Teams where both users are in the TeamsOnly upgrade mode.
locale: en-us
document_id: 1ac8f101-bdb5-2b55-d5f4-e070b70768d4
document_version_independent_id: 964d836e-d00b-b585-8f02-e03c5ec8dab9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/native-chat-for-external-users.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: native-chat-for-external-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/native-chat-for-external-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7dce722c-4dad-2ce0-c3be-fa413b46af7b
---

# Microsoft Teams chat experience when communicating with people outside the organization - Microsoft Teams | Microsoft Learn

When a Microsoft Teams user is chatting with someone outside the organization, there are two possible chat experiences:

- Native chat - a chat experience that includes formatting, @mentions, emojis, etc.
- Text-only chat

Native chat is available when communicating with people in other Microsoft 365 organizations, provided both users are in [Teams only coexistence mode](setting-your-coexistence-and-upgrade-settings) and both are in the same cloud environment. It's also available when communicating with Teams users not managed by an organization (those using Microsoft accounts).

Text-only chat is available in all other chat experiences, including:

- Communicating with Skype for Business users
- Communicating with Skype users
- Communicating between cloud environments, such as GCC High to commercial cloud

The following table shows the chat experience users get when communicating between organizations, across clouds, and with unmanaged Teams accounts (people with personal accounts).

| Chat experience | Commercial | GCC | GCC High | DoD |
| --- | --- | --- | --- | --- |
| **Commercial** | Native | Native | Text only | Text only |
| **GCC** | Native | Native | Text only | Text only |
| **GCC High** | Text only | Text only | Native | Text only |
| **DoD** | Text only | Text only | Text only | Native |
| **Skype** | Text only | Not available | Not available | Not available |
| **Skype for Business Server** | Text only | Text only | Text only | Text only |
| **Unmanaged Teams accounts** | Native | Not available | Not available | Not available |

Note

In the 21Vianet environment, external chats between organizations within 21Vianet cloud are supported as native chats. Cross‑cloud chats between 21Vianet and Commercial organizations are supported as text‑only 1:1 chats.

## Teams chat experience while migrating from Skype for Business Server

Teams periodically checks the upgrade mode for people in other organizations, and when it finds them running Teams in the `TeamsOnly` upgrade mode, it prompts you to switch to a native Teams chat and lock the original chat.

When you switch to a native Teams chat, Teams doesn't merge the two conversations. Instead, you'll see both of the chats in your chat feed. The new, native-Teams chat is active, but the old, text-only chat is locked.

If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the `TeamsOnly` upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat. You won't be able to continue in the native Teams chat. You can still read the native Teams chat, but you can't continue the conversation there.

If Teams finds an old text-only chat with this person, it revives that chat. Otherwise, Teams creates a new text-only chat.