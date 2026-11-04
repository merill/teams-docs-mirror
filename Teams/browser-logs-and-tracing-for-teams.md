---
layout: Conceptual
title: Browser logs and tracing for Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/browser-logs-and-tracing-for-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.reviewer: xiashi
ms.date: 2023-10-10T00:00:00.0000000Z
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.subservice: msteams-admin
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Learn about Browser and WebRTC logs produced by Microsoft Teams, where they can be found, how to collect logs with Microsoft Support, and how they can help with monitoring and troubleshooting.
locale: en-us
document_id: ac117ef1-934d-2d7c-5311-5482f807f1b2
document_version_independent_id: ac117ef1-934d-2d7c-5311-5482f807f1b2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/browser-logs-and-tracing-for-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: browser-logs-and-tracing-for-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/browser-logs-and-tracing-for-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 94fbbb88-ad24-2cd2-c730-d4a7a7913d9d
---

# Browser logs and tracing for Teams - Microsoft Teams | Microsoft Learn

For some categories of errors, Microsoft Support might require you to collect a browser trace. A browser trace can provide important details about the state of the Teams client when the error occurs. This article describes how to collect browser and WebRTC logs for Teams.

## Browser logs

Before you start the browser trace, make sure that you’re signed in to Teams. It's important to sign in before you start the trace so the trace doesn't contain sensitive sign-in information.

After you’ve signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.

- [Chrome & Microsoft Edge (Chromium)](/en-us/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)
- [Microsoft Edge](/en-us/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)
- [Safari](/en-us/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)
- [Firefox](/en-us/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

Note

In the steps, replace all references to the Azure portal with the Teams client.

## WebRTC logs in browsers

WebRTC logs can assist Microsoft Support by providing connection details for audio and video calls. Follow the steps to access the WebRTC logs in Microsoft Edge (Chromium) or Chrome:

1. Open a new tab and go to one of the following URLs:

    - Microsoft Edge (Chromium): `edge://webrtc-internals/`
    - Chrome: `chrome://webrtc-internals/`
2. Open the Teams Web application and reproduce the problem.
3. Go back to the tab that was accessed in step 1 and you'll see at least two tabs:

    - GetUserMedia Requests
    - `https://teams.microsoft.com/url`
4. Choose the tab with the name of the Teams application and save the page content.