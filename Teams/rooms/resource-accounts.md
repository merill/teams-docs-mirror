---
layout: Conceptual
title: Microsoft Teams Rooms Resource Accounts - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/resource-accounts
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: sohailta
ms.date: 2026-04-28T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Learn how to see the status of your resource accounts information; and the information pertaining to mailbox settings, location, and license.
locale: en-us
document_id: 1c45b8a6-0a93-e50a-44e7-9f5f7a812410
document_version_independent_id: 1c45b8a6-0a93-e50a-44e7-9f5f7a812410
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/resource-accounts.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/resource-accounts
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/resource-accounts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: eb97da9c-4f3c-7bf6-aa93-0edf45b3fe19
---

# Microsoft Teams Rooms Resource Accounts - Microsoft Teams | Microsoft Learn

Resource accounts is a feature that enables you to see the status of your resource accounts for Teams Rooms; and the information pertaining to mailbox settings, location, and license.

Important

If you're setting up your Pro Management Portal for the first time, you need to open Planning &gt; Inventory and select the **Get Data** button to connect the Pro Management Portal to your resource accounts in Microsoft 365. Allow 15 minutes for replication once you select the **Get Data** button to see your resource accounts in the portal.

Important

The option of managing resource accounts isn't available for GCC tenants.

## View resource accounts

The **Resource Accounts** page shows you all the resource accounts that your organization created for your Teams Rooms. You can see the account name, user principal name (UPN), and location in different columns for each resource account.

The **Resource Accounts** page also has a **Refresh** option on the command bar to fetch newly created resource accounts from Entra.

Note

Resource accounts with their Exchange property set to "Hide from Global Address List (GAL)" won't be shown in the inventory. Disable "Hide from GAL" to ensure the rooms are visible in your inventory.

### View settings for each resource account

Select a resource account; you're taken to the page showing its settings and other details. In this page, you can see the settings of the account and its mailbox; and information pertaining to the resource account's location and license.

[![Screenshot that shows the Account Configuration tab.](../media/account-configuration-tab.png)](../media/account-configuration-tab.png#lightbox)

To know more about the settings of the account or its mailbox, hover over the setting with the cursor, as shown in the following screenshot:

[![Screenshot that shows the information of a setting displayed on a mouse-hover over the setting.](../media/viewing-information-of-setting-by-mouse-hover.png)](../media/viewing-information-of-setting-by-mouse-hover.png#lightbox)

On the same page, that is, the page containing the settings and other details, you can also see the status of the resource account. The **Status** label at the top shows whether a resource account is correctly set up to be used with Teams Rooms.

[![Screenshot that shows the status of a resource account.](../media/status-of-resource-account.png)](../media/status-of-resource-account.png#lightbox)

The following statuses are supported for resource account settings:

- **No Action Needed**: This status implies that the account and mailbox settings have been configured as required for Teams rooms.
- **Needs Action**: This status implies that the account hasn't been configured correctly, and that we must review our account information.
- **N/A**: This status implies that the account information isn't available.

## Configure resource accounts

To configure the settings of a resource account and its mailbox, perform the following steps:

1. Select a resource account to navigate to the page containing the resource account's settings and other details.
2. Enable the settings under the **Account settings** and **Mailbox settings** panes.

Once you've configured the settings of the account and its other associated settings, you can navigate to the page displaying the settings and other details to verify the status. You can see that the status has been updated (to **No action needed**), under the **Status** label.

[![Screenshot that shows the updated status of a resource account whose settings and that of its mailbox has just been configured.](../media/status-updated-on-configuration-completion.png)](../media/status-updated-on-configuration-completion.png#lightbox)

### View licenses

To view the licenses assigned to a resource account, perform the following steps:

1. Select a resource account and navigate to the page displaying its settings and other details.
2. Select **Licenses** tab. You can view the Teams Rooms licenses that have been assigned to the chosen resource account.

    [![Screenshot that shows the page displaying details of licenses assigned to a resource account.](../media/licenses-assigned-to-resource-account.png)](../media/licenses-assigned-to-resource-account.png#lightbox)

### Other information

This section lists crucial alert messages and their descriptions:

| Message | Description |
| --- | --- |
| Mailbox settings aren't available. You need to be a admin to get this information. Contact your administrator to get access. | This message appears if the users don't have permissions. Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role. |
| An error occurred while loading resource account(s). If the problem persists please contact support. | This message appears when an error has occurred while loading accounts. |
| An error occurred while loading summary, please try again later. If the problem persists please contact support. | This message appears when an error has occurred while loading stats. |
| An error occurred while exporting file, please try again later. If the problem persists, please contact support. | This message appears when an error has occurred while exporting resource accounts. |
| An error occurred while saving your request, please try again later. If the problem persists, please contact support. | This message appears when an error has occurred while saving mailbox settings. |
| Your changes have been saved successfully. | This message appears when the mailbox settings have been saved successfully. |
| An error occurred while applying recommended config. Please try again later. If the problem persists, please contact support. | This message appears when an error has occurred while applying recommended configuration to resource accounts. |