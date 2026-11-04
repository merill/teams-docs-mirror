---
layout: Conceptual
title: Turn off Communication Credits auto recharge for Microsoft MCA Customers - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/turn-off-communication-credits-auto-recharge-mca-customers
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.reviewer: dachocro
ms.date: 2026-04-30T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 691c9301-1f66-41fe-9b2c-ca24ae987463
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- admindeeplinkMAC
description: Learn how to turn off Communication Credits automatic recharge if you're a Microsoft Customer Agreement (MCA) customer.
locale: en-us
document_id: 0d8f6008-136f-52a1-70c8-f721f1be0491
document_version_independent_id: efaeb679-a1c9-ab98-9f0b-f253a19cecec
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/turn-off-communication-credits-auto-recharge-mca-customers.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: turn-off-communication-credits-auto-recharge-mca-customers
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/turn-off-communication-credits-auto-recharge-mca-customers.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/32a16317-1f6b-490b-86ee-a2f31dda9381
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/04d891c0-5bfa-4605-a844-964f64f59c36
platformId: 13f2bd11-0b06-8361-926a-77d7f37ca1cf
---

# Turn off Communication Credits auto recharge for Microsoft MCA Customers - Microsoft Teams | Microsoft Learn

Microsoft Customer Agreements (MCA) allow customers to pay for services *after* the services were consumed, also known as post-usage billing.

Because Communication Credits are a prepaid budget to support outgoing minutes, they're not available to purchase for customers with MCA Calling and Audio Conferencing subscriptions.

- For more information about the types of billing accounts, see [Understand your Microsoft business billing account](/en-us/microsoft-365/commerce/manage-billing-accounts).
- To learn how to check if your tenant has an MCA calling subscription, see [View my billing accounts](/en-us/microsoft-365/commerce/manage-billing-accounts#view-my-billing-accounts).

Most customers not using an MCA have the *Automatic Top Up* (ATU) flag enabled within their account. The ATU flag automatically refills your Communication Credit balance to the threshold you selected. **MCA customers need to turn this setting off.**

## How to turn off the auto-recharge setting

When switching to an MCA, you need to disable this ATU option. Otherwise, the Communication Credit balance indefinitely refills itself, and the commerce system doesn't switch to the post-usage mechanism under an MCA.

If you're moving to an MCA subscription, turn off automatic recharge by completing the following steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) with your admin credentials.
2. In the left navigation, go to **Billing** &gt; **Your products**.
3. Select **Communication Credits** in your list of products.
4. On the Communication Credits page, find the **Billing settings** section, and then select **Edit auto recharge settings**.
5. On the Auto-recharge settings page, clear the **Auto recharge** checkbox.
6. Select **Save**.

When this process is complete, you can transition to an MCA before your Communication Credit balance is empty. Even as an MCA customer, the commerce system consumes your Communication Credit balance before changing to post-usage billing. There's no extra action needed by you to ensure this switch happens.