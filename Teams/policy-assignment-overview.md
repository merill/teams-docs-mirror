---
layout: Conceptual
title: Assign policies in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/policy-assignment-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: tomkau, ritikag, jastark
ms.date: 2021-03-10T00:00:00.0000000Z
ms.topic: get-started
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: Learn the different ways to assign policies and policy packages to users and groups in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
locale: en-us
document_id: c9cdd2f0-86e0-6001-1600-e1617b14e338
document_version_independent_id: c9cdd2f0-86e0-6001-1600-e1617b14e338
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/policy-assignment-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: policy-assignment-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/policy-assignment-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/86a4b315-a9f1-4577-b985-6fb0e0e67420
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/96ac410d-d052-4707-8007-df31dd0fe041
platformId: 659b7554-3009-f2d9-5184-cf6ca0e07df7
---

# Assign policies in Teams - Microsoft Teams | Microsoft Learn

As an admin, you use policies to control the Teams features that are available to users in your organization. For example, there are calling policies, meeting policies, and messaging policies, to name just a few.

Organizations have different types of users with unique needs. Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.

To easily manage policies in your organization, Teams offers several ways to assign policies to users. Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of. You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles. The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to. Global (Org-wide default) policies apply to the largest number of users in your organization. You only have to assign policies to those users that require specialized policies.

This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.

For details on how to **assign policies to users and groups**, see [assigning policies to users and groups](assign-policies-users-and-groups). For details on how to **assign policy packages**, see [assign policy packages](assign-policy-packages).

## Which policy takes precedence?

A user has one effective policy for each policy type. It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type. In these kinds of scenarios, which policy takes precedence? A user's effective policy is determined according to rules of precedence, as follows.

If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence. In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.

![Diagram showing how a directly assigned policy takes precedence.](media/assign-policies-example-directly-assigned.png)

If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence. If a user is a member of multiple groups, the policy that has the highest ([group assignment ranking](assign-policies-users-and-groups#group-assignment-ranking)) for the given policy type takes precedence.

In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.

![Diagram showing how a policy inherited from  group takes precedence.](media/assign-policies-example-group.png)

If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type. Here's a visual example.

![Diagram showing how a global policy takes precedence.](media/assign-policies-example-global.png)

To learn more, see ([Precedence rules](assign-policies-users-and-groups#precedence-rules)).

## Ways to assign policies

Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each. Select the links to learn more.

Before assigning policies to individual users or groups, start by setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization. Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.

| Do this | If... | Using... |
| --- | --- | --- |
| [Assign a policy to individual users](assign-policies-users-and-groups#assign-a-policy-to-individual-users) | You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users. | The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module |
| [Assign a policy to a group](assign-policies-users-and-groups#assign-a-policy-to-a-group) | Assign policies based on a user's group membership. For example, assign a policy to all users in a security group or distribution list. | The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module |
| [Assign a policy to a batch of users](assign-policies-users-and-groups#assign-a-policy-to-a-batch-of-users) | Assign policies to large sets of users. For example, assign a policy to hundreds or thousands of users in your organization at a time. | The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module |
| [Assign a policy package to users](assign-policy-packages#assign-a-policy-package-to-users) | Assign multiple policies to specific sets of users in your organization who have the same or similar roles. For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings. Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling. | The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module |
| [Assign a policy package to a group](assign-policy-packages#assign-a-policy-package-to-a-group) | Assign multiple policies to a group of users in your organization who have the same or similar roles. For example, assign a policy package to all users in a security group or distribution list. | The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module |
| [Assign a policy package to a batch of users](assign-policy-packages#assign-a-policy-package-to-a-batch-of-users) | Assign multiple policies to a batch of users in your organization who have the same or similar roles. For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings. Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling. | PowerShell cmdlets in the Teams PowerShell module |

Note

To unassign policies, you can remove assignments in bulk for all users directly assigned to a policy. To learn more, read [Unassign policies in bulk](assign-policies-users-and-groups#unassign-policies-in-bulk).

## Set the global policies

Follow these steps to set the global (Org-wide default) policies for each policy type.

### Using the Microsoft Teams admin center

1. In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update. For example, **Teams** &gt; **Teams policies**, **Meetings** &gt; **Meetings policies**, **Messaging policies**, or **Voice** &gt; **Calling policies**.
2. Select the **Global (Org-wide default)** policy to view the current settings.
3. Update the policy as needed, and then select **Save**.

[![Screenshot that shows the update global policy in Teams admin center.](media/teams-meetings-policies-global-general.png)](media/engineering-meeting-policy.png#lightbox)

Note

After you submit any policy operation, you'll be prompted with a pop-up dialog box to confirm it. This includes policy assignments, changing an existing policy, and creating new custom policies. You must confirm to start the policy operation, or you can cancel and go back later.

### Using PowerShell

To set the global policies using PowerShell, use the Global identifier. Start by reviewing the current Global policy to determine which setting you want to change.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Next, update the Global policy as needed. You only need to specify values for the settings that you want to change.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## View your policy assignments in the Activity log

When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the [Activity log](https://admin.teams.microsoft.com/activitylog). The activity log shows network record upload information, group policy operations from Teams admin center and PowerShell, and batch policy operations (for more than 20 users) from the Teams admin center, for the last 30 days.

[![Screenshot of the Activity log page.](media/teams-activity-log.png)](media/activity_log.png#lightbox)

To view your policy operations in the Activity log:

1. In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.
2. You'll see the following information about each policy operation:
    - **Activity**: The name of the policy operation. For example: **Group policy assignment**
    - **Group name**: The name of the group the policy operation was completed on.
    - **Policy type**: The type of policy.
    - **Policy name**: The name of the policy operation. For batch policy assignments, you can select the link to view more details. This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started. You'll also see the list of users in the batch, and the status and result for each user.
    - **Submitted by**: The name of the user who submitted the policy operation.
    - **Submitted on**: Date and time the policy operation was submitted.
    - **Completed on**: Date and time the policy operation was completed.
    - **Impacted**: Number of users in the batch or group.
    - **Overall status**: Status of the policy operation. A policy can have one of the following statuses:
        - **Not started**: The policy operation was submitted by the admin.
        - **In progress**: The policy operation has started processing.
        - **Rolling out to users**: The system has started applying the policy update to users.
        - **Completed**: The policy update has been applied all users.
        - **Completed with 'x' errors**: The policy operation is complete, but there are errors.

Note

You can also get to the Activity log from the **Users** page. After you select **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page. Select the **Activity log** link in the banner.

This video shows the steps to view and manage the assigned and effective policies for a user.

This video is about differences between global and custom policies.