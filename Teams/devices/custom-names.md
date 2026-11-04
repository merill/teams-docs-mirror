---
layout: Conceptual
title: Add a custom name for Teams panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/custom-names
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: eviegrimshaw
ms.date: 2026-03-23T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: This article provides the information required when you want to add in a custom name for a Microsoft Teams panel.
locale: en-us
document_id: 170c7bd8-8671-4b19-71cc-bf617a2efe3f
document_version_independent_id: 170c7bd8-8671-4b19-71cc-bf617a2efe3f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/custom-names.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/custom-names
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/custom-names.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b3ad7ac0-08ef-413f-f4a6-e5bd7753c6ed
---

# Add a custom name for Teams panels - Microsoft Teams | Microsoft Learn

You can customize the display name for your Teams panel. For example, you can shorten the name to something that is more easily readable for your users. 

The custom name is displayed on the Teams panel home screen, so we recommend making sure it's clear and understandable to your users. In addition, this doesn't change the display name shown on Microsoft Teams Rooms if you have one inside of the room.

> 
> [![Screenshot of the home screen of the Teams panel with the custom name.](media/custom-names/image.png)](media/custom-names/image.png#lightbox)

> 
> [![Screenshot of the dialogue box showing the full conference room name.](media/custom-names/image1.png)](media/custom-names/image1.png#lightbox)

## Set up and manage custom names for your Teams panels

Note

Within 24 hours of the custom name being updated to a name other than the GAL one, the Teams panel home screen reflects the new name. The home screen also has a tooltip that when selected, shows the user the GAL name.

### Using the Teams Rooms Pro Management Portal

1. Sign in to the **Teams Rooms Pro Management Portal**.
2. Go to **Planning** &gt; **Inventory** &gt; **Rooms** &gt; select the room where you’d like to apply a custom name.
3. In the **Custom name** field, add the name for the Teams panel. By default, this field is automatically filled with the name that is shown in the Global Address Book (GAL).
4. Select **Save**.

### Using Microsoft Places

Teams panels references the "nickname" field within Microsoft Places to determine if a custom name is displayed. You can use the Places Graph APIs to modify the "nickname" value on a given Places object. You can learn more in [Update place](/en-us/graph/api/place-update?view=graph-rest-1.0&amp;tabs=http#example-5-update-a-room).

### Show or hide the custom name locally on the panel

In Teams admin settings, an admin can view the GAL name and custom name if one is applied under **Device settings** &gt; **Display name**. It isn't possible to edit the name in these admin settings. Editing can only be done in the Teams Rooms Pro Management portal.

If you would like to remove the custom name, you can remove the name in the custom name field in the Teams Rooms Pro Management portal or Graph, and the display name on Teams panel automatically defaults to the GAL name.

## Frequently asked questions

**Question:** I'm not able to see the custom name field in Teams Rooms Pro Management portal when I select a room account in Inventory. What am I missing?**Answer:** Make sure that the panel is appearing as signed into the room account in the Pro Management portal, and the panel has a Teams Rooms Pro or Teams Shared Device license assigned.

**Question:** What admin role do I need in order to be able to add a custom name in the Teams Rooms Pro Management portal?**Answer:** The admin must be a global admin, Exchange admin, or Mail Recipients admin.