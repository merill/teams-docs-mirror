---
layout: Conceptual
title: Manage email communications for events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-email-communications
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
audience: admin
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: absri
ms.date: 2026-10-06T00:00:00.0000000Z
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Learn how to manage email communications for events in the Microsoft Teams admin center and through PowerShell.
locale: en-us
document_id: 578bacbc-93b1-6035-7fad-48a3114704e5
document_version_independent_id: 578bacbc-93b1-6035-7fad-48a3114704e5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-email-communications.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-email-communications
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-email-communications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d6d1bb1b-1a02-f3d1-b2ce-39c442149b1c
---

# Manage email communications for events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

## Overview

You can control whether event organizers and co-organizers can edit email templates for their events. With email templates, organizers and co-organizers can manage waitlists, remind attendees about events they registered for, and provide clear instructions for attendees before, during, and after the event.

You can also configure the domain used to send event emails. Using a verified custom domain helps improve sender recognition and deliverability, and provides a more consistent experience.

Important

Starting February 1, 2026, organizations using premium custom HTML templates for Teams events email notifications must [set up and verify their sending domain in Microsoft 365](/en-us/microsoft-365/admin/email/select-domain-to-use-for-email-from-microsoft-365-products). Without this setup, custom templates can't be used, and event emails must originate from an authenticated, customer-owned domain.

Organizers and co-organizers can edit the following email communication templates:

- Registration confirmation
- Pending approval
- Waitlisting
- Registration rejected
- Registration cancellation
- Event cancellation
- Date and time update
- Event reminder
- Event recording available

## Manage email communications for events

You can use the Teams admin center or PowerShell to manage whether organizers and co-organizers can edit email templates for their events.

| Teams admin center policy option | Parameter value in PowerShell | Behavior |
| --- | --- | --- |
| On | Enabled | **This is the default value.** Organizers and co-organizers can edit all email templates for their events. |
| Off | Disabled | Organizers and co-organizers can’t edit any email templates for their events. |

### Using the Teams admin center

To manage whether organizers and co-organizers can edit email templates for their events, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. Turn the **Customize event emails** toggle **On** or **Off**.
4. Select **Save**.

### Using PowerShell

Use the **`-AllowEmailEditing`** parameter in the [CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy) PowerShell cmdlet to control whether organizers and co-organizers can edit email templates.

The following example turns off **`-AllowEmailEditing`** so organizers and co-organizers can't edit email templates:

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowEmailEditing Disabled
```

To learn more about the **`-AllowEmailEditing`** parameter, see the following articles:

- [Set-CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy)
- [New-CsTeamsEventsPolicy](/en-us/powershell/module/teams/new-csteamseventspolicy)
- [Grant-CsTeamsEventsPolicy](/en-us/powershell/module/teams/grant-csteamseventspolicy)
- [Get-CsTeamsEventsPolicy](/en-us/powershell/module/teams/get-csteamseventspolicy)
- [Remove-CsTeamsEventsPolicy](/en-us/powershell/module/teams/remove-csteamseventspolicy)

## Set up a custom domain for event emails (recommended)

For a more professional and reliable communication experience, admins can configure Teams events email notifications to be sent from a verified custom domain instead of Microsoft default addresses. This helps:

- Improve sender recognition and branding for attendees.
- Increase email deliverability and reduce spam classification.
- Build greater trust for external audiences receiving invitations and updates.

While events can function without a custom domain, emails are sent from Microsoft-provided addresses that might be less recognizable to recipients. Using a custom domain ensures a more consistent and enterprise-ready experience, especially for large-scale or external events.

Admins can configure this setting in the Microsoft 365 admin center by selecting a verified domain for sending system notifications. For steps, see [Select the domain to use for email from Microsoft 365 products](/en-us/microsoft-365/admin/email/select-domain-to-use-for-email-from-microsoft-365-products).

## Platform support

To view the list of platforms that support this feature, see [Platform support for Teams events features](events-platform-support).