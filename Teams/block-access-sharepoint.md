---
layout: Conceptual
title: Block access to SharePoint for specific users - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/block-access-sharepoint
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: Nigolc
ms.date: 2020-07-23T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: msteams-admin
audience: Admin
ms.collection:
- M365-collaboration
- trust-pod
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about how to block access to SharePoint for specific users
locale: en-us
document_id: 2308e7ef-1a9a-0fd1-53c4-7b6e5387978a
document_version_independent_id: 9d9a661f-841c-6b3b-b579-f4e507bcbddd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/block-access-sharepoint.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: block-access-sharepoint
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/block-access-sharepoint.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f654f13f-231f-1a0b-064c-cb39e805beca
---

# Block access to SharePoint for specific users - Microsoft Teams | Microsoft Learn

Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams. However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices. Under the CA policy rules, blocking SharePoint would lead to blocking Teams as well. This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.

Note

Blocking or limiting access on unmanaged devices relies on Microsoft Entra Conditional Access policies. Learn about [Microsoft Entra ID licensing](https://azure.microsoft.com/pricing/details/active-directory/). For an overview of conditional access in Microsoft Entra ID, see [Conditional access in Microsoft Entra ID](/en-us/azure/active-directory/conditional-access/overview). For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](/en-us/microsoft-365/enterprise/sharepoint-file-access-policies). If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](/en-us/azure/active-directory/conditional-access/concept-conditional-access-conditions#supported-browsers), or they will also have limited access.

You can block or limit access for:

- Users in the organization or only some users or security groups.
- All sites in the organization or only some sites.

When access is blocked, users will see an error message. Blocking access helps provide security and protects secure data. When access is blocked, users will see an error message.

1. Open the SharePoint Admin Center.
2. Expand **Policies** &gt; **Access Policies**.
3. In the **Unmanaged Devices** section, select **Block Access** and select **Save**.

    ![the Unmanaged devices section for Policies.](media/no-sharepoint-access1.png)
4. Open the [Microsoft Entra ID](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.

    You'll see a new policy has been created by SharePoint that's similar to this example:

    ![a new policy that's named Use app-enforced Restrictions for browser access.](media/no-sharepoint-access2.png)
5. Update the policy to target only specific users or a group.

    ![the SharePoint admin center with the Select user section highlighted.](media/no-sharepoint-access2b.png)

Note

Setting this policy will cut your access to the SharePoint admin portal. We recommended that you configure the exclusion policy and select the Global and SharePoint admins.

1. Verify that only SharePoint is selected as targeted Cloud App

    ![SharePoint is selected as the targeted app.](media/no-sharepoint-access3.png)
2. Update **Conditions** to include desktop clients, as well.

    ![desktop and mobile apps highlighted.](media/no-sharepoint-access4.png)
3. Make sure that **Grant access** is enabled

    ![grant access is enabled.](media/no-sharepoint-access5.png)
4. Make sure **Use app enforced restrictions** is enabled.
5. Enable your policy and select **Save**.

    ![The app enforced restrictions is enabled.](media/no-sharepoint-access6.png)

To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working. If your access has been blocked, you'll see a message in Teams that states the item might not exist.

![The item not found message.](media/access-denied-sharepoint.png)

In SharePoint, you'll receive an access denied message.

![The access denied message.](media/blocked-access-warning.png)