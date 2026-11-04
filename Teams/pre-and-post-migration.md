---
layout: Conceptual
title: Best migration practices for app centric management - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/pre-and-post-migration
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal
ms.author: vikasalmal
manager: prkosh
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- m365initiative-voice
- M365-collaboration
- Tier1
search.appverid: MET150
ms.date: 2026-02-27T00:00:00.0000000Z
ms.reviewer: nguyenb
description: Learn about the best practices for migrating to app centric migration, which includes pre and post migration best practices.
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: a4fed804-ecc3-a09a-cacc-d248c3bcf8d2
document_version_independent_id: a4fed804-ecc3-a09a-cacc-d248c3bcf8d2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/pre-and-post-migration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: pre-and-post-migration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/pre-and-post-migration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 6ff18354-92e7-3dfb-efac-131ccb7af9c5
---

# Best migration practices for app centric management - Microsoft Teams | Microsoft Learn

App centric management simplifies the process of allowing apps for your users and groups. App centric management migration involves preserving the users and apps allowed in your app permission policies. You can also add or exclude users during the migration.

We recommend you follow these steps before and after the manual migration to check app centric management migration health.

Note

App centric management migration does not affect the graph permissions consented for the apps.

## Pre-migration

1. Export app catalog and note allowed apps
2. Review permission policies and note allowed or blocked apps
3. Identify users permitted for each app through permission policies

### Step 1: Export app catalog and note allowed apps

Navigate to **Manage Apps** page and export the full list of apps in the catalog as a CSV file, including each app’s allowed or blocked app status. The allowed or blocked status determines whether the app is available to everyone or no one, respectively. This status is used in the following steps to filter your users. For more details, see [export app catalog as CSV](manage-apps#export-agent-and-app-catalog-as-csv).

[![Screenshot showing  export App catalog and note your allowed apps.](media/step1-export-app-catalog.png)](media/step1-export-app-catalog.png#lightbox)

### Step 2: Review permission policies and note allowed or blocked apps

If you have multiple permission policies, follow these steps to get the permission policies list:

1. Go to **Teams admin center** &gt; **Manage apps** &gt; **Permission policies**.
2. Open each permission policy and note which apps are allowed or blocked.

Steps to get the permission policies list using PowerShell commands:

1. Run the PowerShell command: `Get-CsTeamsAppPermissionPolicy`.

    The following result is displayed:

    [![Screenshot showing interpreting results.](media/step2-interpret-results.png)](media/step2-interpret-results.png#lightbox)

#### Retrieve allowed apps in each permission policy

You can retrieve allowed apps in each permission policy using PowerShell commands. But not all default apps are displayed in the response. To view the complete list, assign the result to a variable.

For example: `$msftApps = Get-CsTeamsAppPermissionPolicy -Identity "Global" | Select-Object -ExpandProperty DefaultCatalogApps $msftApps.id`

#### Filter out blocked apps

1. After collecting information on all apps permitted within the tenant, identify the users or groups authorized to use each app.
2. Merge this data with the export from the Manage Apps page.

Note

Any app marked as blocked in Manage Apps will remain blocked, regardless of the policy assignment results.

### Step 3: Identify users permitted for each app

You can identify users permitted for each app in the following ways:

- Teams admin center
- PowerShell

#### Get a list of users assigned to a policy in UI

1. Go to [Teams admin center](https://admin.teams.microsoft.com/).
2. Go to **Users** &gt; **Manage users**.

    [![Screenshot showing manage users page.](media/step3-manage-users-page.png)](media/step3-manage-users-page.png#lightbox)
3. Select the filter located at the top right of the Manage users table.

    [![Screenshot showing manage users page filter.](media/step3-manage-users-page-filter.png)](media/step3-manage-users-page-filter.png#lightbox)
4. Select the policy name for which you need the user assignments and click **Apply**.

    [![Screenshot showing manage users page applied page.](media/step3-manage-users-page-filter-applied.png)](media/step3-manage-users-page-filter-applied.png#lightbox)

    All the users assigned to the policy filtered are displayed.

    [![Screenshot showing manage users page filter results.](media/step3-manage-users-page-filter-result.png)](media/step3-manage-users-page-filter-result.png#lightbox)

    You can also export the users list to CSV.

    [![Screenshot showing export manage users page csv.](media/step3-manage-users-page-export-csv.png)](media/step3-manage-users-page-export-csv.png#lightbox)

#### Identify users allowed for each app in PowerShell

You can also use the following PowerShell command to export user assignments for each custom policy. This script generates an Excel file if the given policy has user assignments; otherwise, a message is shown indicating that no user assignments exist.

PowerShell command output is as follows:

[![PowerShell command output.](media/step3b-pscommand-output.png)](media/step3b-pscommand-output.png#lightbox)

The exported file appears as follows:

[![Exported file output.](media/step3b-exported-file.png)](media/step3b-exported-file.png#lightbox)

- To define the base path for exports: `$basePath = "C:\Users\<user name>\Downloads"`
- To ensure the base path exists: if (-not (Test-Path -Path $basePath)) { New-Item -ItemType Directory -Path $basePath | Out-Null }
- To retrieve all Teams app permission policies: `$policies = Get-CsTeamsAppPermissionPolicy | Select-Object Identity`
- To loop through each policy: `foreach ($policy in $policies) { $policyName = $policy.Identity #Ignore 'Global' policy if ($policyName -eq 'Global') { continue }`
- To remove 'TAG:' prefix if it exists:

    `if ($policyName -like 'TAG:*') {  $policyName = $policyName -replace '^TAG:', '' }`
- To retrieve the users assigned to the current policy: `$users = Get-CsOnlineUser -Filter "TeamsAppPermissionPolicy -eq '$policyName' -and SoftDeletionTimestamp -eq `$null" | Select-Object Identity, DisplayName, UserPrincipalName, TeamsAppPermissionPolicy, AccountEnabled, AccountType`
- To check if the users count is zero: `if ($users.Count -eq 0) { Write-Host "`e[31m$policyName does not have any user assignments`e[0m" continue }`
- To export users to a CSV file: `$outputPath = "$basePath\users_$($policyName).csv" $users | Export-Csv -Path $outputPath -NoTypeInformation` Write-Host "`e[32mExported users for policy: $policyName to $outputPath`e[0m" }

## Post migration

After migration customers can validate against the pre-migration posture using the same steps. Follow the instructions defined in this section to gather your previous permission policies and compare them to your app centric management settings. Review your permission policies and note your allowed/blocked apps.

## Bulk app management

1. **Create distribution lists and add members**: You can use the `New-DistributionGroup` and `Add-DistributionGroupMember` PowerShell commands to create distribution lists and add members.

    For example: `New-DistributionGroup -Name "DTDEAUG_MSTeamsAppPolicy_M365TeamsAdmins" -PrimarySmtpAddress "DTDEAUG_MSTeamsAppPolicy_M365TeamsAdmins@man-es.com"``Add-DistributionGroupMember -Identity "DTDEAUG_MSTeamsAppPolicy_M365TeamsAdmins" -Member "user1@man-es.com"`
2. **Assign all apps to a distribution list**: To assign all apps to the distribution list DTDEAUG\_MSTeamsAppPolicy\_M365TeamsAdmins@man-es.com, you can use the `Update-M365TeamsApp` PowerShell command. Here is an example to assign all apps together:

    `$apps = Get-AllM365TeamsApps foreach ($app in $apps) { Update-M365TeamsApp -Id $app.Id -AppAssignmentType UsersAndGroups -Groups "DTDEAUG_MSTeamsAppPolicy_M365TeamsAdmins@man-es.com" }`
3. **Modify availability of specific apps to everyone**: To modify the availability of specific apps to everyone, you can use the `Update-M365TeamsApp` PowerShell command with the `AppAssignmentType` parameter set to `Everyone`.

    For example: `$appIds = @("appId1", "appId2", "appId3", ...) # List of 53 app IDs foreach ($appId in $appIds) { Update-M365TeamsApp -Id $appId -AppAssignmentType Everyone }`
4. **Allow Microsoft apps to multiple distribution lists**: To allow all Microsoft apps to the distribution lists DTDEAUG\_MSTeamsAppPolicy\_ITTestMSPVA@man-es.com and DTDEAUG\_MSTeamsAppPolicy\_M365TeamsAdmins@man-es.com, you can use the `Update-M365TeamsApp` command.

    For example: `$msApps = Get-AllM365TeamsApps | Where-Object { $_.Publisher -eq "Microsoft" } foreach ($app in $msApps) { Update-M365TeamsApp -Id $app.Id -AppAssignmentType UsersAndGroups -Groups "DTDEAUG_MSTeamsAppPolicy_ITTestMSPVA@man-es.com","DTDEAUG_MSTeamsAppPolicy_M365TeamsAdmins@man-es.com" }`

    Here's an example of the `list.csv` file: `AppId,DistributionList appId1,DTDEAUG_MSTeamsAppPolicy_Group1@man-es.com appId2,DTDEAUG_MSTeamsAppPolicy_Group2@man-es.com appId3,DTDEAUG_MSTeamsAppPolicy_Group3@man-es.com` ...

The following PowerShell script can be used to read the CSV file and assign the applications to the specified distribution lists: `$csv = Import-Csv -Path "C:\path\to\list.csv" foreach ($row in $csv) { Update-M365TeamsApp -Id $row.AppId -AppAssignmentType UsersAndGroups -Groups $row.DistributionList }` This PowerShell script loops through each row in the CSV file and assign the applications to the corresponding distribution lists.

The following is another example:

1. Made required changes to Teams Admin Center Configuration Updates.
2. Applied all available apps to Teams Admin Distribution Group for smooth management.

    The following PowerShell command is used: `Import-Csv .\AppList1.csv | %{Update-M365TeamsApp -Id $_.AppId  -AppAssignmentType UsersAndGroups -Groups $_.GroupID -OperationType Add}`
3. Assigned all Microsoft apps to a designated custom policy group to keep all Microsoft apps organized and managed under a specific policy for targeted user group. The following PowerShell command is used: `Import-Csv .\AppList2.csv | %{Update-M365TeamsApp -Id $_.AppId  -AppAssignmentType UsersAndGroups -Groups $_.GroupID -OperationType Add}`
4. Mapped specific apps to their respective custom policy groups for making access control more effective. The following PowerShell command is used: `Import-Csv .\AppList3.csv | %{Update-M365TeamsApp -Id $_.AppId  -AppAssignmentType UsersAndGroups -Groups $_.GroupID -OperationType Add}`
5. Update **Global Policy** to make selected apps accessible to all users across the organization. The following PowerShell command is used: `gc '.\GlobalApps.txt' | %{Update-M365TeamsApp -Id $_ -AppAssignmentType Everyone}`