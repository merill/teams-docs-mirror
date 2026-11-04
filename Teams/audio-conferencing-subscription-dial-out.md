---
layout: Conceptual
title: Audio Conferencing Dial-Out/Call Me At minutes - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/audio-conferencing-subscription-dial-out
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: mikedav, oscarr
ms.date: 2026-10-08T00:00:00.0000000Z
ms.topic: concept-article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- m365initiative-meetings
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-mar2020
description: Dial-Out and Call Me At minutes benefit. Each audio conferencing subscription provides 60-minutes per-user per-month to Zone A countries and regions.
locale: en-us
document_id: 037fe22c-ba09-e381-231d-c37f6bb2a774
document_version_independent_id: e8046130-d407-3155-53c5-9043110cd793
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/audio-conferencing-subscription-dial-out.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: audio-conferencing-subscription-dial-out
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/audio-conferencing-subscription-dial-out.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c0fba945-0b13-a925-733c-e12e33d020c7
---

# Audio Conferencing Dial-Out/Call Me At minutes - Microsoft Teams | Microsoft Learn

## Microsoft Teams and Audio Conferencing

Each standard Audio Conferencing subscription includes 60 minutes per user, per month, for dial-out calls to non-premium numbers in any Zone A country or region, as defined in this document. This benefit applies to Audio Conferencing *monthly subscription* licenses and doesn't extend to Audio Conferencing pay-per-minute licenses.

Note

The dial-out minute pool size of the Audio Conferencing dial-out to USA and Canadian subscriptions is based on the number of licenses *assigned* to users. For example, if a customer has 100 licenses, and 20 of them are assigned to users, the dial-out minute pool of the Audio Conferencing dial-out to USA or Canadian subscription is 1,200 minutes (60 dial-out minutes to the subscription x 20 licenses assigned to users).

Note

The [complimentary dial-out](complimentary-dial-out-period) is only available in Russia, South Korea, and Taiwan, where Audio Conferencing is available, but Communications Credits setup isn't currently supported.

## Audio Conferencing "Dial Out From a Meeting" & "Call Me At" details

When you adopt our Audio Conferencing service, Microsoft allows your users to dial out from meetings organized by users assigned an Audio Conferencing subscription license. Dial-out calls to countries and regions not included in the [Zone A countries and regions](audio-conferencing-zones) list are charged per minute using Communications Credits. For dial-out calls that are billed per minute (calls exceeding the tenant dial-out minute pool or calls to destinations not in the [Zone A countries and regions](audio-conferencing-zones) list), the calls and their associated rates are based on the destination of the call and not the organizer's country or region of residence or the meeting participant initiating the dial-out call. For example, when a meeting participant in the United States, France, or Zimbabwe initiates an audio conference dial-out call to a phone number in France—a Zone A country/region, the system bills it at the same per-minute rate.

| Meeting organizer license usage location | Destination dialed | Can I use my dial-out minute pool minutes? | Do I need Communications Credits? |
| --- | --- | --- | --- |
| United States | United States | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
| United States | United Kingdom | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
| United States | Zimbabwe | No | Yes on *ALL* calls |
| United Kingdom | United Kingdom | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
| United Kingdom | United States | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
| United Kingdom | Zimbabwe | No | Yes on *ALL* calls |
| Zimbabwe | Zimbabwe | No | Yes on *ALL* calls |
| Zimbabwe | United States | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
| Zimbabwe | United Kingdom | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
| Cook Islands | Cook Islands | No | Yes on *ALL* calls |
| Cook Islands | United States | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
| Cook Islands | United Kingdom | Yes (Zone A country/region) | Yes *after* consuming the tenant minute pool |
|  |  |  |  |

## How are minute pools calculated?

Consider the following example. A customer purchases 115 Audio Conferencing subscription licenses and has 10 users in the United States, 100 users in the United Kingdom, and 5 users in Zimbabwe, all with Audio Conferencing subscription licenses assigned. All 115 users share a pool of (115 users x 60 min = 6,900 conferencing dial-out minutes per calendar month) to place outbound calls to non-premium numbers in any of the [Zone A countries and regions](audio-conferencing-zones), *regardless* of where the meeting organizer is licensed or physically located. For example, a Zimbabwe meeting organizer can dial out to any of the [Zone A countries and regions](audio-conferencing-zones) up to the minute pool limit.

- All dial-out calls exceeding 6,900 minutes per calendar month are billed per minute using Communications Credits at our published rates to that destination.

    Note

    The customer must set up [Communications Credits](what-are-communications-credits) and assign the Communications Credits license to the meeting organizer.
- Dial-out calls to destinations outside the [Zone A countries and regions](audio-conferencing-zones) list are billed per minute at published rates using Communications Credits—provided you set up Communications Credits and assigned the license to the meeting organizer.

## How can I monitor my minute pool usage?

- You can monitor the usage against your dial-out minute pool in the Microsoft Teams admin center. In the left navigation, go to **Analytics & reports** &gt; **Usage reports**, and then select **PSTN minute pools**. The Zone A dial-out minute pool is labeled in the report as "Outbound Calls to Zone A Countries and Regions."
- Email notifications are sent to the following admins when the utilization of your organization's dial-out minutes pool reaches 80 percent and 100 percent:

    - Billing Administrator
    - Global Administrator
    - User Administrator
    - Helpdesk Administrator
    - Service Support Administrator
    - Microsoft Entra Joined Device Local Administrator
    - Application Administrator
    - License Administrator
    - Cloud Device Administrator
    - Authentication Administrator
    - Privileged Authentication Administrator
    - Teams Communications Administrator
    - Teams Communications Support Engineer
    - Teams Communications Support Specialist
    - Teams Administrator

For more information on Communication Credits, see [Communications Credits](what-are-communications-credits).