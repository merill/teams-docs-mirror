---
layout: Conceptual
title: Phone numbers and licensing changes - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phone-numbers-licensing-changes
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
ms.date: 2025-05-09T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: Medium
f1.keywords:
- CSH
ms.custom:
- has-azure-ad-ps-ref
- azure-ad-ref-level-one-done
description: Learn how licensing changes can affect phone number management.
locale: en-us
document_id: 3275e03f-6c8e-a61f-2d0b-52b0bc45e0d7
document_version_independent_id: 3275e03f-6c8e-a61f-2d0b-52b0bc45e0d7
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phone-numbers-licensing-changes.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phone-numbers-licensing-changes
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phone-numbers-licensing-changes.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: ed1a5776-0f85-7eab-f876-4721d5532fd4
---

# Phone numbers and licensing changes - Microsoft Teams | Microsoft Learn

How you remove and assign licenses to users can impact a user's ability to make and receive Public Switched Telephone Network (PSTN) calls in Microsoft Teams. This article describes how you can manage licensing changes to ensure your users' ability to make and receive PSTN calls isn't impacted.

For general information on managing phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-landing-page). For general information on Teams add-on licensing, see [Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).

## Remove a license

If you have a user with an assigned phone number and you remove one or more of the prerequisites licenses, it unassigns the phone number from the user. Without an assigned phone number, the user's ability to make and receive PSTN calls in Microsoft Teams is impacted.

Depending on the user's [PSTN connectivity option](pstn-connectivity), removing a license has the following impact on telephony parameters:

- **Removing a Microsoft 365 Calling Plan license from a user with a Calling Plan phone number** will:

    - Copy any value in OnPremLineUri to LineUri
    - Set EnterpriseVoiceEnabled to False
    - Set phone number assignment status to Unassigned in the phone number database
- **Removing a Microsoft 365 Phone System license from a user with an Operator Connect phone number** will:

    - Clear LineUri
    - Set EnterpriseVoiceEnabled to False
    - Set the phone number’s assignment status to Unassigned in the phone number database
- **Removing a Microsoft 365 Phone System license from a user with a Direct Routing phone number** will:

    - Clear LineUri
    - Set EnterpriseVoiceEnabled to False
    - Remove the phone number from the phone number database

## Change a license

You may need to change a license for a user that involves one of the prerequisite licenses. When you make a prerequisite license change, ensure that the changes are made in one operation and saved at the same time. This method ensures that the user keeps their assigned phone number and can continue making and receiving PSTN calls in Microsoft Teams.

For example, assume you want to assign a Microsoft 365 E5 license to a user who currently has a Microsoft 365 E3 license.

- If you're using Teams admin center, in the **Licenses and apps** tab on the user details, ensure that the old license is removed and the new license is added before you click **Save changes**.
- If you're using the PowerShell cmdlet [Set-MgUserLicense](/en-us/powershell/module/microsoft.graph.users.actions/set-mguserlicense), execute the cmdlet once and use both the -AddLicenses and the -RemoveLicenses parameters.

(If you remove the old license and save the change, and then add the new license and save the change, the phone number is unassigned and the user might lose the ability to make and receive PSTN calls in Microsoft Teams. After assigning the new license, you’ll need to re-assign the phone number to the user.)

For information about how to change the license simultaneously with group-based licensing, see [Change license assignments for a user or group in Microsoft Entra ID](/en-us/azure/active-directory/enterprise-users/licensing-groups-change-licenses).