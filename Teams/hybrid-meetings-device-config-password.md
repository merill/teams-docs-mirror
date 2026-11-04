---
layout: Conceptual
title: Step 5 - Turn off password expiration - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/hybrid-meetings-device-config-password
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
ms.date: 2025-01-17T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- m365solution-teamshybrid
- m365solution-scenario
- m365initiative-meetings
- teams-rooms-devices
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
ms.localizationpriority: high
description: Disable password expiration on resource accounts used with Teams Rooms devices.
locale: en-us
document_id: 3beec0ce-0b72-9c12-6068-dbff759f1d56
document_version_independent_id: 3beec0ce-0b72-9c12-6068-dbff759f1d56
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/hybrid-meetings-device-config-password.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: hybrid-meetings-device-config-password
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/hybrid-meetings-device-config-password.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0abff8a6-ee3f-fc6d-a806-3512be4a884e
---

# Step 5 - Turn off password expiration - Microsoft Teams | Microsoft Learn

![IT Pro audience](media/hybrid-audience-itpro-small.png)

Based on organization policies, resource account passwords may be set to expire automatically after a period of time. If the resource account password expires, the Teams Rooms device with sign out and can't sign in again without manual intervention.

Note

Setting **Password never expires** is a requirement for shared Microsoft Teams devices. If your organization prohibits passwords that don't expire, you'll need to create an exception for Teams device resource accounts.

To turn off password expiration, follow the steps in one of the following tabs:

# [Microsoft Graph PowerShell](#tab/graph-powershell-password)
1. Connect to [Microsoft Graph PowerShell](/en-us/microsoft-365/enterprise/connect-to-microsoft-365-powershell):

    ```PowerShell
       Connect-MgGraph -Scopes "User.ReadWrite.All"
    ```
2. Set the password to never expire, this example sets the password for the account ConferenceRoom01@contoso.com to never expire.

    ```PowerShell
    Update-MgUser -UserId ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
    ```

# [Active Directory (On-premises)](#tab/active-directory1-password)
1. Connect to [Active Directory PowerShell](/en-us/powershell/module/activedirectory):

    ```PowerShell
       Import-Module ActiveDirectory
    ```
2. Set the password to never expire, this example sets the password for the account ConferenceRoom01@contoso.com to never expire.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---