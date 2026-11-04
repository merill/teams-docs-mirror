---
layout: Conceptual
title: Plan for Teams Phone Mobile - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/operator-connect-mobile-plan
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.date: 2026-08-21T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
ms.reviewer: odocspr
search.appverid: MET150
description: Learn how to plan for Teams Phone Mobile, including benefits, requirements, licensing, and deployment considerations.
locale: en-us
document_id: d80cd376-5bcb-2548-ae65-14fe0cc62445
document_version_independent_id: d80cd376-5bcb-2548-ae65-14fe0cc62445
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/operator-connect-mobile-plan.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: operator-connect-mobile-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/operator-connect-mobile-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c5b22188-7bd9-bde4-4f9f-7254d95b5518
---

# Plan for Teams Phone Mobile - Microsoft Teams | Microsoft Learn

This article is for administrators and IT professionals who are evaluating Teams Phone Mobile for their organization. It provides an overview of Teams Phone Mobile, when to use it, licensing and requirements, and key considerations for planning your deployment.

Teams Phone Mobile is a Public Switched Telephone Network (PSTN) connectivity option for Microsoft Teams Phone. With Teams Phone Mobile, a user's company-provided, SIM-enabled mobile phone number can also be used as their Teams phone number. This integration gives users one business phone number across their mobile device and Microsoft Teams endpoints.

For a list of operators participating in the Teams Phone Mobile program and the countries or regions where their service is available, see [Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/teams-phone-mobile).

For information about other PSTN connectivity options, see [PSTN connectivity options](pstn-connectivity).

## When to choose Teams Phone Mobile

Teams Phone Mobile is designed for organizations with mobile-first employees who want to use one business phone number across Microsoft Teams and their mobile devices.

Teams Phone Mobile might be the right solution for your organization if:

- You have mobile-first users, such as sales representatives, field workers, or employees who frequently work away from a desk.
- You want users to have one company-provided, SIM-enabled mobile number for both their mobile device and Teams Phone.
- Your preferred mobile operator participates in the Teams Phone Mobile program.
- You want to work with a participating mobile operator to provide PSTN connectivity for Teams.
- You want users to make and receive business calls through either their smartphone's native dialer or Microsoft Teams.

You can use Teams Phone Mobile alongside other PSTN connectivity options within the same Teams tenant. For example, you might use Teams Phone Mobile for mobile workers, Operator Connect for knowledge workers, and Direct Routing for users or locations with more complex telephony requirements.

Note

Teams Phone Mobile supports user phone numbers. It doesn't support Audio Conferencing numbers or voice application numbers, such as numbers used for Auto attendants and Call queues.

## How Teams Phone Mobile works

Teams Phone Mobile connects a participating mobile operator with Microsoft Teams Phone. The operator provides the mobile service and eligible SIM-enabled phone numbers, while Teams extends Teams Phone capabilities to those numbers.

At a high level, deploying Teams Phone Mobile involves the following steps:

1. **Choose a participating mobile operator.** Confirm that the operator supports Teams Phone Mobile in the countries or regions where you plan to deploy the service.
2. **Verify licensing and user requirements.** Make sure users have the required Teams Phone licenses and an eligible mobile subscription.
3. **Enable the operator.** Enable your selected operator for your organization in the Teams admin center.
4. **Add phone numbers.** Work with your operator to make eligible SIM-enabled mobile numbers available in your Microsoft 365 tenant.
5. **Assign numbers to users.** Assign the mobile numbers to licensed Teams users.
6. **Configure calling settings.** Configure emergency addresses and user incoming calling preferences as appropriate for your deployment.

For step-by-step configuration guidance, see [Configure Teams Phone Mobile](operator-connect-mobile-configure).

## Benefits and key capabilities

Teams Phone Mobile combines mobile connectivity with Teams Phone capabilities to provide a consistent calling experience across devices and networks.

### One business phone number

Users can use one company-provided, SIM-enabled phone number across their mobile device and Teams endpoints. Calls can be made and received through either the smartphone's native dialer or Teams.

### Call continuity across devices

Users can move calls from their smartphone's native dialer to the Teams app or another Teams endpoint without dropping the call. This capability allows users to start a call on one device and continue it on another.

### Integrated Teams calling experience

Teams Phone Mobile integrates mobile calling with Teams capabilities, including:

- Combined call history.
- Unified voicemail.
- Teams presence integration.
- Call transfer through Teams.
- Incoming calling preferences.
- Caller ID options.

When a user is on a call using the native dialer, their Teams presence can reflect that they're in a call.

### Collaboration capabilities

Users can move calls into Teams and access collaboration capabilities such as video, content sharing, recording, transcription, and adding participants.

### Security and compliance

Organizations can extend supported Teams security, privacy, and compliance capabilities to Teams Phone Mobile calling scenarios.

Compliance recording can also be available for calls made through the native dialer and Teams app when your organization has the required subscriptions and services.

## Licensing and requirements

Before deploying Teams Phone Mobile, verify that your organization and users meet the following requirements.

### Licensing

Users must have a Teams Phone license.

Teams Phone functionality is available through eligible Teams Phone licensing, including supported Microsoft 365 licensing that includes Teams Phone.

For more information, see [What is Teams Phone](what-is-phone-system-in-office-365) and [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).

### Mobile operator and subscription

Users must have an eligible mobile subscription with a participating Teams Phone Mobile operator.

The operator must support using the user's SIM-enabled mobile number with Teams Phone. Your operator makes eligible phone numbers available in your Microsoft 365 tenant so that you can assign them to users.

### Teams mode

Users who are assigned Teams Phone Mobile numbers must be in **TeamsOnly** mode. Your entire organization doesn't need to be in TeamsOnly mode.

For more information, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability).

## Plan your deployment

Before configuring Teams Phone Mobile, consider the following areas.

### Identify your users

Determine which users or groups would benefit from Teams Phone Mobile.

Teams Phone Mobile is particularly suited for users who rely heavily on mobile devices for business calling and need access to the same business identity across their mobile device and Teams.

You can deploy Teams Phone Mobile to selected users without using it as the PSTN connectivity option for your entire organization.

### Choose a participating operator

Identify a Teams Phone Mobile operator that supports the countries or regions where your users are located.

Confirm with the operator:

- Teams Phone Mobile availability in the required countries or regions.
- Mobile subscription requirements.
- Phone number eligibility.
- Number migration or porting requirements.
- Operator-specific deployment requirements.

For participating operators and availability, see [Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/teams-phone-mobile).

### Plan your phone numbers

Determine whether users will receive new mobile numbers or use existing eligible numbers.

Your operator makes eligible numbers available to your Microsoft 365 tenant. How you manage the numbers depends on whether you're assigning numbers to new Teams users or moving users from another PSTN connectivity option.

For detailed phone number scenarios, see [Manage phone numbers for Teams Phone Mobile](operator-connect-mobile-configure-numbers).

### Plan for emergency calling

Review your emergency calling requirements before assigning Teams Phone Mobile numbers.

Emergency address management for Teams endpoints can vary depending on your operator. Your operator might assign emergency addresses, allow you to manage them in the Teams admin center, or require you to contact the operator to make changes.

Calls made through the native dialer of a SIM-enabled smartphone might use location information available to the mobile operator for emergency calling.

For more information, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling).

### Plan incoming calling preferences

Determine how you want incoming calls to behave on users' SIM-enabled mobile devices.

Teams Phone Mobile supports policies that determine whether incoming calls ring the Teams app or the smartphone's native dialer first. You can also allow users to control their incoming calling preference.

These policies can be configured after Teams Phone Mobile is enabled.

For configuration instructions, see [Configure Teams Phone Mobile](operator-connect-mobile-configure#step-6-manage-user-incoming-calling-policies).

## What's next?

After you've completed your planning, configure Teams Phone Mobile for your organization:

1. [Configure Teams Phone Mobile](operator-connect-mobile-configure) to enable your operator and configure the service.
2. [Manage phone numbers for Teams Phone Mobile](operator-connect-mobile-configure-numbers) to assign new numbers or move existing numbers.
3. Review [PSTN connectivity options](pstn-connectivity) if you plan to use Teams Phone Mobile alongside other PSTN connectivity solutions.