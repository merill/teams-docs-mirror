---
layout: Conceptual
title: Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-end-to-end-encryption
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.date: 2026-08-28T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: willdixon
description: Learn how to manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls in your organization.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- purview-compliance
- trust-pod
ms.custom:
- Security
locale: en-us
document_id: b601b72a-bcaa-2afd-22f7-8123856d2a97
document_version_independent_id: b601b72a-bcaa-2afd-22f7-8123856d2a97
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-end-to-end-encryption.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-end-to-end-encryption
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-end-to-end-encryption.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 90fcbe66-852c-4efd-2cc3-e4618b685f52
---

# Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls - Microsoft Teams | Microsoft Learn

This article describes how to enable and manage end-to-end encryption (E2EE) for Teams meetings and one-to-one calls.

You can manage E2EE using enhanced encryption policies in the Teams admin center or PowerShell. E2EE for meetings and one-to-one calls is configured through separate settings within the same policy.

For an overview of how encryption works in Teams, including the standard encryption that applies by default, see [Encryption in Microsoft Teams](teams-encryption).

## Prerequisites

- A work or school account assigned to the Teams administrator or Global administrator role.

    Important

    Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role. To learn more, see [About administrator roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles).
- A Teams Premium license for meeting organizers who schedule end-to-end encrypted meetings. Teams Premium isn't required for one-to-one call encryption.
- A supported client or device. See Platform and device support later in this article.

## Features that become unavailable when end-to-end encryption is enabled

Because the service can't decrypt media, some features that depend on service-side access aren't available.

The following table lists features that become unavailable during end-to-end encrypted meetings and one-to-one calls.

| Feature | Calls | Meetings |
| --- | --- | --- |
| Live captions and transcription | X | X |
| Recording | X | X |
| Compliance recording (a user subject to it can't use E2EE)^1^ | X | X |
| Real-Time Text (RTT) | X | X |
| Call transfer | X | Not applicable |
| Call merge | X | Not applicable |
| Call park | X | Not applicable |
| Consult then transfer | X | Not applicable |
| Call companion/Transfer to another device | X | Not applicable |
| Adding a participant | X | Not applicable |
| Apps | X | Apps can't access media streams in end-to-end encrypted meetings but might be able to access meeting chat. |
| Breakout rooms | Not applicable | X |
| Excel Live | Not applicable | X |
| PowerPoint Live | Not applicable | X |
| Request control of shared content | Not applicable | X |
| Companion mode/Large gallery | Not applicable | X |
| People dialing by phone (PSTN) | Not applicable | X |
| Microsoft 365 Copilot in meetings and events | Not applicable | X |

^1^If a user is subject to compliance recording, they can't use E2EE for meetings or one-to-one calls because recording requires access to the content that E2EE protects.

Consider user education as part of your E2EE deployment. Users who are permitted to use E2EE might assume they should enable it for all calls and meetings without realizing that some Teams features, such as recording and live captions, become unavailable when E2EE is enabled. Educate users about when to use E2EE to help reduce support requests.

## Manage end-to-end encryption for one-to-one calls in the Teams admin center

For one-to-one calls, E2EE is disabled by default in the Global (Org-wide default) enhanced encryption policy.

Users in your organization automatically get the Global (Org-wide default) policy unless you create and assign a custom policy. You can update the Global (Org-wide default) policy or create custom policies, as needed.

To manage who can make calls with E2EE:

1. Sign in to the Teams admin center as a Teams administrator or Global administrator.
2. In the left navigation, go to **Enhanced encryption policies**.
3. Select the policy you want to update, or choose **Add** to create a new policy and then name it.
4. Next to **End-to-end call encryption**, choose **Not enabled, but users can enable** or **Not enabled**.
5. Select **Save**.
6. [Assign the policy](policy-assignment-overview) to users, groups, or your entire tenant the same way you manage other Teams policies.

Note

Users must [turn on end-to-end encrypted calling](https://support.microsoft.com/teams/calls-devices/use-end-to-end-encryption-for-microsoft-teams-calls) in their Teams settings before they can make an end-to-end encrypted call. Users only need to do this one time on a supported device because Teams synchronizes the setting across supported endpoints.

### Verify an end-to-end encrypted call

During an end-to-end encrypted call, Teams shows a 20-digit security code to both participants. Teams derives the code from the SHA-256 thumbprints of the caller's and callee's endpoint call certificates. The caller and callee can validate the code by reading it aloud to each other and confirm the two match. If the codes don't match, the connection has been intercepted, and they should end the call. To learn more about the user experience, see [Use end-to-end encryption for Microsoft Teams calls](https://support.microsoft.com/teams/calls-devices/use-end-to-end-encryption-for-microsoft-teams-calls).

## Manage end-to-end encryption for meetings in the Teams admin center

Note

Meeting organizers must have a Teams Premium license to use E2EE for meetings. Attendees don't require a Teams Premium license.

For meetings, E2EE is enabled by default in the Global (Org-wide default) enhanced encryption policy, allowing meeting organizers with a Teams Premium license to schedule meetings that use E2EE. Users in your organization automatically get the Global (Org-wide default) policy unless you create and assign a custom policy.

You can update the Global (Org-wide default) policy or create custom policies, as needed.

To manage who can create meetings with E2EE:

1. Sign in to the Teams admin center as a Teams administrator or Global administrator.
2. In the left navigation, go to **Enhanced encryption policies**.
3. Select the policy you want to update or choose **Add** to create a new policy and then name it.
4. Next to **End-to-end meeting encryption**, choose **Not enabled, but users can enable** or **Not enabled**.
5. Select **Save**.
6. [Assign the policy](policy-assignment-overview) to users, groups, or your entire organization the same way you manage other Teams policies.

If the policy is turned on for a meeting organizer, you can enforce end-to-end meeting encryption by using a meeting template. Sensitivity labels can enforce end-to-end encryption even if the policy isn't enabled for the meeting organizer.

## Use PowerShell to manage encryption policies

To manage enhanced encryption policies by using PowerShell, use the following cmdlets.

| Cmdlet | What it does |
| --- | --- |
| [Get-CsTeamsEnhancedEncryptionPolicy](/en-us/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) | Returns information about the Teams enhanced encryption policies in your organization. |
| [Grant-CsTeamsEnhancedEncryptionPolicy](/en-us/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) | Assigns and unassigns existing enhanced encryption policies to a user. Use `$NULL` to unassign all policies from a user. |
| [New-CsTeamsEnhancedEncryptionPolicy](/en-us/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) | Creates a new Teams enhanced encryption policy. |
| [Remove-CsTeamsEnhancedEncryptionPolicy](/en-us/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) | Deletes an enhanced encryption policy from your organization. You can't delete the Global (Org-wide default) policy. |
| [Set-CsTeamsEnhancedEncryptionPolicy](/en-us/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) | Updates values in an existing Teams enhanced encryption policy. |

### Example

#### Enable end-to-end encryption for one-to-one calls for the entire tenant through the default global policy

To enable E2EE for one-to-one calls for the entire tenant through the default global policy, run the following command.

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

`DisabledUserOverride` means that E2EE is disabled in Teams by default, but users can override the default and turn on E2EE in their Teams settings. To disable it for everyone with no user override, use `Disabled` instead.

Note

Users can have one and only one encryption policy assigned to them at a time. When you unassign a policy from a user by passing `-PolicyName $NULL`, that user is then assigned the default global policy. You can't unassign the default global policy.

## Platform and device support

E2EE is supported on the latest versions of the following platforms and clients.

The following platforms support end-to-end encrypted meetings and one-to-one calls:

- Teams desktop client for Windows and Mac
- iOS and Android mobile devices
- Microsoft Teams Rooms on Windows and Android

All other platforms, such as Web, Virtual Desktop (VDI), and Cloud Video Interoperability (CVI) devices, aren't currently supported. Participants who try to join an end-to-end encrypted meeting from one of these platforms are blocked.

A maximum of 200 participants can attend an end-to-end encrypted meeting.