---
layout: Conceptual
title: Manage whether meetings in your organization can detect sensitive content during screen sharing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/detect-sensitive-content
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: freda.li
ms.date: 2025-07-01T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
description: Learn how to manage whether meetings in your organization can detect sensitive content during screen share.
locale: en-us
document_id: cac90c34-acdd-b552-9aa9-49f4a136f84e
document_version_independent_id: cac90c34-acdd-b552-9aa9-49f4a136f84e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/detect-sensitive-content.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: detect-sensitive-content
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/detect-sensitive-content.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 79876732-0b19-9379-ed96-f3bd6ac905fa
---

# Manage whether meetings in your organization can detect sensitive content during screen sharing - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

## Overview

As an admin, you can manage whether meetings in your organization can detect sensitive content during screen sharing. When you turn on the **Detect sensitive content during screen sharing** policy setting for organizers with a Teams Premium license, sensitive information like credit card and account numbers in shared screen content is identified during their meetings. When sensitive content is detected, both the presenter and the meeting organizer receive notifications to stop sharing and the presenter sees a **Stop sharing** button. This added layer of protection helps safeguard sensitive data and minimizes accidental disclosure. Organizers with a Teams Premium license can use their **Meeting options** to choose which meetings have this feature.

Important

When sensitive content is detected during a meeting, the data remains within the compliant boundary. No visual data from detected shared content is stored.

We currently support the following sensitive content categories in English:

- Credit Card Numbers
- U.S. Bank Account Numbers
- ABA Routing Numbers
- EU Debit Card Numbers
- EU Password Numbers
- EU Driver’s License Numbers
- EU Social Security Numbers
- EU National Identification Numbers
- U.S. Social Security Numbers
- U.S./U.K. Passport Numbers
- U.S. Individual Taxpayer Identification Numbers
- EU Tax Social Security Numbers

This feature is supported on Teams desktop, web, mobile, and video-based screen sharing (VBSS).

The following table shows where sensitive content detection is configured:

| Setting | Admin policy | Sensitivity label | Template | Meeting organizer |
| --- | --- | --- | --- | --- |
| Detect sensitive content during screen sharing | Yes | Yes | Yes | Yes |

To learn more about meeting templates, see [IT admins - Create a custom meeting template in Microsoft Teams](create-custom-meeting-template). To learn more about sensitivity labels, see [Use sensitivity labels to protect calendar items, Teams meetings, and chat](/en-us/purview/sensitivity-labels-meetings).

Note

End-to-end encryption isn't available in meetings where sensitive content detection is turned on.

To learn more about how your users use this feature, see [Sensitive content detection in Microsoft Teams meetings](https://support.microsoft.com/office/sensitive-content-detection-in-microsoft-teams-meetings-11f235f9-a170-4490-8bcb-703019d20a63).

## Manage whether meetings can detect sensitive content in the Teams admin center

To manage whether meetings in your organization can detect sensitive content in the Teams admin center, use the following steps:

1. Open the Teams admin center.
2. Expand **Meetings** from the navigation pane.
3. Either select an existing policy or create a new one.
4. Within your chosen policy, navigate to the **Content Protection** section.
5. Toggle the **Detect sensitive content during screen sharing** setting **On** (default) or **Off**.
6. Select **Save**.