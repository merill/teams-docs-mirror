---
layout: Conceptual
title: Restrict Teams Resource Accounts Sign In to only Teams Rooms with Conditional Access - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/block-non-compliant-teams-rooms-devices
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Follow this guide to learn how to restrict Teams Rooms resource accounts to only function on organization joined Teams Rooms devices.
author: kwekuako
ms.author: kwekua
manager: scotv
ms.date: 2026-05-28T00:00:00.0000000Z
ms.topic: how-to
ms.service: skype-for-business-server
ms.collection: RestrictedMode
ms.localizationpriority: medium
ms.reviewer: kwekua;
search.appverid: MET150
audience: Admin
locale: en-us
document_id: 577a856f-61dd-e532-809c-f963612a8fe4
document_version_independent_id: 577a856f-61dd-e532-809c-f963612a8fe4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/block-non-compliant-teams-rooms-devices.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/block-non-compliant-teams-rooms-devices
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/block-non-compliant-teams-rooms-devices.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 30ce2956-9b7f-1f73-5415-2aa36f66948c
---

# Restrict Teams Resource Accounts Sign In to only Teams Rooms with Conditional Access - Microsoft Teams | Microsoft Learn

In this article, you learn how to restrict Teams Rooms resource account authentication using conditional access policies to ensure accounts authenticate only on organization managed Teams Rooms on Windows devices.

## Prerequisites

To configure these settings, your organization must have the following licenses:

- Entra ID Premium P1 (or higher) (for dynamic groups & Conditional Access)
- Microsoft Intune (for device compliance and enrollment)
- Microsoft Entra ID Governance (for Access Packages)

[Teams Rooms Pro](/en-us/microsoftteams/rooms/rooms-licensing) licenses include Entra ID P1 and Intune, but Entra ID Governance may need to be purchased separately based on organization licensing.

The IT admin completing this must be a member of the following roles to perform these tasks:

- [Conditional Access Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference)
- [Exchange Online Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference)

## Step 1: Group all Teams Rooms resource accounts in Entra ID

All Teams resource accounts should be grouped together to ensure consistent conditional access policy assignment. If an existing group doesn't exist, create a new dynamic group that captures all [Teams Rooms resource accounts](/en-us/microsoftteams/rooms/create-resource-account?tabs=m365-admin-center%2Cgraph-powershell-password#create-resource-account--assign-the-license) called **MTR\_Resource\_Accounts** with these steps:

1. Go to the [Entra ID admin center](https://go.microsoft.com/fwlink/p/?linkid=2327102) &gt; **Groups** &gt; **New group**.
2. Select **Security** as the group type and add a name.
3. Under **Membership type**, choose **Dynamic User** and add a rule: (user.userPrincipalName -startsWith "mtr-").
4. Review and create the group.

## Step 2: Configure access packages to control Entra ID join permissions

For this security control to work, the Teams Rooms on Windows devices must be Entra ID joined. Access packages can be created to allow resource accounts to complete the Entra join of Teams devices in a controlled, limited-time window.

### Setup two security groups that are mapped to access packages

- Create Entra security group for Entra join called MTR\_DeviceSetup.
- Create Entra security group for Entra join called MTR\_DeviceFull.

### Allow resource accounts to complete Entra join of Teams devices in a controlled, limited-time window.

1. In **Microsoft Entra ID** &gt; **Identity Governance** &gt; **Access packages**, create two packages:

    - MTR Device Setup (one-time, limited duration)
    - MTR Device Full (persistent membership for deployed devices)
2. For MTR Device Setup:

    - **Resource roles**: Assign the MTR\_DeviceSetup group Requests: Require two-step approval (local IT manager + global admin).
    - **Duration**: Configure a short access window (for example, one day) for Entra join. Under **Lifecycle** -&gt; **Expiration** set the Access package assignments expire = "Number of days" and set number of days = 1.
    - **Users who can request access**: For users in your directory and select **Specific users and groups**.
    - **Select users and groups**: set to **MTR\_Resource\_Accounts** dynamic group.
3. For MTR Device Full:

    - **Resource roles**: Assign the MTR\_DeviceFull group
    - **Requests**: Require two-step approval (local IT manager + global admin).
    - **Duration**: Access package assignments expire = "Never"
    - **Users who can request access**: For users in your directory and select **Specific users and groups**.
    - **Select users and groups**: set to **MTR\_Resource\_Accounts** dynamic group.

## Step 3: Tag approved devices via extension attributes

Each Entra ID joined Teams Rooms device needs to be marked with an extension attribute to separate that Windows device from other Entra ID joined devices. These device accounts can be marked and remote manually or as part of an automated flow.

1. As part of the Access Package workflow (upon successful Entra join), use an Entra ID provisioning action or Azure Automation runbook to set a device extension attribute (for example, extensionAttribute2 = "MTR\_Approved").
2. Confirm in **Entra ID** &gt; **Devices** that the attribute appears on the device object.
3. When the device is removed from MTR Device Full, remove the device object extension attribute.
4. Confirm in **Entra ID** &gt; **Devices** that the attribute is removed on the device object when removed from MTR Device Full access package.

## Step 4: Conditional access policies

Deploy two key Conditional Access (CA) policies to enforce compliance.

| Policy Name | Conditions | Grant Controls |
| --- | --- | --- |
| MTR - Restrict Resource Accounts to Managed Devices | \* Users: MTR\_Resource\_Accounts (Dynamic group) \* Cloud apps: All Microsoft 365 apps \* Device: device.extensionAttribute2 -eq "MTR\_Approved" | Grant access only if device is compliant and Entra joined |
| MTR - Block Resource Accounts except for initial setup | \* Users: MTR\_Resource\_Accounts (Dynamic group) \* Cloud apps: All Resources Exclusion group: MTR\_DeviceSetup | Block |

## Step 5: Verify and test

1. New Resource Account
    - Create a test conference room account.
    - Verify membership in MTR\_Resource\_Accounts group.
2. Device Enrollment
    - Request the MTR Device Setup access package for the test account.
    - Within the approval window, perform Entra ID join on a Teams device.
    - Verify device object is tagged MTR\_Approved.
3. Sign-In Tests
    - On the joined device, sign in to the Teams Rooms application with the resource account - Allowed.
    - On a non-MTR-Approved device, attempt a sign in using the same resource account - Blocked.
    - On a nonjoined device, attempt sign-in with the same resource account - Blocked.
4. Sign-In Tests
    - Remove device from MTR Device\_Full access package for when a Teams device is retired/decommissioned.
    - Attempt sign in from the device and ensure it's blocked.

## Best practices

- Review dynamic group rules periodically to ensure extension attribute schema remains accurate.
- Rotate extension attribute values if compromised, update dynamic group rules accordingly.
- Audit Access Package assignments monthly for orphaned or stale approvals.
- Document multifactor authentication enforcement for all accounts as a mandatory security practice.