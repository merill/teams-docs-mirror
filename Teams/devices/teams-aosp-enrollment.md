---
layout: Conceptual
title: Intune Enrollment for Teams Android Devices - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/teams-aosp-enrollment
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn to configure Intune for automatic enrollment for Teams Android devices
author: MattSlomka
ms.author: mattslomka
ms.reviewer: tjaved
manager: srpall
ms.service: msteams
ms.topic: install-set-up-deploy
ms.date: 2025-11-25T00:00:00.0000000Z
ms.subservice: itpro-devices
locale: en-us
document_id: c02f5324-e3f4-b5d4-5851-fed6137a102c
document_version_independent_id: c02f5324-e3f4-b5d4-5851-fed6137a102c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/teams-aosp-enrollment.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/teams-aosp-enrollment
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/teams-aosp-enrollment.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6763db41-9d7b-78d1-3c84-0c7eb0e3ab1c
---

# Intune Enrollment for Teams Android Devices - Microsoft Teams | Microsoft Learn

Learn how IT administrators can prepare their environment for Teams Android devices to automatically enroll in Intune using a mobile device enrollment (MDM) method called Android Open Source Project (AOSP) Device Management. This MDM enrollment method replaced the legacy Device Administrator enrollment method.

This article covers:

- Setting up new AOSP Device Management enrollment profiles
- Creating new Intune compliance policies

Note

These steps are specific to Teams Android devices (Teams Rooms on Android, Teams phone, & Teams Panels). If you have non-Teams devices, refer to the Intune guidance for setting up profiles: [Set up Android (AOSP) device management in Intune for corporate-owned user-associated devices - Microsoft Intune | Microsoft Learn](/en-us/mem/intune/enrollment/android-aosp-corporate-owned-user-associated-enroll)

### Prerequisites

To complete this setup, you need:

- Intune licenses assigned to your Teams Android device resource accounts or user accounts.
- Teams Android Devices deployed which are enrolled using Device Administrator.
- Intune administrative permission.

Important

Teams Rooms Basic licenses don't include Intune so devices using a Basic licensed resource account will not enroll with Intune. Likewise, if an organization doesn't want to enroll in Intune, they can remove the Intune license on their resource accounts at which point the AOSP enrollment profile outlined in this article isn't required.

## Step 1 - Set up a new AOSP device management enrollment profile

In order for Teams Android Devices to enroll in AOSP Device Management successfully, an enrollment profile must be created.

### Setup AOSP management enrollment profiles

1. Sign in to the Intune Management Console using an account with Intune administrator permissions: https://intune.microsoft.com/.
2. Select **Devices** &gt; **Enrollment** &gt; then **Android**.
3. Under **Android Open Source Project (AOSP)** &gt; **Enrollment Profiles**, select **Corporate-owned, user-associated devices**.
4. Select **Create policy**.
5. Use the following settings for the profile configuration:

    - **Name**: Give the profile a name like 'AOSP – Teams Devices'.
    - **Description**: Put in a description so others in the organization know what this enrollment profile is used for.
    - **Token expiration date**: Defaults to 65 years into the future and is best left at 65 years to avoid expiration.
    - **Wi-Fi**: Select **Not configured**.
    - **For Microsoft Teams devices**: Select **Enabled**.
    - **Apply device name template**: Select **No**

    ![Screenshot of AOSP enrollment profile.](/en-us/microsoftteams/rooms/media/android-migration-guide/aosp-enrollment-profile.png)

Note

There's a limit of one enrollment profile per tenant with the **For Microsoft Teams devices** toggle set as **Enabled**. An expired enrollment token prevents devices from completing a successful sign-in and blocks new devices from enrolling.

1. Select **Next**.
2. Review the profile and then select **Create**.

The enrollment profile is now ready to enroll devices.

Note

AOSP enrollment profiles include a QR code but Teams Android devices don't use this QR code. The devices have a custom configuration that allows enrollment using the Teams resource account credentials instead of the QR code.

## Step 2 - Set up AOSP Device Management Compliance Policies (if necessary)

If your organization uses [Conditional Access](/en-us/intune/intune-service/protect/conditional-access) with Intune Compliance as a requirement for successful sign in, you need to create a compliance policy and assign it to ensure devices are marked compliant post migration. If you don't create a compliance policy while requiring compliance as an authentication factor, the device will sign out after migration.

### Create a AOSP Device Management Compliance Policy

Note

The compliance policy is just an example of conditions you can set, the full list of supported compliance conditions is available in [Supported Conditional Access and Intune device compliance policies](/en-us/microsoftteams/rooms/supported-ca-and-compliance-policies?tabs=mtr-a#supported-device-compliance-policies)

1. Sign in to the Intune Management Console with an account with Intune administrator permissions: https://intune.microsoft.com/.
2. Select **Devices** &gt; **Compliance**, then **Create policy**.
3. Under **Platform** &gt; **Android (AOSP)**, then select **Create**.
4. Provide a name and description for the policy.
5. Select **Next**.
6. Under **Device Health** set 'Rooted Devices' to **Block**.
7. Under **Device Properties** set the 'Minimum OS version' and 'Maximum OS version' to match devices in your organization.
8. Under **System Security** set 'Require encryption of data storage on device' to **Yes**.
9. Select **Next**, then select **Next**.
10. Assign this profile to all devices in the organization or a group of devices.
11. Select **Next**, then select **Create**.

Tip

In step 10, selecting "All Devices" only assigns this compliance policy to all devices in your organization enrolled using AOSP Device Management, it will not conflict with Intune devices enrolled using other methods. If you have non-Teams AOSP DM enrolled devices, use an Entra ID [dynamic device group](/en-us/entra/identity/users/groups-create-rule) to apply the compliance policy to only your Teams Devices. Use this syntax for the dynamic membership rules to filter the Entra ID group to only devices enrolled using the Intune enrollment profile created earlier (example uses `AOSP – Teams Devices` as the profile name):

```odata
(device.enrollmentProfileName -eq "AOSP – Teams Devices")
```