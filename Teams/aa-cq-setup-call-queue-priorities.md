---
layout: Conceptual
title: Setup - Call Priorities for Call Queues - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-call-queue-priorities
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.date: 2026-08-31T00:00:00.0000000Z
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
customer-intent: As a Teams Administrator, I want to set up call priorities to ensure high-priority calls are answered first, while lower-priority calls are held in a queue until a representative (agent) is available.
description: Learn how to use PowerShell to set up call priorities for a call queue so higher-priority calls are answered before lower-priority calls.
locale: en-us
document_id: 63bfbdea-2018-591c-ed13-66f567062634
document_version_independent_id: 63bfbdea-2018-591c-ed13-66f567062634
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-call-queue-priorities.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-call-queue-priorities
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-call-queue-priorities.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 34c62803-97de-4032-c93d-8aa513928c03
---

# Setup - Call Priorities for Call Queues - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to use **Call Priority** to prioritize calls within a call queue.

## Planning and licensing review

### Planning

- [Call priorities for call queues](aa-cq-plan-call-queue-priorities)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

None.

## What's new in Call Queues (last six months)

- November 10, 2026
    - Monitor, Whisper, Barge, Takeover for authorized users now supports joining active calls.
- October 19, 2026
    - Monitor, Whisper, Barge, Takeover for authorized users now supports outbound calls.
- September 30, 2026
    - [Automatic Recording for Call Queue](aa-cq-setup-call-queue-recording-automatic) can be configured in Teams admin center.
- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) updated.
- August 17, 2026
    - Assigning templates to a call queue has moved to the new **Templates** step.
    - [Compliance Recording for Call Queues](aa-cq-setup-call-queue-template-recording-compliance) configuration is now available in Teams admin center.
- August 13, 2026
    - Automatic Recording for Call Queue can be configured via PowerShell.

## How is priority assigned and honored

Priority is assigned to a call in the following situations:

- Teams Phone Agents and auto attendants can set the priority of a call when transferring to a call queue.
- Resource accounts assigned to a call queue can have a priority set.

When a call arrives at a call queue that already has a priority set, the call queue honors the setting. When a call arrives at a call queue that doesn't have a priority set, the call queue uses the priority assigned to the resource account the call arrived on.

The default priority for all calls is 3.

## Configure call priorities

Call priorities can currently only be configured using PowerShell.

### Scenario 1: Priority to callers based on dialed number

In this scenario, Contoso Support has a single Technical Support call queue that's open 24/7. Contoso's website and documentation provide their customers with the general number for all support requests. However, customers who sign up for "enhanced support" are given a dedicated number to call. The enhanced support customers are given priority over other customers based on the level of enhanced support purchased (or not purchased).

Contoso Support defines the following call priorities for their resource accounts:

- **Priority 4** - Any customer calling the general support phone number.
- **Priority 3** - Customers calling the Bronze level support phone number.
- **Priority 2** - Customers calling the Silver level support phone number.
- **Priority 1** - Customers calling the Gold level support phone number.

Customers in the call queue are presented to representatives (agents) in the order of their priority. The Gold level customers are all presented first, followed by Silver, Bronze, and finally general support customers.

![Diagram showing the call flow for Scenario 1.](media/aa-cq/aa-cq-call-priorities-scenario-1.svg)

The following command uses the [New-CsOnlineApplicationInstanceAssociation](/en-us/powershell/module/teams/new-csonlineapplicationinstanceassociation) cmdlet with the `-CallPriority` parameter to set the call priority for a call queue based on the dialed number (Gold, Silver, Bronze, General):

Expand to see the PowerShell example

```powershell
# Assign resource accounts to call queue
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity
$goldID = (Get-CsOnlineUser -Identity contoso-support-gold@contoso.com).Identity
$silverID = (Get-CsOnlineUser -Identity contoso-support-silver@contoso.com).Identity
$bronzeID = (Get-CsOnlineUser -Identity contoso-support-bronze@contoso.com).Identity
$generalID = (Get-CsOnlineUser -Identity contoso-support-general@contoso.com).Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($goldID) -ConfigurationID $callQueueID -ConfigurationType CallQueue -CallPriority 1
New-CsOnlineApplicationInstanceAssociation -Identities @($silverID) -ConfigurationID $callQueueID -ConfigurationType CallQueue -CallPriority 2
New-CsOnlineApplicationInstanceAssociation -Identities @($bronzeID) -ConfigurationID $callQueueID -ConfigurationType CallQueue -CallPriority 3
New-CsOnlineApplicationInstanceAssociation -Identities @($generalID) -ConfigurationID $callQueueID -ConfigurationType CallQueue -CallPriority 4
```

### Scenario 2: Priority to callers based on Auto attendant menu choices

In this scenario, Contoso Travel has a single Travel Support call queue for all travel inquiries. This call queue is associated with an auto attendant that provides callers with the following options:

> 
> Thank you for calling Contoso Travel. If you are currently traveling and need immediate assistance, press 1. If you are calling to inquire about an existing booking, press 2. To make a new booking, press 3. For all other inquiries, press 4.

Callers who press 1 get top priority and connect to representatives first, followed by callers who press 2, 3, and 4 in decreasing order of priority.

![Diagram showing the call flow for Scenario 2.](media/aa-cq/aa-cq-call-priorities-scenario-2.svg)

The following command uses the [New-CsAutoAttendantCallableEntity](/en-us/powershell/module/teams/new-csautoattendantcallableentity) cmdlet with the `-CallPriority` parameter to set the call priority for a call queue based on the Auto attendant menu choices (immediate assistance, existing booking, new booking, other inquiries):

Expand to see the PowerShell example

```powershell
# Create the Auto Attendant
$callQueueID = (Get-CsCallQueue -NameFilter "Travel").Identity
$callableEntity1 = New-CsAutoAttendantCallableEntity -Identity $callQueueID -Type ConfigurationEndpoint -CallPriority 1
$callableEntity2 = New-CsAutoAttendantCallableEntity -Identity $callQueueID -Type ConfigurationEndpoint -CallPriority 2
$callableEntity3 = New-CsAutoAttendantCallableEntity -Identity $callQueueID -Type ConfigurationEndpoint -CallPriority 3
$callableEntity4 = New-CsAutoAttendantCallableEntity -Identity $callQueueID -Type ConfigurationEndpoint -CallPriority 4

$greetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso Travel"
$menuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "If you are currently traveling and require immediate assistance, press 1. If you are calling to inquire about an existing booking, press 2. To make a new booking, press 3. For all other inquiries press 4."

$menuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $callableEntity1
$menuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $callableEntity2
$menuOption3 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone3 -CallTarget $callableEntity3
$menuOption4 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone4 -CallTarget $callableEntity4

$defaultMenu = New-CsAutoAttendantMenu -Name "Default menu" -Prompts @($menuPrompt) -MenuOptions @($menuOption1, $menuOption2, $menuOption3, $menuOption4)
$defaultCallFlow = New-CsAutoAttendantCallFlow -Name "Default call flow" -Greetings @($greetingPrompt) -Menu $defaultMenu
New-CsAutoAttendant -Name "Contoso Travel" -LanguageId en-US -TimeZoneId "Eastern Standard Time" -DefaultCallFlow $defaultCallFlow
```

### Scenario 3: Priority to representatives transferring calls to another call queue

In this scenario, Contoso Finance Customer Service representatives triage calls and they often transfer these calls to Tier 2 Support groups. Tier 2 Support groups can also take calls directly from customers. Contoso wants call transfers from Customer Service to have higher priority than calls that are directly dialed into Tier 2 Support, as these callers have already waited and spoken with a representative.

![Diagram showing the call flow for Scenario 3.](media/aa-cq/aa-cq-call-priorities-scenario-3.svg)

## Considerations

Keep in mind the following considerations when configuring call priorities:

- Representatives always receive calls with the highest priority first, regardless of how long lower-priority calls have been waiting.
- Call priorities aren't supported for [authorized users](aa-cq-plan-authorized-users).
- Keep the highest and lowest call priorities available for future use.
- Representatives don't receive notifications about which calls are what priority. The priority is only used to determine the order in which calls are presented to representatives.

## Related Call Queue setup and configuration articles

- [Shared call history](aa-cq-setup-call-queue-template-shared-history)
- [Compliance recording](aa-cq-setup-call-queue-template-recording-compliance)
- [Authorized users](aa-cq-setup-authorized-users)