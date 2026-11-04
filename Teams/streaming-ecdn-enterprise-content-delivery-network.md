---
layout: Conceptual
title: Enterprise content delivery networks for streaming Microsoft Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/streaming-ecdn-enterprise-content-delivery-network
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.topic: concept-article
ms.service: msteams
ms.subservice: teams-events
audience: admin
ms.date: 2026-10-06T00:00:00.0000000Z
ms.collection:
- M365-collaboration
- m365initiative-meetings
ms.reviewer: gaurav.chawla, nguyendavid
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: 
description: Learn about scale video delivery and enterprise content delivery networks (eCDNs) for Microsoft Teams streaming events.
locale: en-us
document_id: e1cd8ee0-0f3b-4c25-1221-305bd18e557a
document_version_independent_id: e1cd8ee0-0f3b-4c25-1221-305bd18e557a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/streaming-ecdn-enterprise-content-delivery-network.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: streaming-ecdn-enterprise-content-delivery-network
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/streaming-ecdn-enterprise-content-delivery-network.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
platformId: 35670f54-dd75-0fcb-bc2b-29414f742ab2
---

# Enterprise content delivery networks for streaming Microsoft Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Live events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

Teams streaming events can use enterprise content delivery networks (eCDNs), including the Microsoft eCDN and eCDNs from Microsoft partners. Teams streaming events include:

- Teams events [optimized for large audiences](plan-events), such as town halls.
- Live events.

Video playback from Microsoft Teams events uses adaptive bitrate streaming (ABR), which is delivered as a unicast stream. Every viewer gets their own video stream from the internet. For events or videos sent out to large portions of your organization, there could be a significant amount of network and internet bandwidth consumed by viewers.

Video playback from Microsoft Teams events uses adaptive bitrate streaming (ABR) delivered as a unicast stream. This means that each viewer gets their own video stream from the internet. For events or videos sent out to a large portion of your organization, this can result in viewers consuming significant network and internet bandwidth.

As an admin, you might want to understand and reduce the network traffic for events and popular videos. If so, you can enable Teams to integrate with Microsoft’s enterprise content delivery network (eCDN). Microsoft eCDN includes capabilities like real-time monitoring and in-depth network analytics. You can also choose to use an eCDN solution from our trusted partners. These eCDN platforms let you monitor, scale, and optimize the distribution of video streams (and sometimes other content types) across your enterprise network.

## Teams events

Microsoft eCDN is the default for Teams events [optimized for large audiences](plan-events), such as town halls. You can also choose an eCDN solution from one of our partners.

Without Microsoft eCDN, event organizers might not be able to access some future features that require this eCDN solution.

If you want your event organizers to use your chosen eCDN provider, see the Manage the eCDN solution for Teams events section in this article.

## Microsoft eCDN

**Microsoft eCDN** solves the network congestion problem that occurs during large corporate virtual events such as all-hands meetings. Microsoft eCDN forms a mesh network over the LAN, reducing the load by up to 98%. With WebRTC as its foundation, Microsoft eCDN eliminates the need for any software or hardware installations. Microsoft eCDN is included with Teams Enterprise.

- Microsoft eCDN works out of the box without any configuration. The network configuration for Microsoft eCDN ensures that remote workers and/or heavy video traffic doesn't strain your network nor oblige you to invest in costly infrastructure. It includes automatic site detection, automatic VPN detection, and automatic NAT/firewall traversal. To learn more, see [How to enable Microsoft eCDN](/en-us/ecdn/how-to/enable-microsoft-ecdn-for-your-tenant).
- Silent Testing with Microsoft eCDN allows admins to simulate large events on their corporate network, allowing thorough and nondisruptive testing and troubleshooting before a real event. To learn more, see [Perform a silent test](/en-us/ecdn/how-to/perform-silent-test).
- Industry-leading analytics from Microsoft eCDN provide granular analyses and allow admins to quickly find the root cause for any streaming issue. Your toolkit includes delivery and UX metrics, advanced drill downs, and per-user analytics. Learn more at [Analytics](/en-us/ecdn/technical-documentation/analytics).

## Acquire and set up your eCDN solution outside of Teams

Get expert help with monitoring and scaling video delivery by teaming up with trusted Microsoft eCDN partners. Before you can enable an eCDN solution to use with Teams, you must purchase and set up that eCDN solution outside and separate from Teams. To ensure that the solution meets your needs, some partners provide free trials of their content delivery and network analytics technologies. Several eCDN solutions are preintegrated and can be enabled for use with Teams. See information about the providers in the next section.

### Hive Streaming

Hive Streaming enables superior video experience (VX) to drive change in the enterprise by maximizing the reach and quality of internal video communications. Hive’s next-generation VX products are designed to empower companies before, during, and after each internal live video stream by enabling stakeholders across the organization to:

- **Pressure-test the network** and the entire video infrastructure chain to secure events
- Access advanced stream control features, such as **modifying stream bitrate in real time**
- Receive and **act on disruption alerts during live video events**
- Get **enhanced and actionable analytics** individually tailored to IT or Communications stakeholders
- Gain unique **insights into video performance, viewer experience, and engagement**
- Unlock **advanced eCDN capabilities to address weak network links globally** with an elegant software-only solution that eliminates the need for edge caching at low bandwidth sites

Hive’s ingenious peer-to-peer algorithm helps achieve the highest streaming quality while efficiently offloading the corporate network with up to 99% bandwidth savings. Hive’s VX solutions work out of the box and are 100% software-based, requiring nothing but viewer machines to reliably deliver video to even the most bandwidth-restricted sites. With a stellar track record of 99.99% service uptime, Hive Streaming offers 24/7 top-tier support. It also provides comprehensive Service- and Experience-Level Agreements. Hive Streaming plays an integral role in the video experience and networking infrastructure of Fortune 500 companies across the globe. For more information, visit [Hive Streaming](https://www.hivestreaming.com/partners/microsoft).

### Kollective

**Kollective Technology** is a cloud-based, content distribution platform that uses intelligent peering to deliver live and on-demand enterprise video, providing 100% video quality and 100% engagement at just 1% of the bandwidth. Kollective’s integration with Teams events allows globally dispersed employees to easily consume video, improving employee communication, boosting overall engagement, and increasing training and retention opportunities. **Kollective IQ** is a sophisticated, user-friendly analytics platform for Microsoft Stream. With customizable reporting, visualizations, and dashboards, it's easy to quantify and digest both user experience and engagement across complex global enterprise networks. Communication managers and network administrators can watch real-time events and network activity, so bottlenecks can be addressed quickly, ensuring peak network performance. To learn more about these options, see [Kollective eCDN for Microsoft](https://kollective.com/microsoft-live-events/).

### Ramp

**Ramp eCDN** reduces network bandwidth consumption by 90% or more when streaming events and video on demand (VOD). Use Ramp to mix and match any combination of eCDN technologies—multicast, caching, and peer-to-peer networking. With centralized management, monitoring, and insightful analytics, you gain visibility and control over network performance, creating the highest-quality viewer experience.

- **Ramp Multicast+** is the most efficient way to stream live video. Using the multicast protocol, you only consume the bandwidth required for one viewer, whether you have 100, 10,000, or 100,000 viewers. Learn more at [Ramp Multicast+](https://www.rampecdn.com/altitudecdn/multicast/).
- **Ramp OmniCache™** is video-specific caching software that uses local caches to serve live and VOD video to nearby audiences, drastically reducing the number of video streams traveling across your internet connections and WAN links. Learn more at [Ramp OmniCache](https://www.rampecdn.com/altitudecdn/video-cache/).
- **Ramp Peer-to-Peer (P2P)** lets you optimize bandwidth even at locations with limited infrastructure. P2P builds a peer network of client devices watching the same content to redistribute the video streams from one viewing device to another. Learn more at [Ramp P2P](https://www.rampecdn.com/altitudecdn/p2p/).

Note

Your chosen eCDN solution is subject to the selected partner eCDN provider’s terms of service and privacy policy, which will govern your use of the eCDN provider’s solution. Your use of the eCDN provider’s solution won't be subject to the Microsoft volume licensing terms or Online Services Terms. If you don't agree to the third-party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.

## Configure your eCDN solution

Follow these steps to configure your eCDN solution:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; [**Live events settings**](https://admin.teams.microsoft.com/broadcasts/settings).
2. Turn the **Video distribution provider** toggle **On**.
3. Choose an **eCDN/SDN provider** from the **Video distribution provider** dropdown list.
4. Fill out the other fields as directed by your solution provider (some solution providers don't use all the fields).
5. Select **Save**. It might take up to 24 hours to see your changes.
6. To check whether your setup is correct, select **Verify setup**.
    - Search for any video in your organization to validate with.
    - If your eCDN provider is set up correctly, you see a **Success** message on the verify setup tool.
    - If you aren't set up correctly, you see a **Failure** message. Copy the event message to share with your provider for troubleshooting.

## Manage the eCDN solution for Teams events

Microsoft eCDN is the default for organizers in events optimized for large audiences. You can manage whether your organizers use the Microsoft eCDN solution or one of our partner eCDN solutions.

| Teams admin center policy option | Parameter value in PowerShell | Behavior |
| --- | --- | --- |
| On | $true | **This is the default value.** Event organizers with this policy use Microsoft eCDN. |
| Off | $false | Event organizers with this policy use your chosen partner eCDN solution. These organizers might not have access to some future event features. |

### Using the Teams admin center

To manage which eCDN solution your organizers use for events by using the Teams admin center, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. Turn the **Use Microsoft eCDN** toggle **Off**.
4. Select **Save**.

### Using PowerShell

To manage which eCDN solution your organizers use for events by using PowerShell, use the **`-UseMicrosoftECDN`** parameter within [**CsTeamsEventsPolicy**](/en-us/powershell/module/teams/set-csteamseventspolicy).

To allow event organizers to use a partner eCDN solution, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -UseMicrosoftECDN $false
```

## Configure Teams production type events through Teams and Viva Engage for your eCDN solution

If you plan to create Teams events through Teams or Viva Engage, you need to [configure your eCDN provider to be integrated with Microsoft Teams](teams-live-events/what-are-teams-live-events#enterprise-content-delivery-network-ecdn) as well.

### Get to video analytics reports for your eCDN solution

As noted earlier in this article, some eCDN solutions also provide analytics reports that give deeper information about playback sessions, viewers, and quality of service. If your provider gave you an analytics report URL template during the setup in the Teams admin center, then video or event owners can effortlessly access the analytics report for any specific video or event. Owners of videos can see an Analytics tab directly under the video. On this tab, there's a link for owners to access the analytics report for this specific video in the eCDN provider's system. If you're a Teams admin, you can access the Analytics tab and view the eCDN analytics report link, even without ownership of the live event or video.

1. As a Teams admin, go to the video player page.
2. Select **Settings**.
3. Select **View in admin mode**.
4. Select the **Analytics** tab.

## Troubleshooting issues

Make sure that your eCDN solution is set up correctly in your network and that you properly configure Teams to enable the provider per their instructions and specific configuration strings. If you're still having issues, some of the information in the next section might help.

### Verify setup tool

If you're having issues with your eCDN solution, you can always come back and run the **Verify setup** tool. The eCDN provider event messages shown for your test video can give you and your eCDN provider more information on what's not working.

Go to **Settings** &gt; **Admin Settings** &gt; **eCDN provider** &gt; **Verify setup**.

### Disable eCDN for a specific session via URL query string

To determine if an issue you're seeing is with the eCDN solution or with Teams, you can easily disable the eCDN solution for a specific playback session via query string.

- If your playback URL already has a question mark, **?**, in it, then add **&disableSDN=true**.
- If your playback URL doesn't have a question mark, **?**, in it then add **?disableSDN=true**.

### View eCDN info in browser console

If your eCDN solution provider supports it, they might print debug information during initialization of playback through their solution. This extra info could be helpful in determining what is going wrong. You can enable extra console debug messages via the query string.

- If your playback URL already has a question mark, **?**, in it, then add **&isSDNDebug=true**.
- If your playback URL doesn't have a question mark, **?**, in it then add **?isSDNDebug=true**.

Select **F12** on your keyboard when your browser is active and switch to the **Console** tab to see all the information printed during the loading of the page with the isSDNDebug=true query string set on the playback URL.

## Configure a third-party video distribution provider

If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for events in Teams.

### Using the Microsoft Teams admin center

1. In the left navigation, go to **Meetings** &gt; **Live event settings**.
2. Under **Third-party video distribution providers**, complete the following: ![Third-party video distribution provider settings in the admin center.](media/teams-live-events-settings-distribution-provider-new.png)
    - **Third-party distribution provider** Turn this ON to enable the third-party video distribution provider.
    - **SDN provider name** Choose the provider you're using.
    - **SDN Configuration** Enter SDN Configuration details.

### Using Windows PowerShell

Get the license ID or API token and API template from your provider contact. Next, run one of the following, depending on the provider you're using:

#### Microsoft eCDN

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName microsoft
```

#### Hive

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```

#### Kollective

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```

#### Ramp

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/en-us/powershell/module/teams/set-csteamsmeetingbroadcastconfiguration).

Note

Your chosen eCDN solution is subject to the selected third-party provider’s terms of service and privacy policy, which governs your use of the eCDN provider’s solution. Your use of the eCDN provider’s solution won't be subject to the Microsoft volume licensing terms or Online Services Terms. If you don't agree to the third-party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.

## Platform support

To view the list of platforms that support this feature, see [Platform support for Teams events features](events-platform-support).