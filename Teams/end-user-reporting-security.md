---
layout: Conceptual
title: End user reporting for security - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/end-user-reporting-security
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: yilinyang-MSFT
ms.author: yilyang
manager: charup
ms.date: 2026-07-08T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: 
description: Learn about end user reporting for security.
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
document_id: 43f7b35a-d959-4f17-ea52-36f4f2bec511
document_version_independent_id: 43f7b35a-d959-4f17-ea52-36f4f2bec511
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/end-user-reporting-security.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: end-user-reporting-security
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/end-user-reporting-security.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 8b8822ca-35bb-7e0c-bb9c-c522e8cc3abb
---

# End user reporting for security - Microsoft Teams | Microsoft Learn

In organizations with Microsoft Defender for Office 365 Plan 2 or Microsoft Defender XDR, admins can decide whether users can report malicious messages in Microsoft Teams. Security admins can also get visibility into the Teams messages that users are reporting.

Users can report messages in Teams from chats and channels for security concern and for incorrect detection.

## User experience in Teams – Report a Message for Security Concern

Users who see a concerning chat or a channel message in Teams can report it as a security risk. To report a message:

1. Go to chat or channel message and select **… &gt; Report this message**.
2. Select **Security concern.** Depending on the organization settings, you maybe asked to choose a reason for reporting the message.
3. Review the selections and select **Report**.

[![Screenshot of selecting 'Report this message'.](media/report-this-msg.png)](media/report-this-msg.png#lightbox)

[![Screenshot of 'Report message as security risk'.](media/report-msg-security-risk.png)](media/report-msg-security-risk.png#lightbox)

## User experience in Teams - Report an External User for Security Concern

User can report suspicious external users while blocking them in Teams, from external chat requests and user profile cards. Use **Report user** when you want to report the sender rather than a specific message.

To report a user from an external chat request:

1. Open the external chat request.
2. Select **Block, Delete or Leave**, depending on the chat type and your organization's settings, and follow the prompt to block the user.
3. Click **Report this person** checkbox and confirm.

To report a user from profile card:

1. Open the user's profile card.
2. Open the menu option and select **Block contact**
3. Click **Report this person** checkbox and confirm.

[![Screenshot of 'Report an external user during blocking'.](media/end-user-reporting-security/report-user-dialog.png)](media/end-user-reporting-security/report-user-dialog.png#lightbox)

## User reporting settings for Teams messages – Security Concern

'Report a security concern' reporting of messages and users in Teams is made of two separate settings:

- **In the Teams admin center**: 'On' by default and controls whether users are able to report messages and user from Teams. When this setting is turned off, users can't report messages or users within Teams, so the corresponding setting in the Microsoft Defender portal is irrelevant.
- **In the Microsoft Defender portal**: 'On' by default for new tenants. Existing tenants need to enable it. If "Report a security concern" is turned on in the Teams admin center, it also needs to be turned on in the Defender portal for user reported messages to show up correctly on the **User reported** tab on the **Submissions** page. Only user reporting of messages is supported in Microsoft Defender as of now. User reporting of external users is not yet supported in Microsoft Defender.

## Turn off or turn on user reporting for security concerns in Teams admin center

1. Sign in to the Teams Admin Center at [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com/).
2. In the left navigation, select **Messaging policies**.
3. Select a policy.
4. Turn on the setting: **Report a security concern**.
5. Select **Save** to apply the changes.

[![Screenshot of turning on user reporting for security concerns in Teams admin center.](media/user-report-security-teams-admin-center.png)](media/user-report-security-teams-admin-center.png#lightbox)

Learn about turning off or turning on user reporting of Teams messages in the [Defender portal](/en-us/defender-office-365/submissions-teams#turn-off-or-turn-on-user-reporting-of-teams-messages-in-the-defender-portal).

Note

To access this policy in the new experience, go to **Settings & policies**. To learn more, see [Unified policies and settings management in the Teams admin center](unified-policies-settings-management-teams-admin-center).

## User experience in Teams – Report Not a Security Concern

Users can report messages in Teams chats or channels that are incorrectly flagged by Link Protection as containing malicious URLs.

To report a message as not a security concern:

1. In the Teams chat or channel, locate the message that was flagged.
2. Hover over the message without selecting it.
3. Select **... More options** &gt; **Report this message**.
4. In the report dialog that opens, select **Not a security concern**.
5. Select **Report** to submit your feedback.

[![Screenshot of 'Report this message' for 'report not a security concern.](media/report-not-security-option-menu.png)](media/report-not-security-option-menu.png#lightbox)

[![Screenshot of 'Report not a security concern'.](media/report-not-security-concern.png)](media/report-not-security-concern.png#lightbox)

## User reporting settings for Teams messages – Not a Security Concern

Incorrect detection (Not a security concern) reporting of messages in Teams is made of two separate settings:

- **In the Teams admin center**: The setting controls whether users are able to report incorrect detections on messages flagged as security risks from Teams. When this setting is turned off, users can't report messages within Teams, so the corresponding setting in the Microsoft Defender portal is irrelevant.
- **In the Microsoft Defender portal**: 'On' by default for new tenants. Existing tenants need to enable it. If user reporting of messages is turned on in the Teams admin center, it also needs to be turned on in the Defender portal for user reported messages to show up correctly on the **User reported** tab on the **Submissions** page.

## Turn off or turn on user reporting for incorrect detections concerns in Teams admin center

1. Sign in to the Teams Admin Center at [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com/).
2. In the left navigation, select **Messaging settings**.
3. Scroll down to **Messaging safety** settings.
4. Turn on the setting: **Report incorrect security detections**.
5. Select **Save** to apply the changes.

[![Screenshot of turning on 'Report incorrect security detections'.](media/report-incorrect-security-detections.png)](media/report-incorrect-security-detections.png#lightbox)

Learn about turning off or turning on user reporting of Teams messages in the [Defender portal](/en-us/defender-office-365/submissions-teams#turn-off-or-turn-on-user-reporting-of-teams-messages-in-the-defender-portal).