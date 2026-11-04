---
layout: Conceptual
title: Prevent users from sharing content in external Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/block-external-content-share
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
audience: Admin
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: maahma
ms.date: 2025-05-29T00:00:00.0000000Z
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
description: Learn how to control whether users in your org with a Teams Premium license can share content when attending external Teams meetings.
locale: en-us
document_id: dd19efe5-4e71-9fe3-3ee7-6e945e43f2d7
document_version_independent_id: dd19efe5-4e71-9fe3-3ee7-6e945e43f2d7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/block-external-content-share.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: block-external-content-share
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/block-external-content-share.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 47d2b95b-7168-7c4f-69a0-d4989f283e8d
---

# Prevent users from sharing content in external Teams meetings - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events

## Overview

If you enabled content sharing for users in your org, they can present a screen, window, or app in Microsoft Teams meetings. When users from your org attend external meetings, they can share content if the organizer of that meeting set **Who can present** to **Everyone** or **Specific people**. However, you might want to prevent some of your users from sharing sensitive information when attending external meetings.

As an admin, you can control whether users in your org with a Teams Premium license can share content when attending external Teams meetings.

## Manage the types of meetings your users can share content in

You can use the Teams admin center or the **`-ContentSharingInExternalMeetings`** parameter in PowerShell to manage the types of meetings your users can share content in.

| Teams admin center policy option | PowerShell value | Behavior |
| --- | --- | --- |
| Any org | EnabledForAnyone | **This is the default value.** Users with this assigned policy can share content when attending meetings that any org hosts. |
| Trusted orgs and guests | EnabledForTrustedOrgs | Users with this assigned policy can only share content when attending meetings that trusted orgs and guests that you defined in your [External access policy](trusted-organizations-external-meetings-chat) host. |
| No other orgs | Disabled | Users with this assigned policy can’t share content when attending any external meetings. |

### Prevent users from sharing content in external meetings in the Teams admin center

Follow these steps in the Teams admin center to manage the types of meetings your users can share content in:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Either select an existing policy or create a new one.
3. Navigate to the **Content sharing** section.
4. Set **Participants can share content in external meetings hosted by** to your chosen value of either **Any org** (default), **Trusted orgs and guests**, or **No other orgs**.
5. Select **Save**.

### Prevent users from sharing content in external meetings using PowerShell

You can use the **`-ContentSharingInExternalMeetings`** parameter in the [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet to manage which external meetings your users can share content in.

To prevent users with this policy from sharing content in any external meetings, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -ContentSharingInExternalMeetings Disabled
```

For users with this policy to only share content in meetings that trusted orgs and guests host, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -ContentSharingInExternalMeetings EnabledForTrustedOrgs
```

## Platform support

To view the list of platforms that support this feature, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-advanced-management-for-meetings).

This policy doesn't prevent your users from sharing content in external meetings anonymously when they aren't signed into Teams.