---
layout: Conceptual
title: Collect log files for monitoring and troubleshooting in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/log-files
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: mastank
ms.date: 2024-09-11T00:00:00.0000000Z
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.subservice: msteams-admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- asset-status-active
search.appverid: MET150
description: Learn about collecting Teams logs for support engineers, where they can be found, and how they can help with monitoring and troubleshooting.
locale: en-us
document_id: 97d5e6d3-b7e0-d79f-0dea-ed423186a157
document_version_independent_id: ec6e68aa-552f-ab45-3c8e-92eff526b173
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/log-files.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: log-files
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/log-files.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b75c6931-6fea-9946-925e-9ab69efe560a
---

# Collect log files for monitoring and troubleshooting in Teams - Microsoft Teams | Microsoft Learn

There are two types of logs that are automatically created upon request, which can be used to assist Microsoft support in troubleshooting Teams.

- MS Teams Support Log Files, which contain media and signaling logs in addition to platform logs (not created when collecting logs while using the Teams browser client).
- Weblogs, which contain application event logs. You may see multiple weblog files depending on the types of users logged in and using the client (when using the Teams browser client, there will only be one log).
    - Public Enterprise = Prod-Weblogs
    - Public Consumer = Life-Weblogs
    - GCCH = GCCH-Weblogs
    - DOD = DOD-Weblogs

Note

The media and signaling logs are encrypted and can only be decrypted by Microsoft Support. Weblogs are text files and readable by any text editor. Additionally, performance enhancements have made it possible to always enable media logging. Accordingly, the administrative policy to control media logging has been deprecated.

Note

For Teams on VDI, Media logs are only available for the new [Slimcore-based VDI solution](/en-us/microsoftteams/vdi-2). For Teams on VDI using legacy WebRTC-based media optimization, please contact your VDI provider for instructions on gathering and interpreting media logs. For Teams Web, see [Browser logs and tracing for Teams](/en-us/microsoftteams/browser-logs-and-tracing-for-teams).

## Logs overview

It’s important to collect logs as soon as an issue occurs.

Note

To preserve disk space, the size of logs files for Microsoft Teams Virtual Desktop (VDI) clients is limited by default. If an issue is encountered on a VDI client, turn **Extended Logging** on in Teams Privacy settings before reproducing the issue and collecting logs.

When you create a support request with Microsoft Support, the support engineer will require the diagnostic logs. Having the diagnostic logs on hand before creating the support request allows Microsoft to quickly start troubleshooting the problem.

Note

Times in logs are recorded in Coordinated Universal Time (UTC). When opening a support case, be sure to inform the support agent of the time difference between the local time the issue occurred, and UTC time.

## Log collection

Both sets of logs are collected in the Downloads folder by default. The Prod-Weblogs will already be compressed, but the MS Teams Support Log Files need to be compressed before uploading to Microsoft Support.

To collect logs for Windows:

- Select the Microsoft Teams icon in your system tray and then select **Collect support files**, or use the Ctrl + Alt + Shift + 1 keyboard shortcut.

To collect logs for Mac:

- Select the **Help** menu in Microsoft Teams and then select **Collect support files**, or use the Option + Command + Shift + 1 keyboard shortcut.

Note

Wait until the banner showing **Downloading web logs** is dismissed from the Teams client before retrieving logs from the download location. To collect logs from Teams browser client, use the keyboard shortcut.

Note

When multiple accounts are in use from a single client, the generated logs include diagnostic information for all logged-in accounts in Teams, regardless of tenant or cloud. To learn how to manage this configuration, see [How different technologies affect Microsoft Teams sign-in](/en-us/microsoftteams/sign-in-teams#how-to-restrict-teams-sign-in-on-desktop-devices).