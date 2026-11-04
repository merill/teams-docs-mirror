---
layout: Conceptual
title: Call sharing and group call pickup - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/call-sharing-and-group-call-pickup
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.date: 2026-03-24T00:00:00.0000000Z
ms.reviewer: jastark
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
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Call sharing and group call pickup in Microsoft Teams let users share incoming calls with colleagues so that calls can be captured when the user is unavailable.
locale: en-us
document_id: a82f953e-22d5-e4af-71e2-4ed4e9d0550a
document_version_independent_id: f6a80581-d145-f2d4-5ae2-95f7faac4aaa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/call-sharing-and-group-call-pickup.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: call-sharing-and-group-call-pickup
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/call-sharing-and-group-call-pickup.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b2b27f8f-3701-524d-bd24-c916aa215be8
---

# Call sharing and group call pickup - Microsoft Teams | Microsoft Learn

The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.

Group call pickup is less disruptive to recipients than other forms of call sharing because users can configure how they want to be notified of an incoming shared call, and they can decide whether to answer it. The order in which members of the call group are notified about the incoming call can be specified as simultaneous or in order (with 5 or less members).

Important

Users, the call group owner, and members of the call group must be in Teams Only deployment mode. For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability).

## License required

Users must be assigned a Microsoft Teams Phone license to set up and use call sharing and group call pickup. For additional details on the licensing model, see [Here's what you get with Teams Phone](/en-us/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## Limitations

- A user can only own one call group.
- Each call group can have up to 25 users.
- A user can be a member of up to 25 call groups.
- If you add more than five members to a call group, the ring order automatically switches to "Everyone at once."

Mobile devices are only notified if they're set for "banner" and "ring."

SIP Devices only support the "ring" and "mute" notification modes for group call pickup. For "banner" the notification is suppressed because SIP Gateway doesn't support alerting without ringing.

## Enable the use of group call pickup

You enable call groups by configuring the **TeamsCallingPolicy AllowCallGroups** setting for a user. You can use Teams admin center or PowerShell. When enabled, the user can configure their call groups in the Teams client.

Important

When you turn off call groups for users, you must clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.

## Use Teams admin center

You can use the Teams admin center to configure group call pickup for your users.

To configure immediate call forward settings:

1. In the Teams admin center, go to **Users** &gt; **Manage users** and select a user.
2. On the user details page, go to the **Voice** tab.
3. Under **Call answering rules**, you can select either:

    - **Ring user's devices** and select **Group call pickup** from the **Also allow** dropdown. You can also select **Group call pickup** from the **If unanswered** dropdown.
    - **Be immediately forwarded** and select **Group call pickup** from the **Call forward type** dropdown
4. Select **Manage call group** and select **Add people** to add the appropriate users to the call group.
5. For each user in the call group, select the type of notification that you want the user to see when they get an incoming call. **Ring** is the default notification type.
6. From the dropdown, select the appropriate call group order.
7. Select **Save**.

## Use PowerShell

To configure call groups for users, use the following Teams PowerShell Module cmdlets:

- [Set-CsUserCallingSettings](/en-us/powershell/module/teams/set-csusercallingsettings)
- [Get-CsUserCallingSettings](/en-us/powershell/module/teams/get-csusercallingsettings)

### PowerShell examples

The following example creates a call group for user1@contoso.com with the members user2@contoso.com and user3@contoso.com, and sets immediate call forwarding to the call group for user1@contoso.com:

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

The next example shows how to update the call group of user1@contoso.com to add user5@contoso.com, and remove user6@contoso.com:

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```