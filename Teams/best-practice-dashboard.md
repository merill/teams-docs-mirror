---
layout: Conceptual
title: Best practice configurations dashboard for Microsoft Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/best-practice-dashboard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: wlibebe
ms.author: wlibebe
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: snigdha.chaturvedi
ms.date: 2026-07-15T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
description: Learn how to use the Teams Premium usage report in the Teams admin center to know how often users are using each Teams Premium feature.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: ad7ba228-5d15-4da0-b67b-c37d2b507ecd
document_version_independent_id: ad7ba228-5d15-4da0-b67b-c37d2b507ecd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/best-practice-dashboard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: best-practice-dashboard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/best-practice-dashboard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
platformId: 940691ab-554b-8805-e278-06814298b04b
---

# Best practice configurations dashboard for Microsoft Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Events

As an admin, it's important to ensure that your users have a reliable collaboration experience for their Teams meetings. The best practice configurations dashboard for Microsoft Teams meetings helps you manage and monitor your environment for seamless collaboration.

This dashboard provides you with best practice configurations, the effect of your current settings, and actions you can take to follow Microsoft's recommendations. The dashboard highlights locations that don't follow Microsoft's recommended best practices. When you follow recommended actions, the trend of locations not adhering to best practices is tracked to help monitor progress. All monitored areas are evaluated over a period of seven days.

## Access the best practice configurations dashboard

In the left navigation of the Teams admin center, go to **Meetings** &gt; **Best practice configurations**.

[![Screenshot that shows the overall Dashboard](media/best-practice-dashboard/dashboard.png)](media/best-practice-dashboard/dashboard.png#ligthbox)

The **Summary** widget displays the number of best practices that need action and the number without issues.

The **Best practice configurations** table provides statuses and insights for the following best practices:

- Enable the correct ports and protocols
- Update outdated Teams clients
- Implement split tunneling for VPNs
- Bypass cloud proxy
- Bypass local proxy
- Address DNS resolution failures
- Optimize for virtual desktop environment (VDI)

    To view a detailed dashboard with recommendation, select a best practice from a row in this table. A list of IP addresses is shown for each city, displaying the extent to which each location follows best practices. You can use the name of the city, country/region, or the IP address to search and filter for locations. You can also export the dashboard's table in a CSV file that you can share.

## Interpret the dashboards

The following sections provide details on the information in each best practice configuration's dashboard. Each dashboard is grouped by countries/regions, cities, and public IP addresses to identify systemic issues affecting your organization. These broader categories allow efficient detection and resolution of widespread problems impacting multiple users within a specific region or network segment, quickly identifying patterns and trends that indicate underlying issues, instead of trying to pinpoint every individual affected user.

### Update outdated Teams clients

For the best meeting experience, your users should always use the latest version of Teams. The media streams in this dashboard show when Windows and Mac users are on a client build that's more than three months old, which can negatively affect meeting quality. The outdated Teams clients dashboard monitors desktop clients (Windows and Mac) across the organization and highlights the locations most impacted by outdated Teams clients. To learn more about Teams updates, see [Why it's important to keep Teams updated](teams-client-update#servicing-agreement).

To view outdated Teams clients, select **Update outdated client versions** in the **Best practice configurations** table.

[![Screenshot of the Best practice configuration's outdated Teams clients dashboard.](media/db-clients-small-1.png)](media/db-clients-expand-1.png#lightbox)

| Callout | Description |
| --- | --- |
| **1** | **Client versions trend** - Trend of cities with supported and outdated Teams clients. |
| **2** | **Recommended action** - Actions you should take to meet the recommended best practice configurations. |
| **3** | **Regions with out-of-date clients** - Visual map that includes a date for when this dashboard was generated and a count of cities with outdated clients. You can also search by country, city, and region. |
| **4** | The table provides the following data: <br>- **Cities** - Cities and regions impacted.<br>- **Public IPs (reflexive)**- Public IPs of users on outdated clients.<br>- **Percentage of out-of-date clients** - Percentage of streams coming from outdated versions of the Teams client.<br>- **Number and percentage of streams** - Count of media streams coming from outdated clients.<br>- **Status: Action required** - You must follow Microsoft's recommended actions to update the status. |
| **5** | You can use these buttons to: <br>- Export the table to a CSV file.<br>- Filter by city, public IP address, and status.<br>- Toggle the map view on or off.<br>- Manage settings for columns in the table. |

### Implement split tunnelling for VPNs

For reliable Teams connectivity, network administrators should enable a [direct connection for VPN users](/en-us/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) (split tunnelled) to Microsoft Teams services. This section monitors the tenant locations and highlights those that have a high proportion of streams being routed through the VPN. 

The following details are available: 

- Cities and regions impacted
- Public IPs (reflexive) that have a high proportion of streams routed through VPN
- Internet service provider
- Percentage and volume of streams routed through VPN The following details are available: 

    - Cities and regions impacted
    - Public IPs (reflexive) that have a high proportion of streams routed through VPN
    - Internet service provider
    - Percentage and volume of streams routed through VPN

The media streams in this report reflect Teams media communications that connect over a virtual private network (VPN) without split tunnelling. Indirect connections introduce additional latency into media communications and can degrade a user’s media quality. [Learn more](/en-us/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) about setting up split tunnelled connections for VPN users to optimize media quality in your organization. 

[![Screenshot that shows SplitTunnelling](media/best-practice-dashboard/tunnelling.png)](media/best-practice-dashboard/tunnelling.png#ligthbox)

### Enable the correct ports and protocols

The media streams in the **Enable the correct ports and protocols** dashboard reflect Teams media communications conducted over Transmission Control Protocol (TCP) instead of User Datagram Protocol (UDP). This dashboard highlights locations that have a high proportion of streams using TCP.

You should open UDP ports on both the network and client firewalls to Microsoft Teams services to avoid any effect on meeting and call quality. UDP is the preferred network protocol for media streams and high rates of TCP usage can negatively affect the Teams user experience. To learn more about UDP ports and client firewalls, see [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges#microsoft-teams).

To view ports and protocols, select **Enable the correct ports and protocols** in the **Best practice configurations** table.

[![Screenshot of the Best practice configuration's ports and protocols dashboard.](media/db-ports-small-1.png)](media/db-ports-expand-1.png#lightbox)

| Callout | Description |
| --- | --- |
| **1** | **Network traffic trend** - Trend of cities with TCP and UDP traffic. |
| **2** | **Recommended action** - Actions you should take to meet the recommended best practice configurations. |
| **3** | **Regions with TCP traffic** - Visual map that includes a date for when this dashboard was generated and a count of cities with TCP and UDP traffic. You can also search by country, city, and region. |
| **4** | The table provides the following data: <br>- **Cities** - Cities and regions impacted.<br>- **Public IPs (reflexive)** - Count and list of public IPs (reflexive) that have a high proportion of streams using TCP.<br>- **Volume of TCP stream** - Volume of streams using TCP.<br>- **Volume of UDP stream** - Volume of streams using UDP.<br>- **Total streams** - Total of UDP and TCP streams.<br>- **Percent of TCP** - Percentage of streams using TCP.<br>- **Status: Action required** - You must follow Microsoft's recommended actions to update the status. |
| **5** | You can use these buttons to: <br>- Export the table to a CSV file.<br>- Filter by city, public IP address, and status.<br>- Toggle the map view on or off.<br>- Manage settings for columns in the table. |

### Address DNS resolution failures

This dashboard monitors and highlights the locations most affected by Domain Name System (DNS) resolution failures, offering clear visibility into impacted cities and subnets. These insights help you prioritize out where to focus first, so you can fix issues faster and maintain media quality and service performance. To ensure reliable connectivity, you should ensure that DNS resolution occurs close to the network egress point. This setup enhances fault tolerance, reduces reliance on external DNS servers, and improves the overall stability and efficiency of Teams. To learn more about egress network connections, see [Microsoft 365 network connectivity principles](/en-us/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#egress-network-connections-locally).

To view DNS resolution failures, select **Address DNS resolution failures** in the **Best practice configurations** table.

[![Screenshot of the Best practice configuration's DNS resolution failures dashboard.](media/dns-failure-small.png)](media/dns-failure-expand.png#lightbox)

The following details are available:

- Cities and regions impacted
- Public IPs (reflexive) that have a high proportion of streams having DNS resolution failures
- Number and percentage of streams originating from the DNS resolution failure

### Bypass local proxy

This dashboard monitors locations where a high number of streams are routed through a proxy. To improve performance, it's best to keep the connection between the user's device and Microsoft Teams services as short and direct as possible. When too much traffic flows through a proxy server, the server can get overwhelmed—leading to delays, poor media quality, and a frustrating experience. To learn more about local proxies, see [Proxy servers for Teams and Skype for Business Online](proxy-servers-for-skype-for-business-online#not-using-a-proxy-server-is-recommended).

To view local proxies, select **Bypass local proxy** in the **Best practice configurations** table.

[![Screenshot of the Best practice configuration's Bypass local proxy dashboard.](media/bypass-local-proxy-small.png)](media/bypass-local-proxy-expand.png#lightbox)

The following details are available:

- Cities and regions impacted
- Public IPs (reflexive) that have a high proportion of streams routed over proxy
- Percentage and volume of streams routed over proxy

### Bypass cloud proxy

This dashboard highlights locations where a large number of streams are routed through cloud-based proxies. These proxies can introduce latency and packet loss, which might affect call quality. To improve performance, we recommend bypassing cloud proxy configurations for Teams traffic, including TLS/SSL inspection. Teams media traffic is already encrypted, so you don't need proxies for security. To learn more about cloud proxies, see [Microsoft 365 network connectivity principles](/en-us/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#optimizing-connectivity-to-microsoft-365-services).

To view cloud-based proxies, select **Bypass cloud proxy** in the **Best practice configurations** table.

[![Screenshot of the Best practice configuration's Bypass cloud proxy dashboard.](media/bypass-cloud-proxy-small.png)](media/bypass-cloud-proxy-expand.png#lightbox)

The following details are available:

- Cities and regions impacted
- Public IPs (reflexive) that have a high proportion of streams routed over proxy
- Percentage and volume of streams routed over proxy

### Optimize for virtual desktop environment(VDI)

This dashboard monitors locations and identifies those with a high percentage of streams routed through unoptimized Virtual Desktop Infrastructure (VDI). It offers visibility into impacted cities and subnets, enabling administrators to prioritize remediation efforts and sustain optimal media quality and service performance.

To enhance user experience, enabling media optimization for all VDI connections is recommended. When activated, media optimization offloads Teams media traffic to the user's local client, reducing latency and improving reliability for Teams media workloads. To learn more about VDI, see [VDI solutions for Teams](/en-us/microsoftteams/vdi-2#optimizing-with-new-vdi-solution-for-teams).

To view unoptimized VDI streams, select **Optimize for virtual desktop environment** in the **Best practice configurations** table.

![Screenshot showing the user's image.](media/best-practice-dashboard/image.png)

The following details are available:

- Cities and regions impacted
- Public IPs (reflexive) that have high proportion of streams using unoptimized VDI
- Number and percentage of streams originating from unoptimized VDI
- Number and list of users on unoptimized VDI connection

\*\*Administrators with the appropriate roles can export a list of users currently connected to Virtual Desktop Infrastructure (VDI) sessions without media optimization enabled. This capability supports targeted remediation planning and helps drive focused improvements in user experience. The following roles are supported for this export functionality:

- Teams Administrator
- Teams Communications Administrator
- Teams Communications Support Engineer
- Teams Telephony Administrator
- Teams Reader
- Global Administrator
- Global Reader

Note

Downloading the user list isn't currently supported for administrators who are scoped to an administrative unit.