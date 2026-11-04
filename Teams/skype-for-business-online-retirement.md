---
layout: Conceptual
title: Skype for Business Online retirement - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/skype-for-business-online-retirement
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
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: landerl
ms.date: 2019-09-06T00:00:00.0000000Z
audience: admin
description: Learn about the retirement plan for Skype for Business Online, and how Microsoft is helping customers migrate to Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: a2cea1cc-731d-bfba-3ed5-63a6339ecf88
document_version_independent_id: 7681956e-e442-07a3-7f7b-f086a0aff173
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/skype-for-business-online-retirement.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: skype-for-business-online-retirement
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/skype-for-business-online-retirement.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7d72c8e0-ba1c-c9aa-975f-495ce08b9b86
---

# Skype for Business Online retirement - Microsoft Teams | Microsoft Learn

On July 31, 2021, Microsoft retired Skype for Business Online. This retirement was announced in July 2019 to give customers two years advance notice to plan their upgrades to Microsoft Teams. With Skype for Business Online being retired, Microsoft wants to ensure customers have the required information and resources to plan and execute a successful upgrade to Teams. The Skype consumer service isn't affected by this retirement. For background on why Skype for Business Online was retired, see [FAQ—Upgrading from Skype for Business to Microsoft Teams](faq-journey).

Microsoft will begin decommissioning the Skype for Business Online infrastructure on or after June 30, 2022. In addition, beginning in October 2022, Microsoft will begin decommissioning aspects of that infrastructure specific to hybrid organizations. This article contains guidance for organizations with TeamsOnly users that were upgraded from any version of Skype for Business.

Important

**The retirement of Skype for Business Online does not affect support for on-premises deployments of Skype for Business Server and Lync Server 2013**. However, hybrid customers with a mix of users homed online and on-premises *must* upgrade any *online* users to be TeamsOnly. Any online users must be assigned TeamsOnly mode using TeamsUpgradePolicy. In addition, Microsoft is providing assisted upgrades to help automate the upgrade of remaining Skype for Business Online users to TeamsOnly mode. Hybrid organizations need not move their *on-premises* Skype for Business users to the cloud as a result of this retirement. *Microsoft fully supports hybrid organizations with a mix of TeamsOnly users and on-premises Skype for Business users*. Customers with hybrid deployments of Skype for Business Server or Lync Server 2013 should review [Implications of Retirement of Skype for Business Online](/en-us/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-retirement-of-skype-for-business-online).

## What to expect post-retirement

It's no longer possible for users homed in the cloud to be assigned a mode other than TeamsOnly. This means:

- When licensing new users that aren't homed in on-premises Skype for Business Server, users are automatically assigned TeamsOnly mode, regardless of the tenant's global policy of TeamsUpgradePolicy.
- In hybrid organizations, when moving users homed on-premises to the cloud, users are automatically assigned TeamsOnly mode regardless of whether the `MoveToTeams` switch was specified in `Move-CsUser`.
- Users homed in the cloud can't be assigned a mode other than TeamsOnly. Users homed online do *not* use Skype for Business server on-premises.

Any customers that have remaining users homed in Skype for Business Online but aren't yet assigned TeamsOnly mode must assign TeamsOnly mode to these users as soon as possible. In addition, Microsoft will provide assisted upgrades for Skype for Business Online users not in TeamsOnly mode. The assisted upgrade experience depends on whether your organization is a pure online organization or an organization with on-premises Skype for Business users. For more information, see [Assisted Upgrades from Skype for Business Online to Microsoft Teams](upgrade-assisted). After the assisted upgrade is complete, all *online* users will be in TeamsOnly mode. *Any users homed on-premises remain on-premises and won't be made TeamsOnly*.

Users in TeamsOnly mode receive incoming chats and calls in Teams, and also schedule meetings in Teams. They can't initiate chats or calls or schedule meetings in Skype for Business Online. TeamsOnly users can join Skype for Business meetings they already have or receive in the future. However, after Microsoft removes the Skype for Business Online infrastructure for a given TeamsOnly user, TeamsOnly users may only join Skype for Business meetings anonymously. Beginning after June 30, 2022, newly created TeamsOnly users will no longer be provisioned with the Skype for Business Online infrastructure so if they're invited to a Skype for Business meeting, they would need to join anonymously. Similarly, users moved from on-premises to Teams Only in hybrid organizations will no longer be provisioned with the Skype for Business Online infrastructure beginning in October 2022. If these users are invited to a Skype for Business meeting, they would also need to join anonymously using the Skype for Business Web App.

## Guidance for organizations with on-premises deployments of Skype for Business Server

- When creating new users in your on-premises Active Directory environment, if these users will be synchronized to Microsoft Entra ID and you intend to license them for Teams, then *before assigning these users the license*, **you must first enable them in your on-premises Skype for Business deployment and ensure the change has synchronized to the cloud via Microsoft Entra Connect**. You can verify the change has fully synced to the cloud using Get-CsOnlineUser. The change has synchronized if the user's HostingProvider= "SRV:". It shouldn't be "sipfed.online.lync.com".
- Be aware that TeamsOnly users will need to anonymously join Skype for Business meetings once Microsoft removes the legacy Skype for Business Online infrastructure for hybrid organizations, beginning in October 2022. For details, see What To Expect Post Retirement. As an alternative, you can ensure meetings scheduled by all users (whether on-premises or Teams Only) in your organization are Teams meetings, which enables authenticated meeting join for any user in the organization (subject to policy configuration). To achieve this, take the following actions:

    - For any users that are assigned either **Skype for Business Only** or **Skype for Business with Teams Collaboration** modes, change the coexistence mode to **Skype for Business with Teams Collaboration and Meetings**. This mode offers the same functionality as the other two, except new meetings scheduled by the user will be Teams meetings instead of Skype for Business meetings. When you assign this mode directly to a user (as opposed to at the tenant level), it will by default also automatically convert any Skype for Business meetings to Teams meetings organized by that user.
    - For users that are in Islands mode, you can require them to always schedule meetings in Teams by assigning them an instance of TeamsMeetingPolicy with the PreferredMeetingProviderForIslandsMode=Teams.
    - To ensure any existing Skype for Business meetings are converted to Teams meetings (for example, if you have Islands users), you can use Start-CsExMeetingMigration to trigger the [Meeting Migration Service](/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) to convert a user's meetings to Teams.
- To ensure any contacts from Skype for Business Server are properly migrated to Teams when a user is moved from on-premises to TeamsOnly, be sure migrated users sign into Teams within 30 days of being migrated from on-premises. This is a temporary requirement as Microsoft transitions Teams away from the legacy Skype for Business Online infrastructure.

## Actions to take before June 30, 2022

Now that Skype for Business Online is retired, Microsoft will begin decommissioning the supporting infrastructure no sooner than June 30, 2022. For any organization with TeamsOnly users that were upgraded from any version of Skype for Business, you need to take action if either of these situations applies:

- If you have any TeamsOnly users that previously had contacts in Skype for Business *and* who haven't yet logged in to Teams since being upgraded.
- If you have any TeamsOnly users that still have Skype for Business Online meetings that they organized before they were upgraded to TeamsOnly.

If either of these situations apply to your organization, you must take action by June 30, 2022 as described below:

- **Skype for Business Online Contacts:** After a user has been upgraded to TeamsOnly mode, the first time that user signs in to Teams, any existing contacts in that user’s Skype for Business Online account will be migrated to Teams. After Microsoft removes the Skype for Business Online infrastructure, you can no longer migrate contacts *for users who haven't yet signed in to Teams.* To migrate contacts from Skype for Business to Teams, Microsoft recommends that all users who previously had Skype for Business sign in to Teams at least once before June 30, 2022.
- **Skype for Business Online Meetings:** After an organization is upgraded to TeamsOnly, users create all new meetings as Teams meetings. In some cases, TeamsOnly users may still have Skype for Business Online meetings which they previously organized. Currently, upgraded TeamsOnly users and any invited attendees can join Skype for Business Online meetings using their Skype for Business client. After Microsoft removes the Skype for Business Online infrastructure for a given TeamsOnly user, however, that user may only join Skype for business meetings anonymously, and any remaining Skype for Business Online meetings *organized by that user* will no longer exist. The organizer and any attendees won't be able to join these meetings. If users in TeamsOnly organizations have any remaining Skype for Business Online meetings that they organized, Microsoft recommends that they reschedule these meetings as Teams meetings. Alternatively, administrators may use the [Meeting Migration Service](/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) to convert these meetings to Teams meetings. In either case, complete these actions by June 30, 2022.

## How Microsoft is helping customers upgrade to Teams

We strongly recommend that you begin your upgrade from Skype for Business Online to Teams today. Take advantage of the resources available to help plan your Teams deployment and upgrade from Skype for Business:

- [Teams deployment and upgrade documentation](upgrade-start-here) – Free technical guidance for IT administrators.
- [Teams upgrade planning workshops](upgrade-workshops-landing-page) – Free interactive upgrade planning workshops that provide guidance, best practices, and resources designed to help you plan and implement your upgrade to Teams.
- [Assisted upgrades from Skype for Business Online to Microsoft Teams](upgrade-assisted) – Automated program that assists you with upgrading Skype for Business Online users to Teams.
- [FastTrack for Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams deployment assistance available for qualifying plans.
- [Teams training](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) – Free online training videos designed to get your organization up and running with Teams.
- [Microsoft Partners](https://www.microsoft.com/solution-providers/home) – Microsoft solution providers can help you take full advantage of Teams.
- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Teams news about new features, adoption and usage resources, Teams devices, and integration with other business applications.

If you’re a current Skype for Business Online customer, start planning your upgrade to Teams today. We’re excited for you to experience its powerful communication and collaboration capabilities, and we’re committed to helping along the way. For more information about the Skype for Business Online retirement, see [FAQ—Upgrading from Skype for Business to Microsoft Teams](faq-journey).