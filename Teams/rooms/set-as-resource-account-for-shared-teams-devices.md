---
layout: Conceptual
title: Set as a Resource Accounts for Shared Devices in Teams Rooms Pro Management - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/set-as-resource-account-for-shared-teams-devices
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Set as a Resource Accounts for Shared Devices in Teams Rooms Pro Management
author: Dimehta
ms.author: dimehta
manager: srpall
ms.service: msteams
ms.topic: article
ms.date: 2026-08-04T00:00:00.0000000Z
ms.subservice: msteams-admin
locale: en-us
document_id: 2931510a-9c3f-d3be-8ec9-8632021114c0
document_version_independent_id: 2931510a-9c3f-d3be-8ec9-8632021114c0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/set-as-resource-account-for-shared-teams-devices.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/set-as-resource-account-for-shared-teams-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/set-as-resource-account-for-shared-teams-devices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d0d200b3-0138-8681-5d4d-2f825a44d6e6
---

# Set as a Resource Accounts for Shared Devices in Teams Rooms Pro Management - Microsoft Teams | Microsoft Learn

## Overview

Organizations commonly deploy shared Teams devices (Teams Rooms, Teams panels, and Teams phones) in meeting rooms, collaboration spaces, and common areas using accounts that are not tied to a single individual. These devices are deployed using Teams [resource accounts](/en-us/microsoftteams/rooms/create-resource-account) dedicated to the device which appear as user accounts within Entra ID. The "Set as Resource" capability within the Pro Management Portal enables IT administrators to specify that these accounts are dedicated to Teams Devices by marking them as a resource which sets an attribute in Entra ID on these accounts. Marking shared device accounts as a resource helps strengthen security, improve governance alignment, and reduce unintended access to Microsoft 365 resources that are intended for individual users.

## Key Benefits

Shared device accounts are fundamentally different from personal user accounts as they exist to support room experiences and shared collaboration scenarios not personal productivity workflows. By marking shared device accounts as Resource Accounts, organizations can use this to strengthen their security posture. Key benefits include:

- Microsoft 365 services are able to differentiate resource accounts from standard user accounts, enabling more secure, consistent, and resource aware behaviors across the ecosystem
- Removes resource accounts from meeting chats after the call ends
- Removes access to shared files and recordings
- Align shared device identities with Microsoft 365 governance and compliance models
- Prepare for future platform capabilities that enforce resource-specific access policies

## How it Works

When an administrator marks an account as a Resource Account in PMP:

1. PMP updates the account using Microsoft service APIs
2. The account is identified as a shared resource account within supported Microsoft 365 services
3. Shared device scenarios receive resource aware security handling
4. No user interaction is required on the Teams Rooms device as the operation is designed to be silent and non-disruptive for end users

Tip

**Set as a Resource** is configured automatically as part of the transition to [password-less resource accounts](/en-us/microsoftteams/rooms/passwordlessentraresourceaccounts). The steps in this guide allow you to configure **Set as a Resource** without transitioning to password-less if desired.

## Set a Resource Account as a Resource

1. Sign in to the [Teams Rooms Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service) using an account with [Teams Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#teams-administrator) privileges.
2. Select **Planning** &gt; **Resource Accounts** in the left navigation.
3. Select one or more shared device accounts
4. Select **Set as Resource**
5. Review the confirmation information
6. Select **Confirm**
7. PMP processes the request in the background
8. After the operation completes successfully, the account is marked as **Yes** in the Resource column.

## View Resource Account Status

The Resource Accounts page includes a **Resource** status column.

- Yes: The account is marked as a Resource Account and secured for shared-device usage
- No: The account has not yet been secured as a Resource Account

## Best Practices

Microsoft recommends:

- Using Resource Accounts for all Teams Rooms and shared collaboration devices
- Avoiding personal user accounts for shared meeting spaces
- Regularly reviewing shared device account inventory in PMP
- Applying governance and lifecycle management policies consistently across shared endpoints