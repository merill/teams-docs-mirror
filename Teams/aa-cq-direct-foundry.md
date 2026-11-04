---
layout: Conceptual
title: Setup - Voice enable Microsoft Foundry agents - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-direct-foundry
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
ms.date: 2026-10-21T00:00:00.0000000Z
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
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want learn about voice enabling my Microsoft Foundry agents through Teams Phone so I know when and how to use them within my organization.
description: Setup - Voice enable Microsoft Foundry agents through Teams Phone
locale: en-us
document_id: 30adfa22-7526-63c6-3650-75ee14af854c
document_version_independent_id: 30adfa22-7526-63c6-3650-75ee14af854c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-direct-foundry.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-direct-foundry
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-direct-foundry.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/54fcef21-b24a-4ef4-9c4a-a525c23ee9a3
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ab60220-e56b-41ff-a8bf-45b8d7ab716f
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
platformId: 7727a1ca-c101-0664-da55-682f163e0eba
---

# Setup - Voice enable Microsoft Foundry agents - Microsoft Teams | Microsoft Learn

## Planning and licensing review

### Planning

- [Manage Teams resource accounts](aa-cq-manage-resource-accounts)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- Azure subscription

## Known issues

None.

## Overview

[Microsoft Foundry](https://go.microsoft.com/fwlink/?LinkId=2387204) is the enterprise AI platform to build, ground, and govern AI apps and agents at scale. It brings together your full agent lifecycle with open development, built-in intelligence, and consistent security, compliance, and policy controls across every agent.

Direct dial Microsoft Foundry voice agents through Microsoft Teams Phone allow you to create conversational AI bots and attach them directly to a phone number via Teams Phone's resource accounts. By using these first-party conversational voice agents, you can significantly enhance your current Interactive Voice Response experiences or upgrade your current call flows.

By front-ending your call flow with a Microsoft Foundry voice agent, you unlock deep automation and tailored experiences. You can design custom workflows to handle common inquiries, such as billing, order status, and inventory checks. The agent acts as an intelligent first point of contact, resolving issues independently before seamlessly routing the call to a human representative using traditional Teams Phone routing systems if needed.

## What you will build

![High level call diagram showing the components a Teams call goes through to reach a Foundry agent.](media/aa-cq/direct-foundry.png)

## Prerequisites

- Azure access - An Azure subscription where you can create Foundry, ACS, an app registration, Azure Bot, and Event Grid resources.
- Teams administration - Teams and Microsoft 365 permissions to create, license and assign a phone number to a resource account.
- PowerShell - with the lastest MicrosoftTeams module. The custom application-endpoint menu option is PowerShell only.

## Values to collect

| Variable | Where to obtain it | Used later for |
| --- | --- | --- |
| `<foundry-project>` | Foundry project creation | Hosting the voice agent and ACS project connection |
| `<voice-agent>` | Foundry agent creation | The agent whose Channels tab receives the Teams binding |
| `<application-client-id>` | App registrations → Overview | Azure Bot Microsoft App ID and Teams resource-account ApplicationId |
| `<azure-tenant-id>` | App registrations → Overview | Azure Bot single-tenant configuration |
| `<acs-endpoint-host>` | ACS Properties / JSON | Foundry connection and ACS server-consent request |
| `<acs-immutable-resource-id>` | ACS Properties / JSON | Teams resource-account AcsResourceId |
| `<teams-tenant-id>` | Get-CsTenan | ACS server-consent scope |
| `<resource-account-object-id>` | Get-CsOnlineApplicationInstance | Foundry phone binding, ACS consent, and MA ApplicationEndpoint target |
| `<teams-service-number>` | Teams admin center | Resource-account assignment and Foundry phone binding |

## Setup procudure

### Step 1: Create and test the Foundry voice agent

1. Open [Microsoft Foundry](https://ai.azure.com/login).
2. Create a Foundry project in the Azure subscription you will use for ACS.
3. Create an agent with **Interaction mode: Voice.** (This choice cannot be changed later.)
4. Configure concise telephone instructions and a session-start greeting.
5. Leave tools and knowledge empty for the first connectivity test.
6. Run a browser voice session and verify greeting, two-way speech, and barge-in.

**Expected:** The agent works in the Foundry playground before any Teams infrastructure is added.

### Step 2: Create Azure Communication Services

[ACS creation guide](/en-us/azure/communication-services/quickstarts/create-communication-resource)

1. Open [Azure portal](https://portal.azure.com/).
2. Create an ACS resource in the same Entra tenant as the Foundry project.
3. Select the data location that matches the Teams tenant’s data location.
4. Open the ACS resource’s Properties or JSON view.

- hostName -&gt; `<acs-endpoint-host>`
- immutableResourceId -&gt; `<acs-immutable-resource-id>`

**Expected:** ACS is provisioned and you have `<acs-endpoint-host>` and `<acs-immutable-resource-id>`.

### Step 3: Create the application identity and Azure Bot

1. Open [Entra admin center](https://entra.microsoft.com/).
2. Create a **single-tenant** app registration. Record its **client ID** and **tenant ID**.
3. Create a client secret and store it securely. Do not place it in source, tickets, screenshots, or chat.
4. Create an Azure Bot using the existing app registration, Global data residency, and Standard/S1.
5. Set the Bot **Messaging endpoint** to: `https://eventgrid.azure.net`
6. Enable the Microsoft Teams Calling channel and set its calling webhook to the same Event Grid URL.
7. Open [Azure portal](https://portal.azure.com/).
8. On the Azure subscription, register the `Microsoft.EventGrid` resource provider.

**Expected:** The Azure Bot is bound to `<application-client-id>`, and both Teams event paths target Event Grid.

### Step 4: Create and link the Teams resource account

```powershell
Connect-MicrosoftTeams

$appId = [Guid]"<application-client-id>"
$acsId = [Guid]"<acs-immutable-resource-id>"
$resourceAccountUpn = "voice-agent-ra@contoso.onmicrosoft.com"

$ra = New-CsOnlineApplicationInstance `
    -UserPrincipalName $resourceAccountUpn `
    -ApplicationId $appId `
    -DisplayName "Foundry Voice Agent"

# Wait for Teams directory propagation before retrieving the object.
$ra = Get-CsOnlineApplicationInstance -Identity $resourceAccountUpn

Set-CsOnlineApplicationInstance `
    -Identity $ra.ObjectId `
    -ApplicationId $appId `
    -AcsResourceId $acsId `
    -DisplayName "Foundry Voice Agent"

Sync-CsOnlineApplicationInstance `
    -ObjectId $ra.ObjectId `
    -ApplicationId $appId `
    -AcsResourceId $acsId

Get-CsOnlineApplicationInstance -Identity $ra.ObjectId |
    Format-List DisplayName, UserPrincipalName, ObjectId, ApplicationId, AcsResourceId
```

**Expected:** The output contains an ObjectId, the app client ID, and the ACS immutable resource ID. Save the ObjectId as `<resource-account-object-id>`.

### Step 5: License the resource account and satisfy the portal’s number requirement

1. Open [Microsoft 365 admin center](https://admin.microsoft.com/).
2. Assign the **Microsoft Teams Phone Resource Account** license in Microsoft 365 admin center.
3. Open [Teams admin center](https://admin.teams.microsoft.com/).
4. Choose an unassigned Teams service number whose capabilities include `VoiceApplicationAssignment`.

If the Teams UI is disabled for the custom resource account, assign the number through PowerShell.

```powershell
$telephoneNumber = "<teams-service-number>"

$number = Get-CsPhoneNumberAssignment -TelephoneNumber $telephoneNumber
$number | Format-List TelephoneNumber, NumberType, PstnAssignmentStatus, Capability, AssignmentBlockedState

Set-CsPhoneNumberAssignment `
    -Identity "voice-agent-ra@contoso.onmicrosoft.com" `
    -TelephoneNumber $telephoneNumber `
    -NumberType $number.NumberType
```

**Expected:** The resource account is Licensed, and the number’s assignment target is the resource-account ObjectId.

### Step 6: Create the Foundry Microsoft Teams phone binding

1. Open [Microsoft Foundry](https://ai.azure.com/login).
2. Open the target voice agent, then **Channels → Phone numbers → Add a number → Microsoft Teams**.
3. Select **Automatic configuration** for secure incoming-call delivery.
4. Select the ACS resource.
5. Enter `<teams-service-number>` and `<resource-account-object-id>`.
6. Complete the binding and wait for it to appear on the Channels page.

**Important:** The binding is associated with whichever Foundry agent’s Channels tab you are using. No Foundry agent ID is written onto the Teams resource account.

**Expected:** The Microsoft Teams number is visible on the voice agent’s Phone numbers card.

### Step 7: Grant ACS server consent for the Teams resource account

[Teams Phone Extensibility guide](/en-us/azure/communication-services/quickstarts/tpe/teams-phone-extensibility-quickstart)

ACS must authorize the exact pair of `<teams-tenant-id>` and `<resource-account-object-id>`. A direct call commonly returns **Busy** until this is complete.

**Read the ACS key locally with Read-Host -AsSecureString. Never paste it into chat or save it in the script. Rotate it immediately if exposed.**

```powershell
$acsHost = "<acs-endpoint-host>"
$teamsTenantId = "<teams-tenant-id>"
$resourceAccountId = "<resource-account-object-id>"
$apiVersion = "2025-06-30"

$secureKey = Read-Host "Paste the ACS access key" -AsSecureString
$ptr = [Runtime.InteropServices.Marshal]::SecureStringToBSTR($secureKey)
try { $accessKey = [Runtime.InteropServices.Marshal]::PtrToStringBSTR($ptr) }
finally { [Runtime.InteropServices.Marshal]::ZeroFreeBSTR($ptr) }

$body = '{"principalType":"teamsResourceAccount"}'
$path = "/access/teamsExtension/tenants/$teamsTenantId/assignments/$resourceAccountId?api-version=$apiVersion"
$date = [DateTime]::UtcNow.ToString("r",[Globalization.CultureInfo]::InvariantCulture)
$bodyBytes = [Text.Encoding]::UTF8.GetBytes($body)
$sha = [Security.Cryptography.SHA256]::Create()
try { $hash = [Convert]::ToBase64String($sha.ComputeHash($bodyBytes)) }
finally { $sha.Dispose() }

$toSign = "PUT`n$path`n$date;$acsHost;$hash"
$hmac = [Security.Cryptography.HMACSHA256]::new([Convert]::FromBase64String($accessKey))
try {
    $signature = [Convert]::ToBase64String(
        $hmac.ComputeHash([Text.Encoding]::UTF8.GetBytes($toSign)))
} finally { $hmac.Dispose() }

$headers = @{
    "x-ms-date" = $date
    "x-ms-content-sha256" = $hash
    "Authorization" = "HMAC-SHA256 SignedHeaders=x-ms-date;host;x-ms-content-sha256&Signature=$signature"
}

Invoke-RestMethod -Method Put `
    -Uri "https://$acsHost$path" `
    -Headers $headers `
    -Body $body `
    -ContentType "application/json"
```

**Expected:** The response identifies the resource-account ObjectId, Teams tenant ID, and principal type teamsResourceAccount.

### Step 8: Validate the complete call path

1. Call `<teams-service-number>`. Confirm the Foundry greeting, two-way audio, and barge-in.
2. Open [Microsoft Foundry](https://ai.azure.com/login) agent’s Traces tab and confirm the sessions appear.

## Related Teams Phone Agent setup and configuration articles

- [Third-party voice agents](aa-cq-setup-third-party-voice-agents)
- [Teams Phone Agents](aa-cq-setup-teams-phone-agent)