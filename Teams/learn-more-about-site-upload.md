---
layout: Conceptual
title: Add and update reporting labels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/learn-more-about-site-upload
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.reviewer: mamcgrath
ms.date: 2025-09-15T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-voice
description: Learn how to add and update Call Analytics reporting labels by uploading a text file that contains a list of physical locations and associated subnets.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
locale: en-us
document_id: 2f8119c9-61af-b469-af98-ddd37764c0ca
document_version_independent_id: 7d829a74-9df7-5b6f-8e1c-44d3e5d38f75
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/learn-more-about-site-upload.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: learn-more-about-site-upload
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/learn-more-about-site-upload.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: ce87748d-3732-78f7-b64d-019646ed4769
---

# Add and update reporting labels - Microsoft Teams | Microsoft Learn

Warning

Starting September 15, 2025, Reporting Labels will no longer be supported. To manage your tenant data for reporting, see [Building and endpoint data](cqd-upload-tenant-building-data).

Reporting labels are used in your organization to indicate the physical locations of offices, buildings, or organizational sites. The Reporting labels page in the Microsoft Teams admin center lets you provide a text file (.csv or .tsv) containing a list of physical locations and their associated network subnets. This file is used by Call Analytics for generating reports. When you upload your subnet mapping, the reports provided by these services will contain the location names as well, making the reports easier to understand and use for remediating any potential issues.

Important

Reporting Labels that you upload will be handled as *Support Data* under your agreement for Office 365, including any information that would otherwise be considered *Customer Data* or *Personal Data*. Please don't include data you do not wish to provide to Microsoft as *Support Data*, as this information will be visible to Microsoft Engineers for support purposes.

The report labels and locations data you provide is a single data structure – there's currently no interface available to make individual edits to the data.

**To edit the table of subnets and locations**

1. In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** &gt; **Reporting labels**.
2. Select **Upload data**.
3. In the **Upload data** pane, select **Select a file**, and then browse to and upload your edited .csv or .tsv file.
4. Select **Upload**.

You can download a sample template [here](https://download.microsoft.com/download/0/b/9/0b9c1610-d421-489a-a3f9-d1ae703c9f1b/locations-template.zip).

Use the following example to help create your data file.

Important

Your data file shouldn't contain column headers (such as Network, Network Name, etc.). These are used here for informational purposes only.

| Network | Network Name | Network Range | Building Name | Ownership Type | Building Type | Building Office Type | City | Zip Code | Country | State | Region | Inside Corp | Express Route |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 10.0.128.0 | SVC-1 | 32 | USCAMTV001 | Contoso Leased RE&F | Office | RE&F | Mountain View | 94043 | US | CA | US | 1 | 1 |
| 10.0.130.0 | SVC-1 | 32 | USCAMTV001 | Contoso Leased RE&F | Office | RE&F | Mountain View | 94043 | US | CA | US | 1 | 1 |
| 10.0.131.0 | SVC-1 | 32 | USCAMTV001 | Contoso Leased RE&F | Office | RE&F | Mountain View | 94043 | US | CA | US | 1 | 1 |
| 10.0.132.0 | SVC-1 | 32 | USCAMTV001 | Contoso Leased RE&F | Office | RE&F | Mountain View | 94043 | US | CA | US | 1 | 1 |

For more information about formatting your data file, see [Tenant data file format and Building data file structure](cqd-upload-tenant-building-data#building-data-file).