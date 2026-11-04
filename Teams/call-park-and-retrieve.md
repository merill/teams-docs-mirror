---
layout: Conceptual
title: Configure call park and retrieve in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/call-park-and-retrieve
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-09-24T00:00:00.0000000Z
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
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Learn about how to configure call park and retrieve to place a call on hold in Microsoft Teams.
locale: en-us
document_id: 3e03ef3d-81d8-c98f-8427-fe7c008ea30f
document_version_independent_id: 17af3418-b94d-f233-60c0-778b2e8dc02b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/call-park-and-retrieve.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: call-park-and-retrieve
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/call-park-and-retrieve.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b8a9214a-b9fd-a557-65c0-177c0b79dd44
---

# Configure call park and retrieve in Microsoft Teams - Microsoft Teams | Microsoft Learn

Call park and retrieve lets a user place a call on hold. When a call is parked, the service generates a unique code for call retrieval. The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call. For more information on how your users can park a call, see [Park a call in Teams](https://support.microsoft.com/teams/calls-devices/park-a-call-in-microsoft-teams).

Some common scenarios for using call park are:

- A receptionist parks a call for someone working in a factory. The receptionist then announces the call and the code number over the public address system. The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.
- A user parks a call on a mobile device because the device battery is running out of power. The user can then enter the code to retrieve the call from a Teams desk phone.
- A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer. An expert enters the code in Teams clients to retrieve the call.

To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.

By default, the range of call pickup numbers is from 10-99. You can also create your own custom range between 10-9999. The first parked call renders a pickup code of the start of range (for instance 10). The next parked call renders a pickup code incremented by 1, that is, 11, and so on, until the end of the range is rendered as a pickup code. After which, the rendered pickup codes start over from the start of the range once again.

You can specify a timeout as the number of seconds to wait before ringing back when the parked call isn't picked up. The allowed range is 120-1800 seconds, and the default value is 300 seconds.

To configure call park and retrieve, you must be a Teams administrator. Call park and retrieve is turned off by default. You can enable it for users and create user groups by using the call park policy. Assign the same call park policy to users who need to park and retrieve calls amongst themselves.

Note

When users are **not** assigned the same call park policy, retrieving parked calls fails.

Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability). It isn't supported on Skype for Business IP phones.

You can configure call park and retrieve by using the Teams admin center or by using PowerShell.

## Use Teams admin center

To create a new call park policy instance:

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Call park policies**.
2. On the **Manage policies** tab, select **Add**.
3. Enter a name for the policy, and then switch **Call park** to **On**.
4. Change the range and park timeout as required.
5. Select **Save**.

You can edit the policy by choosing it in the list and selecting **Edit**.

For the policy to work, it must be assigned to users. You can assign the policy to users individually or to a group. To learn more, see [Assign policies to users and groups](assign-policies-users-and-groups).

## Use PowerShell

To manage call park and retrieve policies by using PowerShell, use the following Teams PowerShell Module cmdlets:

- [New-CsTeamsCallParkPolicy](/en-us/powershell/module/teams/new-csteamscallparkpolicy)
- [Set-CsTeamsCallParkPolicy](/en-us/powershell/module/teams/set-csteamscallparkpolicy)
- [Get-CsTeamsCallParkPolicy](/en-us/powershell/module/teams/get-csteamscallparkpolicy)
- [Remove-CsTeamsCallParkPolicy](/en-us/powershell/module/teams/remove-csteamscallparkpolicy)
- [Grant-CsTeamsCallParkPolicy](/en-us/powershell/module/teams/grant-csteamscallparkpolicy)

### PowerShell examples

#### Create a custom call park policy

The following example creates a custom call park policy that generates pickup numbers from 500 to 1500. The call rings back the parker after 600 seconds if the parked call is unanswered.

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### Edit a call park policy

The following example turns off the call park policy:

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### Grant a call park policy to a user

The following example grants the call park policy to a user:

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### Remove a call park policy

The following example removes the call park policy:

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```