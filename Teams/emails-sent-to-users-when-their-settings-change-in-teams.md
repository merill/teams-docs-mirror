---
layout: Conceptual
title: Emails sent to users when their settings change - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/emails-sent-to-users-when-their-settings-change-in-teams
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
ms.date: 2025-01-29T00:00:00.0000000Z
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change in Microsoft Teams. '
locale: en-us
document_id: b0cd207e-eec4-11a5-9037-5d72a9ad5044
document_version_independent_id: b3757462-ceca-36ab-1b7a-8568a7481743
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/emails-sent-to-users-when-their-settings-change-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: emails-sent-to-users-when-their-settings-change-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/emails-sent-to-users-when-their-settings-change-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c4b5a86b-37ff-17c8-0a09-9260bfc5ec41
---

# Emails sent to users when their settings change - Microsoft Teams | Microsoft Learn

Emails are automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams) using Microsoft as the audio conferencing provider.

By default, there are four types of email that are sent to your users who are enabled for Audio Conferencing. However, you can limit the number of emails sent to users. Audio Conferencing in Microsoft 365 or Office 365 sends emails to your users when:

- **An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**

    This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Teams Meeting Update Tool. The Teams Meeting Update Tool is used to update existing meetings for the user. For details, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).

    Note

    If your organization uses dynamic conference IDs, your users' meetings have unique conference IDs. Check out the [View and reset a conference ID assigned to a user in Microsoft Teams](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams) article for more information.

    Here's an example of this email:

    ![Teams Verify License.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing).
- **The conference ID or default conference phone number of a user changes.**

    This email contains the conference ID, default conference phone number, and the instructions and link to use the Teams Meeting Update Tool. The Teams Meeting Update tool is used to update existing meetings for the user. This email doesn't include the user's audio conferencing PIN. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams).

    Here's an example of this email:

    ![Dial-in conferencing info has changed.](media/teams-emails-sent-to-users-when-settings-change-image2.png)
- **The audio conferencing PIN of a user is reset.**

    This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user. See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams).

    Here's an example of this email:

    ![Dial-in conferencing PIN changed.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
- **A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**

    This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.

    See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Here's an example of this email:

    ![Dial-in conferencing is turned off.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Manage emails

You can make changes to the email that is automatically sent to users. By default, the sender of the emails is from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell. For more information, see [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams).

## Turn off emails

When you turn off sending emails to users, emails aren't sent even when a user gets assigned a license. In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN isn't sent to the user. When this happens, you must personally inform your users.

By default, emails are sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.

### Using the Microsoft Teams admin center

1. In the left navigation, go to **Meetings** &gt; **Conference Bridges**.
2. At the top of the **Conference Bridges** page, select **Bridge settings**.
3. In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.
4. Select **Save**.

### Using Windows PowerShell

You can also use the Microsoft Teams PowerShell module and run:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $False
```

You can use the [Set-CsOnlineDialInConferencingTenantSettings](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.

For more information, see the [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams/).

## Want to know more about Windows PowerShell?

By default, the sender of the emails is from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

- [Why you need to use Office 365 PowerShell](/en-us/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
- [Best ways to manage Office 365 with Windows PowerShell](/en-us/previous-versions//dn568025%28v=technet.10%29)

For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams).