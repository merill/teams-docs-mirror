---
layout: Conceptual
title: Complimentary dial-out - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/complimentary-dial-out-period
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: mikedav, OscarR
ms.date: 2026-10-08T00:00:00.0000000Z
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: Low
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Learn about the complimentary dial-out for a Microsoft 365 calling plan and Audio Conferencing in Microsoft Teams.
locale: en-us
document_id: be7b92a3-be5b-fd38-fb9e-7811212386fa
document_version_independent_id: da10315a-a190-4433-1e82-d22aef8ef1a0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/complimentary-dial-out-period.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: complimentary-dial-out-period
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/complimentary-dial-out-period.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: b11915e3-d2b2-dbcc-ee90-09ddf83bf749
---

# Complimentary dial-out - Microsoft Teams | Microsoft Learn

## Teams PSTN Services

Customers may use a Microsoft 365 or Calling Plan and Teams Audio Conferencing as permitted in the Teams PSTN Services Use Terms and Customer's volume licensing agreement. The PSTN Services Use Terms may be found at [Licensing Resources and Documents](https://www.microsoft.com/licensing/docs).

### Complimentary dial out availability

The complimentary dial-out is only available in Russia, South Korea, and Taiwan, where Audio Conferencing is available, but Communications Credits setup isn't currently supported.

### Complimentary dial out details

For Audio Conferencing customers in Russia, South Korea, and Taiwan, we provide an additional complimentary benefit related to dial out from meetings that licensed Audio Conferencing users create. With complimentary dial-out, Microsoft allows meeting organizers or authorized attendees, as defined in meeting policy settings, to make dial-out calls from within the meeting to non-premium phone numbers in the 44 [Zone A countries and regions](audio-conferencing-zones). This benefit is applicable to Audio Conferencing monthly subscription licenses and doesn't extend to Audio Conferencing pay-per-minute licenses.

In addition, there's a 900-minute limit during the complimentary dial out as such:

Users with a license usage location (the location is the user country or region location that is defined in the licensing area of the Microsoft 365 admin center) in *any*\_ country or region can dial out from a conference to any of the 44 [Zone A countries and regions](audio-conferencing-zones). Each user receives 900 minutes per user per month to *any* of the [Zone A countries and regions](audio-conferencing-zones), which are pooled at the tenant level. For example, a customer has purchased 115 Audio Conferencing subscription licenses and has 10 users in the US, 100 users in the UK, and 5 users in India, all with Audio Conferencing subscription licenses assigned to their users.

- All 115 users share a pool of (115 users X 900 min) = 103,500 conferencing dial-out out minutes per calendar month, which can be used to place outbound calls to any of the [Zone A countries and regions](audio-conferencing-zones).
- All calls exceeding the 103,500 minutes per calendar month are billed per minute using Communications Credits at our published rates to that destination. (Note: Tenant must set up Communications Credits and assign the Communications Credits license to the meeting organizer).
- All outbound calls to destinations not in the [Zone A countries and regions](audio-conferencing-zones) list are billed per minute using Communications Credits at our published rates to that destination (provided tenant has set up Communications Credits and assigned the Communications Credits license to the meeting organizer).

Note

You can monitor the usage against dial-out minute pool in the Teams admin center. In the Microsoft Teams admin center, go to **Legacy portal** &gt; **Reports** &gt; **PSTN Minute Pools**. This complimentary minute pool will be labeled in the report as "Outbound Calls to Zone A countries and regions."

Email notifications are sent to all tenant administrators of a given customer when the utilization of the tenant's dial-out minutes pool has reached 80% and 100%.

For dial-out calls that are billed per minute (calls exceeding the tenant dial-out minute pool or calls to destinations not in the [Zone A countries and regions](audio-conferencing-zones) list), the calls and their associated rates are based primarily on the destination of the call and not the country or region of the organizer or the participant initiating the dial-out call. For example, a call to a phone number in France will be billed with the same rate if it's initiated by a meeting participant in the United States or one in France.

For more information about Communication Credits, see [Communications Credits](what-are-communications-credits).