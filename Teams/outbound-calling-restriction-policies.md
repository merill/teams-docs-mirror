---
layout: Conceptual
title: Outbound call restrictions - Audio Conferencing & PSTN calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/outbound-calling-restriction-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: oscarr
ms.date: 2026-11-03T00:00:00.0000000Z
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: article
ms.service: msteams
ms.subservice: teams-audio-conferencing
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- Tier1
- m365initiative-meetings
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Administrators can control the type of audio conferencing and end-user PSTN calls that users can make.
locale: en-us
document_id: 305a21ef-6e99-3f0d-99a0-990489a93715
document_version_independent_id: 5edc67ee-0d68-50a3-fafd-f764d8762fa5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/outbound-calling-restriction-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: outbound-calling-restriction-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/outbound-calling-restriction-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
- https://authoring-docs-microsoft.poolparty.biz/devrel/6ab06385-661e-4214-8870-bbe4071c960d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
- https://authoring-docs-microsoft.poolparty.biz/devrel/131ba09e-4280-4ae7-8622-1f9f1c0daad1
platformId: 0f3e8830-2b67-b3c5-1d7c-dc730f894763
---

# Outbound call restrictions - Audio Conferencing & PSTN calls - Microsoft Teams | Microsoft Learn

As an admin, you can use outbound call controls to restrict the types of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that users in your organization can make.

You can apply outbound call controls on a per-user or per-tenant basis. The policies provide two controls that let you independently restrict each type of outbound call. By default, both controls allow international and domestic outbound calls.

| Control | Description | Control options |
| --- | --- | --- |
| Audio Conferencing PSTN calls | Restricts the type of outbound calls that are allowedfrom within meetings organized by a user. | - Any destination (default)- In the same country or region as the organizer- [Zone A countries or regions](audio-conferencing-zones) only- Don't allow |
| End-user PSTN calls | Restricts the type of calls that users can make. | - International and Domestic (default)- Domestic- None |

To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones).

Note

A call is considered domestic if the number dialed is in the same country/region where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end-user (in the case of end-user PSTN calls).

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Restrict audio conferencing outbound calls

### Using the Microsoft Teams admin center

1. In the left navigation, select **Users** &gt; **Manage users**, and then select the display name of the user from the list of available users.
2. Next go to **Audio Conferencing**, select **Edit**.
3. Under **Dial-out from meetings**, select the dial-out restriction option you want.
4. Select **Save**.

### Using PowerShell

A single policy, OnlineDialOutPolicy, controls outbound call restrictions, with a separate restriction attribute for each type of outbound call. The policy can't be customized, but predefined policy instances are available for each combination of settings.

Use the Get-CSOnlineDialOutPolicy cmdlet to view the available outbound calling policies.

**Set the policy on a per-user level with the following cmdlet**.

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Set the policy on the tenant level with the following cmdlet**.

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

All users in the tenant who don't have a dial-out policy assigned receive this policy. Users who already have a dial-out policy assigned remain with their current policy.

**Check the current policy at the tenant level with the following cmdlet**.

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

Note

The Grant-CsDialoutPolicy cmdlet doesn't include Online in its name, unlike the Get-CsOnlineDialOutPolicy cmdlet.

The following table provides an overview of each policy.

| PowerShell cmdlet | Description |
| --- | --- |
| Identity='tag:DialoutCPCandPSTNInternational' | The user can dial out from a conference to domestic and international numbers and make outbound PSTN calls to domestic and international numbers. |
| Identity='tag:DialoutCPCDomesticPSTNInternational' | The user can dial out from a conference only to domestic numbers and make outbound PSTN calls to domestic and international numbers. |
| Identity='tag:DialoutCPCDisabledPSTNInternational' | The user can't dial out from a conference but can make outbound PSTN calls to domestic and international numbers. |
| Identity='tag:DialoutCPCInternationalPSTNDomestic' | The user can dial out from a conference to domestic and international numbers but can make outbound PSTN calls only to domestic numbers. |
| Identity='tag:DialoutCPCInternationalPSTNDisabled' | The user can dial out from a conference to domestic and international numbers but can't make outbound PSTN calls, except to emergency numbers. |
| Identity='tag:DialoutCPCandPSTNDomestic' | The user can dial out from a conference only to domestic numbers and make outbound PSTN calls only to domestic numbers. |
| Identity='tag:DialoutCPCDomesticPSTNDisabled' | The user can dial out from a conference only to domestic numbers but can't make outbound PSTN calls, except to emergency numbers. |
| Identity='tag:DialoutCPCDisabledPSTNDomestic' | The user can't dial out from a conference but can make outbound PSTN calls only to domestic numbers. |
| Identity='tag:DialoutCPCandPSTNDisabled' | The user can't dial out from a conference or make outbound PSTN calls, except to emergency numbers. |
| Identity='tag:DialoutCPCZoneAPSTNInternational' | The user can dial out from a conference only to [Zone A countries and regions](audio-conferencing-zones) and make outbound PSTN calls to domestic and international numbers. |
| Identity='tag:DialoutCPCZoneAPSTNDomestic' | The user can dial out from a conference only to [Zone A countries and regions](audio-conferencing-zones) and make outbound PSTN calls only to domestic numbers. |
| Identity='tag:DialoutCPCZoneAPSTNDisabled' | The user can only dial out from a conference to [Zone A countries and regions](audio-conferencing-zones) but can't make outbound PSTN calls, except to emergency numbers. |