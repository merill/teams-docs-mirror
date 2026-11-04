---
layout: Conceptual
title: Acquire phone numbers for your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-phone-numbers-landing-page
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: julienp
ms.date: 2026-05-28T00:00:00.0000000Z
ms.topic: article
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: Medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: Learn how to get telephone numbers for Microsoft Teams for your organization.
locale: en-us
document_id: 83357059-7998-84aa-32ee-655c18a60fcd
document_version_independent_id: 74646315-46b3-1265-4517-a618219db2e3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-phone-numbers-landing-page.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-phone-numbers-landing-page
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-phone-numbers-landing-page.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e75361a2-731b-a980-eb24-245551131177
---

# Acquire phone numbers for your organization - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Microsoft Calling Plans, Operator Connect, Teams Phone Mobile, and Direct Routing

This article provides an overview and considerations for getting phone numbers in Microsoft Teams.

Telephone numbers aren't included with [Teams Phone licensing](teams-phone-licensing). Telephone numbers for your tenant are acquired through the service provider that provides your tenant with connectivity and access to the Public Switched Telephone Network (PSTN).

Once you get a PSTN connection to your tenant, you can then acquire telephone numbers from the service provider and assign the numbers to accounts that are licensed to use Teams Phone.

To learn more about the PSTN integrations available to you, see [PSTN Connectivity options](pstn-connectivity).

Once numbers are acquired and available in your tenant, they can be managed in the following administrative tools:

- Teams admin center (TAC)
- Teams PowerShell
- On-premises Active Directory (for Direct Routing on-premises numbers)

To learn more, see [Manage phone numbers for users](assign-change-or-remove-a-phone-number-for-a-user).

## Prerequisites

Before you can get telephone numbers in Teams, you must have a phone number services agreement and a tenant integration with one or more PSTN service providers. To learn more, see [PSTN Connectivity options](pstn-connectivity).

## Number usage types

Number usages define the services that support a given phone number. The following table lists the number usage types supported with Microsoft Teams Phone.

| Number usage | Usage type and purpose | Number type supported |
| --- | --- | --- |
| **User** | User (subscriber) These numbers are for users or devices in your organization. | Geographic (Toll) |
| **Voice app** | Call queue and Auto attendant Voice app service numbers are for assigning to resource accounts that support voice applications. | Geographic (Toll) Toll-free |
| **Conference** | Dedicated conference bridge Conference service numbers are for assigning to conference bridges so that users can dial-by-phone into a Teams meeting. | Geographic (Toll) Toll-free |

### Acquiring and managing telephone numbers

How you acquire and manage telephone numbers depends on your PSTN connectivity solution. Use the following table to learn more about how to acquire numbers for your tenant:

| PSTN connectivity solution | Guidance for acquiring and managing numbers |
| --- | --- |
| Microsoft Calling Plan | [Get phone numbers with Microsoft Calling Plans](getting-phone-numbers-for-your-users) |
| Operator Connect | [Get phone numbers with Operator Connect](get-phone-numbers-with-operator-connect) |
| Teams Phone Mobile | [Get phone numbers with Teams Phone Mobile](operator-connect-mobile-configure#step-2-manage-phone-numbers-and-assign-licenses) |
| Direct Routing | [Get phone numbers with Direct Routing](get-phone-numbers-with-direct-routing) |