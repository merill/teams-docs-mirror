---
layout: Conceptual
title: Turn guest access in Microsoft Teams on or off - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-guests
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
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
ms.date: 2024-06-11T00:00:00.0000000Z
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
- chat-teams-channels-revamp
- guest-access-external-collab
ms.localizationpriority: medium
f1.keywords:
- CSH
description: Learn about how to turn on or turn off the guest access feature in Microsoft Teams as an Office 365 admin.
locale: en-us
document_id: 042d7ce6-ee22-690f-8188-ff8a4a585847
document_version_independent_id: 3e5bc99c-e08e-44e0-cda3-687ed3633175
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-guests.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-guests
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-guests.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9ccc61cb-3424-ecd7-4695-796dd6b32d78
---

# Turn guest access in Microsoft Teams on or off - Microsoft Teams | Microsoft Learn

This article describes how to configure guest access settings - including calls, meetings, and chat - in Teams. Guest access in Teams also requires configuring other settings in Microsoft 365, including settings in Microsoft Entra ID, Microsoft 365 Groups, and SharePoint. If you're ready to start inviting guests to teams, read one of the following:

- To configure guest access for Teams for general use, see [Collaborate with guests in a team](/en-us/previous-versions/microsoft-365/solutions/collaborate-as-team).
- To collaborate with a partner organization that uses Microsoft Entra ID and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](/en-us/microsoft-365/solutions/b2b-extranet).

Note

If you just want to find, call, chat, and set up meetings with people in other organizations, use [external access](trusted-organizations-external-meetings-chat).

## Configure guest access in the Teams admin center

1. Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).
2. Select **Users** &gt; **Guest access**.
3. Set **Guest access** to **On**.

    ![Allow guest access switch set to On .](media/guest-access-setting.png)
4. Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guests.

    - **Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.
    - **Video conferencing** - Turn this setting **On** to allow guests to use video in their calls and meetings.
    - **Screen sharing**– This setting controls the availability of screen sharing for guests.
        - Turn this setting to **Not enabled** to remove the ability for guests to share their screens in Teams.
        - Turn this setting to **Single application** to allow sharing of individual applications.
        - Turn this setting to **Entire screen** to allow complete screen sharing.
    - **Meet now in channels** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.
    - **Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.
    - **Delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.
    - **Delete chat** - Turn this setting **On** to allow guests to delete an entire chat conversation.
    - **Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.
    - **Giphy in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations. Giphy is an online database and search engine that allows users to search for and share animated GIF files. Each Giphy is assigned a content rating.
    - **Giphy content rating**– Select a rating from the drop-down list:
        - **Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.
        - **Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.
        - **Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.
    - **Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.
    - **Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.
    - **Immersive reader for messages** - Turn this setting **On** to allow guests to use [immersive reader in Teams](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a).

    ![Guest permissions settings in Teams.](media/manage-guest-access-image1.png)
5. Select **Save**.

Note

If you're an administrator, and you're having trouble with guest access in Teams, select **Run Tests** below, which will populate the guest access diagnostic in the Microsoft 365 admin center. These tests will check your configuration and recommend next steps to enable guest access for your organization.

## Turning guest access off

If you turn guest access off in Teams, existing guests lose access to their team. However, they are not removed from the team. They are still visible to people in the team and can be @mentioned. If you turn Teams guest access on again, they will regain access.

If you plan to leave guest access off, you may want to advise your team owners to manually remove the guest accounts from their teams. While these guests won't have access, having their accounts visible in the team could lead to confusion for other people in the team.