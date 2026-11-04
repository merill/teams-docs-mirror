---
layout: Conceptual
title: Add places to emergency locations - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/add-change-remove-emergency-place-organization
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
ms.date: 2026-09-17T00:00:00.0000000Z
ms.topic: how-to
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
- NOCSH
description: Learn how to add a place for an emergency location and assign a place to your users.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 95e37447-e86a-a47c-7a00-e369b5767fc4
document_version_independent_id: bf737b00-9fe6-2999-b8bd-9d462399c2c9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/add-change-remove-emergency-place-organization.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: add-change-remove-emergency-place-organization
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/add-change-remove-emergency-place-organization.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/5cf46315-b33f-4e99-8224-a1592697eff9
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/715d24c3-3683-4219-82c5-1e3c813fb7fc
platformId: 112b946d-a7b6-092d-c315-2f82fc22de5b
---

# Add places to emergency locations - Microsoft Teams | Microsoft Learn

This article explains how to add places to an emergency location. It also describes how to assign a place for an emergency location to a user or phone number. Before reading this article, ensure you read [Manage emergency locations](add-change-remove-emergency-location-organization).

Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.

This article applies to Microsoft Calling Plans, Operator Connect, Teams Phone Mobile, and Direct Routing.

You can manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.

## Add a place to an emergency location

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Locations** &gt; **Emergency addresses**.
2. In the list, select the name of the location for which you want to add a place.
3. On the **Places** tab, select **Add**.
4. Enter a place name.
5. Optionally, enter an Emergency Location Identification Number (ELIN). To learn more, see [Emergency location identification number applications](considerations-direct-routing#emergency-location-identification-number-applications).
6. Select **Apply**.

### Using PowerShell

See [New-CsOnlineLisLocation](/en-us/powershell/module/teams/new-csonlinelislocation).

## Change a place for an emergency location

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Locations** &gt; **Emergency addresses**.
2. In the list, select the name of the location for which you want to change a place.
3. On the **Places** tab, select the place you want to change, and then select **Edit**.
4. Update the place information, and then select **Apply**.

### Using PowerShell

See [Set-CsOnlineLisLocation](/en-us/powershell/module/teams/set-csonlinelislocation). If you need to update the Emergency Location Identification Number (ELIN), don't set the ELIN attribute to an empty or null string. Otherwise, you receive an error.

## Remove a place from an emergency location

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Locations** &gt; **Emergency addresses**.
2. In the list, select the name of the location for which you want to remove a place.
3. On the **Places** tab, select the place you want to remove, and then select **Delete**.

Note

Places assigned to a user or a phone number can't be deleted. To delete a place, first assign associated users and phone numbers to a different location, then delete the place.

### Using PowerShell

See [Remove-CsOnlineLisLocation](/en-us/powershell/module/teams/remove-csonlinelislocation).

## Assign a place to your users

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Voice** &gt; **Phone numbers**.
2. On the **Phone numbers** page, go to the **Numbers** tab, select a user number in the list, and then select **Edit**.
3. On the **Edit** pane, under **Emergency location**, do one of the following:

    - To assign a place, search for the location or place, and then select the place in the search results.
    - To change the place that's already assigned to the user, select **X** to remove the existing location and place, search for and then select the place you want to assign.
4. Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**. By default, this setting is **On**.
5. Select **Apply**.

### Using PowerShell

See [Set-CsPhoneNumberAssignment](/en-us/powershell/module/teams/set-csphonenumberassignment).