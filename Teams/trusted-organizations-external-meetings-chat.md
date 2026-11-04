---
layout: Conceptual
title: IT Admins - Manage external meetings and chat with people and organizations using Microsoft identities - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/trusted-organizations-external-meetings-chat
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: nigolc
ms.date: 2025-11-19T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: meetings
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
- Tier1
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- chat-teams-channels-revamp
- guest-access-external-collab
ms.localizationpriority: medium
description: For IT admins - Learn how to configure chat and meetings with people outside your organization who use Microsoft Entra ID, Microsoft Teams Essentials, or Skype.
locale: en-us
document_id: 59900927-5e5f-77a4-04be-e05a91330fca
document_version_independent_id: 1e4d6b87-f57c-fa45-1630-3c32b821d93c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/trusted-organizations-external-meetings-chat.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: trusted-organizations-external-meetings-chat
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/trusted-organizations-external-meetings-chat.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 737b733e-cd99-50b4-37bb-e5e47834ef89
---

# IT Admins - Manage external meetings and chat with people and organizations using Microsoft identities - Microsoft Teams | Microsoft Learn

With the *external access* feature in Teams, you can allow users in your organization to chat and meet with people outside the organization who are using Microsoft as an identity provider. You can configure external access with:

- Other Microsoft 365 organizations (chat and meetings)
- Teams users not managed by an organization (those users with a [Microsoft account](https://account.microsoft.com)) (chat only)
- Skype users (chat only)

Users in your organization can accept or block incoming chats from people outside the organization. For details, see [Accept or block people outside your org who send you a chat](https://support.microsoft.com/office/4b5b917d-895a-4379-a204-a111b2e24f41).

People from outside your organization don't have access to your teams, sites, or other Microsoft 365 resources. If you want them to have access to your teams and channels, see [Collaborate with guests in a team](/en-us/previous-versions/microsoft-365/solutions/collaborate-as-team) and [Collaborate with external participants in a shared channel](/en-us/microsoft-365/solutions/collaborate-teams-direct-connect).

Note

Your users can add apps when they host meetings or chats with people outside your organization. They can also use apps shared by external users when they join meetings or chats hosted externally. The data policies of the hosting user's organization, and the data sharing practices of any non-Microsoft apps shared by that user's organization, are applied. [Learn more about use of apps by people outside your organization](apps-external-users).

## Related settings

There are other settings in Teams—including guest access and anonymous access—that affect meetings with people outside your organization. For more information, see [Plan for meetings with external participants in Microsoft Teams](plan-meetings-external-participants) for more information.

The meeting lobby can control how people outside your organization join meetings. For more information, see [Control who can bypass the meeting lobby in Microsoft Teams](who-can-bypass-meeting-lobby) and [Configure the Microsoft Teams meeting lobby for sensitive meetings](configure-lobby-sensitive-meetings).

### Organization settings and user policies for external access

Each external access option has both an organization setting and user policies. The organization settings apply to your entire organization. User policies determine the users who can use the options you configured at the organization level.

Configure the organization settings to specify which types of external meetings and chat you want to allow. Then configure user policies for the users who should have access to these features. Both the organization settings and user policies are turned on by default.

For a user to use external access, both the organization setting and a user policy must allow it.

Use the procedures on the tabs in this article to configure organization settings and user policies.

# [Organization settings](#tab/organization-settings)
In this section, you can configure:

- Meetings and chat with trusted Microsoft 365 organizations
- Chat with external Teams users not managed by an organization
- Chat and calls with Skype users
- Block external users

You can also configure these settings by using PowerShell

### Specify trusted Microsoft 365 organizations

For meetings and chat with other Microsoft 365 organizations, you can specify which domains you want to trust. By default, all external domains are allowed. You can allow or block certain domains in order to define which organizations your organization trusts for external meetings and chat.

In order to chat and meet with people in external domains, the organizations that you trust must also trust your organization, and their users must be enabled for external access. If not, they can't chat with users in your organization and are considered anonymous when joining meetings hosted by your organization. [Learn more about meetings with other Microsoft 365 organizations](plan-meetings-external-participants#meetings-with-other-microsoft-365-organizations).

You can specify which domains are allowed or which domains are blocked. If you specify blocked domains, all other domains are allowed; if you specify allowed domains, all other domains are blocked. There are four scenarios for configuring trusted organizations:

- **Allow all external domains**: The default setting in Teams, and it lets users in your organization find, call, chat, and set up meetings with people external to your organization in any domain.

    In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business so long as the other organization also enabled external access.
- **Allow only specific external domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains. Once you set up a list of allowed domains, all other domains are blocked.
- **Block specific domains**: By adding domains to a **Block** list, you can communicate with all external domains *except* the domains you blocked. Once you set up a list of blocked domains, all other domains are allowed.
- **Block all external domains**: Prevents users in your organization from finding, calling, chatting, and setting up meetings with people external to your organization in any domain.

Note

People from blocked domains can still join meetings anonymously if anonymous access is allowed. To learn more, see [Manage anonymous participant access to Teams meetings](anonymous-users-in-meetings).

[![Screenshot of external domains settings.](media/external-access-domain-settings.png)](media/external-access-domain-settings.png#lightbox)

To allow specific domains, do the following steps:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Next to **Teams and Skype for Business users in external organizations**, choose **Allow only specific external domains**.
3. Select **Add external domains**.
4. In the **Domain** box, type the domain that you want to allow and then select **Done**.
5. If you want to allow another domain, enter in another domain.
6. Select **Done**.

To block specific domains, do the following steps:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Next to **Teams and Skype for Business users in external organizations**, choose **Block only specific external domains**.
3. Select **Block external domains**.
4. In the **Domain** box, type the domain that you want to allow and then select **Done**.
5. If you want to block another domain, enter in another domain.
6. Select **Done**.

By default, when you block domains, subdomains aren't blocked. For example, if you block contoso.com, marketing.contoso.com isn't blocked. If you want to block all subdomains, you can use the [Set-CsTenantFederationConfiguration](/en-us/powershell/module/teams/set-cstenantfederationconfiguration) PowerShell cmdlet with the `-BlockAllSubdomains` parameter. For example:

```powershell
Set-CsTenantFederationConfiguration -BlockAllSubdomains $True
```

#### Block federation with Teams trial-only tenants

You can control your organization's external access with Teams trial-only tenants (that don't have any purchased licenses), by using the `-ExternalAccessWithTrialTenants` setting in PowerShell (at least version 6.4.0 is required).

The default value for this setting is **Blocked**, but you can override it to **Allowed**, using the following command:

```powershell
Set-CsTenantFederationConfiguration -ExternalAccessWithTrialTenants "Allowed"
```

To block external communication with trial-only tenants, use the following command:

```powershell
Set-CsTenantFederationConfiguration -ExternalAccessWithTrialTenants "Blocked"
```

When set to **Blocked**, users from these trial-only tenants aren't able to search and contact your users via chats, Teams calls, and meetings (using the users' authenticated identities) and your users aren't able to reach users in these trial-only tenants. Users from the trial-only tenant are also removed from existing chats.

Users from trial-only tenants are blocked by default (with no option to override) from external communication with users in other Microsoft 365 cloud environments and with Microsoft Skype for Business server users. Two tenants with only trial subscriptions can federate with each other if the -ExternalAccessWithTrialTenants parameter value is Allowed by both tenants.

#### Diagnostic Tool

If you're an administrator, you can use the following diagnostic tool to validate if a Teams user can communicate with a Teams user in a trusted organization:

1. Select **Run Tests**, which populates the diagnostic in the Microsoft 365 admin center:
2. In the Run diagnostic pane, enter the **Session Initiation Protocol (SIP) Address** and the **Federated tenant's domain name**, and then select **Run Tests**.
3. The tests return the best next steps to address any setting or policy configurations that are preventing communication with the external Teams user.

#### Skype for Business Online

If you want chats and calls to arrive in the user's Skype for Business client, configure your users to be in any mode other than TeamsOnly. For more information, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability).

### Manage chats and meetings with external Teams users not managed by an organization

You can choose to enable or disable chats and meetings with external unmanaged Teams users (users not managed by an organization, such as Microsoft Teams (free)). If enabled, you can also control if people with unmanaged Teams accounts can start chats and meetings with users in your organization.

Note

Chats and meetings with external unmanaged Teams users isn't available in Microsoft 365 Government Community Cloud (GCC), GCC High, or DOD deployments, or in private cloud environments.

To allow chats and meetings with unmanaged Teams accounts:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Turn on the **People in my organization can communicate with unmanaged Teams accounts** setting.
3. If you want to allow external unmanaged Teams users to start the conversation, select the **External users with Teams accounts not managed by an organization can contact users in my organization** checkbox.
4. Select **Save**.

[![Screenshot of external accounts settings.](media/external-access-accounts-not-managed-by-org.png)](media/external-access-accounts-not-managed-by-org.png#lightbox)

If **External users with Teams accounts not managed by an organization can contact users in my organization** is turned off, unmanaged Teams users can't search by email address to find users in your organization. Users in your organization must initiate all communications with unmanaged Teams users.

To prevent chat with unmanaged Teams accounts:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Turn off the **People in my organization can communicate with unmanaged Teams accounts** setting.
3. Select **Save**.

### Manage chat and calls with Skype users

Follow these steps to let Teams users in your organization chat with and call Skype users. Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.

Meetings aren't supported with Skype users. If invited to a meeting, they're considered anonymous when joining.

Note

External communication with Skype users isn't available in GCC, GCC High, or DOD deployments, or in private cloud environments.

To configure chat and calls with Skype users:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Turn the **Allow users in my organization to communicate with Skype users** setting on or off.

    [![Screenshot of Skype users setting.](media/external-access-skype-settings.png)](media/external-access-skype-settings.png#lightbox)
3. Select **Save**.

To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop).

### Block external users

You can block specific external users from collaborating with your organization. If a user is added to the blocklist, your organization can't have 1:1 and group chats with these users. If chats already exist before a user is added to the blocklist, the blocked user is removed from the chat. This feature is turned off by default.

To enable and configure blocked users list, do the following steps:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Turn **Block specific users from communicating with people in my organization setting** on. ![A screenshot of the External Users page that shows the settings for this page.](media/trusted-organizations-external-meetings-chat/blockuser1.jpg)
3. Add users to the blocklist by selecting the **Block a user** button.
4. In the User box, type the email address of the user you want to block and then select the **Apply** button. Select the **Cancel** button to leave without taking any action. You must type in a valid individual email or a messaging resource identifier (MRI).

    ![A screenshot of the External Users page with the Block a user sidebar open on the right-hand side of the page.](media/trusted-organizations-external-meetings-chat/blockuser2.jpg)
5. If you want to block another user, select **Add users** and then the **Apply** button. A maximum of 200 users can be entered in this list.

    [![A screenshot of the External Users page with the Add users section displaying the emails of blocked users, and the Add users option available to add more emails.](media/trusted-organizations-external-meetings-chat/blockuser4.png)](media/trusted-organizations-external-meetings-chat/blockuser4.png#lightbox)

Administrators can configure blocked user settings using [Set-CsTeamsExternalAccessConfiguration](/en-us/powershell/module/microsoftteams/set-csteamsexternalaccessconfiguration) PowerShell cmdlet.

Note

Enabling the Blocked user functionality might generate two audit events - one for the admin setting, and another for any related roster changes that occur when users are blocked.

### Allow my security team to manage blocked domains

Note

This feature is currently in Public Preview and corresponds to Message center post MC1133508.

Microsoft Teams Administrators can let Security Administrators manage blocked external domains in the Microsoft Defender for Office security portal. This feature utilizes the Tenant Allow/Block List functionality specifically for Teams. When this feature is on, Security Administrators can view, add, remove blocked external domains. These actions are performed in Microsoft Defender portal and block incoming communications (including chats, meetings, and calls) from the specified domains.

To turn on this feature, do the following steps:

Teams admin center:

1. Sign in to the Teams Admin Center at [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com/).
2. In the left navigation, select **Users** &gt; **External Access**.
3. Turn on **Allow my security team to manage blocked domains**.

Microsoft Defender portal:

1. In the Microsoft Defender portal at https://security.microsoft.com, go to **Email & collaboration** &gt; **Policies & rules** &gt; **Threat Policies** &gt; **Rules** section &gt; **Tenant Allow/Block Lists**.
2. Select the **Teams domains** tab.
3. Add external domains as needed to block communications.

Prerequisites:

- Microsoft Defender for Office 265 Plan 1 or Plan 2.
- Teams external access tenant setting configured as one of the following options:
    - **Block only specific external domains**
    - **Allow all external domains**

The blocked domain lists in both the Teams admin center and Microsoft Defender security portal are the same.

### Configure organization settings by using PowerShell

Trusted organizations can be configured by using the [Set-CsTenantFederationConfiguration](/en-us/powershell/module/teams/set-cstenantfederationconfiguration) cmdlet.

The following table shows the cmdlet parameters used for configuring trusted organizations.

| Configuration | Parameter |
| --- | --- |
| Allow or prevent meetings and chat with other Teams organizations and Skype for Business | `-AllowFederatedUsers` |
| Specify allowed domains | `-AllowedDomains` |
| Specify blocked domains | `-BlockedDomains` |
| Block subdomains | `-BlockAllSubdomains` |

Chat with Teams users not managed by an organization and Skype users can be configured by using the [Set-CsTenantFederationConfiguration](/en-us/powershell/module/teams/set-cstenantfederationconfiguration) cmdlet.

The following table shows the cmdlet parameters used for configuring chat with Skype and unmanaged Teams users.

| Configuration | Parameter |
| --- | --- |
| Allow or prevent chat with Teams users that aren't managed by an organization | `-AllowTeamsConsumer` |
| Allow or prevent Teams users not managed by an organization starting conversations | `-AllowTeamsConsumerInbound` |
| Allow or prevent chat with Skype users | `-AllowPublicUsers` |

Before you can run these cmdlets, you must be connected to Microsoft Teams PowerShell. For more information, see [Manage Teams with Microsoft Teams PowerShell](/en-us/microsoftteams/teams-powershell-managing-teams).

# [User policies](#tab/user-policies)
If you enabled one of the external access settings for the organization, you can specify which users in your organization can chat or meet with people outside your organization by using an external access policy (both of these settings must be enabled for users to chat or meet with people outside your organization).

For meeting organizers who aren't enabled for external access, meeting attendees from other organizations are considered anonymous when joining their meetings.

Your organization's external access settings can override external access policies.

In this section, you can configure the following settings:

- External access policies in Teams admin center
- External access policies using PowerShell
- Granular domain in external access policies

### Configure external access policies in Teams admin center

You can manage your entire organization's external access settings by completing the following steps:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Select the **Policies** tab.
3. In the list of policies, select the **Org-wide default settings**.
4. Adjust the settings as you need.
5. Select **Save**.

If you want to create a custom policy, complete the following steps:

1. In the Teams admin center, go to **Users** &gt; **External access**.
2. Select the **Policies** tab.
3. Select **+ Add**.
4. Enter in a name and description for your policy.
5. Adjust the settings as you need.
6. Select **Save**.

[![A screenshot of the external access policy page in the Teams admin center.](media/external-access-policy-tac.png)](media/external-access-policy-tac.png#lightbox)

You can then assign this policy to specific users or groups. To learn how to assign and remove policies to users and groups, see [Assign policies to users and groups](assign-policies-users-and-groups).

### Configure external access policies using PowerShell

External access policies are configured by using [Set-CsExternalAccessPolicy](/en-us/powershell/module/teams/set-csexternalaccesspolicy) cmdlet.

The following table shows the cmdlet parameters used for configuring who can chat and meet with people outside your organization.

| Configuration | Parameter |
| --- | --- |
| Allow or prevent meetings and chat with other Teams organizations and Skype for Business | `-EnableFederationAccess` |
| Allow or prevent chat with Teams users that aren't managed by an organization | `-EnableTeamsConsumerAccess` |
| Allow or prevent Teams users not managed by an organization starting conversations | `-EnableTeamsConsumerInbound` |
| Allow or prevent chat with Skype users | `-EnablePublicCloudAccess` |

To limit external meetings and chat to specific users, you must:

- Turn off the control for the default org-wide policy.
- Create a new policy with the control turned on, and assign the appropriate users to it.

You can use the following example script, substituting *parameter* for the control you want to change, *PolicyName* for the name you want to give the policy, and *UserName* for each user for whom you want to enable/disable external access.

Be sure you installed the [Microsoft Teams PowerShell Module](/en-us/microsoftteams/teams-powershell-install) before running the script.

```powershell
Connect-MicrosoftTeams

# Disable external access globally
Set-CsExternalAccessPolicy -<parameter> $false

# Create a new external access policy
New-CsExternalAccessPolicy -Identity <PolicyName> -<parameter> $true

# Assign users to the policy
$users_ids = @("<UserName1>", "<UserName2>")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "<PolicyName>" -Identity $users_ids
```

The parameters for configuring external access are:

- EnableFederationAccess - controls chat and meetings with other Microsoft 365 organizations
- EnableTeamsConsumerAccess - controls chat with Teams users not managed by an organization

For example, to enable communications with external Teams users not managed by an organization:

```powershell
Connect-MicrosoftTeams

Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

New-CsExternalAccessPolicy -Identity ContosoExternalAccess -EnableTeamsConsumerAccess $true

$users_ids = @("MeganB@contoso.com", "AlexW@contoso.com")

New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "ContosoExternalAccess" -Identity $users_ids
```

You can see the new policy by running `Get-CsExternalAccessPolicy`.

See [New-CsBatchPolicyAssignmentOperation](/en-us/powershell/module/teams/new-csbatchpolicyassignmentoperation) for other examples of how to compile a user list.

### Configure granular domains in external access policies

External access policies give you granular control over external collaboration in Microsoft Teams. This feature allows you to create custom policies that define which external domains can be allowed or blocked for users and groups in your organization. Unlike organization settings that apply to everyone, these policies can either inherit the organization's domain list or define completely different domain lists for specific users and groups.

For a user to communicate with external domains, the following statements must be true:

- The organization-level **Manage external domains for this organization** setting must be turned on.
- A policy that allows/disallows the desired external domains must be assigned to the user or a group.
- The external organization must also allow federation with your organization.

Understanding which domain settings take effect:

- **Custom policy assigned to user**: The value for **Allow or block external domains** setting in the custom policy takes precedence over organization settings.
- **No custom policy assigned**: The user inherits the organization settings
- **Global (Org-wide default) policy**: Can't be modified; always set to **Use organization settings**.

The methods to manage domains in the external access policy are described in the following list:

- **Use organization settings**: Inherits the organization's global federation settings. This configuration is the default.
- **Allow all external domains**: Allows communication with any external domain without restrictions.
- **Allow only specific external domains**: Restricts communication to only the domains specified in the allowed list.
- **Block only specific external domains**: Prevents communication with domains listed in the blocked list while allowing all others.
- **Block all external domains**: Completely restricts external domain communication for assigned users.

When you use allowlists or blocklists in the policy, the entries are limited to 100 domains per each policy.

#### Configure granular federation in external access policies using Teams admin center

1. Sign in to the Teams Admin Center at [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com/).
2. In the left navigation, select **Users** &gt; **External access**.
3. Select the **Policies** tab.
4. Click to add a policy or modify an existing one.
5. Turn on **Manage external domains for this policy** to allow federation in the policy.
6. Select **Allow or block external domains** to configure how domains are managed in the policy.
7. Select **Save** to apply the changes.

#### Configure granular federation in external access policies using PowerShell

1. Before proceeding, verify that `AllowFederatedUsers` in [`TenantFederationConfiguration`](/en-us/powershell/module/microsoftteams/set-cstenantfederationconfiguration#-allowfederatedusers) tenant settings is set to `$True`. When this setting is disabled (`$False`), the granular domain controls defined in your policies don't work.

    ```powershell
    Connect-MicrosoftTeams
    
    Set-CsExternalAccessPolicy -EnableFederationAccess $True
    ```
2. Turn on the external domain management for the external access policy:

    ```powershell
    Connect-MicrosoftTeams
    
    Set-CsExternalAccessPolicy -EnableFederationAccess $True
    ```
3. Manage external organizations in this policy in one of the following ways (`CommunicationWithExternalOrgs`):

    - Use organization settings (`OrganizationDefault`): Inherits the organization's global federation settings (`TenantFederationConfiguration`). This configuration is the default.
    - Allow all external domains (`AllowAllExternalDomains`): Allows communication with any external domain without restrictions.
    - Allow specific external domains (`AllowSpecificExternalDomains`): Restricts communication to only the domains specified in the `AllowedExternalDomains` list.
    - Block specific external domains (`BlockSpecificExternalDomains`): Prevents communication with domains listed in the `BlockedExternalDomains` list while allowing all others.
    - Block all external domains: Completely restricts external domain communication for assigned users.

    When using `AllowSpecificExternalDomains` or `BlockSpecificExternalDomains` each policy is limited to a maximum of 100 domains per list (either allowed or blocked).

    For the Global (Org-wide default) policy, `CommunicationWithExternalOrgs` can only be set to `OrganizationDefault`.

    The following example allows Contoso and Fabrikam and blocks all other organizations:

    ```powershell
    Set-CsExternalAccessPolicy -Identity ExampleWithAllowedSpecificDomains -CommunicationWithExternalOrgs "AllowSpecificExternalDomains" -AllowedExternalDomains @("contoso.com", "fabrikam.com")
    ```

    The following example allows all domains:

    ```powershell
    Set-CsExternalAccessPolicy -Identity ExampleWithAllAllowedDomains -CommunicationWithExternalOrgs
    ```

    The following example creates a new policy where example1.com is blocked and all others are allowed:

    ```powershell
    New-CsExternalAccessPolicy -Identity BlockSpecificExample -CommunicationWithExternalOrgs "BlockSpecificExternalDomains" -BlockedExternalDomains @("example1.com")
    ```
4. Check that your settings are applied by running `Get-CsExternalAccessPolicy`.
5. [Assign the policy](/en-us/microsoftteams/assign-policies-users-and-groups) to users and groups. Keep in mind that users or groups assigned to the policy communicate with domains specified within the policy, and not domains defined at the organization settings.

The following table shows the cmdlet parameters used for configuring granular domains in external access policy.

| Configuration | Parameter |
| --- | --- |
| Manage external domains for this policy | `-EnableFederationAccess` |
| Domain management choice | `-CommunicationWithExternalOrgs` |
| List of blocked external domains | `-BlockedExternalDomains` |
| List of allowed external domains | `-AllowedExternalDomains` |

## Compliance and external access

See the following references to understand how external access works with compliance features in Microsoft 365.

- [eDiscovery in external access and guest environments](/en-us/microsoftteams/ediscovery-investigation#ediscovery-in-external-access-and-guest-environments)
- [Message retention with external access users](/en-us/microsoft-365/compliance/retention-policies-teams#messages-and-external-users)
- [Data loss prevention and Microsoft Teams](/en-us/microsoft-365/compliance/dlp-microsoft-teams)

---