---
layout: Conceptual
title: Setup - Teams Phone Agent Spam Detection - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-teams-phone-agent-template-spam-detection
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
ms.date: 2026-10-21T00:00:00.0000000Z
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
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to set up a spam detection template for teams phone agent and apply it so that teams phone agent handles spam calls in the way that I want.
description: Learn how to set up a spam detection templatee for teams phone agent and apply it so that teams phone agent handles spam calls in the way that I want.
locale: en-us
document_id: 43eac573-51c9-d881-cf14-85c5de138415
document_version_independent_id: 43eac573-51c9-d881-cf14-85c5de138415
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-teams-phone-agent-template-spam-detection.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-teams-phone-agent-template-spam-detection
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-teams-phone-agent-template-spam-detection.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d9edfabc-b117-e131-6412-3e76ee92fa09
---

# Setup - Teams Phone Agent Spam Detection - Microsoft Teams | Microsoft Learn

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

This article is for IT pros and Teams administrators who want to configure spam detection for teams phone agent calls.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Questions and Answers](aa-cq-plan-teams-phone-agent-tools-questions-answers)
- [Appointment](aa-cq-plan-teams-phone-agent-tools-appointments)
- [Agents and queues](aa-cq-plan-teams-phone-agent-agents-queues)
- [Recording calls](aa-cq-plan-recording)
- [Templates and resources](aa-cq-plan-templates-resources)
- [Nested call flows](aa-cq-plan-nesting)
- [Reporting considerations](aa-cq-plan-reporting)
- [Design call flows](aa-cq-design-call-flows)
- [Getting started](aa-cq-reference-getting-started)

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

### Create the spam detection template for Teams Phone Agent

To create a **Spam Detection** template in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**.
2. Select **Templates and resources**.
3. Select **Templates**.
4. Select **Spam Detection** as the template type.
5. Select **Add** to create a new Spam Detection template.
6. Enter a **Name** for the template.
7. Enter a **Description** for the template.
8. Spam detection is enabled by default. Disable spam detection if required.
9. Select the call routing option when spam is detected:

- **Disconnect** - the call is disconnected.
- **Transfer to Operator** - the call is transferred to the Operator. If no Operator is configured, the call is disconnected.
- **Redirect Call**- redirect the call to:
    - **Person in the organization**- a person in your organization who can receive voice calls.
        - The person must be voice enabled. For details, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).
    - **Voice app** - Choose the Auto Attendant or Call Queue when choosing this destination. The call priority can be set when the destination is a Call Queue.
    - **Resource account** - Choose the resource account associated with the Teams Phone Agent, Auto Attendant or Call Queue when choosing this destination.
    - **External phone number** - any phone number. See [Outbound calling line identification (number)](aa-cq-reference-limits-supported-configurations#outbound-calling-line-identification-number).
    - **Voicemail**- the voice mailbox associated with a Microsoft 365 group that you specify.
        - In Microsoft 365 admin center, enable **Let people outside the organization email this team** for the Microsoft 365 group that you specify.

1. Enter any phone numbers that should always be considered as spam in the **Inclusion Scope**.
2. Enter any phone numbers that should never be considered as spam in the **Exclusion Scope**.
3. Select **Save**.

### Assign the template to the Teams Phone Agent

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Auto attendants**.
2. Select the Teams Phone Agent you want to have automatic recording for.
3. On the **Templates** tab, scroll to find the **Spam Detection** section.
4. Select the spam detection template template from the dropdown.
5. Select **Submit**.