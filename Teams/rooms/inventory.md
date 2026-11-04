---
layout: Conceptual
title: Inventory management for resource accounts and devices in Teams Rooms Pro Management portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/inventory
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: srpall
ms.date: 2026-04-28T00:00:00.0000000Z
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- teams-rooms-devices
- teams-rooms-consoles
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: Learn how to manage your resource account inventory in the Teams Room Pro Management portal.
ai-usage: ai-assisted
ms.custom: QuickDraft
locale: en-us
document_id: 5c601441-4892-a861-b06b-921eb85a26fe
document_version_independent_id: 5c601441-4892-a861-b06b-921eb85a26fe
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/inventory.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/inventory
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/inventory.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e8b93797-aff0-d078-bfcc-fc2d5bdaec91
---

# Inventory management for resource accounts and devices in Teams Rooms Pro Management portal - Microsoft Teams | Microsoft Learn

Manage your organization's meeting rooms and device inventory using the inventory management features in Microsoft Teams Rooms. This guide covers how to onboard your organization, manage your location directory, search for meeting rooms, and update meeting room information.

## Onboard your organization

To set up your inventory and load data for the first time, you need to take an action:

1. Sign in to the [Teams Rooms Pro Management portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service).
2. Select **Planning** then **Inventory** in the left navigation pane.
3. Select **Get data** to retrieve the location details and inventory of Microsoft Teams Rooms devices deployed in your organization.

Note

This process may take some time, depending on the number of meeting rooms. For example, a large organization with over 20,000 meeting rooms might experience a wait of up to 20 minutes.

## Refresh your inventory on demand

It can take up to 48 hours for recently added resource accounts to appear. You can perform an on-demand sync and the account should be visible within 15 minutes.

1. Sign in to the [Teams Rooms Pro Management portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service).
2. Select **Planning** then **Inventory** in the left navigation pane.
3. Select **Sync** to retrieve the latest inventory of resource accounts.

## Manage Your location directory and view meeting rooms

Once the setup is complete, your organization's location directory appears in the left pane. Meeting rooms are organized hierarchically by location details, such as country/region, state, city, campus, building, floor, and room. You can also view a comprehensive list of all meeting rooms within your organization.

At the top, you find a summary that includes a breakdown of meeting rooms, including the number of unlicensed rooms. Additionally, there's a quick overview of meeting rooms categorized by type, such as Small, Medium, and Large.

Note

Resource accounts with their Exchange property set to "Hide from Global Address List (GAL)" won't be shown in the inventory. Disable "Hide from GAL" to ensure the rooms are visible in your inventory.

## Search for specific meeting rooms

To filter your meeting rooms, use the search feature. You can search for rooms in your organization by address details such as country/region, state, and city, or by meeting room name and other attributes, such as the device manufacturer, capacity, place type, and device type.

## Manage Your inventory of devices

You can view and manage your inventory of Teams Room systems and other assets from the inventory pane:

- If a Microsoft Teams Room console is deployed in a meeting room, it's automatically detected and added to the room's inventory.
- To remove a device, select it and select the **Remove** button.
- To add a new device, select **Add** and choose from the available Teams Room system devices in your organization.

Microsoft Teams Room systems, Surface Hubs, Collab Bars, Teams Displays, and Teams IP Phones are automatically detected. For all other hardware types, you can manually add them to the room inventory under the **Meeting Room assets** section. You can also manage additional meeting room assets, such as projectors, docking stations, routers, motion sensors, or tables, using the **Add, Edit, or Remove** functions in the **Manage Room assets** section.

## Update your meeting room information

Select a room from your inventory and go to the **General** tab to update details such as address, building, and floor. The changes are immediately reflected in your location directory. Updated location information will also be saved in Microsoft Entra.

## Access control

To create, edit, or remove resource accounts in a Microsoft 365 tenant, high-level privileges are required. Specifically, the IT administrator must be assigned to either the Exchange Admin or Global Admin role to perform these actions.

Important

Microsoft recommends using roles with the fewest permissions. Using lower-permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.