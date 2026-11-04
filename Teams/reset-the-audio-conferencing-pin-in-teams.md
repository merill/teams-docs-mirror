---
layout: Conceptual
title: Reset the Audio Conferencing PIN in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/reset-the-audio-conferencing-pin-in-teams
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
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
- seo-marvel-apr2020
description: Learn how to reset a user's Audio Conferencing PIN in Microsoft Teams, and learn important facts about PINs.
locale: en-us
document_id: 401f39f3-f614-6d63-adbd-1ed78ed804f0
document_version_independent_id: 26b45c86-8f6f-8704-d95a-f8c341e569ad
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/reset-the-audio-conferencing-pin-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: reset-the-audio-conferencing-pin-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/reset-the-audio-conferencing-pin-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 03fd0904-4b0b-b900-519f-babcaa6e6fc6
---

# Reset the Audio Conferencing PIN in Microsoft Teams - Microsoft Teams | Microsoft Learn

A PIN is a code made up of numbers that's created for each Microsoft Teams Audio Conferencing user. Meeting organizers use Audio Conferencing PINs to start meetings over the phone. If organizers use the Microsoft Teams app to start the meeting, a PIN isn't required. If users forget their PIN and can't locate it in their activation email, as an admin, you can reset it. Your users can also reset their own PIN.

Meetings start when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone. When a meeting requires a PIN to start, users who join over the phone are placed in the lobby. These users listen to music on hold until the organizer admits them. If the meeting organizer doesn't require a PIN to start the meeting over the phone, then callers aren't asked to provide a PIN when they join the meeting.

## Reset a user's PIN

Using the Microsoft Teams admin center:

1. In the left navigation, select **Users**, and then select the user from the list of available users.
2. Select **Edit**.
3. Under **Audio Conferencing**, select **Reset PIN**.
4. Select **Reset**.

## Have a user reset their own PIN

1. Have your user go to https://dialin.teams.microsoft.com/usp.
2. Select **Reset PIN**.

    Note

    For GCCHs go to: https://dialin.cpc.gov.teams.microsoft.us/usp. For DoD go to: https://dialin.cpc.dod.teams.microsoft.us/usp.

    Note

    A PIN reset email isn't sent to the user if they use this method.

## What else should you know about PINs?

- For security purposes, the PIN is only shown to you, as an admin, once- when the PIN is reset. After you reset the PIN, the PIN is listed as \*\*\*\*\*\*\*\*\*\*\*.
- Automatically sending emails to users is on by default. When users are set up for Audio Conferencing or when their PIN is reset, they receive an email. If you turn off automatically sending emails, PIN reset emails aren't sent to the user and you have to manually send the PIN information to the user.
- When a meeting starts, the organizer needs to admit all Public Switched Telephone Network (PSTN) users in the lobby to join the meeting. If two PSTN participants try to join a meeting that already started, they're placed in the lobby with hold music. When the meeting organizer joins via phone using their PIN, they can start the meeting and use the in-meeting command (\*21) to admit all PSTN users in the lobby.
- The default setting is to not allow anonymous callers to start a meeting.
- When you set up a user for Audio Conferencing, by default they're sent emails that include conferencing information and their PIN. The user must have a Microsoft 365 or Office 365 mailbox. When you reset a PIN, the new one is emailed to the user's primary Simple Mail Transfer Protocol (SMTP) address (alias).
- When you set up Audio Conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs. The setting isn't applied to the PIN setting for existing Audio Conferencing users. For more information, see [Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings-in-teams).
- The email by default is set to the Microsoft 365 or Office 365 primary SMTP address of the user. You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address. You can override the default email address by using Windows PowerShell. This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.

## Want to know more about Windows PowerShell?

With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

- [Why you need to use Office 365 PowerShell](/en-us/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
- [Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/en-us/previous-versions//dn568025%28v=technet.10%29)

For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams).

## Related topic

- [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams)