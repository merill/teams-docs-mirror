---
layout: Conceptual
title: Setup - Third-party voice agents - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-third-party-voice-agents
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
ms.date: 2026-08-31T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to set up third-party voice agents to be part of my call flows.
description: Learn how to set up certified third-party voice agents for voice applications using PowerShell and Azure Communication Services.
locale: en-us
document_id: 7f076e59-33d2-2a29-2f20-cd624d46fecd
document_version_independent_id: 7f076e59-33d2-2a29-2f20-cd624d46fecd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-third-party-voice-agents.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-third-party-voice-agents
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-third-party-voice-agents.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/54fcef21-b24a-4ef4-9c4a-a525c23ee9a3
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ab60220-e56b-41ff-a8bf-45b8d7ab716f
platformId: 895bbda2-e6bb-e6c7-4f3c-755d6f2a15cc
---

# Setup - Third-party voice agents - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to integrate certified third-party voice agent solutions and use them with Teams Phone Agent, Auto Attendant, and Call Queue.

## Planning and licensing review

### Planning

- [Third-party voice agents](aa-cq-plan-third-party-voice-agents)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

- When a call is transferred from Teams to a third-party voice agent, and the voice agent tries to conference or transfer an external phone number, the call fails.

## What's new in Third-Party Voice Agents (last six months)

- June 15
    - Generally available

## Steps to create a third-party voice agent for Teams Phone Agent, Auto Attendant, or Call Queue

The Teams portion of the third-party voice agent configuration is currently available through PowerShell only.

The following Azure resources are also required:

- An Azure account with an active subscription. [Create an account for free](https://azure.microsoft.com/pricing/purchase-options/azure-account?cid=msft_learn).
- A Communication Services resource. For more information, see [Create a Communication Services resource](/en-us/azure/communication-services/quickstarts/create-communication-resource).
- A configured Event Grid endpoint. For more information, see [Incoming call concepts](/en-us/azure/communication-services/concepts/call-automation/incoming-call-notification#receiving-an-incoming-call-notification-from-event-grid).
- An application or service endpoint to host your voice agent logic. This must be reachable by Azure Communication Services events.

1. Obtain the Azure application identifier for the voice agent.
2. Create and license a new resource account that links to the Azure application.

```powershell
$raVA = New-CsOnlineApplicationInstance -UserPrincipalName <contoso_user@contoso.com> -DisplayName "<Name of Resource Account>" -ApplicationID "<3rd Party Voice Agent Application ID>"

# Set the Resource Account's Location
Update-MgUser -UserId $raVA.ObjectId -UsageLocation <Location (i.e. US)>

# Assign the Microsoft Teams Phone Resource Account license to the Resource Account
$skuID = (Get-MgSubscribedSKU | Where {$_.SkuPartNumber -eq "PHONESYSTEM_VIRTUALUSER"}).SkuId
Set-MgUserLicense -UserId $raVA.Identity -AddLicenses @{SkuId = $skuID} -RemoveLicenses @()
```

### Example - Via an auto attendant

Create an auto attendant

```powershell
$aaDefaultGreetingText = "<Greeting>"

$aaDefaultGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt $aaDefaultGreetingText

$aaDefaultMenuPromptText = "<For the voice agent, press 1>"

$aaDefaultMenuPromptPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt $aaDefaultMenuPromptText

$aaDefaultMenuOpt1CE = New-CsAutoAttendantCallableEntity -Type ApplicationEndpoint -Identity $raVA.Identity

$aaDefaultMenuOpt1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -CallTarget $aaDefaultMenuOpt1CE -DtmfResponse Tone1 -VoiceResponses "<Voice Agent>"

$aaDefaultMenu = New-CsAutoAttendantMenu -Name "Default Open Menu" -MenuOptions @($aaDefaultMenuOpt1) -Prompt @($aaDefaultMenuPromptPrompt)

$aaDefaultMenuCallFlow = New-CsAutoAttendantCallFlow -Name "Default Open Call Flow" -menu $aaDefaultMenu -Greetings @($aaDefaultGreetingPrompt)

$aaAA = New-CsAutoAttendant -Name "<Name>" -LanguageId <Language ID> -TimeZoneId "<Insert your Time Zone ID>" -DefaultCallFlow $aaDefaultMenuCallFlow
```

Perform the following steps in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Create a resource account.
2. License the resource account.
3. Assign the resource account to the auto attendant.
4. Optionally, assign a phone number to the resource account.

## Related third-party voice agent setup and configuration articles

- [Teams Phone Agents](aa-cq-setup-teams-phone-agent)
- [Auto Attendants](aa-cq-setup-auto-attendant)
- [Call Queues](aa-cq-setup-call-queue)