---
layout: Conceptual
title: Migrating from Slack to Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/slack-to-teams-migration-tool
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.topic: upgrade-and-migration-article
ms.date: 2026-08-31T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: troys
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guidance on migrating data from Slack to Microsoft Teams.
ms.localizationpriority: medium
locale: en-us
document_id: e5004988-3387-9271-91b0-a1348ba363c5
document_version_independent_id: e5004988-3387-9271-91b0-a1348ba363c5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/slack-to-teams-migration-tool.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: slack-to-teams-migration-tool
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/slack-to-teams-migration-tool.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: ea29abb6-811f-b22b-0768-e087ae851d09
---

# Migrating from Slack to Microsoft Teams - Microsoft Teams | Microsoft Learn

The Slack to Teams Migration Tool from Microsoft allows customers to migrate data from their Slack workspace to Microsoft Teams. The current version of the tool migrates the following data:

- Slack channels (public and private).
- Slack channel messages (including threading and standard reactions).
- Slack channel file attachments.
- Slack channel canvas and list content (migrated to HTML and JSON file attachments within the Teams channel, respectively).
- Slack channel membership (owners and members).

The migration tool is a service that runs in the Microsoft 365 admin center. It uses Slack export packages and online access to the customer's Slack workspace to retrieve customer data. Customers generate Slack export packages through the Slack workspace administration interface.

Once the export package is ready, customers upload the export package provided by Slack into a Microsoft Azure Blob Storage container within their own tenant. The customer grants permission for the migration tool to read the export package so it can begin scanning the contents of that export package.

Once the export package content is scanned, the customer can decide which Slack channels to migrate to Microsoft Teams and decide how much content to migrate. For example, customers may wish to migrate all of the data in a channel or only a subset of data based on a date range.

Once these choices are made, the customer maps their Slack users to equivalent Microsoft 365 users. The customer also selects which Microsoft Teams and channels to map their Slack channels to. Mapping can be performed via the migration tool's web UI or via CSV files for larger-scale migrations.

Once migration starts, the Slack data is transformed into equivalent data by the migration tool and imported into Microsoft Teams. No data is deleted from Slack during this migration process.

## Prerequisites

### Slack

Customers must have permission to export their Slack workspace data into an export package. Workspace Owners, Workspace Admins, Org Owners, and Org Admins have sufficient permission, as do members with the Export Admin system role. For more information, see: [Export your workspace data](https://slack.com/help/articles/201658943-Export-your-workspace-data).

### Microsoft 365

1. Administrators performing a migration must have a Microsoft 365 administrator role assignment that has permission to access the Slack to Teams Migration Tool. Any of the following Microsoft 365 administration roles can be used:

    - Microsoft 365 Migration Administrator (recommended)
    - SharePoint Administrator
    - Global Administrator
2. Customers must grant consent to allow the "M365 Teams Migration" app to import data into Microsoft 365. Only a user with the Global Administrator role can grant this one-time consent, which is remembered for all future migrations performed by this migration tool. This consent can be performed at any time before starting a migration by following [this link](https://login.microsoftonline.com/organizations/adminconsent?client_id=830fd2ff-25ae-4585-b538-76b741b7b04b). If this consent isn't granted before starting a migration, the migration tool prompts the migration administrator to provide consent.

    The following [Microsoft Graph permissions](/en-us/graph/permissions-reference) are granted to the "M365 Teams Migration" app through this consent:

    - **Application.ReadWrite.All**: Read and write all applications
    - **Channel.Create**: Create channels
    - **ChannelMember.ReadWrite.All**: Add and remove members from all channels
    - **ChannelSettings.Read.All**: Read the names, descriptions, and settings of all channels
    - **Chat.ReadWrite.All**: Read and write all chat messages
    - **ChatMember.ReadWrite.All**: Add and remove members from all chats
    - **Sites.ReadWrite.All**: Read and write items in all site collections
    - **Team.Create**: Create teams
    - **TeamMember.ReadWrite.All**: Add and remove members from all teams
    - **TeamSettings.Read.All**: Read all teams' settings
    - **TeamsTab.ReadWrite.All**: Read and write tabs in Microsoft Teams.
    - **Teamwork.Migrate.All**: Create chat and channel messages with anyone's identity and with any timestamp
    - **User.Read**: Sign in and read user profile

### Azure Blob Storage

1. Customers must have an Azure Blob Storage account to store their Slack export file. The Microsoft 365 Migration app reads the exported data from the Slack export file hosted in Azure Blob Storage.
2. Customers must have permission to create and manage Azure storage accounts. Any of the following Azure roles can be used:

    - Owner (gives you full control)
    - Contributor (sufficient for creating resources)
    - Storage Account Contributor (minimum requirement)
3. Customers must have the User Access Administrator Azure role to grant permission for the migration app to access the Azure Blob Storage account.

For more information about Azure roles, see [Azure built-in roles](/en-us/azure/role-based-access-control/built-in-roles).

## Migration steps

### Step 1: Grant consent for the Microsoft 365 Teams Migration app to import data into Teams

1. As a user with the Global Administrator role in Microsoft 365, browse to [this site](https://login.microsoftonline.com/organizations/adminconsent?client_id=830fd2ff-25ae-4585-b538-76b741b7b04b).
2. At the **Permissions requested** prompt for the Microsoft 365 Teams Migration app, select **Accept**.

Note

The Global Administrator role is required to provide this one-time consent. Once this consent is provided, it's remembered for all future migrations performed by this migration tool and the Global Administrator role is no longer required to proceed with the migration. You can use other roles, such as Microsoft 365 Migration Administrator or SharePoint Administrator, to perform the migration. If consent isn't provided at this time, the migration app prompts you to provide consent before importing data into Microsoft Teams.

### Step 2: Export Slack workspace data

The steps to perform an export can vary depending on the type of Slack plan your organization is subscribed to. See [Export your workspace data](https://slack.com/help/articles/201658943-Export-your-workspace-data) for the specific steps to follow for your Slack plan.

Note

The steps to export data from private channels may be different than the steps to export data from public channels.

Once the Slack workspace export is ready, download the Slack export ZIP file.

### Step 3: Create an Azure Blob Storage account

1. Browse to the [Microsoft Azure portal](https://portal.azure.com).
2. Select **Storage accounts**.
3. Select **Create**.
4. Fill out the following fields in the **Basics**tab:
    1. **Subscription**: Select your Azure subscription.
    2. **Resource group**: Select an existing resource group or create a new one.
    3. **Storage account name**: Create a new, unique name for your storage account.
    4. **Region**: For all countries outside of Europe, we recommend a US region such as **East US** or **West US 2** for optimal migration performance and minimum Azure bandwidth pricing cost. For countries in Europe, select a European region such as **North Europe** or **West Europe**.
    5. **Performance**: Standard
    6. **Redundancy**: Select **Local Redundant Storage (LRS)** for basic redundancy, or **Geo-Redundant Storage (GRS)** or **Zone-Redundant Storage (ZRS)** for better redundancy.
5. Select **Next** and fill out the following fields in the **Advanced**tab:
    1. **Require secure transfer for REST API operations**: Enabled
    2. **Allow enabling anonymous access on individual containers**: Disabled
    3. **Enable storage account key access**: Disabled
    4. **Default to Azure Active Directory authorization**: Enabled
    5. **Minimum TLS version**: Version 1.2
    6. **Access tier**: Hot
6. Select **Next**and fill out the following fields in the Networking tab:
    1. **Public network access**: Enabled
7. Select **Next** and fill out the following fields in the **Data protection**tab:
    1. **Enable soft delete for blobs**: Enabled
    2. **Enable soft delete for containers**: Enabled
8. Select **Next** and fill out the following fields in the **Encryption**tab:
    1. **Encryption type**: Microsoft-managed keys (MMK)
    2. **Enable support for customer-managed keys**: Blobs and files only
    3. **Enable infrastructure encryption**: Enabled
9. Select **Review + create**.
10. Select **Create**.

For more information, see [Create an Azure storage account](/en-us/azure/storage/common/storage-account-create).

### Step 4: Grant permission for the migration app to access the Azure Blob Storage account

1. Browse to the [Microsoft Azure portal](https://portal.azure.com).
2. Select **Storage accounts**.
3. Select the storage account you created.
4. In the navigation pane, select **Access Control (IAM)**.
5. In the toolbar, select **Add**.
6. Select **Add role assignment**.
7. Select the **Storage Blob Data Reader** role.
8. Select **Next**.
9. Make sure the **Assign access role to field** is set to **User, group, or service principal**.
10. Select **+ Select members**.
11. Search for and select the **Office 365 Mover** application.
12. Select **Select**.
13. Select **Next**.
14. Select **Review + assign**.

### Step 5: Create an Azure Blob Storage container

1. In the navigation pane, select **Storage browser**.
2. Select **Blob containers**.
3. Select **Add container**.
4. Enter a name for the storage container in the **Name** field.
5. Select **Create**.

### Step 6: Upload Slack export file to Azure Blob Storage container

![A screenshot showing the upload window for blob containers. The Upload blob window is imposed over the Storage browser pane, with Drag and drop files here or Browse for files as the two options.](media/migration-upload-blob.png)

1. In the navigation pane, select **Storage browser**.
2. Select **Blob containers**.
3. Select the name of the container you created.
4. Select **Upload**.
5. Select **Browse for files**.
6. Select the Slack export file and then select **Open**.
7. Select **Upload**.
8. Select the name of the newly uploaded file in the Azure Blob Storage container.
9. In the Overview tab, copy the **URL** property of this file to the clipboard.

### Step 7: Provide the Slack export file to the migration app

![A screenshot of the Get started window in the admin center.](media/get-started-migration.png)

1. Browse to the [Microsoft 365 admin center](https://admin.cloud.microsoft).
2. Select **Setup** in the navigation pane.
3. Select **Migration and imports**.
4. Select **Slack to Teams**.
5. If you didn't provide a Slack export file to the migration tool previously, select **Get started**.
6. In the **Export file URL in Azure Blob Storage** field, enter the URL of the Slack export file stored in the Azure Blob Storage container. (This URL is the URL that you previously copied to the clipboard.)
7. Select **Upload file**.
8. Select **Complete setup**.

Note

If you import a new package, only new tasks (channels) are detected. If existing channels contain new content in the new package, manually select the channel and perform a scan.

![A screenshot showing the layout of the side panel that allows you to upload the Slack export file to the Azure blob storage container.](media/provide-slack-export-file-for-import.png)

### Step 8: Select workspaces for scan and migration

Note

This step only applies if you provided a Slack export file that contains data from multiple workspaces. If your Slack export file only contains data from a single workspace, this step isn't part of your experience and you can skip to the next step.

Org Owners in a Slack Enterprise plan can export data from multiple workspaces into a single Slack export file. The Slack to Teams Migration Tool supports migrating data from multiple workspaces in parallel from such a file. When you select multiple workspaces, the channels from all of the selected workspaces are presented in the **Conversations** tab. You can later modify which workspaces are selected via the **Switch workspaces** button in the **Conversations** tab.

The migration tool can't operate on more than 50,000 channels at a time, so you can only select multiple workspaces when the total number of channels across the selected workspaces doesn't exceed that limit.

1. In the **Select workspaces for scan and migration** pane that appears, select one or more workspaces. Ensure the total number of channels across the workspaces doesn't exceed the 50,000 channel limit.
2. Select **Save**.

### Step 9: Scan Slack channels

1. In the **Conversations** tab, select one or more channels for the migration tool to scan by checking their checkbox.
2. Select **Scan messages** in the toolbar.
3. Wait for the **Channel scan status** to reach the **Completed** state for the channels in question.
4. Examine the other columns to review the results of the scan, including the total number of messages in the channel and the last message posted date. These results should help you decide which channels you want to migrate and estimate the length of the migration duration.

### Step 10: Select Slack channels for migration

![A screenshot of the Send to migration panel on the right-hand side of the Migration page in the admin center.](media/send-to-migration.png)

1. In the **Conversations** tab, select one or more channels for the migration tool to migrate by checking their checkbox.
2. Select **Send to migration**.
3. In the **Send to migration details**pane that appears, decide on the date range of messages to migrate for the selected channels.
    1. Select the **Send all messages to migration** radio button if you want all messages in the selected channels to be migrated
    2. Select the **Only send messages from the selected date range** radio button if you want a subset of messages in the selected channels to be migrated.

    - This radio button displays time in UTC.
    - The **Earliest message date** field specifies the earliest date of root messages to be migrated (starting at the beginning of the specified day).
    - The **Latest message** date field specifies the latest date of root messages to be migrated (ending at the end of the specified day).
    - Replies to root messages are automatically migrated when their root messages are migrated, even when those replies are outside of the specified message date range.
    - If replies are within the specified message date range, but their root message isn't, then the replies don't migrate.
    - For example, specifying January 20, 2025 as the earliest message date and January 21 as the latest message date results in two days-worth of root messages and all of their replies migrating.
4. Select **Send to migration** when you finish selecting which messages to migrate.

### Step 11: Map Slack identities to Microsoft 365 identities

All users in a Slack workspace must be mapped to Microsoft 365 users before starting the migration. This mapping includes deactivated users. Migration can't proceed until all Slack users are mapped to Microsoft 365 users.

For smaller migrations, you may prefer to use the web-based user interface (UI) of the migration tool to perform the user mapping. Slack users can be automatically mapped to Microsoft 365 users using the **Auto-map** option. This option automatically maps users when any of the following criteria are met:

1. The email address of a Microsoft 365 user matches the email address of the Slack user.
2. The username portion of the email address of a Microsoft 365 user matches the username portion of the email address of the Slack user.
3. The display name of a Microsoft 365 user matches the display name of the Slack user.

After the auto-map operation completes, you can manually map the identities of any remaining user that auto-map couldn't map. If there's no equivalent Microsoft 365 user for a Slack user, you can map the Slack user to the **Unknown user**.

For large-scale migrations with many users, you may find it easier to map users using a CSV file. The migration tool gives you the option to download a CSV template file, enter the mappings, and then upload the CSV file to the migration tool. If there's no equivalent Microsoft 365 user for a Slack user, you can map the Slack user to **unknown**.

If you wish to rerun the Auto-map operation, you must first select the **Clear Identities** button. This selection erases all mappings from Slack users to Microsoft 365 users in the migration tool. You can then select **Auto-map** to rerun the auto-map operation.

#### Map identities using the web-based UI

1. Select the **Migrations** tab.
2. Select **Map identities** in the toolbar.
3. Select **Auto-map** in the toolbar to discover all the Slack users in the Slack export package and automatically map their accounts to Microsoft 365 accounts with the same email address.
4. After the mapping process finishes, successfully mapped accounts have their **Mapping status** set to **Automatically set**. Accounts that still need to be mapped have their **Mapping status** set to **Mapping needed**.
5. Select the row for an account where mapping is still needed.
6. In the **Select a new user** mapping pane that appears, enter the name or email address of the Microsoft 365 account that this user should be mapped to in the **Equivalent Microsoft 365 user** field. Then select the desired Microsoft 365 account in the drop-down list. If there's no equivalent Microsoft 365 account, move your cursor focus on the **Equivalent Microsoft 365 user** field and select **Unknown user** in the drop-down list.
7. Select **Save**.
8. Repeat steps 5 to 7 until all accounts are mapped.
9. Select **Close**.

Note

You can return to this page and manually update the mapping of a user at any time. Select the row for an account, then update the mapping in the **Select a new user mapping** pane.

#### Map identities using a CSV file (for large-scale migrations with many users)

1. Select the **Migrations** tab.
2. Select **Map identities** in the toolbar.
3. Select **Auto-map** in the toolbar to discover all the Slack users in the Slack export package and automatically map their accounts to Microsoft 365 accounts with the same email address.
4. After the mapping process is finishes, successfully mapped accounts have their **Mapping status** set to **Automatically set**. Accounts that still need to be mapped have their **Mapping status** set to **Mapping needed**.
5. Select **Export Identities** and a CSV file containing the account mappings downloads.
6. Open the downloaded CSV file with a compatible app.
7. For each Slack account where the **Microsoft 365 Email ID (Enter unknown if user not present)** column is empty, enter the email address of the equivalent Microsoft 365 user. If there's no equivalent Microsoft 365 user, enter **unknown** so the Slack user maps to the **Unknown user**.

Note

You don't need to modify any other column to set the mapping.

1. Save your changes to the CSV file.
2. On the **Map identities** page, select **Import users**.
3. On the **Import users** pane, select **Select file**.
4. Select the CSV file with your saved changes and select **Open**.
5. Once the validation completes successfully with no issues found, select **Save**.

Note

You can manually update the mapping of a user at any time by reediting the CSV file and reimporting the updated CSV file. All previous mappings are overwritten with the mappings in the newly imported CSV file.

### Step 12: Map Slack channels to their destination

Each Slack channel you wish to migrate must be mapped to a destination team and channel within Teams. The migration tool can migrate Slack channels to existing teams created inside or outside of the migration tool, or to new teams created by the migration tool. However, it can only migrate to Teams channels created by the migration tool.

For smaller migrations, you may prefer to use the web-based UI of the migration tool to perform the destination mapping. For large-scale migrations with many channels, you may find it easier to map channels via a CSV file. The migration tool gives you the option to download a CSV template file, enter the mappings, and then upload the CSV file to the migration tool.

#### Map destinations using the web-based UI

![A screenshot of the Map destinations page in the admin center.](media/map-channel-to-destination.png)

1. Select the **Migrations** tab.
2. Select the checkbox of the Slack channel to be mapped.
3. Select **Map destinations** in the toolbar.
4. Select **Manually map to destination**.
5. In the **Microsoft Teams name** drop-down list, select **Create a new team** to create a new destination team. Otherwise, begin typing the name of an existing team, then select the team from the results in the drop-down list.
6. If you create a new team, enter the team name in the **Microsoft Teams team name** field and select whether the team should be public or private.
7. In the **Channel name** field, select **Create a new channel** to create a new destination channel for the selected team. Otherwise, select an existing channel.
8. If you create a new channel, enter the channel name in the **Channel name** field and select whether the channel should be shared, standard, or private. Then select **Add channel**.
9. Once you set the desired destination team and channel, select **Save changes**.

Note

You can manually update the mapping of a channel at any time before migration starts. Check the checkbox for a channel, select **Map destinations**, then select **Manually map to destination**.

#### Map destinations using a CSV file (for large-scale migrations)

1. Select the **Migrations** tab.
2. Select the checkboxes of the Slack channels to map. You can select multiple channels.
3. Select **Map destinations** in the toolbar.
4. Select **Upload destinations and map**.
5. On the **Upload destinations** pane, select the **Download template: MigrationDestination.csv** link and a CSV file containing the channel mappings of the selected channels downloads.
6. Open the downloaded CSV file with a compatible app.
7. For each Slack channel, enter the following information:
    1. In the **Teams team name** column, enter the name of the destination team.
    2. In the **TeamID** column, specify the GUID of the existing destination team, which can be retrieved via the [Get-Team](/en-us/powershell/module/microsoftteams/get-team) PowerShell cmdlet. If you're creating a new destination team, set the **TeamID** column to **New** (case-insensitive).
    3. In the **Teams team type** column, enter **Public** to make the team a public team or **Private** to make the team a private team.
    4. In the **Teams channel** name column, enter the name of the destination channel.
    5. In the Teams channel type column, enter **Shared** to make this channel a shared channel, **Standard** to make this channel a standard channel, or **Private** to make this channel a private channel.

Tip

Microsoft recommends setting the destination channel type to shared because shared channels provide the most flexibility. Standard or private channels can also be used, but aren't recommended.

Note

You don't need to modify any other column to set the mapping.

1. Save your changes to the CSV file.
2. In the **Upload destinations** pane, select **Browse**.
3. Select the CSV file with your saved changes and select **Open**.
4. Once the validation completes successfully with no issues found, select **Save**.

Note

You can manually update the mapping at any time by reediting the CSV file and reimporting the updated CSV file. Previous mappings are overwritten with the mappings in the newly imported CSV file.

Note

When the destination channel is configured as a shared channel, the migration tool automatically ensures that migrated channel members have the required access. As part of this process, the tool may add users to the destination team, if they are not already part of the Team, and share the channel with the parent team.

### Step 13: Start migration

Once you map all Slack user identities to Microsoft 365 users and map the Slack channels to their destination teams and channels, you're ready to perform the channel migrations.

1. Select the **Migrations** tab.
2. Check the checkbox of the Slack channels to migrate. You can select multiple channels.
3. Select **Migrate** in the toolbar.
4. The **Before you migrate** pane appears, confirming whether or not you successfully mapped all Slack user accounts to Microsoft 365 user accounts. the pane also confirms whether or not you granted consent for the Microsoft 365 Teams Migration app to import data into Teams. If any tasks aren't complete, complete these tasks before proceeding.
5. Select **Start migration**.

The channel migration tasks are queued in the migration tool and are performed at the earliest opportunity. The migration tool can migrate up to 20 channels in parallel. If the number of channels queued for migration exceeds this limit, the channels over the limit remain in the queue until existing channel migrations complete. The migration tool automatically picks up new channel migrations waiting in the queue as capacity becomes available, until the queue is empty. The migration tool typically migrates 2 - 3 messages per second for each channel.

You can monitor the progress of each channel migration by reviewing the **Channel Migration status** column of each channel in the Migrations tab. Its status resets to **Migrated** when the migration finishes.

![A screenshot showing a completed migration.](media/migration-complete.png)

## Incremental migration

The migration tool supports incremental migration to migrate content from a Slack channel to a Teams channel in multiple passes. For example, if it takes an extended amount of time to migrate content from a Slack channel to a Teams channel, your users may need to continue communicating in that Slack channel after the initial migration starts. You can use the incremental migration capability to migrate the content that was added to the Slack channel after the previous migration pass. The migration tool keeps track of its most recently migrated root message to avoid creating duplicate messages in the Teams channel as a result of multiple channel migration passes.

Note

Microsoft encourages performing a channel migration in a single pass where possible due to the increased complexity and limitations of incremental channel migration.

1. When selecting the date range of messages to migrate during the initial migration task creation step, you must specify either **Send all messages to migration** or specify a date range that includes not only messages in the current Slack export file but also potential future messages.
2. Once you complete a migration pass for the channel, you can provide a different Slack export file to the migration tool by going to the **Channels** tab and selecting **Specify export file** in the toolbar. The Slack export file you provide must be from the same Slack tenant and contain channel content for the channel you want to perform an additional channel migration pass on.
3. After providing the different Slack export file, go to the **Migrations** tab.
4. Check the checkbox of the channel migration task you previously ran and would like to perform an additional migration pass on.
5. Select **Migrate** in the toolbar.
6. The **Before you migrate** pane appears, confirming whether or not you successfully mapped all Slack user accounts to Microsoft 365 user accounts. the pane also confirms whether or not you granted consent for the Microsoft 365 Teams Migration app to import data into Teams. If any tasks aren't complete, complete these tasks before proceeding.
7. Select **Start migration** to perform the additional migration pass.

The migration task looks for the selected channel's content in the current Slack export file provided to the migration tool. If it finds content newer than the latest root message previously migrated by this migration task, while also being within the message date range specified for the migration task, it migrates that additional channel content to the same Teams channel.

Note

You must rerun the same channel migration task to perform an incremental migration of a previously migrated channel. You can't create a new channel migration task to perform an incremental migration.

## Post-migration steps

After you complete your migrations from Slack to Teams, there are optional post-migration actions you may wish to perform.

### Disconnect your Slack import project

The Slack to Teams Migration Tool creates an import project to keep track of:

- The Slack export file
- The Slack channels in the export file
- The Slack identities and their mapping to Microsoft 365 identities
- Migration jobs and their destination mappings

The import project is automatically created when you provide a Slack export file to the Slack to Teams Migration Tool. Once you complete all migrations from the Slack export file, you can disconnect the import project to reset the migration tool for any future Slack migrations to your Microsoft 365 tenant.

1. Browse to the [Microsoft 365 admin center](https://admin.cloud.microsoft).
2. Select **Setup** in the navigation pane.
3. Select **Migration and imports**.
4. Select **Slack to Teams**.
5. Select the **Complete disconnect from Slack Import** button at the top of the page (shaped like a power plug disconnected from a power socket).
6. In the **Delete data to complete disconnect** dialog, select **Delete**.

### Remove your Slack export file from Azure Blob Storage

Once you complete all migrations from a Slack export file, you no longer need to store that export file in an Azure Blob Storage container. You can delete that file and its container from Azure Blob Storage at your convenience. If you no longer need to store data in Azure Blob Storage, you can [cancel your Azure Blob Storage subscription](/en-us/azure/cost-management-billing/manage/cancel-azure-subscription) from the Azure portal.

### Revoke permissions from the M365 Teams Migration app

Once you complete all migrations from Slack to Teams, you can revoke the Microsoft Graph permissions from the "M365 Teams Migration" app that you previously granted through the admin consent experience. This revocation reduces the risk that the migration tool could be abused if a Microsoft 365 administrator account is compromised in the future. For more information, see [Review permissions granted to enterprise applications](/en-us/entra/identity/enterprise-apps/manage-application-permissions).

1. As a Global Administrator, browse to the [Microsoft Entra admin center](https://entra.microsoft.com).
2. Select **Enterprise apps** in the **Entra ID** section of the navigation pane.
3. Select **All applications** in the **Manage** section.
4. Select **M365 Teams Migration**.
5. Select **Permissions** in the **Security** section.
6. For each permission listed in the **Admin consent** tab, select the **"..."** context menu and then select **Revoke permission**. When prompted to confirm that you want to revoke the permission, select the **Yes, revoke** button.

You must reapply the revoked permissions if you wish to use the migration tool again, which you can do at any time by following the steps to grant consent.

## Scan and migration reports

The migration tool can generate reports for each channel scan and migration. The reports show detailed status information about the scan or migration, including details on any warnings or failures encountered during the scan or migration. Reports are in the CSV file format, with each row representing one conversation (channel).

The scan report is available only after the channel scan concludes for a given channel. Scan reports aren't available for a channel if its scan status is **Never run**, **Queued**, or **In Progress**.

The migration report is available only after the channel migration concludes for a given channel. Migration reports aren't available for a channel if its migration status is **Not started**, **Queued**, or **In Progress**.

### Review a channel scan report

1. Select the **Conversations** tab.
2. Check the checkboxes of the Slack channel scan you wish to review. You may select multiple channels.
3. Select **Generate report** in the toolbar.
4. Scan report generation begins. It may take time to process the scan events and generate the scan report.
5. When the scan report is ready, select the **Recent actions** button at the top of the page (shaped like a clock with an arrow circling it).
6. In the **Recent actions** pane, select the scan summary report link to download the file.
7. In the downloaded ZIP file, open the SlackScanSummary.csv file with a compatible app.

Here you can review the details of each conversation (channel) scan, including:

- Slack Conversation Name
- Slack Conversation Type
- Slack Conversation ID
- Slack Conversation Creator ID
- Creator Destination Identity
- Is Conversation Migratable
- Is Slack Connect Channel
- Is Archived
- Number of Members
- Items Scanned
- First Message Posted (UTC)
- Last Message Posted (UTC)
- Scan Status
- Scan Start (UTC)
- Scan End (UTC)
- Task ID
- Transaction ID
- Error Code
- Error Message

### Review a channel migration report

1. Select the **Migrations** tab.
2. Check the checkboxes of the Slack channel migrations you wish to review. You may select multiple channel migrations.
3. Select **Generate report** in the toolbar.
4. Migration report generation begins. It may take time to process the migration events and generate the migration report.
5. When the migration report is ready, select the **Recent actions** button at the top of the page (shaped like a clock with an arrow circling it).
6. In the **Recent actions** pane, select the migration summary report link to download the file.
7. In the downloaded ZIP file, open the SlackMigrationSummary.csv file with a compatible app.

Here you can review the details of each conversation (channel) migration, including:

- Slack Conversation Name
- Slack Conversation Type
- Slack Conversation ID
- Teams Team Name
- Teams Team Type
- Teams Conversation Name
- Teams Conversation Type
- Teams Web URL
- Team ID
- Channel ID
- Total Migrated Messages
- Task ID
- Transaction ID
- Transaction Start Time (UTC)
- Transaction End Time (UTC)
- Channel Migration Status
- Error Code
- Error Message
- Original Posting of Last Migrated Message (UTC)

## Supported Content

- Slack channels
    - Public
    - Private
- Channel ownership and membership
- Channel message metadata
    - Created by
    - Created date
- Channel message content and formatting
    - Block quote
    - Bold, italics, and strikethrough
    - Lists
        - Bulleted
        - Ordered
    - Code
    - Code blocks
    - Standard emojis
    - GIPHY
    - Images
    - Links
    - @-mentions
    - Standard reactions
    - Threading
- File attachments

## Known Limitations

1. Only one Slack tenant can be connected to the migration tool at a time. To migrate more Slack tenants, disconnect the migration tool from the current Slack tenant and then provide a Slack export file from the new tenant to the migration tool.
2. The migration tool currently only migrates Slack channel content. It doesn't migrate content outside of Slack channels such as:
    - Direct Messages (one-on-one chats)
    - Group chats and related content
    - Workflows
    - Custom app integration
3. The migration tool currently doesn't support migrating channel links (such as **#channel\_name**). Unsupported content may be marked with a flag such as **NOTMIGRATED** or **NOTSUPPORTED**.
4. The migration tool currently doesn't support Slack connect channels.
5. The migration tool currently doesn't support Slack archived channels. You can unarchive the Slack channel before performing the export to make it available for migration.
6. The migration tool currently doesn't support migrating (combining) multiple Slack channels into a single Teams channel. Each Slack channel must be migrated to its own independent Teams channel.
7. When you perform an incremental migration, the migration tool doesn't support migrating content older than previously migrated content. For example, it doesn't support migrating the most recent 90 days' messages in the initial pass, and then migrating content older than 90 days in an additional pass.
8. When you perform an incremental migration, the migration tool only migrates new root messages and their replies. If new replies are added to a root message that migrated previously, the new replies to that previously migrated root message don't migrate.
9. When you perform an incremental migration, the migration tool doesn't sync edits or deletions of previously migrated messages. It only migrates newly added messages from Slack to Teams.
10. The migration tool currently doesn't support custom emoji reactions.
11. If a file attachment's filename contains characters restricted by SharePoint, the migration tool replaces each restricted character with an underscore ("\_") character when migrating the file to Microsoft Teams.
12. Slack channel canvas pages migrate into Teams channels as HTML file attachments.
13. Slack channel lists migrate into Teams channels as JSON file attachments.
14. **Total Migrated Messages** counts may be different than the **Total Messages** count under certain circumstances. For example, Slack message thread replies that are also sent to the full channel are migrated to Teams as two separate messages. One migrated message is the thread reply while the other migrated message is a new root message in the channel.
15. The migration tool currently doesn't support migrating attachment system metadata:
    - Created at
    - Created by
    - Last edited at
    - Last edited by