---
layout: Conceptual
title: Setup - Automatic Recording for Teams Phone Agent - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-teams-phone-agent-template-recording-automatic
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: pavellatif
ms.author: pavellatif
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
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams administrator, I want to set up an automatic recording template for Teams Phone Agent and apply it to record and transcribe inbound calls.
description: Learn how to create an automatic recording template for Teams Phone Agent and apply it to record and transcribe inbound calls.
locale: en-us
document_id: 28188493-9052-1c56-a994-a4d3911de285
document_version_independent_id: 28188493-9052-1c56-a994-a4d3911de285
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-teams-phone-agent-template-recording-automatic.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-teams-phone-agent-template-recording-automatic
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-teams-phone-agent-template-recording-automatic.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e0b51fb8-6e6e-d230-2924-448e7c1f4e22
---

# Setup - Automatic Recording for Teams Phone Agent - Microsoft Teams | Microsoft Learn

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

This article is for IT pros and Teams administrators who want to create an automatic recording template for Teams Phone Agent and assign the template to a Teams Phone Agent to record and transcribe inbound calls.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Recording calls](aa-cq-plan-recording#automatic-recording-for-teams-phone-agent)
- [Getting started](aa-cq-reference-getting-started)

### Licensing

- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)
- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

- Changes to the SharePoint site structure, file names, or permissions can cause access issues, permission errors, or automatic recording failures.
- To assign an automatic recording template to a Teams Phone Agent or manage its authorized users list, the Teams administrator must also be a SharePoint site administrator for the site used by the template. See [Teams Phone Agent management and SharePoint interaction](aa-cq-setup-teams-phone-agent-template-recording-automatic#teams-phone-agent-management-and-sharepoint-interaction) on how to avoid this issue.

## Prerequisites

- Ensure SharePoint site creation is enabled in the tenant (default is on). See [Manage site creation in SharePoint](/en-us/sharepoint/manage-site-creation).
- The SharePoint host must exist and must have been visited at least once before you create the template.

## Teams Phone Agent management and SharePoint interaction

The Teams administrator creating the automatic recording template becomes the SharePoint site admin of the template's associated site.

Tip

Microsoft recommends that all other Teams administrators be configured as SharePoint site admins. This will prevent issues when trying to reuse the SharePoint site in other templates or when trying to manage the authorized users on Teams Phone Agent with an automatic recording for template assigned.

## Automatic Recording template for Teams Phone Agent

An automatic recording template for Teams Phone Agent defines where, in SharePoint, recordings and transcripts will be stored as well as the prompts played to callers to let them know that recording is enabled.

An automatic recording template for Teams Phone Agent can be reused across multiple Teams Phone Agents.

### Create the automatic recording template for Teams Phone Agent

To create an **Automatic Recording** template in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851):

1. Expand **Voice**.
2. Select **Templates and resources**.
3. Select **Templates**.
4. Select **Automatic Recording** as the template type.
5. Select **Add** to create a new Automatic Recording template.
6. Enter a **Name** for the template.
7. Enter a **Description** for the template.
8. Call recording is enabled by default. Disable call recording if required.
9. Transcription is enabled by default. Disable transcription if required.
10. Use the **Default** announcement or configure a **Custom announcement**.
    - The default announcement is: `This call will be recorded.`
    - Teams Phone Agent only supports the **greeting message** option.
11. Enter the **SharePoint host name**.
    - Example: contoso.sharepoint.com
    - The host must already exist and must have been visited in a standard browser before you create the template.
    - **This setting can't be modified once the template is created.**
12. Enter the **SharePoint site name**.
    - The site must be provisioned through the template creation process. Manually created SharePoint sites aren't supported and might cause access or permission errors. You can reuse sites provisioned through this process across multiple Automatic Recording for Teams Phone Agent templates.
    - **This setting can't be modified once the template is created.**
13. Select a user, preferably a Teams administrator, to be the **Recording Document Owner**.
    - This user can access the recording if there's a problem uploading it to SharePoint.
    - This access is only for upload failure situations.
14. Select **Save**.

### Assign the template to the Teams Phone Agent

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Auto attendants**.
2. Select the Teams Phone Agent you want to have automatic recording for.
3. On the **Templates** tab, scroll to find the **Automatic recording template** section.
4. Select the automatic recoding template template from the dropdown.
5. Select **Submit**.