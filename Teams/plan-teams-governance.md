---
layout: Conceptual
title: Plan for governance in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/plan-teams-governance
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: reference
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: rowille
ms.date: 2018-07-27T00:00:00.0000000Z
audience: admin
description: In this article, you will learn about how to plan for implementing governance capabilities in Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 20c43928-84c0-0a75-9354-66aef3b83e46
document_version_independent_id: f95298ae-de58-02eb-0b49-8390ab161d4c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/plan-teams-governance.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: plan-teams-governance
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/plan-teams-governance.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1d77889b-7182-c615-3c0d-37096f2a2772
---

# Plan for governance in Teams - Microsoft Teams | Microsoft Learn

Teams provides a rich set of tools to implement any governance capabilities your organization might require. This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.

Tip

Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)

## Group and team creation, naming, classification, and guest access

Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams. You can configure these areas by using Microsoft Entra ID and sensitivity labels.

| - | - | - |
| --- | --- | --- |
| ![An icon depicting decision points](media/audio_conferencing_image7.png) | Decision points | - Does your organization require a specific naming convention for teams?<br>- Do team creators need the ability to assign organization-specific classifications to teams?<br>- Do you need to restrict the ability to add guests to teams on a per-team basis?<br>- Does your organization require limiting who can create teams? |
| ![An icon depicting the next steps](media/audio_conferencing_image9.png) | Next steps | - Document your organization’s requirements for team creation, naming, classification, and guest access.<br>- Plan to implement these requirements as a part of your Teams rollout.<br>- Communicate and publish your policies to inform Teams users of the behavior they can expect. |

Note

To help you plan ahead, [learn more about setting these policies and what licenses they require](/en-us/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).

Note

Limiting group and team creation can slow your users’ productivity, because many Microsoft 365 and Office 365 services require that groups be created for the service to function. For additional information, visit [Plan for governance in Teams](/en-us/microsoft-365/solutions/manage-creation-of-groups).

#### Additional information

After you’ve determined your requirements, you can implement them by using Microsoft Entra ID controls. For technical guidance on how to implement these settings, see:

- [Microsoft Entra cmdlets for configuring group settings](/en-us/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
- [Enforce a naming policy for Microsoft 365 groups in Microsoft Entra ID](/en-us/azure/active-directory/users-groups-roles/groups-naming-policy)
- [Microsoft 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)
- [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
- [End of lifecycle options for groups, teams, and Viva Engage](/en-us/microsoft-365/solutions/end-life-cycle-groups-teams-sites-viva-engage)

## Group and team expiration, retention, and archiving

Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files). You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active. Note that teams that are archived continue to have the expiration policy applied and may be deleted unless excluded or renewed.

| - | - |
| --- | --- |
| ![An icon depicting decision points.](media/audio_conferencing_image7.png)Decision points | - Does your organization require specifying an expiration date for teams?<br>- Does your organization require specific data retention policies be applied to teams?<br>- Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state? |
| ![An icon depicting the next steps.](media/audio_conferencing_image9.png)Next steps | - Document your organization’s requirements for team expiration, data retention, and archiving.<br>- Plan to implement these requirements as part of your Teams rollout.<br>- Communicate and publish your policies to inform Teams users of the behavior they can expect. |

Tip

Use the following table to capture your organization’s requirements.

| Capability | Details | Microsoft Entra ID P1 or P2 license required | Decision |
| --- | --- | --- | --- |
| Expiration policy | Manage the lifecycle of Microsoft 365 groups by setting an expiration policy. | P1 | TBD |
| Retention policy | Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center. **Note**: Using this feature requires licensing of Microsoft 365 or Office 365 Enterprise E3 or above. | No | TBD |
| Archive and restore | Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future. | No | TBD |

Note

Group expiration is a Microsoft Entra ID P1 or P2 feature. For this feature to be available, your tenant must have a subscription to Microsoft Entra ID P1 or P2 and licenses for the administrator who configures the settings and the members of the affected groups.

#### Additional information

For technical guidance on how to implement these settings, see:

- [Set up Microsoft 365 groups expiration](/en-us/azure/active-directory/users-groups-roles/groups-lifecycle).
- [Set up Teams retention policies](retention-policies).
- [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## Group and team membership management

Consistently managing members of project based, or restricted groups are necessary for teams that require rapid onboarding and offboarding or users and guests. Your organization may also need to make sure all current members have the business justification to be in a team. Managing members can be hard because team owners can leave and users don’t usually leave groups on their own accord when a project ends or when they change roles. The best way to manage group membership that allows users to get access when needed but ensure the group doesn't have a risk of inappropriate access is through two district processes: entitlement management and access reviews.

[Entitlement management](/en-us/azure/active-directory/governance/entitlement-management-overview) allows you to delegate to someone, such as a project manager, to collect all the resources that are needed, including teams memberships, into a single package. They can also define who can make requests: either users in your tenant or from other connected organizations. The project manager will receive access requests in their email and approve or deny requests in the MyAccess portal. Administrators can configure the conditions of access to include an expiry date or period by when the user or guest will be removed from the team unless access is renewed. Administrators can also set up the groups associated with teams to take part in access reviews. For [access reviews](/en-us/azure/active-directory/governance/access-reviews-overview), the group owners will receive regular reminders to review the members of a team. Access reviews include recommendations, which makes it easier for group owners to go through their regular attestation process.

| - | - | - |
| --- | --- | --- |
| ![An icon depicting decision points](media/audio_conferencing_image7.png) | Decision points | Does your organization require a consistent process for managing membership of one or more teams?  Does your organization require owners, or the members themselves, to justify their continued membership of one or more teams on a regular basis?  Does your organization require approval for users and guests to request access to resources including teams, groups, SharePoint sites, and apps? |
| ![An icon depicting the next steps](media/audio_conferencing_image9.png) | Next steps? | Document your organizations requirements for each team or specific teams for membership expiry.Plan how your organization can bundle teams, groups, SharePoint sites, and apps together in access packages.Plan which people, such as the requestor's manager, a project manager, a sponsor for a connected organization or a security officer in your organization will need to approve or deny access requests. |

Tip

Use the following table to capture your organization’s requirements.

| Capability | Details | Microsoft Entra ID P1 or P2 license required | Decision |
| --- | --- | --- | --- |
| Access reviews | Setup access reviews to recertify the membership of specific teams at regular interval | P2 | TBD |
| Entitlement management | Setup access package to allow users and guests to request access to teams | P2 | TBD |

Note

To help you plan ahead, [learn more about what licenses they require](https://azure.microsoft.com/pricing/details/active-directory/).

### Additional information

For technical guidance on how to implement these settings, see:

- [Entitlement management](/en-us/azure/active-directory/governance/entitlement-management-overview)
- [Access reviews](/en-us/azure/active-directory/governance/access-reviews-overview)

## Teams feature management

Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to. You can manage messaging, meeting, and calling features, either at the Microsoft 365 or Office 365 organization level or per-user.

| - | - |
| --- | --- |
| ![An icon depicting decision points.](media/audio_conferencing_image7.png)Decision points | - Does your organization require limiting Teams features for your entire tenant?<br>- Does your organization require limiting Teams features for specific users? |
| ![An icon depicting the next steps.](media/audio_conferencing_image9.png)Next steps | - Document your organization’s requirements for limiting Teams features at the tenant and user level.<br>- Plan to implement your specific requirements as part of your Teams rollout.<br>- Communicate and publish your policies to inform Teams users of the behavior they can expect. |

### Teams feature management focus areas

Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies. Different policies can be applied to all users by default or per user as required by your organization.

For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:

- [Manage Microsoft Teams settings for your organization](enable-features-office-365)
- [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center)
- [Private channels in Microsoft Teams](private-channels)
- [Shared channels in Microsoft Teams](shared-channels)
- [Manage meeting policies in Teams](meeting-policies-overview)
- [Manage messaging policies in Teams](messaging-policies-in-teams)
- [Manage your apps in the Microsoft Teams admin center](manage-apps)

Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them. See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams) for more information.

## Security and compliance

Teams is built on the advanced security and compliance capabilities of Microsoft 365 and Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.

Important

If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview).