---
layout: Conceptual
title: Teams Phone licensing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-phone-licensing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: roykuntz
ms.date: 2026-04-28T00:00:00.0000000Z
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.topic: get-started
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- intro-overview
description: Applying Teams Phone licensing.
locale: en-us
document_id: f429f0d5-2bb7-88b3-6ed3-5fee734bd437
document_version_independent_id: f429f0d5-2bb7-88b3-6ed3-5fee734bd437
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-phone-licensing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-phone-licensing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-phone-licensing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 8327f4a0-1752-3e69-73d2-4bfe39a0d9b6
---

# Teams Phone licensing - Microsoft Teams | Microsoft Learn

This article is for IT administrators and IT professionals who are managing Teams Phone workloads for an organization and want to understand the scenarios of assigning licenses to user and resource accounts.

To learn more about Teams Phone, see [What is Teams Phone](what-is-phone-system-in-office-365) and [Teams Phone feature overview](here-s-what-you-get-with-phone-system).

The article sections include the following:

- Understanding identity management for Teams Phone
- Understanding Microsoft 365 licensing and applications
- Licensing Teams Phone - for end users
- Licensing Teams Phone - for shared devices
- Licensing Teams Phone - for voice applications
- Licensing Teams Phone - adding PSTN
- Licensing Teams Phone - for Shared Calling
- Considerations

### Understanding identity management for Teams Phone

One of the most important, uniquely-identifiable records used in Microsoft Teams administration is the user account.

#### User accounts

User accounts are the sets of data that define your end-users in Microsoft cloud services.

In Microsoft Teams, user accounts are inherited from and synchronized with Microsoft 365, where user accounts are created, licensed, and managed. Accounts that are created in Microsoft 365 are also synchronized with Microsoft Entra ID for identity and access management.

To learn more about creating accounts in Microsoft 365, see [Add users](/en-us/microsoft-365/admin/add-users/add-users).

To learn more about identities in Microsoft Entra ID, see [What is Microsoft Entra ID?](/en-us/entra/fundamentals/whatis).

Administering, or creating and editing user accounts and assigning licenses requires the Microsoft 365 *User admin* role. To learn more, see [About admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles).

It is important to understand Microsoft 365 identity management and user account coexistence in all of the Microsoft cloud services, because delivering Teams capabilities to your end-users involves creating users and assigning licenses in Microsoft 365 admin center (MAC), while assigning Teams Phone policies and telephone numbers in the Teams admin center (TAC).

#### Resource accounts

In Teams, specialized accounts are designed for voice applications, like Auto Attendants and Call Queues.

These specialized accounts have a limited set of specific parameters compared to normal user accounts, and are called '*Resource accounts*'.

Teams resource accounts support Teams voice applications, only, and are disabled for end-users--they can't be used to login to Microsoft 365 applications.

### Understanding Microsoft 365 licensing and applications

The first step in delivering Teams capabilities to your organization is to assign appropriate licensing to the intended Microsoft 365 user and resource accounts.

Granting a user or resource account with permissions to use *a Microsoft 365* ***application*** is accomplished by assigning *a Microsoft 365* ***license*** to their account.

For example, if you need to set up an existing Teams user with permissions to use Teams as their phone system, your first step is to assign their user account with a license that grants them permission to use the **Microsoft 365 Phone System** application.

There are several ways to license a user account so that it can use the **Microsoft 365 Phone System** application. For more information, see Licensing Teams Phone for end users.

To learn more about assigning licenses in Microsoft 365, see the following resources.

- [Assign Microsoft 365 licenses to user accounts](/en-us/microsoft-365/enterprise/assign-licenses-to-user-accounts)
- [Assign or unassign licenses for users](/en-us/microsoft-365/admin/manage/assign-licenses-to-users)
- [Manage Teams licenses](user-access)

### Licensing Teams Phone - for end users

All users who require their own telephone number to make and receive telephone calls must be assigned with licensing that includes the **Microsoft Teams** and **Microsoft 365 Phone System** applications.

There are several license assignment combinations available to meet the requirement.

Assigning the following license combinations are just a few examples that grant end users the ability to use Teams Phone.

- A ***Microsoft Teams Enterprise*** license combined with a ***Microsoft 365 E5 (no Teams)*** license - *Microsoft 365 E5 (no Teams)* includes the **Microsoft 365 Phone System** application
- A ***Microsoft Teams Enterprise*** license combined with ***Microsoft Teams Phone Standard*** license
- A legacy ***Microsoft 365 E5*** license - includes **Microsoft Teams** and **Microsoft 365 Phone System** applications
- A ***Office 365 F3*** license combined with a ***Microsoft Teams Phone Standard for Frontline Workers*** license

In the case where any Microsoft 365 E5 license is used, it isn't necessary to also assign the stand-alone ***Microsoft Teams Phone Standard*** license.

There are three variations on the ***Microsoft Teams Phone Standard*** license, each requiring the purchase of a Prerequisite License as listed in the following table:

| **License** | **Prerequisite License(s)** |
| --- | --- |
| Microsoft Teams Phone Standard | Microsoft 365 Business Basic/Business Standard/Business Premium/F1/F3/E3/A3; Microsoft Teams EEA; Microsoft Teams Enterprise; Microsoft Teams Essentials (AAD Identity); Office 365 F3/E1/E3/A1/A3 |
| Microsoft Teams Phone Standard for Frontline Workers | Microsoft 365 F1/F3; Office 365 F3 |
| Microsoft Teams Phone with Calling Plan | Microsoft 365 Business Basic/Business Standard/Business Premium/F1/F3/E3/A3; Microsoft Teams EEA; Microsoft Teams Enterprise; Microsoft Teams Essentials (AAD Identity); Office 365 F3/E1/E3/A1/A3 |

To learn more about licensing for Teams Phone, see [Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).

### Licensing Teams Phone - for shared devices

In scenarios requiring that phone calls can be made to or from communication devices shared by many users, you can use one of the following specialized licenses:

- [***Microsoft Teams Shared Device*** license](phones/phones-for-teams) - *applied to users accounts that are created to support common area telephones*
- [***Microsoft Teams Room Pro*** license](rooms/rooms-licensing) - *applied to user accounts that are created to support Microsoft Teams Rooms and audio/video hardware for shared collaboration spaces*

The **Microsoft 365 Phone System** application is included in each of these specialized, shared device licenses.

For a deeper dive, see [Microsoft Teams Shared Devices licensing](teams-add-on-licensing/teams-shared-device-license).

### Licensing Teams Phone - for voice applications

In scenarios where you're provisioning voice applications, like Auto Attendants and Call Queues, use the following specialized license:

[Microsoft Teams Phone Resource Account license](teams-add-on-licensing/virtual-user)

To learn more about obtaining this license, creating a resource account, and more, see [Obtain Microsoft Teams Phone Resource Account license](aa-cq-manage-resource-accounts#obtain-microsoft-teams-phone-resource-account-licenses).

### Licensing Teams Phone - adding PSTN

Assigning necessary licenses to an account is one prerequisite to setting up Teams Phone. Another key prerequisite is integrating your tenant with a Public Switched Telephone Network (PSTN) solution.

With PSTN access to your tenant and licensed users, Microsoft Teams Phone provides support for 1:1 calling and group calling between a Teams client--and any PSTN telephone number.

Note

A PSTN solution is separate from a Teams Phone license. A **PSTN solution** provides a customer's tenant with phone numbers and PSTN access to domestic, international, and emergency calling. The ***Teams Phone licensing*** entitles a Teams user to use **Microsoft 365 Phone System** application and its enhanced calling capabilities, and *access* to the PSTN solution.

If you elect to use Microsoft to provide your PSTN access and phone numbers, in addition to Teams Phone licensing, the user also requires a Microsoft Calling Plan license. To learn more, see [Microsoft Calling Plans](calling-plans-for-office-365).

If you have India PSTN requirements, a separate, India-specific Microsoft Teams Phone license from a licensed telecom operator in India is required. See [Plan Operator Connect for India](operator-connect-india-plan).

If you elect to use a PSTN operator other than Microsoft, then Microsoft doesn't require other licensing because the PSTN costs are incurred from your preferred operator.

To learn more, see [PSTN connectivity options](pstn-connectivity).

The ***Teams Phone with Calling Plan*** license bundle is Microsoft’s all-in-the-cloud solution. This option provides Private Branch Exchange (PBX) capabilities and external calls to the Public Switched Telephone Network (PSTN) with Microsoft as your carrier. If the Teams Phone with Calling Plan bundle is available in your location and you don't already have a ***Microsoft 365 E5*** or ***Office 365 E5*** license that includes the **Microsoft 365 Phone System** application, you should consider this option. But if your PSTN calling requirements are more complex, Microsoft supports several third-party PSTN connectivity options for making external calls.

### Licensing Teams Phone - for Shared Calling

Microsoft Teams can support multiple users sharing a single phone number. In this scenario, a resource account is provisioned with Teams Phone and a telephone number, and then you grant a policy to users that allows them to access the phone number of the licensed resource account to make outbound calls.

With Shared Calling, end users don't need a dedicated phone number or a calling plan. They only require a license for Teams Phone, as described in Licensing Teams Phone for end users.

Shared Calling is a cost-effective way to give users a way to make outbound calls, without allocating a calling plan and a phone number to every user. If a Microsoft service number is used for the Shared Calling resource account, then the Shared Calling resource account requires a Microsoft pay-as-you-go calling plan license assigned.

To learn more about Shared Calling, see [Plan for Shared Calling](shared-calling-plan).

### Considerations

Licensing for the **Microsoft Teams Enterprise** application isn't required when Licensing Teams Phone for shared devices and Licensing Teams Phone for voice applications.

***Microsoft Teams Shared Device*** licenses are supported only for telephone devices.

For more information about licenses to use with Teams, see [Teams add-on license options](teams-add-on-licensing/microsoft-teams-add-on-licensing).

For next steps, see [Set up Teams Phone](setting-up-your-phone-system).