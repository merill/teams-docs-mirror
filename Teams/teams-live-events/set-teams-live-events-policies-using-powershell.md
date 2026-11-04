---
layout: Conceptual
title: Use PowerShell to set live events policies - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-live-events/set-teams-live-events-policies-using-powershell
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.date: 2026-06-11T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: christi.balaki,cmunden
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Examples of how to use PowerShell to set policies in Teams to control who can hold live events in your organization and the features available in the events.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 8cb395f1-fce4-2d64-c66e-36a6cd818ca6
document_version_independent_id: 79bf1d7e-8cbc-5146-dfda-a6ae38d49be7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-live-events/set-teams-live-events-policies-using-powershell.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-live-events/set-teams-live-events-policies-using-powershell
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-live-events/set-teams-live-events-policies-using-powershell.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: bc35c950-4790-2581-0eb4-31ee17682d0c
---

# Use PowerShell to set live events policies - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:

- [Get-CsTeamsMeetingBroadcastPolicy](/en-us/powershell/module/teams/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/en-us/powershell/module/teams/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/en-us/powershell/module/teams/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/en-us/powershell/module/teams/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/en-us/powershell/module/teams/new-csgrouppolicyassignment)

Note

Before you can run these cmdlets, you must install the Microsoft Teams PowerShell module and run `Connect-MicrosoftTeams` to connect to Teams. To learn more, see [Install Microsoft Teams PowerShell Module](../teams-powershell-install).

The following sections provide user scenarios for various PowerShell commands used to manage events produced in Teams:

Note

These examples are for events produced in Teams.

## Allow a user to schedule live events

1. If the user is assigned the global policy, run the following script and verify that the **`-AllowBroadcastScheduling`** parameter is set to *True*:

    ```PowerShell
    Get-CsTeamsMeetingBroadcastPolicy -identity Global
    ```
2. Next, to assign the user to the global policy, run the following script:

    ```PowerShell
    Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
    ```

## You want all users in your organization to be able to schedule live events

If users are assigned the global policy, run and verify that **`-AllowBroadcastScheduling`** is set to *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

If users are assigned a policy other than the global policy, run and verify that **`-AllowBroadcastScheduling`** is set to *True*:

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

## You want to turn off live events scheduling for your organization

To turn off live events scheduling, run the following script:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

To assign all users in your organization to the global policy, run the following script:

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

## You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them

### 1. Allow a large number of users to schedule live events

1. Run the following script to verify that \*\*`-AllowBroadcastScheduling`\*\*is set to *True*:

    ```PowerShell
    Get-CsTeamsMeetingBroadcastPolicy -Identity Global
    ```
2. Next, to assign a user or users to the global policy, run the following script:

    ```PowerShell
    Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
    ```

### 2. Create a new policy that doesn't allow specific users to schedule live events

1. To create a new policy that doesn't allow specific users to schedule live events, run the following script:

    ```PowerShell
    New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
    ```
2. To turn off live events scheduling, run the following script:

    ```PowerShell
    Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
    ```
3. To assign users to this policy, run the following script

    ```PowerShell
    Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
    ```

## You want to turn off live event scheduling for a large number of the users and allow a set of users to schedule them

### 1. Turn off live events scheduling for a large number of users

1. To disable live events scheduling, run the following script:

    ```PowerShell
    Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
    ```
2. To assign those users to the global policy, run the following script:

    ```PowerShell
    Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
    ```

### 2. Create a new policy that allows specific users to schedule live events

1. To create a policy to allow live events scheduling, run the following script:

    ```PowerShell
    New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingPolicy
    ```
2. To turn on live events scheduling, run the following script:

    ```PowerShell
    Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingPolicy -AllowBroadcastScheduling $true
    ```
3. To assign users to this policy, run the following script:

    ```PowerShell
    Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingPolicy -Verbose
    ```

## Set who can join live events

To set the global policy to allow users to create events that everyone, including anonymous users, can attend, run the following script:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```

## Set the recording option for live events

Note

This setting applies only to events produced in Teams.

To set the global policy to disable recording for live events, run the following script:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```

## Set live captions and subtitles in live events

Note

This setting applies only to events produced in Teams.

To set the global policy to turn on live captions and subtitles (transcription) for event attendees, run the following script:

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### Related articles

- [Set up for Teams live events](set-up-for-teams-live-events)
- [Teams PowerShell overview](../teams-powershell-overview)