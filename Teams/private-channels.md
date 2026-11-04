---
layout: Conceptual
title: IT Admins - Private channels in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/private-channels
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: jasonlewis
ms.date: 2026-10-01T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: Admin
ms.custom:
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use and manage private channels in Microsoft Teams.
locale: en-us
document_id: ce34b12b-aa50-608b-bbfa-a1fb4bb79f8d
document_version_independent_id: 9ddeb6f4-f30a-1e72-fc94-ae66def91f40
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/private-channels.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: private-channels
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/private-channels.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: acc345c6-ea15-a0b3-411c-6b6bf2306d3f
---

# IT Admins - Private channels in Microsoft Teams - Microsoft Teams | Microsoft Learn

Private channels in Microsoft Teams create focused spaces for collaboration within your teams. Only the users on the team who are owners or members of the private channel can access the channel. Anyone, including guests, can be added as a member of a private channel as long as they're existing members of the team.

You can use a private channel to limit collaboration to specific individuals or to facilitate communication between a group of people assigned to a specific project, without having to create another team to manage.

For example, a private channel is useful in these scenarios:

- A group of people in a team want a focused space to collaborate without having to create a separate team.
- A subset of people in a team wants a private channel to discuss projects and topics, such as budgets, resourcing, strategic positioning, and so on.

A lock icon indicates a private channel. Only members of private channels can see and participate in private channels that they're added to.

When a private channel is created, it links to the parent team and can't be moved to a different team. Additionally, private channels can't be converted to standard channels and vice versa.

Note

Private channels now support channel meetings and are no longer limited to 30 channels per team. Instead, private channels are included in the overall support limit of up to 1,000 channels per team. Currently, this excludes tenants in special cloud environments - for those tenants, the enhanced functionality comes later this year.

[Compare private channels with other types of channels](/en-us/microsoftteams/teams-channels-overview#channel-feature-comparison).

## Private channel creation

By default, any team owner or team member can create a private channel. Guests can't create them. The ability to create private channels can be managed at the team level and at the organization level. Use [policies](teams-policies) to control which users in your organization are allowed to create private channels. Once you set the policies, team owners can turn off or turn on the ability for members to create private channels in the **Settings** tab for a team.

The person who creates a private channel is the private channel owner and only the private channel owner can directly add or remove people from it. A private channel owner can add any team member to a private channel they created, including guests. Members of a private channel have a secure conversation space, and when new members are added, they can see all conversations (even old conversations) in that private channel.

Team owners who aren't a member of a private channel can see the channel under **Manage team** but not in the channels and teams list. A private channel owner or team owner (whether or not they're a member of the private channel) can delete the private channel. A deleted private channel can be restored within 30 days after its deletion.

Team members can only see private channels that they're added to.

## Adding and removing owners and members

A private channel owner can't be removed through the Teams client if they're the last owner of one or more private channels.

If a private channel owner leaves your organization or if they're removed from the Microsoft 365 group associated with the team, a member of the private channel is automatically promoted to be the private channel owner.

If a team member leaves or is removed from a team, that user is removed from all private channels in the team. If the user is added back to the team, they must be added back to the private channels in the team.

Note

Learn more about enhancements to private channels and streamlining of compliance management at [New enhancements in Private Channels in Microsoft Teams unlock their full potential](https://techcommunity.microsoft.com/blog/microsoftteamsblog/new-enhancements-in-private-channels-in-microsoft-teams-unlock-their-full-potent/4438767). B2B collaboration user properties are described at [Understand and manage the properties of B2B guest users](/en-us/entra/external-id/user-properties).

## Channel owner settings

Each private channel has its own settings that the channel owner can manage, including the ability to add and remove members, add tabs, and @mentioning for the entire channel. These settings are independent of the parent team settings. When a private channel is created, it inherits settings from the parent team, after which its settings can be changed independently of the parent team settings.

The private channel owner can select **Manage channel**, and then use the **Members** and **Settings** tabs to add or remove members and edit settings.

## Private channel owner and member actions

The following table outlines what actions owners, members, and guests can do in private channels.

| Action | Team owner | Team member | Team guest | Private channel owner | Private channel member | Private channel guest |
| --- | --- | --- | --- | --- | --- | --- |
| Create private channel | Admin controlled | Admin and team owner controlled | No | N/A | N/A | N/A |
| Delete private channel | Yes | No | No | Yes | No | No |
| Leave private channel | N/A | N/A | N/A | Yes unless they're the last owner | Yes | Yes |
| Edit private channel | No | N/A | N/A | Yes | No | No |
| Restore deleted private channel | Yes | No | No | Yes | No | No |
| Add members | No | N/A | N/A | Yes | No | No |
| Edit settings | No | N/A | N/A | Yes | No | No |
| Manage tabs and apps | No | N/A | N/A | Yes, apps must be installed for the team | Channel owner controlled | No |

## Private channel SharePoint sites

Each private channel has its own SharePoint site. The separate site is to ensure access to private channel files is restricted to only members of the private channel. These sites can be easily enhanced to a full-featured site through the [site management interface](https://support.microsoft.com/office/a2f2a5c2-093d-4897-8b7f-37f86d83df04). Each site is created in the same geographic region as the site for the parent team. These lightweight sites have a custom template ID, "TEAMCHANNEL#0" or "TEAMCHANNEL#1", for easier management through PowerShell and Graph API.

Note

Only people with owner or member permissions in the channel have access to the channel site. People in the parent team and admins don't have access unless they're also channel members. Also note, private channels have been moved to group compliance as part of an ongoing initiative. With this change, newly created **private** channels will not be created with a folder by default.

A private channel site syncs data classification and inherits guest access permissions from the site of the parent team. Membership to the site owner and member groups are kept in sync with the membership of the private channel within Teams. Site permissions for a private channel site can't be managed independently through SharePoint.

Teams manages the lifecycle of the private channel site. If the site is deleted outside of Teams, a background job restores the site within four hours as long as the private channel is still active.

If a private channel or a team containing a private channel is restored, the sites are restored with it. If a private channel site is restored and it's beyond the 30-day soft delete window for the private channel, the site operates as a standalone site.

Retention policies can also be used for private channel sites. For more information, see [Learn about retention for SharePoint and OneDrive](/en-us/microsoft-365/compliance/retention-policies-sharepoint).

Note

When you create a new team, private channel, or shared channel in Microsoft Teams, a team site in SharePoint gets automatically created. To edit the site description or classification for this team site, go to the corresponding channel’s [settings in Microsoft Teams](https://support.microsoft.com/office/change-a-team-s-data-security-classification-in-teams-bf39798f-90d2-44fb-a750-55fa05a56f1d).

Learn more about managing [Microsoft Teams connected teams sites](/en-us/SharePoint/teams-connected-sites).

## Compliance copies of private channel messages

Compliance copies of messages sent in a private channel are now delivered to the group mailbox (instead of mailbox of all private channel members). The titles of the compliance copies are formatted to indicate which private channel they were sent from.

For more information about performing an eDiscovery search for private channel messages, see [eDiscovery of private channels](ediscovery-investigation#ediscovery-of-private-and-shared-channels).

## Considerations around file access in private channels

[Sharing files and folders](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c) in a private channel works the same as with other SharePoint sites. Users can share files and folders using sharable links based on the [sharing settings configured by the SharePoint Administrator](/en-us/sharepoint/turn-external-sharing-on-or-off).

Sharing a OneNote notebook in a private channel site is the same as sharing access to any other item. If a user is granted access to a notebook in a private channel through SharePoint, removing the user from the team or private channel doesn't remove the user's access to the notebook. If an existing notebook is added as a tab to a private channel, access to the private channel isn't changed, and the notebook retains its existing permissions.

## Private channel limitations

Private channels don't support connectors and tabs in Stream, Planner, Tasks by Planner and To Do, and Forms.

It isn't possible to convert a private channel to another channel type.

Notifications from private channels aren't included in missed activity emails.

Note

To check if all private channels in your tenant have been moved to the new compliance model, please refer to the PowerShell module: [Get-TenantPrivateChannelMigrationStatus (MicrosoftTeams) | Microsoft Learn](/en-us/powershell/module/microsoftteams/get-tenantprivatechannelmigrationstatus).