---
layout: Conceptual
title: Report suspicious Teams Meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/end-user-reporting-teams-meeting
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how users can report suspicious or scam meetings or participants in Microsoft Teams
author: smahadevan
ms.author: smahadevan
ms.reviewer: smahade
manager: charup
ms.service: msteams
ms.subservice: msteams-admin
ms.topic: how-to
ms.date: 2026-09-17T00:00:00.0000000Z
ms.custom:
- Security
locale: en-us
document_id: cd25c921-6089-ee2f-2b74-92828be211bb
document_version_independent_id: cd25c921-6089-ee2f-2b74-92828be211bb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/end-user-reporting-teams-meeting.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: end-user-reporting-teams-meeting
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/end-user-reporting-teams-meeting.md
platformId: f5921383-ad93-e426-548f-ebfdb35645a4
---

# Report suspicious Teams Meetings - Microsoft Teams | Microsoft Learn

In organizations with Microsoft Defender for Office 365 or Microsoft Defender XDR, users can report suspicious meetings or meeting participants in Microsoft Teams. These reports give security administrators visibility into meetings and participants that users believe might represent a security concern.

Users can report:

- A **meeting** as a security concern.
- A **meeting participant** as a security concern.
- A meeting participant that was identified as suspicious but is **not a security concern**.

## User experience in Teams - Report a security concern

Users who encounter suspicious activity during a Teams meeting can report the meeting or an individual participant.

### Report during a meeting

1. In the meeting, select **More (...)**.
2. Select **Report a security concern**.
3. If reporting a participant, select the participant you want to report in the dialog.
4. In the reporting dialog, provide more information about the security concern.
5. Review the information and select **Report**.

The report is submitted for security investigation.

### Report an individual participant from the participant tile

You can report a specific participant directly from the participant tile in the meeting gallery.

1. In the meeting gallery, locate the participant you want to report.
2. On the participant tile, select **...**.
3. Select **Report**.
4. In the reporting dialog, optionally provide more information about the security concern.
5. Select **Report** to submit the report.

### Report an individual participant from the roster pane

You can also report a specific participant from the meeting roster.

1. Open the **People** or participant roster pane in the meeting.
2. Locate the participant you want to report.
3. Select **...** next to the participant's name.
4. Select **Report**.
5. In the reporting dialog, optionally provide more information about the security concern.
6. Select **Report** to submit the report.

Both entry points open the participant reporting flow for the selected participant.

## Report a security concern after a meeting

Users can report a security concern after the meeting ends.

1. Open the relevant meeting from the Teams post-meeting experience.
2. Select **Report a security concern**.
3. If applicable, select the participant associated with the concern.
4. Provide more information.
5. Select **Report**.

This process gives users an opportunity to report suspicious behavior even if they didn't report it while the meeting was in progress.

## User reporting settings for Teams meetings

Administrators control user reporting for Teams meetings through administrative settings. The configuration determines whether users in the organization can report security concerns related to Teams meetings.

- **In the Teams admin center**: The setting controls whether users can report a meeting or an individual meeting participant from Microsoft Teams. When you turn off this setting, users can't submit security concern reports from Teams meetings.
- **In the Teams admin center**: The setting controls whether users can report a meeting or an individual meeting participant from Microsoft Teams. When this setting is turned off, users can't submit security concern reports from Teams meetings.
- **In the Microsoft Defender portal**: Administrators can control whether supported user-submitted reports are shared with Microsoft for analysis. This setting is separate from the setting that controls whether the reporting experience is available to users in Teams.

## View user-reported meeting security concerns

Security administrators can review security concerns submitted by Teams users through the applicable user-submission and protection reporting experiences. Reports can provide investigation context about the reported meeting or participant so that administrators can assess the security concern and take appropriate action.

Reports can provide investigation context about the reported meeting or participant so that administrators can assess the security concern and take appropriate action.

## Turn off or turn on user reporting for meetings in the Teams admin center

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com).
2. In the left navigation, open the policy or settings page that controls reporting for Teams meetings.
3. Select the **Allow users to report meetings** policy.
4. Turn off or turn on the policy.
5. Select **Save** to apply the changes.

## User experience: Report as not a security concern

Users can also provide feedback when Teams identifies a meeting or participant as suspicious but the user believes it isn't a security concern.

To provide feedback:

1. Open the relevant meeting or participant experience.
2. Select **Report as not a security concern**.
3. Provide more information explaining why the meeting or participant isn't a security concern.
4. Select **Report**.

This feedback helps distinguish legitimate meeting activity from activity that might require further security investigation.