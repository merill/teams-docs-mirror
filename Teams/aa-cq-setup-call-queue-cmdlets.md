---
layout: Conceptual
title: Setup - Call Queue via PowerShell - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-call-queue-cmdlets
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
- tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
description: Learn how to configure call queues via cmdlets
locale: en-us
document_id: fdcd4ef0-e1b7-f4de-f4c1-92c911d2fbab
document_version_independent_id: fdcd4ef0-e1b7-f4de-f4c1-92c911d2fbab
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-call-queue-cmdlets.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-call-queue-cmdlets
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-call-queue-cmdlets.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
platformId: f7b2532a-bccc-0c48-317b-98460cac9db6
---

# Setup - Call Queue via PowerShell - Microsoft Teams | Microsoft Learn

## What's new in Call Queues (last six months)

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

## Prerequisites

- Ensure you have tenant administration rights.
- The agents, distribution lists, and Teams channels mentioned in this article have already been created.

1. Determine if the `MicrosoftTeams` PowerShell module is already installed.

    ```powershell
    Get-InstalledModule -Name MicrosoftTeams
    ```

    If the `MicrosoftTeams` PowerShell module is already installed, the output from the command will look similar to:

    ```
    Get-InstalledModule -Name MicrosoftTeams
    
    Version              Name                                Repository           Description
    -------              ----                                ----------           -----------
    7.7.0                MicrosoftTeams                      PSGallery            Microsoft Teams cmdlets module for Windows PowerShell and PowerShell Core....
    ```

    Proceed to Step 2.

    If the `MicrosoftTeams` PowerShell model is not already installed, proceed to Step 3.
2. Update the `MicrosoftTeams` module

    ```powershell
    Update-Module MicrosoftTeams
    ```

    Proceed to the Scenarios
3. Install the `MicrosoftTeams` PowerShell modeule on your computer.

    - Set up your computer for [Windows PowerShell](/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    - MSTeams Module Installed

        ```powershell
        Install-Module -Name MicrosoftTeams -Force -AllowClobber
        ```
    - Microsoft Graph module installed

        ```powershell
        Install-Module -Name Microsoft.Graph -Force -AllowClobber
        ```

## Scenarios

### Sales (Users and Groups)

- Nested behind Auto Attendant: Yes
- Calling: Through Sales auto attendant only - no resource account required
- Language: English US
- Greeting: None (calls are greeted by the Sales auto attendant)
- Music on hold: Play an audio file
    - Filename: sales-hold-in-queue-music.wav
- Call Answering: Users
    - Bill@contoso.com
    - Mary@contoso.com
- Call Answering: Group
    - Sales@contoso.com
- Conference Mode: On
- Routing method: Round Robin
- Presence-based routing: On
- Call agents can opt out of taking calls: Yes
- Call agent alert time: 15
- Call overflow handling: 200
    - Redirect to: Adele@contoso.com
- Call timeout handling: 120 seconds
    - Redirect to: Adele@contoso.com
- No agents handling
    - Apply to all calls
    - Redirect to: Adele@contoso.com
- Callback: No
- Service Level: 20 seconds
- Auth User
    - Adele@contoso.com
- Voice applications Policy: Sales
- Compliance Recording: No
- Shared call history: Yes
    - Template: Sales
- Automatic recording: No

Expand to see PowerShell commands

### Login

When prompted, enter your Teams administrator credentials.

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MgGraph -Credential $credential
```

### Create Audio Files

Replace `d:\\` with the path to where the wav files are stored on your computer.

```powershell
$content = [System.IO.File]::ReadAllBytes('d:\sales-hold-in-queue-music.wav')
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
```

### Create Shared Call History template

### Create Automatic Recording for Call Queue template

### Get Users ID

```powershell
$userAdeleID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity
$userSalesBillID = (Get-CsOnlineUser -Identity "sip:bill@contoso.com").Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity "sip:mary@contoso.com").Identity
```

### Get list of supported languages

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### Create Call queue

```powershell
New-CsCallQueue -Name "Sales" -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID "en-US"
```

### Support (Microsoft Shifts)

- Nested behind Auto Attendant: Yes -
- Calling: Through Support auto attendant, internally, and via the PSTN - resource account required
- Language: English UK
- Greeting: Play an audio file
    - Filename: support-greeting.wav
- Music on hold: Play an audio file
    - Filename: support-hold-in-queue-music.wav
- Call Answering: Microsoft Shifts Support Team
    - Support@contoso.com
- Conference Mode: On
- Routing method: Longest Idle
- Presence-based routing: N/A – on by default because of Longest Idle
- Call agents can opt out of taking calls: No
- Call agent alert time: 15
- Call overflow handling: 200
    - Redirect: Support Shared Voicemail
        - Play an audio file (support-shared-voicemail-greeting.wav)
        - Transcription enabled
- Call timeout handling: 45 minutes
    - Redirect: Support Shared Voicemail
        - TTS: "We're sorry to have kept you waiting and are now transferring your call to voicemail."
        - Transcription enabled
- No agents handling
- Callback: Yes
- Service Level: 30 seconds
- Auth User
- Compliance Recording
- Shared call history
- automatic recording

Expand to see PowerShell commands

### Login

When prompted, enter your Teams administrator credentials.

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MgGraph -Credential $credential
```

### Create audio files

Replace `d:\\` with the path to where the wav files are stored on your computer.

```powershell
$content1 = [System.IO.File]::ReadAllBytes('d:\support-greeting.wav')
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content1).ID

$content2 = [System.IO.File]::ReadAllBytes('d:\support-hold-in-queue-music.wav')
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content2).ID

$content3 = [System.IO.File]::ReadAllBytes('d:\support-shared-voicemail-greeting.wav')
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content3).ID
```

### Get Support team group ID

```powershell
$teamSupportID = (Get-Team -DisplayName "Support").GroupID
```

### Get list of supported languages

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### Create Call queue

```powershell
New-CsCallQueue -Name "Support" -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID "en-US"
```

### Get license types

```powershell
Get-MgSubscribedSku
```

### Create and Assign Resource Account

A phone number isn't required here as the call queue is nested behind an auto attendant.

- ApplicationID
    - Auto Attendant: ce933385-9390-45d1-9512-c8d228074e07
    - Call Queue: 11cd3e2e-fccb-42ad-ad00-878b93575e07

The license type shown after `(PHONESYSTEM_VIRTUALUSER)` must be one that's listed by the `Get-MgSubscribedSku` cmdlet.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Update-MgUser -UserId "Support-RA@contoso.com" -UsageLocation US

Set-MgUserLicense -UserId "Support-RA@contoso.com" -AddLicenses @(contoso:PHONESYSTEM_VIRTUALUSER) -RemoveLicenses @()

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

### Facilities (Teams Channel)

- Nested behind Auto Attendant: No
- Direct calling from PSTN: No (internal calling only)
- Language: French FR
- Greeting: None
- Music on hold: default
- Call Answering: Team: Facilities
- Call Answering Channel: Help Desk
    - Channel Owner: Fred@contoso.com
- Conference Mode: On
- Routing method: Round Robin
- Presence-based routing: On
- Call agents can opt out of taking calls: No
- Call agent alert time: 15
- Call overflow handling: 200
    - Disconnect
- Call timeout handling: 45 minutes
    - Disconnect
- No agents handling
- Callback: Yes
- Service Level: 30 seconds
- Auth User
- Compliance Recording
- Shared call history
- automatic recording

Expand to see PowerShell commands

### Login

When prompted, enter your Teams administrator credentials.

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MgGraph -Credential $credential
```

### Get Facilities team group ID

```powershell
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
```

### Get Facilities Help Desk team channel ID

```powershell
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
```

### Get Facilities Help Desk channel owner user ID

```powershell
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
```

### Get on behalf of Calling Resource Account ID

```powershell
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
```

### Get list of supported languages

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### Create Call queue

```powershell
New-CsCallQueue -Name "Facilities" -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID "fr-FR" -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true
```

### Get license types

```powershell
Get-MgSubscribedSku
```

### Create and assign Resource Account

A phone number isn't required here as the call queue is nested behind an auto attendant.

- ApplicationID
    - Auto Attendant: ce933385-9390-45d1-9512-c8d228074e07
    - Call Queue: 11cd3e2e-fccb-42ad-ad00-878b93575e07

The license type shown after `(PHONESYSTEM_VIRTUALUSER)` must be one that's listed by the `Get-MgSubscribedSku` cmdlet.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Update-MgUser -UserId "Facilities-RA@contoso.com" -UsageLocation US

Set-MgUserLicense -UserId "Facilities-RA@contoso.com" -AddLicenses @(contoso:PHONESYSTEM_VIRTUALUSER) -RemoveLicenses @()

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```