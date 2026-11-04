---
layout: Conceptual
title: Manage call routing policies for Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-voice-routing-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: filippse
ms.date: 2026-09-28T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to create and manage call routing policies for Microsoft Teams Direct Routing.
locale: en-us
document_id: 65db142a-ac56-3cdb-91db-6f74d6244b7a
document_version_independent_id: c65c99d6-e940-381b-e248-d2c82d07670a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-voice-routing-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-voice-routing-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-voice-routing-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: ffe852aa-dc4a-a440-f6ea-0e9418b5fcc4
---

# Manage call routing policies for Direct Routing - Microsoft Teams | Microsoft Learn

If you've deployed [Direct Routing](direct-routing-landing-page) in your organization, you use call routing policies to allow Teams users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.

A call routing policy (also called a voice routing policy) is a container for PSTN usage records. You create and manage voice routing policies by going to **Voice** &gt; **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.

You can use the global (Org-wide default) policy or create and assign custom policies. Users will automatically get the global policy unless you create and assign a custom policy. Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.

It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams. You'll also need to enable the user for Direct Routing and complete other configuration steps. To learn more, see [Configure Direct Routing](direct-routing-configure).

## Create a custom call routing policy

### Use the Microsoft Teams admin center

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Voice routing policies**, and then select **Add**.
2. Enter a name and description for the policy.
3. Under **PSTN usage records**, select **Add PSTN usage**, and then select the records that you want to add. If you need to create a new PSTN usage record, select **Add**.
4. If you added multiple PSTN usage records, arrange them in the order that you want.
5. When you're done, select **Apply**.
6. Select **Save**.

### Use PowerShell

See [New-CsOnlineVoiceRoutingPolicy](/en-us/powershell/module/teams/new-csonlinevoiceroutingpolicy).

## Edit a call routing policy

### Use the Microsoft Teams admin center

You can edit the global policy or any custom policies that you create.

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Voice routing policies**.
2. Select the policy by clicking to the left of the policy name, and then select **Edit**.
3. Select **Add/remove PSTN usage records**, make the changes that you want, and then select **Save**.

### Use PowerShell

See [Set-CsOnlineVoiceRoutingPolicy](/en-us/powershell/module/teams/set-csonlinevoiceroutingpolicy).

## Assign a custom call routing policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

See also [Grant-CsOnlineVoiceRoutingPolicy](/en-us/powershell/module/teams/grant-csonlinevoiceroutingpolicy).