---
layout: Conceptual
title: Configure QoS settings in the Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meetings-real-time-media-traffic
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
ms.reviewer: siunies
ms.date: 2024-04-18T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: meetings
audience: Admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier2
description: Learn how to enable QoS markers and set port ranges for each type of media traffic in Teams meetings.
locale: en-us
document_id: 0d8c556f-8ddc-ddcc-48d5-69ca75a55698
document_version_independent_id: 0d8c556f-8ddc-ddcc-48d5-69ca75a55698
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meetings-real-time-media-traffic.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meetings-real-time-media-traffic
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meetings-real-time-media-traffic.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 2d5c2a5a-d4cd-a90a-fabb-786071f9b9bd
---

# Configure QoS settings in the Teams admin center - Microsoft Teams | Microsoft Learn

This article is for administrators and IT professionals who are configuring Quality of Service for Microsoft Teams. This article describes how to enable QoS in the Teams admin center.

**Before reading this article, be sure to read [Implement Quality of Service in Microsoft Teams](qos-in-teams)**, which describes everything you need to know to successfully use QoS with Microsoft Teams:

- QoS concepts, such as QoS queues, DSCP, DSCP markers and tagging, and so on
- Network readiness considerations
- Choosing a QoS implementation method
- Choosing port ranges
- Validating your implementation

Note: If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](qos-in-teams-clients) and all internal network devices to fully implement the changes to QoS in Teams.

## Manage QoS markers in the Microsoft Teams admin center

1. Go to the [Teams admin center](https://admin.teams.microsoft.com).
2. In the left navigation, go to **Meetings** &gt; **Meeting settings**.
3. Under **Network**, do the following:

    ![Screenshot of the network settings for meetings in the admin center.](media/meeting-settings-network.png)

    - To enable QoS, turn on **Quality of Service (QoS) markers for real-time media traffic**. You can specify whether or not to use markers, but you can't set custom markers for each traffic type. For more information about DSCP markers, see [Select a QoS implementation method](qos-in-teams#step-2-select-a-qos-implementation-method).

        Important

        Enabling QoS is performed only on the endpoints for tagging packets leaving the client. We recommend applying matching QoS rules on all internal network devices for incoming traffic.
    - If you've enabled Quality of Service, you must manage your port settings.

        To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing. The port ranges for calling and meeting signaling are not customizable currently.

        Selecting a port range that is too narrow will lead to dropped calls and poor call quality. For more information about choosing port ranges, see [Choose initial port ranges](qos-in-teams#step-3-choose-initial-port-ranges-for-each-media-type).

        The port ranges you assign can't overlap and should be adjacent to each other.

        Important

        Do not select **Automatically use any available ports** unless you aren't implementing QoS. If you select this option, available ports between 1024 and 65535 are used.

After using QoS for a while, you can use [Call Quality Dashboard](cqd-what-is-call-quality-dashboard) to determine if changes are required to your QoS configuration.