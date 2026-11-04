---
layout: Conceptual
title: Add peripherals to inventory - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/get-peripheral-information
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: altonk
ms.author: tonysmit
manager: pamgreen
ms.reviewer: eviegrimshaw
ms.date: 2026-07-08T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.localizationpriority: medium
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Rooms
- Tier1
ms.custom: QuickDraft
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn how to gather information about connected devices and add them to your inventory in Microsoft Teams
locale: en-us
document_id: 42ef7e0d-60d3-64a6-20e1-0ef922c53e96
document_version_independent_id: 42ef7e0d-60d3-64a6-20e1-0ef922c53e96
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/get-peripheral-information.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/get-peripheral-information
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/get-peripheral-information.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/07bb3e10-d135-43ff-bc8b-360497cb39fa
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/12e559b9-eaf6-4aee-9af7-62334e15f863
platformId: 90ebf13e-d00b-8ae9-2763-8a8b1c480b43
---

# Add peripherals to inventory - Microsoft Teams | Microsoft Learn

The script utilizes PowerShell cmdlets and native Windows API functions to gather information about connected devices (peripherals). It can tell the differences between different types of peripherals such as USB devices, monitors, cameras, speakers, and microphones.

When you run the PowerShell script, the data is exported to a CSV file that can be upload to Teams Pro Management Portal for managing, monitoring, and reporting usage of devices in BYOD rooms and Bookable Desks.

## Steps

1. Go [here](https://www.microsoft.com/download/details.aspx?id=106063) to download the **Get-TeamsBYODSpaceDevices.ps1** PowerShell script.
2. Unblock and extract the downloaded zip file. Move the **Get-TeamsBYODSpaceDevices.ps1** script to your preferred location on your PC.
3. Open a new PowerShell window and navigate to the location where you moved the **Get-TeamsBYODSpaceDevices.ps1** script.

    Note

    You can optionally open the script and customize it before you run it. However, don't change the sheet name. The sheet name must be named **PERIPHERALS**.
4. Run the script by executing the following command in the PowerShell window:

    ```powershell
    \Get-TeamsBYODSpaceDevices.ps1
    ```
5. The script prompts will guide you through the process:

    1. Wait for the script to detect and gather information about internal peripherals. The waiting period is essential for the script to make sure it establishes a baseline between internal and externally connected peripherals.
    2. Connect the external peripherals when prompted.
    3. Provide the Account information so as to properly associate the peripheral with the right room or desk account.
    4. Provide the folder path where the PERIPHERALS.csv file will be saved when prompted.
    5. The script will process the discovered peripheral data and export it to the specified file path.
6. Review the exported data to verify accuracy.
7. When finished, enter 'Y' when prompted to end the collection process.
8. Open the CSV saved to the specified file path and review the device details collected, including the following fields:

    1. Account - Resource account for the desk or desk pool to associate the peripheral device with, entered by the user.
    2. Display Name - Display name for the desk or desk pool in Teams Pro Management Portal, entered by the user.
    3. Product ID - ID for the product detected by the script.
    4. Vendor ID - ID for the product manufacturer detected by the script.
    5. Serial Number - Serial number for the peripheral device detected by script. Serial number value must be present and unique or the peripheral association will not work correctly for a bookable desk. Rows with serial number value missing will be skipped during import. When the script is unable to detect a device's serial number correctly, the device may be an older model or is otherwise unsupported. As a fallback, use the peripheral auto-association process, which can detect some devices not detected by the script.
    6. Peripheral Name - How the peripheral device name should appear in Teams Pro Management Portal.
    7. Peripheral Type - How the peripheral device type should appear in Teams Pro Management Portal.
9. Check to ensure the **CSV file contains only plain text**. Values can include letters, numbers, spaces, and symbols, but not links or other non-text content. The import process will fail if links or non-text content is present in the file.
10. Save the CSV file in .XLSX format. The first sheet in the CSV file must be titled **PERIPHERALS**.

    Important

    If sensitivity labels are enabled in your tenant, verify that the Excel file has a label of non-business, public, or general. Any other more confidential setting will cause the import to fail.
11. Sign in and open the [Microsoft Teams Pro Management portal](https://portal.rooms.microsoft.com/), on the **Planning &gt; Inventory &gt; Devices** page, select **Import** to add the device inventory to upload the file you modified.
12. Verify that the device and desk association is updated successfully in the Teams Pro Management portal.