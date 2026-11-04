---
layout: Conceptual
title: Teams Silent Testing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-silent-testing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: guypaskar
author: PeerDiego
manager: hadarweiss
f1.keywords:
- NOCSH
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: meetings
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Hybrid
- M365-email-calendar
ms.date: 2026-07-06T00:00:00.0000000Z
description: Learn about Teams Silent Testing.
locale: en-us
document_id: 493603ae-dce3-4aa6-6ad1-2c596a17a399
document_version_independent_id: 493603ae-dce3-4aa6-6ad1-2c596a17a399
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-silent-testing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-silent-testing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-silent-testing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 880bff2b-a2cb-a7de-3c4e-e2bd531dc608
---

# Teams Silent Testing - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](enhanced-teams-experience) for meetings and are included with Teams Enterprise for events.**

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

## Overview

The **Teams Silent Testing** feature enables IT admins of Microsoft Teams to schedule and simulate tests between users of a subnet in their organization and Microsoft Calling Servers. Teams Silent Testing consists of two distinct test types:

- **Silent Test Calls**: Simulate standard Teams calls to test call quality and network performance.
- **Silent Test Town halls**: Simulate large-scale events to test broadcast capabilities and network capacity. This feature applies to Teams events [optimized for large audiences](plan-events).

This feature enables proactive monitoring of call quality and network monitoring by having tests run according to the schedule set silently in the background without interrupting users. Once a test is run, IT admins can view a report detailing call quality and potential issues so proactive measures can be taken to help improve the end-user calling, meeting, and event experience.

### Why Silent Test?

Existing monitoring tools (Call Quality Dashboard (CQD), Real-Time Monitoring, Alerts) are reactive; they detect issues after users experience them. Teams Silent Testing offers **proactive monitoring**, allowing IT teams to detect and address network issues before they affect users.

Imagine scenarios such as:

- **Network Changes**: You update your network firewall rules or Wi-Fi configurations. Running Silent Tests helps validate performance proactively before users report issues.
- **New Location Setup**: You launch a new office location. Even with only a few Teams clients available, Silent Tests can provide early indicators of network readiness.
- **Routine Health Checks**: Scheduling daily or weekly Silent Tests allows continuous monitoring to catch degradations early, reducing the risk of outages impacting end users.

By integrating Teams Silent Testing into your operational routines, you can detect and resolve potential issues proactively, ensuring better reliability and user satisfaction.

#### Key points

**General characteristics (both test types):**

- Tests run silently in the background on the Teams client at scheduled times.
- Tests target a specific subnet.
- Tests run only on the desktop client - Windows and macOS.
- Tests only run if the device is idle (user isn't in an active Teams call).
- No user experience disruption: no notifications, sounds, or visible changes.

**Silent Test Calls:**

- Call tests run for 60 seconds on users' machines in the background.

**Silent Test Town halls:**

- Town hall tests can be configured to run up to 180 minutes.

**Endpoint requirements:**

- Device must be located in the targeted subnet.
- Teams client must be installed and running.
- Device must be powered ON.
- User must not be on an active Teams call.
- Teams user signed in to the device must have a Teams Premium license for Silent Test Calls. Silent Test Town halls is included with Teams Enterprise.

## Networking requirements

For Silent Testing to work properly, your network infrastructure must meet specific requirements to ensure successful communication with Microsoft Teams services. The following external connections are required to be accessible:

| Hostname | Ports | Protocol | Description |
| --- | --- | --- | --- |
| \*.ecdn.teams.microsoft.com | 443 | HTTPS/WebSocket over TCP | Silent Test scheduler |
| \*.ecdn.teams.cloud.microsoft | 443 | HTTPS/WebSocket over TCP | Unified domain |

Important

As part of the [Unified Domains](/en-us/microsoft-365/enterprise/cloud-microsoft-domain) initiative, domains are transitioning from `*.teams.microsoft.com` to `*.teams.cloud.microsoft`. Both domains are required during the transition period to ensure uninterrupted service.

## Licensing details

- Silent Test Calls is a Teams Premium feature. Silent Test Town halls is included with Teams Enterprise.

## How to schedule a Silent Test

Teams Silent Tests can be scheduled via the **Teams Admin Center**.

To schedule tests, you must have either the Global Admin or Teams Admin role.

1. In the left navigation of the Teams admin center, go to **Analytics & reports** &gt; **Silent Tests**.
2. Select **Schedule Test**.
3. Select **Town hall** or **Meeting** (for Call)
4. Fill out the form:

    - **Test name**
    - **Target subnets** - Multiple subnets can be entered comma separated. Subnet IDs must be in valid CIDR format. For example, 192.168.1.0/24. Only IPv4 is currently supported.
    - **Frequency** - Once only, Daily, Weekly, etc.
    - [Town hall only] **Maximum participants**
    - [Town hall only] **Duration**
    - **Start date and time**
5. Save the schedule.
6. View scheduled tests at the bottom of the page. You can **edit** or **abort** existing schedules if necessary.

## How to view Silent Test reports

The method for reviewing results differs depending on the test type.

### Silent Test Calls

On the Silent Test Calls page, select **Download Report** to download a Power BI report file.

When a test is completed, open the Power BI report, sign in with your admin credentials, and choose the subnet/test name to view a report.

If you don't have Power BI set up, see the following articles to learn how to download and configure it:

- [Set up CQD Power BI Connector](/en-us/microsoftteams/cqd-power-bi-connector)
- [CQD Power BI Query Templates](/en-us/microsoftteams/cqd-power-bi-query-templates)

#### Reports

When you first open the Power BI report, you see an overview of your results from using Silent Test Calls.

[![Screenshot that shows the Silent Test report.](media/doppler/silent-testing-report.png)](media/doppler/silent-testing-report.png#lightbox)

As you select data points such as subnet or building name, the report changes to reflect that scope.

[![Screenshot that shows the filtered Silent Test report.](media/doppler/silent-testing-report-filtered.png)](media/doppler/silent-testing-report-filtered.png#lightbox)

### Silent Test Town halls

Silent Test Town hall performance can be viewed in the Microsoft eCDN Analytics pages.

Performance data can be viewed in the Analytics dashboards shortly after the test begins.

For more information on how to read the analytics, see the following articles:

- [Microsoft eCDN analytics overview](/en-us/ecdn/technical-documentation/analytics)
- [Microsoft eCDN drilldowns analytics overview](/en-us/ecdn/technical-documentation/drilldowns)