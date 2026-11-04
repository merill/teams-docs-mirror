---
layout: Conceptual
title: User reported security submissions report in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/end-user-reported-security-signal
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to use the User reported security submissions protection report in the Teams admin center to review and export security-related reports submitted by users in your organization.
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.service: msteams
ms.subservice: msteams-admin
ms.topic: concept-article
ms.date: 2026-07-30T00:00:00.0000000Z
ms.reviewer: yilyang
audience: admin
locale: en-us
document_id: 09d72064-41ae-c822-e665-85f5e8dd078a
document_version_independent_id: 09d72064-41ae-c822-e665-85f5e8dd078a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/end-user-reported-security-signal.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: end-user-reported-security-signal
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/end-user-reported-security-signal.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8237b110-c562-2399-91f6-2728b9a8254d
---

# User reported security submissions report in Microsoft Teams - Microsoft Teams | Microsoft Learn

## Overview

The User reported security submissions report in the Microsoft Teams admin center helps you review security-related reports submitted by users in your organization. You can export these reports to a CSV file for further analysis.

These user-submitted reports help you identify suspicious activity and strengthen your organization’s security posture by using feedback collected directly from Teams experiences. You can view and export reports for:

- **Calling**: Calls that users [reported for a security concern](end-user-reporting-teams-calling).
- **Chats and channels**: Chat and channel messages that users [reported for a security concern](end-user-reporting-security).
- **User**: External users that users [reported for a security concern](end-user-reporting-security).

## Prerequisites

- Reported interactions appear in the User reported security submissions reports only after users submit reports.
- Users can submit reports only when the required reporting settings are enabled in the Teams admin center.

    - For calls, the **Report a call** setting must be turned on in the user's calling policy.
    - For chat and channel messages and external users, the **Report a security concern** setting must be turned on in the user's messaging policy.

## View the User reported security submissions report

To view the User reported security submissions report:

1. In the left navigation of the Teams admin center, go to **Analytics & reports** &gt; **Protection reports**.
2. On the **View reports** tab, under **Report**, select **User reported security submissions**.
3. Under **Report category**, choose one of the following categories:

    - **Calling**
    - **Chats and channels**
    - **User**
4. Under **Date range**, select a predefined time range. For example, **Last 24 hours**, **Last 7 days**, or **Last 30 days**.
5. Select **Run report**.

    [![Screenshot of the user reported security submissions report for reporting users in the Teams admin center.](media/user-reported-security-submissions-report.png)](media/user-reported-security-submissions-report.png#lightbox)

## Interpret the User reported security submissions report

Use the information in the following tables to interpret the data in the Calling, Chats and channels, and User reports.

### Calling

| Item | Description |
| --- | --- |
| Date and time | Date and time when the report was submitted. |
| Reporter name | Name of the user who submitted the report, with a link to their user detail page. |
| Caller name | Number of the caller whose call is being reported. Could be an empty value. |
| Caller phone number | Phone number of the call that's being reported. |
| Call start time | Time stamp when the call began. |
| Submission ID^1^ | Unique identifier of the submission. |
| Call ID^1^ | Unique identifier of the reported call. |
| Call duration^1^ | Length of the call that's reported. |
| Participant list^1^ | List of participants in the call. |
| Caller ID^1^ | Microsoft Resource Identifier (MRI) of the caller. Admins can use this identifier when blocking the caller on the External Access page of the Teams admin center. |
| Caller tenant ID^1^ | Unique identifier of the tenant of the caller that's reported. |
| Caller domain name^1^ | Domain name of the tenant where the call is reported. |
| Reporter phone number^1^ | Phone number of the user who submitted the report. |
| Reporter user ID^1^ | User ID of the user who submitted the report. |
| Reporter display name^1^ | Display name of the user who submitted the report. |
| Reporter tenant ID^1^ | Unique identifier of the tenant where the reporter user belongs to. |
| Reporter comments^1^ | Optional comments that the reporter user sent along with the report, if any. |

^1^Available only in the exported CSV file.

### Chats and channels

| Item | Description |
| --- | --- |
| Date and time | Date and time when the report was submitted. |
| Reporter name | Name of the user who submitted the report, with a link to their user detail page. |
| Sent from | Sender of the reported message, including their display name and email address, if available. If the sender uses a consumer account, their email address might not be available depending on their privacy setting. |
| Message sent date | Date and time when the reported message was sent. |
| Submission ID^1^ | Unique identifier of the submission. |
| Reported message^1^ | Unique identifier of the reported message. |
| Conversation ID^1^ | Unique identifier of the conversation thread that contains the reported message. |
| Conversation name^1^ | Name of the conversation thread that contains the reported message, if any. |
| Message last edited^1^ | Date and time when the reported message was last edited. |
| Participant list^1^ | List of participants in the conversation, including their display name, email address, and Microsoft Resource Identifier (MRI). Maximum 20 entries: up to 10 entries from the reporter's tenant and up to 10 entries from non-reporter tenants. |
| Participant count^1^ | Count of the participants in the conversation. |
| Sender user ID^1^ | Microsoft Resource Identifier (MRI) of the sender. Admins can use this identifier when blocking the sender on the External Access page of the Teams admin center. |
| Sender tenant ID^1^ | Unique identifier of the tenant where the sender belongs to. This field might be blank if the sender uses a consumer account. |
| Sender domain name^1^ | Domain of the sender. This field might be blank if the sender uses a consumer account, depending on their privacy setting. |
| Is external^1^ | Whether the sender is an external user. |
| Reporter user ID^1^ | User ID of the user who submitted the report. |
| Reporter display name^1^ | Display name of the user who submitted the report. |
| Reporter email address^1^ | Email address of the user who submitted the report. |
| Reporter tenant ID^1^ | Unique identifier of the tenant where the reporter user belongs to. |
| Reporter comments^1^ | Optional comments that the reporter user sent along with the report, if any. |

^1^Available only in the exported CSV file.

### User

| Item | Description |
| --- | --- |
| Date and time | Date and time when the report was submitted. |
| Reporter name | Name of the user who submitted the report, with a link to their user detail page. |
| Reported user name | Reported user's display name and email address, if available. If the reported user uses a consumer account, their email address might not be available depending on their privacy setting. |
| First contact date and time | If the user was reported from a 1:1 chat invitation, this field shows the date and time when the first invitation message was sent. This field might be blank if the report was submitted from a group chat invitation or a user's profile card. |
| Submission ID^1^ | Unique identifier of the submission. |
| Conversation ID^1^ | Unique identifier of the conversation thread where the user was reported from. This field might be blank if the user was reported from their profile card and not from a conversation. |
| Conversation name^1^ | Name of the conversation thread where the user was reported from, if any. |
| Reported user ID^1^ | Microsoft Resource Identifier (MRI) of the reported user. Admins can use this identifier when blocking the user on the External Access page of the Teams admin center. |
| Reported user tenant ID^1^ | Unique identifier of the tenant where the reported user belongs to. This field might be blank if the reported user uses a consumer account. |
| Reported user domain name^1^ | Domain of the reported user. This field might be blank if the reported user uses a consumer account, depending on their privacy setting. |
| Reporter user ID^1^ | User ID of the user who submitted the report. |
| Reporter display name^1^ | Display name of the user who submitted the report. |
| Reporter email address^1^ | Email address of the user who submitted the report. |
| Reporter tenant ID^1^ | Unique identifier of the tenant where the reporter user belongs to. |
| Reporter comments^1^ | Optional comments that the reporter user sent along with the report, if any. |
| Report submitted from^1^ | Location where the user was reported from. Possible values include "A/B screen", which refers to the Accept/Block screen for 1:1 and group chat invitations, and "Profile card", which refers to the reported user's profile card. A profile card can be opened by hovering over a user's profile picture anywhere in Teams and isn't necessarily associated with a chat conversation. |

^1^Available only in the exported CSV file.