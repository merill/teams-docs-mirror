---
layout: Conceptual
title: Create people manager teams in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/create-manager-directs-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: pbethi
ms.date: 2025-03-13T00:00:00.0000000Z
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-chat
audience: admin
description: Learn how to use a PowerShell script to create a team for each manager with their directs as team members.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom:
- chat-teams-channels-revamp
- has-azure-ad-ps-ref, azure-ad-ref-level-one-done
- teams-chat-and-channels
ms.collection:
- M365-collaboration
locale: en-us
document_id: 6599136d-7882-4a01-e00c-600ea3c7acbb
document_version_independent_id: 824a153c-285f-ba54-a478-141b9502386b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/create-manager-directs-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-manager-directs-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/create-manager-directs-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: af76d0a2-c2d8-e888-d616-4a57de9f1c77
---

# Create people manager teams in Microsoft Teams - Microsoft Teams | Microsoft Learn

When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels. This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.

To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members. This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization). But it's a valuable tool you can use to impose some order on your Teams structure from the start.

This script reads your Microsoft Entra ID and gets a list of managers and their direct reports. It uses this list to create one team per people manager.

## How to use the PowerShell script

Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers) (which assumes you've already run the [Connect-MgGraph](/en-us/powershell/microsoftgraph/authentication-commands) and [Connect-MicrosoftTeams](/en-us/powershell/module/teams/connect-microsoftteams) PowerShell modules). The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.

Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams). This script reads in the `ExportedManagerDirects.txt` file and creates a team for each manager, with that manager's direct reports as members. If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.

Review the report, then rerun the script after you've turned on Teams for anybody who needs it. The script won't create a second team for any manager it's already created a team for.

For each team, the script creates a **General** and **Just for fun** channel.

## Best practices

- Ask each people manager to add your organization's crisis communications website as a tab to the **General** channel for each team.
- Check out the new Crisis Communications app by reading [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).