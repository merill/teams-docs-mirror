---
layout: Conceptual
title: Monitor Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-monitor-and-troubleshoot
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: filippse
ms.date: 2026-09-10T00:00:00.0000000Z
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- NOCSH
description: Learn how to monitor and troubleshoot Direct Routing configuration, including Session Border Controllers, Direct Routing components, and Telecom trunks.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 99036b5e-f358-fda3-d9b1-1279952b59a5
document_version_independent_id: 9ea42c59-7db5-9c66-ef58-98b4909ccd10
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-monitor-and-troubleshoot.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-monitor-and-troubleshoot
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-monitor-and-troubleshoot.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 3c23638a-6188-ecde-eb0e-e91d30e01cb3
---

# Monitor Direct Routing - Microsoft Teams | Microsoft Learn

This article describes how to monitor and troubleshoot your Direct Routing configuration.

The ability to make and receive calls by using Direct Routing involves the following components:

- Session Border Controllers (SBCs)
- Direct Routing components in the Microsoft Cloud
- Telecom trunks

If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.

Microsoft is working on providing more tools for troubleshooting and monitoring. Check the documentation periodically for updates.

## Troubleshoot Direct Routing

To troubleshoot Direct Routing, see [Diagnose issues with Direct Routing](/en-us/MicrosoftTeams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

## Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages

Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health. There are no actions required from the tenant administrator to enable the SIP options monitoring. The collected information is taken into consideration when routing decisions are made.

For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.

The following diagram shows an example of the configuration:

![SIP options configuration example.](media/sip-options-config-example.png)

When a user makes a call to number +1 425 &lt;any seven digits&gt;, Direct Routing evaluates the route. There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com. Both SBCs have equal priority in the route. Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.

An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.

When a call is made, the following logic applies:

- The SBC was paired at 11:00 AM.
- The SBC sends options at 11:01 AM, 11:02 AM, and so on.
- At 11:15, a user makes a call and the routing mechanism selects this SBC.

Direct Routing takes the regular interval options three times (the regular interval is one minute). If options were sent during the last three minutes, the SBC is considered healthy.

If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it's considered healthy. If not, the SBC will be demoted from the route.

Demotion means that the SBC won't be tried first. For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.

If sbc1.contoso.com doesn't send SIP options on a regular interval as previously described, it's demoted. Next, sbc2.contoso.com tries for the call. If sbc2.contoso.con can't deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.

If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.

## Monitor Call Quality Analytics dashboard and SBC logs

In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.

You can use the following tools to monitor your configuration:

- Call Quality Dashboard
- SBC logs

The Direct Routing service has descriptive error codes reported to either Call Analytics or the SBC logs.

The Call Quality Dashboard provides information about call quality and reliability. To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/en-us/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).

In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.

![Sample SIP code for call failure.](media/failed-response-code.png)

However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail. In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics won't help. In this case, refer to the SBC logs. Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.