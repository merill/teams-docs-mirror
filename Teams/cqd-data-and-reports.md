---
layout: Conceptual
title: Data and reports in Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cqd-data-and-reports
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: jamp, siunies, mikedav, gageames
ms.date: 2026-06-16T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Learn about the data and reports available in Microsoft Call Quality Dashboard (CQD).
locale: en-us
document_id: 718b597f-258b-3d61-17b8-1d41c8436d07
document_version_independent_id: 78f3333e-36cd-384a-8b5b-29bae7e1ed88
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/cqd-data-and-reports.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cqd-data-and-reports
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/cqd-data-and-reports.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/2d774b87-7dcb-40bf-a0b9-5a7a9efff0d1
- https://authoring-docs-microsoft.poolparty.biz/devrel/d3197845-b4ce-44c6-a237-cd4be160e76c
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/89dc5f37-0e4e-4b05-ad87-5fcd2b941a8a
- https://authoring-docs-microsoft.poolparty.biz/devrel/aea905fb-0a9d-4d46-b30f-e9cbaf772d1b
platformId: 2aefbe0e-f687-254c-b815-74a2eb1f9912
---

# Data and reports in Call Quality Dashboard (CQD) - Microsoft Teams | Microsoft Learn

Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed. Call records are typically available in CQD within 30 minutes of the end of a call and remain in CQD for 12 months, except for end user identifiable information (EUII) fields, which are removed after 28 days. In rare cases, some calls may take longer than 30 minutes to appear in CQD.

## Many ways to access call quality data

You can access call quality data by several different avenues. Pick the one that best meets your needs:

| Resource | Description |
| --- | --- |
| CQD in Power BI | Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](cqd-power-bi-query-templates) and the CQD Quality of Experience Report (QER). The CQD Power BI templates are regularly updated to support new Teams features, calling scenarios, and the latest telemetry we have available in CQD. |
| Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com) | Call quality data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format. You can't customize the data that you find under **Users**. |
| CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com) | Robust summary and detailed reports that meet most needs, with drill-through filtering. You can also create customized reports in the CQD portal. |
| Graph API | Access raw call quality data yourself using the [Graph API](/en-us/graph/api/resources/callrecords-api-overview). Using Graph API is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data. For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data. CallRecords Graph API might not contain all of the fields that are available in CQD and naming conventions might differ between the two products. |

## EUII data

Caution

As of late-March 2025, permissions for location sharing in Microsoft Teams changed. Users must now consent to sharing their location with Microsoft Teams using individual toggles for the purposes of **Emergency calls** and **Insights for IT admins**. If users in your tenant deny sharing their location except for emergencies, CQD can't provide admins with the BSSID of the client endpoint. Quality and reliability troubleshooting tasks that rely on BSSID—such as deep analysis of issues involving wireless networks—will become more difficult and potentially less accurate as fewer clients will report them.

On fully managed devices, the operating system controls location sharing. It turns location sharing on by default and allows users to turn it off only through the system’s location setting. On non-fully managed devices, Teams users must choose between **Allow all** and **Keep emergency only**. In the Teams client, this setting can be changed by your users in **Settings** &gt; **Privacy** &gt; **Location** &gt; **Insights for IT admins**.

For compliance reasons, EUII data (also known as personally-identifiable information or PII) is only kept for 28 days. As CQD's data crosses the 28-day mark, fields that contain EUII are cleared, resulting in EUII-free data. Fields that contain EUII data are:

- IP Address
- User ObjectId
- MAC Address
- Sip Uri (Skype for Business only)
- Phone Number
- UPN
- Feedback Text
- Client Endpoint Name
- Local Address
- Remote Address
- Base Address
- BSSID
- Local Site
- Remote Site
- Auto Attendant Identity
- Call Queue Identity
- Transferred from Call Queue Identity
- Organizer ObjectId
- Organizer UPN
- Organizer Sip Uri (Skype for Business only)
- VTC Device Name
- VTC Device Detail

### Admin roles with and without EUII access

These [RBAC](/en-us/azure/role-based-access-control/overview) roles **DO** have EUII access:

- Teams Service Admin
- Teams Communications Admin
- Teams Communications Support Engineer
- Skype for Business Admin
- Global Reader
- Global Admin

Important

Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role. To learn more, see [About Admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles).

These RBAC roles **DON'T** have EUII access:

- Reports Reader
- Teams Communications Support Specialist

Note

Users assigned to one or more [Administrative Units](/en-us/azure/active-directory/roles/administrative-units) won't see end-user identifying information (EUII) even if their role would ordinarily allow it.

## Date controls

CQD supports the following Rolling Trend types:

- 5-day
- 7-day
- 30-day
- 60-day
- 90-day

The URL Date parameter accepts a Day field. Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend. The URL Date parameter "00" indicates "today."

| URL | End date of Rolling Day Trend |
| --- | --- |
| https://&lt;cqdv3&gt;/spd/#/Dashboard/&lt;reportid&gt;/2019-02/ | Current Day of Feb 2019 |
| https://&lt;cqdv3&gt;/spd/#/Dashboard/&lt;reportid&gt;/2019-02-15/ | Feb 15, 2019 |
| https://&lt;cqdv3&gt;/spd/#/Dashboard/&lt;reportid&gt;/00/ | Current Day |

By default, the current day of the month is used as the last day of the Rolling Day Trend.

## Data available in CQD reports

The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can create custom reports.

If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](cqd-power-bi-query-templates).

| Feature | Summary Reports | Detailed Reports |
| --- | --- | --- |
| Application sharing metric | No | Yes |
| Customer building information support | Yes | Yes |
| Customer endpoint information support | Only in cqd.teams.cloud.microsoft | Only in cqd.teams.cloud.microsoft |
| Drill down analysis support | No | Yes |
| Media reliability metrics | No | Yes |
| Out-of-the-box reports | Yes | Yes |
| Overview reports | Yes | Yes |
| Per-user report set | No | Yes |
| Report set customization (add, delete, modify reports) | No | Yes |
| Video-based screen sharing metrics | No | Yes |
| Video metrics | No | Yes |
| Amount of data available | Last 12 months | Last 12 months |
| Microsoft Teams data | Yes | Yes |

## Summary Reports

These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD. They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.

| Tab | Description |
| --- | --- |
| Overall Call Quality | Aggregate of the other three tabs. |
| Server—Client | Details of the streams between server and client endpoints. |
| Client—Client | Details of the streams between two client endpoints. |
| Voice Quality SLA | Info about calls included in the Skype for Business voice quality [SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services). |

### Overall Call Quality tab

Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages. The legend in the upper-right corner shows which color and visual elements represent these metrics.

![Screenshot that shows the Call Quality tab.](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)

Streams are classified in three groups: Good, Poor, and Unclassified. There are also calculated *Poor %* values that give you the ratio of streams classified as *Poor* to the total classified stream count. Since *Poor % = Poor streams/(Poor streams+ Good streams) \* 100*, the *Poor %* is unaffected by the presence of multiple *Unclassified* streams. To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard).

Note

Default reports in CQD Portal currently classify media streams as Good or Poor as defined in [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard). However, Teams call reporting is transitioning to use the newer [Intelligent Media Quality Classifiers](cqd-intelligent-media-quality-classifiers). During this transition period, you may find differences in quality classification depending on which classification system is used.

Use the scale on the left to measure the stream count values.

![Screenshot: shows stream count values.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)

Use the scale on the right to measure the Poor % values.

![Screenshot: shows poor % values.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)

You can also obtain the actual numerical values by hovering the mouse over a bar.

Note

The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.

![Screenshot: shows mouse used to access data.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)

The overall stream volume helps determine how relevant the calculated Poor percentages are. The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.

### Server-Client tab and Client-Client tabs

These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios. The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.

- Wired Inside
- Wired Outside
- WiFi Inside
- WiFi Outside

Similarly, the Client-Client tab has five collapsible sections:

- Wired Inside — Wired Inside
- Wired Inside — Wired Outside
- Wired Outside — Wired Outside
- Wired Inside — WiFi Inside
- Wired Inside — WiFi Outside

#### Inside versus Outside

CQD classifies a stream as *Inside* or *Outside* using Building information, if it exists. Endpoints of each stream are associated with a subnet address. If the subnet appears in the list of subnets marked InsideCorp in the uploaded building information, it's considered *Inside*. If building information isn’t uploaded, Inside Test always classifies the streams as *Outside*.

The Inside Test for a Server-Client scenario only considers the client endpoint. Because servers are always outside from a user's perspective, this isn't accounted for in the test.

#### Wired versus WiFi

As the names indicate, the classification criteria is based on the type of client connections. Server is always wired and it isn't included in the calculation. In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.

Note

Given a stream, if one of the two endpoints connects to a WiFi network, CQD classifies it as WiFi.

## Tenant Data information

The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner. This page is used for admins to upload their own information, such as:

- A map of IP address and geographical information.
- A map of Endpoint to Endpoint Make/Model/Type, etc.

We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports. If you haven't already uploaded this data, read [Upload tenant and building data](cqd-upload-tenant-building-data).

## Detailed reports

| Name | Description |
| --- | --- |
| Location-Enhanced Reports | Shows quality trends based on location information. This report appears only if you've [uploaded your tenant data](cqd-upload-tenant-building-data). |
| Reliability Reports | Includes audio, video, video-based screen sharing (VBSS), and app sharing reports. |
| Quality of Experience Reports | Audio quality and reliability for all clients and devices, including meeting rooms. These reports are a "slimmed-down" version of the downloadable [Power BI templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability. |
| Quality Drill Down Reports | Drill downs: Date by region, locations, subnets, hour, and users. |
| Failure Drill Down Reports | Drill downs: Date by region, locations, subnets, hour, and users. |
| Rate My Call Reports | Analyze user call ratings by region, location, or by user. Includes verbatim feedback. |
| Help Desk Reports | Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone. Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware. |
| Client Version Reports | Client Version Summary: View the Sessions and Users counts for each client app versionClient Version by User: View user names for each client app version Prebuilt filters for Product and Client Type help focus the versions to specific clients. |
| Endpoint Reports | Shows call quality by machine endpoints (computer make and model). These reports include building data, if you've uploaded it. |

## Create custom detailed reports

If the default CQD reports don't meet your needs, you can create your own custom charts and reports.

From the pull-down list of reports at the top of the screen, select **Detailed Reports**.

Note

The user interface for custom reports will be changing over the coming months. As the change rolls out, you can select "Return to Classic Portal" from the top menu if you'd prefer to use the previous user interface. This option will be removed once the change is fully rolled out.

### Create a new report

To create a new report, select **New Report** to open the Query Editor. Each report is backed by a query that returns any of the [dimensions and measures](dimensions-and-measures-available-in-call-quality-dashboard) available in CQD. A report is a visualization of the data returned by its query. The Report Editor helps you edit these queries and the display options of the report. When you open the Report Editor, you see:

![Screenshot: shows the CQD custom report query editor.](media/cqd-query-editor.png)

### Add data to your report

Dimensions, measures, and filters are chosen in the left pane of the query editor. Click on the search bar under each category to see the full list of available fields, which you can filter by typing in the field name. Click the check box for your desired field to add it to the report. A well-formed report should have at least one dimension, measurement, and filter. Depending on the size of your organization, you may need to add additional filters or remove dimensions to reduce the amount of data returned.

Once a field is added to your report, you can customize the field name and order in which it appears in the report. Click the field name again to close the field options.

When adding measurements, you can configure a number of visualization options such as the chart type, color, axis position, and whether values are stacked.

As you add fields to your report, the preview will issue new queries to reflect your changes. If desired, this can be disabled by choosing "Off" under the Auto Update option.

### Customize your report

Options for chart customization are displayed at the top of the editor. For example, you can choose between a chart or a table of results, as well as customize the height and width of the report. You can also select "Show Sparkline" to embed a small trend within a table of results. The report name and description can be modified in the fields at the top of the editor.

Once your report is complete, select "Save."

### Organize your reports

Reports are stored in a hierarchy, starting with the top-level default report. If you would like to add additional views under an existing report, select the menu in the top-right corner of a report and choose "Add Sub Report." You can also use this menu to edit, clone, delete, or download an existing report. Once a sub report is created, you can click on the main report title to view its sub reports.

The hierarchy of reports is displayed at the top of the page and can be used to navigate back to the top-level report at any time.

### Sharing your reports

CQD custom report definitions can be exported from the report menu as a .cqdx file, which can be shared with other CQD users. These files can be imported from the top menu by choosing "Import Report."

You can also use the menu on the chart axis to view and export the chart data in a number of formats, such as JPG, PNG, SVG, and PDF, as well as download the data in CSV or Excel formats.

### Users dashboard

Select the Users Dashboard on the left menu to view a list of all users who have reports in CQD. Click on a user to view their reports. However, only a report owner can edit or delete an existing report.

## Query filters

Query filters are implemented by using the Query Editor in CQD. These filters are used to reduce the number of records returned by CQD, thus minimizing the report's overall size and query times. Query filters are especially useful for filtering out unmanaged networks. The filters listed in the following table use regular expressions (RegEx).

| Filter | Description | CQD query filter example |
| --- | --- | --- |
| No blank values | Some filters don't have the option to filter for blank values. To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs. | Second Building Name &lt;&gt; ^\s\*$ |
| Exclude common subnets | Without a valid building file to separate managed from unmanaged networks, home networks are included in the reports. These home subnets are outside the scope of IT's control and can be quickly excluded from a report. Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0. | Second Subnet &lt;&gt; 10.0.0.0 |192.168.0.0 |192.168.1.0 |
| View inside only | Used to filter a report for managed (inside) or unmanaged (outside). The managed CQD template is already preconfigured with these filters. | Second Inside Corp = Inside |

## Report filters

Use CQD report filters to narrow the focus of your investigations. Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.

| Filter | Description | CQD report filter example |
| --- | --- | --- |
| Month | Start with the year first, then month. | 2017-10 |
| Alphabetic | Filters for any alphabetic characters. | [a-z] |
| Numeric | Filters for any numeric characters. | [0-9] |
| Percentage | Filters for a percentage. | ([3-9]\.)|([3-9])|([1-9][0-9]) |

### Drill-down filters

CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations. If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value. If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.

![Diagram illustrating drill-down report flow.](media/qerguide-image-drillthrureportflow.png)

### Multi-select filters

In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).

In order to select multiple filter values, begin by adding a new filter to the report. Select **+** beside the **Filters** label, enter the name of the Dimension you want to use, and select **Add**.

![Screenshot of adding a multi-select filter.](media/cqd-multi-select-filters.png)

Then, select **Search** (a magnifying glass icon next to the new filter). CQD displays a text field and a number of options, including **Select All** and **Invert**. Enter a value, and select **Search** next to that field to search. Alternatively, leave the text field empty and select **Search** to view up to the first 100 options.

```URL
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Example:

![Screenshot of adding a query filter.](media/cqd-multi-select-filters-2.png)

### Dashboard level filters

Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters. These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.

![Screenshot of a dashboard filter.](media/cqd-dashboard-level-filters.png)

```URL
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### URL filters

CQD supports adding filters to the URL. These URL filters make it easy to share or bookmark a CQD query. You can define parameters in the URL, such as Trending Month, tenant ID, or language. You can also add Product or Dashboard level filters to the URL. Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.

To add a filter, append the following to the end of the URL:

```URL
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Example:

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter. Add these filters to the URL after the Trending Month and before the URL parameters:

`filter/DATA_MODEL_NAME|VALUE`

For example, to apply a Product filter value of Microsoft Teams, you'd add the following information:

`filter/[AllStreams].[Is%20Teams]|[True]`

Your entire URL would look something like this:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

To apply URL filters with multi-select values, separate each value with a pipe ( | ) character. For example:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

If you specify an invalid name or value, the URL filter isn't applied.

You can use a URL filter to filter every report for a specific dimension. The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business. Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.

| Filter | Description | CQD query filter example |
| --- | --- | --- |
| No blank values | Some filters have no option to filter for blank values. To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs. | Second Building Name &lt;&gt; ^\s\*$ |
| Exclude common subnets | Without a valid building file to separate managed from unmanaged networks, home networks are included in the reports. These home subnets are outside the scope of IT's control and can be quickly excluded from a report. Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0. | Second Subnet &lt;&gt; 10.0.0.0 |192.168.0.0 |192.168.1.0 |
| View inside only | Used to filter a report for managed (inside) or unmanaged (outside). | Second Inside Corp = Inside |

#### How to find your tenant ID

The tenant ID in CQD corresponds to the Directory ID in Azure. If you don't know your Directory ID, you can find it in the Azure portal:

1. Sign in to the Microsoft Azure portal: https://portal.azure.com
2. Select **Microsoft Entra ID**.
3. Under **Manage**, select **Properties**. Your tenant ID is in the **Directory ID** box.

You can also find your tenant ID by using PowerShell:

```powershell
Login-AzureRmAccount
```

## Comparing Teams and Skype for Business CQD data

When reviewing your data, you may see differences in data between Teams and Skype for Business. Some reasons:

- Differences in the mechanisms for ensuring performance and reliability:
    - Teams has auto-reconnect and fast roaming. Skype for Business doesn't.
    - Teams has dynamic bandwidth management. Skype for Business doesn't.
- Differences in [IP address ranges](office-365-urls-ip-address-ranges) between Teams and Skype for Business. The Teams IP ranges are newer, which could cause connectivity problems at the firewall.