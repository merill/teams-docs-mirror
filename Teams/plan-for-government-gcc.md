---
layout: Conceptual
title: Microsoft 365 Government - GCC deployments - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/plan-for-government-gcc
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: daro
ms.date: 2018-07-16T00:00:00.0000000Z
audience: admin
description: Guidance for IT pros to drive Microsoft 365 deployments in entities that handle data subject to US government regulation
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
locale: en-us
document_id: e7faee29-6d56-f3bf-766c-6deaefe92e34
document_version_independent_id: 6029b6f8-7d49-6474-fa40-2793000c74a4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/plan-for-government-gcc.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: plan-for-government-gcc
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/plan-for-government-gcc.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 8825c50d-a279-4ec3-b9bb-790785c30f39
---

# Microsoft 365 Government - GCC deployments - Microsoft Teams | Microsoft Learn

This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements. New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://download.microsoft.com/download/a/7/3/a73633b9-9be8-42b2-adc3-7809ad924495/Quick-Start-Guide-for-GCC.pdf).

Note

If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.

## Step 1: Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.

The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).

In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:

- Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.
- Your organization's customer content is stored within the United States.
- Access to your organization's customer content is restricted to screened Microsoft personnel.
- Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.

You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

The [Microsoft 365 US Government service description](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.

Tip

You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**. Then you can review this list with your colleagues to confirm that this service meets your organization's needs.

| - | - |
| --- | --- |
| ![An icon depicting decision points.](media/audio_conferencing_image7.png)Decision points | - Decide whether Microsoft 365 Government - GCC is appropriate for your organization.<br>- Confirm that your organization meets eligibility requirements. |

Note

Microsoft 365 Government - GCC is only available in the United States. Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).

## Step 2: Apply for Microsoft 365 Government - GCC

Having decided that this service is right for your organization, start the process of [applying for this service here](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy).

## Step 3: Understand Microsoft 365 Government - GCC default security settings.

We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.

| - | - |
| --- | --- |
| ![An icon depicting a decision point.](media/audio_conferencing_image7.png)Decision point | - Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make. |

## Step 4: Understand which capabilities are currently unavailable or disabled by default.

To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans. Refer to the following table to see which features are available.

[Microsoft Teams service description](/en-us/office365/servicedescriptions/teams-service-description)

Note

Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional integration work is completed.

| - | - |
| --- | --- |
| ![An icon depicting a decision point.](media/audio_conferencing_image7.png)Decision point | - Decide whether the Teams feature set meets your organization's needs. |

## Step 5: Plan for governance

Determine your requirements for governance and how you can meet them. Go to [Plan for governance in Teams](plan-teams-governance) for more information.

| - | - |
| --- | --- |
| ![An icon depicting a decision point.](media/audio_conferencing_image7.png)Decision point | - Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance). |

## Step 6: Deploy Teams for collaboration

After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](deploy-overview). Be sure to engage with your Adoption and Change Management team and Teams champions.

You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.

## Step 7: Deploy Teams for meetings and voice

This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-landing-page).