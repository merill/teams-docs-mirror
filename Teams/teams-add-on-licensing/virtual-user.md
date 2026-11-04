---
layout: Conceptual
title: Microsoft Teams Phone Resource Account licenses - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-add-on-licensing/virtual-user
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: roykuntz
ms.date: 2026-04-26T00:00:00.0000000Z
ms.topic: reference
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-collaboration
- tier1
audience: Admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- admindeeplinkMAC
description: Learn how to assign Microsoft Teams Phone Resource Account licenses to resource accounts for auto attendants and call queues in your organization.
locale: en-us
document_id: d6891495-01c6-117b-c28b-28232782ba74
document_version_independent_id: 1c23b35a-e9ba-ffdd-9baa-a3f83f4ed9ca
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-add-on-licensing/virtual-user.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-add-on-licensing/virtual-user
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-add-on-licensing/virtual-user.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: ffd9c4d9-a92e-25db-beb0-bb1e09c73d65
---

# Microsoft Teams Phone Resource Account licenses - Microsoft Teams | Microsoft Learn

Note

There is no longer any cost associated with acquiring Teams Phone Resource Account licenses.

In Microsoft Teams, auto attendants and call queues that directly answer calls require an associated resource account. Each resource account must be assigned a **Microsoft Teams Phone Resource Account** license to ensure they're correctly identified by the system and properly function, *regardless of whether the resource account will be assigned a telephone number*.

A Microsoft calling plan isn't required unless you want to be able to dial out using that resource account. For more information, see [Plan for Teams auto attendant and call queues](../plan-auto-attendant-call-queue).

The **Teams Phone Resource Account** license should never be assigned to users that aren't resource accounts.

Note

All resource accounts must be assigned a **Teams Phone Resource Account** license, regardless of whether they'll be assigned a phone number or not.

If you're currently using resource accounts that aren't assigned any license, you should revisit them to ensure they're assigned a **Teams Phone Resource Account** license.

Don't assign a **Teams Phone Standard** license to a resource account. If you currently have resource accounts configured with **Teams Phone Standard** licenses, you must switch to a **Teams Phone Resource Account** license as described below.

## How to obtain Microsoft Teams Phone Resource Account licenses

You obtain Teams Phone Resource Account licenses from the same purchasing channel you purchased the subscription containing Teams Phone. For example, if you purchased Resource Account licenses through an Enterprise Agreement (EA), you need to order through EA.

For Web Direct customers:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Go to **Marketplace** &gt; **All products**.
3. Search for *Resource* and select **Microsoft Teams Phone Resource Account**.
4. Scroll to find the **Microsoft Teams Phone Resource Account** license.
5. Select the **Details** button.
6. Choose the number of licenses you wish to purchase, your subscription length and billing frequency.
7. Select the **Buy** button.
8. Fill in the purchasing details.
9. Select the **Place order** button.

    Note

    You must still **Buy** the license even though it has a cost of zero.

## Change an existing resource account to use a Microsoft Teams Phone Resource Account license

If you have existing resource accounts using a **Teams Phone Standard** license, you must switch to using to a **Teams Phone Resource Account** license:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Purchase the new **Teams Phone Resource Account** license.
3. Go to Users &gt; Active users &gt; Find the Existing resource account that you want to update licenses for &gt; Manage product licenses &gt; Licenses and apps &gt; Uncheck the "Teams phone standard" license to unassign it from this resource account and then Check the "Microsoft Teams Phone Resource Account Licenses" to assign this new license to the resource account.
4. Click Save changes
5. For more information refer [Assign or unassign licenses for users in the Microsoft 365 admin center](/en-us/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

Warning

Always remove a **Teams Phone Standard** license and assign the **Teams Phone Resource Account** license in the same license activity. If you remove the old license, save the account changes, add the new license, and save the account settings again, the resource account may no longer function as expected, like your organization's auto attendants and call queues not working anymore.

If this happens, we recommend you create a new resource account using the **Teams Phone Resource Account** license and remove the broken resource account.