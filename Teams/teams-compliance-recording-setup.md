---
layout: Conceptual
title: Set up compliance recording in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-compliance-recording-setup
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: yasmineh
ms.date: 2026-07-20T00:00:00.0000000Z
audience: admin
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: kkodali
description: Learn how to set up compliance recording for calling, meetings, events in Microsoft Teams.
ms.collection:
- M365-collaboration
locale: en-us
document_id: d29260e5-a358-863b-1880-6bdec5e293fa
document_version_independent_id: d29260e5-a358-863b-1880-6bdec5e293fa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-compliance-recording-setup.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-compliance-recording-setup
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-compliance-recording-setup.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 790acbab-1432-3cf8-9ad0-bacb2d36613c
---

# Set up compliance recording in Microsoft Teams - Microsoft Teams | Microsoft Learn

To use a compliance recording solution with Microsoft Teams, admins must create a compliance recording application instance and configure compliance recording policies. These policies determine which users are recorded and which recorder is used for their communications in Teams calls, meetings, and events.

This article describes how to create an application instance, create a compliance recording policy, and assign the policy to users.

## Create a compliance recording application instance

Create an application instance in your tenant.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
```

Example results

- RunspaceId : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
- ObjectId : 5069aae5-c451-4983-9e57-9455ced220b7
- TenantId : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
- UserPrincipalName : cr.instance@contoso.onmicrosoft.com
- ApplicationId : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
- DisplayName : ComplianceRecordingBotInstance
- PhoneNumber :

```powershell
Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
```

Contact your compliance recording provider to get their application Id.

## Create and manage your compliance recording policy

Once a compliance recording solution is in place, you can create and assign recording policies to control which users are recorded and which recorder is used for each user. Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.

Use [Microsoft Teams PowerShell](teams-powershell-overview) to manage compliance recording policies. You can apply policies at the tenant, per-user, and security group level for your organization. For more information, see the Microsoft Learn articles on [meeting policies](meeting-policies-overview), [calling policies](teams-calling-policy), and [policy assignment to groups](assign-policies-users-and-groups#assign-a-policy-to-a-group).

1. Create a compliance recording policy.

    ```powershell
    New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"
    ```

    Example results

    - Identity : Global
    - ComplianceRecordingApplications : {}
    - Enabled : True
    - WarnUserOnRemoval : True
    - Description : Test policy created by tenant admin

    ```powershell
    Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
    -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
    ```

    See [Set-CsTeamsComplianceRecordingPolicy](/en-us/powershell/module/teams/set-csteamscompliancerecordingpolicy).
2. Assign the compliance recording policy to a user.

    ```powershell
    Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
    ```

    See [Grant-CsTeamsComplianceRecordingPolicy](/en-us/powershell/module/teams/grant-csteamscompliancerecordingpolicy).

    ```powershell
    Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl
    ```

    Example

    - UserPrincipalName : testuser@contoso.onmicrosoft.com
    - TenantId : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
    - TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy