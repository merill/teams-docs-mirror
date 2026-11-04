---
layout: Conceptual
title: Signal settings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/signal-settings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: altsou
ms.date: 2024-09-17T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: itpro-rooms
audience: Admin
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: Customize which signals are enabled with the new Signal settings.
f1keywords: 
locale: en-us
document_id: 75f83af9-fe0f-024d-585b-5a560ed5aff9
document_version_independent_id: 75f83af9-fe0f-024d-585b-5a560ed5aff9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/signal-settings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/signal-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/signal-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/540ac133-a371-4dbb-8f94-28d6cc77a70b
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/60bfc045-f127-4841-9d00-ea35495a5800
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 0a2b7e34-2edb-9e58-ffaf-5041194f5339
---

# Signal settings - Microsoft Teams | Microsoft Learn

The health of a meeting room is determined by signals that monitor important functions of the device. Your organization can have different preferences or needs for your environment where certain signals are more useful than others, or trigger more often than desired. To help focus on the signals that are important to you, it's possible to enable or disable signals through the **Settings &gt; Signals** page.

On the **Signal settings** page, all signals are listed and can be sorted by **Signal** name, **Device type**, **Category** and **Signal state**. Or they can be filtered by **Device type**, **Category** and **Signal state**.

**To disable signals:**

Disabling a signal turns it off for all applicable devices, closing active tickets of the respective signal and prevent further tickets or remediation.

1. In the left navigation of the Microsoft Teams Rooms Pro Management portal, go to **Settings &gt; Signals**.
2. On the **Signal settings** page, select one or more signals from the list.
3. Select **Disable**.

**To enable signals:**

Enabling a signal turns it on for all applicable devices. The signal will be evaluated at the next cycle. Tickets previously closed through disabling can't be reactivated.

1. In the left navigation of the Microsoft Teams Rooms Pro Management portal, go to **Settings &gt; Signals**.
2. On the **Signal settings** page, select one or more signals from the list.
3. Select **Enable**.

**To reset signal to default:**

Resetting a signal to default will enable or disable the signal to its default value, as recommended by the Pro service.

1. In the left navigation of the Microsoft Teams Rooms Pro Management portal, go to **Settings &gt; Signals**.
2. On the **Signal settings** page, select one or more signals from the list.
3. Select **Reset to default**.