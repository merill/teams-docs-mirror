---
layout: Conceptual
title: Setup - Teams Phone Agent Questions and Answers tools - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-teams-phone-agent-tools-questions-answers
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
ms.date: 2026-10-07T00:00:00.0000000Z
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
customer-intent: As a Teams Administrator, I want to set up Questions and Answers tools so I can use them with Teams Phone Agent.
description: Learn how to create a Questions and Answers tool for Teams Phone Agent in the Teams admin center, using document or URL knowledge sources.
locale: en-us
document_id: 03767b64-d67f-a862-777f-9df9c03f6d4d
document_version_independent_id: 03767b64-d67f-a862-777f-9df9c03f6d4d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-teams-phone-agent-tools-questions-answers.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-teams-phone-agent-tools-questions-answers
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-teams-phone-agent-tools-questions-answers.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7e87ede9-d550-611b-2ec6-4857c5ee46a4
---

# Setup - Teams Phone Agent Questions and Answers tools - Microsoft Teams | Microsoft Learn

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

This article is for IT pros and Teams administrators who want to create **Questions and Answers** tools for use with Teams Phone Agent.

## Planning and licensing review

### Planning

- [Questions and Answers tools for Teams Phone Agent](aa-cq-plan-teams-phone-agent-tools-questions-answers)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)

## Known issues

None.

## What's new in Teams Phone Agent (last six months)

- October 21, 2026
    - [Spam detection](aa-cq-setup-teams-phone-agent-template-spam-detection) can be configured in Teams admin center.
- October 19, 2026
    - [Copilot Credit Estimator](https://nptnlopcost-ppe-h8b6dtchacfcgqhk.b02.azurefd.net/#/estimator) now supports Teams Phone Agent.
- October 14, 2026
    - Teams Phone Agent now supports 42 voices, including 33 new ones.
- September 30, 2026
    - Teams Phone Agent is now generally available to all customers.
    - [Appointments integration with Microsoft Bookings](aa-cq-setup-teams-phone-agent-tools-appointments) can be configured in Teams admin center.
    - [Automatic Recording for Teams Phone Agent](aa-cq-setup-teams-phone-agent-template-recording-automatic) can be configured in Teams admin center.
    - [Maximum call length with configurable disconnect message](aa-cq-setup-teams-phone-agent#whats-new-configurable-call-length) can be configured in Teams admin center.
    - Question and Answers URLs are refreshed daily.
- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent updated.
- September 1, 2026
    - Appointments integration with Microsoft Bookings can be configured via PowerShell.
- August 31, 2026
    - [AI disclaimer](aa-cq-setup-teams-phone-agent#ai-disclaimer-customization) can be configured in Teams admin center.
    - [Maximum call length](aa-cq-setup-teams-phone-agent#whats-new-configurable-call-length) can be configured in Teams admin center.
- August 17, 2026
    - Automatic Recording for Teams Phone Agent can be configured via PowerShell.
- August 12, 2026
    - Spam detection can be configured via PowerShell.
    - AI disclaimer customization can be configured via PowerShell.
    - Maximum call length can be configured in PowerShell.
- July 20, 2026
    - [Historical reporting](aa-cq-report-historical) for Teams Phone Agent is now available.
- June 15, 2026
    - Entered Frontier Public Preview

## Steps to create a Questions and Answers tool for Teams Phone Agent

To create a **Questions and Answers** tool in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**.
2. Select **Templates and resources**.
3. Select **Tools**.
4. Select **Add**.

    ![Screenshot showing Tools being selected on the Templates and resources page.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-01.png)
5. Enter a **Name** and **Description** for the tool.
6. Select **Questions and Answers** as the tool type.

    ![Screenshot showing the Questions and Answers tool type when creating a new tool.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-03.png)
7. Select **Knowledge - Document** or **Knowledge - URL**.

    ![Screenshot showing the Questions and Answers tool with the option to select a document or URL.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-04.png)

    For **Knowledge - Document**:

    ![Screenshot showing the Questions and Answers tool when selecting a document.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-04-document.png)

    Teams Phone Agent Questions and Answers tool articles support the following file types:

    - DOC, DOCX (Microsoft Word)
    - JSON, HTML, XML
    - PDF
    - PPTX (Microsoft PowerPoint)
    - TXT, CSV
    - XLS, XLSX (Microsoft Excel)
    - ZIP (of any of the supported file types)

    Each Questions and Answers tool may contain a maximum of ten files, totaling no more than 5 MB in size.

    The overall size of the ZIP file is still restricted to 5 MB in size; the expanded file sizes can be larger.

    Tip

    Remember to update your Questions and Answers tools as documents are updated so that Teams Phone Agent can continue to provide the most up-to-date information to callers.

    For **Knowledge - URL**:

    ![Screenshot showing the Questions and Answers tool when selecting a URL.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-04-url.png)

    Teams Phone Agent Questions and Answers tool articles support **public facing** web pages (URLs):

    - Teams Phone Agent does not crawl the website. Only the specific page referenced by the URL is used. Links on the page are not followed.
    - Highly interactive pages requiring user input are not suitable.
    - Pages requiring authentication are not supported.
    - Intranet pages that are only accessible within an organization are not supported. All pages must be public facing.

    URLs will be rescanned/refreshed once per day.
8. Select **Save** to save your changes.

## Related Teams Phone Agent setup and configuration articles

- [Appointments](aa-cq-setup-teams-phone-agent-tools-appointments)
- [Agents and Queues](aa-cq-setup-teams-phone-agent-agents-queues)
- [Third-party voice agents](aa-cq-setup-third-party-voice-agents)
- [Holidays](aa-cq-setup-holidays)
- [Teams Phone Agents](aa-cq-setup-teams-phone-agent)

## PowerShell

For instructions on creating a Questions and Answers tool using PowerShell, see [Set up Teams Phone Agent with PowerShell](aa-cq-setup-teams-phone-agent-cmdlets).