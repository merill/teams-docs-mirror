---
layout: Conceptual
title: Entra ID Join for Teams Rooms on Windows - Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/mtrw-entraid-join
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to configure your environment and successfully Entra ID join a Teams Rooms on Windows device
author: MattSlomka
ms.author: mattslomka
manager: kimmatlock
ms.service: msteams
ms.topic: how-to
ms.date: 2026-08-12T00:00:00.0000000Z
ms.subservice: itpro-rooms
locale: en-us
document_id: 4f8c56db-db69-702b-78f7-e2bc49c13690
document_version_independent_id: 4f8c56db-db69-702b-78f7-e2bc49c13690
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/mtrw-entraid-join.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/mtrw-entraid-join
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/mtrw-entraid-join.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 023b4843-78f8-0bb5-3b9b-f690ff0dc6b4
---

# Entra ID Join for Teams Rooms on Windows - Teams | Microsoft Learn

Teams Rooms on Windows devices run the underlying Windows operating system that can be connected to [Microsoft Entra ID](/en-us/entra/identity/devices/concept-directory-join) to allow Entra ID accounts to sign into Windows. Entra ID joining a Teams Rooms on Windows device enables storage of platform credentials and granular control over access to the Teams Rooms device administrative settings.

Note

A Teams Rooms on Windows device must be Entra ID joined for devices/accounts to transition to [password-less resource accounts](/en-us/MicrosoftTeams/rooms/passwordlessentraresourceaccounts).

The recommended way to connect Teams Rooms on Windows devices to Entra ID is to do so automatically using [Autopilot and Autologin](/en-us/microsoftteams/rooms/autopilot-autologin). If Autopilot and Autologin aren't used to deploy the device, Entra ID join can be completed manually. Manual Entra ID join can be completed in three ways:

1. The Teams Resource Account credentials (covered in this article).
2. A device enrollment account ([Learn More](/en-us/intune/device-enrollment/setup-enrollment-manager)).
3. A Windows Configuration Designer package ([Learn More](/en-us/intune/device-enrollment/windows/create-bulk-package)).

## Allow Resource Accounts to join devices to Microsoft Entra ID

1. Sign in to the [Azure portal](https://portal.azure.com/).
2. Select **Microsoft Entra ID**.
3. In the **Overview** screen, under **Manage** in the left pane, select **Devices**.
4. In the **Devices | Overview** screen, under **Manage** in the left pane, select **Device Settings**.
5. In the **Devices | Devices** **settings** screen, under **Users may join devices to Microsoft Entra**, select **All** or **Selected**.

    1. If **All** is selected, resource accounts can join devices to Entra ID.
    2. If **Selected** is selected, only specific accounts can be used to complete the Entra ID join.

        1. Select the link under **Selected**.
        2. Review the groups or users selected to confirm if resource accounts are included in that scope. If not, add the relevant resource accounts or resource account group created in prior steps.
        3. Select **OK**.
6. In the **Devices | Overview** screen, select **Save**.

## Join a Teams Room on Windows device to Entra ID

1. From the Teams Rooms console, switch to [admin mode](/en-us/microsoftteams/rooms/rooms-operations#switching-to-admin-mode) by selecting **More (...)** and then select **Settings**.
2. Enter the administrative credentials.
3. Select **Windows Settings**.
4. Log in to the desktop with administrative credentials.
5. At the Windows desktop, select the **start button**.
6. Select **Settings**.
7. Select **Accounts**.
8. Select **Access work or school**.
9. Select **Connect**.
10. Select **Join this device to Microsoft Entra ID**.
11. Sign in with the resource account credentials.
12. Confirm the organization displayed is correct and select **Join**.
13. Restart the device to return to the Teams Rooms application.

Note

A device enrollment manager (DEM) account can also be used following the same instructions above using the DEM account instead of the resource account in step 11.