---
layout: Conceptual
title: Meeting provider for Islands mode - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-provider-islands-mode
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: article
ms.service: msteams
ms.subservice: meetings
ms.reviewer: lsomi
ms.date: 2025-03-28T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier2
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
description: Learn to use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.
locale: en-us
document_id: 569ed341-2518-19bd-063d-4e204327c538
document_version_independent_id: 569ed341-2518-19bd-063d-4e204327c538
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-provider-islands-mode.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-provider-islands-mode
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-provider-islands-mode.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: 43246a14-bed8-8754-0c88-ea9966e4e3bf
---

# Meeting provider for Islands mode - Microsoft Teams | Microsoft Learn

Islands mode allows users to run Teams alongside Skype for Business with similar functionality available in both clients.

As an admin, you can use this per-user policy to control which Outlook meeting add-in is used for users who are in Islands mode. You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.

You can only apply this policy to users who are in Islands mode and have the -**`AllowOutlookAddIn`** parameter set to **True** in their Teams meeting policy. To learn more about the Outlook add-in, see [Admin - authentication requirements and functionality of the Teams Meeting add-in in Outlook](outlook-add-in-authentication-policy-requirements).

## Manage the meeting provider for Islands mode with PowerShell

You must use the -**`PreferredMeetingProviderForIslandsMode`** parameter in PowerShell to control which Outlook meeting add-in is used for users who are in Islands mode. You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet. Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/new-csteamsmeetingpolicy) cmdlet and assign it to users.

To specify which meeting add-in you want to be available to users, set the -**`PreferredMeetingProviderForIslandsMode`** parameter as follows:

### TeamsAndSfB

**This setting is the default value.** To enable both the Teams Meeting add-in and Skype for Business add-in in Outlook for users with this policy, run the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -PreferredMeetingProviderForIslandsMode TeamsAndSfB
```

If you set the value to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled. However, existing Teams meeting join links aren't migrated to Skype for Business. Only Skype for Business meetings scheduled after the change have a Skype for Business meeting join link.

### Teams

To only enable the Teams Meeting add-in in Outlook for users with this policy, run the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -PreferredMeetingProviderForIslandsMode Teams
```

The **Teams** value ensures that all future meetings have a Teams meeting join link, but doesn't migrate existing Skype for Business meeting join links to Teams. This value doesn't affect presence, chat, Public Switched Telephone Network (PSTN) calling, or any other capabilities in Skype for Business, allowing users to keep using Skype for Business for these capabilities.