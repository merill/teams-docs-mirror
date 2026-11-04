---
layout: Conceptual
title: Trunk failover on outbound calls - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-trunk-failover-on-outbound-call
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.reviewer: filippse
ms.date: 2025-05-06T00:00:00.0000000Z
ms.topic: article
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
description: Read this topic to learn how to handle trunk failovers on outbound calls from Teams to the Session Border Controller (SBC).
locale: en-us
document_id: 485ba3d8-4016-aeb6-214c-22645d4ed439
document_version_independent_id: 328e0dac-7821-7607-0d89-8fba7711b11c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-trunk-failover-on-outbound-call.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-trunk-failover-on-outbound-call
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-trunk-failover-on-outbound-call.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fdc44c86-f2d4-79ba-d9b3-29f46681c558
---

# Trunk failover on outbound calls - Microsoft Teams | Microsoft Learn

This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).

## Failover on network errors

If a trunk can't be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter. The datacenter might be located in a different geographical region, outside of your current one. A trunk might not be connected if a connection is refused, if there's a TLS timeout, or if there are any other network-level issues.

For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.

## Failover of specific SIP codes received from the Session Border Controller (SBC)

When a call from a Teams client to the Public Switched Telephone Network (PSTN) is made with the following traffic flow: Teams Client -&gt; Direct Routing -&gt; SBC -&gt; Telephony network, any non-2xx final response code from the SBC can be configured to be retried on another SBC in the voice routing policy. Note that failover will only happen in the absence of non-100 provisional responses from the SBC, to prevent double ringing telephony network.

The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).

Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server couldn't produce a response within a suitable amount of time, for example, if it couldn't determine the location of the user in time. The client MAY repeat the request without modifications at any later time."

This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error. However, there's one more SBC in the route that might be able to reach the callee.

In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call. Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue. By default, the call will be completed at this moment.

![Diagram showing SBC unable to reach PSTN due to network issue.](media/direct-routing-failover-response-codes1.png)

There's one more SBC in the route that can potentially deliver the call. If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried (SBC2.contoso.com in the following diagram):

![Diagram showing routing to second SBC.](media/direct-routing-failover-response-codes2.png)

Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC can't make a call due to network or other issues.

Default values: 408, 503, 504