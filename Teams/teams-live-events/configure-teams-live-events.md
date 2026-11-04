---
layout: Conceptual
title: Configure live event settings in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-live-events/configure-teams-live-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.date: 2026-07-15T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: chbalaki,cmunden
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: Learn how to manage settings for Teams live events that are held in your organization.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
locale: en-us
document_id: 4b358007-ded1-e7e2-01ff-e646a0d8f9b6
document_version_independent_id: ef681dd5-896c-1b48-7009-63cf5847f126
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-live-events/configure-teams-live-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-live-events/configure-teams-live-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-live-events/configure-teams-live-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 60affa7a-fa0d-82d2-1207-414fb872fa48
---

# Configure live event settings in Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

Teams live events settings allow you, as an admin, to manage settings for live events in your organization. You can set up a support URL and configure a third-party video distribution provider. These settings apply to all live events that are created in your organization.

![Screen shot of Teams live events settings.](../media/teams-live-events-settings-new.png)

## Add event support URL

The support URL for the event is shown to live event attendees. Add your organization's support URL so attendees can contact support during live events.

### Use the Microsoft Teams admin center to add an event support URL

1. Open the Teams admin center.
2. Go to **Meetings** &gt; **Live event settings**.
3. Under **Support URL**, enter your organization's support URL.
4. Select **Save**.

### Use PowerShell to add an event support URL

In PowerShell, the **`-SupportURL`** parameter in the **CsTeamsMeetingBroadcastConfiguration** cmdlet allows you to add a support URL for live events.

To add a support URL, use the following script:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```

## Configure a third-party video distribution provider

For information about setting up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution, see [Enterprise content delivery networks for streaming Microsoft Teams events](/en-us/microsoftteams/streaming-ecdn-enterprise-content-delivery-network).