---
layout: Conceptual
title: Guest access in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/guest-access
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: manish.jaisinghani
ms.date: 2026-07-16T00:00:00.0000000Z
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.guestaccess.overview
- chat-teams-channels-revamp
- guest-access-external-collab
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
description: Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.
locale: en-us
document_id: 2492e210-08f9-a476-97ec-008926def961
document_version_independent_id: adcb0dd9-4a3c-b665-6e34-ce3276c89b4d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/guest-access.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: guest-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/guest-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 82e2001b-4284-0eb7-005b-2d665c236e93
---

# Guest access in Microsoft Teams - Microsoft Teams | Microsoft Learn

With guest access, you can provide access to teams, documents in channels, resources, chats, and applications to people outside your organization, while maintaining control over your corporate data. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams. If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](/en-us/previous-versions/microsoft-365/solutions/collaborate-as-team).

Important

All Guests must be added to at least one Team before guest access features and functionality will be available to the guest account. [Learn more](https://support.microsoft.com/office/add-guests-to-a-team-in-microsoft-teams-fccb4fa6-f864-4508-bdde-256e7384a14f).

Note

If you just want to find, call, chat, and set up meetings with people in other Microsoft 365 organizations, use [external access](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings).

When you invite a guest to Teams, a guest account is created for them in Microsoft Entra ID and they're covered by the same compliance and auditing protection as other Microsoft 365 users. With Microsoft Entra B2B collaboration, you can enforce conditional access and multifactor authentication (MFA) policies for B2B users. These policies can be enforced at the organization, app, or individual user level, the same way that they're enabled for people inside your organization. For more information, see [Authentication and Conditional Access for External Identities](/en-us/azure/active-directory/external-identities/authentication-conditional-access). Guest access is subject to Microsoft Entra ID and Microsoft 365 service limits.

In Teams, guests are clearly identified. A guest's name includes the label **(Guest)**, and a channel includes an icon to indicate that there are guests on the team. For more information, see [What the guest experience is like](/en-us/microsoftteams/guest-experience).

Guests can leave the team at any time from within Teams. For details, see [How do I leave a team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076). (Leaving the team doesn't remove the guest account from your organization's directory. Your Microsoft Entra admin must remove the guest account.)

The guest experience has limitations by design. For a full list of what a guest can and can't do in Teams, see [Guest experience in Microsoft Teams](/en-us/microsoftteams/guest-experience).

Note

Shared channels offer an alternative to guest access, allowing you to invite people outside your organization without requiring a guest account in Microsoft Entra ID. To compare guest access with shared channels, see [Plan external collaboration](/en-us/microsoft-365/solutions/plan-external-collaboration).

## Guest invitation process

Team owners can add guests to a team in the Teams client. To learn more, read [Add guests to a team](https://support.office.com/article/fccb4fa6-f864-4508-bdde-256e7384a14f).

Teams Administrators can also add guests to a team in the Teams admin center.

Guests you already added via Microsoft Entra B2B, Microsoft 365 Groups, or SharePoint are ready to go. Team owners can add those guests to their teams. If you add a guest directly to the Microsoft 365 group associated with a team, the guest gets access to the team. However, the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.

After a guest is added to a team, it can take up to 12 hours for them to have access.

You can delegate the ability to add guests to specific people in your organization by assigning the Guest Inviter role. For more information, see [Limit who can invite guests](/en-us/microsoft-365/solutions/limit-who-can-invite-guests).

The guest invitation process works as follows:

1. A team owner adds a guest to a team.
2. The guest receives a welcome email from the team owner, with information about the team and what to expect now that they're added.
3. The guest accepts the invitation. Guests who have a work or school account in Microsoft Entra ID can accept the invitation and authenticate directly. Other users are sent a one-time pass code to validate their identity ([One-time passcode authentication](/en-us/azure/active-directory/external-identities/one-time-passcode) required).
4. After accepting the invitation, the guest can participate in teams and channels, receive and respond to channel messages, [access files in channels](https://support.office.com/article/c593c78a-27c4-4661-a598-682baa30ca7e), participate in chats, join meetings, collaborate on documents, and more.

## Set up guest access

Guest access in Teams is an organization-wide setting. You can control guest access to individual teams by using [sensitivity labels](/en-us/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Guest access in Teams requires configuring other settings in Microsoft 365, including settings in Microsoft Entra ID, Microsoft 365 Groups, and SharePoint. If you're ready to start inviting guests to teams, read one of the following articles:

- To configure guest access for Teams for general use, see [Collaborate with guests in a team](/en-us/previous-versions/microsoft-365/solutions/collaborate-as-team).
- To collaborate with a partner organization that uses Microsoft Entra ID and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](/en-us/microsoft-365/solutions/b2b-extranet).

See [Set up secure collaboration with Microsoft 365 and Microsoft Teams](/en-us/microsoft-365/solutions/setup-secure-collaboration-with-teams) for overall information about secure collaboration using Teams.

## Licensing for guest access

Guest access can be used with all Microsoft 365 Business Standard, Microsoft 365 Enterprise, and Microsoft 365 Education subscriptions. No extra Microsoft 365 license is necessary. The [billing model for Microsoft Entra External ID](/en-us/azure/active-directory/b2b/licensing-guidance) applies to guests in Microsoft 365. Only people from outside your organization can be invited as guests.

Guests are subject to [Microsoft 365 or Office 365](/en-us/office365/servicedescriptions/office-365-service-descriptions-technet-library) and [Microsoft Entra ID](/en-us/office365/servicedescriptions/azure-active-directory) service limits.

## Diagnosing issues with Guest Access

To troubleshoot issues with inviting guests in Teams, administrators can run a diagnostic tool in the Microsoft 365 admin center to validate that guest access is correctly configured for use in Teams.

1. Select the following text "**Run Tests**" to populate the diagnostic in the Microsoft 365 admin center.
2. The test results tell you if the tenant is configured correctly for guest access. If the tenant isn't configured correctly, the diagnostic provides information on what steps to take to address issues with the configuration.

## Tracking guests in your organization

You can track guest additions in Microsoft Entra ID or the Microsoft 365 security center. Adding a guest in Teams is audited and logged as a Microsoft Entra group administration activity "Added member to group." For more information, see [Auditing and reporting a B2B collaboration user](/en-us/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log](/en-us/purview/audit-new-search).

### Guest access reviews

You can use Microsoft Entra ID to create an access review for users who are in groups or teams or assigned to an application. Creating recurring access reviews can save you time. If you need to routinely review users who have access to an application, a team, or a group, you can define the frequency of those reviews.

You can perform a guest access review yourself, ask guests to review their own access, or ask an application owner or business decision maker to perform the access review. Reviews are done in Microsoft Entra ID. For more information, see [Manage guest access with Microsoft Entra access reviews](/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).