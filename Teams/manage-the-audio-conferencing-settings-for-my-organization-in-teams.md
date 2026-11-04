---
layout: Conceptual
title: Manage Audio Conferencing settings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-the-audio-conferencing-settings-for-my-organization-in-teams
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
ms.date: 2026-10-28T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-voice
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
description: See Microsoft Teams steps to assign a dial-in conferencing license to a user and many other dial-in conferencing settings.
locale: en-us
document_id: f7992544-c8a5-c58f-390f-b42061f68992
document_version_independent_id: 3054f911-36b6-3360-2290-02310688dc0a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-the-audio-conferencing-settings-for-my-organization-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-the-audio-conferencing-settings-for-my-organization-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-the-audio-conferencing-settings-for-my-organization-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: faca576c-610f-d75e-c766-12ba7d724f6b
---

# Manage Audio Conferencing settings - Microsoft Teams | Microsoft Learn

It might be easier for you to see all of the Audio Conferencing settings for Microsoft Teams in one place.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Assign an Audio Conferencing license

Note

You can't assign licenses using Teams. You must use the Microsoft 365 admin center. For details, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).

### To assign a license for a user

1. Sign in to Microsoft 365 with your work or school account.
2. In the left navigation of the **Microsoft 365 admin center**, go to **Users** &gt; **Active users**, and then select the user or users from the list of available users.

    Note

    If you're assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down &gt; choose one of the options or create your own view. Then select **Edit**, **Next** twice &gt; select the license &gt; select **Submit**.
3. In the Action pane under **Product licenses**, select **Edit**.
4. On the **Product Licenses** page, turn on **Audio Conferencing** and then select **Save**. For more on licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing).

    Note

    After you assign the license, Microsoft might not initially appear in the list as an Audio Conferencing provider. If this happens, either sign out of the admin center or press CTRL+F5 to refresh the browser window.

## Manage emails sent to Audio Conferencing users

### Manage using the Microsoft Teams admin center

1. In the left navigation, go to **Meetings** &gt; **Conference Bridges**.
2. At the top of the **Conference Bridges** page, select **Bridge settings**.
3. In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.
4. Select **Save**.

### Manage emails using Windows PowerShell

For more information, see [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams/).

## Reset a conference organizer's PIN

Each meeting that a user schedules gets assigned a unique conference ID. Although a conference ID is automatically created and assigned to a user, there might be times when a user loses or doesn't want to use their conference ID. You can set the ID to a specific number.

### Reset a conference organizer's PIN using the Microsoft Teams admin center

1. In the navigation pane, select **Users**, and then select the user from the list of available users.
2. Under **Audio Conferencing**, select **Reset PIN**, and then select **Reset**.

    Users receive an email with their PIN when they're set up for Audio Conferencing or when the PIN is reset. But if you turn off automatically sending emails, a PIN reset email isn't sent and you have to manually send the PIN to the user. The PIN is only shown once after the reset. Once the PIN is displayed after the reset, it isn't shown anymore on the user properties; instead, \*\*\*\*\* is shown.

    For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams).

## Send an email with Audio Conferencing information to a user

### Send an email using the Microsoft Teams admin center

1. In the navigation pane, select **Users**, and then select the user from the list of available users.
2. Under **Audio Conferencing**, select **Send conference info in email**.

    Note

    When you select Send conference info in email, the Audio Conferencing PIN isn't sent to the user.

For details, see [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams).

## Set the phone numbers included on invites

### Set invite phone numbers using the Microsoft Teams admin center

For details, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams).

You can also set phone numbers by adding them to the *TeamsAudioconferencingpolicy* and assigning the policy to your users. Toll and toll-free phone numbers added to the policy take precedence over the phone numbers set individually for users via the Audio Conferencing settings pane. If no phone numbers are added to the *Teamsaudioconferencingpolicy*, then the phone number set individually for users via the Audio Conferencing settings pane is displayed in Microsoft Teams meeting requests. [Audio Conferencing policy settings for toll and toll-free numbers](audio-conferencing-toll-free-numbers-policy) has more information.

## Choose Audio Conferencing bridge settings

### Set the meeting experience when callers join a meeting using the Microsoft Teams admin center

1. In the navigation pane, go to **Meetings** &gt; **Conference Bridges**.
2. Select **Bridge settings**.
3. In the **Bridge settings** pane, toggle **Meeting entry and exit notifications** on or off.

    This setting is on by default. If you turn off this option, users who already joined the meeting by default aren't notified when someone enters or leaves the meeting.
4. Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.

    If you choose **Names or phone numbers**, you can also choose to turn **Ask callers to record their name before joining the meeting** on or off.

    Note

    By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).
5. Select **Save**.

See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge).

### Set the PIN length for meetings

1. In the navigation pane, go to **Meetings** &gt; **Conference Bridges**.
2. Select **Bridge settings**.
3. In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then select **Save**.

    The PIN must be between 4 and 12 digits. The default is 5.

For details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge).

### Manage emails from being sent to users

1. In the left navigation, go to **Meetings** &gt; **Conference Bridges**.
2. At the top of the **Conference Bridges** page, select **Bridge settings**.
3. In the **Bridge settings** pane, toggle **Automatically send emails to users if their Audio Conferencing settings change** on or off.
4. Select **Save**.

    You can also send email to the user with the Audio Conferencing settings. Go to the user's Audio Conferencing properties and select **Send conference info in email**.

    If you do this, the email only includes the conference phone number, but the PIN isn't included.

For details, see [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams).

## See and set the primary (default) and secondary (alternate) languages on an Audio Conferencing bridge

### See primary and secondary languages using the Microsoft Teams admin center

1. In the navigation pane, go to **Meetings** &gt; **Conference Bridges**.
2. Select a phone number from the list and select **Edit**.
3. Choose the languages you want under **Default language** and **Alternate languages (optional)**.
4. Select **Save**.

See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams).

## See Audio Conferencing dial-in numbers using the Microsoft Teams admin center

1. In the navigation pane, go to **Meetings** &gt; **Conference Bridges**.
2. Select a phone number from the list and select **Edit**. Here you can:

    - View the phone numbers that are to be used for Audio Conferencing.
    - View the location, and the primary language that the Audio Conferencing auto attendant uses.

See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams).

## Setting Audio Conferencing dial-in numbers in PowerShell

You can set a user's Audio Conferencing toll and toll-free number in PowerShell.

1. Connect to the Microsoft Teams service.

    ```powershell
    PS C:\> Connect-MicrosoftTeams
    ```
2. Assign a toll number to a user (for example, assign the toll number +612 800 0000 to sarah@contoso.com).

    ```powershell
    PS C:\> Set-CsOnlineDialInConferencingUser sarah@contoso.com -ServiceNumber 6128000000
    ```
3. Optional: assign a toll-free number to a user (for example, assign the toll-free number +61 1800 000 000 to sarah@contoso.com).

    ```powershell
    PS C:\> Set-CsOnlineDialInConferencingUser sarah@contoso.com -ServiceNumber 61280001234
    ```

    Note

    You can only assign toll or toll-free numbers that are registered within your organization.

## Want to know more about Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

- [Why you need to use Microsoft 365 or Office 365 PowerShell](/en-us/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
- [Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/en-us/previous-versions//dn568025%28v=technet.10%29)

For more information about Windows PowerShell, see [Microsoft Teams PowerShell reference](/en-us/powershell/module/teams).