---
layout: Conceptual
title: Conditional Access and compliance best practices for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/conditional-access-and-compliance-for-devices
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
ms.date: 2026-10-19T00:00:00.0000000Z
ms.topic: best-practice
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
description: Learn about recommended Conditional Access and Intune device compliance policies and best practices for Microsoft Teams Rooms.
locale: en-us
document_id: 27c7b5b4-963e-265b-decf-57fe4a614905
document_version_independent_id: 27c7b5b4-963e-265b-decf-57fe4a614905
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/conditional-access-and-compliance-for-devices.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/conditional-access-and-compliance-for-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/conditional-access-and-compliance-for-devices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: 972e4272-39bd-3afa-1eb6-dd8cf6929b9f
---

# Conditional Access and compliance best practices for Microsoft Teams Rooms - Microsoft Teams | Microsoft Learn

This article provides requirements and best practices for Conditional Access and Intune device compliance policies for Microsoft Teams Rooms on Windows, Teams Rooms on Android, and Teams panel devices.

Note

To use this feature with a Teams Rooms device, you need to assign a Microsoft Teams Rooms Pro license to the device. For more information, see [Microsoft Teams Rooms licenses](rooms-licensing).

## Requirements

- Teams Rooms resource accounts created, for more information, see [Create resource accounts for rooms and shared Teams devices](create-resource-account).
- A Microsoft Entra ID P1 Service Plan is required to use Conditional Access which is included in the Microsoft Teams Rooms Pro and Shared Device licenses.

## Teams Rooms Conditional Access best practices

Conditional Access policies can secure the sign in process on devices that are in shared spaces. For an overview of Conditional Access in Microsoft Entra ID, see [What is Conditional Access in Microsoft Entra ID?](/en-us/azure/active-directory/conditional-access/overview).

When using Conditional Access to secure Teams Rooms, consider the following best practices:

- Include all Microsoft 365 room resources accounts associated with Teams Rooms in one Microsoft Entra ID user group.
- Use a naming standard for all Teams Rooms resource accounts. For example, the account names 'mtr-room1@contoso.com' and 'mtr-room2@contoso.com' both start with the prefix 'mtr-'. When account names are standardized, you can use dynamic groups in Microsoft Entra ID to automatically apply Conditional Access policies to all of these accounts at once. For more information on dynamic groups, see [Rules for dynamically populated groups membership](/en-us/azure/active-directory/enterprise-users/groups-dynamic-membership).
- Exclude your Teams Rooms resource accounts from all existing Conditional Access policies and create a new policy specific to the resource accounts.
- Don't require user interactive multifactor authentication (MFA). User interactive MFA isn't supported for Teams Rooms resource accounts since the resource accounts don't have a second device to approve the MFA request. Alternative methods to achieve multifactor authentication for userless devices should be used which satisfy at least two of these factors: something you are, something you know, and something you have.
- Teams device resource accounts should be excluded from any policies requiring action to be taken during the sign in flow such as user interactive MFA or adding authentication methods with self-service password reset, the prompt for registration isn't supported on Teams devices and will block sign in.
- For end-user personal accounts signing into a Teams device, ensure that the other authentication methods are configured on a workstation or mobile device prior to attempting sign in on a Teams device.
- For Teams Android devices, the manufacturer name and device model are passed to conditional access within the **Display Name** field at initial login. This can be used to filter and allow or deny sign in for specific device makes and models.

For a list of supported Conditional Access assignments for Teams Rooms, see [Supported Conditional Access policies](supported-ca-and-compliance-policies#supported-conditional-access-policies).

### Example Conditional Access policy

In this example, the Conditional Access policy works as follows:

1. The account signing in must be a member of a specific user group, in this example, the "Shared devices" group.
2. The account signing in must only be trying to access specific resources (required resources can be found here: [Supported Conditional Access policies](/en-us/microsoftteams/rooms/supported-ca-and-compliance-policies)). Attempts to sign into any other client app are rejected.
3. The authentication method must be modern authentication. Legacy authentication mechanisms should be blocked.
4. The resource account must be signing in on the Windows or Android device platform.
5. The resource account must also sign in from a known, trusted location.
6. The resource account must be signing in from a compliant device.

If these conditions are met successfully, and the device has the correct username and password, then the resource account signs into Teams.

## Intune compliance for Teams Rooms

Compliance requirements are defined rules that devices must meet to be marked as compliant, such as minimum operating system version. Device compliance can be used as a condition in conditional access before the resource account can sign in.

For a list of supported Intune compliance policies for Teams Rooms, see [Supported device compliance policies](supported-ca-and-compliance-policies#supported-device-compliance-policies).

### Example Intune compliance policy for Teams Rooms on Windows

1. Require that a firewall is running on Teams Rooms on Windows.
2. Require a minimum operating system version.
3. Require that Microsoft Defender is running on Teams Rooms.

This compliance policy should be assigned to the Teams Rooms devices and the Teams Rooms resource accounts. If the device doesn't meet these requirements, it will be marked non-compliant.

### Example Intune compliance policy for Teams Rooms on Android and Teams panels

1. Minimum operating system version is greater than Android 10.
2. Block rooted devices.
3. Require encryption of data storage on device

This compliance policy should be assigned to the Teams Rooms devices and the Teams Rooms resource accounts. If the device doesn't meet these requirements, it will be marked non-compliant.