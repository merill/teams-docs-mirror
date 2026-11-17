---
layout: Conceptual
title: Malicious URL protection in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/malicious-url-protection-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.date: 2026-11-16T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: 
description: Learn about malicious URL protection in Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- teams-security
- trust-pod
ms.custom:
- Security
locale: en-us
document_id: 6a097da4-3bb8-8f28-59dd-c2520a53cc3d
document_version_independent_id: 6a097da4-3bb8-8f28-59dd-c2520a53cc3d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/malicious-url-protection-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: malicious-url-protection-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/malicious-url-protection-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c1bc8fad-bd4c-b5a3-6e58-de6ecbe9c0b2
---

# Malicious URL protection in Microsoft Teams - Microsoft Teams | Microsoft Learn

Malicious URL protection helps safeguard users from malicious URLs shared in Teams chats, channels, and meeting messages, including URLs in QR codes. This feature helps protect your organization from phishing and other link-based threats by automatically displaying warnings when potentially harmful links are detected in Teams conversations.

## How malicious URL protection works

At a high level, here's how malicious URL protection works:

1. A user sends a message that contains a URL directly or embedded in a QR code in a chat, channel, or meeting conversation.
2. Teams automatically scans the URL against threat intelligence databases to identify potentially malicious links.
3. If the URL is detected as potentially malicious, Teams displays warnings to both the sender and all recipients in the conversation.

## Manage malicious URL protection in Teams

For **new tenants**, this protection is included as part of Teams baseline security protection and doesn’t require admin configuration.

For **existing tenants** and **GCC**, **GCC High**, and **DoD tenants**, admins can turn malicious URL protection off or on in the Teams admin center. It's enabled by default.

To turn off or turn on malicious URL protection:

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com/).
2. In the left navigation, go to **Messaging** &gt; **Messaging settings**.
3. Under **Messaging safety**, turn off or turn on **Malicious URL protection**.

    [![Screenshot of the Malicious URL protection setting in the Teams admin center.](media/malicious-url-protection.png)](media/malicious-url-protection.png#lightbox)
4. Select **Save**.

This is a tenant-level setting. When enabled, all users in your organization have malicious URL protection applied to their Teams messages.

## User experience

Here's an overview of the user experience. For more information, see [Make sure chats, links, and files are secure in Microsoft Teams](https://support.microsoft.com/teams/troubleshooting/make-sure-chats-links-and-files-are-secure-in-microsoft-teams).

### Sender experience

When a user sends a message that contains a potentially malicious URL, the user:

- Sees a warning that the URL is identified as potentially harmful.

    [![Screenshot of message of malicious URL for sender.](media/sender-msg-malicious-url-protect.png)](media/sender-msg-malicious-url-protect.png#lightbox)
- Can edit or delete the message.
- Can remove or replace the problematic URL in the message.

### Receiver experience

When someone sends a message that contains a potentially malicious URL, as the recipient, the user:

- Sees a warning before any interaction with the flagged URL.

    [![Screenshot of message of flagged URL.](media/receiver-msg-flagged-url.png)](media/receiver-msg-flagged-url.png#lightbox)
- Receives information about the potential threat to help them make an informed decision.
- Can choose whether to proceed with caution or avoid the link entirely.

### External collaboration experience

When collaborating with users from external organizations, malicious URL protection follows these rules:

- If any organization in the conversation has malicious URL protection enabled, the protection applies to all participants.
- A warning message is displayed to all participants in the conversation when any organization has the feature enabled.

## How malicious URL protection differs from Safe Links and zero-hour auto purge (ZAP)

The following table summarizes the differences between malicious URL protection, [Safe Links for Teams in Microsoft Defender for Office 365](/en-us/defender-office-365/safe-links-about#safe-links-settings-for-microsoft-teams), and [zero-hour auto purge (ZAP) for Teams in Microsoft Defender](/en-us/defender-office-365/zero-hour-auto-purge#zero-hour-auto-purge-zap-in-microsoft-teams).

| - | Malicious URL protection | Safe Links | ZAP for Teams |
| --- | --- | --- | --- |
| **Availability** | All Teams users (baseline protection) | Requires Defender for Office 365 Plan 1 or Plan 2 license | Requires Defender for Office 365 Plan 1 or Plan 2 license |
| **Action** | Displays warning | Blocks on click | Removes content |
| **Configuration** | Automatic | Microsoft Defender portal | Microsoft Defender portal |

Here are more details:

- **Malicious URL protection**:

    - Is available for all Teams users as part of baseline protection.
    - Doesn't block URLs on click.
    - Adds warnings to messages to inform users about URLs identified as potentially malicious.
    - Doesn't require an additional license.
- **Safe Links**:

    - Blocks URLs at the time of click based on your Defender portal settings.
    - Requires a Microsoft Defender for Office 365 Plan 1 or Plan 2 license.
- **Zero-hour auto purge (ZAP)**:

    - Removes malicious URLs and content entirely for internal messages.
    - Actions are based on your Defender portal settings.
    - Requires a Microsoft Defender for Office 365 Plan 1 or Plan 2 license.