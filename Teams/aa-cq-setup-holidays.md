---
layout: Conceptual
title: Setup - Holidays - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-holidays
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
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to create holiday schedules and routing so I can use them with Teams Phone Agent and Auto Attendant.
description: Learn how to create and change holiday schedules and call routing for use with Teams Phone Agent and auto attendants in the Teams admin center.
locale: en-us
document_id: b9908d77-78bc-ce88-ba84-4f1bd9fea504
document_version_independent_id: 37118dd4-d036-8da7-d750-4c9f503a370a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-holidays.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-holidays
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-holidays.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 831af077-e81b-fc8b-9fe7-0454968d7271
---

# Setup - Holidays - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

Caution

**Daylight Savings Time changes – Manual changes to auto attendant time zones required by some customers.**

On November 1, 2026, Daylight Savings Time will end in North America.

In Canada, the provinces of Alberta, British Columbia, and Manitoba will remain on Daylight Savings Time and will not move the clocks back one hour.

Customers with Teams Phone Agents serving these provinces that have time zone configurations that reference **(UTC-7:00) Mountain Time (US & Canada)**, **(UTC-8:00) Pacific Time (US & Canada)**, or **(UTC-05:00) Eastern Time (US & Canada)** must be updated as follows:

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

Customers with Teams Phone Agents serving these areas that have time zone configurations that reference **(UTC-05:00) Eastern Time (US & Canada)** should change the time zone selection to **(UTC-05:00) Bogota, Lima, Quito, Rio Branco** or **(UTC-05:00) Chetumal** as DST is not observed in these areas.

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

This article is for IT pros and Teams administrators who want to create holiday schedules and routing for use with Teams Phone Agent and Auto Attendant.

## Planning and licensing review

### Planning

- [Holidays](aa-cq-plan-holidays)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

None.

## Steps to create Holidays

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), expand **Voice**, select **Holidays**, and then select **Add**.
2. Select **New holiday**.
3. Enter a name for the holiday.
4. Select **Add new date**.
5. Under **Start time**, select the calendar icon and choose the date when you'd like the holiday to begin.
6. Use the dropdown list to select a start time for the holiday.
7. Under **End time**, select the calendar icon and choose the date when you'd like the holiday to end.
8. Use the dropdown list to select an end time for the holiday. The **End time** must be after the **Start time**.

    Note

    If the holiday is for one full day (that is, a 24-hour period), the **End time** should be set to the next day and the time to 12:00 AM. For example, if your organization is closed on January 1 for New Year's Day, set the **Start time** to January 1 at 12:00 AM and the **End time** to January 2 at 12:00 AM.
9. Optionally, add more dates for recurring holidays. Up to 50 separate date ranges can be added to a single holiday.
10. Select **Save**.

[![Screenshot showing configured holidays.](media/aa-cq/aa-cq-setup-holidays.png)](media/aa-cq/aa-cq-setup-holidays.png#lightbox)

## Change a holiday

To change a holiday:

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), expand **Voice**, and then select **Holidays**.
2. Select the holiday from the list.
3. Under **Start time**, select the calendar icon and choose the date when you'd like the holiday to begin.
4. Use the dropdown list to select a start time for the holiday.
5. Under **End time**, select the calendar icon and choose the date when you'd like the holiday to end.
6. Use the dropdown list to select an end time for the holiday. The **End time** must be after the **Start time**.
7. Select **Save**.

## Related Teams Phone Agent and Auto Attendant setup and configuration articles

- [Teams Phone Agent](aa-cq-setup-teams-phone-agent)
- [Auto Attendant](aa-cq-setup-auto-attendant)

## PowerShell

For instructions on setting up Holidays using PowerShell, see:

- [Teams Phone Agent with PowerShell](aa-cq-setup-teams-phone-agent-cmdlets)
- [Auto Attendant with PowerShell](aa-cq-setup-auto-attendant-cmdlets)