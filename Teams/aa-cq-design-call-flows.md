---
layout: Conceptual
title: Design - Call flows for voice applications - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-design-call-flows
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
ms.topic: concept-article
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
customer-intent: As a Teams Administrator, I want to learn how I should design my call flows so I can easily provision them in Teams.
description: Learn how to design and diagram call flows for Teams Phone Agent, auto attendants, and call queues, including routing destinations and best practices.
locale: en-us
document_id: ae20291d-bcd6-aab7-0810-7804a6fc426c
document_version_independent_id: ae20291d-bcd6-aab7-0810-7804a6fc426c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-design-call-flows.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-design-call-flows
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-design-call-flows.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: f9e59f5b-bf05-a7e9-be1e-60371165a541
---

# Design - Call flows for voice applications - Microsoft Teams | Microsoft Learn

As part of the planning process, we recommend that you work out the call routing for your organization in a diagram. The diagram helps determine the most efficient routing for people calling in to your organization. You can also use the diagram to determine the auto attendants and call queues that you need to create, along with related requirements such as service numbers, licenses, and resource accounts.

Let's look at how auto attendants and call queues route calls.

## Auto Attendants

Auto attendants route all calls in one of the following ways:

- **Redirect immediately** - calls can be redirected to one of the call routing destinations immediately upon answering or after an initial greeting.
- **Redirect based on dial options** - callers can be directed to choose between options that are assigned to the numbers on their telephone keypad: 0-9, `*`, and `#`. Each dial key can be assigned a call routing destination.
- **Dial people by name or extension** - callers can be directed to dial the extension number of the person they're trying to reach in your organization's directory, or by spelling the person's name.
- **Disconnect** - an auto attendant can hang up the call.

An auto attendant can redirect calls to the following destinations:

- **Operator**- the operator defined for the auto attendant.
    - Defining an operator is optional but recommended.
    - An operator can be any of the other destinations in this list.
- **Person in the organization** - a person in your organization who is able to receive voice calls. This person can be an online user or a user hosted on-premises using Skype for Business Server.
- **Voice app** - another auto attendant or a call queue. The call priority can be set when the destination is a call queue.
- **Resource account** - the resource account associated with another auto attendant or call queue. The call priority can be set when the resource account is associated with a call queue.
- **Voicemail**- the voice mailbox associated with a Microsoft 365 Group, distribution list, or mail-enabled security group that you specify.
    - Using a Microsoft 365 Group is recommended.
    - You can choose if you want voicemail transcriptions and the "Please leave a message after the tone" system prompt.
- **External phone number** - any phone number. See [Outbound Calls from Teams Phone Agent, Auto Attendant, or Call Queue](aa-cq-reference-prerequisites-licensing#outbound-calls-from-teams-phone-agent-auto-attendant-or-call-queue).
- **Announcement**- play a recorded audio file or text-to-speech.
    - The caller returns to the auto attendant menu when the announcement finishes playing.

Auto attendants offer separate call routing options for calls received outside of business hours and on holidays.

For more information on when to use **Voice app** or **Resource account** as the routing destination, see [Nested auto attendants and call queues](aa-cq-plan-nesting).

Note

A single auto attendant can only support a single "dial by" method. To allow callers to dial by name and by number, you need to create an auto attendant that has an option for dial by name and another auto attendant for dial by extension. Each of these options route to separate auto attendants configured for these "dial by" scenarios.

## Call Queues

Call queues place the caller on hold until a representative (agent) assigned to the queue is available to take their call. There are three situations where a caller might be directed out of the queue:

- **Call overflow** - if the number of calls waiting in the queue exceeds the limit that you set, then new callers are redirected out of the queue.
- **Call timeout** - if a caller stays in the queue longer than the configured timeout setting, they're redirected out of the queue.
- **No agents** - if there are no agents opted in or logged into the queue, callers may be redirected out of the queue.

Calls redirected out of a queue can be sent to the following destinations:

- **Person in the organization** - a person in your organization who is able to receive voice calls. This person can be an online user or a user hosted on-premises using Skype for Business Server.
- **Voice app** - another auto attendant or a call queue.
- **Resource account** - the resource account associated with another auto attendant or call queue.
- **External phone number** - any phone number. See [Outbound Calls from Teams Phone Agent, Auto Attendant, or Call Queue](aa-cq-reference-prerequisites-licensing#outbound-calls-from-teams-phone-agent-auto-attendant-or-call-queue).
- **Voicemail (personal)** - the voice mailbox associated with a specific user.
- **Voicemail (shared)**- the voice mailbox associated with a Microsoft 365 Group, distribution list, or mail-enabled security group.
    - You can choose if you want voicemail transcriptions and the "Please leave a message after the tone" system prompt.

For more information on when to use **Voice app** or **Resource account** as the routing destination, see [Nested auto attendants and call queues](aa-cq-plan-nesting).

## Call flow diagrams

The following call flow diagrams show three different examples of call routing using auto attendants and call queues.

![Call flow diagram showing call priority based on the dialed resource account phone number.](media/aa-cq/aa-cq-call-priorities-scenario-1.svg)

In this example:

- The call queues are open 24/7.
- Call priorities are assigned based on the resource account phone number dialed by the caller.

![Call flow diagram showing call priority based on auto attendant menu choices.](media/aa-cq/aa-cq-call-priorities-scenario-2.svg)

In this example:

- The auto attendant assigns the call priority based on the menu option selected by the caller.

![Call flow diagram showing call priority for call queue transfers.](media/aa-cq/aa-cq-call-priorities-scenario-3.svg)

In this example:

- The auto attendant assigns a call priority of 3 to all callers.
- Call transfers to the Tier 2 Support call queue can be prioritized over regular callers.

We recommend that you create one or more diagrams similar to the example given to map out your call routing. Be sure your diagram or accompanying documentation includes the following:

- The auto attendants and call queues that have direct access via phone numbers, as these require resource accounts.
- The off-hours and holiday routing requirements for each auto attendant.
- The membership for each call queue. (You can add users individually or map the queue to different kinds of groups. Mapping a queue to a team provides the most versatile experience.)

## Call routing best practices

Here are some call routing best practices:

- Look at your existing calling system and analyze the types and frequency of incoming calls. Use this information to help inform your auto attendant and call queue structure.
- Put the most common options at the start of the menu to route calls as quickly as possible.
- Avoid connecting service numbers directly to call queues unless the queues are available 24/7. Call queues don't allow for separate call handling for off hours or holidays. If you want to have a queue with a direct number, assign the number to an auto attendant that automatically redirects to the queue during business hours.
- If you receive numerous calls requesting basic information about your company, such as business hours, location, or website address, consider creating an auto attendant to answer these questions with recorded messages.
- Keep the list of menu items to five or fewer. Callers can have trouble remembering more than five options. Use [nested auto attendants](aa-cq-plan-nesting) if more options are needed to properly route a call.
- Describe the service first, followed by the option (for example: For Sales press 1) rather than the other way around (for example: Press 1 for Sales).
- Use terminology your callers understand rather than what you might use internally.
- To prevent misdirecting calls, avoid frequent updates to call routing. If you change your menu options for an auto attendant, let callers know in the voice prompts for the first 30 days.

Important

The maximum number of transitions a single call is permitted to make through auto attendants and call queues is 25. After the 25th transition, the call is disconnected. This prevents a call from infinitely looping through a series of auto attendants and call queues.

For example, if a call arrives on auto attendant #1 and the caller selects an option that sends them to auto attendant #2, then a transition has occurred. If the caller selects an option on auto attendant #2 that returns them to auto attendant #1 or sends them to call queue #1, a second transition has occurred.

Calls that stay in the same auto attendant but return to the main menu after an announcement or when a user selects a repeat option count as transitions and apply to the maximum transition limit.