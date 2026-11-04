---
layout: Conceptual
title: Availability and use of Teams apps by different types of users from outside an organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/apps-external-users
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: SerdarSoysal
ms.author: serdars
ms.reviewer: shmundra
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Learn how apps in Microsoft Teams work for guests, external access users, and anonymous users.
ms.localizationpriority: high
ms.date: 2026-05-22T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
locale: en-us
document_id: 0735d322-f6f5-7cc8-9994-1420e3fb7baa
document_version_independent_id: f9b25b51-eb9c-63fa-b30e-e1490c8d31b6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/apps-external-users.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: apps-external-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/apps-external-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6c81771f-7b09-598b-2630-ebdfa0ae0a52
---

# Availability and use of Teams apps by different types of users from outside an organization - Microsoft Teams | Microsoft Learn

Teams apps allow collaboration with people outside your organization. As an admin, you control who can access Teams chats, meetings, and channel to collaborate with your organization's users. For detailed information, see [how to allow collaboration with external attendees](manage-external-access) and [what can guests do in Teams](guest-access). This article focuses on use of apps by people outside your organization.

Teams users can add apps when they host meetings or chats with people from other organizations. They can also use apps shared by people in other organizations when they join meetings or chats hosted by those organizations. The data policies of the host organization and the data sharing practices of any third-party apps are applicable.

The following types of users can be present in a Teams chat or meeting and if you allow it, they can use apps in Teams.

- A **guest** is someone who has an [Microsoft Entra B2B collaboration](/en-us/azure/active-directory/external-identities/what-is-b2b) guest account your organization.
- An **external access user** is a user from another organization and might not have access to your organization's Teams resources.
- An **anonymous user** is a user who joins a meeting via a link. The user isn't logged in with their Microsoft account or their organization’s account.
- A **native user** is a signed-in Teams user who creates a chat or a meeting. Other users of the same organization are also considered native users. The organization to which native users belong is considered the host organization. All signed-in users from other organizations are considered as external users.

For a more detailed comparison between guest and external access users, see [communicate with users from other organizations](communicate-with-users-from-other-organizations).

## Guests

### Add, update, and delete apps for guests

- Guest users can't search and add apps from Teams app store (AppSource or client store) and from the in-context stores in Teams.
- Guests can't add, update, or delete apps into a shared context, such as a chat, channel, or meeting.
- Guests can add apps using [deep links](/en-us/microsoftteams/platform/concepts/build-and-test/deep-link-application). However, guests can use such apps in personal scope only.
- Guest users can use apps added by other org users in personal chats, group chats, and teams and channels.

### Usage behavior and policy for guests

Guests can use an app if the app was added by an organization's user.

#### Bots added to a channel

Guests can mention the bot and interact with Adaptive Cards.

#### Personal bots added with policies

- For any app, guests adhere to global and org-wide app policies set for the host organization. If an app is blocked in the host organization, guests can't use it.
- Any bot included in the global default app setup policy is also added for guests.
- After a bot is added, guests can communicate with it.
- You can't remove a guest from the global default app setup policy.
- If you preinstall a bot for your users using app setup policy, guests can't access such a bot.
- To avoid guests from accessing bots, you can create different app setup policies, assign them to internal users, and add bots with the custom policies.

## External access users

External users don't have access to the Teams app store of the host organization and can't add apps in chats. Native users can add and use apps in group chats with external users. App installation and usage adhere to the org-wide app policies and data policies of the host organization. The data sharing practices of any third-party apps shared by that user's organization apply.

### Add, update, and delete apps for external access users

- People from other organizations adhere to the hosting organization's global (org-wide default) policy.
- Users in the hosting organization can add apps in meeting chats with people from other organizations. People from other organizations can't add apps in meeting chats but can interact with bots, tabs, and message extensions once added to the chat.
- A meeting host can install, remove, or update apps for use by all members of a meeting, including external users.
- Apps in one-on-one chat with external users aren't supported.

### Usage behavior and policy for external access users

External users can accomplish the following actions:

- All users in a group chat or meeting chat can tag installed bots and the bot can communicate with all users.
- Participants can access the **Manage your apps** page in their Teams client but can't add, update, or remove apps from this page.
- Participants can open and use an installed tab from the message extension flyout in a group chat.

Note

- Your users' ability to create and participate in external chats is defined by your [external access policies](communicate-with-users-from-other-organizations).
- Apps in external chats aren't supported in Government Community Cloud (GCC), GCC High, and Department of Defense (DoD) environments.

## Anonymous users

### Add, update, and delete apps for anonymous users

Anonymous users can't add, update, or delete apps in meetings.

### Usage behavior and policy for anonymous users

Anonymous users can't directly use apps in meetings. If an app sends an adaptive card in the chat, anonymous users can interact with the card. Such users can interact with apps in Teams meetings if the user-level permission policy enables the app. Anonymous users inherit the user-level global default permission policy.

Anonymous users can interact only with the apps that are already available in a meeting but can't acquire and manage such apps. The native users can continue to use meetings apps even when the anonymous users are attending a meeting.

### Allow anonymous users to use apps in meetings

By default, anonymous users can interact with the existing apps in a meeting. Anonymous users can't add new apps to a meeting. You can disallow anonymous users for interacting with apps.

1. Sign in to the Teams admin center and access **Meetings** &gt; **[Meeting settings](https://admin.teams.microsoft.com/meetings/settings)**.
2. Under **Participants**, change the toggle for **Anonymous users can interact with apps in meetings** to **Off**.
3. Select **Save**.