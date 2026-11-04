---
layout: Conceptual
title: Block inbound calls in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/block-inbound-calls
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
audience: Admin
ms.reviewer: jastark, roykuntz
ms.date: 2026-03-12T00:00:00.0000000Z
ms.localizationpriority: medium
description: Learn how to use PowerShell to manage inbound call blocking.
locale: en-us
document_id: 91c40ca3-c19e-eac3-3adb-815e45ce2388
document_version_independent_id: 1193b36e-8870-aca9-cb9c-59c5fb1f5412
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/block-inbound-calls.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: block-inbound-calls
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/block-inbound-calls.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b26179f8-0940-2ab3-3dbb-2b45a4755a9b
---

# Block inbound calls in Microsoft Teams - Microsoft Teams | Microsoft Learn

Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN). This feature allows an administrator to define a list of number patterns and exceptions at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match. If a match is made, an incoming call is either rejected or routed to a resource account.

This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level. Individual Teams users can't manipulate this list. The Teams client does allow individual users to block PSTN calls. For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/456cb611-3477-496f-b31a-6ab752a7595f).

Note

Blocked callers might experience slightly different behaviors when their call has been rejected. The behavior is based on how the blocked caller's carrier handles the notification that the call isn't allowed to be successfully completed. Examples might include a carrier message stating the call can't be completed as dialed, or simply dropping the call.

It's currently not possible to manage call blocking by using Teams admin center.

## Manage call blocking by using PowerShell

To manage call blocking, you need to define one or more number patterns to block calls from, define exceptions to the number patterns, and enable the call blocking feature. Optionally, you can choose to configure a resource account to handle blocked calls.

Number block patterns are defined as regular expression patterns. After evaluating patterns that redirect to a resource account, the order of the remaining expressions is unimportant--the first pattern matched in the list results in the call being blocked. A new number or pattern that's added or removed in the blocked callers list can take up to 24 hours for the pattern to become active.

### Activate the call blocking feature

To view and activate the call blocking feature, use the **Get-** and **Set-CsTenantBlockingCallingNumbers** Teams PowerShell Module cmdlets.

- [Get-CsTenantBlockedCallingNumbers](/en-us/powershell/module/teams/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list. This cmdlet also returns whether or not blocking is Enabled (True or False).
- [Set-CsTenantBlockedCallingNumbers](/en-us/powershell/module/teams/set-cstenantblockedcallingnumbers) allows you to specify whether the global tenant blocked calls are turned on or off at the tenant level.

### Manage block number patterns

You manage number patterns by using the **New-**, **Get-**, **Set-**, **Test-**, and **Remove-CsInboundBlockedNumberPattern** Teams PowerShell Module cmdlets.

- [Get-CsInboundBlockedNumberPattern](/en-us/powershell/module/teams/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern.
- [New-CsInboundBlockedNumberPattern](/en-us/powershell/module/teams/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.
- [Remove-CsInboundBlockedNumberPattern](/en-us/powershell/module/teams/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.
- [Set-CsInboundBlockedNumberPattern](/en-us/powershell/module/teams/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.
- [Test-CsInboundBlockedNumberPattern](/en-us/powershell/module/teams/test-csinboundblockednumberpattern) tests whether calls from a given phone number will be blocked.

### Examples

#### Block a number (Add a block number)

In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999. The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched. You don't need to include the symbols – and () in the phone numbers because the system strips these symbols before matching. To turn on the number pattern, set the **Enabled** parameter to True. To disable this specific number pattern, set the parameter to False.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

In the next example, instead of blocking the call, the tenant administrator wants to route all calls coming from the number 1 (412) 555-1234 to the resource account specified by the object id d290f1ee-6c54-4b01-90e6-d701748f0851. To turn on the number pattern, the **Enabled** parameter is set to True.

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -ResourceAccount "d290f1ee-6c54-4b01-90e6-d701748f0851" -Pattern "^\+?14125551234$" 
```

Creating a new pattern adds the pattern as enabled by default. The description is an optional field to provide more information.

We recommend that you provide a meaningful name to easily understand why the pattern was added. To block spam numbers, consider naming the rule the same as the number pattern that's being matched, and then add additional information in the description as required.

Patterns are matched using Regular Expressions (Regex). For more information, see [Using Regex](/en-us/microsoftteams/block-inbound-calls).

Allow time for replication before you test and validate.

#### Allow a number (Remove a block number)

You can allow a number to call by removing the blocked number pattern. In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity. Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.

Allow time for replication before you test and validate.

#### View all number patterns

The following cmdlet returns a list of all blocked numbers that are entered for a tenant:

```powershell
Get-CsInboundBlockedNumberPattern
```

Use built-in PowerShell filtering abilities to parse the returned values as required.

#### Test whether a number is blocked

To verify whether a number is blocked in the tenant, use the **Test-CsInboundBlockedNumberPattern** cmdlet.

The **PhoneNumber** parameter is required, and should be a numeric string without any extra characters, such as +, - or (). The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.

In the following examples, you can see that the phone number 1 (312) 555-8884 is blocked because it's in the blocked range above. The phone number 1 (312) 555-8883 is allowed based on the exemption created below.

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

### Manage number exceptions

You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.

- [New-CsInboundExemptNumberPattern](/en-us/powershell/module/teams/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.
- [Get-CsInboundExemptNumberPattern](/en-us/powershell/module/teams/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.
- [Set-CsInboundExemptNumberPattern](/en-us/powershell/module/teams/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.
- [Remove-CsInboundExemptNumberPattern](/en-us/powershell/module/teams/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.

### Examples

#### Add a number exception

In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above. To enable this, a new number exception pattern is created as follows:

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

To turn on the number pattern, the **Enabled** parameter is set to True. To disable this specific number pattern, set the parameter to False.

#### View all number exceptions

In this example, the **Identity** parameter is optional. If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### Modify a number exception

The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity. In this example, the **Identity** parameter is required.

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### Remove a number exception

The **Remove-CsInboundExemptNumberPattern** cmdlet removes the given number pattern from the tenant list. In this example, the **Identity** parameter is required.

If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity. Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value. Allow time for replication before you test and validate.

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## Using Regex

The pattern matching for blocking callers is done by using Regex. Multiple tools are available online to help validate a Regex pattern match. If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics. To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.