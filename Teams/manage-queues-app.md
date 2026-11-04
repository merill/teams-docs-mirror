---
layout: Conceptual
title: Manage Queues app for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-queues-app
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.date: 2026-09-30T00:00:00.0000000Z
ms.topic: how-to
ms.reviewer: colongma, emkirby
audience: admin
ms.service: msteams
ms.subservice: teams-calling
description: Learn how to configure the Queues app in Microsoft Teams.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-voice
- tier1
- teams-1p-app-admin
search.appverid: MET150
locale: en-us
document_id: 1c426f25-bd29-6c77-3a48-f51992ca59bd
document_version_independent_id: 1c426f25-bd29-6c77-3a48-f51992ca59bd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-queues-app.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-queues-app
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-queues-app.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 67159b2d-ddc6-782b-578b-0d03f0a2799c
---

# Manage Queues app for Microsoft Teams - Microsoft Teams | Microsoft Learn

## Overview of Queues app

The Queues app is a Teams-native solution designed to empower organizations to manage customer engagements efficiently, unlocking a set of advanced call functionalities for Teams Phone Call queues and Auto attendants, such as:

- **Call queue management**: Admins can now delegate authorized users, also known as leads or supervisors, to manage and configure Call queues and Auto attendants directly from the Teams client. Authorized users can configure Call queues and Auto attendants from Call settings, and they can opt agents into and out of the queue from Queues app. For more information, see Configure Queues app.
- **Real-time metrics**: The number of waiting calls, average wait time, longest call waiting time metrics, and more are included in real-time metrics within the Queues app. The analytics report shows activity made in the queue from 12:00 AM local time of the signed in user. Real-time metric reports are reported in local time based on the user's current time zone. For more information on real-time reports, see [Get real-time and historical analytics in the Queues app for Microsoft Teams](https://support.microsoft.com/teams/calling/get-real-time-and-historical-analytics-in-the-queues-app-for-microsoft-teams).
- **Historical reporting**: View historical metrics for call queues, and auto attendants, and agent queue actions. Historical metrics report up to the past 45 days and are reported in the UTC time zone. For more information on historical reports, see [Get real-time and historical analytics in the Queues app for Microsoft Teams](https://support.microsoft.com/teams/calling/get-real-time-and-historical-analytics-in-the-queues-app-for-microsoft-teams).
- **Monitor, Whisper, Barge, Takeover** - Authorized users can enter into a monitoring session with selected agents for private coaching. Authorized users can listen to customer calls, whisper to agents with private messages, even barge into or takeover the calls.

    - For information about configuring Monitor, Whisper, Barge, and Takeover, see [Manage voice applications policies in Microsoft Teams](aa-cq-manage-voice-applications-policies).
    - For information on using Monitor, Whisper, Barge, and Takeover, see [Monitor and assist team members in the Queues app in Microsoft Teams](https://support.microsoft.com/teams/calls-devices/monitor-and-assist-team-members-in-the-queues-app-in-microsoft-teams).

Queues app is designed to enhance call queue handling capabilities within Teams for your users who utilize or plan to utilize call queues and auto attendants.

Keep the following in mind:

- The Queues app is currently supported on Teams desktop, Mac, and Virtualized Desktop Infrastructure (VDI) clients, [Teams phones (touch devices only)](phones/queues-app), and iOS and Android mobile clients. It's not supported on web clients.
- Nesting Auto attendants and Call queues without a resource account isn't currently supported for [Authorized users](aa-cq-authorized-users-plan) in Queues App. If you nest an Auto attendant or Call queue without a resource account, authorized users can't edit the auto attendant or call queue.
- Queues app is available in all regions where Teams Phone is supported. For more information, see [Country/region availability for Teams Phone](calling-plan-overview).
- Queues app is available in Commercial, GCC, GCC High, and DoD environments.
- For the best experience in Queues app, we advise having no more than 100 call queues assigned per user. There's a hard limit of 200 call queues assigned per user.
- There's a limit of 200 agents per call queue. For more information, please see [Create a Call queue in Microsoft Teams](aa-cq-setup-call-queue).

To learn more about Call queues and Auto attendants, see [Plan for Teams Auto attendants and Call queues](aa-cq-plan-overview).

Your users can find information on using the Queues app with [Use the Queues app for Microsoft Teams](https://support.microsoft.com/office/370ad83e-c2c1-4a9f-8a59-16c98be102e9).

## Configure users for Queues app

### Licensing

Users must have a Teams Phone and a Teams Premium license to use Queues app. Once a user is licensed for Teams Premium, it can take up to 48 hours for Queues app to be available in the Teams client.

For more information on Teams Phone, see [What is Teams Phone](what-is-phone-system-in-office-365). For more information on Teams Premium, see [Microsoft Teams Premium – Overview for admins](enhanced-teams-experience) and [Teams Premium licensing](teams-add-on-licensing/licensing-enhance-teams).

### Prerequisites

Queues app is enabled by default for all Teams users in your organization who are assigned both a Teams Premium and Teams Phone license and who are voice enabled.

As an IT admin, you can manage Queues app settings and designate *authorized users* to perform various actions such as adding and removing queue members, changing call handling flows, configuring auto attendant greetings, and more. For users who need additional capabilities to manage day-to-day operational changes, such as team leads, you must set up a voice applications policy and assign this policy to authorized users. You can allow authorized users to control call queue membership, auto attendant and call queue greetings, call routing rules, and auto attendant hours of operation.

By utilizing multiple voice application policies, you can assign different levels of permissions that reflect the configuration changes you want to allow authorized users to make to auto attendants and call queues. For example, you could have one voice application policy that allows the "team supervisor" to have access to both real-time and historical reporting and another policy for "shift leads" that allows access to real-time reporting and the ability to opt agents in and out of call queues.

For information on authorized users, see the following articles:

- [Plan for Auto attendant and Call queue authorized users](aa-cq-authorized-users-plan)
- [Set up Auto attendant and Call queue authorized users](aa-cq-authorized-users)
- [Manage voice applications policies in Teams](aa-cq-manage-voice-applications-policies)

For a list of all the Teams voice applications policy configuration and reporting settings, including their definitions, their PowerShell parameters, and their licensing requirements, see [Manage voice applications policies in Teams](aa-cq-manage-voice-applications-policies).

Your users, both queue members and leads, can find information on using the Queues app with [Use the Queues app for Microsoft Teams](https://support.microsoft.com/office/370ad83e-c2c1-4a9f-8a59-16c98be102e9).

## Set up Queues app

Note

You can turn off the Queues app via the Teams admin center. However, doing so also turns off other Microsoft apps like Insights and Tasks. Navigate to **Teams apps** &gt; **Manage apps**. Select **Actions** &gt; **Org-wide app settings** &gt; **Microsoft apps**. Select **Off** and **Save**.

### Step 1: Assign licenses to users in your organization

Queues app is enabled by default for all Teams users in your organization who are assigned both a Teams Premium and Teams Phone license and who are voice enabled.

### Step 2: Assign users, authorized users, and agents to a call queue

In order to use Queues app, your users must be in at least one Call queue. For information on configuring Call queues, see [Plan for Teams Auto attendants and Call queues](aa-cq-plan-overview). For more information on how to add users to a Call queue, see [Create a Call queue](aa-cq-setup-call-queue).

### Step 3: Pin Queues app to Teams (optional)

App setup policies let you customize Teams to highlight the apps that are most important for users in your organization. The apps you set in a policy are pinned to the app bar—the bar on the left side of the Teams desktop client and at the bottom of the Teams mobile clients—where users can quickly and easily access them.

Any user with a Teams Phone and Teams Premium license has access to Queues app and can pin the app on their Teams client. If the app isn’t pinned by you via an app setup policy, your users can still view Queues app in the app bar flyout under **View more apps**.

To automatically pin the Queues app in the Teams client for your users, do the following steps:

1. In the Teams admin center, go to **Teams apps** &gt; **Setup policies**.
2. Select an existing policy or select **Add** to create a new policy.
3. Turn on **User pinning** so that your users can choose to pin the app for convenient access.
4. Under **Pinned apps**, select **Add apps**.
5. Search for **Queues** and select **Add**.
6. Select **Add** and then **Save**.

## Give feedback or report an issue

To send feedback or report an issue, select **Settings and more** (**…**) in Teams, and then choose **Help** &gt; **Give feedback**. Enter your feedback or details about the issue you're experiencing. Indicate at the beginning of your feedback report that you're sending feedback about Queues app so we can easily identify Queues app-related issues.

## Platform support

To view the list of platforms that support this feature, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-queues-app).