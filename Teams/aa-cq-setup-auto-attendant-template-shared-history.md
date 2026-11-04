---
layout: Conceptual
title: Setup - Shared Call History template for Auto Attendant - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-auto-attendant-template-shared-history
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-08-31T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to learn how to set up a Shared Call History template for auto attendants.
description: Learn how to set up a Shared Call History template for auto attendants and assign it to an auto attendant.
locale: en-us
document_id: 7c30e432-aac0-393b-7ea1-14a975ea7fd3
document_version_independent_id: 7c30e432-aac0-393b-7ea1-14a975ea7fd3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-auto-attendant-template-shared-history.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-auto-attendant-template-shared-history
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-auto-attendant-template-shared-history.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: bced9d62-9bd4-527a-7480-c97fea067919
---

# Setup - Shared Call History template for Auto Attendant - Microsoft Teams | Microsoft Learn

Caution

**Daylight Savings Time changes – Manual changes to auto attendant time zones required by some customers.**

On November 1, 2026, Daylight Savings Time will end in North America.

In Canada, the provinces of Alberta, British Columbia, and Manitoba will remain on Daylight Savings Time and will not move the clocks back one hour.

Customers with auto attendants serving these provinces that have time zone configurations that reference **(UTC-7:00) Mountain Time (US & Canada)**, **(UTC-8:00) Pacific Time (US & Canada)**, or **(UTC-05:00) Eastern Time (US & Canada)** must be updated as follows:

- Alberta: Permanently moves to UTC-6:00.

    - Change the auto attendant time zone selection from **(UTC-7:00) Mountain Time (US & Canada)** to **(UTC-6:00) Saskatchewan** as DST is not observed in Saskatchewan.
- British Columbia: Permanently moves to UTC-7:00.

    - Change the auto attendant time zone selection from **(UTC-8:00) Pacific Time (US & Canada)** to **(UTC-7:00) Arizona** as DST is not observed in Arizona.
- Manitoba: Permanently moves to UTC-5:00.

    - Change the auto attendant time zone selection from **(UTC-05:00) Eastern Time (US & Canada)** to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

In Ontario, the following communities and areas will not turn clocks back and will remain on Central Daylight Time year‑round:

- Kenora
- Dryden
- Fort Frances
- Sioux Lookout
- Red Lake
- Rainy River
- Other communities west of the 90th meridian that currently follow Central Time and change clocks seasonally

Customers with auto attendants serving these areas that have time zone configurations that reference **(UTC-05:00) Eastern Time (US & Canada)** should change the time zone selection to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

This article is for IT pros and Teams administrators who want to set up Shared Call History for auto attendants.

## Planning and licensing review

### Planning

- [Shared Call History](aa-cq-plan-shared-call-history)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Queues App](aa-cq-reference-prerequisites-licensing#queues-app)

## Known issues

None.

## What's new in Auto Attendant (last six months)

- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) updated.

## Shared Call History template

The Shared Call History template is used for both call queues and auto attendants.

This Shared Call History for auto attendants article describes the auto attendant options highlighted in the following image:

![Screenshot showing the Shared Call History template with the auto attendant portion highlighted.](media/aa-cq/aa-cq-setup-auto-attendant-shared-history.png)

See [Shared Call History for call queues](aa-cq-setup-call-queue-template-shared-history) for details on configuring Shared Call History for call queues.

## Auto attendants - shared voicemail

Authorized users and voicemail group members can see an evolving history of shared voicemails.

Note

Authorized users and voicemail group members require Queues App to see the Shared Call History for auto attendant information.

## Shared Call History templates

A Shared Call History template defines who can see the auto attendant shared voicemail history.

The same Shared Call History template can be used across multiple auto attendants.

When a Shared Call History template is changed, all the auto attendants that reference the template are also changed.

### Create the Shared Call History template

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Templates and resources**.
2. Select **Templates**.
3. Select **Shared Call History** as the template type.
4. Select **Add** to create a new Shared Call History template.
5. Enter a name for the template.
6. Enter a description for the template.
7. Select the appropriate **Auto attendant and shared voicemails permissions** level.
8. Select **Save**.

### Assign the template to the auto attendant

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Auto attendants**.
2. Select the auto attendant you want to configure Shared Call History for.
3. At any location where calls are redirected to **Voicemail**, the **Shared Call History template** is shown.
4. Select the appropriate Shared Call History template from the dropdown.
5. Select **Submit**.

Note

It's not possible to have a different Shared Call History template on the Business hours, After hours, or Holiday call flows if the same shared voicemail destination is used.