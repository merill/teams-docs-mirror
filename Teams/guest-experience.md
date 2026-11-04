---
layout: Conceptual
title: Guest experience in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/guest-experience
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: manish.jaisinghani
ms.date: 2025-03-24T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
- guest-access-external-collab
description: This article describes the Microsoft Teams functionality available to guests.
locale: en-us
document_id: 048930a4-fdf2-9a90-3b47-46af66db3db4
document_version_independent_id: 8d6a2c84-94e9-b17e-f5c1-91191187ce4e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/guest-experience.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: guest-experience
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/guest-experience.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4b7febb6-208b-e018-732f-973b3f82f88a
---

# Guest experience in Microsoft Teams - Microsoft Teams | Microsoft Learn

When a guest is invited to join a team, they receive a welcome email message. This message includes some information about the team and what to expect now that they're a member. The guest must accept the invitation before they can access the team and its channels. They can accept the invite in the Teams client or by selecting **Open Microsoft Teams** in the email message.

Important

All Guests must be added to at least one Team before guest access features and functionality will be available to the guest account. [Learn more](https://support.microsoft.com/office/add-guests-to-a-team-in-microsoft-teams-fccb4fa6-f864-4508-bdde-256e7384a14f).

Note

After a guest is added to a team, it may take a few hours before they have access.

![Screenshot showing an example of a welcome email message.](media/guest-experience-image1.png)

All team members see a message in the channel thread announcing that the team owner added a guest and providing the guest's name. Everyone on the team can identify easily who is a guest. A tag in the upper-right corner of the channel thread indicates the number of guests on the team and a **(Guest)** label appears next to each guest's name.

![Screenshot showing tag that indicates number of guests on the team.](media/guest-experience-image2.png)

Check out these videos about the guest experience in Teams:

- [Join a Teams meeting as a guest](https://support.microsoft.com/office/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [Work with external guests in a Teams meeting](https://support.microsoft.com/office/work-with-external-guests-180ed260-d3ef-4247-9f24-1984fc76d5f0)

## Comparison of team member and guest capabilities

The following table compares the Teams functionality available for an organization's team members and its guests. Teams admins control the features available to guests.

| Capability in Teams | Teams user in the organization | Guest |
| --- | --- | --- |
| Create a channel *Team owners control this setting.* | ✓ | ✓ |
| Participate in a private chat | ✓ | ✓ |
| Participate in a channel conversation | ✓ | ✓ |
| Post, delete, and edit messages | ✓ | ✓ |
| Share a channel file | ✓ | ✓ |
| Access SharePoint files | ✓ | ✓ |
| Attach files | ✓ | Channel posts only |
| Download private chat files | ✓ | ✓ |
| Search within files | ✓ |  |
| Share a chat file | ✓ |  |
| Add apps (tabs, bots, or connectors) | ✓ |  |
| Create meetings or access schedules | ✓ |  |
| Access OneDrive for Business storage | ✓ |  |
| Create tenant-wide and teams/channels guest access policies | ✓ |  |
| Invite a user outside the Microsoft 365 or Office 365 organization's domain *Team owners control this setting.* | ✓ |  |
| Create a team | ✓ |  |
| Discover and join a public team | ✓ |  |
| View organization chart | ✓ |  |
| Use inline translation | ✓ |  |
| Become team owner | ✓ |  |

The following table shows the calling and meeting features available to guests, compared to other types of users.

| Calling feature | Guest | E1 and E3 user | E5 and Enterprise Voice user |
| --- | --- | --- | --- |
| VOIP calling | Yes | Yes | Yes |
| Group calling | Yes | Yes | Yes |
| Core call controls supported (hold, mute, video on/off, screen sharing) | Yes | Yes | Yes |
| Transfer target | Yes | Yes | Yes |
| Can transfer a call | Yes | Yes | Yes |
| Can consultative transfer | Yes | Yes | Yes |
| Can add other users to a call via VOIP | Yes | Yes | Yes |
| Can add users by phone number to a call | No | No | Yes |
| Forward target | No | Yes | Yes |
| Call group target | No | Yes | Yes |
| Unanswered target | No | Yes | Yes |
| Can be the target of a federated call | No | Yes | Yes |
| Can make a federated call | No | Yes | Yes |
| Can immediately forward their calls | No | No | Yes |
| Can simultaneously ring their calls | No | No | Yes |
| Can route their unanswered calls | No | No | Yes |
| Missed calls can go to voicemail | No | Yes | Yes |
| Have a phone number that can receive calls | No | No | Yes |
| Can dial phone numbers | No | No | Yes |
| Can access call settings | No | No | Yes |
| Can change voicemail greeting | No | Yes | Yes |
| Can change ringtones | No | No | Yes |
| Supports TTY | No | No | Yes |
| Can have delegates | No | No | Yes |
| Can be a delegate | No | No | Yes |

Note

The **Guest user access restrictions** policy in Microsoft Entra ID determines permissions for guests in your directory. There are three policy options.

- The **Guest users have the same access as members (most inclusive)** setting means guests have the same access to directory data as regular users in your directory.
- The **Guest users have limited access to properties and membership of directory objects** settings means that guests don't have permissions for certain directory tasks, such as enumerating users, groups, or other directory resources using Microsoft Graph.
- The **Guest user access is restricted to properties and memberships of their own directory objects (most restrictive)** setting means guests can only access their own directory objects.

To learn more, see [What are the default user permissions in Microsoft Entra ID?](/en-us/azure/active-directory/fundamentals/users-default-permissions)