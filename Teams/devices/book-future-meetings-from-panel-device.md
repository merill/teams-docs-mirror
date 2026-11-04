---
layout: Conceptual
title: Book future meetings directly from Teams panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/book-future-meetings-from-panel-device
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: 'Describing the Microsoft Teams panels feature: Book future meetings directly from Teams panels, where users can now book future room reservations directly from the panel device. '
author: l-birenboim
ms.author: lbirenboim
ms.service: teams-powershell
ms.topic: article
ms.date: 2026-04-13T00:00:00.0000000Z
locale: en-us
document_id: 2ec46b35-2af0-77f2-0834-12c79fc4335f
document_version_independent_id: 2ec46b35-2af0-77f2-0834-12c79fc4335f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/book-future-meetings-from-panel-device.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/book-future-meetings-from-panel-device
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/book-future-meetings-from-panel-device.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f618064e-fb5d-0e9f-4fc4-329c63bfd4df
---

# Book future meetings directly from Teams panels - Microsoft Teams | Microsoft Learn

Applies to: Microsoft Teams

You can book future meetings directly from a Teams panel by browsing the room’s availability and reserving an open time slot. Teams panels show availability for upcoming hours through **midnight the next day**, making it easy to plan ahead without opening Outlook or Teams on another device.

When a reservation is created, a Teams meeting is automatically scheduled for the selected time. Users can also add a guest during booking to simplify coordination for ad‑hoc meetings.

App version needed for this feature: 1449/1.0.97.2026164101 or higher.

![Screenshot showing Teams panel home screen with room availability.](media/book-future-meetings-from-panel-device/panel-bookinfuture-01.jpg)

## Book a future reservation from a Teams panel

Teams panels display the room calendar and availability timeline. A **green bar** indicates that the room is available at that time.

To book a future meeting:

1. On the Teams panel home screen, review the availability timeline.
2. Tap the **chevron** next to an available time slot.
3. Select a **start time** and **end time**.
4. (Optional) Add a **guest**.
5. Tap **Reserve**.

After the reservation is completed, the room is booked for the selected time. If a guest is added, they receive a calendar invite, and a Teams meeting is created automatically.

![Screenshot showing Teams panel reservation dialog with time selection and Reserve button.](media/book-future-meetings-from-panel-device/panel-bookinfuture-02.jpg)

## Turn on future booking for Teams panels (IT admins)

Future meeting booking is **on by default**, but allowing a guest attendee for future bookings is **off by default** and must be enabled by an admin. These settings can be configured either on the device or centrally through the Teams Admin Center.

### Enable future booking on the device

On the Teams panel:

1. Open **Admin settings**.
2. Go to **Meetings**.
3. Turn on **Allow future reservations**.

### Enable future booking in Teams Admin Center

1. Sign in to the **Teams Admin Center**.
2. Go to **Teams devices** &gt; **Panels**.
3. Create a new **configuration profile** or edit an existing one.
4. Go to **Meeting settings**.
5. Turn on **Enable future reservations from device**.

### Configure guest entry settings

Once future booking is enabled, an additional setting becomes available to control guest entry during reservations:

- On-device: **Allow guest attendee**
- In TAC: **Enable guest name entry**

Admins can choose to:

- Turn this setting **on**, allowing users to add a guest name when making a future room reservation from the panel.
- Leave this setting **off**, preventing guest entry during panel-based reservations.

## Licensing requirements

This feature is available for Teams panels with the following licenses:

- **Teams Rooms Pro**
- **Teams Shared Space**

Ensure the panel is correctly signed in and licensed for the feature to appear.

## Frequently asked questions

Question: How far in advance can users book a room from a Teams panel?

**Answer:** Users can reserve available time slots from the current time through **midnight the next day**.

Question: Is a Teams meeting always created when a future reservation is made?

**Answer:** Yes. A Teams meeting is automatically created for every future reservation.

Question: Why don’t I see the option to book future meetings on my panel?

**Answer:** Verify that future booking is enabled either on the device or in Teams Admin Center, and that the panel has a supported license.

Question: What happens if a guest can't attend the meeting?

**Answer:** The guest can decline the meeting invitation from their own Teams calendar. The room reservation remains on the room calendar.

Question: What happens if the meeting is declined and no one uses the room?

**Answer:** The reservation remains on the room calendar for the scheduled time even if the meeting is declined by the guest attendee because the room is the organizer of the meeting so it will *not* be automatically released. See [Check-in and auto release on Microsoft Teams panels](/en-us/microsoftteams/devices/check-in-and-auto-release) for more information.