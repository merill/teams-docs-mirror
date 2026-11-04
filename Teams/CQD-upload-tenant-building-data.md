---
layout: Conceptual
title: Upload building and endpoint data - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cqd-upload-tenant-building-data
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: mikedav, siunies, gageames, jamp
ms.date: 2026-07-01T00:00:00.0000000Z
ms.topic: how-to
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Learn how to upload building and endpoint data in Teams admin center.
locale: en-us
document_id: 200d8054-efa7-bdd3-8b13-d7d73924ecbd
document_version_independent_id: 9972bece-abf2-8f48-ba07-b8a6097602e6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/CQD-upload-tenant-building-data.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cqd-upload-tenant-building-data
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/CQD-upload-tenant-building-data.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 0fd44ded-fbb9-7c90-8862-2c20263bd514
---

# Upload building and endpoint data - Microsoft Teams | Microsoft Learn

To get the most out of Call Quality Dashboard (CQD) and other call reporting tools, we recommend that you upload your building and endpoint data. You can use building files to customize Teams call reports with information unique to your managed networks, such as network names and physical location details. You can use endpoint files to provide information on your managed device fleet like make, model, and asset tags.

## Access building and endpoint data page

To access the building and endpoint data page, follow these steps:

1. Go to the Teams admin center.
2. Select **Analytics & reports &gt; Building and endpoint data** from the navigation pane.
3. From this page, you can upload new files and see a list of uploaded files. You can also select any uploaded file from the list to download it, delete it, or edit its effective time period.

![Image of the building and endpoint data page in Teams Admin Center](media/quality-of-experience-building-and-endpoint-data.jpg)

## Upload building and endpoint files

To upload a building or endpoint file, you must first create a file. You can download a [sample tenant data template](https://download.microsoft.com/download/0/b/9/0b9c1610-d421-489a-a3f9-d1ae703c9f1b/locations-template.zip) for example files to get started. For help with building mapping, see [Create a building map for reporting](cqd-building-mapping) and review the following sections on the structure of building and endpoint files.

After you have a building or endpoint file ready, follow these steps:

1. In Teams admin center, navigate to **Analytics & reports** &gt; **Building and endpoint data** and then select **Upload**.
2. From the **Upload Building or endpoint data** menu, select either **Building** or **Endpoint** for the type of file you'd like to upload, and then select **Upload** to choose a file.
3. After selecting a data file, specify a **Start date**. You can also select **Specify end date** to provide an optional end date. Only calls that occur after the specified start date and before the specified end date (if provided) will include the file's information.
4. After specifying a start and optional end date, select **Apply** to upload the file. Before the file is uploaded, it's validated. If validation fails, an error message is displayed requesting that you correct the file.
5. If no errors occur during validation, the uploaded file will begin processing. You can then see the uploaded data file in the table on the main page, which shows the full list of all uploaded files for the current tenant.

Note

It can take up to four hours to finish processing the building file.

If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.

![Image of the building and endpoint data upload page in Teams Admin Center](media/quality-of-experience-building-and-endpoint-data-upload.jpg)

## Building data file

The first type of tenant data file is the **building** data file. The information in this file provides important context for call reports, such as the network name and physical location details for your managed network. Once a file is uploaded, the file is processed by using the **Network IP** and **Network Range** columns to generate an expanded list of subnets. Tools like Call Quality Dashboard use this list of subnets to populate the file's information into call data using each participant's subnet information.

The format of the data file you upload must meet the following criteria to pass the validation check before upload:

- The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).
- The data file doesn't include a table header row. The first line of the data file is expected to be real data, not header labels like "Network."
- Data types in the file can only be String, Integer, or Boolean. For the Integer data type, the value must be a numeric value. Boolean values must be either 0 or 1.
- If a column uses the String data type, a data field can be empty, but you must still separate these fields with a tab or comma. An empty data field just assigns an empty String value.
- There's a 1,000,000 expanded row limit per tenant data file.
- There must be 16 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):

### Building data file format

| Column name | Data type | Example | Guidance |
| --- | --- | --- | --- |
| NetworkIP | String | 192.168.1.0 | Required |
| NetworkName | String | USA/Seattle/SEATTLE-SEA-1 | Required |
| NetworkRange | Number | 26 | Required |
| BuildingName | String | SEATTLE-SEA-1 | Required |
| OwnershipType | String | Contoso | Optional^1^ |
| BuildingType | String | IT Termination | Optional^1^ |
| BuildingOfficeType | String | Engineering | Optional^1^ |
| City | String | Seattle | Recommended |
| ZipCode | String | 98001 | Recommended |
| Country | String | US | Recommended |
| State | String | WA | Recommended |
| Region | String | MSUS | Recommended |
| InsideCorp | Bool | 1 | Required |
| ExpressRoute^2^ | Bool | 0 | Required |
| VPN | Bool | 0 | Optional |
| PublicIP^3^ | String | 203.0.113.1 | Optional |

^1^ While these optional columns are named to suggest what values you might want to populate them with, you can customize usage for other purposes, such as: Network Priority - `Tier 1, Tier 2, Tier 3`.

^2^ This setting can be used to reflect whether or not the network uses Azure ExpressRoute. You can customize usage for other purposes.

^3^ Use the **PublicIP** column to define the egress (public) IP address for a location. This value disambiguates locations that share the same private IP subnet range, so that calls from each location map to the correct building. Leave this field empty for locations that don't require disambiguation. For more information, see PublicIP.

**Sample row:**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0,203.0.113.1`

Important

The network range can be used to represent a supernet, or a combination of several subnets with a single routing prefix. All new building uploads are checked for any overlapping ranges. If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again. Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports. Certain VPN implementations don't accurately report the subnet information.

If two locations legitimately use the same private IP subnet range (for example, the same default subnet at different branch offices), use the **PublicIP** column to define each location's egress IP address so that calls map to the correct building. For more information, see PublicIP.

The VPN column is optional and defaults to 0. If the VPN column’s value is set to 1, the subnet represented by that row fully expands to match all IP addresses within the subnet. Use this value sparingly and only for VPN subnets since fully expanding these subnets has a negative impact on query times for queries involving building data. If the expansion of the subnet results in a row count beyond the 1,000,000 row limit, the building file isn't accepted.

### Supernetting

You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR), in place of defining each subnet. A *supernet* is a combination of several subnets that share a single routing prefix. Instead of adding an entry for each subnet, you can use the supernetted address. Supernetting is supported, but we don't recommend using it.

For example, Contoso's marketing building is made up of the following subnets:

- 10.1.0.0/24—first floor
- 10.1.1.0/24—second floor
- 10.1.2.0/24—third floor
- 10.1.3.0/24—fourth floor

Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.

- Network = 10.1.0.0
- Network Range = 22

Here are a few things to consider before you implement supernetting:

- Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.
- Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data. Let's say there's a quality problem involving subnet 10.1.2.0. If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab). If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.
- It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.
- It's common to find 192.168.0.0 in data. For many organizations, subnet indicates that the user is at home. For others, this subnet is the IP address scheme for a satellite office. If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide#common-subnets).

Important

The network range can be used to represent a supernet. All new building data file uploads are checked for any overlapping ranges. If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue. Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.

### VPN

The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365, which is where CQD data is sourced from, includes a VPN flag. CQD sees this data as the First VPN and Second VPN dimensions. However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter. Not all VPN vendors properly register Remote Access adapters. Because of this, you might not be able to use the built-in VPN query filters. Use the VPN column discussed above to accurately mark and identify VPN subnets. It's also good practice to label your VPN networks for easy identification in your reports.

Examples of how to label your VPN subnets:

- Define a **Network Name** by entering "VPN" in this field for VPN subnets.

    ![QCD report screenshot showing VPN using network name.](media/qerguide-image-vpnnetworkname.png)
- Define a **Building Name** by entering "VPN" in this field for VPN subnets.

    ![QCD report screenshot showing VPN using building name.](media/qerguide-image-vpnbuildingname.png)

Note

VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless. When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.

### PublicIP

Private IP subnet ranges (such as 192.168.1.0/24 or 10.0.0.0/24) aren't globally unique, so different locations can share the same private subnet. When that happens, subnet-based mapping alone can't tell which building a call came from, and calls from those locations can map to the wrong building.

Use the optional **PublicIP** column to define the egress (public) IP address for a location. The egress IP is the public-facing address that a location's internet traffic exits from. When two rows share the same private **NetworkIP** and **NetworkRange**, the **PublicIP** value disambiguates them so that each location's calls map to the correct building.

Keep the following in mind when you use the **PublicIP** column:

- The column is optional. Leave it empty for locations that don't share a private subnet range with another location.
- Enter the location's egress IP address as a String (for example, `203.0.113.1`). As with other empty String fields, still include the delimiter (tab or comma) when the value is empty.
- Only populate **PublicIP** when you need to disambiguate locations that share the same private subnet. Locations with distinct subnets don't require it.

## Endpoint data file

The other type of data file is the **Endpoint** data file. This file allows you to define user endpoint Make, Model, and Type information for devices used in Teams calls and meetings. The **EndpointName** column in the file should reflect the device name and is matched to the Call Quality Dashboard columns "First Client Endpoint Name" and "Second Client Endpoint Name" to populate data in CQD reports.

The format of the data file you upload must meet the following criteria to pass the validation check before upload:

- The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).
- The content of the data file doesn't include table headers. The first line of the data file is expected to be real data, not a header label like "EndpointName."
- All seven columns use the String data type only. The maximum allowed length is 64 characters.
- Entries are case-sensitive. For example, EndpointName **ABC123** is treated as unique from EndpointName **abc123**.
- A data field can be empty—however, it must still be separated by a tab or comma. An empty data field just assigns an empty String value.
- EndpointName must be unique, otherwise the upload fails. If there's a duplicate row or two rows that use the same EndpointName, the conflict will cause incorrect joining.
- EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels. They can be empty Strings or values such as "IT Department designated 2018 Laptop" or "Asset Tag 5678."
- There must be seven columns for each row and the columns must be in the following order:

### Endpoint data file format

| Column name | Data type | Example | Guidance |
| --- | --- | --- | --- |
| EndpointName | String | 1409W3534 | Required |
| EndpointMake | String | Fabrikam | Optional |
| EndpointModel | String | Model 123 | Optional |
| EndpointType | String | Laptop | Optional |
| EndpointLabel1 | String | IT designated 2018 Laptop | Optional |
| EndpointLabel2 | String | Asset Tag 5678 | Optional |
| EndpointLabel3 | String | Purchase 2018 | Optional |

**Sample row:**

`1409W3534,Fabrikam,Model 123,Laptop,IT designated 2018 Laptop,Asset Tag 5678,Purchase 2018`

## Updating a building file

While gathering building and subnet information, administrators often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available. When this occurs, you need to re-upload your building file. To ensure call reporting accurately represents your network over time, you can upload multiple files with separate start and end dates to reflect the state of your network at different times. Each file applies to calls that occur within the file's start and end times.

Important

While you can have multiple building files with distinct start and end times that apply to different time periods, you can't combine information from multiple files for the same time period.

## Add new subnets over time

You can add new subnets that weren't originally part of your network topology. To add new subnets, follow these steps:

1. Select the latest building file from the list on the **Building and endpoint data** page, and select the **Download** button. Confirm the file downloaded successfully.
2. With the latest building file still selected, select **Edit** and provide an end date that occurs at least one day before the net new subnets were acquired.
3. Append the new subnet information to the local building file you downloaded.
4. Upload the newly modified building file, and set the start date for one day after the previous building file ends.

## Locate missing subnets

After you upload building information for managed networks, every managed network should have a building association. However, this might not always be the case. Typically, a few subnets are missed. To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD. The Missing Subnet Report presents all the subnets with 10 or more audio streams that aren't defined in the building data file. Common home subnets are excluded from this report. Ensure that there are no managed networks in this list.

Important

To filter the report to view only your organization's tenant data, you need to add your tenant ID as a query filter for **Second Tenant ID** to this report. Otherwise, the report shows federated subnets.

Note

Be sure to adjust the Month Year report filter to the current month. Select **Edit**, and adjust the **Month Year** report filter to save the new default month.

## Add missing subnets

If subnets are missing, use the following steps to update the original building data file and re-upload it:

1. Select the latest building file from the list on the **Building and endpoint data** page, and select the **Download** button. Confirm the file downloaded successfully.
2. With the latest building file still selected, select **Delete** to remove it.
3. Append the new subnet information to the local building file you downloaded.
4. Upload the newly modified building file. Be sure to set the start date appropriately so that it applies to historical data.