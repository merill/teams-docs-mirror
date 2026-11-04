---
layout: Conceptual
title: Call Quality Dashboard (CQD) Frequently asked questions (FAQ) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cqd-frequently-asked-questions
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: mikedav, siunies, gageames, jamp
ms.date: 2026-06-16T00:00:00.0000000Z
ms.topic: faq
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Read frequently asked questions (FAQ) and answers about Microsoft Teams Call Quality Dashboard (CQD).
locale: en-us
document_id: 5de72ba4-417f-b90d-6cf4-1af9fbbce5f1
document_version_independent_id: 94abea2e-541a-3d3c-c9da-f8544bbc98d1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/CQD-frequently-asked-questions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cqd-frequently-asked-questions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/CQD-frequently-asked-questions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
platformId: 4e327a68-8589-e78b-9880-0b23698b93ce
---

# Call Quality Dashboard (CQD) Frequently asked questions (FAQ) - Microsoft Teams | Microsoft Learn

## Frequently asked questions

Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?

Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?

Why can't I see EUII in CQD?

I'm trying to use CQD for usage-type reports and find that some of the data is incomplete--why is that?

Why am I seeing Skype for Business information in CQD when I filtered for Teams only?

Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?

Why do Wi-Fi VPN connections show as Wired instead of Wi-Fi?

I turned on Policy-based Recording in Teams and now Peer-to-Peer calls are marked as Conferences--what happened?

When attempting to configure a CQD report in the Power BI service with an SPN, why do I receive an "invalid credential" error?

### Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?

Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard).

For audio streams, any of the five classifiers (which are calculated for the average based on the length of the call) could be within "good" parameters. It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.

To determine if it was a network problem, look at the delta between the average values for the session and the max values. Max values are the maximum detected and reported during the session.

Here's an example of how to troubleshoot this situation. Let's say you take a network trace during a call. During the first 20 minutes, there are no lost packets, but then you have a gap of 1.5 seconds of packets, and then good for the remainder of the call. The average is &lt;10% (0.1) Packet loss even in a Wireshark trace RTP analysis. What was the Max Packet Loss? 1.5 Seconds in a 5-second period would be 30% (0.3). Did that occur within the 5-second sampling period (maybe or it could be split over the sampling period)?

If network metrics look good in the averages and max values, then look to other telemetry data:

- Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.
- Was the audio device in Half Duplex mode to prevent feedback because of microphones that are too close to speakers?
- Check the Device Half Duplex AEC Event Ratio. Was glitching from a device, such as a microphone, introducing noise or static because of USB Audio drop outs when plugged into a Hub or Docking Station?
- Check the Device Glitches and Microphone glitches event ratios. Was the device itself functioning properly?
- Check the Capture and Render Device Not Functioning Event Ratios.

For more on dimensions and measures available in CQD, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard).

For background noise, check the mute event ratio to see the length of time participants were muted.

Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you're interested in. A user reporting the issue might not be the one that was having the issue. They're just reporting the experience.

The telemetry doesn't necessarily call out the issue, but it can help you better understand where to look and inform your decisions. Is it network, device, driver or firmware updates, usage, or user?

### Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?

To compute call count and user count measures, a distinct count if operation is performed against the call or user identifiers in the data set. On large data sets, there's an up to 0.2% error inherent with the distinct countif operation. For the most accurate volume, you should rely on stream count measures since they don't rely on this distinct countif operation. Filtering to reduce the data volume can reduce the error but it may not eliminate this source of error in distinct call and user counts. For more information, see [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard).

### Why can't I see EUII in CQD?

These admin roles can access CQD, but they can't view EUII (end-user identifiable information):

- Microsoft 365 Reports Reader
- Teams Communications Support Specialist

Additionally, users assigned to one or more [Administrative Units](/en-us/azure/active-directory/roles/administrative-units) don't see EUII, even if their role ordinarily allows it.

To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard#assign-admin-roles-for-access-to-cqd).

### I'm trying to use CQD for usage-type reports and find that some of the data is incomplete -- why is that?

Call quality management tools like CQD, Teams admin center, and CallRecord Graph API are based on diagnostic telemetry. The information we show in Teams call quality management tools is only as complete as the telemetry data we receive from clients participating in a call. There are several reasons why we might not receive complete telemetry such as network outages, or [firewall or proxy misconfigurations](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges). We're continuing to work to improve the reliability and resiliency with which Teams clients deliver telemetry to the service.

With that in mind, we don't support the use of call quality management tools for usage reporting. They aren't designed to accommodate nor are they intended for these types of reporting scenarios. Many usage statistics aren't and won't be available within these tools. Teams Admin Center offers a series of [Usage Reports](teams-analytics-and-reports/teams-reporting-reference), and a [Meeting Attendance Report](teams-analytics-and-reports/meeting-attendance-report) is available directly from the Teams client.

### Why am I seeing Skype for Business information in CQD when I filtered for Teams only?

When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams. If the *second endpoint* is Skype for Business, that information shows up in your CQD report. Depending on customers’ scenarios, CQD might include Skype for Business Server 2019 calls when [Call Data Connector](/en-us/skypeforbusiness/hybrid/plan-call-data-connector) is configured. It might also include Skype Bot calls (AA, CVI, VDI), Live Events, and Public Switched Telephone Network (PSTN) calls.

It's possible to remove Skype for Business information from your queries by filtering on dimensions such as *First User Agent Category* and *Second User Agent Category*. You can also use \*User Agent Category Pair, which combines the First and Second dimensions into a single filter.

### Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?

CQD is designed for summarized data queries, and isn't designed for data export. We recommend restructuring your reports, where possible, to not exceed the 10,000 row limit. Start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, and so on. From there, you can drill down into increasingly higher-cardinality dimensions. The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.

### Why do Wi-Fi VPN connections show as Wired instead of Wi-Fi?

This behavior is expected. The VPN vendor created a virtual ethernet adapter that is treated like a wired connection. Since it's not properly labeled, the operating system doesn't know it's a Wi-Fi connection and reports it as wired.

### I turned on Policy-based Recording in Teams and now Peer-to-Peer calls are marked as Conferences--what happened?

This behavior is expected when Policy-based Recording is enabled in Microsoft Teams. Policy-based Recording uses a Teams Recorder Bot deployed in Microsoft Azure to capture meeting contents for compliance purposes. In call quality management, "peer-to-peer" is a description of the flow of media traffic, not the interaction between the users. Because a Recorder Bot is itself a party to the call, the call is no longer peer-to-peer, but a multi-party call. Microsoft Teams classifies Multi-party calls as Conferences. Therefore CQD and other call quality tools indicate as such calls as Conferences.

### When attempting to configure a CQD report in the Power BI service with an SPN, why do I receive an "invalid credential" error?

CQD and the CQD Power BI reports support OAuth user authentication only. Authentication using Service Principals (SPNs), Managed Identities, or other non-user authentication methods is not supported. Users must authenticate with a Microsoft Entra ID user account that has the appropriate permissions to access CQD data.