---
layout: Conceptual
title: Set up Teams Phone in your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/setting-up-your-phone-system
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-04-28T00:00:00.0000000Z
ms.topic: install-set-up-deploy
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- intro-get-started
description: Learn how to set up Microsoft Teams Phone for your organization in Microsoft 365.
locale: en-us
document_id: cad07c2d-dc0c-faa4-9fde-0377c413dc0f
document_version_independent_id: e5a76596-eb09-88eb-46ca-4353061bd631
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/setting-up-your-phone-system.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: setting-up-your-phone-system
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/setting-up-your-phone-system.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3da9b382-b0ba-6d33-80c4-955a13a661af
---

# Set up Teams Phone in your organization - Microsoft Teams | Microsoft Learn

This article provides a high-level roadmap to content for setting up Microsoft Teams Phone--Microsoft's technology for enabling external calling and phone system capabilities in the Microsoft 365 cloud.

Teams Phone deployments will vary in scope for each organization. The steps outlined in this article are general guidelines and can be modified for your deployment.

## Prerequisites

The following guidance assumes you're adding Teams Phone to an existing Teams deployment. If need to deploy Teams as part of your Teams Phone deployment, then start by [Setting up Teams in your org](deploy-enterprise-setup).

Before starting with your Teams Phone deployment, ensure you have a fundamental understanding of the knowledge provided in the following articles.

- [Calling in Teams Overview](cloud-voice-landing-page)
- [Teams Phone features](here-s-what-you-get-with-phone-system)
- [Teams Phone licensing](teams-phone-licensing)

## Provisioning steps - example

To enable Teams Phone in your organization, a series of tasks must be completed.

**Overview of steps** - This article introduces the following steps. Each step contains a summary of the tasks to perform and links to more detailed information.

- Step 1: Buy and assign a Teams Phone license
- Step 2: Choose a PSTN connectivity option
- Step 3: Get and assign phone numbers for your users and services
- Step 4: Set up emergency calling
- Step 5: If you want to set up an auto attendant
- Step 6: If you want to set up a call queue
- Step 7: Set up other Teams Phone features
- Step 8: Manage your deployment

Note

Be aware that some steps will differ depending on the PSTN connectivity option you choose. For example, the steps and sequence for phone number management and emergency calling management might differ. These differences are described in detail in the associated articles.

## Step 1: Buy and assign a Teams Phone license

For each user who uses Teams Phone, you must assign a Teams Phone license to that user.

Don't assign the **Microsoft Teams Phone Resource Account** license to any user other than resource accounts.

For licensing considerations, see [Teams Phone licensing](teams-phone-licensing).

In addition to licensing, the users must be "voice enabled."

To voice enable your users, you can use the Teams admin center or PowerShell.

- In the Teams admin center, go to a **Users** &gt; **Manage users** and select the user you want to edit. Under the **Account** tab &gt; **Assigned phone number**, turn **Enterprise Voice** to **On** and select **Save**.
- For PowerShell, use the [Set-CsPhoneNumberAssignment](/en-us/powershell/module/teams/set-csphonenumberassignment) cmdlet and set the `-EnterpriseVoiceEnabled` parameter to `$true`.

You can assign a license to a single user or you can assign licenses to multiple users in bulk. For more information about available Teams Phone licenses and how to acquire and assign licenses, see [Teams add-on licenses](/en-us/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) and [Assign Microsoft Teams add-on licenses](/en-us/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## Step 2: Choose a PSTN connectivity option

Microsoft options for making external calls to the PSTN include:

- [Microsoft Calling Plan](calling-plans-for-office-365). An all-in-the-cloud solution with Microsoft as your PSTN carrier. If you choose Microsoft Calling Plan as your connectivity option, you have a choice of Calling Plan options, including Domestic, International, and Pay-as-you-go plans.
- [Operator Connect](operator-connect-plan). If your existing carrier participates in the Microsoft Operator Connect program, they can manage PSTN calling for you.
- [Teams Phone Mobile](operator-connect-mobile-plan). If your existing carrier participates in the Microsoft Teams Phone Mobile program, they can manage the service for using SIM-enabled mobile phone numbers with Teams.
- [Direct Routing](direct-routing-plan). This option lets you use your own PSTN carrier by connecting your SBCs to Teams Phone.

For more information about all connectivity options and which one is the best solution for your organization, see [PSTN connectivity options](pstn-connectivity) and [Voice and PSTN connectivity license options](/en-us/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing#voice-and-pstn-connectivity).

Note

For user migrations to PSTN, Shared Calling allows migrating large groups of users to Teams Phone without assigning phone numbers, but still allows users to make calls. Shared calling enables user migration as an effective first step in your migration and supports a phased approach to your Teams Phone road map. See [Shared Calling](shared-calling-plan).

## Step 3: Get and assign phone numbers for your users and services

Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them.

In addition to getting phone numbers for your users, you can acquire toll or toll-free phone numbers for services such as auto attendants and call queues. A service number can handle hundreds of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

How you acquire and manage phone numbers differs depending on your PSTN connectivity option.

For information on how to manage phone numbers for your users and services, see the following articles.

- [Manage phone numbers for your organization](manage-phone-numbers-landing-page) – Provides an overview of phone number types [user and service (Conferencing, Voice apps, etc.)] with links to specific articles for acquiring and managing numbers.
- [Manage phone numbers for users](assign-change-or-remove-a-phone-number-for-a-user) – Describes how to assign and manage the user phone numbers you've acquired.
- [Manage resource accounts for service numbers](aa-cq-manage-resource-accounts) - Describes how to create resource accounts for auto attendants and call queues and assign service numbers to those resource accounts.
- [How many telephone numbers can you get](how-many-phone-numbers-can-you-get) – Describes how many phone numbers you can get, depending on the types of telephone numbers and types of licenses you've bought and assigned.

## Step 4: Set up emergency calling

To set up emergency calling, you--or your PSTN carrier--must define emergency locations and ensure that emergency locations are assigned to each user.

An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance. When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.

How you set up emergency locations and assign these locations to users differs depending on the PSTN connectivity option you choose. For some options, your carrier assumes much of the responsibility for setting up emergency calling. For more information, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing).

Dynamic emergency calling provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client. Setting up dynamic emergency calling also requires you to configure your network settings and topology. For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling) and [Network settings for cloud voice features](cloud-voice-network-settings).

For information about assigning emergency locations to users, see [Manage emergency locations for your organization](assign-change-emergency-location-user).

## Step 5: If you want to set up an auto attendant

Auto attendants let people who call in to your organization navigate a menu system to get them to the right department, call queue, person, or operator.

For information about setting up auto attendants, see [Plan for Teams auto attendants and call queues](aa-cq-plan-overview) and [Set up an auto attendant](aa-cq-setup-auto-attendant).

## Step 6: If you want to set up a call queue

Call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call. You can create single or multiple call queues for your organization.

For more information about call queues, see [Plan for Teams auto attendants and call queues](aa-cq-plan-overview) and [Create a call queue](aa-cq-setup-call-queue).

## Step 7: Set up other Teams Phone features

There are numerous Teams Phone features, which are summarized in [Teams Phone features](here-s-what-you-get-with-phone-system). Some of these features require configuration, others do not. In addition to auto attendants and call queues, some of the more common features you might want to configure include:

- [Cloud voicemail](set-up-phone-system-voicemail)
- [Caller ID](caller-id-policies)
- [Call forwarding and delegation](user-call-settings)

Calling policies control which calling and call forwarding features are available to your users. For more information, see [Calling policies](teams-calling-policy).

## Step 8: Manage your deployment

A successful Teams Phone deployment also involves managing your devices and monitoring call quality and performance. For more information, see:

- [Manage devices](devices/device-management)
- [Manage and monitor call quality](monitor-call-quality-qos)