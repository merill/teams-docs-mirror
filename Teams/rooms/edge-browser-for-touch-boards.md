---
layout: Conceptual
title: Edge browser on Teams Rooms touch boards - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/edge-browser-for-touch-boards
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Microsoft Teams Rooms MTR touch board devices support a built-in Microsoft Edge browser running in private browsing Kiosk mode during a meeting or outside of one.
author: Yoojin-Jung
manager: sohailta
ms.author: yoojinjung
ms.service: msteams
ms.subservice: itpro-rooms
ms.topic: article
ms.date: 2026-04-15T00:00:00.0000000Z
locale: en-us
document_id: c3c15e18-7e17-e4a8-7310-ab3acb2e260e
document_version_independent_id: c3c15e18-7e17-e4a8-7310-ab3acb2e260e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/edge-browser-for-touch-boards.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/edge-browser-for-touch-boards
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/edge-browser-for-touch-boards.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/5287f575-02f0-405f-92b7-800456526b0c
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/06e86142-34c2-4b94-ab9c-9477c21f7152
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: df8eb32a-b8a3-f210-0593-5b283ec3f211
---

# Edge browser on Teams Rooms touch boards - Microsoft Teams | Microsoft Learn

Teams Rooms touch board devices, such as Surface Hub 3, support a built-in Microsoft Edge browser running in private browsing mode. This feature allows users in meeting rooms to securely access websites directly from the room system’s touch display, whether during a meeting or outside of one. Additionally, when a user shares the Edge browser window during a meeting (using the room system’s Share menu), a toggle is available to enable or disable sharing of the browser’s audio into the meeting. With the Edge browser enabled and configured, users in the room can tap the **Edge** icon on the Teams Rooms touch board device to launch a private browsing session. During meetings, users can use the **Share** tray to share the Edge browser content with meeting participants. 

Note

Edge browser on Teams Rooms devices is restricted from accessing the room’s camera and microphone directly through the browser. This limitation is in place to prevent conflicts with the Teams Rooms application, which manages AV hardware for meetings and collaboration. 

Check out our video to learn more about using the Edge browser on Microsoft Teams Rooms touch board devices:

## Step 1: Confirm requirements

1. Supported devices: A certified Teams Rooms on Windows touch board device
2. Teams Rooms Pro license assigned to resource account signed in to the device.
3. Teams Rooms on Windows application version 5.4 or later installed on the device.

## Step 2: Configure Edge browser settings

### Configure a single device

1. Sign in to the [Teams Pro Management Portal](enrolling-mtrp-managed-service) and select the Teams Rooms on Windows touch board device you want to configure.
2. Go to the **Settings** tab and then find the **Device** settings section.
3. Adjust Edge browser settings:

- **Edge browser (on/off)**: Enable or disable the Edge browser feature on the Teams Rooms device. Turn this setting on to allow the Edge browser to be used on that device (the browser icon will appear on the device’s home screen when enabled). It’s disabled by default.
- **Edge browser start page**: Specify the webpage to open automatically when the browser launches. Only one browser tab can be specified by adding a single URL. This setting isn't available in GCC environments.

Note

Previously this setting allowed multiple tabs to be launched as start pages using a comma separated URL list. This feature is no longer available and restricted to a single start page.

- **Edge browser inactivity timeout**: This setting defines how long the browser can stay idle (with no user interaction) before it automatically closes itself. Enter a value from 0 to 100 minutes. (A value of 0 minutes means the session has no automatic timeout and will remain open until manually closed.) 10-minute is the default.

1. Apply the changes. To learn more, see [Managing Microsoft Teams Rooms on Windows devices](/en-us/microsoftteams/rooms/pro-portal-settings#changing-settings).

### Configure multiple devices

To apply Edge browser settings across multiple devices at once, use **Device Settings Jobs** in the portal. This method allows you to create and deploy configuration profiles to groups of Teams Rooms devices. To learn more, see [Managing Microsoft Teams Rooms on Windows devices](/en-us/microsoftteams/rooms/pro-portal-settings#device-settings-jobs-for-bulk-changes).

## Step 3: Review Microsoft 365 sign-in requirements

When using the Edge browser on a touch board, end users may wish to login to their Microsoft 365 account to access files or collaborate on a document. It requires the end user to authenticate using their personal credentials that are subject to your organization’s conditional access policies. 

Depending on your organization’s conditional access design, users may be blocked due to the design of InPrivate mode in Microsoft Edge that prevents conditional access from getting device **or** user context information as part of the sign-in. This means that conditional access controls that grant access based on device compliance status or user account app protection policies may not work with the kiosk mode Edge browser provided as part of Teams Rooms on Windows. In this case, the conditional access administrator may need to create a policy excluding sign-in attempts from Teams Rooms Touch Board devices. It can be accomplished in several ways including [Compliant Network (via Global Secure Access)](/en-us/entra/global-secure-access/how-to-compliant-network) or [trusted network location](/en-us/entra/identity/conditional-access/concept-assignment-network).