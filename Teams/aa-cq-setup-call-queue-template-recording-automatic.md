---
layout: Conceptual
title: Setup - Automatic Recording template for Call Queue - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-setup-call-queue-template-recording-automatic
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
ms.date: 2026-09-30T00:00:00.0000000Z
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
customer-intent: As a Teams Administrator, I want to set up an automatic recording for call queue template and apply it to my call queues to record inbound calls.
description: Learn how to set up an automatic recording for call queue template and apply it to your call queues to record inbound calls to SharePoint.
locale: en-us
document_id: d505ca90-cf05-7484-4526-c00f30218549
document_version_independent_id: d505ca90-cf05-7484-4526-c00f30218549
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-setup-call-queue-template-recording-automatic.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-setup-call-queue-template-recording-automatic
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-setup-call-queue-template-recording-automatic.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 09783259-537e-eaef-ecca-d9f0bd075f58
---

# Setup - Automatic Recording template for Call Queue - Microsoft Teams | Microsoft Learn

This article is for IT pros and Teams administrators who want to configure automatic recording and transcription for inbound call queue calls.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Recording calls](aa-cq-plan-recording#automatic-recording-for-call-queue)
- [Getting started](aa-cq-reference-getting-started)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Known issues

- Changes to the SharePoint site structure, file names, or permissions can cause access issues, permission errors, or automatic recording failures.
- To assign an automatic recording template to a call queue or manage its authorized users list, the Teams administrator must also be a SharePoint site administrator for the site used by the template. See [Call queue management and SharePoint interaction](aa-cq-setup-call-queue-template-recording-automatic#call-queue-management-and-sharepoint-interaction) on how to avoid this issue.
- [Explicit recording consent](participant-agreement-recording-transcription) must be **Off**.

## Prerequisites

Important

Users require [Queues App](manage-queues-app) to access the features described in this article. See [Queues App licensing](aa-cq-reference-prerequisites-licensing#queues-app).

- Ensure SharePoint site creation is enabled in the tenant (default is on). [Manage site creation in SharePoint](/en-us/sharepoint/manage-site-creation).
- The SharePoint host must have been visited at least once prior to creating the template.
- [Conference mode](aa-cq-setup-call-queue#conference-mode) is enabled on the call queue.
- [Call answering](aa-cq-setup-call-queue#step-3-call-answering)must use a group or channel.
    - Users and Shifts are not supported
- [Shared Call History](aa-cq-setup-call-queue-template-shared-history)in enabled on the call queue.
    - With Shared Call History enabled, authorized users and representatives (agents) will be able to access the recordings and transcriptons through Queues App.

## What's new in Call Queues (last six months)

- October 19, 2026
    - Monitor, Whisper, Barge, Takeover for authorized users now supports outbound calls.
- September 30, 2026
    - [Automatic Recording for Call Queue](aa-cq-setup-call-queue-recording-automatic) can be configured in Teams admin center.
- September 29, 2026
    - [Historical reporting](aa-cq-report-historical) updated.
- August 17, 2026
    - Assigning templates to a call queue has moved to the new **Templates** step.
    - [Compliance Recording for Call Queues](aa-cq-setup-call-queue-template-recording-compliance) configuration is now available in Teams admin center.
- August 13, 2026
    - Automatic Recording for Call Queue can be configured via PowerShell.

## Call queue management and SharePoint interaction

The Teams administrator creating the automatic recording template becomes the SharePoint site admin of the template's associated site.

Tip

Microsoft recommends that all other Teams administrators be configured as SharePoint site admins. This will prevent issues when trying to reuse the SharePoint site in other templates or when trying to manage the authorized users on call queues with an automatic recording for call queue template assigned.

## Automatic Recording template for Call Queue

An automatic recording template for Call Queue defines where, in SharePoint, recordings and transcripts will be stored, the prompts played to callers to let them know that recording is enabled, and defines who has access to the recordings.

An automatic recording template for Call Queue can be reused across multiple call queues.

### Create the automatic recording template for Call Queue

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Templates and resources**.
2. Select **Templates**.
3. Select **Automatic Recording** as the template type.
4. Select **Add** to create a new Automatic Recording template.
5. Enter a **Name** for the template.
6. Enter a **Description** for the template.
7. Call recording is enabled by default. Disable call recording if required.
8. Transcription is enabled by default. Disable transcription if required.
9. Select which call recordings call queue representatives (agents) can access. Authorized users have access by default.
    - For the best experience, it is recommended to use Queues app with shared call history enabled to access the recordings.
    - **This setting can't be modified once the template is created.**
10. Use the **Default** announcement or configure a **Custom announcement**.
    - The default announcement is: `This call will be recorded.`
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

### Assign the template to the call queue

1. In the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851), go to **Voice** &gt; **Call queue**.
2. Select the call queue you want to have automatic recording for.
3. On the **Templates** tab, scroll to find the **Automatic recording template** section.
4. Select the automatic recoding template template from the dropdown.
5. Select **Submit**.