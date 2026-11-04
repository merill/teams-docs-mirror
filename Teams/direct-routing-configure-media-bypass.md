---
layout: Conceptual
title: Configure media bypass with Direct Routing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/direct-routing-configure-media-bypass
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
audience: ITPro
ms.reviewer: 
ms.date: 2026-09-10T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
f1.keywords:
- NOCSH
description: Learn how to configure media bypass with Direct Routing for Teams Phone.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: a65beb81-260d-8b98-b3c3-32e93b728e69
document_version_independent_id: 13c7c654-5182-eaf6-2d66-66b1b5e943ca
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/direct-routing-configure-media-bypass.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: direct-routing-configure-media-bypass
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/direct-routing-configure-media-bypass.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 51264f02-a284-8cfa-61a3-cabdc117ed75
---

# Configure media bypass with Direct Routing - Microsoft Teams | Microsoft Learn

Before configuring media bypass with Direct Routing, be sure you read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass).

To turn on media bypass, the following conditions must be met:

1. Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC. To learn about SBCs, which ones support media bypass, and for instructions, see the certification page.
2. You need to turn on media bypass on the trunk using the following command: **Set-CSOnlinePSTNGateway -Identity &lt;sbc\_FQDN&gt; -MediaBypass $true**.
3. Make sure that the required ports are opened.

## Migrate from non-bypassed trunks to bypass-enabled trunks

You can switch all users at once or you can implement a phased approached (recommended).

- **Switch all users at once.** If all conditions are met, you can turn on bypass mode. However, all your production users are switched at the same time. Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.
- **Phased approach. (Recommended)**. Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.

    This approach is recommended because it allows for a smoother transition and uninterrupted user experience. This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall. Note you'll need to make sure that your certificate supports both trunks. In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.

![Migrate from non-bypassed trunks to bypass-enabled trunks).](media/direct-routing-media-bypass-8.png)

For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:

- [AudioCodes deployment documentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle deployment documentation](https://www.oracle.com/communications/partner-microsoft/)
- [Ribbon Communications deployment documentation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) deployment documentation](https://www.anynode.de/anynode-and-microsoft-teams/)

For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers).