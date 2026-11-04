---
layout: Conceptual
title: Set up for live events in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-live-events/set-up-for-teams-live-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: christi.balaki,cmunden
ms.date: 2026-06-11T00:00:00.0000000Z
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: Set up for live events in Teams, including set up your network, assign licenses, enable live event features and scheduling, and video distribution solutions.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: b9aa4676-855a-fddb-bb0b-96b7095c695e
document_version_independent_id: 7c39f08c-0d56-6d29-1356-879d9d6ff51c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-live-events/set-up-for-teams-live-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-live-events/set-up-for-teams-live-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-live-events/set-up-for-teams-live-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fdc21613-16c9-f89f-1e8a-59adcfe41424
---

# Set up for live events in Microsoft Teams - Microsoft Teams | Microsoft Learn

Important

Teams live events retired on June 30, 2026. Events scheduled before June 30, 2026 are supported through February 28, 2027. [Learn more about Teams live events retirement](https://go.microsoft.com/fwlink/?linkid=2347480).

We recommend transitioning to the unified Teams events experience, which provides a centralized way to set up and manage digital and hybrid events at scale. Organizers can use templates to schedule town halls and create events from scratch to tailor the experience. To learn more, see [Plan for Teams events](/en-us/microsoftteams/plan-events).

When you're setting up for live events, there are several steps that you must take.

## Step 1: Set up your network for live events in Teams

Live events produced in Teams require you to [prepare your organization's network for Teams](../prepare-network).

## Step 2: Get and assign licenses

Ensure you have correct license assignments for [who can create and schedule live events](plan-for-teams-live-events#who-can-attend-create-and-schedule-live-events) and [who can watch live events](plan-for-teams-live-events#who-can-watch-live-events).

## Step 3: Set up live events policies

Live events policies control which users in your organization can hold live events and specify the features that are available during these events. You can use the default policy or create one or more custom live events policies. After you create a custom policy, assign it to a user or groups of users in your organization.

Note

Users in your organization get the global (Org-wide default) policy unless you create and assign a custom policy. By default, in the global policy, live event scheduling is turned on for Teams users, while live captions and subtitles (transcription) is turned off. Everyone in the organization can join live events, and the recording setting is set to always record.

### Create or edit a live events policy

1. In the left navigation of the Microsoft Teams admin center, go to **Meetings** &gt; **Live events policies** &gt; **Manage Policies** tab.
2. Do one of the following options:

    - If you want to edit the existing default policy, choose **Global (Org-wide default)**.
    - If you want to create a new custom policy, choose **+Add**.
    - If you want to edit a custom policy, select the policy, and then choose **Edit**.

    Here are the settings you can change to fit the needs of your organization.

    [![Screen shot of live events policy settings in the Microsoft Teams admin center.](../media/live-event-policies-tac-small.png)](../media/live-event-policies-tac-expand.png#lightbox)

| Setting | Description |
| --- | --- |
| **Title** | The policy's title that appears on the live events policies page. It can't be longer than 64 characters or have any special characters. |
| **Description** | Add a description so you know why this policy was created. |
| **Live events scheduling** | Toggling this setting **On** lets users in your organization create and schedule live events in Teams. |
| **Transcription for attendees** | This setting can only be applied to events produced in Teams. Turning this on enables live event attendees to see live captions and subtitles during the event. |
| **Who can join scheduled live events** | Choose one of the following options:**Everyone** Users can create live events that everyone, including people outside your organization, can attend. This setting turns on the **Public** permission type in Teams when a user schedules a live event.**Everyone in the organization** Users can create live events that people in your organization, including [guests](../add-guests) added to your organization, can attend. Users can't create live events that anonymous users can attend. This setting turns on the **Org-wide** permission type in Teams when a user schedules a live event.**Specific users or groups** Users can create live events that only specific users or groups in your organization can attend. Users can't create live events that everyone in your organization or anonymous users can attend. This setting turns on the **People and groups** permission type in Teams when a user schedules a live event. |
| **Recording an event** | This setting can only be applied to events produced in Teams. Choose one of the following. **Always record**- Live events that users with this policy create are always recorded. After the event is over, event team members can download the recording and attendees can watch the event. **Never record**- Live events that users with this policy create are never recorded. **Organizer can record**- Users with this policy can decide whether to record live events that they create. If the event is recorded, after the event is over, event team members can download the recording and attendees can watch the event. |

You can also manage live event policies using Windows PowerShell, and, currently, GCC High and DoD customers must use this method. For more information, see [Use PowerShell to set live events policies in Teams](set-teams-live-events-policies-using-powershell).

### Assign a live events policy to users

If you created a custom live events policy, assign it to users for the policy to be active. You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](../policy-assignment-overview).

## Step 4: Set up a video distribution solution for live events in Teams

Playback of live event videos uses adaptive bitrate streaming (ABR) but it's a unicast stream, meaning every viewer is getting their own video stream from the internet. For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers. For organizations that want to reduce this internet traffic for live events, Microsoft offers a first-party solution, [Microsoft eCDN](/en-us/ecdn) (enterprise content delivery network). Live events solutions are also integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or eCDNs. These SDN/eCDN platforms allow organizations to optimize network bandwidth without sacrificing end-user viewing experiences. These solutions can help create a more scalable and efficient video distribution across your enterprise network.

- **Microsoft eCDN** Microsoft eCDN is integrated into Teams and is also compatible with Stream and Viva Engage. It employs peer-to-peer technology within a corporate network to offload bandwidth from the WAN connection.
- **Purchase and set up your solution outside of Teams** Get expert help with scaling video delivery by using Microsoft's trusted video delivery partners.

The following SDN/eCDN solutions are preintegrated and can be set up to be used with Teams streaming:

- **Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution. Hive is a software-based solution that requires no extra hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without affecting to your network. For customers looking to understand the impact video is having on their network before purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers. [Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
- **Kollective** is a cloud-based, smart-peering distribution platform that uses your existing network infrastructure to deliver content in many forms (live streaming video, on-demand video, software updates, security patches, and more) faster, more reliably, and with less bandwidth. The world's largest financial institutions trust our secure platform and with no extra hardware, setup, and maintenance are easy. [Learn more](https://kollective.com/microsoft).
- **Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth, and support successful live event broadcasts and on-demand streaming. The support for Ramp OmniCache for live events produced in Teams is coming soon. [Learn more](https://rampecdn.com).

Note

If you choose a third-party SDN or eCDN solution, it's subject to the selected **third-party provider's terms of service and privacy policy**, which governs your use of the provider's solution. Your use of the provider's solution isn't subject to the Microsoft volume licensing terms or Online Services Terms. If you don't agree to the **third party provider's terms**, then don't turn on the solution in Teams.

After you set up the SDN or eCDN solution, you're ready to configure the provider for live events in Teams.