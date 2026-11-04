---
layout: Conceptual
title: Weaponizable file protection in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/weaponizable-file-protection-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: marina-hayrapetyan
ms.author: mhayrapetyan
manager: ktsuji
ms.date: 2025-09-08T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: 
description: Learn about weaponizable file protection in Microsoft Teams.
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
document_id: d9eda956-a869-7b4a-2b25-d2a6418a9cde
document_version_independent_id: d9eda956-a869-7b4a-2b25-d2a6418a9cde
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/weaponizable-file-protection-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: weaponizable-file-protection-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/weaponizable-file-protection-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 19557364-f1bb-904f-9f54-c4ee347e5fe2
---

# Weaponizable file protection in Microsoft Teams - Microsoft Teams | Microsoft Learn

Enhanced security protection in Microsoft Teams automatically blocks messages containing potentially weaponizable file types in chats and channels. This feature helps protect your organization from file-based attacks by preventing unsafe content from being shared in Teams conversations.

## How file type protection works in Teams

At a high level, here's how the new file protection feature works in Microsoft Teams:

1. A user attempts to send a message containing an attachment with a weaponizable file type.
2. Teams automatically scans the message and identifies files with weaponizable extensions.
3. If a blocked file type is detected, Teams prevents the message from being delivered and displays appropriate notifications to both sender and recipients.

## User experience in Teams

### Sender experience

If you send a message containing a weaponizable file, both the file attachment and the complete message content are blocked. As the sender, you can:

- See a blocked message indicator in your chat or channel.
- Receive a clear notification explaining why the message was blocked.
- Have the option to edit the original message to remove the unsafe file.
- Resend the message once the problematic file is removed.

[![Screenshot for sender that a message and file blocked.](media/file-msg-blocked.png)](media/file-msg-blocked.png#lightbox)

### Receiver experience

As a receiver, when someone attempts to send you a message with a disallowed file type, you can:

- See an indication that a message was blocked due to security concerns.
- Not have access to view the blocked message content or download the file.
- Receive different levels of detail depending on your Teams client version.

### [![Screenshot for receiver that a message with file is blocked.](media/receiver-file-msg-blocked.png)](media/receiver-file-msg-blocked.png#lightbox) External collaboration

When collaborating with users from external organizations, Weaponizable File Protection follows these rules:

- If any organization in the conversation has File protection enabled, it applies to everyone.
- Messages containing blocked file types will be blocked for all, when any participating organization has turned on the feature.

## Turn off or turn on file protection through Teams Admin Center

To enable file protection using the Teams Admin Center:

1. Sign in to the Teams Admin Center at [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com/).
2. In the left navigation, select **Messaging settings**.
3. Scroll down to **Messaging safety** settings.
4. Turn on the setting: **Scan messages for file types that are not allowed**.
5. Select **Save** to apply the changes.

[![Screenshot to turn on file protection using Teams admin center.](media/teams-admin-center-file-protection.png)](media/teams-admin-center-file-protection.png#lightbox)

Once enabled, all users in the tenant will have file protection applied to their Teams messages.

### Turn off or turn on file protection through PowerShell

You can also configure file protection using PowerShell with the Teams module:

```powershell
Set-CsTeamsMessagingConfiguration -FileTypeCheck "Enabled" -Identity Global
```

## Blocked file types

Teams file protection blocks the following file extensions that are commonly associated with malware and security threats:

`ace, ani, apk, app, appx, arj, bat, cab, cmd, com, deb, dex, dll, docm, elf, exe, hta, img, iso, jar, jnlp, kext, lha, lib, library, lnk, lzh, macho, msc, msi, msix, msp, mst, pif, ppa, ppam, reg, rev, scf, scr, sct, sys, uif, vb, vbe, vbs, vxd, wsc, wsf, wsh, xll, xz, z`

The list of blocked file types isn't currently configurable by administrators.