---
layout: Conceptual
title: Setup - Teams Phone Agent - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-teams-phone-agent
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
ms.date: 2026-11-03T00:00:00.0000000Z
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
customer-intent: As a Teams Administrator, I want to set up Teams Phone Agents for my callers to interact with.
description: Learn how to create and configure a Teams Phone Agent in the Teams admin center, including call flows, dial scope, authorized users, and diagnostics.
locale: en-us
document_id: 0f5959a7-ff50-3aa2-ccfd-65b36331e5a1
document_version_independent_id: 0f5959a7-ff50-3aa2-ccfd-65b36331e5a1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-teams-phone-agent.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-teams-phone-agent
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-teams-phone-agent.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: 8caa4679-32d0-3854-093d-53efae67e1a2
---

# Setup - Teams Phone Agent - Microsoft Teams | Microsoft Learn

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

This article is for IT pros and Teams administrators who want to create Teams Phone Agents.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Questions and Answers](aa-cq-plan-teams-phone-agent-tools-questions-answers)
- [Appointment](aa-cq-plan-teams-phone-agent-tools-appointments)
- [Agents and queues](aa-cq-plan-teams-phone-agent-agents-queues)
- [Spam detection (Teams Phone Agent)](aa-cq-plan-teams-phone-agent-spam-detection)
- [Recording calls](aa-cq-plan-recording)
- [Templates and resources](aa-cq-plan-templates-resources)
- [Nested call flows](aa-cq-plan-nesting)
- [Reporting considerations](aa-cq-plan-reporting)
- [Design call flows](aa-cq-design-call-flows)
- [Getting started](aa-cq-reference-getting-started)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)

## Known issues

- Use **Resource account** based transfers when configuring transfers from:

    - Teams Phone Agent to Teams Phone Agent.
    - Auto Attendant to Teams Phone Agent.
    - Call Queue to Teams Phone Agent.

    **Voice app** based transfers are not supported in these transfer scenarios.
- Teams Phone Agent to Teams Phone Agent transfers where Automatic Recording for Teams Phone Agent is enabled may result in the greeting, AI disclaimer or recording prompts playing over each other.
- Assigning an Automatic Recording template to a Teams Phone Agent during creation fails.

    - Workaround: Save the Teams Phone Agent first, then edit it to add the Automatic Recording template.
- Teams Phone Agent is not supported for use in India.

Expand to see a list of issues with individual features

### Agents and queues

None.

### Appointments

None.

### Authorized Users

Not supported.

### Automatic recording

- Changes to the SharePoint site structure, file names, or permissions can cause access issues, permission errors, or automatic recording failures.
- To assign an automatic recording template to a Teams Phone Agent or manage its authorized users list, the Teams administrator must also be a SharePoint site administrator for the site used by the template. See [Teams Phone Agent management and SharePoint interaction](aa-cq-setup-teams-phone-agent-template-recording-automatic#teams-phone-agent-management-and-sharepoint-interaction) on how to avoid this issue.

### Questions and Answers

None.

### Shared call history

None.

### Spam

None.

## What's new in Teams Phone Agent (last six months)

- October 21, 2026
    - [Spam detection](aa-cq-setup-teams-phone-agent-template-spam-detection) can be configured in Teams admin center.
- October 19, 2026
    - [Copilot Credit Estimator](https://nptnlopcost-ppe-h8b6dtchacfcgqhk.b02.azurefd.net/#/estimator) now supports Teams Phone Agent.
- October 14, 2026
    - Teams Phone Agent now supports 42 voices, including 33 new ones.
- September 30, 2026
    - Teams Phone Agent is now generally available to all customers.
    - [Appointments integration with Microsoft Bookings](aa-cq-setup-teams-phone-agent-tools-appointments) can be configured in Teams admin center.
    - [Automatic Recording for Teams Phone Agent](aa-cq-setup-teams-phone-agent-template-recording-automatic) can be configured in Teams admin center.
    - [Maximum call length with configurable disconnect message](aa-cq-setup-teams-phone-agent#configurable-call-length) can be configured in Teams admin center.
    - Question and Answers URLs are refreshed daily.
- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent updated.
- September 1, 2026
    - Appointments integration with Microsoft Bookings can be configured via PowerShell.
- August 31, 2026
    - [AI disclaimer](aa-cq-setup-teams-phone-agent#ai-disclaimer-customization) can be configured in Teams admin center.
    - [Maximum call length](aa-cq-setup-teams-phone-agent#configurable-call-length) can be configured in Teams admin center.
- August 17, 2026
    - Automatic Recording for Teams Phone Agent can be configured via PowerShell.
- August 12, 2026
    - Spam detection can be configured via PowerShell.
    - AI disclaimer customization can be configured via PowerShell.
    - Maximum call length can be configured in PowerShell.
- July 20, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent is now available.
- June 15, 2026
    - Entered Frontier Public Preview

## Steps to create a Teams Phone Agent

To create a **Teams Phone Agent** in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**.
2. Select **Auto attendants**.
3. Select **Add**.
4. Select **Teams Phone Agent**.

### Teams Phone Agent setup

Note

The setup steps assume that all required **Questions and Answers** and **Appointment** tools, and any required Microsoft Copilot Studio associated **Agents and Queues**, have been created.

Step 1 - General info (expand to see instructions)

#### Step 1: General info

##### Name

Type a name for the Teams Phone Agent in the box at the top.

##### Teams Phone Agent

The **Teams Phone Agent** feature is enabled by default. Disabling Teams Phone Agent here returns to the standard [Auto Attendant](aa-cq-setup-auto-attendant) setup options.

##### How do callers reach this Teams Phone Agent

For details on how to create resource accounts and ready them for use with Teams Phone Agents, see [Manage Teams resource accounts](aa-cq-manage-resource-accounts).

###### Through a resource account

Select this option if this Teams Phone Agent needs to be called directly.

###### Through a voice app (no resource account needed)

This option is not currently available for Teams Phone Agent.

##### Language

Specify a supported language for this Teams Phone Agent. This is the default language that Teams Phone Agent uses for the disclaimer message, if the language spoken by the caller isn't recognized, or if Teams Phone Agent isn't able to speak in the same language as the caller.

Expand to see list of supported languages

| # | Locale | Language | Optimized Voice |
| --- | --- | --- | --- |
| 1. | ar-EG | Arabic (Egypt) |  |
| 1. | ar-EG | Arabic (Egypt) |  |
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
| 36 | id-ID | Indonesian (Indonesia) |  |
| 37 | is-IS | Icelandic (Iceland) |  |
| 38 | it-IT | Italian (Italy) | Isabella |
| 39 | ja-JP | Japanese (Japan) |  |
| 40 | kn-IN | Kannada (India) |  |
| 41 | ko-KR | Korean (Korea) |  |
| 42 | lt-LT | Lithuanian (Lithuania) |  |
| 43 | lv-LV | Latvian (Latvia) |  |
| 44 | mr-IN | Marathi (India) |  |
| 45 | nb-NO | Norwegian Bokmål (Norway) |  |
| 46 | fa-IR | Persian (Iran) |  |
| 47 | pl-PL | Polish (Poland) |  |
| 48 | pt-BR | Portuguese (Brazil) | Thalita |
| 49 | pt-PT | Portuguese (Portugal) |  |
| 50 | ro-RO | Romanian (Romania) |  |
| 51 | ru-RU | Russian (Russia) |  |
| 52 | sk-SK | Slovak (Slovakia) |  |
| 53 | sl-SI | Slovenian (Slovenia) |  |
| 54 | sr-RS | Serbian (Serbia) |  |
| 55 | es-ES | Spanish (Spain, International) | 🎵 [Ximena](https://res.cdn.office.net/s01-itpro-tac-ui/1.0.261025.2/5c0ab10bfbdf65f6.wav) |
| 56 | es-MX | Spanish (Mexico) |  |
| 57 | sv-SE | Swedish (Sweden) |  |
| 58 | ta-IN | Tamil (India) |  |
| 59 | th-TH | Thai (Thailand) |  |
| 60 | tr-TR | Turkish (Turkey) |  |
| 61 | uk-UA | Ukrainian (Ukraine) |  |
| 62 | ur-PK | Urdu (Pakistan) |  |
| 63 | vi-VN | Vietnamese (Vietnam) |  |

##### Voice

Specify the voice Teams Phone Agent should use. The voice sets the gender and tone that Teams Phone Agent speaks in.

Sample what the voice sounds like by selecting **Play**.

Use the [Voice Gallery](https://go.microsoft.com/fwlink/?LinkId=2387203) to sample those voices that don't have a **Play** option.

Note: Not all of the voices in the Voice Gallery are available in Teams Phone Agent.

Expand to see list of supported voices

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

##### Voice inputs

Voice inputs are automatically enabled when Teams Phone Agent is enabled, and they can't be turned off.

##### Operator (optional)

Tip

Configuring an **Operator** is recommended.

Specify the destination for calls to the operator.

The auto attendant directs callers to the **Operator** when callers don't make any selection from the menu or when a call processing error occurs (for example, a call transfer to an invalid phone number). Setting the **Operator** also gives callers the option to break out of the menus and speak to a designated person.

Note

Make sure to also set up an **Operator** key on the menu options; otherwise, the **Operator** feature isn't enabled.

After setting the **Operator**, select **Next**.

Step 2 - Call handling hours (expand to see instructions)

#### Step 2: Call handling hours

##### Time zone

Specify the time zone for this Teams Phone Agent.

The time zone is used for calculating business hours if you create a separate call flow for after hours.

##### Business and after hours

- If business hours aren't changed, the **Business-hours call flow** is followed from 9:00 AM to 5:00 PM (09:00-17:00), and the **After-hours call flow** is followed outside of these hours, every day of the week.
- Business hours can be set with multiple breaks in time during the day.
- Any time of day that isn't set as business hours is considered after-hours.
- You can set different incoming call-handling options and greetings for after-hours.

1. Next to the weekday in the table, adjust the **Start at** and **End at** times.
2. If needed, select **+** (add new time) to specify multiple sets of hours for a given day, for example, to specify a lunch break.

The routing options for **Business-hours call flow** and **After-hours call flow** are configured in the next two steps.

After setting the **Business and after hours** times, select **Next**.

##### Previous steps

- Step 1 - General info

Step 3 - Business-hours call flow (expand to see instructions)

#### Step 3: Business-hours call flow

##### Greeting options

Select the greeting option that callers will receive during business hours.

- **Default Teams Phone Agent Greeting**
    - `Hello, you've reached Teams Phone Agent. How can we help you today?`
- **Play an audio file** - this option is not supported with Teams Phone Agent.
- **Add a greeting message** - enter the text for the greeting.

The Teams Phone Agent greeting message can be entered in multiple languages. Teams Phone Agent will speak the greeting in each language to callers.

###### AI disclaimer customization

Caution

Microsoft Teams Phone Agent provides participant standard notifications as required by the law, including, but not limited to, recording, transcription, and interaction with AI. If you choose to disable these notifications, you are responsible to inform your participants in real time in accordance with applicable laws.

The default Teams Phone Agent disclaimer notification is:

`I'm a virtual assistant. How can I help you today?`

Accept the default message, customize it or disable it.

##### Call routing options

Select what happens to the call after the greeting is played.

- **Disconnect** - the call is disconnected. Teams Phone Agent is not engaged.
- **Redirect call**- the call is redirected to one of the call routing destinations. Teams Phone Agent is not engaged.
    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled. For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
    - **Voice app** - Choose the Auto Attendant or Call Queue when choosing this destination. The call priority can be set when the destination is a Call Queue.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
- **Play menu options** - the call is presented with a list of options to choose from. Teams Phone Agent is engaged.

###### Play menu options

###### Force listen

Teams Phone Agent doesn't support this option.

###### Set up the greeting and menu options

- **Play an audio file** - Teams Phone Agent doesn't support this option.
- **Add a greeting message** - Enter the greeting text.

Important

Teams Phone Agent uses this greeting only when it acts as an auto attendant. Enter text for the auto attendant routing options only. Don't mention **Tools** or **Agents & queues**, because those options aren't available in auto attendant mode.

See [Teams Phone Agent usage-based billing](aa-cq-setup-teams-phone-agent-ubb#teams-phone-agent-usage-based-billing)

###### Set menu options

Assign keys 0-9, \* (asterisk), and # (pound) on the phone keypad to call routing destinations.

Key assignments don't need to be sequential. For example, you can map keys 0, 1, and 3, and leave key 2 unused.

If you set an operator in Step 1, map a key to it. If no key is mapped to the operator, the "Operator" voice command is also disabled.

Tip

Assign the lower keys to the auto attendant routing options and the higher keys to **Tools** and **Agents & queues**. That way, callers hear a familiar auto attendant menu when Teams Phone Agent acts as an auto attendant.

For each menu option, specify the following settings:

- **Dial key** - the key on the telephone keypad to access this option. The caller can press or say this key number and Teams Phone Agent will route the call.
- **Voice command** - defines the voice command that a caller can give to access this option. It can contain multiple words like "Customer Service" or "Operations and Grounds."
- **Description** - use this field to give Teams Phone Agent detailed information on when to use this option. This should include keywords a caller may use when identifying actions they are looking to perform.
- **Destination**- the specific routing or resource for Teams Phone Agent to invoke.
    - **Operator** - the operator defined for the Teams Phone Agent.
    - **Person in the organization** - a person in your organization who can receive voice calls.
    - **Tools** - access Questions and Answers andAppointments.
    - **Agents & queues** - access Microsoft Copilot Studio (MCS) agents and third party IVRs.^See Note 1^
    - **Voice app** - Choose the Teams Phone Agent, Auto Attendant, or Call Queue when choosing this destination.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Announcement (Audio file)** - Teams Phone Agent doesn't support this option.
    - **Announcement (Typed)** - Teams Phone Agent doesn't support this option.

Notes:

1. To add a [Microsoft Foundry](https://go.microsoft.com/fwlink/?LinkId=2387204) agent: ↩

- Complete the [Voice enable Microsoft Foundry agents](aa-cq-direct-foundry) setup.
- Select **Resource account** as the destination and then select the resource account assigned to the Foundry agent.

###### Maximum call length

The default Teams Phone Agent call length is 4 minutes. When the configured time limit is reached, callers hear the disconnect message and then the call ends automatically.

###### Disconnect message

The default message is:

`I’m sorry the time limit of the call has been reached, and we will be disconnected in a moment, goodbye.`

Provide a **Custom message** if required.

###### Directory search

Choose an option for **Directory search**.

- **Dial by name** - If you enable this option, callers can say the user's name they want to speak with. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.
- **Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.

Note

If you want to offer callers both the **Dial by name** and **Dial by extension** features, you can enable the **Dial by name** feature on the main Teams Phone Agent and then config an option to transfer to a second Teams Phone Agent or Auto Attendant where **Dial by extension** is enabled.

For more information, see the [Dial by name or number reference](aa-cq-reference-dial-by-name-number).

After setting the business-hours call flow options, select **Next**.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours

Step 4 - After-hours call flow (expand to see instructions)

#### Step 4: After-hours call flow

##### Greeting options

Select the greeting option that callers will receive during business hours.

- **Default Teams Phone Agent Greeting**
    - `Hello, you've reached Teams Phone Agent. How can we help you today?`
- **Play an audio file** - this option is not supported with Teams Phone Agent.
- **Add a greeting message** - enter the text for the greeting.

The Teams Phone Agent greeting message can be entered in multiple languages. Teams Phone Agent will speak the greeting in each language to callers.

###### AI disclaimer customization

Caution

Microsoft Teams Phone Agent provides participant standard notifications as required by the law, including, but not limited to, recording, transcription, and interaction with AI. If you choose to disable these notifications, you are responsible to inform your participants in real time in accordance with applicable laws.

The default Teams Phone Agent disclaimer notification is:

`I'm a virtual assistant. How can I help you today?`

Accept the default message, customize it or disable it.

##### Call routing options

Select what happens to the call after the greeting is played.

- **Disconnect** - the call is disconnected. Teams Phone Agent is not engaged.
- **Redirect call**- the call is redirected to one of the call routing destinations. Teams Phone Agent is not engaged.
    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled. For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
    - **Voice app** - Choose the Auto Attendant or Call Queue when choosing this destination. The call priority can be set when the destination is a Call Queue.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
- **Play menu options** - the call is presented with a list of options to choose from. Teams Phone Agent is engaged.

###### Play menu options

###### Force listen

Teams Phone Agent doesn't support this option.

###### Set up the greeting and menu options

- **Play an audio file** - Teams Phone Agent doesn't support this option.
- **Add a greeting message** - Enter the greeting text.

Important

Teams Phone Agent uses this greeting only when it acts as an auto attendant. Enter text for the auto attendant routing options only. Don't mention **Tools** or **Agents & queues**, because those options aren't available in auto attendant mode.

See [Teams Phone Agent usage-based billing](aa-cq-setup-teams-phone-agent-ubb#teams-phone-agent-usage-based-billing)

###### Set menu options

Assign keys 0-9, \* (asterisk), and # (pound) on the phone keypad to call routing destinations.

Key assignments don't need to be sequential. For example, you can map keys 0, 1, and 3, and leave key 2 unused.

If you set an operator in Step 1, map a key to it. If no key is mapped to the operator, the "Operator" voice command is also disabled.

Tip

Assign the lower keys to the auto attendant routing options and the higher keys to **Tools** and **Agents & queues**. That way, callers hear a familiar auto attendant menu when Teams Phone Agent acts as an auto attendant.

For each menu option, specify the following settings:

- **Dial key** - the key on the telephone keypad to access this option. The caller can press or say this key number and Teams Phone Agent will route the call.
- **Voice command** - defines the voice command that a caller can give to access this option. It can contain multiple words like "Customer Service" or "Operations and Grounds."
- **Description** - use this field to give Teams Phone Agent detailed information on when to use this option. This should include keywords a caller may use when identifying actions they are looking to perform.
- **Destination**- the specific routing or resource for Teams Phone Agent to invoke.
    - **Operator** - the operator defined for the Teams Phone Agent.
    - **Person in the organization** - a person in your organization who can receive voice calls.
    - **Tools** - access Questions and Answers andAppointments.
    - **Agents & queues** - access Microsoft Copilot Studio (MCS) agents and third party IVRs.^See Note 1^
    - **Voice app** - Choose the Teams Phone Agent, Auto Attendant, or Call Queue when choosing this destination.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Announcement (Audio file)** - Teams Phone Agent doesn't support this option.
    - **Announcement (Typed)** - Teams Phone Agent doesn't support this option.

Notes:

1. To add a [Microsoft Foundry](https://go.microsoft.com/fwlink/?LinkId=2387204) agent: ↩

- Complete the [Voice enable Microsoft Foundry agents](aa-cq-direct-foundry) setup.
- Select **Resource account** as the destination and then select the resource account assigned to the Foundry agent.

###### Maximum call length

The default Teams Phone Agent call length is 4 minutes. When the configured time limit is reached, callers hear the disconnect message and then the call ends automatically.

###### Disconnect message

The default message is:

`I’m sorry the time limit of the call has been reached, and we will be disconnected in a moment, goodbye.`

Provide a **Custom message** if required.

###### Directory search

Choose an option for **Directory search**.

- **Dial by name** - If you enable this option, callers can say the user's name they want to speak with. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.
- **Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.

Note

If you want to offer callers both the **Dial by name** and **Dial by extension** features, you can enable the **Dial by name** feature on the main Teams Phone Agent and then config an option to transfer to a second Teams Phone Agent or Auto Attendant where **Dial by extension** is enabled.

For more information, see the [Dial by name or number reference](aa-cq-reference-dial-by-name-number).

After setting the after-hours call flow options, select **Next**.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow

Step 5 - Holidays call flow (expand to see instructions)

#### Step 5: Holidays call flow (optional)

The auto attendant can have a different call flow for each [holiday you configure](aa-cq-setup-holidays).

On the Holiday call settings page, select **Add**.

##### Name

Type a name for the holiday in the box at the top.

##### Holiday

From the **Holiday** dropdown, choose the holiday you want to use.

##### Greeting options

Select the greeting option that callers will receive during business hours.

- **Default Teams Phone Agent Greeting**
    - `Hello, you've reached Teams Phone Agent. How can we help you today?`
- **Play an audio file** - this option is not supported with Teams Phone Agent.
- **Add a greeting message** - enter the text for the greeting.

The Teams Phone Agent greeting message can be entered in multiple languages. Teams Phone Agent will speak the greeting in each language to callers.

###### AI disclaimer customization

Caution

Microsoft Teams Phone Agent provides participant standard notifications as required by the law, including, but not limited to, recording, transcription, and interaction with AI. If you choose to disable these notifications, you are responsible to inform your participants in real time in accordance with applicable laws.

The default Teams Phone Agent disclaimer notification is:

`I'm a virtual assistant. How can I help you today?`

Accept the default message, customize it or disable it.

##### Call routing options

Select what happens to the call after the greeting is played.

- **Disconnect** - the call is disconnected. Teams Phone Agent is not engaged.
- **Redirect call**- the call is redirected to one of the call routing destinations. Teams Phone Agent is not engaged.
    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled. For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
    - **Voice app** - Choose the Auto Attendant or Call Queue when choosing this destination. The call priority can be set when the destination is a Call Queue.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
- **Play menu options** - the call is presented with a list of options to choose from. Teams Phone Agent is engaged.

###### Play menu options

###### Force listen

Teams Phone Agent doesn't support this option.

###### Set up the greeting and menu options

- **Play an audio file** - Teams Phone Agent doesn't support this option.
- **Add a greeting message** - Enter the greeting text.

Important

Teams Phone Agent uses this greeting only when it acts as an auto attendant. Enter text for the auto attendant routing options only. Don't mention **Tools** or **Agents & queues**, because those options aren't available in auto attendant mode.

See [Teams Phone Agent usage-based billing](aa-cq-setup-teams-phone-agent-ubb#teams-phone-agent-usage-based-billing)

###### Set menu options

Assign keys 0-9, \* (asterisk), and # (pound) on the phone keypad to call routing destinations.

Key assignments don't need to be sequential. For example, you can map keys 0, 1, and 3, and leave key 2 unused.

If you set an operator in Step 1, map a key to it. If no key is mapped to the operator, the "Operator" voice command is also disabled.

Tip

Assign the lower keys to the auto attendant routing options and the higher keys to **Tools** and **Agents & queues**. That way, callers hear a familiar auto attendant menu when Teams Phone Agent acts as an auto attendant.

For each menu option, specify the following settings:

- **Dial key** - the key on the telephone keypad to access this option. The caller can press or say this key number and Teams Phone Agent will route the call.
- **Voice command** - defines the voice command that a caller can give to access this option. It can contain multiple words like "Customer Service" or "Operations and Grounds."
- **Description** - use this field to give Teams Phone Agent detailed information on when to use this option. This should include keywords a caller may use when identifying actions they are looking to perform.
- **Destination**- the specific routing or resource for Teams Phone Agent to invoke.
    - **Operator** - the operator defined for the Teams Phone Agent.
    - **Person in the organization** - a person in your organization who can receive voice calls.
    - **Tools** - access Questions and Answers andAppointments.
    - **Agents & queues** - access Microsoft Copilot Studio (MCS) agents and third party IVRs.^See Note 1^
    - **Voice app** - Choose the Teams Phone Agent, Auto Attendant, or Call Queue when choosing this destination.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Announcement (Audio file)** - Teams Phone Agent doesn't support this option.
    - **Announcement (Typed)** - Teams Phone Agent doesn't support this option.

Notes:

1. To add a [Microsoft Foundry](https://go.microsoft.com/fwlink/?LinkId=2387204) agent: ↩

- Complete the [Voice enable Microsoft Foundry agents](aa-cq-direct-foundry) setup.
- Select **Resource account** as the destination and then select the resource account assigned to the Foundry agent.

###### Maximum call length

The default Teams Phone Agent call length is 4 minutes. When the configured time limit is reached, callers hear the disconnect message and then the call ends automatically.

###### Disconnect message

The default message is:

`I’m sorry the time limit of the call has been reached, and we will be disconnected in a moment, goodbye.`

Provide a **Custom message** if required.

Repeat the procedure as needed for more holidays.

###### Directory search

Choose an option for **Directory search**.

- **Dial by name** - If you enable this option, callers can say the user's name they want to speak with. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.
- **Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.

Note

If you want to offer callers both the **Dial by name** and **Dial by extension** features, you can enable the **Dial by name** feature on the main Teams Phone Agent and then config an option to transfer to a second Teams Phone Agent or Auto Attendant where **Dial by extension** is enabled.

For more information, see the [Dial by name or number reference](aa-cq-reference-dial-by-name-number).

After setting the holidays call flow options, select **Next**.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow

Step 6 - Templates (expand to see instructions)

#### Step 6: Templates (optional)

##### Set the Automatic Recording template for Teams Phone Agent (optional)

Select an existing template from the drop-down or Create a new template.

To create an Automatic Recording template for Teams Phone Agent, see [Automatic Recording for Teams Phone Agent](aa-cq-setup-teams-phone-agent-template-recording-automatic).

##### Set the Spam Detection template for Teams Phone Agent (optional)

Select an existing template from the drop-down or Create a new template.

To create a Spam Detection template for Teams Phone Agent, see [Spam Detection for Teams Phone Agent](aa-cq-setup-teams-phone-agent-template-spam-detection).

Once you select the optional templates, select Next button at the bottom of the Add a Call queue page.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow
- Step 5 - Holidays call flow

Step 7 - Dial scope (expand to see instructions)

#### Step 7: Dial scope (optional)

The **dial scope** defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension. The default of **All online users** includes all users in your organization that are online users or hosted on-premises using Skype for Business Server.

You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups. For example, you might want to exclude executives in your organization from the dialing directory.

If a user is in both lists, or if they're hidden from the Exchange GAL, they're excluded from the directory.

Note

It might take up to 36 hours for a new user to have their name listed in the directory.

After setting the **Dial scope** options, select **Next**.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow
- Step 5 - Holidays call flow
- Step 6 - Templates

Step 8 - Authorized users (expand to see instructions)

#### Step 8: Authorized users (optional)

**Authorized users** specifies the users who can make changes to this Teams Phone Agent. The capabilities that the users have are determined by the [Teams voice applications policy](aa-cq-manage-voice-applications-policies) that is assigned to the user.

Select **Add**, search for the user, select the user, and then select **Add**.

Important

A user needs a voice applications policy that allows at least one type of configuration change, and must be an authorized user for at least one Teams Phone Agent, auto attendant or call queue.

A user can't make any configuration changes if:

- The user has a policy assigned but isn't assigned as an authorized user to at least one auto attendant or call queue.
- The user is assigned as an authorized user to at least one auto attendant or call queue but doesn't have a policy assigned.

For more information, see [Set up authorized users](aa-cq-setup-authorized-users).

After setting the **Authorized users** option, select **Next**.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow
- Step 5 - Holidays call flow
- Step 6 - Templates
- Step 7 - Dial scope

Step 9 - Review & submit (expand to see instructions)

#### Step 9: Review & submit

Review the configured flow in the **Call Flow** visualizer, and export a copy to PDF.

Select **Submit**.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow
- Step 5 - Holidays call flow
- Step 6 - Templates
- Step 7 - Dial scope
- Step 8 - Authorized users

Important

Teams Phone Agent is delivered through usage-based billing with Copilot Credits.

You must [Setup - Usage Based Billing](aa-cq-setup-teams-phone-agent-ubb) in order for Teams Phone Agent to work. If the required spending policies are not configured, or if there are insufficient Copilot Credits, then Teams Phone Agent works as an Auto Attendant until there are available credits.

## Extra functionality available through PowerShell cmdlets

Important

These configuration options are currently only available through PowerShell cmdlets and don't appear in the Teams admin center.

### Dial by name improvements

When a dial-by-name search returns multiple people with the same name, the results can now be enhanced by appending additional information after the name. This makes it easier for callers to reach the correct person.

The default is to say only the name. However, the office or department information can now be added as part of the results.

For more information, see [New-CsAutoAttendant -UserNameExtension](/en-us/powershell/module/teams/new-csautoattendant#-usernameextension).

## Related Teams Phone Agent setup and configuration articles

- [Questions and Answers](aa-cq-setup-teams-phone-agent-tools-questions-answers)
- [Appointment](aa-cq-setup-teams-phone-agent-tools-appointments)
- [Agents and Queues](aa-cq-setup-teams-phone-agent-agents-queues)
- [Holidays](aa-cq-setup-holidays)

## PowerShell

For instructions on creating Teams Phone Agents using PowerShell, see [Set up Teams Phone Agent with PowerShell](aa-cq-setup-teams-phone-agent-cmdlets).

## Teams Phone Agent / Auto Attendant diagnostic tool

As an administrator, you can use the following diagnostic tool to validate that an auto attendant is able to receive calls:

1. Select **Run Tests**, which populates the diagnostic in the Microsoft 365 admin center.
2. In the Run diagnostic pane, enter the resource account in the **Username or Email** field, and then select **Run Tests**.

The tests identify tenant, policy, or resource account configurations that are preventing the auto attendant from receiving calls, and provide steps to fix any problems identified.