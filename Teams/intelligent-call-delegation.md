---
layout: Conceptual
title: Manage intelligent call delegation in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/intelligent-call-delegation
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: nijait
ms.date: 2026-11-17T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
audience: admin
f1.keywords:
- NOCSH
- System.Collections.Generic.Dictionary`2[System.String,System.Object]
description: Learn how to manage intelligent call delegation for users in your organization using Teams personal attendant policies.
locale: en-us
document_id: 8f2b039c-ee67-f2e8-daaf-357f56e8ffa1
document_version_independent_id: 8f2b039c-ee67-f2e8-daaf-357f56e8ffa1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/intelligent-call-delegation.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: intelligent-call-delegation
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/intelligent-call-delegation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: d2198986-f4ec-0717-be80-08c8edafeefe
---

# Manage intelligent call delegation in Microsoft Teams - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Events ![Image of a checkmark for Yes](/en-us/office/media/icons/success-teams.png)Calls

Note

This feature is currently in public preview.

## Overview

Intelligent call delegation in Microsoft Teams is an AI-powered voice agent that helps users manage incoming calls. It answers calls on users' behalf, gathers context about the caller's intent, and takes action based on users' availability and settings. It can screen calls, route urgent calls to users, and schedule follow-up appointments through Microsoft Bookings.

As an admin, you use Teams personal attendant policies to control whether users in your organization can use intelligent call delegation, and which settings are available to them.

## Prerequisites

- Users must have a Microsoft Copilot license.
- Intelligent call delegation uses usage-based billing with Copilot Credits. Admins must [set up usage-based billing for Copilot Credits](/en-us/copilot/implement/usage-based-billing-copilot-credits-setup) and [create a spending policy](/en-us/copilot/implement/usage-based-billing-manage-copilot-credits) for intelligent call delegation in the Microsoft 365 admin center.

    Note

    When you create the spending policy, under **Agents and services**, ensure that only **Intelligent call delegation** is selected. Clear the checkboxes for all other services. When you select users and groups, choose the appropriate scope before assigning the policy.

## How intelligent call delegation works

When users turn on intelligent call delegation, the voice agent answers calls on their behalf. Depending on the user's settings, it can perform actions including:

- Screen incoming calls and collect the caller's reason for calling.
- Route urgent calls to the user and provide context about the call.
- Route suspected spam calls to voicemail when spam filtering is enabled.
- Schedule callbacks and follow-up meetings when the user is unavailable, including after the user returns from out of office.
- Notify the user when it answers or takes action on a call. Users can monitor calls through a live preview and join at any time.
- Provide a post-call summary in call history when available.

Callers are informed that they're speaking with an attendant rather than a person. When intelligent call delegation is turned on, it replaces the user's existing call routing settings. For more information about the user experience, see [Use intelligent call delegation in Microsoft Teams](https://support.microsoft.com/teams/copilot/use-copilot-call-delegation-in-microsoft-teams).

## Manage intelligent call delegation

You can use the Teams admin center or PowerShell to manage intelligent call delegation for your users. By default, intelligent call delegation is enabled in Teams personal attendant policy, and users with the policy can choose whether to turn it on or off in their Teams settings. Individual settings, such as call screening and scheduling follow-ups, are also enabled by default, and users can change them. Depending on the setting, users can turn it on or off or choose from available options.

### Use the Teams admin center

1. In the left navigation of the Teams admin center, go to **Voice** &gt; **Personal attendant policies**.
2. Select an existing policy or create a new one.
3. Under **General**, turn **Enable Personal Attendant** on or off.
4. If you turned on **Enable Personal Attendant**, configure the remaining policy settings under the following sections:

    - **Choose how Personal Attendant speaks**
    - **Choose which calls Personal Attendant answers**
    - **Choose what Personal Attendant can do**
    - **Manage recording and transcription**

    For more information about each policy setting, see the Policy settings table.
5. Select **Save**.

#### Policy settings

The following table describes personal attendant policy settings for intelligent call delegation in the Teams admin center.

| Policy setting | Description |
| --- | --- |
| **Choose how Personal Attendant speaks** |  |
| User's preferred name | Specifies the name Personal Attendant uses when referring to the user. |
| Assistant voice | Specifies the voice callers hear when Personal Attendant answers calls. |
| Language | Specifies the language Personal Attendant uses to communicate with callers. |
| Conversation tone | Specifies the tone Personal Attendant uses when communicating with callers. |
| **Choose which calls Personal Attendant answers** |  |
| Internal Teams calls | Controls whether Personal Attendant answers calls from users in the same organization. |
| Federated Teams calls | Controls whether Personal Attendant answers calls from other organizations. |
| External PSTN calls | Controls whether Personal Attendant answers calls from the public telephone network. |
| **Choose what Personal Attendant can do** |  |
| Screen calls before connecting | Controls whether Personal Attendant screens calls and provides context before connecting. |
| Calendar integration | Controls whether Personal Attendant can access the user's personal Bookings calendar to check availability and schedule follow-ups. |
| Callbacks for people outside the user's contacts | Controls whether Personal Attendant uses calendar integration for callbacks to people outside the user's contacts. |
| **Manage recording and transcription** |  |
| Automatically save transcription | Controls whether transcripts are automatically saved for calls handled by Personal Attendant. |
| Automatically save recording | Controls whether recordings are automatically saved for calls handled by Personal Attendant. |

### Use PowerShell

Use the following PowerShell cmdlets to create, manage, and assign personal attendant policies:

- [New-CsTeamsPersonalAttendantPolicy](/en-us/powershell/module/microsoftteams/new-csteamspersonalattendantpolicy)
- [Set-CsTeamsPersonalAttendantPolicy](/en-us/powershell/module/microsoftteams/set-csteamspersonalattendantpolicy)
- [Get-CsTeamsPersonalAttendantPolicy](/en-us/powershell/module/microsoftteams/get-csteamspersonalattendantpolicy)
- [Grant-CsTeamsPersonalAttendantPolicy](/en-us/powershell/module/microsoftteams/grant-csteamspersonalattendantpolicy)
- [Remove-CsTeamsPersonalAttendantPolicy](/en-us/powershell/module/microsoftteams/remove-csteamspersonalattendantpolicy)

Example:

The following command creates a new policy named SalesPersonalAttendantPolicy with calendar integration for scheduling follow-ups disabled.

```powershell
New-CsTeamsPersonalAttendantPolicy -Identity SalesPersonalAttendantPolicy -CalendarBookings Disabled
```