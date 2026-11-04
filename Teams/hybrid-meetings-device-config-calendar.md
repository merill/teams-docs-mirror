---
layout: Conceptual
title: Step 7 - Configure calendar options - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/hybrid-meetings-device-config-calendar
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: sohailta
ms.date: 2025-01-17T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- m365solution-teamshybrid
- m365solution-scenario
- m365initiative-meetings
- teams-rooms-devices
ms.localizationpriority: high
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
description: Configure how a resource account responds to meeting invites.
locale: en-us
document_id: 477e3f23-97b0-1c62-549a-c1618449ba10
document_version_independent_id: 477e3f23-97b0-1c62-549a-c1618449ba10
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/hybrid-meetings-device-config-calendar.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: hybrid-meetings-device-config-calendar
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/hybrid-meetings-device-config-calendar.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
platformId: b2fee468-b855-d2f2-b475-4d6f82ec5795
---

# Step 7 - Configure calendar options - Microsoft Teams | Microsoft Learn

![IT Pro audience](media/hybrid-audience-itpro-small.png)

To help your users more easily schedule meetings in a Teams Rooms, you can create room lists in Exchange Online.

Exchange room lists are used to control which resource accounts (and therefore the Teams Rooms they're associated with) appear in the Room Finder. Room Finder is an Outlook feature that helps users find rooms that are near them, available for reservation, and meet other criteria such as the availability of a display.

Room lists are a special type of Exchange distribution group that lets you group resource accounts (and therefore the Teams Rooms they're associated with) together in a meaningful way. For example, you might want to create room lists for all the rooms in each building on your campus.

Microsoft Places lets you set specific attributes about a resource account and its Teams Rooms. Some of the attributes you can set are:

- Building
- City
- Capacity
- Wheelchair-accessible
- Room features

Room Finder in Outlook shows a list of rooms available to them for reservation based on a combination of room lists and place attributes selected by a user. To make the best use of room lists and places, create room lists based on a place attribute, such as building. For example, set the city and building place attributes for each resource account, and then add each resource account to a building room list. When a user tries to choose a room to reserve, Outlook shows a list of cities and the room lists available in each of those cities.

Important

Each resource account needs to have its place attributes set. If these attributes, especially city, building, and capacity, aren't set, those rooms won't show up as available options for reservation even if a room list contains them.

To create a room list, follow the instructions in [Create a rooms list](/en-us/exchange/recipients/room-mailboxes?view=exchserver-2019&amp;preserve-view=true#create-a-room-list).

To configure the place attributes for a resource account, see [Set-Place](/en-us/powershell/module/exchange/set-place).