---
layout: Conceptual
title: Manage Attendee Capacity Pack add-on licenses for Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/attendee-capacity-pack-manage
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.reviewer: divyasrirk
ms.date: 2026-07-06T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.custom:
- Licensing
description: Learn how to assign and manage Attendee Capacity Pack add-on licenses for event organizers in your organization in the Teams admin center.
locale: en-us
document_id: 56e27776-4027-9e2e-83a4-c398f7ebe145
document_version_independent_id: 56e27776-4027-9e2e-83a4-c398f7ebe145
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/attendee-capacity-pack-manage.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: attendee-capacity-pack-manage
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/attendee-capacity-pack-manage.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a466b127-95ce-ac24-6be2-cdb3157cbf2f
---

# Manage Attendee Capacity Pack add-on licenses for Teams events - Microsoft Teams | Microsoft Learn

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

As an admin, you manage [Attendee Capacity Packs](teams-add-on-licensing/attendee-capacity-pack) for your event organizers on the Teams Events page of the Teams admin center. You can view your attendee pack inventory, assign and manage licenses, and view your event inventory to monitor how attendee packs are used across your organization.

## Overview

[Attendee Capacity Packs](teams-add-on-licensing/attendee-capacity-pack) are add-on licenses that increase attendee capacity for Teams events, enabling your event organizers to host larger events at scale. With an attendee pack, organizers can host events with capabilities to engage with audiences (including reactions, raise hand, polls, and Q&A), beyond the 3,000-attendee limit included with Teams Enterprise.

Attendee packs determine the maximum capacity an organizer can set for a Teams event, and come in a range of sizes. An organizer with an attendee pack can host an unlimited number of events for the duration of the license, with the maximum number of attendees per event that the pack allows.

Important

Each organizer can only be assigned one attendee pack at a time. An organization can purchase multiple packs of varying sizes and assign them to different organizers.

### Attendee pack sizes

| Pack size | Maximum number of attendees per event |
| --- | --- |
| 5K | 5,000 |
| 10K | 10,000 |
| 20K | 20,000 |
| 35K | 35,000 |
| 50K | 50,000 |
| 75K | 75,000 |
| 100K | 100,000 |

Note

Organizers with an active Teams Premium license purchased before April 1, 2026, can continue to host events for up to 100,000 attendees until their current Teams Premium term ends.

After April 1, 2026, when your Teams Premium term expires, events with capabilities to engage with audiences that have more than 3,000 attendees require an attendee pack sized to the desired attendee capacity. To avoid disruption to large events, plan to purchase the appropriate pack in advance.

## Prerequisites

Before you manage attendee packs in the Teams admin center, make sure the following prerequisites are met:

- Your organization purchased Attendee Capacity Pack add-on licenses.
- You must be assigned the Global Administrator role to access the License Management section and manage all licensing capabilities in the Teams admin center.

**Note**: Users assigned the Teams Administrator role can access the License Management section in read-only mode and cannot create, modify, or remove license assignments or settings.

## View your attendee pack inventory

To view your organization's attendee pack inventory:

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com).
2. In the left navigation, go to **Add-on Licenses** &gt; **Teams Events**.

    On the Teams Events page, you see your organization’s attendee pack inventory, including available attendee packs that you purchased and current assignments. If there are no active attendee packs in your organization, you see this page with a redirect to purchase attendee packs in the Microsoft 365 admin center.

    The attendee pack inventory shows the following information about your organization's attendee packs.

    | Column | Description |
    | --- | --- |
    | **Pack size** | Maximum number of attendees the pack supports per event. |
    | **Total licenses** | Total number of attendee pack licenses purchased for that size. |
    | **Assigned** | Number of packs currently assigned to organizers. |
    | **Available** | Number of unassigned packs available for assignment. |

## Assign an attendee pack to an organizer

To assign an attendee pack to an organizer:

1. In the Teams admin center, go to **Add-on Licenses** &gt; **Teams Events**.
2. On the **Licenses** tab, select **Assign to new users** to get started.

    [![Screenshot of the Assign new users option on the Licenses tab of the Teams Events page.](media/attendee-pack-assign-users.png)](media/attendee-pack-assign-users.png#lightbox)
3. In the **Assign Add-on licenses** pane:

    1. In the **Search for a user** field, search for and select the organizer or organizers you want to assign the pack to.
    2. For each individual user, select the pack size that you want to assign in the **Attendee pack** column.
    3. Or, select multiple users at once, and then choose the **Modify** drop-down option at the top of the table to assign a particular pack to the users you selected.

        [![Screenshot of the Assign Add-on licenses pane.](media/attendee-pack-assign-pane.png)](media/attendee-pack-assign-pane.png#lightbox)
4. Select **Apply**, and then confirm to apply the assignments.

The organizer or organizers with the assigned pack can schedule events up to the maximum attendee capacity of the pack.

## View assigned attendee packs

To see which organizers have attendee packs assigned to them:

1. In the Teams admin center, go to **Add-on Licenses** &gt; **Teams Events**.
2. If one or more organizers are assigned an attendee pack, you see a table that shows the following information.

    | Column | Description |
    | --- | --- |
    | **Display name** | Name of the organizer with an assigned attendee pack. |
    | **Username** | Email address or UPN of the organizer. |
    | **Assigned pack** | Size of the attendee pack assigned to the organizer. |
    | **Upcoming event date** | Date and time of the latest event scheduled by the organizer. |
    | **Location** | Usage location assigned to the organizer's profile. |

## Change or reassign an attendee pack

You can change the attendee pack that's assigned to an organizer. For example, you can assign a smaller or larger capacity pack to one or more organizers.

Note

An organizer can only be assigned one attendee pack at a time. Assigning a different pack to an organizer who is already assigned a pack replaces the existing assignment.

### Change the attendee pack for one organizer

1. In the Teams admin center, go to **Add-on Licenses** &gt; **Teams Events**.
2. On the **Licenses** tab, in the **Attendee pack** column of the table, select the drop-down in the user's row, and then choose the pack size that you want.
3. Select the pack, and then confirm to save the changes.

### Change the attendee pack for multiple organizers

1. In the Teams admin center, go to **Add-on Licenses** &gt; **Teams Events**.
2. On the **Licenses** tab, select multiple users, and then select the **Modify** drop-down option at the top of the table.
3. Select the pack size that you want to change to, save, and then confirm to apply the changes.

    [![Screenshot of the Modify drop-down option in the table.](media/attendee-pack-change.png)](media/attendee-pack-change.png#lightbox)

## Remove an attendee pack from an organizer

To unassign an attendee pack from an organizer:

1. In the Teams admin center, go to **Add-on Licenses** &gt; **Teams Events**.
2. On the **Licenses** tab, select the organizer in the table, and then select **Remove**.
3. In the confirmation dialog, select **Remove** to confirm.

The pack is returned to the available attendee pack inventory and can be reassigned to another organizer.

## View attendee pack usage and event inventory

On the **Usage reports** tab of the Teams Events page, you can monitor how attendee packs are used across your organization.

The event inventory view shows the following reports:

- Teams events reports
- Teams live events report