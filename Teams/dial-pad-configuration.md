---
layout: Conceptual
title: Teams dial pad access - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/dial-pad-configuration
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
ms.date: 2025-05-08T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Learn about how to validate configuration requirements to display a dial pad in the Teams client so that users can make telephone calls.
locale: en-us
document_id: e994851c-2be6-6a89-fce5-f9238ce4796b
document_version_independent_id: e4e6be9d-1128-31b8-be3e-adfd9817b4d8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/dial-pad-configuration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: dial-pad-configuration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/dial-pad-configuration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2398392f-6348-a5d7-1125-672243206a80
---

# Teams dial pad access - Microsoft Teams | Microsoft Learn

In the Calls app of the Teams client, a dial pad enables users to enter phone numbers to make external telephone calls. The dial pad is available for users with a Teams Phone license, provided they're configured properly.

If all steps are not completed when you [Set up Teams Phone](setting-up-your-phone-system), the dial pad may not display for the user.

The following prerequisites are necessary for the dial pad to display:

- User is assigned with a Teams Phone ("MCOEV") license
- User is homed online and not in Skype for Business on premises
- User is Enterprise Voice enabled
- User has Make private calls enabled in Teams Calling Policy

Note

In order to use the dial pad to make a call, the user must also have one of the following [PSTN connectivity options](pstn-connectivity): Microsoft Calling Plan, Operator Connect, Teams Phone Mobile, Direct Routing, or is able to use [Shared Calling](shared-calling-plan).

This article provides PowerShell cmdlets that you can use to validate the prerequisite configurations that are necessary for the dial pad to display to the user.

In most cases, you need to look at various properties in the output of the [Get-CsOnlineUser](/en-us/powershell/module/teams/get-csonlineuser) cmdlet. Examples assume $user is either the UPN (UserPrincipalName) or SIP address of the user.

## User is assigned with a Teams Phone ("MCOEV") license

In this first validation check, you are validating that the user has a Teams Phone license assigned.

From the PowerShell cmdlet output, make sure that the assigned plan for the user shows the ***CapabilityStatus*** attribute set to **Enabled** and the ***Capability*** set to **MCOEV** (MCOEV indicates a Teams Phone license). You might see MCOEV, MCOEV1, and so on. All are acceptable--as long as the ***Capability*** starts with **MCOEV**.

To check that the attributes are set correctly, use the following command:

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

The output will look like the following. You only need to check the **CapabilityStatus** and the **Capability** attributes:

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

To learn more about Teams Phone licenses, see [Teams Phone licensing](teams-phone-licensing).

## User is homed online and not in Skype for Business on premises

To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with "sipfed.online." To check the values, use the following command:

```PowerShell
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

The output should be similar to:

```PowerShell
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## User is Enterprise Voice enabled

A prerequisite to validating this step is ensuring the user has a Teams Phone license assigned. Assigning a Teams Phone license to a user opens a gate for the user's account to be configured as Enterprise Voice Enabled.

If the license and M365 Phone System app are assigned to the user but they still don't see their dial pad, the Enterprise Voice Enabled status may be set to false.

To update a user account so that their Enterprise Voice Enabled status is set to *true*, check their status in Teams admin center or in PowerShell.

- In the Teams admin center, go to a **Users** &gt; **Manage users** and select the user you want to edit. Under the **Account** tab &gt; **Assigned phone number**, turn **Enterprise Voice** to **On** and select **Save**.
- For PowerShell, use the [Set-CsPhoneNumberAssignment](/en-us/powershell/module/teams/set-csphonenumberassignment) cmdlet and set the `-EnterpriseVoiceEnabled` parameter to `$true`.

To check if the user is Enterprise Voice Enabled, use the following PowerShell command:

```PowerShell
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

The output should look like:

```PowerShell
EnterpriseVoiceEnabled
----------------------
                  True
```

Note

When assigning a telephon number to a licensed user, Enterprise Voice Enabled is automatically set to True. If a phone number is assigned and the value is False, you must use the TAC or PowerShell cmdlet to manually set the value to True.

## User has Make Private Calls enabled in Teams Calling Policy

In PowerShell, the user's effective TeamsCallingPolicy must have AllowPrivateCalling set to true. Unless you assign a custom policy, users automatically inherit the global calling policy, which has AllowPrivateCallingPolicy set to true by default.

In the Teams admin center, the calling policy setting is indicated as ***Make private calls***.

Using PowerShell, to get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:

```PowerShell
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

The output should look like:

```PowerShell
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
```

## Additional notes

- You might need to restart the Teams client after making any of these configuration changes.
- If you recently updated any of the above criteria, you might need to wait a few hours for the client to receive the new settings.
- If you still don't see the dial pad, check if there's a provisioning error by using the following command:

    ```PowerShell
    Get-CsOnlineUser -Identity $user|Select UserValidationErrors
    ```
- If it's been more than 24 hours and you're still seeing problems, contact Support.