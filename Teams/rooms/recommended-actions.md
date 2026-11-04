---
layout: Conceptual
title: Recommended Actions in Teams Rooms Pro Management - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/recommended-actions
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to use Recommended Actions in Teams Rooms Pro Management to proactively manage device upgrades, data hygiene, and meeting space optimization.
author: glai-MSFT
ms.author: garla
ms.service: msteams
ms.topic: overview
ms.date: 2026-06-23T00:00:00.0000000Z
ms.subservice: itpro-rooms
ai-usage: ai-assisted
manager: ronjohns
locale: en-us
document_id: 58d90d3f-3a0a-6eff-2883-9ece22f11e88
document_version_independent_id: 58d90d3f-3a0a-6eff-2883-9ece22f11e88
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/recommended-actions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/recommended-actions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/recommended-actions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6466e432-957d-9efb-b2f3-12a580402c74
---

# Recommended Actions in Teams Rooms Pro Management - Microsoft Teams | Microsoft Learn

## Overview

The **Recommended Actions** page in the Teams Rooms Pro Management portal's Analytics & Reports section provides proactive recommendations based on your organization's environment and upcoming events that can impact devices, such as support or certification expirations. Admins are prompted to update room account data, enabling rich insights from the portal. This feature helps admins maintain smooth operations and plan and budget efficiently.

[![Screenshot of the Recommended Actions overview page in the Teams Rooms Pro Management portal Analytics and Reports section.](media/recommended-actions/image.png)](media/recommended-actions/image.png#lightbox)

Note

Rooms that are hidden from the address book are not included in Shared Spaces Insights and Recommended Actions pages. Specifically, the “HiddenFromAddressListsEnabled” must be set to false for the room resource account mailbox for the room to be included. For more information, refer to [HiddenFromAddressListsEnabled](/en-us/powershell/module/exchangepowershell/set-mailbox?view=exchange-ps#-hiddenfromaddresslistsenabled&amp;preserve-view=true).

## Prerequisites

At least one Teams Rooms Pro or Teams Shared Devices license is required to access the Recommended Actions page.

Note

Only tiles relevant to your tenant are shown on this page.

## Enable Meeting Space Optimization Recommendations

To receive meeting space optimization recommendations, an administrator with appropriate access must enable the setting that allows Microsoft to use your room, device, and usage data in the Teams Rooms Pro Management portal for this purpose. This setting is turned off by default.

### What enabling this setting means

When this setting is enabled, Microsoft analyzes this data to:

- Identify meeting spaces and devices that may benefit from optimization
- Provide recommendations for rooms not currently configured as Teams Rooms to help optimize those spaces
- Direct admins to Microsoft websites where they can learn more about recommended Teams Rooms devices and available purchasing options in supported regions

This is a tenant-level setting that is turned off by default. Admins can enable or turn off this setting at any time.

### Who can change this setting

The following [Teams Rooms Pro Management portal roles](/en-us/microsoftteams/rooms/rooms-pro-rbac) have the required access to enable or disable this setting in the portal:

- Teams Rooms Pro Manager
- Global Administrator
- Teams Administrator

### How to enable this setting

1. Sign in to the [Teams Rooms Pro Management portal](https://portal.rooms.microsoft.com) with an account that has the required administrator role.
2. In the Teams Rooms Pro Management portal, go to **Settings** &gt; **General** &gt; **Meeting space optimization recommendations**.
3. In the **Meeting space optimization recommendations** section, select the check box to allow the use of your room, device, and usage data to provide recommendations that help you optimize your meeting spaces and plan improvements in your tenant. By default, this setting is **Disabled**.
4. Enter your email address to acknowledge that you're enabling this feature.
5. Select **Save**.

[![Screenshot of the Meeting space optimization recommendations setting under Settings &gt; General in the Teams Rooms Pro Management portal.](media/recommended-actions/meeting-space-optimization-recommendations-setting.png)](media/recommended-actions/meeting-space-optimization-recommendations-setting.png#lightbox)

Note

The end-of-support and end-of-certification recommendations are related to room health and Teams service and do not require this setting to be turned on.

### Log history

Teams Rooms Pro Manager, Global Administrator, and Teams Administrator roles can check the log history under **Settings** &gt; **General** &gt; **Log history** to view when this setting was enabled or disabled.

## Role-Based Access Control (RBAC)

Recommended Actions adheres to [role-based access controls](/en-us/microsoftteams/rooms/rooms-pro-rbac) in the Teams Rooms Pro Management portal, displaying rooms the user is authorized to view.

## Global Page Location Filters

The global page filters refer to the dropdown filters on the **Recommended Actions** page. These filters carry over into the detailed view and are categorized into:

- Location filters
- Group filter

### Location filters

Use location filters to see recommended actions for a specific location. Select the desired location and press the **Apply** button to update the recommended actions for the selected location. The default recommendations are for the entire tenant.

[![Screenshot of the location filters dropdown on the Recommended Actions page in the Teams Rooms Pro Management portal.](media/recommended-actions/location-filters.png)](media/recommended-actions/location-filters.png#lightbox)

### Location and Capacity Data Source

The location hierarchy in the Shared Spaces Insights and Recommended Actions pages are sourced from the Places API (V1) room resource type in Microsoft Graph. For more information, refer to the [room resource type](/en-us/graph/api/resources/room?view=graph-rest-1.0&amp;preserve-view=true) and [physical address](/en-us/graph/api/resources/physicaladdress?view=graph-rest-1.0&amp;preserve-view=true).

The following table shows the location hierarchy and capacity fields that map to the Places API room properties.

| Location Hierarchy | Set-Place (cmdlet) | Room resource type (Graph API) |
| --- | --- | --- |
| Country/Region | countryOrRegion | physicalAddress.countryOrRegion |
| State/Province | state | physicalAddress.state |
| City | city | physicalAddress.city |
| Building name | building | building |
| Floor | floorLabel | floorLabel |
| Capacity | capacity | capacity |

Note

The Places API has FloorLabel and FloorNumber room properties. The location hierarchy is using the FloorLabel property for the floor location filter. For additional information on setting these room properties, refer to: [Set-Place](/en-us/powershell/module/exchangepowershell/set-place?view=exchange-ps&amp;preserve-view=true) and [Get-Place](/en-us/powershell/module/exchangepowershell/get-place?view=exchange-ps&amp;preserve-view=true)

### Group filter

You can filter the data using the group filter at the top of the Teams Rooms Pro Management portal as a page-level filter.

[![Screenshot of the group filter dropdown at the top of the Recommended Actions page in the Teams Rooms Pro Management portal.](media/recommended-actions/group-filters.png)](media/recommended-actions/group-filters.png#lightbox)

## Device Upgrades

This section provides proactive recommendations based on device end of support or certification expirations and suggestions on rooms that can be upgraded to Teams Rooms to assist with space planning. The **View recommendation** button in each tile opens a side panel with more details on the rooms. Reference the following link for more information on Teams Rooms certification program and end of support information: [Teams certified devices](../devices/certified-devices-overview) and [Windows 10 support ending](/en-us/microsoftteams/rooms/rooms-lifecycle-support#support-ending-for-teams-rooms-devices-running-windows-10).

The following options are available to help with upgrade planning:

- **Metrics:** Selecting the metrics can filter the table to show those rooms.
- **Upgrade options:** Select the link to view suggested upgrade options in the devices store.
- **Filtering options:** Columns can be filtered to help prioritize upgrades. Selecting **Reset all** resets the filters to the default state.
- **Column Sort:** Columns can be sorted to help prioritize upgrades.
- **Search by Room name:** Search by the room display name to find the room of interest.

[![Screenshot of the Teams Rooms end-of-support drilldown view showing room list, metrics, end-of-support date bar chart, room name search bar, and filter options.](media/recommended-actions/l2-mtr-end-of-support.png)](media/recommended-actions/l2-mtr-end-of-support.png#lightbox)

### Meeting space optimization recommendations

The following tiles in the **Device upgrades** section help admins plan Teams Rooms deployments by identifying non–Teams Rooms that can be upgraded to deliver richer, more consistent meeting experiences.

- Non-Teams Rooms with a Teams Rooms certified video bar
- Non-Teams Rooms without a Teams Rooms certified video bar

#### Non-Teams Rooms with a Teams Rooms certified video bar

This tile identifies rooms already equipped with a Teams Rooms–certified video bar used in BYOD mode. These rooms can be upgraded to Teams Rooms with minimal additional hardware, making them strong candidates for quick, cost-efficient upgrades.

Rooms are grouped into:

- BYOD rooms with certified video bar
- BYOD rooms with certified video bar and Teams Panels

#### Non-Teams Rooms without a Teams Rooms certified video bar

This tile identifies rooms that don't have a certified video bar and require additional hardware to upgrade to Teams Rooms. Rooms are categorized to support upgrade planning based on current device setup:

- **Stand-alone Panel rooms:** Rooms with a Teams Panel but no Teams Room device
- **BYOD peripherals rooms with Panels:** Rooms with BYOD peripherals and a Teams Panel
- **BYOD peripherals rooms:** Rooms with BYOD peripherals only
- **No devices room:** Rooms with no detected Teams devices or peripherals

## Data Hygiene

This section provides proactive recommendations based on device or room account data enabling richer data insights from the portal. The **View recommendation** button in each tile opens a side panel with more details on the rooms.

The following options are available:

- **Metrics:** Selecting the metrics can filter the table to show those rooms.
- **Filtering options:** Columns can be filtered to prioritize taking actions. Selecting **Reset all** resets the filters to the default state.
- **Column Sort:** Columns can be sorted to help prioritize actions.
- **Search by Room name:** Search by the room display name to find the room of interest.

[![Screenshot of the data hygiene drilldown room list showing rooms missing location or capacity information, metrics, room name search bar, and filter options.](media/recommended-actions/l2-missing-location-and-capacity.png)](media/recommended-actions/l2-missing-location-and-capacity.png#lightbox)