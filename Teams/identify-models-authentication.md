---
layout: Conceptual
title: Identity models and authentication for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/identify-models-authentication
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: DivySri-RK
ms.author: divyasrirk
manager: prgholve
ms.date: 2020-09-25T00:00:00.0000000Z
ms.topic: reference
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: 
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- trust-pod
description: Learn about the different identity models for Microsoft Teams such as cloud-only and hybrid. Also learn about multifactor authentication.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: e6383162-7bcd-70cc-f7dd-b818d236bfdf
document_version_independent_id: 34c9897a-29ae-0048-30ce-da5abaffb76a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/identify-models-authentication.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: identify-models-authentication
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/identify-models-authentication.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/6ab06385-661e-4214-8870-bbe4071c960d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/131ba09e-4280-4ae7-8622-1f9f1c0daad1
platformId: dc050cf5-fa7f-d945-1699-17d3dcce6d21
---

# Identity models and authentication for Microsoft Teams - Microsoft Teams | Microsoft Learn

Microsoft Teams supports all the identity models that are available with Microsoft 365 and Office 365, which include:

- **Cloud-only**: User accounts are created and managed in Microsoft 365 or Office 365 and stored in Microsoft Entra ID. User sign-in credentials (account name and password) are validated by Microsoft Entra ID.
- **Hybrid**: User accounts are typically managed in an on-premises Active Directory Domain Services (AD DS) forest. Depending on the configuration, credential validations are done by Microsoft Entra ID, AD DS, or a federated identity provider. This model uses directory synchronization from AD DS to Microsoft Entra ID with Microsoft Entra Connect.

For more information, see [Microsoft 365 identity models and Microsoft Entra ID](/en-us/microsoft-365/enterprise/about-microsoft-365-identity).

## Configurations

Depending on your organization's decisions of which identity model and configuration you use, the implementation steps may vary.

If you haven't already deployed Microsoft 365 or Office 365 and an identity model, use this table.

| Identity Model | Deployment Checklist | Additional information |
| --- | --- | --- |
| All | 1. Compare Microsoft 365 and Office 365 plan options and obtain a subscription and a tenant.<br>2. Create a Microsoft 365 or Office 365 organization for your tenant.<br>3. Purchase Microsoft 365 or Office 365 licenses for the tenant<br>4. Configure domains and admin user accounts. | - [Office 365 plan options](/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)<br>- [Compare Microsoft 365 for business Plans](https://go.microsoft.com/fwlink/?linkid=854617)<br>- [Buy or remove subscription licenses](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)<br>- [Add licenses to a subscription](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)<br>- [Set up Microsoft 365 for business](/en-us/microsoft-365/admin/setup/setup?view=o365-worldwide)<br>- [Add a domain with the setup wizard](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)<br><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) is available to assist you. |
| Cloud identity | - Create user accounts with the Microsoft 365 admin center | - [Add users and assign licenses](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) |
| Hybrid identity | 1. Install Microsoft Entra Connect.<br>2. Configure directory synchronization.<br>3. Manage users and groups with AD DS tools. | - [Set up directory synchronization](/en-us/microsoft-365/enterprise/set-up-directory-synchronization) |
| Hybrid identity with federated authentication | 1. Install and configure a federated identity provider such as AD FS.<br>2. Install Microsoft Entra Connect and configure directory synchronization and federated authentication.<br>3. Manage users and groups with AD DS tools. | - [Plan your AD FS deployment](/en-us/previous-versions/azure/azure-services/dn151324%28v=azure.100%29)<br>- [Checklist: Deploy your federation server farm](/en-us/previous-versions/azure/azure-services/dn528856%28v=azure.100%29)<br>- [Configure extranet access for AD FS](/en-us/previous-versions/azure/azure-services/dn528859%28v=azure.100%29)<br>- [Set up a trust between AD FS and Microsoft Entra ID](/en-us/previous-versions/azure/azure-services/jj205461%28v=azure.100%29)<br>- [Verify and manage single sign-on with ADFS](/en-us/previous-versions/azure/azure-services/jj151809%28v=azure.100%29)<br>- [Set up directory synchronization](/en-us/microsoft-365/enterprise/set-up-directory-synchronization) |
|  |  |  |

## Multifactor authentication

Passwords are the most common method of authentication for signing in to a computer or online service, but they're also the most vulnerable. People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.

To provide an extra level of security for sign-ins, use multifactor authentication (MFA), which requires both a password and other verification method such as:

- A text message sent to a phone that requires the user to type a verification code.
- A phone call.
- The Microsoft Authenticator smart phone app.
- Other methods available with hybrid identity and federated authentication.

MFA is supported with any Microsoft 365 or Office 365 plan that includes Microsoft Teams. It's highly recommended that at a minimum you require MFA for that accounts that are [assigned administrator roles](/en-us/microsoft-365/admin/add-users/about-admin-roles), such as Teams service admin.

You should also roll out MFA to your users. Once your users are enrolled for MFA, the next time they sign in, they'll see a message that asks them to set up their extra verification method.

For more information, see [multifactor authentication for Microsoft 365](/en-us/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).