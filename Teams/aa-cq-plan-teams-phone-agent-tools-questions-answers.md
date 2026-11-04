---
layout: Conceptual
title: Planning - Questions and Answers tools for Teams Phone Agent - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-plan-teams-phone-agent-tools-questions-answers
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
customer-intent: As a Teams Administrator, I want to learn about the Questions and Answers tools feature for Teams Phone Agent so I know when and how to use it within my organization.
description: Learn how Questions and Answers tools let Teams Phone Agent answer caller questions from a knowledge base, and which sources are supported.
locale: en-us
document_id: e8eabeea-ec1d-77f0-b01d-e21be9d80216
document_version_independent_id: e8eabeea-ec1d-77f0-b01d-e21be9d80216
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-plan-teams-phone-agent-tools-questions-answers.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-plan-teams-phone-agent-tools-questions-answers
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-plan-teams-phone-agent-tools-questions-answers.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: 1acc3cfb-00c2-e366-e580-ef6f30409af1
---

# Planning - Questions and Answers tools for Teams Phone Agent - Microsoft Teams | Microsoft Learn

Important

**Teams Phone Agent is now generally available.**

Submit a brief [Teams Phone & Voice AI Interest](https://go.microsoft.com/fwlink/?LinkId=2375305) intake form to indicate your interest in exploring Teams Phone Agent & Voice AI capabilities for your business.

**We want your feedback**

Help us improve Teams Phone Agent. [Share your feedback](https://go.microsoft.com/fwlink/?LinkId=2375134) on our planning and setup documentation, the Teams admin center experience, Teams Phone Agent features, or tell us about features and improvements you’d like to see.

This article is for IT pros and Teams administrators who want to learn about the **Questions and Answers** tools feature for Teams Phone Agent.

## Knowledge bases

A knowledge base is a structured repository of information (articles) designed to help users find answers, solve problems, and understand systems or processes. It typically includes:

- FAQs and troubleshooting guides
- How-to articles and tutorials
- Product documentation
- Standard operating procedures
- Support and feedback mechanisms

Knowledge bases can be for internal or external use. They often support AI-driven tools like chatbots, Copilot agents, and virtual assistants.

In Teams Phone Agent, knowledge bases are called **Questions and Answers** tools.

## Teams Phone Agent Questions and Answers tools

A Teams Phone Agent **Questions and Answers** tool is a collection of articles, a knowledge base, from various sources.

Each **Questions and Answers** tool should only contain answers specific to the types of questions that callers ask based on the phone number they called.

If a **Questions and Answers** tool is generic in nature, then Teams Phone Agent responds with generic answers.

Important

Teams Phone Agent doesn't store a copy of the articles that make up the **Questions and Answers** tool. It maintains an abstract representation of the knowledge derived from them.

### Supported document types

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

### Supported web pages

Teams Phone Agent Questions and Answers tool articles support **public facing** web pages (URLs):

- Teams Phone Agent does not crawl the website. Only the specific page referenced by the URL is used. Links on the page are not followed.
- Highly interactive pages requiring user input are not suitable.
- Pages requiring authentication are not supported.
- Intranet pages that are only accessible within an organization are not supported. All pages must be public facing.

URLs will be rescanned/refreshed once per day.

## Best practices

- **Acronyms:** All acronyms should be defined within the document.
- **Single Language:** Files should be in a single language that matches the language that Teams Phone agent is configured for.
- **No complex formatting:** No complex or nested tables, no pivot tables in Excel.
- **No videos or images:** Documents shouldn't contain macros, videos, or graphics as these objects are ignored.
- **No sensitivity labels:** Documents must not have sensitivity labels, require passwords to open, or include restrictions from security policies. Anyone must be able to open the files.
- **Avoid conflicting information:** Ensure articles in a Questions and Answers tool contain no conflicting information, as conflicts can cause Teams Phone Agent to provide incorrect responses.
- **No Workflows:** The articles used in Teams Phone Agent Questions and Answers tool should not contain any type of workflow instructions to Teams Phone Agent.

## Licensing requirements

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)
- [Teams Phone Agent](aa-cq-reference-prerequisites-licensing#teams-phone-agent)

## Known issues

None.