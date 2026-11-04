---
layout: Conceptual
title: Configure Multi-line in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/multi-line
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: pavellatif
ms.author: pavellatif
manager: roykuntz
ms.reviewer: mshaikh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.date: 2026-03-27T00:00:00.0000000Z
audience: admin
search.appverid: MET150
description: Learn how to configure multi-line for users in Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- CSH
locale: en-us
document_id: 326fbba2-062a-c3d5-ac60-c5476f0eb59b
document_version_independent_id: 326fbba2-062a-c3d5-ac60-c5476f0eb59b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/multi-line.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: multi-line
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/multi-line.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2a196786-4315-6e44-77b1-a059bb2aec37
---

# Configure Multi-line in Microsoft Teams - Microsoft Teams | Microsoft Learn

This article describes how to configure multi-line for users with Teams Phone in Microsoft Teams. Multi‑line gives callers more flexibility and control by allowing administrators to assign more than one phone number to a single user. With full support across Teams desktop, Teams web and Teams devices, users can seamlessly make and receive calls from multiple numbers without switching accounts or hardware. One person can present different outgoing caller IDs (or "lines") and receive calls on multiple business numbers — all integrated in Teams. This feature makes it easy to manage different roles, departments, or regional identities—all from one unified Teams experience.

Multi-line phone numbers are categorized as *alternate line* in Teams Phone and are additional phone numbers assigned to a user. Administrators can assign up to 11 phone numbers (including Primary line and [Private line](/en-us/microsoftteams/private-line)) to a single Teams Phone user, all within one Teams account. These numbers can be in different countries or use different PSTN connectivity types — any mix of Calling Plan (CP), Direct Routing (DR), Operator Connect (OC), and Teams Phone Mobile (maximum of one). The alternate phone numbers can also include "soft" numbers that have a Teams Shared Calling Routing policy assigned.

## Requirements

Keep the following requirements for multi-line in mind:

- Admin role: You must have one of the following roles:
    - Teams Administrator
    - Teams Communications Administrator
    - Teams Telephony Administrator
- Users can be assigned **one** primary line and up to **nine** more alternate lines.
- There can be a maximum of **one** Teams Phone Mobile number assigned to a single user.
- Internal or external reverse number lookup (RNL) works with alternate lines.
- Alternate lines can be any type of phone number and from any geographical region the tenant has access to Teams Phone (for example, Direct Routing, Operator Connect, Calling Plan, Teams Phone Mobile).
- Alternate lines have the same licensing requirements as the user’s primary phone number.
- Users must have a primary line assigned from their usage location before an alternate line can be assigned.
- Users must be "voice enabled" for alternate lines. Before you can enable voice for your users, you must assign a licenseto them first. To enable voice for your users, you can use the Teams admin center or PowerShell.
    - In the Teams admin center, go to a **Users** &gt; **Manage users** and select the user you want to edit. Under the **Account** tab &gt; **Assigned phone number**, turn **Enterprise Voice** to **On** and select **Save**.
    - For PowerShell, use the [Set-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/set-csphonenumberassignment) cmdlet and set the `-EnterpriseVoiceEnabled` parameter to `$true`.
- **User should not be located in India**. We currently do not support multi-line in India.

### Licensing requirements

The automated provisioning and deprovisioning of alternate line licenses must match the user's primary line. The following user license combinations are simultaneously supported for both primary line, private line, and alternate lines:

| User license combinations | Phone number category available for assignment |
| --- | --- |
| Teams Phone | Direct Routing, Operator Connect, Teams Phone Mobile |
| Teams Phone with Calling Plan | Direct Routing, Operator Connect, Teams Phone Mobile, Calling Plan |

For more information about licensing, see [Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).

## Capabilities and Limitations

The table summarizes what is currently supported and what isn't yet available:

| Feature / Capability | Support |
| --- | --- |
| **Multiple numbers per user** | **Supported.** Assign up to **11** phone numbers (1 primary + 1 private + up to 9 alternate) to a single Teams user. Numbers can span different countries and PSTN connectivity types. |
| **Outgoing calls on alternate lines** | **Supported** on Teams desktop, Teams web, and Teams Phone devices. Users can choose any assigned line for outbound calls via the **Call As** dropdown or line-specific tabs. On **SIP desk phones**, alternate lines can receive inbound calls but **cannot be selected** for outbound calls. |
| **Incoming calls on alternate lines** | **Supported.** All inbound PSTN calls to any assigned number ring the same user in Teams across Teams desktop, Teams web, Teams Phone devices, and Teams mobile (iOS/Android). |
| **Teams desktop & web clients** | **Supported.** Teams for Windows, Mac, and web fully support multi-line calling. Each alternate number appears as a **separate tab** in the Calls app. |
| **Teams mobile (iOS/Android)** | **Coming soon.** Mobile app support for alternate lines is planned for a future update. For now, on **Teams mobile (iOS/Android)**, alternate lines can receive inbound calls but **cannot be selected** for outbound calls or shown any multi-line options. |
| **Teams PowerShell Module** | **Supported.** Multi-line management is fully available in Teams PowerShell module. |
| **Teams Admin Center (TAC)** | **Supported.** Multi-line management is fully available in TAC. |
| **Graph API** | **Not yet Supported.** Multi-line management via Graph API isn't yet available; admins must use PowerShell or TAC to manage alternate phone numbers. |
| **Call History** | **Supported (unified).** All calls from all lines appear in a single call history with identifiers showing which number was used. |
| **Voicemail** | **Supported (unified).** All lines share one voicemail box. Notifications don't indicate which number the caller dialed. No separate voicemail per line. |
| **Call Delegation / Call Groups** | **Not yet supported.** Delegation and call groups apply uniformly; per-line delegation isn't supported yet. |
| **Call Queues & Auto Attendants** | **Not yet supported.** Alternate numbers are direct user lines only and can’t be added to Call Queues or Auto Attendants. |
| **Teams Phone Mobile (SIM integration)** | **Partial.** Only **one** Teams Phone Mobile (SIM) line per user. Other non-SIM numbers (DR, CP, OC) can be added alongside it. Teams Phone Mobile (SIM) First Run experience and native dialer support for alternate Teams Phone Mobile number isn't yet available. This feature is to be released along with support for Teams mobile (iOS/Android). |
| **Survivable Branch Appliance (SBA)** | **Not supported** for alternate numbers in this release. |
| **Number-level policies** | **Available (partial).** Certain policies can be assigned per phone number. |
| **Call settings** | **Partial.** User **Call settings** (forwarding, redirection) apply uniformly across primary and alternate lines. |

## Configure an alternate line for a user

Alternate lines can be configured in the Teams admin center or with PowerShell. You must have Teams PowerShell Module version 7.6.0 or later to use the updated [Set-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/set-csphonenumberassignment) cmdlets.

### Assign an alternate line to a user using Teams admin center

1. From the Teams admin center, go to **Users** &gt; **Manage users**.
2. Select a user.
3. From the user's Account tab, under Assigned phone number, select **Assign alternate phone number**.
4. From the Assign alternate phone number panel, select the **Phone number type**.
5. Select a phone number for **Assigned phone number**.
6. Add a phone number extension if applicable.
7. Assign an emergency location for the alternate number. This location **must** match the alternate phone number's country location for proper emergency call handling.
8. (optional) Select whether to inform the user about new phone number by toggling **Email user with phone number information** button.
9. Select **Apply**.

Important

- The user must already have an assigned primary line to have alternate lines assigned.
- If assigning Operator Connect numbers, the ability to set or change the emergency location depends on the operator. Contact the corresponding operator for more information.
- Call forwarding for alternate lines follows the same rules as primary line. If a user forwards the primary line to any phone number or delegate, calls to alternate lines are also forwarded to same phone number or delegate. Depending on licensing, this action may result in extra cost.

### Assign an alternate line to a user using Teams PowerShell module

Alternate lines can be assigned using [Set-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/set-csphonenumberassignment) cmdlet. The only difference from primary number assignment is that you need to specify the parameter `-AssignmentCategory` with the **Alternate** attribute.

The following PowerShell script assigns the Microsoft Calling Plan phone number +14255551234 as an alternate line for user1@contoso.com:

```powershell
Set-CsPhoneNumberAssignment -Identity user1@contoso.com -PhoneNumber '+14255551234' -PhoneNumberType CallingPlan -AssignmentCategory Alternate
```

When you assign a phone number to a user, the `-EnterpriseVoiceEnabled` parameter is automatically set to **True**.

### Assign policies to an alternate line using Teams admin center

A key aspect of multi-line configuration is that certain policies can be assigned per phone number independently from the user-level policies that govern the primary number. The following policies support per-number assignment for alternate lines:

| Policy | Notes |
| --- | --- |
| **Tenant Dial Plan** | Controls number normalization rules for the specific alternate number. |
| **Emergency Call Routing Policy** | **Required** for alternate phone numbers with **Direct Routing**. |
| **Emergency Calling Policy** | Defines emergency calling notification and routing behavior per number. |
| **Calling Line Identity (Caller ID) Policy** | Controls outbound caller ID masking or replacement for calls made on the alternate line. |
| **Online Voice Routing Policy** | **Required** for alternate phone numbers with **Direct Routing**. Without a voice routing policy, calls to and from Direct Routing numbers fail. Can be assigned to any number type (including Calling Plan) to allow specific numbers to route via a customer’s SBC. |
| **Dial Out Restriction (OnlineDialOutPolicy)** | Restricts outbound dialing permissions per number. **This policy isn't available to be assigned via TAC. Use Teams PowerShell module.** |
| **Shared Call Routing Policy** | Enables assigning a soft phone number that uses Shared Calling for call routing. **This policy isn't available to be assigned via TAC. Use Teams PowerShell module.** |

To assign phone number policies:

1. From the Teams admin center, go to **Users** &gt; **Manage users**.
2. Select a user.
3. From the user's Account tab, find the alternate phone number you want to configure under Assigned phone number section.
4. On the alternate number card, look at the **Policies**section:
    1. If no policies are assigned, you see **Assign policy**link. Select the link to assign new policies.
        1. In the **Assign policies** panel, select the desired policy from each dropdown menu. Available options include your custom policies. Select **None** to leave a specific policy unassigned. **These number selectable policies will not fall back to user assigned policies.**
    2. If policies are already assigned, you see **Edit policy**link. To assign new policies or update existing policies, select the link.
        1. In the **Edit policies** panel, select the desired policy from each dropdown menu.
5. Select **Apply**.

Important

- There are several phone number policies applicable to alternate lines. These policies **must** be set at number level and won't fall back to user assigned policies. Ensure applicable phone number policies are assigned for alternate lines by following **Assign policies to an alternate line** instruction.
- Admins can't assign policies directly on primary or private numbers at the phone number level. Policies can only be set on alternate numbers that are already assigned.
- Unassigning or changing an alternate phone number removes all policies associated with that number.
- Removal of primary line also removes all alternate lines from the user. The primary line can be removed from the user by a system provisioning event such as license removal, phone number port-out, phone number migration between number types, and user's primary usage location change.

### Assign policies to an alternate line using Teams PowerShell Module

Number level policies can be assigned to alternate lines using [Set-CsPhoneNumberPolicyAssignment](/en-us/powershell/module/microsoftteams/set-csphonenumberpolicyassignment) cmdlet. The following PowerShell script configures a Tenant Dial Plan to an alternate number:

```powershell
Set-CsPhoneNumberPolicyAssignment -TelephoneNumber +14255551234 -PolicyType TenantDialPlan -PolicyName "HR Department Dial Plan"
```

You can assign all **7** available number level policies using Teams PowerShell Module.

### View policies assigned to an alternate line using Teams PowerShell Module

Number level policies assigned to an alternate line can be verified using [Get-CsPhoneNumberPolicyAssignment](/en-us/powershell/module/microsoftteams/get-csphonenumberpolicyassignment) cmdlet. The following PowerShell script shows how to display all Tenant Dial Plans assigned to an alternate number:

```powershell
Get-CsPhoneNumberPolicyAssignment -TelephoneNumber 14255551234
```

```output
TelephoneNumber PolicyType          PolicyName Authority AssignmentType Reference
--------------- ----------          ---------- --------- -------------- ---------
14255551234     TenantDialPlan      PolicyOne  Tenant    Direct         Direct
14255551234     CallingLineIdentity PolicyTwo  Tenant    Direct         Direct
```

Same cmdlet can also be used to query all the policies currently assigned to various alternate numbers within the tenant. The following example returns a list of all the telephone numbers in the tenant that have at least one policy assigned:

```powershell
PS C:\> Get-CsPhoneNumberPolicyAssignment
```

```output
TelephoneNumber PolicyType          PolicyName    Authority AssignmentType Reference
--------------- ----------          ----------    --------- -------------- ---------
1234567         TenantDialPlan      TestPolicy    Tenant    Direct         Direct
14255551234     TenantDialPlan      PolicyOne     Tenant    Direct         Direct
14255551234     CallingLineIdentity PolicyTwo     Tenant    Direct         Direct
```

More details of the cmdlet can be found in [Get-CsPhoneNumberPolicyAssignment](/en-us/powershell/module/microsoftteams/get-csphonenumberpolicyassignment).

### Remove an alternate line for a user using Teams admin center

1. From the Teams admin center, go to **Users** &gt; **Manage users**.
2. Select a user.
3. From the user's Account tab, under Assigned phone number, find the alternate number you want to remove from the user.
4. On the desired alternate phone number, select **Edit**.
5. Check **Assigned phone number** from the **Edit alternate phone number**panel:
    1. Choose **None** for Operator Connect or Calling Plan numbers.
    2. Delete the phone number and extension (if any) for Direct Routing numbers.
6. Select **Apply**.
7. A confirmation dialog appears. Select **Unassign** to confirm or **Cancel** to go back.

Note

You can't unassign a user's primary phone number while they still have alternate phone numbers assigned. You must remove all alternate phone numbers first, then remove the primary number.

### Remove an alternate line for a user using Teams PowerShell module

Alternate lines can be removed using [Remove-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/remove-csphonenumberassignment) cmdlet. The following PowerShell script unassigns the Microsoft Calling Plan phone number +14255551234 as an alternate line for user1@contoso.com:

```powershell
Remove-CsPhoneNumberAssignment -Identity user1@contoso.com -PhoneNumber +14255551234 -PhoneNumberType CallingPlan
```

### Change an alternate line for a user using Teams admin center

1. From the Teams admin center, go to **Users** &gt; **Manage users**.
2. Select a user.
3. From the user's Account tab, under Assigned phone number, find the alternate number you want to change for the user.
4. On the desired alternate phone number, select **Edit**.
5. From the Edit alternate phone number panel:
    1. Select a new **Phone number type** if applicable.
    2. Select a new phone number for **Assigned phone number** if necessary.
    3. Remove and select a new **Emergency location** where applicable.
    4. Toggle **Email user with phone number information** as required.
6. Select **Apply**.
7. A confirmation dialog appears. Select **Change number** to confirm or **Cancel** to go back.

Note

When you change an alternate phone number, all policies previously assigned to that number are automatically removed. You'll need to reassign policies to the new number (as applicable) after the change. See Assign policies to an alternate phone number for instructions.

### View alternate lines from Manage users page using Teams admin center

The Manage users list view in the Teams admin center includes an **Alternate phone number(s)** column that displays any alternate phone numbers assigned to each user. You can also filter the list by Alternate number to find users who have alternate phone numbers assigned.

1. In the Teams admin center, go to **Users** &gt; **Manage users**.
2. Look for the **Alternate phone number(s)** column in the table.
3. To filter, select the Filter icon and use the **Alternate number** filter.

### View alternate lines using Teams PowerShell Module

Alternate lines can be viewed using [Get-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/get-csphonenumberassignment) cmdlet. The following PowerShell script views all the phone numbers assigned to user1@contoso.com:

```powershell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId user1@contoso.com
```

You can also view specific alternate number details using the following PowerShell script:

```powershell
Get-CsPhoneNumberAssignment -TelephoneNumber +14255551234
```

This example displays information about the telephone number +1 (425) 555-1234, which is assigned as an alternate number for user1@contoso.com.

### Manage alternate lines from Phone numbers page using Teams admin center

The Phone numbers list view in the Teams admin center includes an **Assigned as** column that displays any alternate phone numbers assigned to each user. You can also filter the list by Alternate number to find users who have alternate phone numbers assigned.

1. In the Teams admin center, go to **Voice** &gt; **Phone Numbers**.
2. Look for the **Assigned as**column in the table. This column shows the assignment category for each number:
    1. Primary: the user's main phone number
    2. Alternate: an additional multi-line number
    3. Private: a private line number (shown as "(Private line)" next to the user's name in the Assigned to column)
3. To filter, select the Filter icon and use the **Alternate number** filter.

### Unassign an alternate line from Phone numbers page using Teams admin center

1. In the Teams admin center, go to **Voice** &gt; **Phone Numbers**.
2. Find the alternate phone number you want to unassign. You can use the **Assigned as** filter set to **Alternate** to narrow the list.
3. Select the phone number in the list and then select **Edit** button at the top of the list to open **Assign/unassign** panel.
4. Clear the user from the **Assign/unassign** panel for the phone number.

### Update emergency location for an alternate line from Phone numbers page using Teams admin center

1. In the Teams admin center, go to **Voice** &gt; **Phone Numbers**.
2. Find the alternate phone number for which you want to update the emergency location. You can use the **Assigned as** filter set to **Alternate** to narrow the list.
3. Select the phone number in the list and then select **Edit** button at the top of the list to open **Assign/unassign** panel.
4. Clear the **Emergency location** and select a new location.

## Related links

[Set-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/remove-csphonenumberassignment)

[Get-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/get-csphonenumberassignment)

[Set-CsPhoneNumberPolicyAssignment](/en-us/powershell/module/microsoftteams/set-csphonenumberpolicyassignment)

[Get-CsPhoneNumberPolicyAssignment](/en-us/powershell/module/microsoftteams/get-csphonenumberpolicyassignment)