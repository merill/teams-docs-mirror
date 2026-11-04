---
layout: Conceptual
title: Collaborate with guests from other Microsoft 365 cloud environments - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/collaborate-guests-cross-cloud
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: false
author: MJMicrosoft
manager: David-Rosenthal
ms.author: majaisin
ms.reviewer: dacarrol
ms.date: 2026-08-06T00:00:00.0000000Z
audience: ITPro
ms.topic: how-to
ms.service: m365-planning
ms.collection:
- highpri
- Tier1
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
- guest-access-external-collab
ms.custom: m365-solutions-doc-set
ms.localizationpriority: medium
f1.keywords: NOCSH
description: Enable guest collaboration between Microsoft 365 cloud environments, configure cross-tenant access, and follow these steps to collaborate securely.
locale: en-us
document_id: d8f2f936-79aa-7ea5-4d87-d735880db659
document_version_independent_id: d8f2f936-79aa-7ea5-4d87-d735880db659
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/collaborate-guests-cross-cloud.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: collaborate-guests-cross-cloud
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/collaborate-guests-cross-cloud.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68ec7f3a-2bc6-459f-b959-19beb729907d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/90370425-aca4-4a39-9533-d52e5e002a5d
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4fa17403-15f3-62c3-777f-594104c8f001
---

# Collaborate with guests from other Microsoft 365 cloud environments - Microsoft Teams | Microsoft Learn

This article explains how to enable guest collaboration between Microsoft 365 cloud environments so users can work with external guests across Azure clouds. Microsoft 365 organizations have one of several tenant types and are located in one of three Microsoft Azure clouds:

| Microsoft Azure cloud environment | Microsoft 365 cloud environment |
| --- | --- |
| Microsoft Azure Commercial | Commercial, GCC |
| Microsoft Azure Government | GCC High, DoD |
| Microsoft Azure China | China (21Vianet) |

To invite guests from an organization in a different Microsoft Azure cloud environment, complete the following steps:

1. If the organization you want to collaborate with is in a different Microsoft Azure cloud environment (such as commercial and DoD), enable cross-tenant connections with that Microsoft Azure cloud environment.
2. Set up cross-tenant access settings in Microsoft Entra ID with the organization that you want to collaborate with.

Tenants in Microsoft Azure Government (Microsoft 365 GCC High and DoD) can't create a cross-tenant connection with tenants in Microsoft Azure China.

Note

VDI clients using the new [SlimCore-based optimization](/en-us/microsoftteams/vdi-2#cross-cloud-collaboration) support cross-cloud meetings. WebRTC-based optimization doesn't support cross-cloud meetings.

Note

B2B Member accounts aren't supported for cross cloud guests. All cross cloud users must be of type B2B guest.

Important

The organization that you're collaborating with must also configure these settings for their organization.

## Prerequisites

To invite guests from organizations in other Microsoft 365 cloud environments, you need to configure guest access for your organization. If you haven't previously configured guest access, see one of the following articles depending on your scenario:

- [Collaborate with guests on a document](/en-us/previous-versions/microsoft-365/solutions/collaborate-on-documents)
- [Collaborate with guests in a site](/en-us/previous-versions/microsoft-365/solutions/collaborate-in-site)
- [Collaborate with guests in a team](/en-us/previous-versions/microsoft-365/solutions/collaborate-as-team)

Additionally, to enable B2B collaboration with an organization in a different Microsoft 365 cloud environment, you need the organization's tenant ID. If you know the fully qualified domain name of the other organization, you can look up the tenantID in the Teams admin center. Open [meeting settings](https://admin.teams.microsoft.com/meetings/settings), select **Lookup** under **Cross-cloud meetings**, type in the fully qualified domain name, and select **Show tenant ID**.

For the best meeting experiences across Microsoft clouds, make sure your network is ready for Microsoft Teams. [Prepare your organization's network for Microsoft Teams](/en-us/microsoftteams/prepare-network#network-requirements) contains guidance on how to optimize your network for Teams. Also ensure that the necessary DNS, IPs, and ports are enabled for each of the Microsoft 365 clouds where your users are collaborating. The following table links to the endpoint definitions for each of the Microsoft 365 cloud environments:

| Microsoft 365 Cloud Environment | Endpoints |
| --- | --- |
| Commercial, GCC | [Worldwide endpoints](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges) |
| GCC High | [U.S. Government GCC High endpoints](/en-us/microsoft-365/enterprise/microsoft-365-u-s-government-gcc-high-endpoints) |
| DoD | [U.S. Government DoD endpoints](/en-us/microsoft-365/enterprise/microsoft-365-u-s-government-dod-endpoints) |
| China (21Vianet) | [Microsoft 365 operated by 21Vianet](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges-21vianet) |

## Allow cross-tenant connections with other Microsoft 365 cloud environments

If you're setting up guest sharing with a tenant that's in a different Azure cloud environment than yours, you need to enable connections with that cloud environment before you add the organizational relationship.

Enable the Microsoft Azure cloud environment you want to collaborate with in Microsoft Entra cross tenant access settings.

1. Sign in to [Microsoft Entra ID](https://aad.portal.azure.com) by using a Security administrator account.
2. Select **External Identities**, and then select **Cross-tenant access settings**.
3. Select **Microsoft cloud settings**.
4. Select the checkboxes next to the external Microsoft Azure cloud environments you want to enable.

    [![Screenshot of the Microsoft cloud settings page in Microsoft Entra ID.](media/cross-cloud-settings.png)](media/cross-cloud-settings.png#lightbox)

### Add an organization

After you enable the cloud environments you want to collaborate with, add the specific organizations for B2B collaboration. Unlike B2B collaboration with organizations in the same cloud environment, B2B collaboration with organizations in different Microsoft 365 cloud environments requires that each organization be added to Microsoft Entra cross-tenant access settings.

To add an organization:

1. Sign in to [Microsoft Entra ID](https://aad.portal.azure.com) by using a Security administrator account.
2. Select **External Identities** and then select **Cross-tenant access settings**.
3. Select **Organizational settings**.
4. Select **Add organization**.
5. On the **Add organization** pane, enter the tenant ID for the organization and press Enter.

    Note

    You can't search on domain names from other clouds.
6. Select **Add**.
7. The organization appears in the organizations list. At this point, all access settings for this organization inherit from your default settings.

New organizations inherit B2B collaboration settings from the default. If your default settings block B2B collaboration or if you want to limit collaboration to specific users or groups, update the organization's inbound and outbound settings.

#### Configure inbound settings for the organization

Use the inbound settings to specify which users or groups from the external organization can access resources in your organization.

To configure inbound settings for an organization:

1. Select the inbound access link for the organization that you want to modify.
2. On the **B2B collaboration** tab, choose **Customize settings**.
3. On the **External users and groups** tab, choose **Allow access** and **All &lt;organization&gt; users and groups**. You can choose **Select &lt;organization&gt; users and groups** if you want to limit access to specific users and groups, such as those who signed a non-disclosure agreement.
4. If you want to limit guest access to Microsoft 365, select the **Office 365** application on the **Applications** tab.
5. Select **Save** and close the **Inbound access settings** pane.

#### Configure outbound settings for the organization

Use the outbound settings to specify which users or groups from your organization can access resources in the external organization.

To configure outbound settings for an organization:

1. Select the outbound access link for the organization that you want to modify.
2. On the **B2B collaboration** tab, choose **Customize settings**.
3. On the **Users and groups** tab, choose **Allow access** and set an **Applies to** of all users, or select the users or groups that you want to allow to access the external organization.
4. Select **Save**, choose **Yes** to confirm, and close the **Outbound access settings** pane.