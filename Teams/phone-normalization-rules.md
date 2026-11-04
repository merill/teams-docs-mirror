---
layout: Conceptual
title: Normalization rules for Microsoft Teams dial plans - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phone-normalization-rules
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2025-04-25T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: 'Learn normalization rules for Microsoft Teams user dial plans and trunk dial plans. '
locale: en-us
document_id: 54b587fc-17f7-e3d9-463e-e618d2e67f96
document_version_independent_id: 54b587fc-17f7-e3d9-463e-e618d2e67f96
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phone-normalization-rules.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phone-normalization-rules
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phone-normalization-rules.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/8b896464-3b7d-4e1f-84b0-9bb45aeb5f64
- https://authoring-docs-microsoft.poolparty.biz/devrel/7696cda6-0510-47f6-8302-71bb5d2e28cf
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/b1d2d671-9549-46e8-918c-24349120dbf5
- https://authoring-docs-microsoft.poolparty.biz/devrel/69c76c32-967e-4c65-b89a-74cc527db725
platformId: cf5a7883-c8a6-c408-04b3-01bda034773e
---

# Normalization rules for Microsoft Teams dial plans - Microsoft Teams | Microsoft Learn

This article is for IT Admins and IT Pros who are applying normalization rules to Teams dial plans.

For more on Teams dial plans, see [Routing with dial plans](dial-plans-routing-overview).

Normalization rules are the translation properties of a Teams dial plan and define how phone numbers expressed in various formats are to be translated. The same number string may be interpreted and translated differently, depending on the locale from which it's dialed. Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.

One or more normalization rules must be assigned to the dial plan. Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important. For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic is tried starting with the first normalization rule. If there isn't a match with the first rule, then a match is attempted with the second rule, and so forth. If a match is made, that rule is used and there's no effort to match any other rules that are defined.

Note

Microsoft now enforces the rule that there can be no more than 50 normalization rules in a given dial plan.

### Determining the required normalization rules

Because a tenant dial plan is merged with a given user's service country/region dial plan, it's likely that the service country/region dial plan's normalization rules need to be evaluated. The evaluation determines which tenant dial plan normalization rules are needed.

The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose. The cmdlet takes the user's identity as the input parameter and returns all normalization rules that are applicable to the user.

### Creating normalization rules

Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format. Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found. When you finish, you can enter a test number to verify that the normalization rule works as expected.

For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](/en-us/dotnet/standard/base-types/regular-expressions).

For validating regular expressions, see [Regex101 (an interactive tool for testing and learning regular expressions)](https://regex101.com)

See [Create and manage dial plans](create-and-manage-dial-plans) to create and manage normalization rules for your tenant dial plans.

Note

Normalization rules with the first token as optional are currently not supported on 3pip devices (for example, Polycom VVX 601 model). If you want to apply normalization rules with optionality on 3pip devices, you should create two normalization rules instead of one. For example, the rule ^0?(999)$ should be replaced by the following two rules: (999)$ (Translation:$1) and ^0(999)$ (Translation:$1).

Validate all regular expressions used in dial plan normalization rules as invalid expressions may result in client or service issues.

### Sample normalization rules

The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and aren't meant to be a prescriptive reference for creating your own normalization rules.

**Normalization rules using .NET Framework regular expressions**

| Rule name | Description | Number pattern | Translation | Example |
| --- | --- | --- | --- | --- |
| 4digitExtension | Translates 4-digit extensions. | ^(\d{4})$ | +1425555$1 | 0100 is translated to +14255550100 |
| 5digitExtension | Translates 5-digit extensions. | ^5(\d{4})$ | +1425555$1 | 50100 is translated to +14255550100 |
| 7digitcallingRedmond | Translates 7-digit numbers to Redmond local numbers. | ^(\d{7})$ | +1425$1 | 5550100 is translated to +14255550100 |
| RedmondOperator | Translates 0 to Redmond Operator. | ^0$ | +14255550100 | 0 is translated to +14255550100 |
| RedmondSitePrefix | Translates numbers with on-net prefix (6) and Redmond site code (222). | ^6222(\d{4})$ | +1425555$1 | 62220100 is translated to +14255550100 |
| 5digitRange | Translates 5-digit extensions starting with the digit range between 3-7 inclusive. | ^([3-7]\d{4})$ | +142555$1 | 54567 is translated to +14255554567 |
| PrefixAdded | Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits. | ^([2-9]\d\d[2-9]\d{6})$ | 1$1 | 4255554567 is translated to 14255554567 |
| NoTranslation | Match 5 digits but no translation. | ^(\d{5})$ | $1 | 34567 is translated to 34567 |

**Redmond dial plan based on normalization rules shown in previous table.**

The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.

| Redmond dial plan |
| --- |
| 5digitExtension |
| 7digitcallingRedmond |
| RedmondSitePrefix |
| RedmondOperator |

Note

The normalization rules names shown in the preceding table don't include spaces, but using spaces is a matter of choice. The first name in the table, for example, could be written "5 digit extension" or "5-digit Extension" and still be valid.