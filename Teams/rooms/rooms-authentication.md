---
layout: Conceptual
title: Authentication in Microsoft Teams Rooms on Windows - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-authentication
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: dimehta
ms.date: 2026-02-20T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Learn how to configure modern authentication for Microsoft Teams Rooms on Windows
locale: en-us
document_id: 7f7e3603-9bec-acfc-1854-2c1275950cde
document_version_independent_id: 2aed2376-277a-3e93-5000-e509ff53434d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-authentication.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-authentication
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-authentication.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 245b52c4-9838-cb40-46b6-3cde6d15f504
---

# Authentication in Microsoft Teams Rooms on Windows - Microsoft Teams | Microsoft Learn

Microsoft Teams Rooms on Windows shares authentication component with Teams desktop client and uses the same underlying authentication libraries to connect to Teams and other Microsoft 365 services. As such, Teams rooms requirements for authentication are based on Microsoft Teams requirements. Learn more about [Identity models and authentication for Microsoft Teams](/en-us/microsoftteams/identify-models-authentication).

However, Teams Rooms on Windows have some key differences compared to an end user personal computer where Teams desktop runs. These differences may impact authentication configurations for Teams rooms.

## Key differences from the Teams Desktop application

1. Microsoft Teams Rooms resource accounts are centrally managed by IT administrators in an organization. End users don't have ability to sign in / out of Teams Rooms devices.
2. Microsoft Teams Rooms use Microsoft Entra accounts that are configured with resources mailbox in Microsoft Exchange.
3. Microsoft Teams Rooms on Windows application run under least privileged local user that has been further locked down using Windows [Shell Launcher V2](/en-us/windows/iot/iot-enterprise/customize/shell-launcher) to remove Windows shell components (Start menu, taskbar, settings etc.), such that only Teams Rooms application is aware of resource account used to sign in to Microsoft Teams. This mechanism also prevents other applications to get account information from Windows Account Manager as Windows has no information about resource account used by Teams rooms application.
4. Authentication in Microsoft Teams Rooms on Windows doesn’t require any user intervention and doesn’t support user interactive second-factor authentication. The modern authentication mechanism uses the [resource owner password credentials](/en-us/azure/active-directory/develop/v2-oauth-ropc) (ROPC) authorization grant type in OAuth 2.0.

It’s important to note that Microsoft Teams Rooms resource accounts shouldn't be configured to use user interactive multifactor authentication (MFA), smart card authentication, or client certificate-based authentication. Leverage other secondary factors to secure the Teams Rooms resource accounts such as: compliant device & known network location.

## Conditional Access Considerations

Teams Rooms resource account access to Microsoft 365 service can be limited using Conditional Access policies. Since Windows has no knowledge of resource account that is used by Teams room application, to apply device-level conditional access policies, you must enroll Teams Rooms on Windows devices with Microsoft Intune. Learn more about [Enrolling Microsoft Teams Rooms on Windows devices with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986). When the device is enrolled in Intune, the Teams Rooms application uses Windows enrolled account using Web access management (WAM) to send device compliance status for conditional access evaluation. To learn more about Conditional Access and Intune compliance policies, see [Conditional Access and Intune compliance for Microsoft Teams Rooms](/en-us/microsoftteams/rooms/conditional-access-and-compliance-for-devices) and [Supported Conditional Access and Intune device compliance policies for Microsoft Teams Rooms](/en-us/microsoftteams/rooms/supported-ca-and-compliance-policies?tabs=mtr-w)