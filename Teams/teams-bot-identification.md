---
layout: Conceptual
title: Teams Bot Identification Program - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-bot-identification
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: jessiewa
ms.author: jessiewa
manager: jessiewa
ms.topic: integration
ms.service: msteams
ms.subservice: meetings
audience: admin
ms.reviewer: jessiewa
ms.date: 2026-06-26T00:00:00.0000000Z
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Learn about the Teams Bot Identification Program.
locale: en-us
document_id: 5c8dee86-aded-5c65-1b8c-eee1a178f686
document_version_independent_id: 5c8dee86-aded-5c65-1b8c-eee1a178f686
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-bot-identification.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-bot-identification
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-bot-identification.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1d177f67-71a7-11d5-d8c9-6f7094beee93
---

# Teams Bot Identification Program - Microsoft Teams | Microsoft Learn

## Introduction

AI note-taking and meeting-assistant tools are becoming a familiar part of the Microsoft Teams meeting experience, helping people capture important details while staying present in the conversation. At the same time, organizations need confidence that only intended people and tools are joining their meetings.

To help admins and organizers manage this more effectively, Microsoft Teams is introducing smarter bot protection for meetings. The Teams admin policy, [Manage external bots and their access to meetings](manage-external-bots), helps detect potential external bots, place them in the lobby, clearly identify them for organizers, and require explicit organizer approval before they can join.

This experience gives organizations more visibility and control over automated meeting participants. Even when a meeting allows participants to bypass the lobby, detected bots still require organizer approval before joining. Additional safeguards, such as confirmation prompts and warnings when admitting multiple participants, help reduce accidental bot admission and make bot participation more intentional.

## Microsoft Teams Bot Identification Program (Public Preview)

Microsoft is also introducing the Teams Bot Identification Program to support independent software vendors (ISVs) that build meeting bot experiences for Teams.

Through this program, eligible bot providers can register with Microsoft and include a self-identification marker in their meeting join requests. When Teams recognizes this marker, it can identify the bot as a registered participant. The program is designed to create a clearer path for registered meeting bot experiences while improving transparency for customers.

## Next steps(coming soon)

The public preview has reached its current bot provider capacity. When the program becomes generally available, we’ll publish onboarding guidance and next steps.

## Support boundaries

Microsoft doesn't provide direct support for ISV-owned bot solutions. If you experience an issue with a third-party bot, contact the ISV first for troubleshooting and support.

If the issue requires Microsoft involvement, the ISV can engage Microsoft through the appropriate partner support channels.