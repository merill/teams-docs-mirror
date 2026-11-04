---
layout: Conceptual
title: Manage emergency calling policies in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-emergency-calling-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: pavellatif
manager: roykuntz
ms.reviewer: pavellatif
ms.date: 2026-10-20T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use and manage emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
locale: en-us
document_id: 66544770-c56b-ad8a-5b67-9e20cbc945f1
document_version_independent_id: d69667d5-d486-4b99-5e07-edb2fda7f5c7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-emergency-calling-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-emergency-calling-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-emergency-calling-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6583acda-4781-2b52-5820-254d50fcd3c7
---

# Manage emergency calling policies in Microsoft Teams - Microsoft Teams | Microsoft Learn

If your organization uses Microsoft Calling Plans, Operator Connect, Teams Phone Mobile, or Direct Routing as your [PSTN connectivity option](pstn-connectivity), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.

The emergency calling policy enables you to:

- Allow end users to configure their emergency address when working at remote locations.
- Configure emergency numbers to determine how emergency calling operates in your organization.
- Configure who to notify when a user calls emergency services. For example, you can configure policy settings to automatically notify your organization's security desk and have them listen to emergency calls.

You manage emergency calling policies by using the Microsoft Teams admin center or by using Windows PowerShell. You can assign policies to users and [network sites](cloud-voice-network-settings).

For users, you can use the global (Org-wide default) policy or create custom policies. Users automatically get the global policy unless you create and assign a custom policy. You can edit the settings in the global policy, but you can't rename or delete it. For network sites, you create and assign custom policies.

If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.

For more information, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing) and [Security desk notifications](emergency-calling-security-desk-notifications).

## Create a custom emergency calling policy

### Use the Teams admin center

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Emergency policies**, and then select the **Calling policies** tab.
2. Select **Add**.
3. Enter a name and description for the policy.
4. To allow your end users to configure their emergency address when they're working from a network location outside the corporate network, set the **External location lookup mode** toggle to **On**.
5. To show a banner to remind your end users to confirm their emergency location, enter an **Emergency service disclaimer**.
6. To customize how emergency calling operates in your organization, configure one or more **Emergency numbers**. To do this, follow these steps.

    1. In the **Emergency numbers** table, select **Add**.
    2. In the **Emergency numbers** pane, enter the **Emergency dial string** that people in your organization dial to contact emergency services.
    3. Set how you want to notify people in your organization, typically the security desk, when an emergency call is made. Under **Notification mode**, select one of the following:

        - **Send notification only**: A Teams chat message is sent to the users and groups that you specify.
        - **Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify. Teams notification recipients join the call muted and can't unmute. They can listen to the conversation between the caller and the PSAP operator but can't participate.
        - **Conferenced in and are unmuted**: A Teams chat message is sent to the users and groups that you specify. Teams notification recipients join the call muted and can unmute to participate in the conversation between the caller and the PSAP operator.
    4. If you select the **Conferenced in but are muted** or **Conferenced in and are unmuted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call. For example, enter the number of your organization's security desk, who receives a call when an emergency call is made and can then listen in on the call.

        In **Conferenced in but are muted** mode, the PSTN notification recipient joins muted and can't unmute. In **Conferenced in and are unmuted** mode, the PSTN notification recipient joins unmuted and can participate in the call. To mute their audio in this mode, the PSTN recipient must use their phone's local mute control.
7. Select **Apply**.
8. You might want to add more numbers for testing purposes to have a different notification experiences. To enter more **Emergency numbers**, select **Add**. To change or delete an existing configuration, select the row in the table, and then select **Edit** or **Remove**.
9. Select **Save**.

### Use PowerShell

See [New-CsTeamsEmergencyCallingPolicy](/en-us/powershell/module/teams/new-csteamsemergencycallingpolicy).

## Edit an emergency calling policy

### Use the Microsoft Teams admin center

You can edit the global policy or any custom policies that you create.

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Emergency policies**, and then select the **Calling policies** tab.
2. Select the policy by selecting the area to the left of the policy name, and then select **Edit**.
3. Make the changes that you want, and then select **Apply**.

### Use PowerShell

See [Set-CsTeamsEmergencyCallingPolicy](/en-us/powershell/module/teams/set-csteamsemergencycallingpolicy).

## Assign a custom emergency calling policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

See also [Grant-CsTeamsEmergencyCallingPolicy](/en-us/powershell/module/teams/grant-csteamsemergencycallingpolicy).

## Assign a custom emergency calling policy to a network site

### Use the Microsoft Teams admin center

You can assign the global policy or any custom policies that you create.

1. In the left navigation of the Microsoft Teams admin center, go to **Locations** &gt; **Network topology**, and then select the **Network sites** tab.
2. Select the site by selecting the area to the left of the name, and then select **Edit**.
3. Under **Emergency calling policy**, select the policy, and then select **Save**.

### Use PowerShell

Use the [Set-CsTenantNetworkSite](/en-us/powershell/module/teams/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.

The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```