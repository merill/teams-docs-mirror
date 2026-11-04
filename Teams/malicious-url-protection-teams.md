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
author: marina-hayrapetyan
ms.author: mhayrapetyan
manager: ktsuji
ms.date: 2025-11-04T00:00:00.0000000Z
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

Link Protection helps to safeguard users from malicious URLs shared in chats, channels, and meeting messages. This feature helps protect your organization from phishing and other link-based threats by automatically displaying warnings when potentially harmful links are detected in Teams conversations.

## How Link Protection works in Teams

At a high level, here's how Link Protection works in Microsoft Teams:

1. A user sends a message containing a URL in a chat, channel, or meeting conversation.
2. Teams automatically scans the URL against threat intelligence databases to identify potentially malicious links.
3. If a harmful link is detected, Teams displays clear warnings to both the sender and all recipients in the conversation.

## User experience in Teams

### Sender experience

When you send a message containing a potentially malicious URL, you can:

- See a clear warning that the shared link is flagged as potentially harmful.
- Receive detailed information about why the link was flagged (for R3 users) or a generic warning (for R4 users).
- Retain the ability to edit or delete the message if desired.
- Modify the message to remove or replace the problematic link.

[![Screenshot of message of malicious URL for sender.](media/sender-msg-malicious-url-protect.png)](media/sender-msg-malicious-url-protect.png#lightbox)

### Receiver experience

As a receiver, when someone sends you a message with a flagged URL, you can:

- See a clear warning before any interaction with the flagged link.
- Receive information about the potential threat to help make informed decisions.
- Choose whether to proceed with caution or avoid clicking the link entirely.
- Receive different levels of detail, depending on your Teams client version (R3 users see detailed explanations, R4 users see generic "This message was flagged" warnings).

[![Screenshot of message of flagged URL.](media/receiver-msg-flagged-url.png)](media/receiver-msg-flagged-url.png#lightbox)

### External collaboration experience

When collaborating with users from external organizations, Malicious URL Protection in external conversations follows these rules:

- If any participating organization in the conversation has URL protection enabled, it applies to everyone.
- Warning messages display for all participants when any participating organization has turned on the feature.

## Manage Malicious URL Protection in Teams

For **new tenants** this protection is included as part of Microsoft Teams baseline security posture. Administrators do not need to configure any setting to activate malicious URL protection. 

For **existing tenants** that still display the setting, administrators can review or modify the configuration using the Teams admin center.

To enable Link Protection using the Teams Admin Center:

1. Sign in to the Teams Admin Center at [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com/).
2. In the left navigation, select **Messaging settings**.
3. Scroll down to **Messaging safety** settings.
4. Turn on the setting: **Scan messages for unsafe URLs**.
5. Select **Save** to apply the changes.

[![Screenshot of enabling Link Protection using Teams admin center.](media/links-protection-teams-msg.png)](media/links-protection-teams-msg.png#lightbox)

Once enabled, all users in the tenant can have Link Protection applied to their Teams messages.

## FAQs

- What's the difference between this feature, [Safe Links for Teams in Microsoft Defender for Office 365](/en-us/defender-office-365/safe-links-about#safe-links-settings-for-microsoft-teams), and [zero-hour auto purge (ZAP) for Teams in Microsoft Defender for Office 365 Plan 2](/en-us/defender-office-365/zero-hour-auto-purge#zero-hour-auto-purge-zap-in-microsoft-teams)?
- **Malicious URL protection**:

    - Is available for all Teams users as part of base protection.
    - Doesn't block links on click.
    - Adds warnings to messages to inform users about link reputation.
    - Doesn't require additional licenses.
- **Safe Links**:

    - Blocks URLs at the time of click based on your Microsoft Defender portal settings
    - Requires Microsoft Defender licenses
- **Zero-hour auto purge (ZAP)**:

    - Removes malicious URL and content entirely for internal messages.
    - Actions are based on your settings in the Microsoft Defender portal.
    - Requires Microsoft Defender for Office 365 Plan 1 or Plan 2 license.

    The differences are summarized in the following table:

    | Feature | Malicious URL Protection | Safe Links | ZAP for Teams |
    | --- | --- | --- | --- |
    | **Availability** | All Teams users (base protection) | Requires Defender for Office 365 Plan 1 or Plan 2 license. | Requires Defender for Office 365 Plan 1 or Plan 2 license. |
    | **Action** | Displays warning | Blocks on click. | Removes content. |
    | **Configuration** | Automatic | Microsoft Defender portal. | Microsoft Defender portal. |