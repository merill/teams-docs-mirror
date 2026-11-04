---
layout: Conceptual
title: Teams calling and cloud voice overview - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cloud-voice-landing-page
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
description: Learn about Teams calling with Microsoft cloud voice services in Microsoft 365.
locale: en-us
document_id: a1fa33a8-d910-caee-89ad-62f449a6072f
document_version_independent_id: 2b33ed7d-da28-f5d0-d5ff-d2e72effa3d7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/cloud-voice-landing-page.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cloud-voice-landing-page
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/cloud-voice-landing-page.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f15881bf-9398-04f7-3e2c-95eb6d756afc
---

# Teams calling and cloud voice overview - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![](/en-us/skypeforbusiness/media/yes.png) 2015 ![](/en-us/skypeforbusiness/media/yes.png) 2019 ![](/en-us/skypeforbusiness/media/yes.png) Subscription Edition

This article is for IT administrators and IT professionals who are researching and planning the calling workloads in Microsoft Teams.

## Native Teams calling

Microsoft Teams is a Microsoft 365 application for communication and collaboration. It includes support for native 1:1 calling *and* group calling, from one Teams client to any other internal or external Teams clients.

Native calls between Teams clients are processed by Microsoft 365 Teams cloud services and include unlimited calling.

The Calls app in Teams allows users to originate calls to other Teams users, view call history, and access voicemail that is automatically set up for all Teams users.

Users can use a wide range of features to call each other. For example, they can select a name in their address book and place Teams calls to that person. They can transfer calls to other users, and set up distinctive rings. They make and receive calls using Teams on their mobile devices, on a laptop or PC with a headset, or one of many certified, third-party phone devices.

With the addition of a Public Switched Telephone Network (PSTN) connection to your tenant and Teams Phone licensing for your users, Teams calling also supports making and receiving external telephone calls and a rich set of enterprise-grade, telephone system features.

For more insight on Teams calling features, see [What is Teams Phone](what-is-phone-system-in-office-365) and [Teams calling features](here-s-what-you-get-with-phone-system).

Note

Calling is controlled at the tenant level, per calling policy with the setting [Make private calls](settings-policies-reference). If the **Make private calls setting** is turned off in the calling policy, users with that policy can't see the **Calls** app in their Teams client, can't escalate Chat conversations to audio calls, and can't receive incoming calls.

With **Make private calls setting** turned on, users can call from the **Calls** app and can escalate Chat conversations to audio calls. By default, Microsoft Teams native calling is turned on via policy for all users.

Note

All users licensed for Teams can make calls to other Teams users. To support users making Teams calls with other Teams users who are *external* to your organization, see [Collaborate with people outside your organization](communicate-with-users-from-other-organizations).

## Administering Teams calling

When planning to support Teams calling in your enterprise, consider the following topics to help you with your administrative duties:

### Administration methods

Delivery of the Teams calling workload is accomplished through the Microsoft 365 cloud service, and administrators manage the delivery of Teams calling and other Teams workloads and features through remote management of that cloud service.

#### Access

You can access your tenant and administer Teams Calling and other Teams related workloads using two methods:

- **Teams admin center**

    - For Commercial and Government Community Cloud (GCC) tenants, access Teams admin center via https://admin.teams.microsoft.com
    - For Government Community Cloud High (GCCH) tenants, access Teams admin center via [https://admin.gov.teams.microsoft.us](https://admin.gov.teams.microsoft.us/)
- **PowerShell**

    - To learn more about connecting to Teams and administering users, policies, and more with Teams PowerShell, see [Teams PowerShell overview](teams-powershell-overview).
- **Microsoft Graph Explorer**

    - To learn more about working with data in Microsoft Graph using Graph Explorer, see [Use Graph Explorer](/en-us/graph/graph-explorer/graph-explorer-overview).

#### Teams admin center overview

To learn more about general guidance for administering the Teams admin center, see the following article.

#### Access permissions

To administer Teams features, you must use a privileged role assigned to the account that's used to access your Teams tenant. To learn more about permissions that allow you to administer your tenant (with Teams admin center and with PowerShell) and about Microsoft's RBAC (Role Based Access Control) for Teams, see the following article.

### Policies

Microsoft Teams Phone supports a wide array of features that you control by policy. For example, traditional calling features, like call hold music, call park, call recording, and more, are all administered through policy. Policies can be applied at a global, group, and user level.

#### Teams policy management

To learn about general Teams policy administration concepts, see the following article.

#### Voice specific policies

For more information about voice settings that you can manage with Teams policy, see the following article.

### Network

For network best practices and to ensure it supports the optimal quality of Teams calls, see the following article.

### Reporting users' call activity

Native Teams *call history* for end-users, like other end-user activity, isn't itemized in usage reports for privacy reasons. However, with Microsoft Purview, Teams call metadata can be logged in eDiscovery investigations. To learn more about content reported in compliance investigations, see [Conduct an eDiscovery investigation of content in Microsoft Teams](/en-us/microsoft-365/compliance/ediscovery-teams-investigation).

For more generic insights, you can report on the overall volume of *call activity* in the following article.

### Reporting call quality performance

Microsoft Teams includes a set of tools that can be used to analyze call quality in real-time for single calls in progress or analyze performance trends of all calls across your organization. For more information on these tools to monitor call performance and quality, see the following article.

### Teams admin training

A wide range of resources are available for Teams administrators to learn more about Teams foundational and advanced topics. To view training resources for Teams admins, see the following article.

## Teams Phone and enterprise telecommunications

In addition to a rich set of native calling capabilities, Teams can also serve as your organization's telecommunications platform, allowing your end users to make and receive domestic and international telephone calls.

To learn more about using Teams as a phone system, see the following article.