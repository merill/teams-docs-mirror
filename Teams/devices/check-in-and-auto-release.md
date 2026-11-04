---
layout: Conceptual
title: Check-in and auto release on Teams Panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/check-in-and-auto-release
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: altonk
ms.date: 2026-05-07T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-devices
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: This article provides guidance on how to enable check-in and auto release for Teams panels.
locale: en-us
document_id: df6391e0-0e71-301b-b61e-26a2084654e7
document_version_independent_id: df6391e0-0e71-301b-b61e-26a2084654e7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/check-in-and-auto-release.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/check-in-and-auto-release
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/check-in-and-auto-release.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 08c71f9d-8c3a-87ca-c670-832cbb3cc9f3
---

# Check-in and auto release on Teams Panels - Microsoft Teams | Microsoft Learn

When check-in and auto release are enabled, users must check in at the room they reserved at the start of the meeting. They can do so on Teams panels using the 'Check in' button, that appears ~20 minutes before the meeting start time or, when Teams panels are signed into the same resource account as Teams Rooms, they can do so by joining a meeting on Teams Room. If a user doesn't check in within a set amount of time after the meeting start time, the meeting room declines the meeting invite, sends a cancellation message to the meeting organizer, and the room becomes available for others to reserve.

This feature can be used in a standalone Teams panel deployment or on a Teams panel that is signed into the same resource account as Teams rooms. For rooms with multiple panels, auto release and check-in are supported if the panel devices are all on app version 1449/1.0.97.2024061108 or later. For more functionalities like check-in notifications, you can also pair Teams panels with Teams Rooms on Android with app version 1449/1.0.96.2022011305 or later.

The shared mailbox associated with the Teams panel needs to have the correct time zone set for this feature to work correctly. For information about how to set the time zone for shared mailboxes, see [Time zone settings for shared mailboxes in Outlook on the web](/en-us/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting).

For best practices when downloading app version 1449/1.0.97.2024061108, see our [release notes](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_panels).

Note

When the room is the organizer of the meeting (such as when the reservation was made on the panel device), the room doesn't auto release.

## Enable check-in and auto release

Check-in and auto release are off by default. To turn it on:

1. On the Teams panel, sign in using your admin credentials.
2. Go to **Settings &gt; Device settings &gt; Admin settings &gt; Teams admin settings &gt; Meetings**.
3. Turn on **Release room if no one checks in**.
4. To adjust the amount of time users have to check in before the room is released, go to **Release after:** and select an option from the dropdown.

In addition, you can use configuration profiles to apply this feature to a set of devices. For more information, see [Use configuration profiles in Teams](device-management#use-configuration-profiles-in-teams).

Note

For devices on app version 1449/1.0.97.2024061108 or later, when auto release is enabled, disabled, or adjusted for a room, it can take up to 48 hours for the change to take effect. For this reason, we recommend that the settings are adjusted when no meetings are scheduled for the next 48 hours. 

## Turn on check-in notifications

Note

This feature is currently only available on Teams panels that are paired with a Teams Room on Android. The Teams panel and Teams room must be signed into the same resource account. See **[Pair a Teams panel with a Microsoft Teams Room on Android](use-teams-panels)** to learn more.

Check-in notifications are sent when a meeting is continuing past its reserved time slot. Once a user from the next meeting checks in, the notification appears on the front of room display at their scheduled meeting start time to let the previous meeting participants know their reservation is over, and people are waiting for the space.

To turn on check-in notifications,

1. On the Teams panel, sign in using your admin credentials.
2. Go to **Settings &gt; Device settings &gt; Admin settings &gt; Teams admin settings &gt; Meetings**.
3. Go to **Check-in** and turn on **Send check-in notification**.

Note

When auto release is enabled, for a non-Teams meeting, such as an in-person or third-party meeting, the organizer receives an email prompting them to check in. *No* Teams message is sent because the meeting doesn't have a Teams chat.

### Frequently asked questions

**Question:** **Can I continue to use the check-in feature on Teams panels after Microsoft Places launches their auto release feature? Do they work together?**

**Answer:** Yes, you can! Microsoft Teams and Microsoft Places are working together to light up multiple ways for the user to reflect that they're using the room and prevent it from automatically releasing. For Places preview customers, a [new entry point](/en-us/microsoft-365/places/enable-auto-release?branch=main) is offered in addition to checking in through Teams panels or Teams Rooms.

**Question: I am using auto release today for rooms with only one panel. How does support for multi-panel check-in impact this?**

**Answer:** It doesn't. It's important to note though that once a panel device, regardless of set-up, is on app version 1449/1.0.97.2024061108 or later, any adjustment to the auto release setting can take up to 48 hours to take effect. In addition, read our [release notes](https://support.microsoft.com/en-us/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_panels) for best practices when downloading app version 1449/1.0.97.2024061108.

**Question: Are there any times when a user would be automatically checked in?**

**Answer:** Yes, there are. At this time, the user is automatically checked in if the room is the organizer of the meeting or if the room was invited after the meeting start time. We require check-in if it's a 3P meeting such as Zoom meeting or it's an in-person meeting as in there is no online Teams link. Please make sure devices are on Teams app 1449/1.0.97.2025031901 or later.

**Question: Does this feature support on-premises mailboxes?**

**Answer:** No, this feature is only available for room mailboxes created in Exchange Online after Teams app 1449/1.0.97.2024061108. To learn more about how to manage room mailboxes, see [Manage resource mailboxes in Exchange Online](/en-us/exchange/recipients-in-exchange-online/manage-resource-mailboxes).

**Question: Does 'Send check-in notification' in Teams Admin Settings and Teams Admin Center control whether a Teams chat or email to check-in is sent?**

**Answer:** No, this setting does not control [chat notifications](/en-us/microsoft-365/places/enable-auto-release?branch=main) or Teams meetings or email notification sent for in person and 3rd party meetings. This setting controls the banner(s) that appear on the front of room display. See 'Turn on check-in notifications' above for more information.