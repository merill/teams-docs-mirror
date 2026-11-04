---
layout: Conceptual
title: QR code obscuring in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/qr-code-obscuring-teams-messages
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: yilyang
ms.date: 2026-10-20T00:00:00.0000000Z
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
f1.keywords:
- NOCSH
description: Learn how QR code obscuring works in Microsoft Teams. This feature blurs QR codes in messages from external senders.
locale: en-us
document_id: 42196883-b43f-0280-87fe-b5bc6bb1b1ab
document_version_independent_id: 42196883-b43f-0280-87fe-b5bc6bb1b1ab
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/qr-code-obscuring-teams-messages.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: qr-code-obscuring-teams-messages
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/qr-code-obscuring-teams-messages.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 94ebfed4-160e-2351-aa48-34e37800233d
---

# QR code obscuring in Microsoft Teams - Microsoft Teams | Microsoft Learn

## Overview

Microsoft Teams provides additional protection for QR codes in Teams messages by obscuring images that contain QR codes by default. This experience applies to QR codes in messages from external senders. Users must explicitly reveal the image before they can view or scan the QR code.

This precautionary protection helps increase user awareness and encourages more deliberate interaction with QR code content, which can be used in phishing and fraud attempts. Obscuring QR codes helps ensure that they aren't immediately scannable without user intent.

## How QR code obscuring works in Teams

When an external user sends a message that contains an image with a QR code, Teams blurs the image.

![Screenshot of a Teams message with a blurred QR code image, showing the **Reveal QR code** option.](media/qr-code-obscuring-blur.png)

Users can select **Reveal QR code** to view or scan the QR code.

![Screenshot of a Teams message showing the QR code after a user selects **Reveal QR code** to reveal it.](media/qr-code-obscuring-reveal.png)

A blurred QR code doesn't mean that Teams identified the QR code as malicious. Teams applies this protection to reduce risk and help users make more informed decisions when interacting with QR codes.

## Key considerations

- This experience is enabled by default, and there are no admin controls to enable or disable it.
- This experience applies to QR codes in Teams messages sent by external users.
- This experience is supported on Teams desktop, web, and mobile clients.

Note

For users in China on Teams mobile, this experience applies to QR codes in messages sent by both internal and external users.