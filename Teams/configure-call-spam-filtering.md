---
layout: Conceptual
title: Configure spam filtering for calls in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/configure-call-spam-filtering
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.reviewer: ddobrzanski
ms.date: 2026-04-26T00:00:00.0000000Z
audience: admin
search.appverid: MET150
description: Learn how to configure spam filtering for calls in Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- CSH
locale: en-us
document_id: cfb986eb-c5ef-2eb9-ec38-5a124d26ba5f
document_version_independent_id: cfb986eb-c5ef-2eb9-ec38-5a124d26ba5f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/configure-call-spam-filtering.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-call-spam-filtering
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/configure-call-spam-filtering.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e846c3fb-ff35-4019-efa0-03ff2fab43f3
---

# Configure spam filtering for calls in Microsoft Teams - Microsoft Teams | Microsoft Learn

In Microsoft Teams, admins can configure spam filtering for inbound calls from the Public Switched Telephone Network (PSTN). Teams can detect potential spam calls and notify users with a "Spam Likely" notification.

Spam filtering for calls isn't the same as blocking inbound calls. For more information, see [Block inbound calls](block-inbound-calls).

## Using the Teams admin center

1. Sign in to the [Microsoft Teams Admin Center](https://admin.microsoft.com/).
2. Go to **Calling Policies**.
3. Select the policy you want to edit (e.g., *Global* or a custom policy).
4. Find the **Spam Filtering** setting. This setting allows you to control the type of spam filtering available on incoming calls. This setting is on by default. This setting has three options:

    1. **On** Spam filtering is enabled. In case the call is considered as spam, the user gets a "Spam Likely" notification in Teams, filtering may include basic and captcha interactive voice response (IVR) checks.
    2. **Off** Spam filtering is disabled. No checks are performed. A "Spam Likely" notification doesn't appear.
5. Set it to the option of your choice.
6. Save changes.

## Using PowerShell

To configure spam filtering for calls in Teams, use the `-SpamFilteringEnabledType` parameter with the following cmdlets:

- [Get-CsTeamsCallingPolicy](/en-us/powershell/module/teams/get-csteamscallingpolicy)
- [New-CsTeamsCallingPolicy](/en-us/powershell/module/teams/new-csteamscallingpolicy)
- [Set-CsTeamsCallingPolicy](/en-us/powershell/module/teams/set-csteamscallingpolicy)
- [Remove-CsTeamsCallingPolicy](/en-us/powershell/module/teams/remove-csteamscallingpolicy)
- [Grant-CsTeamsCallingPolicy](/en-us/powershell/module/teams/grant-csteamscallingpolicy)

For example, this script enables spam detection for the global policy:

```powershell
Set-CsTeamsCallingPolicy -Identity Global -SpamFilteringEnabledType Enabled
```