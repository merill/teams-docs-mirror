---
layout: Conceptual
title: Email a user their Audio Conferencing information - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/send-an-email-to-a-user-with-their-dial-in-information-in-teams
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
ms.date: 2026-10-09T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Learn about how to send your users an email with their Audio Conferencing information in Microsoft Teams.
locale: en-us
document_id: 63e4e416-2409-1db4-29a8-e56cddee79de
document_version_independent_id: dd134eff-26be-488d-46bc-8104d0b96614
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/send-an-email-to-a-user-with-their-dial-in-information-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: send-an-email-to-a-user-with-their-dial-in-information-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/send-an-email-to-a-user-with-their-dial-in-information-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 25adb222-38a6-afa5-863d-e5a62976ab0c
---

# Email a user their Audio Conferencing information - Microsoft Teams | Microsoft Learn

Sometimes, Microsoft Teams users need you to send them their Audio Conferencing information. As an admin, you can do this by selecting **Send conference info via email** under the properties for a user. When you send this email, it contains all of the Audio Conferencing information, including the conference phone or dial in phone number for the user.

Here's an example of the email that is sent:

![Example of a dial-in conferencing email message.](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Send an email with Audio Conferencing information to a user

### Sending an email using the Microsoft Teams admin center

1. In the navigation pane, expand **Users** &gt; **Manage users**, and then select the user from the list of available users.
2. In the **Audio Conferencing** section, select **Edit**.
3. Select **Send conference info in email**.

[![Screenshot of Audio Conferencing settings for a user in the Microsoft Teams Admin Center.](media/new-ac-user-small.png)](media/new-ac-user-expand.png#lightbox)

## Audio Conferencing email notifications

There are several emails that are sent to users in your organization after they're enabled for Audio Conferencing:

- When an **Audio Conferencing** license is assigned to them.
- When you manually reset the user's Audio Conferencing PIN.
- When an **Audio Conferencing** license is removed from them.
- When the Audio Conferencing provider for a user is changed from Microsoft to another provider or **None**.
- When the Audio Conferencing provider for a user is changed to Microsoft.

To learn how to manage these email notifications, see [Emails sent to users when their settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams).