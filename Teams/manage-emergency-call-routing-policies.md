---
layout: Conceptual
title: Manage emergency call routing policies for Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-emergency-call-routing-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-09-17T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use and manage emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
locale: en-us
document_id: b0a230ba-f141-3a40-12de-03b05a316a52
document_version_independent_id: 402a7d5f-4736-0f8e-7bba-8af03484085e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-emergency-call-routing-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-emergency-call-routing-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-emergency-call-routing-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 9c99b79f-752f-d20c-969c-82a47a13fedb
---

# Manage emergency call routing policies for Direct Routing - Microsoft Teams | Microsoft Learn

If you deployed [Direct Routing](direct-routing-landing-page) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed. An emergency call routing policy determines whether enhanced emergency services are enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.

Note

These call routing policies are used to identify emergency numbers and PSTN routes for Direct Routing. When Shared Calling is in use with Calling Plans and Operator Connect, these policies are only used to identify emergency numbers. For more information, see [Configure Shared Calling](shared-calling-setup).

You manage emergency call routing policies by going to **Voice** &gt; **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell. The policies can be assigned to users and [network sites](cloud-voice-network-settings).

For users, you can use the global (Org-wide default) policy or create and assign custom policies. Users automatically get the global policy unless you create and assign a custom policy. Keep in mind that you can edit the settings in the global policy but you can't rename or delete it. For network sites, you create and assign custom policies.

If you assigned an emergency call routing policy to a network site and to a user assigned a Direct Routing number and if that user is at that network site, the policy assigned to the network site overrides the policy assigned to the user.

Note

If Shared Calling for Calling Plans or Operator Connect is configured in the same tenant with Direct Routing, site assigned emergency call routing policies can't be used.

## Create a custom emergency call routing policy

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Voice** &gt; **Emergency policies**, and then select the **Call routing policies** tab.
2. Select **Add**.
3. Enter a name and description for the policy.
4. To enable dynamic emergency calling, turn on **Dynamic emergency calling**. When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.
5. Define one or more emergency numbers. Under **Emergency numbers**, select **Add**, and then do the following:

    1. **Emergency dial string**: Enter the emergency dial string. This dial string indicates that a call is an emergency call and the route pattern must match this dial string exactly. 
        Note

        For Direct Routing, Teams clients no longer send emergency calls with a "+" in front of the emergency dial string. Be sure the voice route pattern to match an emergency dial string reflects this change.
    2. **Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks. A dial mask is the number that you want to translate into the value of the emergency dial string. A dial mask allows for alternate emergency numbers to be dialed and still have the call reach emergency services. For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string. A Teams user from Europe who is visiting might not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911. To define multiple dial masks, separate each value by a semicolon. For example, 112;212.
    3. **PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record. The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them. The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).

    Note

    Dial strings and dial masks must be unique within a policy. This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time. PSTN usages should not be added for policies assigned to Shared Calling users for Calling Plans or Operator Connect.
6. Select **Save**.

### Using PowerShell

See [New-CsTeamsEmergencyCallRoutingPolicy](/en-us/powershell/module/teams/new-csteamsemergencycallroutingpolicy).

## Edit an emergency call routing policy

### Using the Teams admin center

You can edit the global policy or any custom policies that you create.

1. In the left navigation of the Teams admin center, go to **Voice** &gt; **Emergency policies**, and then select the **Call routing policies** tab.
2. Select the policy by clicking to the left of the policy name, and then select **Edit**.
3. Make the changes that you want, and then select **Save**.

### Using PowerShell

See [Set-CsTeamsEmergencyCallRoutingPolicy](/en-us/powershell/module/teams/set-csteamsemergencycallroutingpolicy).

## Assign a custom emergency call routing policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/en-us/powershell/module/teams/grant-csteamsemergencycallroutingpolicy).

## Assign a custom emergency call routing policy to a network site

### Using the Teams admin center

You can assign the global policy or any custom policies that you create.

1. In the left navigation of the Teams admin center, go to **Locations** &gt; **Network topology**, and select the **Network sites** tab.
2. Select the site by clicking to the left of the name, and then select **Edit**.
3. Under **Emergency call routing policy**, select the policy, and then select **Save**.

### Using PowerShell

Use the [Set-CsTenantNetworkSite](/en-us/powershell/module/teams/set-cstenantnetworksite) cmdlet to assign an emergency call routing policy to a network site.

This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```