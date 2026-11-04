---
layout: Conceptual
title: Use guest access and external access to collaborate with people outside your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/communicate-with-users-from-other-organizations
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: majaisin
ms.date: 2026-07-10T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.custom:
- chat-teams-channels-revamp
- guest-access-external-collab
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
- Tier2
- essentials-manage
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: Medium
description: Learn how to call, chat, find, and add users from outside the organization in Microsoft Teams using external access and guest access.
locale: en-us
document_id: 5f080a5c-4268-1db4-566f-f1edc27920b5
document_version_independent_id: ac556a92-58af-3e05-f53b-0fc00afc96c0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/communicate-with-users-from-other-organizations.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: communicate-with-users-from-other-organizations
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/communicate-with-users-from-other-organizations.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e7517d04-0721-f2da-589b-75d787c59e77
---

# Use guest access and external access to collaborate with people outside your organization - Microsoft Teams | Microsoft Learn

This article describes two of the options for collaborating with people outside your organization:

- **External access** - A feature that allows users to find, call, and chat with people who have Microsoft identities, including those from other organizations.
- **Guest access** - A feature that allows you to invite people from outside your organization to join a team. Guests can also call, chat, and meet with people in your organization and you can share files and folders with them. Invited people get an [Microsoft Entra B2B collaboration guest account](/en-us/azure/active-directory/external-identities/what-is-b2b) in your directory.

For a complete overview of the external collaboration options in Microsoft 365, see [Overview of external collaboration options in Microsoft 365](/en-us/microsoft-365/enterprise/external-guest-access).

## External access

Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business Server, or Skype. By default, external access is enabled.

To configure external access, see [Manage external meetings and chat with people and organizations using Microsoft identities](trusted-organizations-external-meetings-chat).

For information about cross-cloud external access, such as between commercial and GCC, see [Microsoft Teams chat experience when communicating with people outside the organization](native-chat-for-external-users).

#### Teams accounts not managed by an organization

You can control whether users in your organization can communicate with Teams users who are not managed by an organization by turning external access on or off at the organization level or by using a policy to control it for individual users and groups. You can also control if people with unmanaged Teams accounts can start a conversation with people in your organization.

#### Skype users

Warning

Starting May 5, 2025, Skype Consumer Interoperability with Teams is no longer supported and the associated policies have been deprecated. You may still communicate with users outside of an organization through Teams external access.

## Guest access

Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files. A guest can be given nearly all the same Teams capabilities as a native team member. For more information, see [Guest experience in Teams](guest-experience).

If you need to have meetings with people outside your organization who aren't part of another Microsoft 365 organization, you can use guest access to allow them to log in to your organization for meetings.

Guests are added to your organization's Microsoft Entra ID as B2B collaboration users. They must sign in to Teams using their guest account. If they normally use Teams with another Microsoft 365 organization, they need to switch organizations in Teams to interact with your organization.

Guest access is available between Microsoft 365 cloud environments (such as commercial and GCC) by using cross-cloud guest access. For more information, see [Collaborate with guests from other Microsoft 365 cloud environments](collaborate-guests-cross-cloud).

To configure guest access for Teams, see [Collaborate with guests in a team](/en-us/previous-versions/microsoft-365/solutions/collaborate-as-team).

## Compare external access and guest access

The following tables show the differences between using external access and guests.

#### Things your users can do when communicating with people outside the organization

| Your users can | External access users | Guests |
| --- | --- | --- |
| Chat with someone in another organization | Yes | Yes |
| Call someone in another organization | Yes | Yes |
| See if someone from another organization is available for call or chat | Yes | Yes^1^ |
| Search for people in other organizations | Yes^2^ | No |
| Share files | No | Yes |
| See the out-of-office message of someone in another organization | No | Yes |
| Block someone in another organization | Yes | Yes |
| Use @mentions | Yes^3^ | Yes |

#### Things people outside your organization can do

| People outside your organization can | External access users | Guests |
| --- | --- | --- |
| Access Teams resources | No | Yes |
| Be added to a group chat | Yes | Yes |
| Be invited to a meeting | Yes | Yes |
| Make private calls | Yes | Yes^5^ |
| View the phone number for dial-in meeting participants | No^4^ | Yes |
| Use IP video | Yes | Yes^5^ |
| Use screen sharing | Yes^3^ | Yes^5^ |
| Use meet now | No | Yes^5^ |
| Edit sent messages | Yes^3^ | Yes^5^ |
| Delete sent messages | Yes^3^ | Yes^5^ |
| Use Giphy in conversation | Yes^3^ | Yes^5^ |
| Use stickers and memes in conversation | Yes^3^ | Yes^5^ |
| Presence is displayed | Yes | Yes |
| Use @mentions | Yes^3^ | Yes |

^1^ Provided that the user has been added as a guest and is signed in with the guest account.^2^ Only by email or Session Initiation Protocol (SIP) address.^3^ Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations. ^4^ By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams). ^5^ Allowed by default, but can be turned off by the Teams admin