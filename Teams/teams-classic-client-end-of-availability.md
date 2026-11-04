---
layout: Conceptual
title: End of availability for classic Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-classic-client-end-of-availability
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: divyasrirk
author: DivySri-RK
manager: jtremper
ms.topic: article
ms.date: 2026-07-16T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: 
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn about the end date for support and the end of availability for classic Teams client in regard to various groups of Teams users.
ms.localizationpriority: medium
locale: en-us
document_id: b5f759d5-3f96-c3a8-5102-0c4e101d62a4
document_version_independent_id: b5f759d5-3f96-c3a8-5102-0c4e101d62a4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-classic-client-end-of-availability.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-classic-client-end-of-availability
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-classic-client-end-of-availability.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 973706c1-0a34-86a8-39b5-cf166a6b209c
---

# End of availability for classic Teams client - Microsoft Teams | Microsoft Learn

## Overview

A new Teams client is now rolled out, replacing the classic client. This rollout involved installing the new Teams client, with Microsoft attempting to uninstall the classic Teams client after the installation of new Teams. This article has the timelines and details of **end of support** and **end of availability** for classic Teams client.

### Timeline updates

The rollout of the new Teams client is complete. As of July 1, 2025, the classic Teams client is no longer available.

**Native clients excluding VDI**:

The end of support for the classic Teams client started July 1, 2024. The end of availability for the classic Teams client started July 1, 2025.

![A chart showing the timelines for classic Teams to new Teams.](media/teams-client-eoa-timeline.png)

**VDI timeline**:

The end of support for the classic Teams client in VDI started October 1, 2024. The end of availability for the classic Teams client in VDI started July 1, 2025.

![A chart showing the timelines for classic Teams to new Teams for VDI.](media/new-teams-vdi-timeline.png)

The timeline for VDI in regard to GCCH and DOD tenants. The end of support for VDI for these tenants started October 1, 2024, and the end of availability started July 1, 2025.

![A chart showing the timelines for classic Teams to new Teams for VDI, specific to GCCH and DoD tenants.](media/new-teams-vdi-timeline-gcch-dod.png)

For more information regarding VDI, see [Upgrade to new Teams for Virtualized Desktop Infrastructure (VDI)](teams-client-vdi-requirements-deploy).

The following items are the important timeline concepts to keep in mind:

- **End of support**: The end of our supporting classic Teams client. We no longer provided updates or new features for the client, nor do we help resolve support issues with the classic Teams client.
- **End of availability**: The end of functionality for the classic Teams client. After this date, the classic client no longer works and users can't do work in the classic Teams client.

![A chart showing the timelines for the end of support for classic Teams and the end of availability of classic Teams.](media/teams-client-eoa-timeline-complete.png)

### Timeline for GCC, GCCH, DoD

The end of availability is here for GCC, GCCH, and DoD customers as well.

## User experience

**Classic Teams reached the end of support on July 1, 2024.**

### Using the web app

Users who can't upgrade to the new Teams client on their device can use the new Teams web app on [supported browsers](teams-client-system-requirements) instead.

Here's a list of the messages you may experience on the classic Teams client after June 30, 2025:

| Scenario | End of availability warning | End of availability |
| --- | --- | --- |
| Unsupported operating system | Classic Teams will soon be unavailable, and your OS needs to be updated to run the new Teams. Starting July 1, 2025, classic Teams will no longer be available for use. Update your OS or talk to your IT department. View minimum requirements | Classic Teams is no longer available, and your OS needs to be updated to run the new Teams. As of July 1, 2025, classic Teams is no longer available for use. Update your OS or talk to your IT department. To experience the new Teams, you can try it out on the web. View minimum requirements |
| Windows GPO policy blocked users | Classic Teams will soon be unavailable, but due to org policy, we couldn't update you to the new Teams. Starting July 1, 2025, classic Teams will no longer be available for use. To update to the new Teams, contact your IT department. Learn about installation issues | Classic Teams is no longer available, but due to org policy, we couldn't update you to the new Teams. As of July 1, 2025, classic Teams is no longer available for use. Contact your IT department for more info. To experience the new Teams, you can try it out on the web. Learn about installation issues |
| Any install and launch issues | Classic Teams will soon be unavailable, and we couldn't update you to the new Teams. Starting July 1, 2025, classic Teams will no longer be available for use. To update to the new Teams, contact your IT department. Learn about installation issues | Classic Teams is no longer available, and we couldn't update you to the new Teams. As of July 1, 2025, classic Teams is no longer available for use. Contact your IT department for more info. To experience the new Teams, you can try it out on the web. Learn about installation issues |

Important

For customers who uninstall classic Teams themselves and experience a Teams meeting add-on issue, there are troubleshooting steps available here: [Teams meeting add-in missing from Outlook and new Teams](https://support.microsoft.com/Support/known-issues/teams-meeting-add-in-is-missing-in-outlook-desktop-after-updating-to-new-teams).