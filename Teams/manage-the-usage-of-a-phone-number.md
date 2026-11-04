---
layout: Conceptual
title: Manage the usage of a phone number - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-the-usage-of-a-phone-number
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: julienp
ms.date: 2025-04-04T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
ms.subservice: teams-calling
search.appverid: 
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Learn how to change the usage of a phone number to be used as either a service number or a user number.
locale: en-us
document_id: caf23f5e-0d33-ed26-50df-fef89bb0a0e4
document_version_independent_id: caf23f5e-0d33-ed26-50df-fef89bb0a0e4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-the-usage-of-a-phone-number.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-the-usage-of-a-phone-number
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-the-usage-of-a-phone-number.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3fe5fd1b-7109-271e-7fca-34510c37b184
---

# Manage the usage of a phone number - Microsoft Teams | Microsoft Learn

Microsoft Teams supports using telephone numbers for different purposes. A telephone number's purpose in Teams can be to support a single end user or shared device, or to support services that support your organization.

The purpose of the telephone number is indicated as it's *usage*.

There are three types of number usages in Teams:

- **User** for phone numbers assigned directly to a user or a person.
- **Voice app** for phone numbers assigned to an Auto attendant or Call queue.
- **Conference** for phone numbers assigned to an Audio conferencing bridge.

For more information about types of phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-landing-page).

You might want to change the usage of a phone number, when you want to assign it to a different purpose.

Before changing the usage of a number:

- Be sure you have the right licenses for the target type of number usage.
- You can only assign toll-free numbers to voice apps (Auto attendants and Call queues) and Audio conferencing bridges.

## How to manage the usage of a phone number

You can change the usage of your organization phone numbers by using the Teams admin center.

To change the usage of a phone number by using the Teams admin center:

1. Open the Microsoft Teams admin center and log in with a Teams Telephony Administrator or higher account.
2. In the left navigation, select **Voice** &gt; **Phone numbers**.
3. On the **Phone numbers** page, choose an unassigned number in the list, and then select **Change usage**.

    If you don't see a **Change usage** option, check the following:

    - Make sure you're selecting an unassigned number before trying to change its usage. The value of the **Assignment status** column should be **Unassigned.** Otherwise, the option isn't available.
    - If the number is currently assigned, you need to [remove the phone number from a user](/en-us/MicrosoftTeams/assign-change-or-remove-a-phone-number-for-a-user#remove-a-phone-number-from-a-user) or resource account first. To unassign a number from a conference bridge, see [Change numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge#steps-when-you-unassign-a-service-phone-number-for-a-conferencing-bridge).
    - Make sure you have more types of usage in the **Available usages** column than in the **Licensed usages** column. Otherwise, number usage change option isn't applicable.
4. In the **Change usage** pane, open the list of available usages for the phone number, and then select the intended option.
5. Select **Apply** to set the Licensed usage.

Note

The list of available usages for the telephone number might vary depending on its type (geographic, or toll-free), country or region, and provider. You can quickly review the available usages for each phone number by setting the **Available usages** column in the Phone numbers table to visible.

Important

Microsoft recommends that you use roles with the fewest permissions. Least privileged access practices help improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role. To learn more, see [About administrator roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles) and [Teams administrator roles](using-admin-roles).

## Still need assistance?

If you still need assistance, contact the [Telephone Number Services - Service Desk](/en-us/MicrosoftTeams/manage-phone-numbers-for-your-organization/contact-tns-service-desk).