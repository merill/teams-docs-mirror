---
layout: Conceptual
title: Setup - Auto Attendant - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-auto-attendant
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
f1.keywords:
- CSH
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
audience: Admin
ms.localizationpriority: medium
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to set up auto attendants to direct my callers to the correct users, call queues, and departments.
description: Learn how to set up an auto attendant in Microsoft Teams using Quick or Advanced setup to route callers to the right people, call queues, and departments.
locale: en-us
document_id: a42f9e2c-aeee-76c4-620a-668cce21ba10
document_version_independent_id: 6ff06eab-9c80-9c30-95ef-c17e157fbea1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-auto-attendant.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-auto-attendant
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-auto-attendant.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ccb323ec-f511-c250-e46b-29053c24cb4d
---

# Setup - Auto Attendant - Microsoft Teams | Microsoft Learn

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

This article is for IT pros and Teams administrators who want to set up auto attendants.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Authorized users](aa-cq-plan-authorized-users)
- [Nesting call flows](aa-cq-plan-nesting)
- [Reporting considerations](aa-cq-plan-reporting)
- [Design call flows](aa-cq-design-call-flows)
- [Getting started](aa-cq-reference-getting-started)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

No known issues with the main auto attendant service.

Expand to see issues with individual features

### Authorized users

None.

### Shared call history

None.

## What's new in Auto Attendants (last six months)

- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) updated.

## Steps to create an auto attendant

To set up an auto attendant in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**.
2. Select **Auto attendants**.
3. Select **Add**.

### Setup options

**Quick setup** is for organizations with simpler call routing needs that might not require the full range of configurations offered by Advanced setup.

**Advanced setup** is for organizations with more complex routing requirements, or organizations looking to add functionality to auto attendants that were created through Quick setup.

**Teams Phone Agent** is for AI-driven call flows with self-service capabilities. See [Setup - Teams Phone Agent](aa-cq-setup-teams-phone-agent)

### Quick setup

Quick setup (expand to see instructions)

#### Step 1: General info for Auto attendant

1. Type a name for the auto attendant.
2. Select the time zone to determine the after hours schedule.
3. Select the language for system prompts and text-to-speech greetings.
4. Select how the auto attendant receives calls.

After setting the auto attendant's general info, select **Next**.

#### Step 2: Select call routing options

1. Choose a destination to redirect the call to, or the menu option to play to the caller.

Once you select your call routing options, select the **Submit** button at the bottom of the **Set up Auto attendant** wizard page.

### Advanced setup

Step 1 - General info (expand to see instructions)

#### Step 1: General info

##### Name

Type a name for the auto attendant in the box at the top.

##### Teams Phone Agent

See [Teams Phone Agent](aa-cq-setup-teams-phone-agent) if you want to set up a Teams Phone Agent.

##### How do callers reach this auto attendant

For details on how to create resource accounts and ready them for use with auto attendants, see [Manage Teams resource accounts](aa-cq-manage-resource-accounts).

###### Through a resource account

Select this option if this auto attendant needs to be called directly.

###### Through a voice app (no resource account needed)

Select this option if this auto attendant is [nested](aa-cq-plan-nesting) behind another Teams Phone Agent, Auto Attendant, or Call Queue that has answered the call.

##### Language

Specify a supported language for this auto attendant. This language is used for system-generated voice prompts.

Expand to see list of supported languages/locales

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

##### Voice inputs

Enable **Voice inputs** if you want menu options to become speech-recognition keywords.

For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."

If you choose a language that doesn't support voice inputs, this option isn't available.

##### Operator (optional)

Tip

Configuring an **Operator** is recommended.

Specify the destination for calls to the operator.

The auto attendant directs callers to the **Operator** when callers don't make any selection from the menu or when a call processing error occurs (for example, a call transfer to an invalid phone number). Setting the **Operator** also gives callers the option to break out of the menus and speak to a designated person.

Note

Make sure to also set up an **Operator** key on the menu options, otherwise the **Operator** feature isn't enabled.

After setting the **Operator**, select **Next**.

Step 2 - Call handling hours (expand to see instructions)

#### Step 2: Call handling hours

##### Time zone

Specify the time zone for this auto attendant.

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

##### Previous steps:

- Step 1 - General info

Step 3 - Business-hours call flow (expand to see instructions)

#### Step 3: Business-hours call flow

##### Greeting options

Select the greeting option that callers hear during business hours.

- **No greeting** - no greeting is played.
- **Play an audio file** - upload a prerecorded audio file.
- **Add a greeting message** - enter the text for the greeting.
- If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

If you select **Type a greeting message**, the system reads the text that you enter (up to 1,000 characters) in the language selected in step 1.

##### Call routing options

Select what happens to the call after the greeting is played.

- **Disconnect** - the call is disconnected.
- **Redirect call**- the call is redirected to one of the call routing destinations.
    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled. For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
    - **Voice app** - Choose the Auto Attendant or Call Queue when choosing this destination. The call priority can be set when the destination is a Call Queue.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
- **Play menu options** - the call is presented with a list of options to choose from.

###### Play menu options

###### Force listen

When **Force Listen** is on, callers will have to listen to the entire menu message before being able to enter their selection. Any caller input prior to the end of the menu is ignored. We recommend including information at the start of the menu message instructing callers to wait until the end to make their selection.

###### Set up the greeting and menu options

- **Play an audio file** - upload a prerecorded audio file.
- **Add a greeting message** - enter the text for the greeting.

If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio file. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

###### Set menu options

Assign keys 0-9, \* (asterisk), and # (pound) on the phone keypad to call routing destinations.

Key assignments don't need to be sequential. For example, you can map keys 0, 1, and 3, and leave key 2 unused.

If you set an operator in Step 1, map a key to it. If no key is mapped to the operator, the "Operator" voice command is also disabled.

For each menu option, specify the following settings:

- **Dial key** - the key on the telephone keypad to access this option. If voice inputs are available, callers can also say this number to access the option.
- **Voice command** - defines the voice command that a caller can give to access this option, if voice inputsare enabled. It can contain multiple words like "Customer Service" or "Operations and Grounds."
    - For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.
    - This **Voice command** text also plays in the service confirmation prompt, such as "Transferring your call to sales."
- **Destination**- the specific routing location for this option.
    - **Operator** - the operator defined for the Teams Phone Agent.
    - **Person in the organization** - a person in your organization who can receive voice calls.
    - **Tools** - access Questions and Answers andAppointments
    - **Agents & queues** - access Microsoft Copilot Studio (MCS) agents and third party IVRs
    - **Voice app** - Choose the Teams Phone Agent, Auto Attendant, or Call Queue when choosing this destination.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Announcement (Audio file)** - Play an audio file. The system plays the announcement, and then returns to the Auto attendant menu. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).
    - **Announcement (Typed)** - Type in a message. Text you want the system to read. You can enter up to 1,000 characters. The system plays the announcement, and then returns to the Auto attendant menu.

##### Directory search

If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**. Dial keys are matched before directory searches are performed. If a caller uses dial keys assigned to specific destinations, the system routes the call immediately. The caller is transferred before they finish entering the full name or extension. We recommend that you create a separate Auto attendant for directory search and have your main Auto attendant link to it with a dial key.

If you didn't assign dial keys, then choose an option for **Directory search**.

- **Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.
- **Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**. (You can set who is and isn't included in the directory on the [Dial scope](?tabs=dial-scope) page.)

Note

If you want to offer callers both the **Dial by name** and **Dial by extension** features, you can enable the **Dial by name** feature on the main Auto Attendant and then config an option to transfer to a second Auto Attendant where **Dial by extension** is enabled.

For more information, see the [Dial by name or number reference](aa-cq-reference-dial-by-name-number).

After setting the business-hours call flow options, select **Next**.

##### Previous steps:

- Step 1 - General info
- Step 2 - Call handling hours

Step 4 - After-hours call flow (expand to see instructions)

#### Step 4: After-hours call flow

##### Greeting options

Select the greeting option that callers hear during business hours.

- **No greeting** - no greeting is played.
- **Play an audio file** - upload a prerecorded audio file.
- **Add a greeting message** - enter the text for the greeting.
- If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

If you select **Type a greeting message**, the system reads the text that you enter (up to 1,000 characters) in the language selected in step 1.

##### Call routing options

Select what happens to the call after the greeting is played.

- **Disconnect** - the call is disconnected.
- **Redirect call**- the call is redirected to one of the call routing destinations.
    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled. For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
    - **Voice app** - Choose the Auto Attendant or Call Queue when choosing this destination. The call priority can be set when the destination is a Call Queue.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
- **Play menu options** - the call is presented with a list of options to choose from.

###### Play menu options

###### Force listen

When **Force Listen** is on, callers will have to listen to the entire menu message before being able to enter their selection. Any caller input prior to the end of the menu is ignored. We recommend including information at the start of the menu message instructing callers to wait until the end to make their selection.

###### Set up the greeting and menu options

- **Play an audio file** - upload a prerecorded audio file.
- **Add a greeting message** - enter the text for the greeting.

If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio file. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

###### Set menu options

Assign keys 0-9, \* (asterisk), and # (pound) on the phone keypad to call routing destinations.

Key assignments don't need to be sequential. For example, you can map keys 0, 1, and 3, and leave key 2 unused.

If you set an operator in Step 1, map a key to it. If no key is mapped to the operator, the "Operator" voice command is also disabled.

For each menu option, specify the following settings:

- **Dial key** - the key on the telephone keypad to access this option. If voice inputs are available, callers can also say this number to access the option.
- **Voice command** - defines the voice command that a caller can give to access this option, if voice inputsare enabled. It can contain multiple words like "Customer Service" or "Operations and Grounds."
    - For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.
    - This **Voice command** text also plays in the service confirmation prompt, such as "Transferring your call to sales."
- **Destination**- the specific routing location for this option.
    - **Operator** - the operator defined for the Teams Phone Agent.
    - **Person in the organization** - a person in your organization who can receive voice calls.
    - **Tools** - access Questions and Answers andAppointments
    - **Agents & queues** - access Microsoft Copilot Studio (MCS) agents and third party IVRs
    - **Voice app** - Choose the Teams Phone Agent, Auto Attendant, or Call Queue when choosing this destination.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Announcement (Audio file)** - Play an audio file. The system plays the announcement, and then returns to the Auto attendant menu. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).
    - **Announcement (Typed)** - Type in a message. Text you want the system to read. You can enter up to 1,000 characters. The system plays the announcement, and then returns to the Auto attendant menu.

##### Directory search

If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**. Dial keys are matched before directory searches are performed. If a caller uses dial keys assigned to specific destinations, the system routes the call immediately. The caller is transferred before they finish entering the full name or extension. We recommend that you create a separate Auto attendant for directory search and have your main Auto attendant link to it with a dial key.

If you didn't assign dial keys, then choose an option for **Directory search**.

- **Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.
- **Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**. (You can set who is and isn't included in the directory on the [Dial scope](?tabs=dial-scope) page.)

Note

If you want to offer callers both the **Dial by name** and **Dial by extension** features, you can enable the **Dial by name** feature on the main Auto Attendant and then config an option to transfer to a second Auto Attendant where **Dial by extension** is enabled.

For more information, see the [Dial by name or number reference](aa-cq-reference-dial-by-name-number).

After setting the after-hours call flow options, select **Next**.

##### Previous steps:

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

Select the greeting option that callers hear during business hours.

- **No greeting** - no greeting is played.
- **Play an audio file** - upload a prerecorded audio file.
- **Add a greeting message** - enter the text for the greeting.
- If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

If you select **Type a greeting message**, the system reads the text that you enter (up to 1,000 characters) in the language selected in step 1.

##### Call routing options

Select what happens to the call after the greeting is played.

- **Disconnect** - the call is disconnected.
- **Redirect call**- the call is redirected to one of the call routing destinations.
    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled. For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
    - **Voice app** - Choose the Auto Attendant or Call Queue when choosing this destination. The call priority can be set when the destination is a Call Queue.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
- **Play menu options** - the call is presented with a list of options to choose from.

###### Play menu options

###### Force listen

When **Force Listen** is on, callers will have to listen to the entire menu message before being able to enter their selection. Any caller input prior to the end of the menu is ignored. We recommend including information at the start of the menu message instructing callers to wait until the end to make their selection.

###### Set up the greeting and menu options

- **Play an audio file** - upload a prerecorded audio file.
- **Add a greeting message** - enter the text for the greeting.

If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio file. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

###### Set menu options

Assign keys 0-9, \* (asterisk), and # (pound) on the phone keypad to call routing destinations.

Key assignments don't need to be sequential. For example, you can map keys 0, 1, and 3, and leave key 2 unused.

If you set an operator in Step 1, map a key to it. If no key is mapped to the operator, the "Operator" voice command is also disabled.

For each menu option, specify the following settings:

- **Dial key** - the key on the telephone keypad to access this option. If voice inputs are available, callers can also say this number to access the option.
- **Voice command** - defines the voice command that a caller can give to access this option, if voice inputsare enabled. It can contain multiple words like "Customer Service" or "Operations and Grounds."
    - For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.
    - This **Voice command** text also plays in the service confirmation prompt, such as "Transferring your call to sales."
- **Destination**- the specific routing location for this option.
    - **Operator** - the operator defined for the Teams Phone Agent.
    - **Person in the organization** - a person in your organization who can receive voice calls.
    - **Tools** - access Questions and Answers andAppointments
    - **Agents & queues** - access Microsoft Copilot Studio (MCS) agents and third party IVRs
    - **Voice app** - Choose the Teams Phone Agent, Auto Attendant, or Call Queue when choosing this destination.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Announcement (Audio file)** - Play an audio file. The system plays the announcement, and then returns to the Auto attendant menu. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).
    - **Announcement (Typed)** - Type in a message. Text you want the system to read. You can enter up to 1,000 characters. The system plays the announcement, and then returns to the Auto attendant menu.

##### Directory search

If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**. Dial keys are matched before directory searches are performed. If a caller uses dial keys assigned to specific destinations, the system routes the call immediately. The caller is transferred before they finish entering the full name or extension. We recommend that you create a separate Auto attendant for directory search and have your main Auto attendant link to it with a dial key.

If you didn't assign dial keys, then choose an option for **Directory search**.

- **Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.
- **Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension. Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**. (You can set who is and isn't included in the directory on the [Dial scope](?tabs=dial-scope) page.)

Note

If you want to offer callers both the **Dial by name** and **Dial by extension** features, you can enable the **Dial by name** feature on the main Auto Attendant and then config an option to transfer to a second Auto Attendant where **Dial by extension** is enabled.

For more information, see the [Dial by name or number reference](aa-cq-reference-dial-by-name-number).

Repeat the procedure as needed to add more holidays.

After setting the holidays call flow options, select **Next**.

##### Previous steps:

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow

Step 6 - Dial scope (expand to see instructions)

#### Step 6: Dial scope (optional)

The **dial scope** defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension. The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.

You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups. For example, you might want to exclude executives in your organization from the dialing directory.

If a user is in both lists, or if they're hidden from the Exchange GAL, they're excluded from the directory.

Note

It might take up to 36 hours for a new user to have their name listed in the directory.

After setting the **Dial scope** options, select **Next**.

##### Previous steps:

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow
- Step 5 - Holidays call flow

Step 7 - Authorized users (expand to see instructions)

#### Step 7: Authorized users (optional)

**Authorized users** specifies the users who are authorized to make changes to this auto attendant. The capabilities that the users have are determined based on the [Teams voice applications policy](aa-cq-manage-voice-applications-policies) that is assigned to the user.

Select **Add**, search for the user, select **Add**, and then select **Add**.

Important

A user needs a voice applications policy that allows at least one type of configuration change and must be an authorized user for at least one auto attendant or call queue.

A user can't make any configuration changes if:

- The user has a policy assigned but isn't assigned as an authorized user to at least one auto attendant or call queue.
- The user is assigned as an authorized user to at least one auto attendant or call queue but doesn't have a policy assigned.

For more information, see [Set up authorized users](aa-cq-setup-authorized-users).

After setting the **Authorized users** option, select **Next**.

##### Previous steps:

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow
- Step 5 - Holidays call flow
- Step 6 - Dial scope

Step 8 - Review & submit (expand to see instructions)

#### Step 8: Review & submit

Review the configured flow in the **Call Flow** visualizer, and export a copy to PDF.

Select **Submit**.

##### Previous steps

- Step 1 - General info
- Step 2 - Call handling hours
- Step 3 - Business-hours call flow
- Step 4 - After-hours call flow
- Step 5 - Holidays call flow
- Step 6 - Dial scope
- Step 7 - Authorized users

## Extra functionality available through PowerShell cmdlets

Important

These configuration options are only available through PowerShell cmdlets and don't appear in the Teams admin center.

### Dial by name improvements

When a dial-by-name search returns multiple people with the same name, the results can now be enhanced by appending additional information after the name. Enhancing the results makes it easier for callers to reach the correct person.

The default is to only say the name. However, the office or department information can now be added as part of the results.

For more information, see [New-CsAutoAttendant -UserNameExtension](/en-us/powershell/module/teams/new-csautoattendant#-UserNameExtension).

## Related Auto Attendant setup and configuration articles

- [Holidays](aa-cq-setup-holidays)
- [Authorized users](aa-cq-setup-authorized-users)
- [Dial by name or number reference](aa-cq-reference-dial-by-name-number)
- [Answering Auto Attendant and Call Queue calls](aa-cq-reference-answer-calls)

## PowerShell

For instructions on creating auto attendants using PowerShell, see [Auto attendants with PowerShell](aa-cq-setup-auto-attendant-cmdlets).

## Auto attendant diagnostic tool

As an administrator, you can use the following diagnostic tool to validate that an auto attendant is able to receive calls:

1. Select **Run Tests**, which populates the diagnostic in the Microsoft 365 admin center.
2. In the Run diagnostic pane, enter the resource account in the **Username or Email** field, and then select **Run Tests**.

The tests identify tenant, policy, or resource account configurations that are preventing the auto attendant from receiving calls, and also provide steps to fix any problems identified.