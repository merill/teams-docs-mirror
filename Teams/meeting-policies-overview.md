---
layout: Conceptual
title: Manage meeting and events policies in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-policies-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: bryannyce
ms.date: 2026-07-09T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Learn to manage meeting and events policy settings in Teams and use them to control the features available to meeting participants for meetings and events.
locale: en-us
document_id: 813bcae6-1c45-1d12-6652-de7d0986edfa
document_version_independent_id: fe0b1991-f210-bf08-850a-487f4c9b1b8e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-policies-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-policies-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-policies-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 79a36f70-9dcf-b685-2cb3-cdf8589fffef
---

# Manage meeting and events policies in Microsoft Teams - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Events

As an admin, you can use meeting and events policies to control the features that are available to organizers and participants of meetings and events in your organization. Depending on the feature, you can manage meeting policies in the Microsoft Teams admin center or through [PowerShell](teams-powershell-overview).

You can edit the settings in the global policy or create and assign one or more custom policies. Users get the global policy unless you create and assign a custom policy.

Policies are implemented in one of the following ways:

| Implementation type | Description |
| --- | --- |
| Per-organizer | When you implement a per-organizer policy, all participants inherit the policy of the organizer. For example, **Who can bypass the lobby** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy. |
| Per-user | When you implement a per-user policy, the policy allows or prevents a given feature for each user. For example, **Meet now in channel meetings** is a per-user policy. |
| Per-organizer and per-user | When you implement a combination of a per-organizer and per-user policy, certain features are restricted for participants based on their policy and the organizer's policy. For example, **Meeting recording** is a per-organizer and per-user policy. Turn on this setting to allow the meeting organizer and participants to start and stop a recording. |

## Create a custom meeting or events policy

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies** or **Events policies**.
2. Select **Add**.
3. Enter a name and description for the policy. The name can't contain special characters or be longer than 64 characters.
4. Choose the settings that you want.
5. Select **Save**.

Note

After you create a policy, its name can't be changed. To access this policy in the new experience, go to **Settings & policies**. To learn more, see [Unified policies and settings management in the Teams admin center](unified-policies-settings-management-teams-admin-center).

This video shows the steps to create and assign a custom meeting policy to a user (or users).

## Edit a meeting or events policy

You can edit the global policy and any custom policies that you create.

1. In the left navigation of the Microsoft Teams admin center, go to **Meetings** &gt; **Meeting policies** or **Events policies**.
2. Choose the policy by clicking to the left of the policy name, and then select **Edit**.
3. From here, make the changes that you want.
4. Select **Save**.

Note

A user can be assigned only one meeting policy and one events policy at a time.

This video shows the steps to edit an organizational-wide default meeting policy.

## Assign a meeting or events policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

Note

You can't delete a policy if users are assigned to it. You must first assign a different policy to all affected users, and then you can delete the original policy.