---
layout: Conceptual
title: Reference - PowerShell cmdlets for voice applications - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-reference-cmdlets
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
ms.topic: reference
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
ms.custom:
- Phone System
- seo-marvel-apr2020
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
customer-intent: As a Teams Administrator, I want a reference list of all teams cmdlets needed to fully manage teams phone agent, auto attendant, and call queue configuration
description: Reference - PowerShell cmdlets for Teams Phone Agent, Auto Attendant, and Call Queue
locale: en-us
document_id: f9b9f205-5dee-ffcf-be6c-f01be1439cca
document_version_independent_id: f9b9f205-5dee-ffcf-be6c-f01be1439cca
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-reference-cmdlets.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-reference-cmdlets
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-reference-cmdlets.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: a74989a9-ae3b-2c6e-9d23-b7425cfccbed
---

# Reference - PowerShell cmdlets for voice applications - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

Caution

**Daylight Savings Time changes – Manual changes to auto attendant time zones required by some customers.**

On November 1, 2026, Daylight Savings Time will end in North America.

In Canada, the provinces of Alberta, British Columbia, and Manitoba will remain on Daylight Savings Time and will not move the clocks back one hour.

Customers with Teams Phone Agents serving these provinces that have time zone configurations that reference **(UTC-7:00) Mountain Time (US & Canada)**, **(UTC-8:00) Pacific Time (US & Canada)**, or **(UTC-05:00) Eastern Time (US & Canada)** must be updated as follows:

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

Customers with Teams Phone Agents serving these areas that have time zone configurations that reference **(UTC-05:00) Eastern Time (US & Canada)** should change the time zone selection to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

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

The following cmdlet references are for Microsoft Teams Phone Agent, Auto Attendants, and Call Queues.

## Teams Phone Agent

The following cmdlets are specific to Teams Phone Agent feature configuration. The Auto Attendant cmdlets must also be used in order to create a working Teams Phone Agent.

- [Get-CsMainlineAttendantFlow](/en-us/powershell/module/microsoftteams/get-csmainlineattendantflow)
- [New-CsMainlineAttendantAppointmentBookingFlow](/en-us/powershell/module/microsoftteams/new-csmainlineattendantappointmentbookingflow)
- [Get-CsMainlineAttendantAppointmentBookingFlow](/en-us/powershell/module/microsoftteams/get-csmainlineattendantappointmentbookingflow)
- [Set-CsMainlineAttendantAppointmentBookingFlow](/en-us/powershell/module/microsoftteams/set-csmainlineattendantappointmentbookingflow)
- [Remove-CsMainlineAttendantAppointmentBookingFlow](/en-us/powershell/module/microsoftteams/remove-csmainlineattendantappointmentbookingflow)
- [New-CsMainlineAttendantQuestionAnswerFlow](/en-us/powershell/module/microsoftteams/new-csmainlineattendantquestionanswerflow)
- [Get-CsMainlineAttendantQuestionAnswerFlow](/en-us/powershell/module/microsoftteams/get-csmainlineattendantquestionanswerflow)
- [Set-CsMainlineAttendantQuestionAnswerFlow](/en-us/powershell/module/microsoftteams/set-csmainlineattendantquestionanswerflow)
- [Remove-CsMainlineAttendantQuestionAnswerFlow](/en-us/powershell/module/microsoftteams/remove-csmainlineattendantquestionanswerflow)
- [Get-CsMainlineAttendantSupportedLanguages](/en-us/powershell/module/microsoftteams/get-csmainlineattendantsupportedlanguages)
- [Get-CsMainlineAttendantSupportedVoices](/en-us/powershell/module/microsoftteams/get-csmainlineattendantsupportedvoices)
- [Get-CsMainlineAttendantTenantInformation](/en-us/powershell/module/microsoftteams/get-csmainlineattendanttenantinformation)

## Auto Attendant

The following cmdlets allow you to create and manage an Auto Attendant:

- [New-CsAutoAttendant](/en-us/powershell/module/microsoftteams/new-csautoattendant)
- [Get-CsAutoAttendant](/en-us/powershell/module/microsoftteams/get-csautoattendant)
- [Set-CsAutoAttendant](/en-us/powershell/module/microsoftteams/set-csautoattendant)
- [Update-CsAutoAttendant](/en-us/powershell/module/microsoftteams/update-csautoattendant)
- [Remove-CsAutoAttendant](/en-us/powershell/module/microsoftteams/remove-csautoattendant)
- [New-CsOnlineTimeRange](/en-us/powershell/module/microsoftteams/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/en-us/powershell/module/microsoftteams/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/en-us/powershell/module/microsoftteams/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/en-us/powershell/module/microsoftteams/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/en-us/powershell/module/microsoftteams/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/en-us/powershell/module/microsoftteams/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/en-us/powershell/module/microsoftteams/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/en-us/powershell/module/microsoftteams/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/en-us/powershell/module/microsoftteams/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/en-us/powershell/module/microsoftteams/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/en-us/powershell/module/microsoftteams/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/en-us/powershell/module/microsoftteams/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/en-us/powershell/module/microsoftteams/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/en-us/powershell/module/microsoftteams/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/en-us/powershell/module/microsoftteams/Get-CsAutoAttendantTenantInformation)

For a step-by-step guide to creating an Auto Attendant with PowerShell, see [Creating Auto attendants with PowerShell cmdlets](aa-cq-setup-auto-attendant-cmdlets)

## Call Queue

The following cmdlets allow you to create and manage a Call Queue:

- [New-CsCallQueue](/en-us/powershell/module/microsoftteams/New-CsCallQueue)
- [Get-CsCallQueue](/en-us/powershell/module/microsoftteams/Get-CsCallQueue)
- [Set-CsCallQueue](/en-us/powershell/module/microsoftteams/Set-CsCallQueue)
- [Remove-CsCallQueue](/en-us/powershell/module/microsoftteams/Remove-CsCallQueue)

For a step-by-step guide to creating a Call Queue with PowerShell, see [Call Queues with PowerShell](aa-cq-setup-call-queue-cmdlets)

### Compliance Recording for Call Queues

The following cmdlets allow you to create and manage Compliance Recording for Call Queue templates:

- [New-CsComplianceRecordingForCallQueueTemplate](/en-us/powershell/module/microsoftteams/New-CsComplianceRecordingForCallQueueTemplate)
- [Get-CsComplianceRecordingForCallQueueTemplate](/en-us/powershell/module/microsoftteams/Get-CsComplianceRecordingForCallQueueTemplate)
- [Set-CsComplianceRecordingForCallQueueTemplate](/en-us/powershell/module/microsoftteams/Set-CsComplianceRecordingForCallQueueTemplate)
- [Remove-CsComplianceRecordingForCallQueueTemplate](/en-us/powershell/module/microsoftteams/Remove-CsComplianceRecordingForCallQueueTemplate)

### Shared call history

- [New-CsSharedCallQueueHistoryTemplate](/en-us/powershell/module/microsoftteams/New-CsSharedCallQueueHistoryTemplate)
- [Get-CsSharedCallQueueHistoryTemplate](/en-us/powershell/module/microsoftteams/Get-CsSharedCallQueueHistoryTemplate)
- [Set-CsSharedCallQueueHistoryTemplate](/en-us/powershell/module/microsoftteams/Set-CsSharedCallQueueHistoryTemplate)
- [Remove-CsSharedCallQueueHistoryTemplate](/en-us/powershell/module/microsoftteams/Remove-CsSharedCallQueueHistoryTemplate)

## Common cmdlets used by Teams Phone Agent, Auto Attendant, and Call Queue

The following cmdlets are also required to manage common components of Teams Phone Agent, Auto Attendant and Call Queue such as:

- Users
- Resource accounts
- Licenses
- Phone numbers
- Audio files (for Auto Attendant and Call Queue only)
- Supported languages (for Auto Attendant and Call Queue only. See Teams Phone Agent for equivalent cmdlets.)

### Automatic Recording for Teams Phone Agent and Call Queue

The following cmdlets allow you to create and manage Automatic Recording templates:

- [New-CsAutoRecordingTemplate](/en-us/powershell/module/microsoftteams/New-CsAutoRecordingTemplate)
- [Get-CsAutoRecordingTemplate](/en-us/powershell/module/microsoftteams/Get-CsAutoRecordingTemplate)
- [Set-CsAutoRecordingTemplate](/en-us/powershell/module/microsoftteams/Set-CsAutoRecordingTemplate)
- [Remove-CsAutoRecordingTemplate](/en-us/powershell/module/microsoftteams/Remove-CsAutoRecordingTemplate)

### Users and Teams

- Users

    - [Get-CsOnlineUser](/en-us/powershell/module/microsoftteams/Get-CsOnlineUser)
- Teams:

    - [Get-Team](/en-us/powershell/module/microsoftteams/Get-Team)
    - [Get-TeamChannel](/en-us/powershell/module/microsoftteams/Get-TeamChannel)

### Resource accounts

- [New-CsOnlineApplicationInstance](/en-us/powershell/module/microsoftteams/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/en-us/powershell/module/microsoftteams/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/en-us/powershell/module/microsoftteams/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/en-us/powershell/module/microsoftteams/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/en-us/powershell/module/microsoftteams/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/en-us/powershell/module/microsoftteams/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/en-us/powershell/module/microsoftteams/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/en-us/powershell/module/microsoftteams/Get-CsOnlineApplicationInstanceAssociationStatus)

### Teams Phone Resource Account licenses

- [Get-MgSubscribedSku](/en-us/powershell/module/microsoft.graph.identity.directorymanagement/get-mgsubscribedsku)
- [Set-MgUserLicense](/en-us/powershell/module/microsoft.graph.users.actions/set-mguserlicense)

### Phone number assignment

- [Get-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/Get-CsPhoneNumberAssignment)
- [Set-CsPhoneNumberAssignment](/en-us/powershell/module/microsoftteams/Set-CsPhoneNumberAssignment)

### Audio files (for Auto attendants and Call queues only)

- [Get-CsOnlineAudioFile](/en-us/powershell/module/microsoftteams/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/en-us/powershell/module/microsoftteams/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/en-us/powershell/module/microsoftteams/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/en-us/powershell/module/microsoftteams/Remove-CsOnlineAudioFile)

### Supported languages (for Auto Attendant and Call Queue only)

- [Get-CsAutoAttendantSupportedLanguage](/en-us/powershell/module/microsoftteams/Get-CsAutoAttendantSupportedLanguage)

### Supported time zones (for Teams Phone Agent and Auto Attendant only)

- [Get-CsAutoAttendantSupportedTimeZone](/en-us/powershell/module/microsoftteams/Get-CsAutoAttendantSupportedTimeZone)

### Voice applications policies

- [Get-CsTeamsVoiceApplicationsPolicy](/en-us/powershell/module/microsoftteams/Get-CsTeamsVoiceApplicationsPolicy)
- [Grant-CsTeamsVoiceApplicationsPolicy](/en-us/powershell/module/microsoftteams/Grant-CsTeamsVoiceApplicationsPolicy)
- [New-CsTeamsVoiceApplicationsPolicy](/en-us/powershell/module/microsoftteams/New-CsTeamsVoiceApplicationsPolicy)
- [Remove-CsTeamsVoiceApplicationsPolicy](/en-us/powershell/module/microsoftteams/Remove-CsTeamsVoiceApplicationsPolicy)
- [Set-CsTeamsVoiceApplicationsPolicy](/en-us/powershell/module/microsoftteams/Set-CsTeamsVoiceApplicationsPolicy)