---
layout: Conceptual
title: Set up meeting dial-out-confirmation for your users in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-meeting-dial-out-confirmation
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: oscarr
ms.date: 2024-10-16T00:00:00.0000000Z
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: teams-audio-conferencing
audience: admin
search.appverid: MET150
description: Learn how to set up Teams to request a dial-out confirmation to prevent voicemail systems from connecting to meetings when the called person is unable to answer the call.
ms.localizationpriority: medium
ms.collection:
- Tier1
- m365initiative-meetings
locale: en-us
document_id: 988e6602-918e-30c2-8184-45a982cb22d8
document_version_independent_id: e7920d74-7296-4a54-180e-ddf70bfe53ed
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-meeting-dial-out-confirmation.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-meeting-dial-out-confirmation
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-meeting-dial-out-confirmation.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 91a5a9c0-681d-3792-567c-969bd28d5704
---

# Set up meeting dial-out-confirmation for your users in Microsoft Teams - Microsoft Teams | Microsoft Learn

Sending meeting invitations through dial outs and Call me calls is an effective way to invite participants to join a meeting, whether they're new or existing participants, using either a traditional or mobile phone. However, if the person being called doesn't pick up and a voicemail system answers instead, the voicemail system joins the meeting. This results in participants having to listen to the voicemail until someone removes it from the meeting.

To prevent this, you can configure Teams to request a confirmation from the called person before they join the meeting. When a meeting dial out goes to a phone number and the person can't answer, the voicemail system can't connect because it can't provide the required confirmation.

This policy requires anyone receiving dial outs or Call me calls to accept the meeting invitation by pressing 1 on their phone keypad or saying "Okay." This confirmation step ensures that voicemail systems don't join the meeting.

## Set up meeting dial-out confirmation for your users with PowerShell

To enable this policy for all meetings in your organization, set the **`-EnableDialOutJoinConfirmation`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/en-us/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) cmdlet to `true`. To set this parameter, run the following command:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```