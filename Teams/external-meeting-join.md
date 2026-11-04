---
layout: Conceptual
title: Prevent users from joining external Microsoft Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/external-meeting-join
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: vivekmo
ms.date: 2025-05-29T00:00:00.0000000Z
ms.topic: how-to
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
description: Learn how to prevent or block users in your organization from joining external meetings for IT Admins in Microsoft Teams.
locale: en-us
document_id: fbfdd252-f768-2093-2a88-9ae7207ac9d9
document_version_independent_id: fbfdd252-f768-2093-2a88-9ae7207ac9d9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/external-meeting-join.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: external-meeting-join
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/external-meeting-join.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2015b2f3-70ca-946d-b2ab-fd5d18cc39eb
---

# Prevent users from joining external Microsoft Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events

As an admin, you can control which types of Microsoft Teams meetings users in your org can join. Managing the types of meetings your users can join can be helpful in privacy and compliance scenarios, where you might not want specific users or groups in your org joining meetings with external non-trusted trusted or even trusted organizations.

To learn more about trusted organizations, see [IT Admins - Manage external meetings and chat with people and organizations using Microsoft identities](trusted-organizations-external-meetings-chat).

The following table describes how different roles in Teams interact with this policy:

| User role | Policy effect |
| --- | --- |
| Trusted org participant | When this policy is set to **Anyone** or **Only people in trusted orgs**, users in your org can join meetings that trusted organizations (as defined in External access) host.  When this policy is set to **No one**, users in your org can't join externally hosted Teams meetings while using your org’s accounts. However, your users can still join external meetings as anonymous if they aren’t logged in to Teams. |
| Guest | This policy doesn’t affect meetings in other organizations where your users are signed in as guests. |
| Anonymous | This policy doesn't prevent users from joining external meeting anonymously if they’re not signed into Teams. |
| External participant in a shared channel meeting | This policy doesn't prevent users from joining external shared channel meetings. |

## Manage the types of meetings your users can join

You can manage the types of meetings your users can join through the Teams admin center or PowerShell.

| Teams admin center policy option | Parameter value in PowerShell | Behavior |
| --- | --- | --- |
| Anyone | EnabledForAnyone | **This is the default value.** Users with this policy can join any meeting they’re invited to. |
| Only people in trusted orgs | EnabledForTrustedOrgs | Users with this policy can only join in org meetings and meetings that organizations you have a trusted relationship with host. |
| No one | Disabled | Users with this policy can only join in org meetings. |

### Prevent users from joining external meetings using the Teams admin center

To manage the types of meetings your users can join, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one.
3. Go to the **Meeting join & lobby** section.
4. Set **People can join external meetings hosted by** to your chosen value of either **Anyone**, **Only people in trusted orgs**, or **No one**.
5. Select **Save**

### Prevent users from joining external meetings using PowerShell

You can use the **`-ExternalMeetingJoin`** parameter within the [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) PowerShell cmdlet to manage the types of external meetings your users can join.

Before you can run these cmdlets, you must be connected to Microsoft Teams PowerShell. For more information, see [Manage Teams with Microsoft Teams PowerShell](/en-us/microsoftteams/teams-powershell-managing-teams).

For more information on PowerShell cmdlets for Teams meetings, see the Related articles section.

For users to only join meetings that are in org or hosted by orgs that you have a trusted relationship with, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -ExternalMeetingJoin  EnabledForTrustedOrgs
```

To only allow users to join in org meetings, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -ExternalMeetingJoin  Disabled
```