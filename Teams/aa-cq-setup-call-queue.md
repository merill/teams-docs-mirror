---
layout: Conceptual
title: Setup - Call Queue - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-call-queue
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
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to create and manage call queues.
description: Learn how to set up call queues in Microsoft Teams. Call queues provide a greeting message, hold music, call redirecting, and other features.
locale: en-us
document_id: b755d9ae-13ac-019f-f5f4-a95b1eee2989
document_version_independent_id: f7afd8ad-e6e0-6c79-aed1-4ee87d48ba12
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-call-queue.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-call-queue
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-call-queue.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: afbce417-2a89-b490-fe1f-f63e7b3eebc2
---

# Setup - Call Queue - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to create call queues.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Authorized users](aa-cq-plan-authorized-users)
- [Shared call history](aa-cq-plan-shared-call-history)
- [Call priorities for call queues](aa-cq-plan-call-queue-priorities)
- [Recording calls](aa-cq-plan-recording)
- [Templates and resources](aa-cq-plan-templates-resources)
- [Nesting call flows](aa-cq-plan-nesting)
- [Reporting considerations](aa-cq-plan-reporting)
- [Design call flows](aa-cq-design-call-flows)
- [Getting started](aa-cq-reference-getting-started)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

No known issues with the main call queue service.

Expand to see issues with individual features

### Authorized users

None.

### Automatic recording

- Changes to the SharePoint site structure, file names, or permissions can cause access issues, permission errors, or automatic recording failures.
- To assign an automatic recording template to a call queue or manage its authorized users list, the Teams administrator must also be a SharePoint site administrator for the site used by the template. See [Call queue management and SharePoint interaction](aa-cq-setup-call-queue-template-recording-automatic#call-queue-management-and-sharepoint-interaction) on how to avoid this issue.
- [Explicit recording consent](participant-agreement-recording-transcription) must be **Off**.

### Call priorities

None.

### Compliance recording

None.

### Shared call history

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

## Steps to create a call queue

To set up a call queue in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**
2. Select **Call queues**
3. Select **Add**.

### Setup options

**Quick setup** is for organizations with simpler call routing needs that might not require the full range of configurations offered by Advanced setup.

**Advanced setup** is for organizations with more complex routing requirements, or organizations looking to add functionality to call queues that were created through Quick setup.

### Quick setup

Quick setup (expand to see instructions)

#### Step 1: General info for Call queue

1. Type a name for the call queue and select the language for system prompts and text-to-speech greetings.
2. Select how the call queue receives calls.

After setting your call queue's general info, select **Next**.

#### Step 2: Select who can answer the incoming calls

1. Select the team and channel, or the users and groups to answer the incoming calls.

    Review the [prerequisites for call queue representatives (agents)](aa-cq-reference-prerequisites-licensing#call-queue-representatives).

Once you select who can answer the incoming calls, select the **Submit** button at the bottom of the **Set up Call Queue** wizard page.

### Advanced setup

Step 1 - General info (expand to see instructions)

#### Step 1: General info

##### Name

Type a name for the call queue in the box at the top.

##### Set the Call queue language

Specify a supported language for this call queue. This language is used for the text-to-speech and system-generated voice prompts.

Supported languages/locales (expand to see list)

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

##### Add an existing resource account

For details on how to create resource accounts and ready them for use with auto attendants or call queues, see [Manage Teams resource accounts](aa-cq-manage-resource-accounts).

All call queues that directly answer calls must have an associated resource account. All resource accounts must be assigned a [Microsoft Teams Phone Resource Account license](teams-add-on-licensing/virtual-user). Multiple resource accounts can be assigned to a call queue.

Nested auto attendants and call queues that receive calls from an auto attendant or call queue that already answered the call don't require a resource account. For more information, see [Nested auto attendants and call queues](aa-cq-plan-nesting).

Representatives see the resource account name or call queue name when they receive an incoming call.

##### Assign a calling ID (optional)

Assign outbound caller ID numbers for the representatives by specifying one or more resource accounts with a phone number. Representatives can select which outbound caller ID number to use with each outbound call they make. Within the Calls app, representatives can use their Call Queue (CQ) / Auto Attendant (AA) number or their own personal Direct Inward Dial (DID).

For details on how to create resource accounts and ready them for use with auto attendants or call queues, see [Manage Teams resource accounts](aa-cq-manage-resource-accounts).

Note

The resource account used for calling ID purposes must have a **Microsoft Teams Phone Resource Account** license and one of the following assigned:

- A Calling Plan license and a phone number assigned
- An Operator Connect phone number assigned
- An online voice routing policy (phone number assignment is optional when using Direct Routing)

1. Under **Assign calling ID**, select the **Add** button.
2. On the **Add accounts** pane, search for one or more resource accounts you want to allow agents to use for outbound caller ID purposes.
3. Select the **Add** button next to the resource account with an assigned phone number.
4. Select the **Add** button at the bottom of the pane.

##### Set the Service level threshold (optional)

Service level measures the efficiency and responsiveness to incoming customer requests within a specific Service level threshold.

You can set the threshold target to any value from 0 to 40 minutes (2,400 seconds). The value should be less than the value set for Call timeout; however, this value difference isn't enforced. Setting the threshold value higher than the call timeout results in the service level always being 100% if there are answered calls or 0% if there are no answered calls. Setting the value to blank (empty) disables the service level metric calculation for the call queue.

Note

Service level metrics aren't currently available in historical reporting.

Changing the service level threshold during business hours causes inaccurate service level calculations for the whole day because previous calls aren't reassessed with the new target.

After you set the service level threshold, select the **Next** button at the bottom of the **Add a Call queue** page.

Step 2 - Greeting and music (expand to see instructions)

#### Step 2: Greeting and music

##### Greeting

Specify if you want to play a *greeting* to callers when they arrive in the queue.

- If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).
- If you select **Type a greeting message**, the system reads the text that you type (up to 1,000 characters) when the call queue answers a call.

Note

*Text-to-speech* text must be entered in your selected language as the system doesn't perform translation.

All words are pronounced in the selected language.

##### Music on hold

Teams provides default music to callers while they're *on hold in a queue*.

- The default music supplied in Teams call queues is free of any royalties payable by your organization.
- If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

Important

You're responsible for independently clearing and securing all necessary rights and permissions to use any music or audio file with your Microsoft Teams service. These rights and permissions might include intellectual property and other rights in any music, sound effects, audio, brands, names, and other content in the audio file from all relevant rights holders, which might include artists, actors, performers, musicians, songwriters, composers, record labels, music publishers, unions, guilds, rights societies, collective management organizations, and any other parties who own, control, or license the music copyrights, sound effects, audio, and other intellectual property rights.

After you select a greeting and on-hold music, select the **Next** button at the bottom of the **Add a Call queue** page.

##### Previous steps:

- Step 1 - General info

Step 3 - Call answering (expand to see instructions)

#### Step 3: Call answering

Review the [prerequisites for adding representatives to a call queue](aa-cq-reference-prerequisites-licensing#call-queue-representatives).

##### Teams channel

You can add up to 200 representatives via a Teams channel.

[Using a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e):

1. Select the **Choose a team** radio button and select **Add a channel**.
2. Search for the team that you want to use, select it, and select **Add**.
3. Select the channel that you want to use (only standard channels are fully supported) and select **Apply**.

The following clients are supported when using a Teams channel for call queues:

- Microsoft Teams Windows client
- Microsoft Teams Mac client

Note

If you use this option, it can take up to 24 hours for the call queue to be fully operational.

Only standard channels are fully supported.

Known issues:

- Assigning private channels to call queues
    - When using a private channel, calls are distributed to all members of the team even if the private channel only has a subset of team members.
    - Assigning a private channel to a call queue might fail, even if the call queue previously had a private channel assigned or if the private channel was previously assigned to a call queue.

##### Users and groups

You can add up to 20 representatives individually and up to 200 representatives via groups.

If you want to add individual users or groups to the queue:

1. Select the **Choose users and groups** radio button.

To **add a user** to the queue:

1. Select **Add users**, search for the user, select **Add**, and then select **Add**.

To **add a group** to the queue:

1. Select **Add groups**, search for the group, select **Add**, and then select **Add**.

    - You can use distribution lists, security groups, and Microsoft 365 Groups or Microsoft Teams teams.

Note

New users added to a group can take up to eight hours for their first call to arrive.

##### Shifts

If you want to use a Shift as your call queue group:

1. Make sure to set up a Shift in the Shifts app by following the steps in [Get started in Shifts](https://support.microsoft.com/office/5f3e30d8-1821-4904-be26-c3cd25a497d6).
2. Select the **Choose a shift** radio button.

To **add a Shift** to the queue:

1. Select **Add a Shift**, search for the team and choose it.
2. Select the scheduling group you want.
3. Select **Apply**.
4. Select **Submit**.

Note

Only representatives who are on shift, opted in, and are available (if *Presence-based* routing applies) receive calls.

- Representatives who are on shift, opted in, but aren't available (if *Presence-based* routing applies) don't receive calls.
- Representatives who are on shift but opted out don't receive calls.
- Representatives who aren't on shift don't receive calls.

Shift adjustments take 15 minutes to sync with the call queue.

- Representatives currently on shift still receive calls up to 15 minutes after they were removed from being on shift.
- Representatives added to a shift for the current time period only start to receive calls 15 minutes after they were added.

Shift activities, custom tags, notes, and colors are ignored.

If there are more than 200 members in the Shift, only the first 200 EV-enabled members, in alphabetical order, are added as representatives to the call queue.

Important

Only a global or teams administrator role can fully manage a call queue with a Teams channel or Teams schedule group (Shifts) assigned. For other roles, you must be the creator or owner of the channel or a member of the team to add a channel or schedule group to the queue.

If there are more than 200 members in the team, group, or shift, only the first 200 enterprise voice enabled members, in alphabetical order, are added as representatives to the call queue.

##### Conference mode

**Conference mode** reduces the amount of time it takes for a caller to be connected to a representative after they accept the call.

Representatives' Teams accounts must be set to TeamsOnly mode. Representatives who don't meet the requirements aren't included in the call routing list.

Tip

Setting **Conference mode** to **On** is the recommended setting.

Once you select your call answering options, select the **Next** button at the bottom of the **Add a Call queue** page.

Keep the following conditions in mind:

- Conference mode isn't supported for calls routed to the queue from a Direct Routing gateway enabled for Location-Based Routing.
- Conference mode is required if Teams users need to consult/transfer calls with call queues.
- Representatives can hear the configured music on hold in queue for up to two seconds when first joining the call.

Important

Transfer mode (when conference mode is disabled) is now in legacy mode. A Message center post will be made at least three months before the scheduled removal date.

##### Previous steps:

- Step 1 - General info
- Step 2 - Greeting and music

Step 4 - Agent selection (expand to see instructions)

#### Step 4: Agent selection

Important

Call presentation to representatives might conflict with Location-Based Routing restrictions. In this case, the representative receives a call toast but can't answer the call. This continues until a representative answers, the caller hangs up, or the call queue times out. For more information on Location-Based Routing, see [Plan Location-Based Routing for Direct Routing](location-based-routing-plan).

**Routing method** determines the order in which representatives receive calls from the queue.

Choose from these options:

- **Attendant routing** rings all representatives in the queue at the same time. The first representative to pick up the call gets the call.
- **Serial routing** rings all call representatives one by one in the order specified in the **Call agents** list. If a representative dismisses or doesn't pick up a call, the call rings the next representative. This cycle repeats until the call is answered, times out, or the caller hangs up.
- **Round robin** balances the routing of incoming calls so that each call representative gets the same number of calls from the queue.
- **Longest idle** routes calls to the representative who is idle the longest. A representative is considered idle if their presence state is *Available*. Representatives who aren't available don't receive calls until they change their presence to *Available*.

Tip

Setting the **Routing method** to **Round robin** or **Longest idle** is the recommended setting.

##### Presence-based call routing

**Presence-based call routing** uses the availability status of call representatives to determine whether a representative should be included in the call routing list for the selected routing method.

Representatives whose availability status is set to **Available** are included in the call routing list and can receive calls. Representatives whose availability status is set to any other status are excluded from the call routing list and can't receive calls until their availability status changes back to **Available**.

You can enable **presence-based call routing** with any of the routing methods.

If an representative opts out of getting calls, they can't receive calls regardless of their availability status.

Tip

Setting the **Presence-based routing** to **On** is the recommended setting.

Note

When **Longest idle** is selected as the routing method:

- Presence-based routing is required and automatically enabled even though the Presence-based routing toggle is **Off** and grayed out.
- When there are fewer calls in the queue than available representatives, only the first two longest idle representatives are presented with calls from the queue.

If **Presence-based routing** isn't enabled and there are multiple calls in the queue, the system presents these calls simultaneously to the representatives, regardless of their presence status. This action results in multiple call notifications to representatives, particularly if some representatives don't answer the initial call presented to them. For more information, see [Configure Busy Options](inbound-call-routing) for Busy on Busy alternatives to presence-based routing.

There might be times when a representative receives a call from the queue shortly after becoming unavailable or a short delay in receiving a call from the queue after becoming available when using **Presence-based routing**.

Representatives who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled. If you have representatives who use Skype for Business, don't enable presence-based call routing.

##### Call agents can opt out of taking calls

You can specify whether representatives have the ability to opt out of taking calls or not.

We recommend turning on **Call agents can opt out of taking calls**.

##### Agent alert time

**Agent alert time** specifies how long a representative's phone rings before the queue redirects the call to the next representative.

Tip

Setting the **Agent alert time** to a minimum **20 seconds** is the recommended setting.

Once you select your representative call routing options, select the **Next** button at the bottom of the **Add a Call queue** page.

##### Previous steps:

- Step 1 - General info
- Step 2 - Greeting and music
- Step 3 - Call answering

Step 5 - Callback (expand to see instructions)

#### Step 5: Callback

##### Enable callback

Enable callback in order to configure when callers will be able to request a callback.

Configuration is maintained when callback is turned off.

##### Eligibility conditions for callback

**Callback** allows *eligible* callers waiting in a call queue to receive a callback to the number they're calling from when a representative becomes available.

A caller becomes *eligible* for callback based on any one of the following configured conditions coming true:

- **Wait time in queue**: Once a caller in queue exceeds this configured wait time, they become eligible for callback. This option applies to callers at the front of the queue.
- **Number of calls in queue**: Once the number of callers in queue reaches this level, new callers arriving in the queue become eligible for callback. This option applies to callers arriving in the queue. Callers that arrived in the queue before this limit was reached aren't eligible for callback.
- **Calls to agent ratio**: Once the number of callers waiting in queue exceeds the ratio, new callers arriving in the queue become eligible for callback. This option applies to callers arriving in the queue.

Additionally, for a caller to become *eligible* for callback, their inbound phone number must be a publicly dialable, nonpremium phone number in E.164 format, and the call must not be presenting to a representative.

**After the music on hold finishes playing**, *eligible* callers receive an option to request callback.

##### Greeting

Set the messaging an caller hears when they become *eligible* for callback. Make sure to include instructions on which key to press.

##### Key to press

Select the key that *eligible* callers must press in order to request the callback. This information shoudl be included in the Greeting.

##### When callback could not be completed

Like regular calls, callbacks can timeout if no agent becomes available. When this happens, an email is sent to the configured group. The email includes all the information required for someone to manually call the caller back.

##### Callback and call queue timeouts

Important

For a callback to work, the Call timeout value must be set high enough to allow:

- The caller to become eligible.
- The music to finish playing.
- The caller to request a callback.
- The callback to wait until a representative is available.
- For the representative to answer the callback.

Consider the following call queue configuration:

- Callback wait time in queue: 60 seconds
- Call queue timeout: 120 seconds
- Call queue music: Default

After a caller waits in the queue for 60 seconds, they become *eligible* for callback. However, since the default music is two minutes long, the call queue timeout occurs first, and callback isn't offered.

**Once a caller successfully requests a callback, the callback request is also subject to the call queue timeout configuration.** If a callback request times out, the information about the caller is sent to the configured email notification address.

Note

For callers in North America, in addition to the other listed requirements, the inbound phone number must not start with:

| Starting Digits |
| --- |
| 1-242, 246, 264, 268, 284 |
| 1-340, 345 |
| 1-441, 473 |
| 1-500 |
| 1-600, 649, 658, 664, 670, 671, 684 |
| 1-700, 721, 758, 767, 784, 787 |
| 1-800, 811, 822, 833, 844, 855, 866, 877, 888 |
| 1-809, 829, 849, 868, 869, 876 |
| 1-900, 939 |
| 1-nnn-555-1212 |
| 1-nnn-555,0100-0199 |

Once you select your callback options, select the **Next** button at the bottom of the **Add a Call queue** page.

##### Previous steps:

- Step 1 - General info
- Step 2 - Greeting and music
- Step 3 - Call answering
- Step 4 - Agent selection

Step 6 - Exception handling (expand to see instructions)

#### Step 6: Exception handling

**Exception handling** determines how calls are handled when certain exceptions occur.

Each exception allows you to **disconnect** the call or **redirect** it to any of the call routing destinations.

For example, when **Overflow** occurs, you might send calls to a backup call queue, but when **Timeout** or **No Agents** occurs, you might want the callers to leave a shared voicemail.

Note

For external transfers, see [Outbound calls from Teams Phone Agent, Auto Attendant, or Call Queue](aa-cq-reference-prerequisites-licensing#outbound-calls-from-teams-phone-agent-auto-attendant-or-call-queue).

##### Overflow: Set how to handle call overflow

###### Maximum calls in the queue

This limit specifies the maximum number of calls that can wait in the queue at any give time.

The default is 50, but it can range from 0 to 200

Note

If the maximum number of calls is set to 0, the greeting message can't play.

###### When the maximum number of calls is reached

You can specify how a call is handled when the **Maximum calls in queue** limit is reached.

- **Disconnect** - the call will be disconnected.

    - You can configure a message to play before the call is disconnected.
        - **None** - no message will play.
        - **Play an audio file** - upload a prerecorded audio file.
        - **Add a greeting message** - enter the text for the greeting.
- **Redirect call** - the call is redirected to one of the following call routing destinations:

    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled.
            - For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
        - See Additional messaging to configure a message through PowerShell that will play before the transfer is completed.
    - **Voice app**- choose the Auto Attendant or Call Queue to transfer to.
        - See [Nested auto attendants and call queues](aa-cq-plan-nesting).
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **Resource account**- choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **External phone number**- any phone number.
        - See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **Voicemail (personal)**- a person in your organization who can receive voice calls. The call will go directly to their voicemail.
        - See Additional messaging to configure a message through PowerShell that will play before the transfer is completed.
    - **Voicemail (shared)**- The voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable Let people outside the organization email this team for the Microsoft 365 group that you specify.
        - Additional options:
            - **Transcription** - turn on transcription for voicemails left by a caller.
            - **Skip voicemail system message** - turns off the default voicemail system prompts.
        - A greeting must be configured.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message**- enter the text for the greeting.
                - Don't include any special characters in the greeting message when redirecting to **Voicemail (shared)** as these aren't spoken by the system.

    If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

##### Call timeout: Set how to handle call timeouts

###### Maximum wait time

This limit specifies the maximum time a call can be on hold in the queue.

You can specify a value from 0 seconds to 45 minutes.

###### When calls times out

You can specify how a call is handled when the **Maximum wait time** limit is reached.

- **Disconnect** - the call will be disconnected.

    - You can configure a message to play before the call is disconnected.
        - **None** - no message will play.
        - **Play an audio file** - upload a prerecorded audio file.
        - **Add a greeting message** - enter the text for the greeting.
- **Redirect call** - the call is redirected to one of the following call routing destinations:

    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled.
            - For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
        - See Additional messaging to configure a message through PowerShell that will play before the transfer is completed.
    - **Voice app**- choose the Auto Attendant or Call Queue to transfer to.
        - See [Nested auto attendants and call queues](aa-cq-plan-nesting).
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **Resource account**- choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **External phone number**- any phone number.
        - See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **Voicemail (personal)**- a person in your organization who can receive voice calls. The call will go directly to their voicemail.
        - See Additional messaging to configure a message through PowerShell that will play before the transfer is completed.
    - **Voicemail (shared)**- The voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable Let people outside the organization email this team for the Microsoft 365 group that you specify.
        - Additional options:
            - **Transcription** - turn on transcription for voicemails left by a caller.
            - **Skip voicemail system message** - turns off the default voicemail system prompts.
        - A greeting must be configured.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message**- enter the text for the greeting.
                - Don't include any special characters in the greeting message when redirecting to **Voicemail (shared)** as these aren't spoken by the system.

    If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

##### No Agents Opted/Logged In

This call exception handling option handles calls when no representatives are opted into the queue or all representatives are logged out of the queue.

###### Apply settings only to new incoming calls

Controls whether the No Agents call treatment applies to:

- **Off** - All Calls (default) - calls already in queue and new calls arriving to the queue, or
- **On** - New Calls Only - only new calls that arrive once the No Agents condition occurs, existing calls remain in queue.

###### When no agents are available

The following options

- **Queue call (default)** - calls will remain in queue - the no agents handling exception is ignored.

- **Disconnect** - the call will be disconnected.

    - You can configure a message to play before the call is disconnected.
        - **None** - no message will play.
        - **Play an audio file** - upload a prerecorded audio file.
        - **Add a greeting message** - enter the text for the greeting.
- **Redirect call** - the call is redirected to one of the following call routing destinations:

    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled.
            - For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
        - See Additional messaging to configure a message through PowerShell that will play before the transfer is completed.
    - **Voice app**- choose the Auto Attendant or Call Queue to transfer to.
        - See [Nested auto attendants and call queues](aa-cq-plan-nesting).
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **Resource account**- choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **External phone number**- any phone number.
        - See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
        - You can configure a message to play before the transfer is completed.
            - **None** - no message will play.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message** - enter the text for the greeting.
    - **Voicemail (personal)**- a person in your organization who can receive voice calls. The call will go directly to their voicemail.
        - See Additional messaging to configure a message through PowerShell that will play before the transfer is completed.
    - **Voicemail (shared)**- The voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable Let people outside the organization email this team for the Microsoft 365 group that you specify.
        - Additional options:
            - **Transcription** - turn on transcription for voicemails left by a caller.
            - **Skip voicemail system message** - turns off the default voicemail system prompts.
        - A greeting must be configured.
            - **Play an audio file** - upload a prerecorded audio file.
            - **Add a greeting message**- enter the text for the greeting.
                - Don't include any special characters in the greeting message when redirecting to **Voicemail (shared)** as these aren't spoken by the system.

    If you select **Play an audio file**, you must upload a supported audio file containing the greeting that you want to play. See [Audio file formats and maximum size](aa-cq-reference-limits-supported-configurations#audio-file-formats-and-maximum-size).

Note

The **No Agents** handling exception occurs under the following conditions:

- Presence-based routing off: No representatives are opted into the queue.
- Presence-based routing on: No representatives logged in, or all representatives are in *Appear Offline*.

If representatives are logged in or opted in, then calls are queued.

Important

Known issues:

1. When **Longest idle** is selected as the routing method, the **No Agents** treatment doesn't work when ***New Calls Only*** is selected and new calls are queued. The ***All Calls*** option works as expected. Support is investigating.

Once you select your call overflow, call timeout, and no agents handling options, select the **Next** button at the bottom of the **Add a Call queue** page.

##### Previous steps:

- Step 1 - General info
- Step 2 - Greeting and music
- Step 3 - Call answering
- Step 4 - Agent selection
- Step 5 - Callback

Step 7 - Templates (expand to see instructions)

#### Step 7: Templates

#### Set the Automatic Recording for Call Queue template (optional)

Select an existing template from the drop-down or Create a new template.

To create an Automatic Recording for Call Queue template, see [Automatic Recording for Call Queue template](aa-cq-setup-call-queue-template-recording-automatic)

##### Set the Compliance Recording for Call Queue template (optional)

Select up to two existing templates from the drop-down or Create a new template.

To create a Compliance Recording for Call Queue template, see [Compliance Recording for Call Queue template](aa-cq-setup-call-queue-template-recording-compliance)

##### Set the Shared call history for call queue template (optional)

Select an existing template from the drop-down or Create a new template.

To create a Shared Call History for Call Queue template, see [Shared Call History for Call Queue template](aa-cq-setup-call-queue-template-shared-history)

Once you select the optional templates, select **Next** button at the bottom of the **Add a Call queue** page.

##### Previous steps:

- Step 1 - General info
- Step 2 - Greeting and music
- Step 3 - Call answering
- Step 4 - Agent selection
- Step 5 - Callback
- Step 6 - Exception handling

Step 8 - Authorized users (expand to see instructions)

#### Step 8: Authorized users

**Authorized users** specifies the users who are authorized to make changes to this call queue. You can determine the capabilities that the users have through [Teams voice applications policies](aa-cq-manage-voice-applications-policies) assigned to your users.

To **add a user** to the authorized users:

1. Select **Add**, search for the user, select **Add**, and then select **Add**.

Important

A user must have a policy assigned that enables at least one type of configuration change. The user must also be assigned as an authorized user to at least one auto attendant or call queue.

A user can't make any configuration changes if:

- The user has a policy assigned but isn't assigned as an authorized user to at least one auto attendant or call queue.
- The user is assigned as an authorized user to at least one auto attendant or call queue but doesn't have a policy assigned.

Note

A maximum of 15 authorized users can be assigned to the call queue.

For more information, see [Set up authorized users](aa-cq-setup-authorized-users).

Once you select your authorized users, select the **Submit** button at the bottom of the **Add a Call queue** page.

##### Previous steps:

- Step 1 - General info
- Step 2 - Greeting and music
- Step 3 - Call answering
- Step 4 - Agent selection
- Step 5 - Callback
- Step 6 - Exception handling
- Step 7 - Templates

## Summary of recommended call queue settings

The following settings are recommended:

- **Conference mode** to **On**
- **Routing method** to **Round robin** or **Longest idle**
- **Presence-based routing** to **On**
- **Agent alert time** to a minimum of **20 seconds**

## Extra functionality available through PowerShell cmdlets

Important

These configuration options are currently only available through PowerShell cmdlets and don't appear in the Teams admin center.

### Additional messaging

The Overflow, Call timeout, and No Agents exception redirect options for **Person in organization** and **Voicemail personal** support additional prompting just like the other redirect options.

Expand to see PowerShell options

| New-CsCallQueue (For new call queues) | Set-CsCallQueue (For existing call queues) |
| --- | --- |
| [-OverflowRedirectPersonTextToSpeechPrompt](/en-us/powershell/module/teams/new-cscallqueue#-OverflowRedirectPersonTextToSpeechPrompt) | [-OverflowRedirectPersonTextToSpeechPrompt](/en-us/powershell/module/teams/set-cscallqueue#-OverflowRedirectPersonTextToSpeechPrompt) |
| [-OverflowRedirectPersonAudioFilePrompt](/en-us/powershell/module/teams/new-cscallqueue#-OverflowRedirectPersonAudioFilePrompt) | [-OverflowRedirectPersonAudioFilePrompt](/en-us/powershell/module/teams/set-cscallqueue#-OverflowRedirectPersonAudioFilePrompt) |
| [-OverflowRedirectVoicemailTextToSpeechPrompt](/en-us/powershell/module/teams/new-cscallqueue#-OverflowRedirectVoicemailTextToSpeechPrompt) | [-OverflowRedirectVoicemailTextToSpeechPrompt](/en-us/powershell/module/teams/set-cscallqueue#-OverflowRedirectVoicemailTextToSpeechPrompt) |
| [-OverflowRedirectVoicemailAudioFilePrompt](/en-us/powershell/module/teams/new-cscallqueue#-OverflowRedirectVoicemailAudioFilePrompt) | [-OverflowRedirectVoicemailAudioFilePrompt](/en-us/powershell/module/teams/set-cscallqueue#-OverflowRedirectVoicemailAudioFilePrompt) |
| [-TimeoutRedirectPersonTextToSpeechPrompt](/en-us/powershell/module/teams/new-cscallqueue#-TimeoutRedirectPersonTextToSpeechPrompt) | [-TimeoutRedirectPersonTextToSpeechPrompt](/en-us/powershell/module/teams/set-cscallqueue#-TimeoutRedirectPersonTextToSpeechPrompt) |
| [-TimeoutRedirectPersonAudioFilePrompt](/en-us/powershell/module/teams/new-cscallqueue#-TimeoutRedirectPersonAudioFilePrompt) | [-TimeoutRedirectPersonAudioFilePrompt](/en-us/powershell/module/teams/set-cscallqueue#-TimeoutRedirectPersonAudioFilePrompt) |
| [-TimeoutRedirectVoicemailTextToSpeechPrompt](/en-us/powershell/module/teams/new-cscallqueue#-TimeoutRedirectVoicemailTextToSpeechPrompt) | [-TimeoutRedirectVoicemailTextToSpeechPrompt](/en-us/powershell/module/teams/set-cscallqueue#-TimeoutRedirectVoicemailTextToSpeechPrompt) |
| [-TimeoutRedirectVoicemailAudioFilePrompt](/en-us/powershell/module/teams/new-cscallqueue#-TimeoutRedirectVoicemailAudioFilePrompt) | [-TimeoutRedirectVoicemailAudioFilePrompt](/en-us/powershell/module/teams/set-cscallqueue#-TimeoutRedirectVoicemailAudioFilePrompt) |
| [-NoAgentRedirectPersonTextToSpeechPrompt](/en-us/powershell/module/teams/new-cscallqueue#-NoAgentRedirectPersonTextToSpeechPrompt) | [-NoAgentRedirectPersonTextToSpeechPrompt](/en-us/powershell/module/teams/set-cscallqueue#-NoAgentRedirectPersonTextToSpeechPrompt) |
| [-NoAgentRedirectPersonAudioFilePrompt](/en-us/powershell/module/teams/new-cscallqueue#-NoAgentRedirectPersonAudioFilePrompt) | [-NoAgentRedirectPersonAudioFilePrompt](/en-us/powershell/module/teams/set-cscallqueue#-NoAgentRedirectPersonAudioFilePrompt) |
| [-NoAgentRedirectVoicemailTextToSpeechPrompt](/en-us/powershell/module/teams/new-cscallqueue#-NoAgentRedirectVoicemailTextToSpeechPrompt) | [-NoAgentRedirectVoicemailTextToSpeechPrompt](/en-us/powershell/module/teams/set-cscallqueue#-NoAgentRedirectVoicemailTextToSpeechPrompt) |
| [-NoAgentRedirectVoicemailAudioFilePrompt](/en-us/powershell/module/teams/new-cscallqueue#-NoAgentRedirectVoicemailAudioFilePrompt) | [-NoAgentRedirectVoicemailAudioFilePrompt](/en-us/powershell/module/teams/set-cscallqueue#-NoAgentRedirectVoicemailAudioFilePrompt) |

### Hiding authorized users

Hidden authorized users aren't visible to Queues App users.

Hiding authorized users (expand to see instructions)

| New-CsCallQueue (For new call queues) | Set-CsCallQueue (For existing call queues) |
| --- | --- |
| [-HideAuthorizedUsers](/en-us/powershell/module/teams/new-cscallqueue#-hideauthorizedusers) | [-HideAuthorizedUsers](/en-us/powershell/module/teams/set-cscallqueue#-hideauthorizedusers) |

#### Example 1

To hide an authorized user in a call queue, see the following example:

```powershell
Set-CsCallQueue -Identity <CallQueueGUID> -AuthorizedUsers @("User 01 GUID", "User 02 GUID") -HideAuthorizedUsers @("User 02 GUID")
```

## Related Call Queue setup and configuration articles

- [Authorized users](aa-cq-setup-authorized-users)
- [Shared call history](aa-cq-setup-call-queue-template-shared-history)
- [Call priorities for call queues](aa-cq-setup-call-queue-priorities)
- [Automatic recording for call queues](aa-cq-setup-call-queue-template-recording-automatic)
- [Compliance recording for call queues](aa-cq-setup-call-queue-template-recording-compliance)
- [Answering Auto Attendant and Call Queue calls](aa-cq-reference-answer-calls)

## PowerShell

For instructions on creating call queues using PowerShell, see [Call queues with PowerShell](aa-cq-setup-call-queue-cmdlets).

## Call queue diagnostic tool

Call queue diagnostic tool (expand to see instructions)

If you're an administrator, you can use the following diagnostic tool to validate that a call queue is able to receive calls:

1. Select **Run Tests**, which populates the diagnostic in the Microsoft 365 admin center.
2. In the Run diagnostic pane, enter the resource account in the **Username or Email** field, and then select **Run Tests**.
3. The tests return the best next steps to address any tenant, policy, and resource account configurations to validate that the call queue is able to receive calls.