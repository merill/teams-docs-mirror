---
layout: Conceptual
title: Setup - Teams Phone Agent Appointment tools - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-teams-phone-agent-tools-appointments
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
customer-intent: As a Teams Administrator, I want to set up Appointment tools so I can use them with Teams Phone Agent.
description: Learn how to create an Appointment tool for Teams Phone Agent, including caller authentication, API authentication, and call flows.
locale: en-us
document_id: 4e0db962-ca12-5c49-e2cb-9fe591b653aa
document_version_independent_id: 4e0db962-ca12-5c49-e2cb-9fe591b653aa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-teams-phone-agent-tools-appointments.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-teams-phone-agent-tools-appointments
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-teams-phone-agent-tools-appointments.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1d6a541d-936f-6eef-94c8-b9edc6c512d5
---

# Setup - Teams Phone Agent Appointment tools - Microsoft Teams | Microsoft Learn

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

This article is for IT pros and Teams administrators who want to create **Appointment** tools for use with Teams Phone Agent.

## Planning and licensing review

### Planning

- [Appointment tools for Teams Phone Agent](aa-cq-plan-teams-phone-agent-tools-appointments)

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

## Steps to create an Appointment tool with Microsoft Bookings for Teams Phone Agent

### Create a shared booking page

To create a shared booking page in [Microsoft Bookings](https://book.ms):

1. Select **+ Create a booking page**.
2. Select **+ Create from scratch**
3. Step 1:
    - Enter a **Name** for the booking page.
    - Optionally **Add a logo**.
    - Select a **Business type**.
    - Change the **Business hours** if needed.
    - Select **Next**.
4. Step 2:
    - **Invite staff** to the booking page.
    - Select **Next**.
5. Step 3:
    - Select **Next** to accept the default service.
6. Step 4:
    - Select **Anyone** to allow callers to book an appointment.
    - Select **Create**.

Wait for the booking page to be created.

### Create an Appointment tool for Teams Phone Agent

To create an **Appointment** tool in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**.
2. Select **Templates and resources**.
3. Select **Tools**.
4. Select **Add**.

    ![Screenshot showing Tools being selected on the Templates and resources page.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-01.png)
5. Enter a **Name** and **Description** for the tool.
6. Select **Appointment** as the tool type.

    ![Screenshot showing the tool type available when creating a new tool.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-03.png)
7. Select **Microsoft shared booking**
8. Select the **Booking link** for the booking page from the drop-down list.
9. Select **Save**

The Appointment tool is now ready to be added to Teams Phone Agent.

Important

Make sure the time zone setting on the shared booking page is the same as the time zone setting in Teams Phone Agent.

## Steps to create a custom Appointment tool for Teams Phone Agent

To create an Appointment tool in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**.
2. Select **Templates and resources**.
3. Select **Add**.

    ![Screenshot showing Tools being selected on the Templates and resources page.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-01.png)
4. Enter a **Name** and **Description** for the tool.
5. Select **Appointment** as the tool type.

    ![Screenshot showing the tool type available when creating a new tool.](media/aa-cq/aa-cq-setup-teams-phone-agent-tools-questions-answers-03.png)
6. Select the **Caller authentication method**. This controls how the caller is verified.

    - **SMS** - a code is sent via SMS.
    - **Email** - a code is sent via email.
    - **User Details** - the caller is requested to provide their details on the call.
7. Select the **API authentication type**. This controls how Teams Phone Agent authenticates with the booking system endpoints.

    - **Basic (Static)** - no authentication is used.
    - **API Key (Static)**
    - **Bearer Token (Static)**
    - **Bearer Token (Dynamic)**
8. Configure the required call flows.

    Call flows are the independent steps required to authenticate callers for access to the booking system, retrieve available time slots, and book, retrieve, update, and delete appointments.

    Based on the **Caller authentication method**, the following call flows are required.

    **System authentication**

    | SMS / Email | User details |
    | --- | --- |
    | Generate auth token | Generate auth token |

    *This call flow is only required if the **API authentication type** is set to **Bearer Token (Dynamic)**.*

    **Caller authentication**

    | SMS / Email | User details |
    | --- | --- |
    | Initiate caller authentication |  |
    | Authenticate caller | Authenticate caller |

    The **Initiate caller authentication** step requests that the booking system send an email or SMS to the caller. The message should contain a one-time numeric code that the caller provides to Teams Phone Agent.

    **Book appointment**

    | SMS / Email | User details |
    | --- | --- |
    | Get available appointment time slots | Get available appointment time slots |
    | Book appointment | Book appointment |

    **Manage appointments**

    | SMS / Email | User details |
    | --- | --- |
    | Get upcoming appointments | Get upcoming appointments |
    | Update appointment | Update appointment |
    | Delete appointment | Delete appointment |
9. Select **Save** to save your changes.

The Appointment tool is now ready to be added to Teams Phone Agent.

## Related Teams Phone Agent setup and configuration articles

- [Questions and Answers](aa-cq-setup-teams-phone-agent-tools-questions-answers)
- [Agents and Queues](aa-cq-setup-teams-phone-agent-agents-queues)
- [Third-party voice agents](aa-cq-setup-third-party-voice-agents)
- [Holidays](aa-cq-setup-holidays)
- [Teams Phone Agents](aa-cq-setup-teams-phone-agent)

## PowerShell

For instructions on creating an Appointment tool using PowerShell, see [Set up Teams Phone Agent with PowerShell](aa-cq-setup-teams-phone-agent-cmdlets).