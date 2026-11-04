---
layout: Conceptual
title: Assisted upgrades - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/upgrade-assisted
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: upgrade-and-migration-article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: billkau
ms.date: 2021-04-22T00:00:00.0000000Z
audience: admin
description: Overview of assisted upgrades from Skype for Business Online to Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
locale: en-us
document_id: 0a0d967c-8da2-54e2-13ff-2799be69d7f2
document_version_independent_id: 9a32dbb8-10a4-5121-afba-fd7a73cb2a41
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/upgrade-assisted.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: upgrade-assisted
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/upgrade-assisted.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1c24a4fc-2ef4-5072-1300-68f4bb3c3c7b
---

# Assisted upgrades - Microsoft Teams | Microsoft Learn

Microsoft retired Skype for Business Online on July 31, 2021. Microsoft is providing an assisted upgrade process to help organizations move remaining Skype for Business Online users to Teams Only. Microsoft assisted upgrades reduce the number of technical tasks and simplify the transition to a world without Skype for Business Online whether your organization is:

- A pure online organization that needs to upgrade from *Skype for Business Online* to become pure Teams Only, or
- A hybrid organization with users in both *Skype for Business Online***and** an on-premises *Skype for Business Server* environment, which must upgrade only its Skype for Business *Online* user to Teams Only.

We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade. Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams. This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.

## The assisted upgrade experience

Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive various forms of notifications: *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users. Upgrade notification in the Message Center and Teams admin center include the scheduled date of the assisted upgrade as well as a link to upgrade resources and training to help drive adoption and usage of Teams.

The assisted upgrade experience differs slightly depending on whether your organization has any users homed in an on-premises Skype for Business Server environment:

- **Pure online organizations:** For organizations *without* any on-premises Skype for Busineess Server users, the assisted upgrade process applies the `TeamsUpgradeOverridePolicy` policy to your organization. When this policy is applied, all users of Skype for Business Online will be placed in TeamsOnly mode.
- **Hybrid Organizations with on-premises Skype for Business users:** This includes organizations with any users homed in Skype for Business Server, regardless of whether Hybrid has been configured. These organizations may have users that fall into one of the following categories:

    - On-premises users homed on Skype for Business Server (that may or may not use Teams, but are not Teams Only users)
    - TeamsOnly users that homed in Skype for Business Online
    - Non-TeamsOnly users that are homed in Skype for Business Online

The assisted upgrade process will only impact the last category of users: Non-Teams Only users homed in Skype for Business Online will be upgraded to Teams Only mode. On-premises Skype for Business users and existing TeamsOnly users won't be impacted by the assisted upgrade process.

Note

Your organization can continue to use Skype for Business Online until your upgrade is complete. If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date. For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).

The duration of the upgrade will vary by volume of users and the characteristics of the deployment. In most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade. During this time, end users will still have access to Skype for Business Online functionality. Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.

## The post-upgrade experience

When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only. We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations) before your upgrade. The table below provides a high-level overview of the Teams Only user experience.

**Chat and Calling**

- All calls and chats are started and received in Teams
- Users can communicate (chat/call) with any Skype for Business user
- Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access)
- Teams users who attempt to sign in to Skype for Business Online are redirected to Teams

**Meetings**

- Users schedule all new meetings in Teams (plugin replaced)

**Migrated Data**

- Existing contacts from Skype for Business Online including federated (but no distribution lists)
- Contacts are migrated when users log into Teams for the first time.

Important

Contacts must be migrated within 90 days of the completion of your upgrade.

- Existing Skype for Business Online meetings are converted to Teams meetings

Important

Customers with pure Skype for Business Online configurations need to use the Meeting Migration Service (MMS) to migrate existing Skype for Business Online meetings to Teams meetings. We recommend using MMS prior to the assisted upgrade date. For more information about MMS, see [Using the Meeting Migration Service (MMS)](/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

If you have a Skype for Business Server hybrid deployment and upgrade to Teams, you can move users between Skype for Business Server and Teams after your upgrade is complete.