---
layout: Conceptual
title: Email options when Audio Conferencing settings change - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/enable-or-disable-sending-emails-when-their-settings-change-in-teams
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
ms.date: 2024-02-21T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Learn how to enable or disable Microsoft Teams from sending emails to users when settings such as pin changes or the default conferencing number changes in Teams. '
locale: en-us
document_id: 7aebda07-e7a4-163c-bf2e-255fe77f975d
document_version_independent_id: e25ce13d-3b29-53ef-1bd2-eb11d20fbc36
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/enable-or-disable-sending-emails-when-their-settings-change-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enable-or-disable-sending-emails-when-their-settings-change-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/enable-or-disable-sending-emails-when-their-settings-change-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5d99fc9f-1633-cc2e-f0ec-9c8014b1263d
---

# Email options when Audio Conferencing settings change - Microsoft Teams | Microsoft Learn

An email is sent to users when they're enabled for Audio Conferencing. There might be times when you want to reduce the number of emails that are sent to Microsoft Teams users. In these cases, you can disable sending emails.

If you disable sending emails, Audio Conferencing emails aren't sent to your users. Emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes aren't sent.

Here's an example of the email that is sent to users when they're enabled for Audio Conferencing:

![Example of an Audio Conferencing email message.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

## When are emails being sent to your users?

- There are several emails that are sent to users in your organization after they're enabled for audio conferencing:

    - When an **Audio Conferencing** license is assigned to them.
    - When you manually reset the user's audio conferencing PIN.
    - When you manually reset the user's conference ID.
    - When the **Audio Conferencing** license is removed from them.
    - When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.
    - When the audio conferencing provider of a user is changed to Microsoft.

## Enable or disable email from being sent to users

You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.

### Using the Microsoft Teams admin center

1. In the left navigation, go to **Meetings** &gt; **Conference Bridges**.
2. At the top of the **Conference Bridges** page, select **Bridge settings**.
3. In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.
4. Select **Save**.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

### Using Windows PowerShell

You can also use the Microsoft Teams PowerShell module and run:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

You can use the [Set-CsOnlineDialInConferencingTenantSettings](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.

For more information, see [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams/).

## Want to know more about Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these articles:

- [Why you need to use Office 365 PowerShell](/en-us/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
- [Best ways to manage Office 365 with Windows PowerShell](/en-us/previous-versions//dn568025%28v=technet.10%29)

For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams).