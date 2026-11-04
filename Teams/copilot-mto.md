---
layout: Conceptual
title: Manage Copilot access for B2B members within multitenant organizations (MTO) in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/copilot-mto
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.date: 2024-12-30T00:00:00.0000000Z
ms.update-cycle: 180-days
author: DaniEASmith
ms.author: danismith
manager: jtremper
ms.reviewer: sadafbadar
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.tgt.pltfrm: cloud
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- magic-ai-copilot
ms.custom:
- admindeeplinkTEAMS
description: Learn how to manage B2B members' access within Multitenant Organization (MTO) for Copilot features in Teams.
locale: en-us
document_id: d31ff958-f4e5-83cb-eb81-60fa5050b04b
document_version_independent_id: d31ff958-f4e5-83cb-eb81-60fa5050b04b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/copilot-mto.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-mto
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/copilot-mto.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: f8b28e14-0abd-2119-5d30-c8d0687f9421
---

# Manage Copilot access for B2B members within multitenant organizations (MTO) in Teams - Microsoft Teams | Microsoft Learn

Important

The support discussed in this article is only available to B2B members within the multitenant organization. It isn't available to external or federated users.

Copilot in Teams enhances users’ day-to-day work with features like AI-generated summaries in chats and suggested action items after a meeting. Microsoft now supports **B2B member access** to Copilot in Teams for licensed users in multitenant organizations to ensure they never lose access to Copilot’s benefits in Team channels and meetings.

**B2B member access** lets people in your org collaborate with members of other organizations in an external Microsoft Entra organization. This access is done by using Microsoft Entra External ID for business-to-business (B2B) collaboration and granting member-level access to Teams channels, meetings, and other resources in your org. For more information about B2B collaboration, see [B2B collaboration](/en-us/entra/external-id/user-properties).

Note

B2B member access is possible only when both organizations allow access to and from each other. Therefore, you need to coordinate with the external organization’s admin to make sure their cross-tenant access settings allow sharing with you. For more information about cross-tenant access settings, see [Overview: Cross-tenant access with Microsoft Entra External ID](/en-us/entra/external-id/cross-tenant-access-overview).

Teams admins can toggle off and on the **Allow Copilot for B2B members** setting in the Teams admin center or with PowerShell. This setting is turned on by default, allowing external members from other organizations who have Copilot licenses to use Copilot when they join meetings hosted by your organization.

## Manage B2B member access to Copilot in the Teams admin center

1. Sign in to the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) using your admin credentials.
2. Expand **Users** from the left-side navigation pane.
3. Under **Users**, select **B2B member access**.
4. Either select an existing policy or create a new one.
5. Toggle the **Allow Copilot for B2B members** setting **On** or **Off**.
6. Select the **Save** button.

## Manage B2B member access to Copilot using PowerShell

The **Allow Copilot for B2B members** setting can also be managed using PowerShell with the [Get-CsTeamsMultiTenantOrganizationConfiguration](/en-us/powershell/module/teams/get-csteamsmultitenantorganizationconfiguration) and [Set-CsTeamsMultiTenantOrganizationConfiguration](/en-us/powershell/module/teams/set-csteamsmultitenantorganizationconfiguration) cmdlets.

To learn how to manage Teams settings using PowerShell, see [Manage Teams with Microsoft Teams PowerShell](teams-powershell-managing-teams).

### Sample scripts

Retrieve your multitenant organization’s Teams configuration by using the following code:

```powershell
Get-CsTeamsMultiTenantOrganizationConfiguration 
```

Turn off the **Allow Copilot for B2B members** setting by using the following code:

```powershell
Set-CsTeamsMultiTenantOrganizationConfiguration -Identity Global -CopilotFromHomeTenant Disabled  
```

Turn on the **Allow Copilot for B2B members** setting by using the following code:

```powershell
Set-CsTeamsMultiTenantOrganizationConfiguration -Identity Global -CopilotFromHomeTenant Enabled  
```