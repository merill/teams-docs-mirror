---
layout: Conceptual
title: Set up the common area phones for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/set-up-common-area-phones
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
ms.date: 2026-08-11T00:00:00.0000000Z
ms.topic: install-set-up-deploy
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
- admindeeplinkMAC
- admindeeplinkTEAMS
description: Learn how to set up common area phones for lobbies, reception areas, and conference rooms.
locale: en-us
document_id: a25e36ac-58d7-4fda-c920-ccf1e2be6069
document_version_independent_id: a25e36ac-58d7-4fda-c920-ccf1e2be6069
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/set-up-common-area-phones.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/set-up-common-area-phones
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/set-up-common-area-phones.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ae8dc260-6cff-135c-b7b3-0ac575a4e684
---

# Set up the common area phones for Microsoft Teams - Microsoft Teams | Microsoft Learn

A common area phone is typically placed in an area like a lobby, reception area, or a conference room and is available to many people to make a call. Common area phones are not directly associated with an individual user and are instead signed in with common area phone resource account tied to a **Microsoft Teams Shared Space** license.

This article provides an overview of how to deploy and configure Teams phone devices as common area phones for shared spaces. For a more complete meeting room experience, including video, consider a dedicated **Teams Rooms** license with a Teams Rooms device instead. For more information about Teams Rooms, see [Microsoft Teams Rooms](../rooms/).

## Step 1 - Buy the licenses

First, you need to purchase a **Teams Shared Devices** license and make sure that you have a certified phone. To search for and learn more about certified Teams Phones, go to [Teams Phones certified hardware](../devices/teams-phones-certified-hardware?tabs=certified-phones).

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Billing** &gt; **Purchase services**.
2. If the **View by category** section isn't already displayed, go to **Purchase from Microsoft**, and select **View products**. Then select **Collaboration and communication**.
3. In the product list, find **Microsoft Teams Shared Devices**, and select **Details**.
4. Enter the number of licenses you need, and select **Buy**.

## Step 2 - Create a new common area phone resource account and assign licenses

Note

Teams has two distinct resource account types, those for Teams devices and those to support call queues and auto attendants. For information on resource accounts for Phone System call queues and auto attendants: [Click Here](/en-us/microsoftteams/manage-resource-accounts)

Important

Resource accounts for common area phone devices are created slightly differently than those for [Teams Rooms](/en-us/microsoftteams/rooms/create-resource-account?tabs=m365-admin-center%2Cgraph-powershell-password#create-resource-account--assign-the-license), this is intentional. Teams Rooms devices are created so they're bookable within Exchange as resource mailboxes unlike common area phones which do not need to be bookable in Exchange. This difference is most noticeable in that resource accounts for common area phones are created as standard user accounts with a unique license as compared to Teams Rooms resource accounts which are created as Exchange user objects with a unique license.

### Using the Microsoft 365 admin center

If you're deploying more than one common area phones at once, learn how to create accounts and assign licenses using PowerShell.

If you're deploying one device:

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Users** &gt; **Active Users** &gt; **Add a user**.
2. Enter a username like `Main` for the first name and `Reception` for the second name.
3. Enter a display name if it doesn't autogenerate one like `Main Reception`.
4. Enter a username like `MainReception` or `Mainlobby`.
5. Manually set the password for your common area phone. To set the password, uncheck **Automatically create a password** and **require this user to change their password when they first sign in**.

    Important

    Manually setting a password for common area phones is highly recommended to prevent sign-in issues for your end users.
6. Select the usage location of the device and assign the **Teams Shared Devices** license to the account. If any other licenses are needed, like Callings Plans, assign them.

Note

You don't need to add a license with Phone System features. It's included with the **Teams Shared Space** license. If you aren't using Microsoft Phone System with Direct Routing or Operator Connect, you may want to add **Calling Plans** licenses. For more information on licenses, see [Microsoft Teams add-on licensing](../teams-add-on-licensing/microsoft-teams-add-on-licensing).

### Using PowerShell

Use PowerShell when you want to create and assign licenses for more than one user account at once. For more information, see [Create Microsoft 365 user accounts with PowerShell](/en-us/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&amp;preserve-view=true) and [Assign Microsoft 365 licenses to user accounts with PowerShell](/en-us/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&amp;preserve-view=true).

Note

Common area phones can be impacted by conditional access rules and other identity configurations, like user interactive Multi-Factor Authentication (MFA). For more information, see [Authentication best practices for Teams Phones](authentication-best-practices-phones).

## Step 3 - Set policies for common area phones

Use policies to control which features are available to users on common area phones.

### IP phone policies

The Teams IP Phone policy can only be modified if the account signing into the phone is licensed with something other than a **Teams Shared Devices** license. If licensed with a Microsoft 365 E3 or E5 subscription, or an Office 365 Enterprise E1, E3, or E5 subscription, you can modify the IP Phone policy. If you're using a **Teams Rooms** license on your common area phone account, it will only let you use `MeetingRoomSignIn` mode. `MeetingRoomSignIn` mode isn't available on most common area phones. For more information about supported overrides for the phone interface, see [Set Microsoft Teams Android devices user interface](/en-us/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection).

Using the Teams IP Phone policy, set the [SignInMode parameter](/en-us/powershell/module/teams/new-csteamsipphonepolicy#parameters) to `CommonAreaPhoneSignIn` to enable the common area phone experience on the Teams phone device.

To configure other parameters, consider creating an [IP phone policy](/en-us/powershell/module/teams/new-csteamsipphonepolicy). For example, if a common area phone is used in a public area, set an IP phone policy to restrict searching your organization's Global Address Book and block hot-desking. To learn more, see [Set Teams Android devices user interface](/en-us/microsoftteams/devices/Teams-Android-devices-user-interface).

### Calling policies

Use calling policies to enable private calls, using call forwarding, or simultaneous ring on common area phones. To learn more, see [Configure calling policies in Teams](../teams-calling-policy).

By default, call park isn't enabled for common area phones. You need to create a policy to enable it. To learn more, see [Call park and retrieve in Microsoft Teams](../call-park-and-retrieve).

Note

After you assign a policy, sign out of the phone and sign back in. It may take up to an hour for a policy assignment to take effect.

## Step 4 - Acquire and assign phone numbers

See [Manage telephone numbers for your organization](../manage-phone-numbers-landing-page) to learn how to acquire and assign phone numbers based on your PSTN connectivity option.

## Step 5 - Sign in to the Teams Phone

Once you create and configure a user account, you can sign into a phone. Depending on how many phones you're deploying, you have three sign-in options:

- Local sign-in.
- Sign in from another device.
- Sign in using the Teams admin center.

### Resource Accounts Sign in Test

Use this tool: [Teams phone sign in test](https://testconnectivity.microsoft.com/tests/TeamsPhoneDeviceSignIn/input) to test that your Teams phone common area resource account is configured for successful sign-on.

### Local sign-in

To sign in locally with a username and password:

1. Turn on the common area phone.
2. Select **Sign in on this device**.
3. Follow the sign-in directions on the device. Once signed in, the phone displays the common area phone user experience.

Note

If you are using a custom setup policy that unpins the calling app, the dial pad doesn't appear on the common area phone. For more information, about Teams setup policies, see [Manage app setup policies in Microsoft Teams](../teams-app-setup-policies).

### Sign in from another device

You can also sign into to a common area phone from another device using a code. When you sign in this way, you enter the username and password on another device, rather than on the phone itself. For more information, see [Remote sign in and sign out for Teams Phones](remote-sign-in-and-sign-out-phones).

1. On your common area phone, find the code displayed on the sign-in screen.
2. On another device, go to https://www.microsoft.com/devicelogin.
3. To complete signing in, enter the code and follow the instructions.

### Sign in using the Teams admin center

As an admin, you can remotely provision and sign into common area phones from the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851). This method is the most efficient sign-in method when you're deploying a large number of phones at once. See [Remote provisioning and sign in for Teams Android Phones](remote-provision-remote-login-phones) to learn more.

## Step 6 - Set up Advanced calling on common area phones (optional)

By default, the basic calling experience will be on the common area phone's home screen, but you can turn on an advanced calling experience.

The following advanced calling features are available for supported Teams phone device models with a **Teams Shared Devices** license and the latest Teams updates (minimum version: 1449/1.0.94.2022061702):

- [Call park and retrieve](../call-park-and-retrieve).
- [Cloud-based voicemail through Exchange Online Plan 2](../set-up-phone-system-voicemail).
    - To disable cloud-based voicemail, see [Voicemail user settings using PowerShell](/en-us/powershell/module/teams/set-csonlinevoicemailusersettings).
- [Call queues](../create-a-phone-system-call-queue).
- [Auto attendants](../create-a-phone-system-auto-attendant).
- [Group call pickup](../call-sharing-and-group-call-pickup).
- [Forwarding rules](../user-call-settings).

Note

Common area phones can't be added as an agent to a call queue that uses **presence-based routing**, because common area phone accounts don't reliably report presence. If you need to route calls to a common area phone through a call queue, use a routing method that doesn't rely on presence (for example, Attendant routing, Serial, Round robin, or Longest idle).

To use these advanced calling features on a supported Teams phone device model, you can turn on the **Advanced calling** toggle in the [Teams admin center](https://admin.teams.microsoft.com/) or on your Teams phone device that is signed into your Teams Shared Devices account. Once you turn on advanced calling home screen experience on the phone, the device will update.

Turning on advanced calling capabilities requires you to purchase hardware models that can support all required capabilities.

### Turn on Advanced calling in Teams admin center

1. Sign into the [Teams admin center](https://admin.teams.microsoft.com/dashboard) with a Microsoft 365 admin account.
2. From the left-side menu, navigate to **Teams devices** &gt; **Phones** &gt; and select the **Configuration profiles** tab.
3. From the list, select the configuration profile assigned to your common area phone.
4. Under the **Calling settings** section, find the **Advanced calling** toggle.
5. Turn on the toggle.
6. At the bottom of the page, select the **Save** button.

### Turn on Advanced calling from a Teams phone device

1. After signing into your Teams phone device, navigate to **Settings** &gt; **Device settings** &gt; **Admin only** &gt; **Calling**.
2. Find the **Advanced calling** toggle and turn it on.

## Step 7 - Set up Hotline/PLAR on common area phones (optional)

You can set up common area phones as hotline phones also known as PLAR (Private Line Auto Ringdown) phones. You can program this phone to autodial a preconfigured PSTN number or a directory contact when the phone handset is picked up.

### Turn on Hotline in the Teams admin center

1. Sign into the [Teams admin center](https://admin.teams.microsoft.com/dashboard) with a Microsoft 365 admin account.
2. From the left navigation, select **Teams devices**, select **Phones**, and then select the **Configuration profiles** tab.
3. From the list, select the configuration profile assigned to your common area phone.
4. Under the **Call settings** section, turn on the **Enable hotline** toggle and then select **Save**.

Note

Verify the Advanced Calling setting is disabled when you are enabling the hotline setting in Teams admin center. Also verify the Team app version on the Android phone is version 1449/1.0.94.2023082303 or later.

### Turn on Hotline from a Teams phone device

1. Sign into your Teams phone device and select **Settings** &gt; **Device settings** &gt; **Admin only** &gt; **Calling** &gt; **Hotline**.
2. Enter a contact or phone number to be autodialed.
3. Enter the display name you want to show on the phone's home screen.
4. Select **Save**.