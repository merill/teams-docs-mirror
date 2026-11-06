---
layout: Conceptual
title: Reference - Supported Configurations - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-reference-limits-supported-configurations
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
ms.topic: reference
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
audience: Admin
ms.date: 2026-11-03T00:00:00.0000000Z
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
customer-intent: As a Teams Administrator, I want to learn about Teams Phone Agent, Auto Attendant, and Call Queue supported configurations to ensure my organization stays within supported limits.
description: Reference the supported configurations and maximums for Teams Phone Agent, auto attendants, and call queues, including languages, voices, and queue limits.
locale: en-us
document_id: a6b2b037-b72b-a477-04eb-848d423a0ab7
document_version_independent_id: a6b2b037-b72b-a477-04eb-848d423a0ab7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-reference-limits-supported-configurations.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-reference-limits-supported-configurations
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-reference-limits-supported-configurations.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: 7a3f39c8-dc13-2bd1-b8f2-577007801d45
---

# Reference - Supported Configurations - Microsoft Teams | Microsoft Learn

This article is for IT pros and administrators who want to understand the supported configurations and limits.

## Teams Phone Agents

- Teams Phone Agents per tenant: No limit
- Languages/Locales: 63
- Voices: 42
- Dial by name / Dial by number per Teams Phone Agent: 1
    - For more information, see [Dial by name or number reference](aa-cq-reference-dial-by-name-number)
- After hours call flows: 1
- Holiday call flows: No limit
- Holiday sets per Teams Phone Agent: 20
- Holidays per holiday set: 50
- Automatic Recording templates: 1

### Teams Phone Agent languages / locales

Languages/Locales: 63 (Expand to see list of supported languages/locales)

| # | Locale | Language | Optimized Voice |
| --- | --- | --- | --- |
| 01 | ar-EG | Arabic (Egypt) |  |
| 02 | ar-SA | Arabic (Saudi Arabia) |  |
| 03 | hy-AM | Armenian (Armenia) |  |
| 04 | bg-BG | Bulgarian (Bulgaria) |  |
| 05 | ca-ES | Catalan (Spain) |  |
| 06 | zh-CN | Chinese (Simplified, PRC) | Xiaoqi, 🎵 [Xiaoxiao](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/5386fbd85fec2a30.wav), Yunfan, 🎵 [Yunxiao](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/0d7132d65af0021a.wav) |
| 07 | zh-HK | Chinese (Traditional, Hong Kong SAR) |  |
| 08 | zh-TW | Chinese (Traditional, Taiwan) |  |
| 09 | hr-HR | Croatian (Croatia) |  |
| 10 | cs-CZ | Czech (Czechia) |  |
| 11 | da-BE | Danish (Belgium) |  |
| 12 | da-DK | Danish (Denmark) |  |
| 13 | nl-NL | Dutch (Netherlands) |  |
| 14 | en-AU | English (Australia) | Siennatopaz |
| 15 | en-CA | English (Canada) |  |
| 16 | en-GB | English (United Kingdom) | Ollie |
| 17 | en-IE | English (Ireland) |  |
| 18 | en-IN | English (India) | 🎵 [Aarti](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/b5b6793994cc8297.wav) |
| 19 | en-PH | English (Philippines) |  |
| 20 | en-US | English (United States) | 🎵 [Andrew](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/0d788fa6d3b13b1d.wav), 🎵 [Ava](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/76dc76cf370e8d30.wav), Tessa |
| 21 | en-ZA | English (South Africa) |  |
| 22 | et-EE | Estonian (Estonia) |  |
| 23 | fi-FI | Finnish (Finland) |  |
| 24 | fr-BE | French (Belgium) |  |
| 25 | fr-CA | French (Canada) |  |
| 26 | fr-CH | French (Switzerland) |  |
| 27 | fr-FR | French (France) | Remy |
| 28 | gl-ES | Galician (Spain) |  |
| 29 | de-AT | German (Austria) |  |
| 30 | de-CH | German (Switzerland) |  |
| 31 | de-DE | German (Germany) | 🎵 [Florian](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/a9dcb83eef8018e5.wav), Seraphina |
| 32 | el-GR | Greek (Greece) |  |
| 33 | he-IL | Hebrew (Israel) |  |
| 34 | hi-IN | Hindi (India) | 🎵 [Diya](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/5908b5cfd1247ee1.wav), 🎵 [Meera](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/6fd584f9d50c9a45.wav) |
| 35 | hu-HU | Hungarian (Hungary) |  |
| 36 | is-IS | Icelandic (Iceland) |  |
| 37 | id-ID | Indonesian (Indonesia) |  |
| 38 | it-IT | Italian (Italy) | Isabella |
| 39 | ja-JP | Japanese (Japan) |  |
| 40 | kn-IN | Kannada (India) |  |
| 41 | ko-KR | Korean (Korea) |  |
| 42 | lv-LV | Latvian (Latvia) |  |
| 43 | lt-LT | Lithuanian (Lithuania) |  |
| 44 | mr-IN | Marathi (India) |  |
| 45 | nb-NO | Norwegian Bokmål (Norway) |  |
| 46 | fa-IR | Persian (Iran) |  |
| 47 | pl-PL | Polish (Poland) |  |
| 48 | pt-BR | Portuguese (Brazil) | Thalita |
| 49 | pt-PT | Portuguese (Portugal) |  |
| 50 | ro-RO | Romanian (Romania) |  |
| 51 | ru-RU | Russian (Russia) |  |
| 52 | sr-RS | Serbian (Serbia) |  |
| 53 | sk-SK | Slovak (Slovakia) |  |
| 54 | sl-SI | Slovenian (Slovenia) |  |
| 55 | es-MX | Spanish (Mexico) |  |
| 56 | es-ES | Spanish (Spain, International) | 🎵 [Ximena](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/5c0ab10bfbdf65f6.wav) |
| 57 | sv-SE | Swedish (Sweden) |  |
| 58 | ta-IN | Tamil (India) |  |
| 59 | th-TH | Thai (Thailand) |  |
| 60 | tr-TR | Turkish (Turkey) |  |
| 61 | uk-UA | Ukrainian (Ukraine) |  |
| 62 | ur-PK | Urdu (Pakistan) |  |
| 63 | vi-VN | Vietnamese (Vietnam) |  |

### Teams Phone Agent voices

Voices: 42 (Expand to see list of supported voices)

| # | Name | Available for all languages | Optimized for |
| --- | --- | --- | --- |
| 01 | 🎵 [Aarti](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/b5b6793994cc8297.wav) | Y | en-IN - English (India) |
| 02 | 🎵 [Andrew](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/0d788fa6d3b13b1d.wav) | Y | en-US - English (US) |
| 03 | Angelo | Y |  |
| 04 | Ardi | Y |  |
| 05 | Arjun | Y |  |
| 06 | Athina | Y |  |
| 07 | 🎵 [Ava](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/76dc76cf370e8d30.wav)^1 ^ | Y | en-US - English (US) |
| 08 | Blessica | Y |  |
| 09 | Dalia | Y |  |
| 10 | 🎵 [Diya](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/5908b5cfd1247ee1.wav) | Y | hi-IN - Hindi (India) |
| 11 | 🎵 [Florian](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/a9dcb83eef8018e5.wav) | Y | de-DE - German (Germany) |
| 12 | Gadis | Y |  |
| 13 | Giuseppe | Y |  |
| 14 | Hyunsu | Y |  |
| 15 | Isabella | Y | it-IT - Italian (Italy) |
| 16 | Jorge | Y |  |
| 17 | Mariela | Y |  |
| 18 | Masaru | Y |  |
| 19 | 🎵 [Meera](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/6fd584f9d50c9a45.wav) | Y | hi-IN - Hindi |
| 20 | Nadira | Y |  |
| 21 | Nanami | Y |  |
| 22 | Ollie | Y | en-GB - English (United Kingdom) |
| 23 | Osman | Y |  |
| 24 | Remy | Y | fr-FR - French (France) |
| 25 | Seraphina | Y | de-DE - German (Germany) |
| 26 | Siennatopaz | N | en-AU - English (Australia) |
| 27 | Sonia | Y |  |
| 28 | SunHi | Y |  |
| 29 | Sylvie | Y |  |
| 30 | Tessa | N | en-US - English (United States) |
| 31 | Thalita | Y | pt-BR - Portuguese (Brazil) |
| 32 | Thierry | Y |  |
| 33 | Tristan | Y |  |
| 34 | Tyler | Y |  |
| 35 | Vivienne | Y |  |
| 36 | William | Y |  |
| 37 | Xiaoqi | Y | zh-CN - Chinese (Simplified, PRC) |
| 38 | 🎵 [Xiaoxiao](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/5386fbd85fec2a30.wav) | Y | zh-CN - Chinese (Simplified, PRC) |
| 39 | 🎵 [Ximena](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/5c0ab10bfbdf65f6.wav) | Y | es-ES - Spanish (Spain) |
| 40 | Yasmin | Y |  |
| 41 | Yunfan | Y | zh-CN - Chinese (Simplified, PRC) |
| 42 | 🎵 [Yunxiao](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/0d7132d65af0021a.wav) | Y | zh-CN - Chinese (Simplified, PRC) |

1. Ava is the default voice and is recommended for all langauges that don't have an optimized voice.

## Auto Attendants

- Auto attendants per tenant: No limit
- Voices: 2 (male/female)
    - Auto selected based on selected language / locale, can only be selected via PowerShell
- Dial by name / Dial by number per Auto attendant: 1
    - For more details, see [Dial by name or number reference](aa-cq-reference-dial-by-name-number)
- After hours call flows: 1
- Holiday call flows: No limit
- Holiday sets per Auto Attendant: 20
- Holidays per holiday set: 50
- Authorized users: 15

### Auto Attendant languages / locales

- Languages/Locales:
    - Text to speech: 54
    - Speech recognition: 14

Languages/Locales: 54 Expand to see list of supported language/locales

| # | Language | Text to Speech (TTS) | Speech Recognition |
| --- | --- | --- | --- |
| 01 | Arabic (Egypt) | Y | N |
| 02 | Arabic (Saudi Arabia) | Y | N |
| 03 | Bulgarian (Bulgaria) | Y | N |
| 04 | Catalan (Spain) | Y | N |
| 05 | Chinese (Simplified, PRC) | Y | Y |
| 06 | Chinese (Traditional, Hong Kong SAR) | Y | N |
| 07 | Chinese (Traditional, Taiwan) | Y | N |
| 08 | Croatian (Croatia) | Y | N |
| 09 | Czech (Czech Republic) | Y | N |
| 10 | Danish (Denmark) | Y | N |
| 11 | Danish (Belgium) | Y | N |
| 12 | Dutch (Netherlands) | Y | N |
| 13 | English (Australia) | Y | Y |
| 14 | English (Canada) | Y | Y |
| 15 | English (India) | Y | Y |
| 16 | English (Ireland) | Y | N |
| 17 | English (Philippines) | Y | N |
| 18 | English (South Africa) | Y | N |
| 19 | English (United Kingdom) | Y | Y |
| 20 | English (United States) | Y | Y |
| 21 | Estonian (Estonia) | Y | N |
| 22 | Finnish (Finland) | Y | N |
| 23 | French (Belgium) | Y | N |
| 24 | French (Canada) | Y | Y |
| 25 | French (France) | Y | Y |
| 26 | French (Switzerland) | Y | Y |
| 27 | German (Austria) | Y | N |
| 28 | German (Germany) | Y | Y |
| 29 | German (Switzerland) | Y | N |
| 30 | Greek (Greece) | Y | N |
| 31 | Hebrew (Israel) | Y | N |
| 32 | Hindi (India) | Y | N |
| 33 | Hungarian (Hungary) | Y | N |
| 34 | Indonesian (Indonesia) | Y | N |
| 35 | Italian (Italy) | Y | Y |
| 36 | Japanese (Japan) | Y | Y |
| 37 | Korean (Korea) | Y | N |
| 38 | Latvian (Latvia) | Y | N |
| 39 | Lithuanian (Lithuania) | Y | N |
| 40 | Norwegian Bokmal (Norway) | Y | N |
| 41 | Polish (Poland) | Y | N |
| 42 | Portuguese (Brazil) | Y | Y |
| 43 | Portuguese (Portugal) | Y | N |
| 44 | Romanian (Romania) | Y | N |
| 45 | Russian (Russia) | Y | N |
| 46 | Slovak (Slovakia) | Y | N |
| 47 | Slovenian (Slovenia) | Y | N |
| 48 | Spanish (Mexico) | Y | Y |
| 49 | Spanish (Spain, International) | Y | Y |
| 50 | Swedish (Sweden) | Y | N |
| 51 | Thai (Thailand) | Y | N |
| 52 | Turkish (Türkiye) | Y | N |
| 53 | Vietnamese (Vietnam) | Y | N |
| 54 | Welsh (United Kingdom) | Y | N |

Note

Auto attendant:

- Choosing a language that doesn't support Speech Recognition disables the voice inputs option within the menu, and dial by name is restricted to using keypad (DTMF) entry only. For more information, see [Dial by Name - Keypad (DTMF) entry](aa-cq-reference-dial-by-name-number#keypad-dtmf-entry).

When using Text to Speech, the text must be entered in the selected language as the system doesn't perform translation.

## Call Queues

- Call queues per tenant: No limit
- Call queues per representative: No limit
- Representatives per Call queue: 200
    - Maximum added as individual users: 20 (not supported if using Automatic Recording for Call Queues)
- Maximum calls waiting per queue: 200
- Maximum call waiting time per call per queue: 45 minutes
- Call representative alert time (seconds):
    - Minimum: 15
    - Maximum: 180^1^
- Maximum authorized users per queue: 15
- Voices: 2 (male/female)
    - Auto selected based on selected language / locale, can't be changed
- Authorized users: 15
- Automatic Recording templates: 1
- Compliance Recording templates: 2

Notes:

1. For representatives using Teams on Windows with a Bluetooth device selected as their Teams audio device, the maximum ring time will be 120 seconds. This applies when the Bluetooth device is selected in Teams and its answer/end call buttons are available for Teams calls.

### Call Queue languages / locales

Languages/Locales: 54 (Expand to see list of supported language/locales)

| # | Language | Text to Speech (TTS) |
| --- | --- | --- |
| 01 | Arabic (Egypt) | Y |
| 02 | Arabic (Saudi Arabia) | Y |
| 03 | Bulgarian (Bulgaria) | Y |
| 04 | Catalan (Spain) | Y |
| 05 | Chinese (Simplified, PRC) | Y |
| 06 | Chinese (Traditional, Hong Kong SAR) | Y |
| 07 | Chinese (Traditional, Taiwan) | Y |
| 08 | Croatian (Croatia) | Y |
| 09 | Czech (Czech Republic) | Y |
| 10 | Danish (Denmark) | Y |
| 11 | Danish (Belgium) | Y |
| 12 | Dutch (Netherlands) | Y |
| 13 | English (Australia) | Y |
| 14 | English (Canada) | Y |
| 15 | English (India) | Y |
| 16 | English (Ireland) | Y |
| 17 | English (Philippines) | Y |
| 18 | English (South Africa) | Y |
| 19 | English (United Kingdom) | Y |
| 20 | English (United States) | Y |
| 21 | Estonian (Estonia) | Y |
| 22 | Finnish (Finland) | Y |
| 23 | French (Belgium) | Y |
| 24 | French (Canada) | Y |
| 25 | French (France) | Y |
| 26 | French (Switzerland) | Y |
| 27 | German (Austria) | Y |
| 28 | German (Germany) | Y |
| 29 | German (Switzerland) | Y |
| 30 | Greek (Greece) | Y |
| 31 | Hebrew (Israel) | Y |
| 32 | Hindi (India) | Y |
| 33 | Hungarian (Hungary) | Y |
| 34 | Indonesian (Indonesia) | Y |
| 35 | Italian (Italy) | Y |
| 36 | Japanese (Japan) | Y |
| 37 | Korean (Korea) | Y |
| 38 | Latvian (Latvia) | Y |
| 39 | Lithuanian (Lithuania) | Y |
| 40 | Norwegian Bokmal (Norway) | Y |
| 41 | Polish (Poland) | Y |
| 42 | Portuguese (Brazil) | Y |
| 43 | Portuguese (Portugal) | Y |
| 44 | Romanian (Romania) | Y |
| 45 | Russian (Russia) | Y |
| 46 | Slovak (Slovakia) | Y |
| 47 | Slovenian (Slovenia) | Y |
| 48 | Spanish (Mexico) | Y |
| 49 | Spanish (Spain, International) | Y |
| 50 | Swedish (Sweden) | Y |
| 51 | Thai (Thailand) | Y |
| 52 | Turkish (Türkiye) | Y |
| 53 | Vietnamese (Vietnam) | Y |
| 54 | Welsh (United Kingdom) | Y |

Important

When using Text to Speech, the text must be entered in the selected language as the system doesn't perform translation.

### Call Queue feature compatibility by call queue type

Expand to see table

| Feature | Standard Call Queues^1^ | Channel Based Call Queues^2^ | Shifts Based Call Queues^3^ | Comment |
| --- | --- | --- | --- | --- |
| **Agent Routing Methods** |  |  |  |  |
| Attendant Routing | Y | Y | Y | *Default* |
| Longest Idle^4^ | Y | Y | Y | *Recommended* |
| Round Robin | Y | Y | Y | *Recommended* |
| Serial | Y | Y | Y | See Note 5 |
| **Agent Routing Options** |  |  |  |  |
| Presence Based Routing^4^ | Y | Y | Y^6^ | *Default* |
| Agents can opt out | Y | Y | Y^6^ | *Default* |
| **Transfer Modes** |  |  |  |  |
| Conference Mode^7^ | Y | Y | Y | *Default* |
| Transfer Mode | Y | Y | Y | See Note 8 |
| **PSTN Connectivity Methods** |  |  |  | See Note 9 |
| Calling Plans | Y | Y | Y |  |
| Direct Routing | Y | Y | Y | See Note 10 & 11 |
| Operator Connect | Y | Y | Y | See Note 10 |
| **Call recording** |  |  |  |  |
| Automatic recording for Call Queue | Y | Y | N | See Note 12 |
| Compliance recording for Call Queue | Y | Y | Y | See Note 13 |
| **Miscellaneous** |  |  |  |  |
| Call toast shows Resource Account Name | Y | Y | Y |  |
| Click-to-call | Y | Y | Y |  |
| Custom Context | Y | Y | Y |  |
| Dynamic caller ID | Y | Y | Y |  |
| [Location based routing](location-based-routing-plan#inbound-calls-through-auto-attendants) | N/A | N/A | N/A | Not supported |
| Monitor, Whisper, Barge, Takeover | Y | Y | Y | See Note 14 |
| Shared Call History | Y | Y | Y | See Note 14 |

#### Notes

- 1. Call answering is configured to use Users and groups. ↩
- 2. Call answering is configured to use a Team and channel (also known as *Voice enabled channels* or *Collaborative calling*). ↩
    - Agents using unsupported devices can still answer calls, but they don't have access to the collaborative calling user interface.
- 3. Call answering is configured to use a Schedule group in Shifts. ↩
- 4. Selecting *Longest Idle* for the agent routing method automatically enables Presence based routing. ↩
- 5. It's not possible to set the order the agents are presented with calls when using a group, teams schedule group, or teams channel for membership. ↩
- 6. Agents who are unavailable or opt out don't receive calls, even if they're scheduled to be on shift. ↩
- 7. Conference mode isn't supported if phone calls are routed to the queue from a Direct Routing gateway enabled for Location-Based Routing. ↩
    - Location based routing isn't supported with Call queues. For more information, see [Voice apps (Auto Attendant or Call Queue)](location-based-routing-plan#inbound-calls-through-auto-attendants).
- 8. Transfer mode is set to be deprecated in the second half of 2026, with the exact timeline confirmed at least three months in advance. ↩
- 9. Transferring calls between Public Switched Telephone Network (PSTN) connectivity methods (Calling Plan, Operator Connect, Direct Routing) isn't supported. ↩
- 10. Microsoft Teams Mobile App only. ↩
- 11. Call queues that are assigned as a Direct Routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents. The Teams client is only supported with a [coexistence mode of Teams Only](setting-your-coexistence-and-upgrade-settings). ↩
- 12. Automatic recording for Call Queue requires: ↩
    - Conference Mode is enabled
    - Call queue membership is configured via Microsoft 365 Security Groups
    - Teams admin center admins require SharePoint site admin to change authorized users once recording is configured
- 13. Compliance recording for call queues requires that Conference Mode is enabled. ↩
    - See [Compliance recording](teams-recording-policy).
- 14. Requires that Conference Mode is enabled. ↩
    - Agents and Authorized users require Queues App to see shared call history.
    - Authorized users require Queues App for Monitor, Whisper, Barge, Takeover functionality.

### Call Queue feature compatibility by device type

Expand to see table

| Feature | Teams Desktop^1^ | Teams Web | Teams Mobile App^2^ | Teams Phone Mobile^3^ | Skype for Business | IP Phones | Comment |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Agent Routing Methods** |  |  |  |  |  |  |  |
| Attendant Routing | Y | Y | Y | Y | Y | Y | *Default* |
| Longest Idle^4^ | Y | Y | Y | Y | N | Y | *Recommended* |
| Round Robin | Y | Y | Y | Y | Y | Y | *Recommended* |
| Serial | Y | Y | Y | Y | Y | Y | See Note 5 |
| **Agent Routing Options** |  |  |  |  |  |  |  |
| Presence Based Routing^4^ | Y | Y | Y | Y^6^ | N | Y | *Default* |
| Agents can opt out | Y | Y | Y | Y^6^ | Y^7^ | Y^7^ | *Default* |
| **Transfer Modes** |  |  |  |  |  |  |  |
| Conference Mode^8^ | Y | Y | Y | Y | Y | Y | *Default* |
| Transfer Mode | Y | Y | Y | Y | Y | Y | See Note 9 |
| **PSTN Connectivity Methods** |  |  |  |  |  |  | See Note 10 |
| Calling Plans | Y | Y | Y | Y | Y | Y |  |
| Direct Routing | Y | Y | Y | Y | N^11^ | Y |  |
| Operator Connect | Y | Y | Y | Y | N | Y |  |
| **Call recording** |  |  |  |  |  |  |  |
| Automatic recording for Call Queue | Y | Y | Y | Y | Y | Y | See Note 13 |
| Compliance recording for Call Queue | Y | Y | Y | N | N | Y | See Note 14 |
| **Miscellaneous** |  |  |  |  |  |  |  |
| Call toast shows Resource Account Name | Y | N | Y | N | Y |  |  |
| Channel Based Queues | Y | N | N | N | N | N | See Note 12 |
| Click-to-call | Y | N | N | N | N | N |  |
| Custom Context | Y | Y | Y | N | N | N |  |
| Dynamic caller ID | Y | Y | Y | N | N | N |  |
| [Location based routing](location-based-routing-plan#inbound-calls-through-auto-attendants) | N/A | N/A | N/A | N/A | N/A | N/A | Not supported |
| Monitor, Whisper, Barge, Takeover | Y | N | N | N | N | N | See Note 15 |
| Shared Call History | Y | N | N | N | N | N | See Note 15 |

#### Notes

- 1. Microsoft Teams Windows client, Microsoft Teams Mac Client, Microsoft Teams on Virtualized Desktop Infrastructure. ↩
- 2. Microsoft Teams iPhone app, Microsoft Teams Android app. ↩
- 3. Teams Phone Mobile Cellular Phone Dialer. ↩
- 4. Selecting *Longest Idle* for the agent routing method automatically enables Presence based routing. ↩
- 5. It's not possible to set the order the agents are presented with calls when using a group, teams schedule group, or teams channel for membership. ↩
- 6. Performed through Teams Phone Mobile app or see Note 7. ↩
- 7. Through the User Settings Portal page at: ↩
    - Public: https://aka.ms/vmsettings.
    - GCCH: https://dialin.cpc.gov.teams.microsoft.us/usp.
    - DOD: https://dialin.cpc.dod.teams.microsoft.us/usp.
- 8. Conference mode isn't supported if phone calls are routed to the queue from a Direct Routing gateway enabled for Location-Based Routing. ↩
    - Location based routing isn't supported with Call queues. For more information, see [Voice apps (Auto Attendant or Call Queue)](location-based-routing-plan#inbound-calls-through-auto-attendants) and [Capabilities not supported by Location-Based Routing](location-based-routing-plan#capabilities-not-supported-by-location-based-routing).
- 9. Transfer mode is set to be deprecated in the second half of 2026, with the exact timeline confirmed at least three months in advance. ↩
- 10. Transferring calls between Public Switched Telephone Network (PSTN) connectivity methods (Calling Plan, Operator Connect, Direct Routing) isn't supported. ↩
- 11. Call queues that are assigned as a Direct Routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents. The Teams client is only supported with a [coexistence mode of Teams Only](setting-your-coexistence-and-upgrade-settings). ↩
- 12. Agents using unsupported devices can still answer calls, however they don't have the collaborative calling user interface. ↩
- 13. Automatic recording for Call Queue requires: ↩
    - Conference Mode is enabled.
    - Call queue membership is configured via Microsoft 365 Security Groups
    - Teams admin center admins require SharePoint site admin to change authorized users once recording is configured
- 14. Requires that Conference Mode is enabled. ↩
    - See [Compliance recording](teams-recording-policy).
- 15. Requires that Conference Mode is enabled. ↩
    - Agents and Authorized users require Queues App to see shared call history.
    - Authorized users require Queues App for Monitor, Whisper, Barge, Takeover functionality.

### Call Queue supported clients

Expand to see table

The following clients are supported for representatives (agents) in a call queue:

- Skype for Business desktop client 2016 (32-bit and 64-bit versions)
- All IP phone models supported for Microsoft Teams.
- Mac Skype for Business Client (version 16.8.196 and later)
- Android Skype for Business Client (version 6.16.0.9 and later)
- iPhone Skype for Business Client (version 6.16.0 and later)
- iPad Skype for Business Client (version 6.16.0 and later)
- Microsoft Teams Windows client (32-bit and 64-bit versions)
- Microsoft Teams Mac client
- Microsoft Teams on [Virtualized Desktop Infrastructure](vdi-2) (Windows Virtual Desktop, Citrix, and VMware)
- Microsoft Teams iPhone app
- Microsoft Teams Android app

## Templates and resources

### Templates

- Number of templates: No limits.

#### Spam detection

- Phone numbers per inclusion/exclusion list: 20

#### Tags

- Tags per template: 15

### Tools

- Number of tools: No limits.

### Agents and queues

- Number of agents and queues: No limits.

## Audio file formats and maximum size

Important

You're responsible for independently clearing and securing all necessary rights and permissions to use any music or audio file with your Microsoft Teams service. These rights and permissions might include intellectual property and other rights in any music, sound effects, audio, brands, names, and other content in the audio file from all relevant rights holders, which might include artists, actors, performers, musicians, songwriters, composers, record labels, music publishers, unions, guilds, rights societies, collective management organizations, and any other parties who own, control, or license the music copyrights, sound effects, audio, and other intellectual property rights.

The supported formats are:

- WAV (uncompressed, linear PCM (Pulse-code modulation) with 8/16/32-bit depth in mono or stereo)
- WMA (mono only)^See Note 1^
- MP3

The audio file content can't be larger than 5 MB.

### Notes

- 1. WMA files will not be supported starting November 1, 2026. ↩
    - Existing WMA audio prompts will continue to work.

## Click-to-call restrictions

To help prevent a denial-of-service attack from web-based click-to-call applications, there's a maximum of 40 click-to-call calls per minute across all auto attendants and call queues in a tenant.

## Greeting message maximum characters

Each greeting message text can be up to 1,000 characters in length.

## Outbound calling line identification (number)

When a Teams Phone Agent, Auto Attendant, or Call Queue transfers to an external number, the system determines the outbound phone number as follows:

- For Calling Plan and Operator Connect numbers, the original caller's phone number is displayed.
- For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:
    - If set to **Disabled**, the original caller's phone number is displayed. Disabled is the default and recommended setting.
    - If set to **Enabled**, the resource account phone number is displayed.

In a Skype for Business hybrid environment, to transfer a call to the Public Switched Telephone Network (PSTN), create a new on-premises user with call forwarding set to the PSTN number. The user must be enabled for Enterprise Voice and have a voice policy assigned. To learn more, see [Auto attendant call transfer to PSTN](/en-us/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).