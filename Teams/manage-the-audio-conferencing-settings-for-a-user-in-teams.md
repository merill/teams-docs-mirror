---
layout: Conceptual
title: Manage the Audio Conferencing settings for a user in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-the-audio-conferencing-settings-for-a-user-in-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: oscarr
ms.date: 2026-10-06T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: An admin can edit the Teams Audio Conferencing settings, including provider, default toll or toll-free number, conference ID, or PIN for a user.
locale: en-us
document_id: 2167d5b2-c4c4-3164-2ed2-9582c8a0f95b
document_version_independent_id: cbbf9c78-5708-a0a9-31c3-d2cb4b31f6d3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-the-audio-conferencing-settings-for-a-user-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-the-audio-conferencing-settings-for-a-user-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-the-audio-conferencing-settings-for-a-user-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 16466e7b-48ef-662d-e757-2c88d879d03e
---

# Manage the Audio Conferencing settings for a user in Microsoft Teams - Microsoft Teams | Microsoft Learn

As an admin, you can edit Audio Conferencing settings for each user in your organization. To edit settings for your organization, see [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams).

## Using the Microsoft Teams admin center

1. Open the Teams admin center.
2. Expand **Users** from the navigation pane and select **Manage users**.
3. Select the name of the user you want to manage.
4. Under the **Audio Conferencing** section in the **Account** tab, edit any of the following settings:

[![Screenshot of Audio Conferencing settings for a user in the Microsoft Teams Admin Center.](media/new-ac-user-small.png)](media/new-ac-user-expand.png#lightbox)

| Setting | Description |
| --- | --- |
| **Send conference info in email** | Select this link to instantly send an email to the user with their audio conferencing phone number. This email doesn't include the PIN. For more information, see [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams). |
| **PIN** | Select **Reset PIN** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams). |
| **Default conferencing toll phone number** (required) | Set the numbers on the audio conferencing bridge and format them as you want them to appear in Teams meeting invitations. To change the default toll number, select **Edit** next to **Audio Conferencing.** In the **Audio Conferencing** pane, choose a number under **Toll number.** You can also set phone numbers by adding them to the **`-Set-CsTeamsAudioConferencingPolicy`** and assigning the policy to your users. Phone numbers added to the policy take precedence over numbers set using the **Default conferencing Toll phone number**. If no phone numbers are added to the **`-Set-CsTeamsAudioConferencingPolicy`**, the phone number set with **Default conferencing Toll phone number** is shown on Microsoft Teams meeting invitations. |
| **Invites from this user can include toll-free number** | This setting can only be changed using the **`-Set-CsTeamsAudioConferencingPolicy`**. |
| **Dial-out permissions** | To change this setting, select **Edit** next to **Audio Conferencing** and in the **Audio Conferencing** pane, choose an option under **Dial-out from meetings**. |

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.