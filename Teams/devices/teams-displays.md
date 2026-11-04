---
layout: Conceptual
title: Microsoft Teams displays - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/teams-displays
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: eviegrimshaw
ms.date: 2025-02-28T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: This article provides an overview of and features supported by Microsoft Teams displays.
locale: en-us
document_id: 006adec0-78ea-ed8c-07c0-ecf811ef023c
document_version_independent_id: d7c830df-9964-c066-8686-8f9e359f5e96
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/teams-displays.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/teams-displays
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/teams-displays.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 112b734a-d367-e922-2ea7-43a3bff83dab
---

# Microsoft Teams displays - Microsoft Teams | Microsoft Learn

Important

End of support for the Teams display app is September 3, 2025. Microsoft will make commercially reasonable best efforts to maintain compatibility with the most recent version of the Teams app provided to manufacturers for a period of two (2) years from this date. See the [Microsoft Product and Services lifecycle](/en-us/lifecycle/products/) for details.

Microsoft Teams displays are a category of all-in-one dedicated Teams devices that feature an ambient touchscreen. This article provides an overview of Teams displays and can help you plan, deliver, and manage Teams displays in your organization.

Teams displays brings together your favorite Teams features–chat, meetings, calls, calendar, and files–into a single device. With Teams displays, users can use a microphone, camera, and speakers (or Bluetooth headset) for a reliable calling and meeting experience. Teams displays integrates with users' Windows PCs to bring a companion experience that allows for seamless cross-device interaction.

To learn more, check out [Get started with Teams displays](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## Features supported by Teams displays

In addition to the [features supported by Teams phones](phones-for-teams#features-supported-by-teams-phones), the following features are unique to Teams displays:

- **Dedicated displays for Teams** Users can access all core Teams features including chat, meetings, calls, teams and channels, files and more.
- **Ambient experience** Users can easily stay on top of their work with always-on and glanceable displays to see important activities and notifications without context-switching on their primary work device. Users can also personalize Teams displays by customizing the background through settings.
- **Leave a note on lock screen** Guests can choose to leave audio, video, and text notes, and users can check the notes left by guests and see who’s stopped by.
- **Virtual front desk experience on Teams-certified displays** Enables staff to greet and serve visitors or employees via video call on a Teams display. It can be used for virtual reception, helpdesk, and a variety of use cases across industries.

## Required licenses

Teams licenses can be purchased as part of [Microsoft 365 and Office 365 subscriptions](/en-us/office365/servicedescriptions/teams-service-description). To learn more about the required licenses to use Teams displays, see [Voice and video calling with Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

For more information about how to get Teams, check out [How do I get access to Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## Deploy Teams displays using Intune

To learn more about how to deploy Teams displays using Intune, see [Deploy Teams phones and Teams displays](phones-panels-deploy).

## Manage Teams displays in your organization

To manage your Teams display devices, in the left navigation of the Microsoft Teams admin center, go to **Teams displays**. From here, you can change the device configuration profile, manage updates, restart devices, add and remove device tags, and more. For more information, see [Manage your devices in Teams](device-management).

## Set up hot-desking on Teams displays

Hot desking allows people in your organization to reserve temporary workspaces in advance through Teams and Outlook, or from the device itself. When hot-desking is enabled, users sign into Teams displays with their Microsoft 365 credentials to access their meetings, chats, and files. When they sign out, all their personal information is removed from the device.

To get started, you'll need to acquire [Microsoft Teams Shared Device licenses](../teams-add-on-licensing/teams-shared-device-license) and create resource accounts for each Teams display. See [Create resource accounts for rooms and shared Teams devices](../rooms/create-resource-account) to create resource accounts.

After you create resource accounts, you can create and assign a policy to enable hot-desking. See [New-CsTeamsIPPhonePolicy](/en-us/powershell/module/teams/new-csteamsipphonepolicy) to learn more.

Important

Because Teams displays with hot-desking are used in shared workspaces by multiple people, Conditional Access rules and other identity configurations in your environment, like Multi-Factor Authentication, can impact these devices and cause sign-in issues. For guidance on securing shared devices, see [Authentication best practices for shared Teams Android devices](authentication-best-practices-for-android-devices).