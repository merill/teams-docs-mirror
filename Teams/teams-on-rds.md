---
layout: Conceptual
title: Using Teams client with remote desktop services - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-on-rds
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: alivano
ms.date: 2025-09-03T00:00:00.0000000Z
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
description: Learn how to use Microsoft Teams with remote desktop services.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
locale: en-us
document_id: 26b8d73b-187d-a76c-5502-91d686a5e34f
document_version_independent_id: 26b8d73b-187d-a76c-5502-91d686a5e34f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-on-rds.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-on-rds
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-on-rds.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ddab3cd8-636f-4a91-896e-1c23f399a6bd
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f409bb5d-e203-40c5-9d95-0ee717231beb
platformId: e3840392-23c8-18b5-e5f4-1e903eb0deb1
---

# Using Teams client with remote desktop services - Microsoft Teams | Microsoft Learn

This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment. Only Windows Server 2022 and 2025 are supported.

## What is RDS?

Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need. RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.

RDS offers deployment flexibility, cost efficiency, and extensibility. RDS is delivered through a variety of deployment options, including Windows Server for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions. Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI), or as a combination of the two.

Important

Teams in a remote desktop services environment is only supported for collaboration and chat functionality. Multimedia workloads aren't supported, since they're not optimized or offloaded to the endpoint. Non-optimized calling and meeting capabilities default to server-side rendering, providing a degraded experience. We recommend customers on RDS turn off calling and meeting functionality, as explained in this article.

## Teams on RDS with chat and collaboration

If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.

### Set policies to turn off calling and meeting functionality

Use the Microsoft Teams admin center or PowerShell to set policies. It might take some time (a few hours) for the policy changes to propagate. If you don't see changes for a given account immediately, try again in a few hours.

[**Calling polices**](teams-calling-policy): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off. Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.

[**Meeting policies**](meeting-policies-overview): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off. Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.

#### Assign policies using the Microsoft Teams admin center

To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:

1. In the left navigation of the Microsoft Teams admin center, go to **Users**.
2. To choose a user, select to the left of the user name, and then select **Edit settings**.
3. Take the following steps:

    a. Under **Calling policy**, select **DisallowCalling**.

    b. Under **Meeting policy**, select **AllOff**.
4. Select **Apply**.

To assign a policy to multiple users at a time:

1. In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.
2. In the **✓** (check mark) column, select the users. To select all users, select the ✓ (check mark) at the top of the table.
3. Select **Edit settings**, make the changes you want, and then select **Apply**.

Or, you can also do the following steps:

1. In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign. For example:

    - Go to **Voice** &gt; **Calling policies**, and then select **DisallowCalling**.
    - Go to **Meetings** &gt; **Meeting policies**, and then select **AllOff**.
2. Select **Manage users**.
3. In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**. Repeat this step for each user you want to add.
4. When you're finished adding users, select **Save**.

#### Assign policies using PowerShell

The following example shows how to use the [Grant-CsTeamsCallingPolicy](/en-us/powershell/module/teams/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/en-us/powershell/module/teams/set-csteamscallingpolicy).

The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy).