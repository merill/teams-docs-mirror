---
layout: Conceptual
title: Planning - Appointment tools for Teams Phone Agent - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-teams-phone-agent-tools-appointments
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
ms.date: 2026-11-03T00:00:00.0000000Z
ms.topic: concept-article
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
customer-intent: As a Teams Administrator, I want to learn about the Appointment tools option for Teams Phone Agent so I know when and how to use it within my organization.
description: Learn how Appointments tools let Teams Phone Agent book appointments through your booking system's API.
locale: en-us
document_id: 9142049a-f8e5-ace1-da45-cb96c67c0839
document_version_independent_id: 9142049a-f8e5-ace1-da45-cb96c67c0839
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-teams-phone-agent-tools-appointments.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-teams-phone-agent-tools-appointments
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-teams-phone-agent-tools-appointments.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: f6c36fa4-8147-d2d4-03f7-dd4b8256edc8
---

# Planning - Appointment tools for Teams Phone Agent - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

This article is for IT pros and Teams administrators who want to learn about the **Appointments** tools option for Teams Phone Agent.

## Appointments

Organizations can use [Microsoft Bookings](/en-us/microsoft-365/bookings/bookings-overview), or a third-party appointment scheduling systems and have Teams Phone Agent automate appointment bookings for callers.

## Microsoft Bookings

Teams Phone Agent can use any existing shared booking page in Microsoft Bookings.

## Custom appointment booking system requirements

Setting up an appointment booking system is done through Application Programming Interface (API) endpoints. There are four main API endpoints that need to be configured for appointments to work:

1. Authentication
2. Availability
3. Booking the appointment
4. Retrieving upcoming appointments

There are five optional API endpoints you can also configure depending on your scenario:

1. Generating an Auth Token
2. Getting caller details
3. Initiating caller authentication
4. Updating appointments
5. Deleting appointments

### Custom booking system best practices

We highly recommend using [Power Automate](/en-us/training/powerplatform/power-automate), which sits between your booking system and Teams Phone Agent. For example, we used Power Automate as our booking system tool because Microsoft Bookings doesn't have the required built-in capabilities to handle the Teams Phone Agent appointment booking system requirements (authentication validation, and so on).

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)
- [Teams Phone Agent with Power Automate](aa-cq-reference-prerequisites-licensing#teams-phone-agent-with-power-automate)

## Prerequisites

A booking system that supports public-facing API endpoints for the appointment booking system requirements listed earlier.

## Known issues

None.