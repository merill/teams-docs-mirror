---
layout: Conceptual
title: Manage who can schedule and attend events in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.reviewer: chbalaki
ms.date: 2026-10-07T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
description: Learn how to manage who can schedule and attend Teams events in your organization.
locale: en-us
document_id: f34ef3f6-1e6e-aec1-bbee-629b33bccc5a
document_version_independent_id: f34ef3f6-1e6e-aec1-bbee-629b33bccc5a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: 0a48bc2c-4214-f266-c53e-c91ee1387b8d
---

# Manage who can schedule and attend events in Microsoft Teams - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of an x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

## Overview

This article describes how you, as an admin, can manage which users can create and attend events in your organization.

To learn more about how to plan for Teams events, see [Plan for Teams events](plan-events). For which features are available by license (including Teams Premium) and by event size, and for attendee capacity limits, see [Meetings and events feature and capacity comparison](/en-us/microsoftteams/meetings-events-feature-comparison).

## Manage who can schedule events

Use the Teams admin center or PowerShell to manage who can schedule and run events in your organization. The following table lists the Teams events policy settings that control this behavior.

| Teams admin center setting and value | PowerShell parameter and value | More information |
| --- | --- | --- |
| **Webinars** (On,Off) | `-AllowWebinars` (Enabled,Disabled) | Controls whether users with this policy can create events with up to 1,000 attendees, such as webinars. |
| **Town halls** (On,Off) | `-AllowTownhalls` (Enabled,Disabled) | Controls whether users with this policy can create events optimized for large audiences, such as town halls. |

The combination of these policy settings determine how the **[Optimize for large audience](plan-events)** option is applied in the scheduling form.

| Webinars | Town halls | Optimize for large audience behavior | Organizer capabilities |
| --- | --- | --- | --- |
| **On**/`Enabled`(Default) | **On**/`Enabled`(Default) | - For events with *up to* 1,000 attendees, **Optimize for large audience** is off, and organizers can turn it on.<br>- For events with *more than* 1,000 attendees, **Optimize for large audience** is on and can't be turned off. | - Create events with up to 1,000 attendees.<br>- Create events optimized for large audiences. |
| **Off**/`Disabled` | **On**/`Enabled` | **Optimize for large audience** is on and can't be turned off. | - Create events optimized for large audiences.<br>- Create view-only events with up to 10,000 attendees (with Q&A). |
| **On**/`Enabled` | **Off**/`Disabled` | **Optimize for large audience** is off and can't be turned on. | Create events with up to 1,000 attendees. |

### Use the Teams admin center to manage who can schedule events

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. Complete the following steps:
    - For events with up to 1,000 attendees, such as webinars, turn the **Webinars** toggle **On** or **Off**.
    - For events [optimized for large audiences](plan-events), such as town halls, turn the **Town halls** toggle **On** or **Off**.
4. Select **Save**.

If you change the value to **Off** after a user schedules an event, they can't run or start the event.

### Use PowerShell to manage who can schedule events

To manage who can schedule events, use the following parameters within the [**CsTeamsEventsPolicy**](/en-us/powershell/module/teams/set-csteamseventspolicy) PowerShell cmdlet:

- For events with up to 1,000 attendees, such as webinars, use the **`-AllowWebinars`** parameter.
- For events [optimized for large audiences](plan-events), such as town halls, use the **`-AllowTownhalls`** parameter.

#### Events up to 1,000 attendees

To prevent organizers with this policy from creating events with up to 1,000 attendees, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

To allow organizers with this policy to create events with up to 1,000 attendees, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
```

#### Events optimized for large audiences

To prevent organizers with this policy from creating events optimized for large audiences, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowTownhalls Disabled
```

To allow organizers with this policy to create events optimized for large audiences, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowTownhalls Enabled
```

## Manage who can attend events

Use the Teams admin center or PowerShell to manage who can attend events in your organization. The following table lists the Teams events policy settings that control this behavior.

| Teams admin center setting and value | PowerShell parameter and value | More information |
| --- | --- | --- |
| **Who can attend webinars**(Everyone,Everyone in my organization excluding guests,Everyone in my organization including guests) | `-EventAccessType`(Everyone,EveryoneInCompanyExcludingGuests,EveryoneInCompany) | Controls who can attend events with up to 1,000 attendees (such as webinars) created by organizers with this policy. |
| **Who can attend town halls**(Everyone,Everyone in my organization excluding guests,Everyone in my organization including guests) | `-TownhallEventAttendeeAccess`(Everyone,EveryoneInOrganization,EveryoneInOrganizationAndGuests) | Controls who can attend events optimized for large audiences (such as town halls) created by organizers with this policy. |

By default, both settings are set to **Everyone**. When users with this policy create events with up to 1,000 attendees or events optimized for large audiences, any user can attend.

### Use the Teams admin center to manage who can attend events

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. Complete the following steps:
    1. For events with up to 1,000 attendees, such as webinars, in the **Who can attend webinars**dropdown list, select one of the following:
        - **Everyone**
        - **Everyone in my organization excluding guests**
        - **Everyone in my organization including guests**
    2. For events [optimized for large audiences](plan-events), such as town halls, in the **Who can attend town halls**dropdown list, select one of the following:
        - **Everyone**
        - **Everyone in my organization excluding guests**
        - **Everyone in my organization including guests**
4. Select **Save**.

### Use PowerShell to manage who can attend events

To manage who can attend events, use the following parameters within the [**CsTeamsEventsPolicy**](/en-us/powershell/module/teams/set-csteamseventspolicy) PowerShell cmdlet:

- For events with up to 1,000 attendees, such as webinars, use the **`-EventAccessType`** parameter.
- For events [optimized for large audiences](plan-events), such as town halls, use the **`-TownhallEventAttendeeAccess`** parameter.

#### Events up to 1,000 attendees

##### Turn off public events

To only allow users in your organization to attend events with up to 1,000 attendees created by organizers with this policy, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
```

##### Turn on public events

To allow any user to attend events with up to 1,000 attendees created by organizers with this policy, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
```

#### Events optimized for large audiences

##### Turn off public events

To only allow users in your organization and guests to attend events optimized for large audiences created by organizers with this policy, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -TownhallEventAttendeeAccess EveryoneInOrganizationAndGuests
```

##### Turn on public events

To allow any user to attend events optimized for large audiences created by organizers with this policy, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -TownhallEventAttendeeAccess Everyone
```