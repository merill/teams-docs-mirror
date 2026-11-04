---
layout: Conceptual
title: Data, privacy, and security for intelligent recap in Teams Premium - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/privacy/intelligent-recap
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: divyasrirk
author: DivySri-RK
manager: prgholve
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: meajam,stbyer
audience: ITPro
ms.collection:
- privacy-teams
- must-keep
description: Learn about what content is used to provide intelligent recap and how intelligent recap uses AI
ms.localizationpriority: medium
ms.date: 2023-11-08T00:00:00.0000000Z
locale: en-us
document_id: d5ccc00b-dc6f-a2f3-4a4e-5bb55a308dd5
document_version_independent_id: d5ccc00b-dc6f-a2f3-4a4e-5bb55a308dd5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/privacy/intelligent-recap.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: privacy/intelligent-recap
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/privacy/intelligent-recap.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0b29b3b8-325c-b89d-2176-9c7075e0c7a5
---

# Data, privacy, and security for intelligent recap in Teams Premium - Microsoft Teams | Microsoft Learn

Intelligent recap uses AI to automatically provide a comprehensive overview of your meeting, helping users save time catching up and coordinating next steps. Found on the **Recap** tab in Teams calendar, meeting chat, and in the Meeting Recaps app, users see AI-powered insights like automatic generated meeting notes, suggested tasks, and personalized highlights to help them quickly find the most important information, even if they miss the meeting.

Intelligent recap is available as part of Teams Premium, which is an add-on license that provides additional features to make Teams meetings more intelligent, engaging, and protected. To get access to Teams Premium, users should contact the IT admin of their organization.

For an overview of intelligent recap, see [Meeting recap in Microsoft Teams](https://support.microsoft.com/office/c2e3a0fe-504f-4b2c-bf85-504938f110ef), or you can watch the [How to use Intelligent recap in Microsoft Teams Premium](https://www.youtube.com/watch?v=n-ub_VdpkAI) video.

## What content is used to provide intelligent recap and where is it stored?

To use intelligent recap users must enable [meeting transcription](https://support.microsoft.com/office/dc1a8f23-2e20-4684-885e-2152e06a4a8b) and [recording](https://support.microsoft.com/office/34dfbe7f-b07d-4a27-b4c6-de62f1348c24), which admins can manage with [Recording & transcription meeting policies](../settings-policies-reference#related-articles-for-recording--transcription-policies) in the Teams admin center. For meetings that have both recording and transcript enabled, a copy of the transcript is stored in the meeting organizer’s Exchange Online account as well as a copy stored in OneDrive along with the recording. For meetings that only have transcript enabled, a copy of the transcript is stored in the organizer’s Exchange online account. For more information, see the following articles:

- [Configure transcription and captions for Teams meetings](../meeting-transcription-captions)
- [Delete the transcript](https://support.microsoft.com/office/dc1a8f23-2e20-4684-885e-2152e06a4a8b#bkmk_delete)
- [Delete a video's transcript and captions file](https://support.microsoft.com/office/da0c37a4-b32b-4394-9ab7-e975ab94a0f2)

The following table shows what content is used to provide intelligent recap and where that content is stored. All the features listed in the table follow the meeting recording retention policy. For more information, see [Teams meeting recording](../meeting-recording?tabs=meeting-policy) and [Learn about retention for Microsoft Teams](/en-us/purview/retention-policies-teams).

| Feature | Description | Created from | Stored in |
| --- | --- | --- | --- |
| AI-generated notes | Understand key points from the discussion | Meeting transcript | AI-generated notes are stored in an Exchange folder in the mailboxes of the meeting participants. |
| AI-generated tasks | Understand suggested tasks and who they’re assigned to | Meeting transcript | AI-generated tasks are stored in an Exchange folder in the mailboxes of the meeting participants. |
| Personalized timeline markers | Video markers for when your name was mentioned | - Meeting transcript  - User display name | Video markers for when your name was mentioned are stored in an Exchange folder in the mailboxes of the meeting participants. |
|  | Video markers for when a screen was shared | - Meeting transcript  - Meeting recording | Video markers for when a screen was shared are stored in OneDrive or SharePoint together with the meeting recording. |
|  | Video markers for when you joined or left the meeting | - Meeting transcript  - Attendance report | Video markers for when you joined or left the meeting are stored in an Exchange folder in the mailboxes of the meeting participants. |
| Speaker timeline markers | Speaker timeline markers allow you to jump to different speakers. Organized by those you work most closely with. | Meeting transcript | Speaker timeline markers are stored in an Exchange folder in the mailboxes of the meeting participants. |
| Auto-generated chapters and topics | Chapters and topics divide the meeting into sections so it’s easy to jump right to where you would like to review. | - Meeting transcript  - PowerPoint Live | Chapters and topics are stored in OneDrive or SharePoint together with the meeting recording. |

## How Microsoft uses data to provide intelligent recap

Customer data isn‘t logged or used for any AI model training or testing.

Intelligent recap automatically inherits your organization’s security, compliance, and privacy policies for Microsoft Teams.

Intelligent recap abides by Microsoft’s commitments to data security and privacy in the enterprise. Data is managed in accordance with our current commitments, while the existing compliance boundaries and privacy protections make intelligent recap the AI solution you can trust. For more information, see [regional and country compliance information on the Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/regional-country-compliance).

Intelligent recap also abides by Microsoft’s commitments to data residency in the enterprise. Data in Teams resides in the geographic region associated with your Microsoft 365 (or Office 365) organization. Intelligent recap is also [multi-geo](/en-us/microsoft-365/enterprise/microsoft-365-multi-geo) capable, for tenants that span multiple geographic locations. To review Microsoft’s data residency policy and documentation, see [Data Residency Overview and Definitions](/en-us/microsoft-365/enterprise/m365-dr-overview).

## What parts of intelligent recap are using OpenAI’s GPT Model?

Currently, only AI-generated notes and AI-generated tasks in intelligent recap use a GPT model from Open AI through [Azure OpenAI Service](https://azure.microsoft.com/products/ai-services/openai-service/). However, more AI-based features might leverage GPT in future versions of Teams Premium.

Customer data isn’t shared with non-Microsoft parties, including with Open AI. Microsoft runs the GPT-based models internally using a dedicated GPT service (Azure OpenAI). This dedicated service runs within the compliance boundaries that are used only for Microsoft 365 (and Office 365) services. AI-generated notes and AI-generated tasks call this dedicated and compliant GPT service, as well as other internal AI models, to produce AI-generated notes and tasks.