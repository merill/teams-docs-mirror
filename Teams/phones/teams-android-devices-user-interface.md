---
layout: Conceptual
title: Set Microsoft Teams Android devices user interface - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/teams-android-devices-user-interface
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: prashibadkur
ms.date: 2025-02-28T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
ms.localizationpriority: medium
description: Learn how to set the user interface on Teams Android devices.
locale: en-us
document_id: 17782a76-3151-67ea-1a29-44613c1ab3f2
document_version_independent_id: 17782a76-3151-67ea-1a29-44613c1ab3f2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/teams-android-devices-user-interface.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/teams-android-devices-user-interface
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/teams-android-devices-user-interface.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b8f03cac-585e-3347-78eb-7e322d36c8f4
---

# Set Microsoft Teams Android devices user interface - Microsoft Teams | Microsoft Learn

Microsoft Teams Android devices can display a specific user interface based on the type of license assigned to the signed-in account. You can override this behavior and control which interface is shown. This article details how the default user interface is chosen and how you can change the interface using a Powershell policy.

There are three types of user interfaces on Teams Phone devices:

1. User
2. Common Area
3. Meeting

If you [assign a user license](/en-us/microsoftteams/user-access) to an account, like an E3 or an E5 license, the Teams device will display the default end-user interface which is fully featured for most user scenarios. However, if a device is performing a specific function, such as a common area phone or a meeting room, there are specific user interfaces for these usages.

Picking the correct interface is important, especially if you purchased a specialized device like a conference phone. For these scenarios, make sure to assign the appropriate license and configure the matching user interface (such as the Meeting interface) for the best experience.

The following three images show how the user interface changes based on the license assigned to the user account.

## End-user interface

The user account is assigned an E5 license. This is a user license, so the device shows the default end-user interface:

![User mode interface.](../media/teams-android-devices-usermode1.jpg)

## Common area interface

In this image, the user account has been assigned a [Microsoft Teams Shared Devices license](/en-us/microsoftteams/teams-add-on-licensing/teams-shared-device-license). Common area phones are primarily used for making and receiving phone calls. As such, the dial pad is shown on the display:

![Common area phone interface.](../media/teams-android-devices-cap1.jpg)

Optionally, you can enable [Advanced Calling](/en-us/microsoftteams/set-up-common-area-phones) interface or [Hotline (Private Line Auto Ringdown)](/en-us/microsoftteams/set-up-common-area-phones) interface on common area phones.

## Meeting interface

This image shows a user account with a [Microsoft Teams Rooms license](/en-us/MicrosoftTeams/rooms/rooms-licensing) assigned. Teams Rooms licenses are meant to be used in meeting rooms or shared spaces, so the user interface changes to make it easy to join a meeting by showing the calendar view:

![Meeting interface.](../media/teams-android-devices-meeting.jpg)

Important

There are other elements of the interface that change. For example, to prevent end-users from signing out of a common area phone or meeting room device, the "Sign out" option on these devices is moved to a part of the settings menu that requires administrator permissions to access.

## Override automatic user interface detection

In some cases, you may choose to assign a license to an account that doesn't match its intended use. For example, you may assign a user license to an account meant to sign in to Teams Rooms on Android. By default, you would see the end-user interface instead of the meeting room interface. To override the default interface, create a new [Teams IP Phone Policy](/en-us/powershell/module/teams/new-csteamsipphonepolicy) and apply to it to that account.

Note

The license assigned to the user account must have at least the same license entitlements as the desired user interface. The **Microsoft Teams Shared Devices** license only allows the common area phone user interface. The **Teams Rooms** license only allows meeting room interfaces. An E3 or E5 license supports all sign-in modes. Learn more about [deploying Teams Phone devices](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/how-to-deploy-teams-phone-devices/ba-p/3994979). The following is an example of how to override automatic license detection. In this example, assume that a meeting room resource account named conf-adams@contoso.com has been assigned an E3 license. When this account is signed-in, you want users to see the meeting room user interface.

### Create a new policy and assign to user

1. Start a remote Windows PowerShell session and connect to Microsoft Teams using the following cmdlet:

    ```Powershell
    Connect-MicrosoftTeams
    ```
2. Create a new Teams IP Phone policy and set the sign-in mode to "MeetingSignIn":

    ```Powershell
    New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'
    
    ```
3. You can now assign this new policy to the meeting room resource account:

    ```Powershell
    Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
    ```

After granting the policy to the meeting room resource account, you'll need to wait for the policy assignment to replicate. You'll also need to sign out of the device and sign back in.

## Impact on Microsoft Teams admin center

Microsoft Teams admin center allows you to manage Microsoft Teams devices. For more information on managing devices using Teams admin center, see [Manage your devices in Microsoft Teams](../devices/device-management).

Teams admin center provides the ability to manage Teams phones. Phones are filtered into one of three tabs based on their function: user phones, common area phones, and conference phone.

![Phones header in Teams admin center.](../media/teams-admin-center-phones-header.png)

As with the user interface detection, Teams phones are categorized based on the license assigned to the account signing in to the phone. For example, if an account that is assigned a **Microsoft Teams Shared Devices** license signs in to a phone, then that phone will be shown in both the default **All phones** section as well as in the **Common area phones** section.

If you would like a phone to appear in a different section, you can either assign a different license to the phone, or create and assign a Teams IP Phone policy as described above.