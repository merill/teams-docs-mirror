---
layout: Conceptual
title: Use Power BI to analyze CQD data for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cqd-power-bi-query-templates
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: siunies, jamp
ms.date: 2026-08-03T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- remotework
- Tier1
- ContentFreshnessFY24
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
description: Use Quality of Experience (QER) Power BI templates to analyze CQD data for Microsoft Teams.
locale: en-us
document_id: dfbb1a90-d5f1-217e-1880-59afe121d979
document_version_independent_id: 7f6c85ae-f2c6-4b0b-6c8a-9bfcbe394328
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/CQD-Power-BI-query-templates.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cqd-power-bi-query-templates
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/CQD-Power-BI-query-templates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d3197845-b4ce-44c6-a237-cd4be160e76c
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/aea905fb-0a9d-4d46-b30f-e9cbaf772d1b
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 13d05388-17df-3776-bf0d-342d9660e853
---

# Use Power BI to analyze CQD data for Microsoft Teams - Microsoft Teams | Microsoft Learn

The Quality of Experience (QER) template is available in the [Power BI query templates for CQD download](https://www.microsoft.com/download/details.aspx?id=102291). The QER is a powerful reporting template that supersedes the original CQD Power BI query templates released in 2020. While the original templates remain available for demonstration purposes, they're no longer supported or updated and we recommend customers switch to the QER template, which continues to receive updates. The CQD Teams Auto Attendant & Call Queue Historical Reports have been replaced with the new [Auto Attendant & Call Queue Historical Report](aa-cq-report-historical) which continues to receive updates.

For Call Quality Dashboard (CQD) reports in Teams, if you'd rather use Power BI to query and report your data, download our CQD Power BI templates. When you open the templates in Power BI, you're prompted to sign in with your CQD admin credentials. You can customize these query templates and distribute them to anyone in your organization who has a Power BI license and CQD admin permissions.

Before you can use these Power BI Template (PBIT) files, you must [Install the Power BI Connector for Microsoft CQD](cqd-power-bi-connector) using the *MicrosoftCallQuality.pqx* file included in the [download](https://www.microsoft.com/download/details.aspx?id=102291).

Make sure you have the right [CQD access role](turning-on-and-using-call-quality-dashboard#assign-admin-roles-for-access-to-cqd) to access the Power BI reports.

## Templates

The following templates are available in the [Power BI query templates for CQD download](https://www.microsoft.com/download/details.aspx?id=102291).

| Pbit | Description |
| --- | --- |
| QER.pbit | The Quality of Experience Report (QER) template empowers customers to proactively identify issues that are impacting the Teams meeting and calling experience before they escalate. Reports are also provided to enable administrators to respond quickly to escalating issues and help answer the question, "What happened during the meeting?" This template provides the following reports:<br>- Search – enables searching by Meeting URL, Conference ID, Subnet, or UPN.<br>- Meeting Health Details – detailed metrics for a single meeting.<br>- User Health Details – detailed metrics for a single user.<br>- Media Health – high level overview of Key Health Indicators (KHI) for overall tenant meeting and calling health.<br>- Media Setup – analyze media setup failures.<br>- Media Reliability – analyze media reliability issues.<br>- Audio/Video/Sharing Health – review mid-level KHIs for audio, video, or sharing health.<br>- Audio/Video/Sharing Health Details – review detailed metrics on audio, video, or sharing health.<br>- VPN – review the impact of VPN on meeting health. (Estimated or Mapped VPN)<br>- Top 10 Reports – identify problem areas in your tenant.<br>- Dailies – review daily report of KHIs.<br>- Usage – general meeting and calling usage.<br>- User Feedback – review user survey feedback, also known as Rate My Call.<br>- Transport – identify networks that are blocking UDP.<br>- Devices – review the impact of devices.<br>- Clients - review client focused metrics.<br>- Building Data – review the building data file in CQD.<br>- PSTN Health and User Details – two reports that provide a high level summary and individual user health for PSTN based calls.<br>- Network Metrics – two reports that display raw network metric details for jitter, packet loss, and latency.<br>- Teams Events Overview **NEW!**– high level overview of health for Teams Events.<br>- Event Health Details **NEW!** – detailed metrics for a single Event, including network metrics for presenters and attendees.<br>- VDI Clients **NEW!** – review VDI client focused metrics.<br>- New Teams Usage **NEW!** – review the media usage for the new Teams client.<br><br> This template is provided on an as-is basis, and supersedes the deprecated templates as indicated below. |
| QER MTR.pbit | Part of the Microsoft Teams Optimized Experiences report package, this template is optimized for analyzing quality and reliability for Microsoft Teams Rooms (Windows & Android) deployments, and includes the following reports: <br>- Overview<br>- Network<br>- Device Health Details<br>- Meeting Health Details |
| QER PS.pbit | Part of the Microsoft Teams Optimized Experiences report package, this template is optimized for analyzing Microsoft Teams Phone deployments, including those environments using Direct Routing, and includes the following reports: <br>- Direct Routing Reports<br>    - SBC Overview<br>    - SBC Details<br>    - User Details by SBC<br>- Phone System Reports<br>    - PSTN Overview<br>    - PSTN User Overview<br>    - PSTN User Details<br>    - PSTN Clients<br>    - PSTN Devices |
| CQD Teams Usage Report.pbit | Shows how users in your organization are using Teams and how much. Make sure you upload the building data to maximize your reporting experience. To learn more, read [Use CQD Power BI report to view Microsoft Teams utilization](cqd-teams-utilization-report). |

## Legacy templates

The following templates are deprecated and no longer maintained. We recommend moving to the newer Quality of Experience (QER) templates going forward.

| Pbit | Description |
| --- | --- |
| CQD PSTN Report.pbit *(Deprecated)* | Example template that provides insights specific for PSTN calls including calls that go through Direct Routing. To learn more, read [Using the CQD PSTN Report](cqd-pstn-report). |
| CQD Helpdesk Report.pbit *(Deprecated)* | This template integrates building and personal data and demonstrates how to build a report to enable drill through from a single user to find the upstream root cause of poor call quality for that user (for example, the user is in a building that's experiencing network problems). |
| CQD Location Enhanced Report.pbit *(Deprecated)* | This example template re-imagines the CQD SPD location reports. Includes nine reports, providing Call Quality, Building WiFi, Reliability, and Rate My Call (RMC) information with additional drill-throughs by Building or by User. Make sure you upload the building data to maximize your reporting experience. |
| CQD Mobile Device Report.pbit *(Deprecated)* | This example template provides insights specifically for mobile device users, including Call Quality, Reliability, and Rate My Call. View mobile network, WiFi network, and mobile operating system reports (Android, iOS). |
| CQD Summary Report.pbit *(Deprecated)* | A demonstration of how CQD combined with Power BI can provide better visualizations, improved presentation, increased information density, and rolling dates. These reports make it easier to identify outliers. Drill into call quality by location with an easy-to-use interactive map. Nine new reports:<br>- Quality Overall<br>- Reliability Overall<br>- RMC (Rate My Call) Overall<br>- Conference Quality<br>- P2P Quality<br>- Conference Reliability<br>- P2P Reliability<br>- Conference RMC<br>- P2P RMC |
| CQD User Feedback (Rate My Call) Report.pbit *(Deprecated)* | Demonstration of a Power BI report using Rate My Call data in a way that you can easily use to help support calling for your organization. Cross-reference with verbatims to identify end user education opportunities. |
| CQD Teams Auto Attendant & Call Queue Historical Report | All customers should now use the new [Auto Attendant & Call Queue Historical Report](aa-cq-report-historical), available for download separately. |

Tip

Once you set up your Power BI reports for CQD data, add them as a tab to a channel. After you select **+** in a channel, select **Power BI** and then find your report. To learn more, read [Embed report with the Power BI tab for Teams](/en-us/power-bi/service-embed-report-microsoft-teams). Remember, only people with a Power BI license and CQD admin credentials can access these reports.

Important

Using CQD reports in Power BI require interactive OAuth authentication using a user account. Service Principals (SPNs) and Managed Identities cannot be used to authenticate against the CQD API and are not supported for Power BI service report access or refresh scenarios.