---
layout: Conceptual
title: Manage the Bookings app in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/bookings-app-admin
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: ITPro
ms.topic: article
ms.service: bookings
search.appverid: 
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
- teams-1p-app-admin
- highpri
- m365initiative-meetings
ms.reviewer: pritikar
ms.date: 2024-04-01T00:00:00.0000000Z
description: Learn how to manage the Bookings app in Teams for users in your organization.
locale: en-us
document_id: c1cf44b6-0499-9a1f-aa73-48e777fbe4a0
document_version_independent_id: b9af859f-9ff2-8975-b900-33fc8c087cae
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/bookings-app-admin.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: bookings-app-admin
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/bookings-app-admin.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9e0197e8-5fe3-1638-9a98-31d7109237e5
---

# Manage the Bookings app in Microsoft Teams - Microsoft Teams | Microsoft Learn

## Overview of Bookings

The Bookings app in Microsoft Teams offers a simple way to organize schedules and manage appointments.

Customize appointment types and details, booking requirements, and manage staff schedules and availability to streamline the booking experience. Bookings is integrated with your and your staff’s Microsoft 365 calendar to help your customers and clients quickly find available times from the booking page.

You can create and manage multiple booking pages, each with their own unique setup, to fit the scheduling needs of your organization.

- [Personal bookings](/en-us/microsoft-365/bookings/bookings-overview#personal-bookings) let you manage your own appointment time slots. You can set and share your availability with your customers, clients, or coworkers. After you create a personal booking page, you can share the link with others, who can then see your availability and schedule a time when you're free.
- [Shared bookings](/en-us/microsoft-365/bookings/bookings-overview#shared-bookings) are booking pages that you create and manage for your team. They allow you to invite your team members so that your customers and clients can book time with you and your team.

Every appointment booked as an online meeting creates a meeting link that people can use to join and meet virtually in Teams.

To learn more, see [Microsoft Bookings](/en-us/microsoft-365/bookings/bookings-overview).

## Prerequisites to use the Bookings app in Teams

- The Exchange mailbox is in Exchange Online. On-premises Exchange Server mailboxes aren't supported.
- Microsoft Bookings is turned on for the organization.
- Users have an appropriate license. Microsoft Bookings is available in the following subscriptions:
    - Office 365: A3, A5, E1, E3, E5, F1, F3, G1, G3, and G5
    - Microsoft 365: A3, A5, E3, E5, F1, F3, Business Basic, Business Standard, Business Premium, Teams Essentials, Teams Premium
- All users of the Bookings app and all staff participating in meetings have a license that supports Teams meeting scheduling.

Note

Bookings app in Teams is not supported in GCC, GCC-H, DOD and sovereign clouds.

To add the Bookings app to Teams, go to **Apps**, and then search for [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b).

## Control access to Bookings within your organization

There are several ways to control who has access to the Bookings app and to specific features of the app. You can turn on or turn off Bookings for your organization or for individual users in the Microsoft 365 admin center. Alternatively, you can create a Bookings app policy to allow select users to create Bookings calendars. To learn more, see [Turn Microsoft Bookings on or off](/en-us/microsoft-365/bookings/turn-bookings-on-or-off).

You can also [create a Teams app setup policy to pin the Bookings app for select users](teams-app-setup-policies).

## Recommended meeting policy settings

To enable the best experience for Bookings, create a Teams meeting policy to automatically admit **People in my organization** and assign the policy to your staff. The policy allows staff to join the appointment automatically and enable the lobby experience for external attendees. To learn more, see [Control who can bypass the meeting lobby in Microsoft Teams](who-can-bypass-meeting-lobby).

For more information about meeting policies, see [Manage meeting and event policies in Teams](meeting-policies-overview).

## SMS text notifications

![Information icon](media/info.png)**This feature is now part of [Teams Premium](teams-add-on-licensing/licensing-enhance-teams).**

SMS text notifications are currently available in Canada, the United Kingdom, and the United States.

You can control whether SMS text notifications can be sent to external attendees for virtual appointments scheduled by your staff in your organization.

By default, this setting is on, and SMS text notifications are enabled for all booking pages in your organization. Keep in mind that Bookings admins and schedulers can later choose to turn off or turn on SMS notifications on an as-needed basis in scheduled appointment types and scheduled individual appointments.

To configure this setting, go to the Microsoft 365 admin center &gt; **Settings** &gt; **Org settings**, and then choose **Bookings**. Select or clear the **Allow Microsoft to send SMS text message notifications** check box.

Learn more about how to [configure SMS text notifications for your organization](/en-us/microsoft-365/bookings/turn-bookings-on-or-off). Use the [Teams SMS notifications usage report](/en-us/microsoft-365/frontline/sms-notifications-usage-report) to understand how your organization is using SMS notifications.

## Optional staff approvals setting

You can require staff to opt in before Bookings shares their schedule availability information and before others can schedule an appointment with them.

To enable this setting, go to the Microsoft 365 admin center &gt; **Settings** &gt; **Org settings**, and then choose **Bookings**. Select the **Require staff approvals** check box.

With this setting turned on, staff receive an email in which they're requested to approve membership to a booking page.

Learn more about [how to configure the staff approvals setting](/en-us/microsoft-365/bookings/turn-bookings-on-or-off).

## Changing your default domain when setting up a Bookings mailbox

When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used. However, the default domain might cause problems when sending meeting invites to external recipients. For example, your invite might get flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.

We recommend that you change the default domain before you create your Bookings mailbox. See [Domains FAQ](/en-us/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365).

If you need to change the default domain after creating your Bookings mailbox, use PowerShell.

```powershell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

To learn more, see [Set Mailbox](/en-us/powershell/module/exchange/mailboxes/set-mailbox).

Note

If you're using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.

## Give feedback or report an issue

To send us feedback or report an issue, select **Feedback**, choose an option, and then enter your feedback or details about the issue you're experiencing. When you're done, select **Submit**.