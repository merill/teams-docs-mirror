---
layout: Conceptual
title: Setup - Create an Auto attendant via PowerShell - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-auto-attendant-cmdlets
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
- Phone System
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
description: Learn how to configure auto attendants via PowerShell
locale: en-us
document_id: 6ad1c0f2-1ddc-5c9c-8eec-1d0c90f5d48f
document_version_independent_id: 6ad1c0f2-1ddc-5c9c-8eec-1d0c90f5d48f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-auto-attendant-cmdlets.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-auto-attendant-cmdlets
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-auto-attendant-cmdlets.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6f60655a-7fdc-2c52-f6fd-408450643669
---

# Setup - Create an Auto attendant via PowerShell - Microsoft Teams | Microsoft Learn

Caution

**Daylight Savings Time changes – Manual changes to auto attendant time zones required by some customers.**

On November 1, 2026, Daylight Savings Time will end in North America.

In Canada, the provinces of Alberta, British Columbia, and Manitoba will remain on Daylight Savings Time and will not move the clocks back one hour.

Customers with auto attendants serving these provinces that have time zone configurations that reference **(UTC-7:00) Mountain Time (US & Canada)**, **(UTC-8:00) Pacific Time (US & Canada)**, or **(UTC-05:00) Eastern Time (US & Canada)** must be updated as follows:

- Alberta: Permanently moves to UTC-6:00.

    - Change the auto attendant time zone selection from **(UTC-7:00) Mountain Time (US & Canada)** to **(UTC-6:00) Saskatchewan** as DST is not observed in Saskatchewan.
- British Columbia: Permanently moves to UTC-7:00.

    - Change the auto attendant time zone selection from **(UTC-8:00) Pacific Time (US & Canada)** to **(UTC-7:00) Arizona** as DST is not observed in Arizona.
- Manitoba: Permanently moves to UTC-5:00.

    - Change the auto attendant time zone selection from **(UTC-05:00) Eastern Time (US & Canada)** to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

In Ontario, the following communities and areas will not turn clocks back and will remain on Central Daylight Time year‑round:

- Kenora
- Dryden
- Fort Frances
- Sioux Lookout
- Red Lake
- Rainy River
- Other communities west of the 90th meridian that currently follow Central Time and change clocks seasonally

Customers with auto attendants serving these areas that have time zone configurations that reference **(UTC-05:00) Eastern Time (US & Canada)** should change the time zone selection to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

## What's new in Auto Attendant (last six months)

- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) updated.

## Prerequisites

1. Install PowerShell on your computer.

    - Set up your computer for [Windows PowerShell](/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    - MSTeams Module Installed

        ```PowerShell
        Install-Module -Name MicrosoftTeams -Force -AllowClobber
        ```
    - Microsoft Graph module installed

        ```powershell
        Install-Module -Name Microsoft.Graph -Force -AllowClobber
        ```
2. Ensure you have tenant administration rights.
3. Purchase Microsoft Teams Phone.
4. The call queues mentioned in this article were set up using the [Creating Call Queues with PowerShell cmdlets](aa-cq-setup-call-queue-cmdlets) guide.

Note

Some of the cmdlets mentioned in this article may be part of the Public Preview version of Teams PowerShell Module. For more information, see [Install Teams PowerShell public preview](teams-powershell-install) and also see [Microsoft Teams PowerShell Release Notes](teams-powershell-release-notes).

Users who already have the MicrosoftTeams module installed should `Update-Module MicrosoftTeams` to ensure the most up-to-date version is installed.

## Scenario

The following auto attendant call flow is built:

![Diagram of Auto Attendant call flow being built with cmdlets.](media/aa-cq/create-a-phone-system-auto-attendant-via-cmdlets.png)

Useful configuration information:

- Auto Attendant: Contoso Main

    - Operator: Adele Vance
    - Enable Voice Inputs: Off
    - Directory Search: None
    - Holidays:
        - January 1, 2022
        - December 24, 2022
        - December 25, 2022
- Auto Attendant: Contoso Dial By Name

    - Operator: Adele Vance
    - Time zone: UTC
    - Language: English US
    - Enable Voice Inputs: On
    - Greeting: None
    - Menu: TTS, "Please say or enter the name of the person you would like to reach. To return to the previous menu press 9"
    - Directory Search: Dial By Name
    - Dial Scope: Sales & Support members

## Login

When prompted, enter your Teams administrator credentials.

```PowerShell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MgGraph -Credential $credential
```

## Get Operator Information

```PowerShell
$operatorID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity

$operatorEntity = New-CsAutoAttendantCallableEntity -Identity $operatorID -Type User
```

## Dial By Name Auto Attendant - Resource Account Creation

Create a resource account here so it can be referenced on the main auto attendant. You can create the actual Dial By Name auto attendant later.

### Get license types

```PowerShell
Get-MgSubscribedSku
```

### Create and assign Resource Account

A phone number isn't required here as the call queue is nested behind an auto attendant.

- ApplicationID
    - Auto Attendant: ce933385-9390-45d1-9512-c8d228074e07
    - Call Queue: 11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoDialByNameAA-RA@contoso.com -DisplayName "Contoso Dial By Name AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Update-MgUser -UserId "ContosoDialByNameAA-RA@contoso.com" -UsageLocation US

Set-MgUserLicense -UserId "ContosoDialByNameAA-RA@contoso.com" -AddLicenses @(contoso:PHONESYSTEM_VIRTUALUSER) -RemoveLicenses @()

$dialByNameApplicationInstanceID = (Get-CsOnlineUser "ContosoDialByNameAA-RA@contoso.com").Identity
```

## Contoso Main Menu Auto Attendant

### Create Holiday Schedules

```PowerShell
$dtr = New-CsOnlineDateTimeRange -Start "24/12/2022" -End "25/12/2022"

$christmasSchedule = New-CsOnlineSchedule -Name "Christmas" -FixedSchedule -DateTimeRanges @($dtr)

$dtr = New-CsOnlineDateTimeRange -Start "01/01/2022" -End "02/01/2022"

$newyearSchedule = New-CsOnlineSchedule -Name "New Year" -FixedSchedule -DateTimeRanges @($dtr)
```

### Create Address, FAX, and Email Information Prompt

```PowerShell
$addressPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To repeat this information at any time press the * key. Our mailing address is: 123 Main Street, Any town, Any Place, County. Our email address is: info@contoso.com. Our fax number is: 929-555-0151"
```

### Create Holiday Prompts and Menu Options

```PowerShell
$christmasGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the Christmas holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contoso."

$christmasMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$christmasMenu = New-CsAutoAttendantMenu -Name "Christmas Menu" -MenuOptions @($christmasMenuOption)

$christmasCallFlow = New-CsAutoAttendantCallFlow -Name "Christmas" -Greetings @($christmasGreetingPrompt) -Menu $christmasMenu

$christmasCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $christmasSchedule.Id -CallFlowId $christmasCallFlow.Id

$newyearGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the New Year's holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contoso."

$newyearMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$newyearMenu = New-CsAutoAttendantMenu -Name "New Year Menu" -MenuOptions @($newyearMenuOption)

$newyearCallFlow = New-CsAutoAttendantCallFlow -Name "New Year" -Greetings @($newyearGreetingPrompt) -Menu $newyearMenu

$newyearCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $newyearSchedule.Id -CallFlowId $newyearCallFlow.Id
```

### Create After Hours Schedules

```PowerShell
$timerangeMoFr = New-CsOnlineTimeRange -Start 08:30 -end 17:00

$timerangeSa = New-CsOnlineTimeRange -Start 10:00 -end 16:00

$afterHoursSchedule = New-CsOnlineSchedule -Name "After Hours Schedule" -WeeklyRecurrentSchedule -MondayHours @($timerangeMoFr) -TuesdayHours @($timerangeMoFr) -WednesdayHours @($timerangeMoFr) -ThursdayHours @($timerangeMoFr) -FridayHours @($timerangeMoFr) -SaturdayHours @($timerangeSa) -Complement
```

### Create After Hours Prompts and Menu Options

```PowerShell
$afterHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices are now closed. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time."

$afterHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To leave a voicemail for our sales team press 1. To leave a message for our support team press 2. If you know the name of the person you would like to reach, press 3. For our address, email and fax information press 4."

$afterHoursMenuOption1Target = (Get-Team -displayname "Sales").GroupID

$afterHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption1Target -Type SharedVoiceMail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $afterHoursMenuOption1Entity

$afterHoursMenuOption2Target = (Get-Team -displayname "Support").GroupID

$afterHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption2Target -Type SharedVoicemail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $afterHoursMenuOption2Entity

$dialbynameAAOption3Target = (Get-CsOnlineUser -Identity "ContosoDialByNameAA-RA@contoso.com").Identity

$dialbynameAAMenuOption3Entity = New-CsAutoAttendantCallableEntity -Identity $dialbynameAAOption3Target -Type applicationendpoint

$dialbynameAAMenuOption3 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone3 -CallTarget $dialbynameAAMenuOption3Entity

$afterHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt
```

### Create After Hours Menu and Call Flow

```PowerShell
$afterHoursMenu = New-CsAutoAttendantMenu -Name "After Hours Menu" -MenuOptions @($afterHoursMenuOption1, $afterHoursMenuOption2, $dialbynameAAMenuOption3, $afterHoursMenuOption4) -Prompt $afterHoursMenuPrompt

$afterHoursCallFlow = New-CsAutoAttendantCallFlow -Name "After Hours Call Flow" -Greetings @($afterHoursGreetingPrompt) -Menu $afterHoursMenu

$afterHoursCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type AfterHours -ScheduleId $afterHoursSchedule.Id -CallFlowId $afterHoursCallFlow.Id
```

### Create Open Hours Prompts and Menu Options

```PowerShell
$openHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt " Thank you for calling Contoso."

$openHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "For Sales press 1. For Support press 2. If you know the name of the person you would like to reach, press 3. For our address, email and fax information, press 4. For all other inquiries press 0 to speak with the operator."

$openHoursMenuOption1Target = (Get-CsOnlineUser "Sales-RA@contoso.com").Identity

$openHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption1Target -Type applicationendpoint

$openHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $openHoursMenuOption1Entity

$openHoursMenuOption2Target = (Get-CsOnlineUser "Support-RA@contoso.com").Identity

$openHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption2Target -Type applicationendpoint

$openHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $openHoursMenuOption2Entity

$openHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt

$openHoursMenuOption0 = New-CsAutoAttendantMenuOption -Action TransferCallToOperator -DtmfResponse Tone0
```

### Create Open Hours Menu

```PowerShell
$openHoursMenu = New-CsAutoAttendantMenu -Name "Open Hours Menu" -MenuOptions @($openHoursMenuOption1, $openHoursMenuOption2, $dialbynameAAMenuOption3, $openHoursMenuOption4, $openHoursMenuOption0) -Prompt $openHoursMenuPrompt

$openHoursCallFlow = New-CsAutoAttendantCallFlow -Name "Open Hours Call Flow" -Greetings @($openHoursGreetingPrompt) -Menu $openHoursMenu
```

### Create Auto Attendant

```PowerShell
$autoAttendant = New-CsAutoAttendant -Name "Contoso Main" -DefaultCallFlow $openHoursCallFlow -CallFlows @($afterHoursCallFlow, $christmasCallFlow, $newyearCallFlow) -CallHandlingAssociations @($afterHoursCallHandlingAssociation, $christmasCallHandlingAssociation, $newyearCallHandlingAssociation) -LanguageId "en-US" -TimeZoneId "Eastern Standard Time" -Operator $operatorEntity
```

### Get license types

```PowerShell
Get-MgSubscribedSku
```

### Create and assign Resource Account

- ApplicationID
    - Auto Attendant: ce933385-9390-45d1-9512-c8d228074e07
    - Call Queue: 11cd3e2e-fccb-42ad-ad00-878b93575e07

```PowerShell
New-CsOnlineApplicationInstance -UserPrincipalName ContosoMainAA-RA@contoso.com -DisplayName "Contoso Main AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Update-MgUser -UserId "ContosoMainAA-RA@contoso.com" -UsageLocation US

$Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'contoso:PHONESYSTEM_VIRTUALUSER'
$addLicenses = @(
@{SkuId = $Sku.SkuId}
)

Set-MgUserLicense -UserId 'ContosoDialByNameAA-RA@contoso.com' -AddLicenses $addLicenses -RemoveLicenses @()

$applicationInstanceID = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$autoAttendantID = (Get-CsAutoAttendant -NameFilter "Contoso Main").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $autoAttendantID -ConfigurationType AutoAttendant
```

### Get list of unassigned service numbers

```PowerShell
Get-CsPhoneNumberAssignment -PstnAssignmentStatus Unassigned -CapabilitiesContain VoiceApplicationAssignment
```

#### Assign available phone number

The usage location assigned to the phone number must match the usage location assigned to the Resource Account.

```PowerShell
Set-CsPhoneNumberAssignment -Identity ContosoMainAA-RA@contoso.com -PhoneNumber +{spare number from output of above command} -PhoneNumberType CallingPlan
```

## Dial By Name Auto Attendant - Completion

### Create Dial Scope

```PowerShell
$salesGroupID = Find-CsGroup -SearchQuery "Sales" | % { $_.Id }

$supportGroupID = Find-CsGroup -SearchQuery "Support" | % { $_.Id }

$dialScope = New-CsAutoAttendantDialScope -GroupScope -GroupIds @($salesGroupID, $supportGroupID)
```

### Create Prompts and Menu Options

```PowerShell
$dialByNameMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Please say or enter the name of the person you would like to reach. To return to the previous menu press 9."

$dialByNameMenuOption9Target = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").Identity

$dialByNameMenuOption9Entity = New-CsAutoAttendantCallableEntity -Identity $dialByNameMenuOption9Target -Type applicationendpoint

$dialByNameMenuOption9 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone9 -CallTarget $dialByNameMenuOption9Entity

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt -EnableDialByName -DirectorySearchMethod ByName

$dialByNameCallFlow = New-CsAutoAttendantCallFlow -Name "Contoso Dial By Name Call Flow" -Menu $dialByNameMenu

$dialByNameAutoAttendant = New-CsAutoAttendant -Name "Contoso Dial By Name" -DefaultCallFlow $dialByNameCallFlow -LanguageId "en-US" -TimeZoneId "UTC" -Operator $operatorEntity -EnableVoiceResponse -InclusionScope $dialScope
```

### Assign Resource Account

```PowerShell
New-CsOnlineApplicationInstanceAssociation -Identities @($dialByNameApplicationInstanceID) -ConfigurationID $dialByNameAutoAttendant.Id -ConfigurationType AutoAttendant
```