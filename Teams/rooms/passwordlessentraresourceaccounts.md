---
layout: Conceptual
title: Transition to Password-less Teams Shared Device Resource Accounts - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/passwordlessentraresourceaccounts
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Enable Password-less Entra Resource Accounts for your Microsoft Teams Shared Space Devices to enhance their reliability, security, and reduce management overhead.
author: Dimehta
manager: Srpall
ms.author: dimehta
ms.service: msteams
ms.topic: article
ms.date: 2026-09-15T00:00:00.0000000Z
locale: en-us
document_id: 3e84d2c2-41bb-a546-51b4-247537d7cd12
document_version_independent_id: 3e84d2c2-41bb-a546-51b4-247537d7cd12
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/passwordlessentraresourceaccounts.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/passwordlessentraresourceaccounts
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/passwordlessentraresourceaccounts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 70ed0775-939e-bcb6-9cee-bebac0b5f968
---

# Transition to Password-less Teams Shared Device Resource Accounts - Microsoft Teams | Microsoft Learn

Password-less Teams Shared Space device Resource Accounts enable a Teams device to sign in using a secure device bound resource account credential instead of relying on stored username and password credentials. This new authentication methodology is intended to reduce dependencies on password-based authentication, improve sign-in resilience, and ensure a secure by default device deployment mechanism. This new methodology builds on the existing Teams Resource Account creation and device deployment process while adding a step post deployment to switch the device authentication method from password based to a secure device bound credential.

This article describes the initial required pre-requisites and the steps required for migrating a Teams Room and its associated resource account to password less.

## Benefits

- Eliminates manual credential management for Teams devices.
- Improved security posture by using a secure device-bound token to communicate between the endpoint and Microsoft 365.
- Device admins have full visibility to the mapping between the device and the resource account credentials.
- Improved sign in resilience by allowing re-authentication attempts without manually re-signing in.
- End users notice no changes to the device functionality.
- Existing resource account creation processes remain and all existing accounts can be transitioned.
- Allow admins to reset or scramble passwords on the accounts so they're unknown.
- Authentication to Microsoft 365 services (Teams, Intune, Pro Management Portal, etc) does not change.

Note

At this time, the password is not removed from the resource account once migrated to password-less. We recommend that IT administrators use the cleanup steps or manually rotate the password after the transition to ensure that the password is unknown and secure.

## What happens in the background

When a Teams device and the associated resource account is transitioned to password-less several actions are taken in the background:

1. [Set as Resource](/en-us/microsoftteams/rooms/set-as-resource-account-for-shared-teams-devices) is configured on the resource account
2. For Teams Rooms on Windows devices, the Teams Rooms app is migrated from using the local 'Skype' Windows user account to instead sign into Windows using the resource account. All Teams Rooms app settings are moved over as part of this transition
3. The device connects to Entra ID and requests its secure token for password-less authentication
4. The device signs in using its new secure token and connectivity is validated. If the device is unable to login successfully the transition will be rolled back automatically.
5. The Pro Management Portal is updated with migration status

## Prerequisites

- Teams Resource Account created and signed into your Teams device.
- The resource account can be created directly in Microsoft Entra ID, or created in on-premises Active Directory and synchronized to Microsoft Entra ID. Accounts synchronized using Password Hash Sync or Pass-through Authentication are supported. An on-premises-only account that isn't synchronized to Microsoft Entra ID isn't supported.
- The Teams resource account must be licensed to convert it to password-less:

    - Teams Rooms on Windows and Teams Rooms on Android require a [Teams Rooms license](/en-us/microsoftteams/rooms/rooms-licensing)
    - Teams panels and Teams phones require a [Teams Shared Space license](/en-us/microsoftteams/teams-add-on-licensing/teams-shared-device-license)
        Note

        Teams panels if using the same resource account as a room device just require the Teams Rooms license you do not need to add the additional Shared Space license in that scenario
- Teams device and Resource Account are both visible in the Teams Rooms Pro Management Portal.
- Supported Teams Devices:

    - Teams Rooms on Windows
    - Teams Rooms on Android
    - Teams panel
    - Teams phone
- Administrative access required to set an account as a resource and schedule a migration: **Teams Administrator**.
- Administrative access required to use **Cleanup password** in the Teams Rooms Pro Management Portal: a portal role that grants permission to edit Resource Accounts and one of the following Microsoft Entra roles for the target account: **Password Administrator**, **User Administrator**, or **Global Administrator**. For a standard resource account that doesn't have a Microsoft Entra administrative role, Password Administrator is the least-privileged password-reset role.
- Teams Administrator alone doesn't provide permission to reset a resource account password.
- Assign Teams Administrator, Password Administrator, and portal permissions according to your organization's security, least-privilege, and separation-of-duties policies. The administrator who performs password cleanup must have both permission to edit Resource Accounts in the portal and permission to reset the target account in Microsoft Entra.
- Password cleanup in the portal isn't available for accounts with a Teams Shared Device license. Reset the passwords for those accounts in Microsoft Entra instead.

#### Teams Rooms on Windows Requirements

- Windows 11 24H2 running build 26100.8655 or later.
- [Microsoft Entra joined](/en-us/microsoftteams/rooms/mtrw-entraid-join) to the same Microsoft Entra tenant where the resource account was created. Microsoft Entra hybrid joined Teams Rooms on Windows devices aren't supported for password-less resource account migration.
- Teams Rooms on Windows app [5.6.135.0](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Windows#561350-5272026)

Note

Teams Rooms on Windows devices using a supported machine-wide proxy configuration, including a static proxy or proxy auto-configuration (PAC) file, are supported for password-less resource account migration. Proxy authentication isn't supported. Configure the proxy as described in Proxy for Teams Rooms on Windows, reboot the device so the Teams Rooms app and Pro Management agent pick up the settings, and verify that the device reports healthy network connectivity before scheduling migration.

#### Teams Rooms on Android Requirements

- Android OS 10 or later.
- Teams Rooms on Android app [1449/1.0.96.2026129709](/en-us/microsoftteams/rooms/rooms-release-note?tabs=Android#144910962026129709-june-2026)
- Authenticator app [6.2605.3066](/en-us/microsoftteams/devices/certified-device-apps?tabs=Authenticator#626053066)
- Teams Admin Agent app [1.0.0202606082157](/en-us/microsoftteams/devices/certified-device-apps?tabs=Agent#100202606082157)

#### Teams panel Requirements

- Android OS 10 or later
- Teams panels app [1449/1.0.97.2026164101](/en-us/microsoftteams/devices/devices-release-notes?tabs=panels#may-2026)
- Authenticator app [6.2605.3066](/en-us/microsoftteams/devices/certified-device-apps?tabs=Authenticator#626053066)
- Teams Admin Agent app [1.0.0202606082157](/en-us/microsoftteams/devices/certified-device-apps?tabs=Agent#100202606082157)
- Teams panels can be stand alone or signed into the same account as a Teams Room device. Teams panels using the same account as a Teams Room device will migrate to password-less at the same time.

#### Teams phone Requirements

- Android OS 10 or later.
- Teams phone app [1449/1.0.94.2026104705](/en-us/microsoftteams/devices/devices-release-notes?tabs=phones#july-2-2026)
- Authenticator app [6.2605.3066](/en-us/microsoftteams/devices/certified-device-apps?tabs=Authenticator#626053066)
- Teams Admin Agent app [1.0.0202606082157](/en-us/microsoftteams/devices/certified-device-apps?tabs=Agent#100202606082157)

Tip

We recommend testing with a small batch of devices prior to migrating your entire environment.

## Administrative roles for migration and password cleanup

Password-less resource account migration and password cleanup are separate operations that require different administrative permissions.

| Task | Required role | Details |
| --- | --- | --- |
| Assign the required administrative roles | Privileged Role Administrator or Global Administrator | This is a one-time role configuration in Microsoft Entra ID. Global Administrator isn't required for routine migration or password cleanup after the appropriate roles are assigned. |
| Set the account as a resource and schedule its migration | Teams Administrator | Required to perform the migration workflow in the Teams Rooms Pro Management Portal. |
| Run **Cleanup password** | A portal role that grants permission to edit Resource Accounts, plus Password Administrator, User Administrator, or Global Administrator | Password Administrator is the least-privileged password-reset role for a standard resource account that doesn't have a Microsoft Entra administrative role. It can be assigned at tenant scope or scoped to an administrative unit containing the resource accounts. |

Assign migration and password-cleanup responsibilities according to your organization's security, least-privilege, and separation-of-duties policies. The password-cleanup administrator needs both a portal role that grants permission to edit Resource Accounts and Password Administrator, User Administrator, or Global Administrator for the target account.

Note

Assigning Teams Administrator doesn't grant permission to reset resource account passwords. Assigning Password Administrator by itself also doesn't grant access to the cleanup operation in the Teams Rooms Pro Management Portal. Assign these permissions to administrators according to your organization's security and separation-of-duties policies.

Tip

For least-privilege administration, place Teams resource accounts in a dedicated administrative unit and assign Password Administrator at the scope of that administrative unit. Assign the role only to administrators responsible for password cleanup, and use Microsoft Entra audit logs to review password-reset activity.

## Step 1: Transition devices and accounts to password-less

Note

The administrator performing this transition must have the Teams Administrator role assigned to their account. Other administrative roles are planned to be added in the future, including Global Administrator.

1. Sign in to the [Teams Rooms Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service) using an account with the Teams Administrator admin role.
2. Select **Planning** &gt; **Resource Accounts** in the left navigation.
3. Select the **Migration** tab.
4. Select eligible resource account(s) to migrate.
5. Select **Schedule migration** to open the migration wizard.
6. Choose to either migrate now or during the next maintenance window.
7. Review the select and select **Confirm**.
8. The device(s) and account(s) will migrate at their scheduled time.

## Step 2: Verify migration progress

After the migration completes you may want to verify the following:

- The room reports a healthy status in the Pro Management Portal.
- The device signs in successfully.
- Teams device starts without repeated sign-in prompts.
- Teams device functionality works as expected.

## Step 3: Cleanup or rotate the resource account password

Important

The administrator who selects **Cleanup password** must have a portal role that grants permission to edit Resource Accounts and one of the following Microsoft Entra roles for the target account: **Password Administrator**, **User Administrator**, or **Global Administrator**. For a standard Teams resource account that doesn't have a Microsoft Entra administrative role, Password Administrator is the least-privileged password-reset role. Assign migration and password-cleanup responsibilities according to your organization's security and separation-of-duties policies.

Password Administrator can be assigned at tenant scope or at the scope of an administrative unit that contains the resource account. An administrative unit-scoped Password Administrator can reset passwords only for nonadministrator accounts in that administrative unit.

If the resource account has a Microsoft Entra administrative role, or is a member or owner of a role-assignable group, Password Administrator might not be able to reset its password. Remove unnecessary privileged assignments from the resource account or use an appropriate higher-privileged role. For more information, see [Who can reset passwords](/en-us/graph/api/resources/users?view=graph-rest-1.0#who-can-reset-passwords).

The portal doesn't support **Cleanup password** for an account with a Teams Shared Device license. Reset the password for that account in Microsoft Entra instead.

After a Teams device transitions to password-less authentication, its resource account password remains in Microsoft Entra ID, but the device no longer uses that password to sign in. Reset or scramble the password to a complex, secure value that isn't known or retained by an administrator.

The built-in **Cleanup password** wizard is available for supported, cloud-managed resource accounts that don't have a Teams Shared Device license. For resource accounts synchronized from Windows Server Active Directory, reset or [scramble the password](/en-us/entra/identity/authentication/how-to-plan-password-scramble-phishing-resistant-passwordless-authentication) in the source directory unless password writeback is enabled and the domain is managed. If authentication is federated to an external identity provider, change the password through that authoritative identity provider. This password-authority guidance is separate from migration eligibility. Changing the password doesn't affect the device-bound credential on a migrated Teams device.

### Use the built-in Cleanup password wizard

1. Sign in to the [Teams Rooms Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service) using an account with permission to edit Resource Accounts in the portal and permission to reset the target resource account's password in Microsoft Entra.
2. Select **Planning** &gt; **Resource Accounts** in the left navigation.
3. Select the **Migration** tab.
4. Select the migrated resource account(s) whose passwords you want to clean up.
5. Select **Cleanup password**.
6. Review and confirm the cleanup.

The wizard resets the selected account passwords to secure, unknown values. It doesn't remove the password property from the accounts. Migrated devices remain signed in using their device-bound credentials.

### Manually reset or scramble the password

1. Sign in to the Microsoft 365 admin center or Microsoft Entra admin center using an account with permission to reset the target resource account's password.
2. Find and select the resource account.
3. Reset the password to a complex, unique value that isn't retained or shared. For more information, see [Reset passwords](/en-us/microsoft-365/admin/add-users/reset-passwords) and [Reset a user's password](/en-us/entra/fundamentals/users-reset-password-azure-portal).
4. Verify that the Teams device remains signed in and healthy in the Teams Rooms Pro Management Portal.

## Troubleshooting, Known Issues, and FAQs

### Troubleshooting Tips

- Verify that the room meets the required platform software and app version requirements.
- Confirm that the resource account is correctly assigned.
- Check sign-in logs within Entra ID for failures.
- Review the migration status in the Pro Management portal – open detail panel for the failed account to see failure reason.
- Retry the migration after remediating any the failure reason or report blocking issues.
- If **Cleanup password**is unavailable or the operation returns an authorization error:
    - Verify that the signed-in administrator has a portal role that grants permission to edit Resource Accounts.
    - Verify that the administrator also has Password Administrator, User Administrator, or Global Administrator with permission to reset the target account's password. Teams Administrator alone isn't sufficient.
    - For an administrative unit-scoped Password Administrator assignment, verify that the resource account is a member of that administrative unit.
    - Verify that the resource account doesn't have a Microsoft Entra administrative role or a membership or ownership relationship with a role-assignable group that Password Administrator isn't permitted to reset.
    - For an account with a Teams Shared Device license, reset the password in Microsoft Entra because the portal cleanup operation isn't supported.
    - After changing a role assignment or administrative unit membership, allow time for the updated authorization to take effect, and then retry the operation.
    - Review Microsoft Entra audit logs to confirm the password-reset attempt and the administrator who initiated it.
- Revert to password authentication:
    - Teams Rooms on Windows: A reset of the Teams Rooms on Windows devices is required to revert from password-less authentication. A reset can be performed using the recovery image from your Teams Rooms manufacturer or with the [recovery tool](/en-us/microsoftteams/rooms/recovery-tool).
    - Teams Rooms on Android, Teams panels, and Teams phones: A full account sign out on the device will remove the password-less authentication token and allow a new sign in with a username and password. A sign out can be performed locally within the Teams settings on the device or by using the remote sign-out functionality in the Pro Management Portal.

### Known issues

**Device Replacement or Credential Changes**

> 
> If you need to replace a device or change the credentials, you must setup the new device using the account with a password first, and then perform the migration steps again to convert to password-less authenmtication.

**Password cleanup when the password is managed outside Microsoft Entra**

> 
> The built-in **Cleanup password** workflow is intended for cloud-managed resource account passwords. For a resource account synchronized from Windows Server Active Directory, reset or scramble the password in the source directory unless password writeback is enabled and the domain is managed. If authentication is federated to an external identity provider, change the password through that authoritative identity provider. This password-authority guidance is separate from migration eligibility. These password changes don't invalidate the device-bound credential on a successfully migrated Teams device.

**Password cleanup for Teams Shared Device-licensed accounts**

> 
> The Teams Rooms Pro Management Portal doesn't support **Cleanup password** for an account with a Teams Shared Device license. Reset the password for that account in Microsoft Entra instead. This limitation doesn't prevent the supported device from being migrated to password-less authentication.

**Pro Management operations fail on a Teams Rooms on Windows device that uses a system-wide proxy**

> 
> On affected Pro Management agent versions, the agent might check the signed-in user's proxy settings before the system-wide Windows proxy settings. If the resource-account user profile has no proxy or has stale proxy settings, Pro Management operations such as app updates, log collection, and driver updates can fail even when the Teams Rooms app can connect through the system-wide proxy. As a temporary workaround, configure matching proxy settings for the signed-in resource-account user. Don't use *bitsadmin /Util /SetIEProxy LOCALSYSTEM* for this issue because the affected agent path doesn't read that configuration and Windows feature updates can remove it, instead follow the proxy configuration guidance in [Proxy for Teams Rooms on Windows](/en-us/microsoftteams/rooms/rooms-prep#proxy-for-teams-rooms-on-windows).

**Teams Rooms on Windows remains on the sign-in page when network connectivity is delayed**

> 
> If network or switch configuration delays network connectivity to a Teams Rooms on Windows device during startup (for example STP delays or portfast being disabled on certain model switches), Resource Account migration might not complete automatic sign-in. The device can remain on the sign-in page after migration. To recover, manually sign in on the device or retry the Resource Account migration after network connectivity is available. To prevent the issue, configure the network so that the device has connectivity during startup.

**Crestron Teams Rooms on Windows devices are not compatible**

> 
> Crestron's unique software configuration is not currently compatible with password-less resource accounts. If a Crestron device has been migrated and you're experiencing issues, the device will need to be factory reset using the Crestron recovery media and continue to use password-based authentication for the time being. Crestron is working on resolution for this.

### Frequently Asked Questions

**Is migration automatic, or does an administrator need to start it?**

> 
> Migration is administrator-initiated. Microsoft doesn't automatically migrate eligible devices or resource accounts. An administrator must schedule the migration from Planning &gt; Resource Accounts &gt; Migration in the Teams Rooms Pro Management portal.

**Is migration to password-less authentication required?**

> 
> Migration is currently optional. We recommend migrating eligible devices to improve security and reduce password-management overhead. Test the migration with a small group of devices before migrating your broader environment.

**Is Set as Resource required before transitioning?**

> 
> No. The migration process sets the account as a resource. You don't need to use Set as Resource before migrating an eligible account.

**Can I deploy a new device as password-less without needing a username and password?**

> 
> No. Devices must be deployed using existing deployment methods using username and password and then transitioned to password-less after the fact. Deployment directly to password-less will come in the future.

**Which devices can be transitioned?**

> 
> Teams Rooms on Windows, Teams Rooms on Android, Teams panels, and Teams phones can be migrated when they meet the prerequisites in this article. Common area phones that use an eligible resource account and supported license are included as Teams phones.

**What changes after the transition?**

> 
> Only the authentication method changes. The device uses a secure, device-bound resource account credential instead of a stored username and password. Meeting, calling, device-management, and other supported device functionality remain unchanged. Administrators don't need to provision or manage a certificate manually. If the resource account password is modified the device will remain signed in unlike prior to the transition where the device would be signed out.

**Which administrative roles are required for migration and password cleanup?**

> 
> A Teams Administrator can set an account as a resource and schedule its migration in the Teams Rooms Pro Management Portal. To run **Cleanup password** for a standard resource account, the administrator needs both permission to edit Resource Accounts in the portal and Password Administrator, User Administrator, or Global Administrator with permission to reset that account's password.
> 
> Assign these roles and responsibilities according to your organization's security, least-privilege, and separation-of-duties policies. The password-cleanup administrator must also have a portal role that grants permission to edit Resource Accounts. Password Administrator can be assigned at tenant scope or scoped to an administrative unit containing the resource accounts. Teams Administrator alone doesn't grant permission to reset passwords.

**On a Teams Rooms on Windows device, after the transition, does it change administrative actions on the device?**

> 
> No accessing [admin mode](/en-us/microsoftteams/rooms/rooms-operations#switching-to-admin-mode) and changing settings on the device doesn't change. The only difference is that to return to the Teams Rooms experience, you need to reboot the PC as the local Skype user account is no longer available to sign-in with.

**Do resource account passwords still need to be managed after transition?**

> 
> After transition, the device no longer uses the resource account password to sign in. The password remains on the account, so we recommend using **Cleanup password** to reset it to a complex, unknown value.
> 
> For a standard resource account that doesn't have a Microsoft Entra administrative role, Password Administrator is the least-privileged password-reset role. User Administrator and Global Administrator can also reset eligible accounts. In all cases, the signed-in administrator must also have a portal role that grants permission to edit Resource Accounts. Teams Administrator alone can't reset the password.
> 
> Password Administrator can be scoped to an administrative unit containing the resource accounts. If a resource account has an administrative role or is a member or owner of a role-assignable group, Password Administrator might not be permitted to reset it. For more information, see [Who can reset passwords](/en-us/graph/api/resources/users?view=graph-rest-1.0#who-can-reset-passwords).
> 
> For an account with a Teams Shared Device license, reset the password in Microsoft Entra because **Cleanup password** isn't supported for that account in the portal.

**Will a converted device sign-in automatically after a restart?**

> 
> Yes. The device continues to use its device-bound credential and should sign in automatically after a restart.

**What happens if a migrated device is reimaged or replaced?**

> 
> The password-less credential is bound to the device and can't be transferred. The credential is also lost when a device is reset or re-imaged. When setting up the re-imaged or replacement device, reset the resource account password following the guidance in Step 3, setup the device using that username and password, and then migrate the device to password-less authentication again starting from Step 1.

**Is this new authentication method similar to something else already available from Microsoft?**

> 
> Password-less resource accounts function similarly to [Windows Hello for Business](/en-us/windows/security/identity-protection/hello-for-business/) authentication for end users. Both store a secure credential that is device bound and used to authenticate against Entra ID. Changing passwords does not impact existing deployed devices adding both security and resiliency.

**I manually signed out or reset my device, why does the device need a password again?**

> 
> This is expected, the password-less authentication token is lost during a manual device sign out or device reset. This is done to allow a way to switch accounts utilized on a device. In a future release we will offer ways to deploy devices from the login screen without needing a password. When setting up the reset device, reset the resource account password following the guidance in Step 3, setup the device using that username and password, and then migrate the device to password-less authentication again starting from Step 1.

**Is the token stored securely? Is the token bound to the device? When does the token expire?**

> 
> Yes, the password-less token is stored in the TPM on Windows and Keystore on Android. In either platforms scenario, the token is device bound and cannot be moved to another device. The token itself does not have a specific expiration.

**How do I revoke a token from a device remotely?**

> 
> Because the password-less token is device bound to the identity in Entra ID, you can delete the device itself from Entra ID and that will invalidate the password-less token. The device will then be signed out automatically at next authentication refresh. Deleting the device in Entra ID deletes that specific make/model/serial device for Android or breaks Entra ID join for Windows device, the account itself and any other devices associated will not be impacted. [Manage devices in Microsoft Entra ID](/en-us/entra/identity/devices/manage-device-identities#delete-a-microsoft-entra-device) has the steps for deleting devices.