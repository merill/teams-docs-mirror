---
layout: Conceptual
title: Allow users to delete bot messages in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/delete-bot-messages
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
ms.reviewer: deekshanyab, mmarchant
ms.date: 2025-08-12T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
- magic-ai-copilot
ms.custom:
- admindeeplinkTEAMS
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Learn how you can allow your users to delete bot messages in Microsoft Teams.
locale: en-us
document_id: f7b85475-291c-fe69-e981-91c7fdc54a1f
document_version_independent_id: f7b85475-291c-fe69-e981-91c7fdc54a1f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/delete-bot-messages.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: delete-bot-messages
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/delete-bot-messages.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8f946159-c3ed-8f09-608f-dfa991b0066e
---

# Allow users to delete bot messages in Teams - Microsoft Teams | Microsoft Learn

The growing catalog of Copilot features and agents in Teams means that your users' chats could include messages from bots, like [Facilitator](facilitator-teams). Your users may find times when the bot's messages are inaccurate, out of date, or irrelevant. In these scenarios, your users may want to delete a bot's messages.

In order to allow users to delete bot messages in Teams, you need to turn on the **Users can delete messages sent by bots** setting in the Teams admin center or by using PowerShell.

## Considerations for deleting bot messages

- The **Users can delete messages sent by bots** setting is turned off by default.
- Any user in a chat can delete bot messages, including guests, external, and anonymous users.
- When a use deletes a bot message, the message is deleted for all users in that chat. Once deleted, the bot's message is replaced by a message indicating the message was deleted.
- Only the user who deleted the bot message in a chat can restore the deleted message, which makes the message visible again to the entire chat.
- Adjusting the **Users can delete messages sent by bots** setting affects all communications in Teams including 1:1 chats, group chats, all channels, and meeting chats.

## Allow delete bot messages in the Teams admin center

The **Users can delete messages sent by bots** setting is a messaging policy and can be managed in the Teams admin center. To manage this setting, complete the following steps:

### The legacy Teams admin center experience

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) with your admin credentials.
2. In the left-side menu, expand the **Messaging** section.
3. Select **Messaging policies** from the menu.
4. On the **Messaging policies** page, change the toggle to **On** for **Users can delete messages sent by bots**.
5. Select the **Save** button.

#### Change the setting for guests (legacy experience)

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) with your admin credentials.
2. In the left-side menu, expand the **Users** section.
3. Select **Guest access** from the menu.
4. On the **Guest access** page, find the **Messaging** section.
5. Change the toggle to **On** for **Users can delete messages sent by bots**.
6. Select the **Save** button.

### The new Teams admin center experience

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) with your admin credentials.
2. In the left-side menu, select **Settings & policies**.
3. On the **Settings & policies** page, choose either the **Global (Org-wide default) settings** or the **Custom policies for users & groups** tab.
4. Once you choose the policy to change, select **Messaging** from the list of setting categories.
5. Change the toggle to **On** for **Users can delete messages sent by bots**.
6. Select the **Save** button.

#### Change the setting for guests (new experience)

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) with your admin credentials.
2. In the left-side menu, select **Settings & policies**.
3. Find the **External collaboration** section, and select **Guest access**.
4. On the **Guest access settings** page, find the **Messaging** section.
5. Change the toggle to **On** for **Users can delete messages sent by bots**.
6. Select the **Save** button.

## Allow delete bot messages using PowerShell

You can also use PowerShell commands to update `CsTeamsMessagingPolicy` to allow users to delete bot messages. The [`UsersCanDeleteBotMessages` parameter](/en-us/powershell/module/teams/set-csteamsmessagingpolicy#-userscandeletebotmessages) can be set to either `$true` or `$false`.

- To update an existing `CsTeamsMessagingPolicy` policy, use the following code snippet. Make sure to update the `Identity` parameter, which defines an existing policy name for this setting.

    ```powershell
        Set-CsTeamsMessagingPolicy -Identity [PolicyName] -UsersCanDeleteBotMessages $true
    ```
- If this policy isn't already assigned to any users, assign this messaging policy to users with the following [`Grant-CsTeamsMessagingPolicy`](/en-us/powershell/module/teams/grant-csteamsmessagingpolicy) code snippet. In this context, the `Identity` parameter is the users' names or group you're assigning the policy to, and `PolicyName` is the name of the policy with the `UsersCanDeleteBotMessages` setting turned on.

    ```powershell
        Grant-CsTeamsMessagingPolicy -Identity [UserGroupName] -PolicyName [PolicyName]
    ```