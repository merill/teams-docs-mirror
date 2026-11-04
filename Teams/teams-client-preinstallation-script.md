---
layout: Conceptual
title: Preinstallation script for the Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-preinstallation-script
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
ms.date: 2025-06-30T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: daro
search.appverid: MET150
f1.keywords:
- NOCSH
description: This article documents a script that administrators can run before beginning an organization's installation of Teams clients, or after an installation fails for some or all clients. This script should help determine what may be blocking the installation of the Teams client on a device or devices.
ms.localizationpriority: medium
locale: en-us
document_id: 4aaf2156-20e5-d273-f709-d07d38c88a79
document_version_independent_id: 4aaf2156-20e5-d273-f709-d07d38c88a79
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-preinstallation-script.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-preinstallation-script
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-preinstallation-script.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a6c8d3ff-c78c-ee63-4e4e-b9e783e1392c
---

# Preinstallation script for the Teams client - Microsoft Teams | Microsoft Learn

Microsoft has a [preinstallation check script](https://aka.ms/NewTeamsReadinessCheck) designed to identify why devices can't install the Teams client. The script also suggests solutions to any problems it finds. Admins can save time installing Teams by running the script in these two use cases:

- Before you install Teams for the first time.
- After the Teams client installation fails on some devices.

When an admin runs this script, they can proactively identify and resolve issues, making it easier to install the Teams across their organization.

Note

If you want to get a preinstall check status across all devices, run this script using device management software like Intune. If you want to have the preinstallation script check the status for a single device, you can run it directly on the device.

## Using the script

You can run the script locally on a device, in Intune, or using some other device management software.

We have sample instructions to run the script in Intune at this location: [Sample instructions](https://github.com/microsoft/MDE-PowerBI-Templates/blob/master/ASR_scripts/AddShortcuts_with_Intune.md)

After running the script:

- If run locally, the failures and suggested resolutions display in the command line for administrators to see. Administrators can fix the issues and run the Teams client installation again.
- If the script is run in Intune or other device management software:
    - Administrators can see issues and suggested resolutions for each device.
    - Administrators can download these results as a CSV file.
    - Administrators can filter the CSV file for each error to identify all devices requiring a specific fix.
    - Administrators can fix one error at a time across all machines and rerun the Teams installation.