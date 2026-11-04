---
layout: Conceptual
title: Uninstallation script for the classic Teams client - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-client-uninstall-script
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
ms.topic: install-set-up-deploy
ms.date: 2026-02-23T00:00:00.0000000Z
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: asgupta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Documenting for a downloadable uninstall script for the classic Teams client which allows you to manually shut off and remove the classic Teams client after moving to the new Teams client on non-VDI devices.
ms.localizationpriority: medium
locale: en-us
document_id: f53c813a-c32a-a31f-c318-ef26fc0319c4
document_version_independent_id: f53c813a-c32a-a31f-c318-ef26fc0319c4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-client-uninstall-script.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-client-uninstall-script
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-client-uninstall-script.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9d6273e4-adcd-9d1e-3c57-a3ea2b947467
---

# Uninstallation script for the classic Teams client - Microsoft Teams | Microsoft Learn

Microsoft has an [uninstallation script](https://aka.ms/uninstallclassicteamsscript) designed to uninstall the classic Teams client from all user profiles found on devices in your organization. If the classic Teams client is running for any user on the machine at the time the script is run, this script also ends the existing classic Teams running instance.

## Using the script

### Running the script on a single device

If you want to have the uninstallation script run for a single device, run it on that device [in administrative mode](/en-us/powershell/scripting/learn/ps101/01-getting-started#how-to-launch-powershell). After you run the script, the classic Teams client is uninstalled from all user profiles of the specified device.

## Running the script with device management software

If you need to have this uninstallation script run across all devices in your organization, run this script using device management software, like Intune. We have [sample instructions](https://github.com/microsoft/MDE-PowerBI-Templates/blob/master/ASR_scripts/AddShortcuts_with_Intune.md) for running the script in Intune.

If the script is run in Intune or other device management software:

- Admins get results in the form of .JSON that indicates different parameters, like how many instances of classic Teams there are, how many have been uninstalled from devices, and so on.
- Admins can download these results as a .CSV file.

Note

After the uninstallation of classic Teams, new Teams and Teams meeting add-in (TMA) might not work together. See [this article](/en-us/microsoftteams/troubleshoot/meetings/teams-meeting-add-in-missing#cause) for more information.

### Teams meeting add-in issue resolution

Please check the Teams version using [Find the version of Microsoft Teams you're using - Microsoft Support](https://support.microsoft.com/en-us/office/find-the-version-of-microsoft-teams-you-re-using-e6d3421f-b4f2-4fc6-a69e-ebc528fb1216).

If version is below 24215.1007.3082.1590, then Microsoft has [an additional script](https://download.microsoft.com/download/d/f/c/dfc1a7ce-e3da-4e12-94fc-bea60ba3d9ba/DetectAndUninstallTMA.ps1) to prevent the TMA issue.

Note

If the new Teams client is running and the TMA issue is detected by this script, it can't fix the issue. If you need to have this TMA script run across all devices in your organization in user context, please refer to these [sample instructions](https://github.com/microsoft/MDE-PowerBI-Templates/blob/master/ASR_scripts/AddShortcuts_with_Intune.md) for running the script in Intune. (User context can be selected by setting **Run this script using the logged-on credentials** to **Yes**.)