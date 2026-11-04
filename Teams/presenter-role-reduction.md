---
layout: Conceptual
title: Limit presenter role permissions for your org - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/presenter-role-reduction
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: idilates
ms.date: 2025-04-30T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
description: Learn how to limit presenter role permissions and capabilities in your org for IT Admins in Microsoft Teams.
locale: en-us
document_id: a2ae65dd-9d39-7ce6-60b2-6a5029941fd5
document_version_independent_id: a2ae65dd-9d39-7ce6-60b2-6a5029941fd5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/presenter-role-reduction.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: presenter-role-reduction
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/presenter-role-reduction.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: efd486ad-31ad-c047-be26-af5389c6ff65
---

# Limit presenter role permissions for your org - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Events

In Microsoft Teams, presenters have responsibilities related to presenting, sharing content and collaborating within the meeting or event. Presenters can mute attendees, change roles within the meeting, manage the lobby, and more.

If a meeting organizer has **Who can present** set to **Everyone** in their meeting options, anyone who the meeting link joins the meeting as a presenter. When meeting organizers have **Who can present** set to **People in my organization** in their meeting options, anyone in their org with the meeting link joins the meeting as a presenter. These meeting option configurations can lead to attendees who are presenters by default having too many controls when they attend meetings. Event organizers select presenters when they create the invite, but they might want their presenters to focus on giving the presentation and engaging with attendees.

As an admin, you can limit presenter role permissions for your tenant. Limiting presenter role permissions only applies to personal accounts, excluding Meeting Teams Rooms.

For a complete table of the permissions presenters have when you restrict their role permissions, see the Presenter capabilities section in this article.

To learn more about the roles meeting organizers can assign, see [Roles in Microsoft Teams meetings](https://support.microsoft.com/office/roles-in-microsoft-teams-meetings-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

## Limit presenter role permissions using PowerShell

To limit presenter role permissions for your tenant, you must use the **`-LimitPresenterRolePermissions`** parameter within the [CsTeamsMeetingConfiguration](/en-us/powershell/module/skype/set-csteamsmeetingconfiguration) PowerShell cmdlet.

| Parameter value in PowerShell | Behavior |
| --- | --- |
| True | Presenter role capabilities are reduced in your tenant. Presenters can’t enable or disable attendees’ mics and cameras, change the roles of other participants, lower hands, or remove other participants from the meeting. |
| False | **This is the default value.** Presenters in this tenant can enable and disable attendee mics and cameras, change the roles of other participants, lower hands, and remove other participants from the meeting. |

To limit presenter role capabilities for tenants with this policy, use the following script:

```powershell
Set-CsTeamsMeetingConfiguration -Identity <policy name> -LimitPresenterRolePermissions  $true
```

## Presenter capabilities

Here’s a complete table of the permissions that presenters have when you restrict their role permissions:

| Capability | Without policy to limit presenter role permissions | With policy to limit presenter role permissions |
| --- | --- | --- |
| Change the roles of other participants | Yes | **No** |
| Disable attendee mics/cameras | Yes | **No** |
| Enable individual or all attendee mics/cameras | Yes | **No** |
| Lower hands | Yes | **No** |
| Remove participants | Yes | **No** |
| Mute other participants | Yes | **No** |
| Add or remove an app | Yes | Yes |
| Admit people from the lobby | Yes | Yes |
| Change app settings | Yes | Yes |
| Manage what attendees see ^1^ | Yes | Yes |
| Participate in meeting chat | Yes | Yes |
| Privately view a PowerPoint file shared by someone else | Yes | Yes |
| Share content | Yes | Yes |
| Speak and share video | Yes | Yes |
| Start or stop live transcription | Yes | Yes |
| Start or stop recording | Yes | Yes |
| Take control of someone else's PowerPoint presentation | Yes | Yes |
| Use an app | Yes | Yes |
| Attendance report | No | No |
| Change meeting options | No | No |
| Edit meeting details | No | No |
| Graph API Supported | No | No |
| Manage breakout rooms | No | No |
| Manage recording permissions | No | No |
| Reschedule or cancel the meeting | No | No |

^1^ When **Manage what attendees see** is enabled, presenters can still lower raised hands, and enable and disable attendees’ mics and cameras. You can enable **Manage what attendees see** through a meeting template or organizers can enable this option through their meeting options. To learn more about **Manage what attendees see**, see [Manage the meeting presentation experience for sensitive Teams meetings](manage-meeting-presentation-experience#manage-which-content-and-video-is-shared-with-attendees).