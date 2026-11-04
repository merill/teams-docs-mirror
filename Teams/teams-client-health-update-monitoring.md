---
layout: Conceptual
title: Update monitoring in the Teams admin center - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-health-update-monitoring
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.topic: article
ms.date: 2025-02-26T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: shals
search.appverid: MET150
f1.keywords:
- NOCSH
description: Monitoring for updates for the Teams client using the Teams admin center.
ms.localizationpriority: medium
locale: en-us
document_id: 702849c2-e4bf-2587-4488-7fdbffc5b562
document_version_independent_id: 702849c2-e4bf-2587-4488-7fdbffc5b562
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-health-update-monitoring.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-health-update-monitoring
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-health-update-monitoring.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 16a6798a-34f9-4cf3-a86d-1ce2f9700ef8
---

# Update monitoring in the Teams admin center - Microsoft Teams | Microsoft Learn

Important

This article describes a Microsoft Teams feature that hasn't yet been released. It's been announced, and it's coming soon. If you're an admin, you can find out when this feature will be released in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)). For more information, see [Teams client health](https://www.microsoft.com/microsoft-365/roadmap?filters=&amp;searchterms=478610) and [Monitor Teams client updates](https://www.microsoft.com/microsoft-365/roadmap?filters=&amp;searchterms=478609).

As an admin, it’s important that your users have the latest and the most secure version of the Teams client. Teams update monitoring in the Teams admin center allows you to proactively monitor Teams client updates and versions. It also helps identify users who aren't on latest version of Teams, so you can support them.

This dashboard highlights the client update status for the devices in your tenant and gives Microsoft recommended insights for moving users to the latest version of Teams client.

## Access the Teams update dashboard

To access the update monitoring and insights dashboard:

1. Go to the Teams admin center and login with your Admin credentials.
2. Select **Teams client health** from the navigation pane on the left-hand side of the window.

![A screenshot of the Teams client health page with callouts marked. The first callout is over the page title. The second callout is on the upper middle of a table showing details. The number three is to the upper right of this table next to search, settings, and export options.](media/teams-client-health-main-page-alt.png)

| Callout number | Details |
| --- | --- |
| Callout 1 | The Client update widget displays the overall version status distribution for all devices in your tenant. The update status widget provides statuses by three categories:- Latest Build: A device is running a Teams client build newer than the last 100% released build.- One or more builds behind: A device is running a Teams client build less than 30 days old and older than the last stable build.- Outdated: A device is running a Teams client build more than 30 days old. |
| Callout 2 | The table under the **Health tab** shows a more detailed breakdown of this information, such as:- Client versions: The exact client version number.- Release Date: The date this specific client version was fully released to the general ring.- Version status: The Teams client version status.- Platform: The platform for the client version.- Devices on this version: The total devices in the tenant currently running this client version.- Users on this version: The total number of users in the tenant currently running this client version.- Percentage of total users: The percentage of total users in the tenant currently running the client version.- Device Crashes: The total number of devices that experienced a client crash in the last 28 days.- Device launch failures: The total number of devices that experienced a client launch failure in the last 28 days. |
| Callout 3 | You can use these buttons to:- Export the table to a CSV file.- Filter and search by versions.- Manage settings for columns in the table. |

### Client version details

You can see your organization's client version distribution and adoption of each client version and the health of each client version in your organization. To view a detailed dashboard with insights, select any version from the health table from a row in this table.

You can identify users and devices running outdated version of Teams, and review troubleshooting insights on issues preventing users from updating to a newer version of Teams.

![A screenshot of the version details page, with callouts. The first callout, on the top left-hand side, is the client version. The second callout, underneath the first, is the date of release. The third callout, to the immediate right of the second, is the Teams client version. The fourth callout, in the middle underneath the third, has charts showing trends. The fifth, center of the screenshot, shows a table with details. The sixth, to the middle right, shows search, settings, and export options.](media/teams-client-version-details-page.png)

| Callout number | Details |
| --- | --- |
| Callout 1 | Client versions - The exact client version number. |
| Callout 2 | Release Date - The date this specific client version was fully released to the general ring. |
| Callout 3 | Version status - The Teams client version status. |
| Callout 4 | - Devices on this version trend: The trend of devices adopting this client version the last 28 days.- Device crashes trend: The trend of devices experiencing client crashes on this version in the last 28 days.- Device launch failure trend: The trend of devices experiencing client launch failures on this version in the last 28 days. |
| Callout 5 | Callout 5: The table provides the following data:- User: The username.- Ring: The ring that the user is currently using.- Device: The device name.- Platform: The platform the user is running Teams client on.- Platform details: Operating system details.- Insight: If the user experienced an update failure and is running an outdated version of Teams.- Last Activity: The timestamp of the last active update. |
| Callout 6 | You can search or filter for any client versions. You can also sort and export the dashboard's table in a CSV file. |

## Client health per user

You can also monitor Client health per user from the user’s page.

1. Go to **Teams** &gt; **Users** &gt; **Manage users** page.
2. Select any user account.
3. Select the **Client health** tab.

![A screenshot of the per-user view, with numbered callouts. The first callout is slightly to the right of the middle of the screenshot, over the Client health tab. The second callout is directly underneath the first, above a table. The third is on the middle right of the screenshot, above the search, settings, and export options.](media/teams-client-per-user-view.png)

| Callout number | Details |
| --- | --- |
| Callout 1 | The Client health tab, which provides key health and update information for all clients used by the user. |
| Callout 2 | The table shows the following information:- Client versions: The exact client version number.- Release Date: The date on which this specific client version was fully released to the general ring.- Version status: The client version status of the Teams client.- Devices: The device name that the user is currently running this Teams client on.- Device Crashes: The number of total crashes experienced by this client version on the user’s specific device in the last seven days.- Device launch failures: Total launch failures experienced by this client version on the user's specific device in the last seven days. |
| Callout 3 | You can search or filter for any client versions. You can also sort and export the dashboard's table in a CSV file. |