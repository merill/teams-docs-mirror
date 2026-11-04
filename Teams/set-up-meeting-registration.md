---
layout: Conceptual
title: Set up Meeting Registration in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-meeting-registration
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: sherimehmood
ms.date: 2024-07-15T00:00:00.0000000Z
ms.topic: install-set-up-deploy
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
description: Learn how to set up and manage meeting registration policies in Teams.
locale: en-us
document_id: 14401145-626a-919b-0d43-8ff5d0ace624
document_version_independent_id: 14401145-626a-919b-0d43-8ff5d0ace624
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-meeting-registration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-meeting-registration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-meeting-registration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 38742863-5b3d-790e-2189-2bc37dd48c04
---

# Set up Meeting Registration in Microsoft Teams - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Events

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

Note

While meetings with registration are no longer supported, you and your users can use events. To learn more about setting up events for your org, see [Plan for Teams events](plan-events). Meetings with registration that were previously scheduled, or created with Graph API are still supported until December 31st, 2024.

This article describes how you, as an admin, can set up and manage meeting registration for your end users in Microsoft Teams meetings.

A meeting is a collaborative virtual meeting where organizers can require participants to register. During meetings, participants can discuss and share information with each other. These meetings can accommodate up to 20k participants. Meetings can include an attendance report and require registration from attendees. However, meeting registration has limited branding and event page configuration. Events, on the other hand, allow organizers to include custom branding, and use extra registration settings, management features, and more. For information, see [Plan for Teams events](plan-events).

Read more about the meeting registration experience for your end users in [Schedule a Teams meeting with registration](https://support.microsoft.com/office/schedule-a-teams-meeting-with-registration-435b2b67-c1bd-411e-9be6-9ed1b4a9f04a)

Note

Meeting registration isn't available for Microsoft 365 GCC High or Microsoft 365 DoD.

## Prerequisites

Before setting up meeting registration in Teams meetings, check to make sure you have the following items:

- The **Private meeting scheduling** setting must be on for meeting registration to work. To read more on private meeting scheduling, see [Configure private meeting scheduling](manage-who-can-schedule-meetings#private-meetings). For students in education tenants, the private meeting scheduling policy is turned off by default. For more information on how to enable private meeting scheduling for students, see [Teams for Education policies and policy packages](policy-packages-edu).

## Set up and manage meeting registration

You can use the Teams admin center or PowerShell to create and manage meeting registration.

### Using the Teams admin center

To set up meeting registration for users in your organization, you can use the Teams admin center.

#### Turn meeting registration on or off

Follow these steps in the Teams admin center to turn meeting registration on or off:

1. Open the Teams admin center.
2. Select **Meetings** from the navigation pane.
3. Under **Meetings**, select **Meeting Policies**.
4. Either select an existing policy or create a new one.
5. Within your chosen policy, navigate to the **Meeting scheduling** section.
6. Turn **Meeting Registration** setting **On** or **Off**.
7. Select **Save**

### Using PowerShell

You can also use PowerShell to set up meeting registration for users in your organization.

To set up meeting registration, use the "**`-AllowMeetingRegistration`**" parameter within the PowerShell **CsTeamsMeetingPolicy** cmdlet.

The following table shows the behaviors of the settings for **`-AllowMeetingRegistration`**:

| Setting value | Behavior |
| --- | --- |
| True | Users with this policy can require registration for their meetings. |
| False | Users with this policy can't require registration for their meetings. |

Before you can run the following cmdlets, you must be connected to Microsoft Teams PowerShell. For more information, see [Manage Teams with Microsoft Teams PowerShell](/en-us/microsoftteams/teams-powershell-managing-teams).

#### Turn on meeting registration in PowerShell

Turn on meeting registration for an existing policy, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
```

#### Turn off meeting registration in PowerShell

Turn off meeting registration, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False 
```

## Who can register for meetings

**Who can register** is set to **Everyone** by default, but in education tenants, the default setting is **People in my organization**. Once you turn on meeting registration, you can use the Teams admin center or PowerShell to manage the types of users organizers can require to register for meetings.

You could use the following steps to manage who can register in the Teams admin center:

1. Navigate to the Teams admin center and go to **Meetings** &gt; **Meeting Policies**
2. Either select an existing policy or create a new one
3. Within your chosen policy, navigate to the **Meeting scheduling** section
4. Select your desired behavior under the **"Who can register"** dropdown from the options of **Everyone** or **People in my organization**
5. Select **Save**.

Or, you could use the following PowerShell scripts to manage who can register for meetings:

- To allow only users in your organization to register for meetings:

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -WhoCanRegister EveryoneInCompany
    ```
- Allow everyone, including anonymous users, to register for meetings:

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -WhoCanRegister Everyone
    ```

Important

If **Anonymous users can join a meeting** is turned off, anonymous users can't join meetings. To learn more and enable this setting, see [Manage anonymous participant access to Teams meetings](anonymous-users-in-meetings).

For more information, on **Who can register** for education tenants, see [Teams for Education Policy Wizard](easy-policy-setup-edu).