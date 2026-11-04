---
layout: Conceptual
title: Plan for immersive events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/immersive-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Immersive events in Teams
author: Sean-Kerawala
ms.author: sekerawa
manager: tyadams
ms.collection:
- M365-collaboration
- m365initiative-meetings
ms.service: msteams
ms.custom: intro-overview
ms.topic: concept-article
ms.date: 2026-10-09T00:00:00.0000000Z
ms.subservice: teams-events
locale: en-us
document_id: fa9610ca-31ec-0f91-07e0-6b57becc9668
document_version_independent_id: fa9610ca-31ec-0f91-07e0-6b57becc9668
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/immersive-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: immersive-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/immersive-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fb8d0947-59e7-0cd3-e1d4-81772eb0b016
---

# Plan for immersive events - Microsoft Teams | Microsoft Learn

Important

Immersive events will retire on April 2, 2027. Immersive events will remain available and supported until that date, including security updates and necessary fixes. More information will be shared as it becomes available.

Note

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](teams-add-on-licensing/licensing-enhance-teams).

Teams Immersive lets your users create, customize, and host immersive 3D events in Microsoft Teams. With Teams Immersive, users can:

- Schedule Teams Immersive events from Teams calendar
- Join an immersive event directly through the Teams app on PC and Mac, or on a Meta Quest 3 device.
- Design 3D spaces and schedule immersive events for PC or Mac – no code or technical expertise required.

Note

This feature is now Generally Available for Teams users on PC, Mac, and Meta Quest devices.

This page for admins covers the required tasks and suggests functional roles that you might need to know about the rollout. You should follow your organization's standard rollout process, including change and configuration management. The following steps are outlined in this article:

1. Prepare your organization
2. Review minimum hardware requirements
3. License requirements
4. Configure endpoints and firewalls
5. Check your bandwidth requirements
6. Work with stakeholders to communicate change
7. (optional) Allow guests to join immersive events
8. (optional) Assign event policies to turn off Immersive events for users and groups
9. (optional) Get early access to immersive events features
10. (optional) Deploying Meta Quest devices for using the Microsoft Teams Immersive app

For details on the Teams Immersive events experience for your users, see [Get started with immersive events in Microsoft Teams](https://support.microsoft.com/topic/a69189df-39c7-478f-a335-0aef7c4e5781).

## Prepare your organization

Executive-level sponsorship is highly advisable to help with any cross-team blocking issues.

You need access to a few administration tools:

- Microsoft 365 admin center to manage and assign Teams licenses.
- (optional) Purview admin center to create sensitivity labels.

In addition, ensure all organizers and attendees of immersive events have access to SharePoint and OneDrive. Event customizations often reference files such as images, videos, audio, or 3D models that are stored in Microsoft 365. Creating Microsoft 365 Groups can be a helpful way to enable secure content sharing.

## Hardware requirements

PC and Mac minimum hardware requirements are 4-core CPU & 8-GB RAM.

## License requirements

Organizers, co-organizers, and attendees must have a commercial Teams license, such as **Microsoft Teams Enterprise** or **any Microsoft 365/Office 365 plan that includes Teams** (Business Basic, Business Standard, Business Premium, Microsoft 365 E3/E5, or Office 365 E1/E3/E5).

Note

Immersive events aren't supported in GCC, GCCH, sovereign clouds, or EDU environments.

### Prerequisites

Admins must have access as a [Global Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference) or [Billing Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference) to assign Teams licenses.

## Firewall and endpoint requirements

In general, the standard set of Microsoft 365 requirements outlined in [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&amp;preserve-view=true) applies to all Teams Immersive event features. The endpoints and firewall settings for immersive events align with standard Microsoft 365 and Teams requirements, as they enable core services like authentication, data exchange, and API access across the Microsoft cloud. Configure your enterprise firewall settings to align with the standard set of Microsoft 365 requirements for **Microsoft Teams**, and **Microsoft 365 Common** outlined in [Microsoft 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&amp;preserve-view=true).

Ensure that you configure your firewall to enable traffic to \*.cloud.microsoft.com, \*.office.com, \*.graph.microsoft.com, \*.substrate.office.com, and \*.microsoft.com over TCP 443, 80.

Teams Immersive also requires the IP addresses and port ranges detailed in [Firewall configuration for Azure Communication Services](/en-us/azure/communication-services/concepts/voice-video-calling/network-requirements) for media capabilities such as audio and screen sharing. Without access to these endpoints, immersive events might not work properly for users in your organization.

## Bandwidth requirements

The following network bandwidth requirements are designed to help users in your organization have the best possible experience with Teams immersive events.

We’re continually improving immersive events for low-bandwidth conditions, but if users experience poor audio, dropouts, or jerky avatar movement, consider optimizing your network.

Teams immersive experiences build on top of [Microsoft Teams network bandwidth requirements](/en-us/microsoftteams/prepare-network) for capabilities (such as video and screen share), with extra bandwidth needed for immersive capabilities (such as avatar movement and spatial audio).

### Immersive participants

- Minimum (kbps): 30/370
- Recommended (kbps): 80/700
- Best performance (kbps): 100/850

As an example, an immersive event with a participant sharing screen requires a minimum of 440-kbps downstream, and 830-kbps upstream, and a maximum of 8,176-kbps downstream and 8,926-kbps upstream.

## Work with stakeholders that communicate change

The stakeholders listed above all have active steps, which affect the setup of your Teams Immersive roll out. However, the deployment might also affect other parts of your organization, or there could be policies and guidelines that should be considered early in the planning process. Here are some areas of your organization you might need to reach out to before you deploy.

- Change Communications: If you have a standard process for contacting users about pending changes, make sure Teams Immersive is part of those communications.
- Help Desk: Have a support plan in place for users who experience issues using Teams Immersive. Make sure your admins have a way to review issues experienced by users so they can be communicated to Microsoft as needed.
- Human Resources: While Teams Immersive doesn't require any specific action from Human Resources for deployment or operations, HR might be interested that immersive events are about creating 3D experiences for users. Check with your HR department for any policies that might affect your immersive event experience.
- Company Branding: If you decide to create custom event experiences for your users, you should check with your company branding experts to make sure any meeting assets meets branding standards.

## Allow guests to join immersive events

Teams Immersive events are joinable by users within your organization and guests.

Some organizations might have trusted individuals they want to invite to their immersive event.

To add a guest, follow the [step-by-step guidance](https://support.microsoft.com/office/add-guests-to-a-team-in-microsoft-teams-fccb4fa6-f864-4508-bdde-256e7384a14f) for adding trusted guests to your tenant via Microsoft 365 admin center.

Note

Guests can be invited as attendees. Guests can't be organizers or co-organizers of immersive events. External (cross-tenant) and anonymous users aren't currently supported.

## Manage who can schedule immersive events through Teams admin center or PowerShell

You can use Teams admin center or PowerShell to manage who can schedule immersive events in your organization. To manage who can schedule immersive events:

- Via Teams admin center: Navigate to Event Policies, create a new policy, specify the users and groups to apply the policy to, then toggle "Immersive events" on or off.
- Via PowerShell: Use the **`-ImmersiveEvents`** parameter within the PowerShell **[CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy)** cmdlet.

### Turn off immersive events

To prevent organizers with this policy from creating immersive, use the following script:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -ImmersiveEvents Disabled
```

### Turn on immersive events

To allow organizers with this policy to create immersive events, use the following script:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -ImmersiveEvents Enabled
```

To learn more about **`-ImmersiveEvents`** policies in PowerShell, see [Set-CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy).

## Platform support

- Immersive events in Teams is available only on PC and MAC, not on web.
- Users can still schedule on web, but to join the immersive event, they must use a PC/MAC.
- Quest isn't yet supported for Immersive events

## Endpoint availability

- Supported: Teams app on PC and Mac (\*app on Meta Quest headset coming soon)
- Not supported: Teams on Web, Teams on Mobile, VDI (Virtual Machine) support, Microsoft Teams Rooms, Dial-In

## User type support

- Supported: Users in your organization (same tenant) and guest users
- Not supported: Cross-tenant (external) and anonymous users

## Known limitations

- Scheduling meetings from Quest isn't supported.
- Joining an event too early (10+ mins) can show 'Meeting not found' error.
- Event customization must be done in Teams, not on Quest.
- Customization sessions expire 8 hours after last join.
- Immersive templates can't be saved for reuse across events (coming soon).
- In an immersive customization session, there's no way to play a video or audio for preview. Video and audio objects can only be played during the live event.
- Users stuck in Lobby see the standard Teams prejoin screen.
- Screen share doesn’t include content audio (Workaround: use a video object for presentations)
- Magnifier doesn't display screen share content.
- Chat is unavailable on Quest devices.
- Selfie capture isn't supported on Quest.
- Guest users can't join immersive events on Quest.
- Quest users can’t see their own reactions or emojis (others still can).
- Passkey-based sign-in isn't supported on Quest (Workaround: Use 2FA or mobile-based authentication).
- Dial-in info might appear for immersive events, but calling the number doesn't allow event join.

## Get early access to immersive events features

To get early access to features in Immersive Events in Microsoft Teams, both organizers and attendees must be on the Public Preview build. Without Public Preview, users can only access Generally Available features and can't receive early access to new features.

### Steps for your users to join Public Preview

1. Your users can send you a request to join the Public Preview program. To allow them to join, you must first set up a **Teams Update policy**. To learn more about managing the Update policy, see [Public preview in Microsoft Teams](public-preview-doc-updates#set-the-update-policy).
2. Once you set the **Teams Update policy**, users can open the Teams app and select **Settings and more (...)** next to their user profile.
3. Select **Settings** &gt; **About Teams**.
4. Under **Early access**, select the **Public preview** checkbox.
5. On their PC or Mac, select **Calendar**, toggle **New Calendar** to **Off**.
6. Now, they can join or customize an event via Teams desktop on PC or Mac.

## Deploying Meta Quest devices for using the Microsoft Teams Immersive app

Important

Conditional Access policies should be modified by someone in your organization with a strong understanding of the implications of the changes. Consult your security team or other expert in your company security policies before making any changes.

**Immersive events support device-level conditional access policies for managed Quest devices through native authentication.** Conditional access is a cornerstone of zero-trust security, ensuring only compliant devices can access corporate resources. Organizations typically enforce these policies using **Microsoft Entra** (identity) and **Microsoft Intune** (device management) to validate device type, OS version, and configuration before granting access.

With native authentication for Microsoft Teams Immersive app on Quest, enterprises can pair **Meta Horizon managed services** (formerly Quest for Business) with Intune to manage device profiles, apply conditional access, and enforce compliance. This integration enables Quest devices to participate securely in immersive events while adhering to organizational policies.

To achieve this goal, companies must collaborate with their **security and endpoint management teams** to configure Quest devices according to enterprise standards. For best results, centrally manage the Quest fleet using **Intune as the MDM provider** and **Entra as the identity provider** via **Meta Admin Center**, ensuring a secure, compliant experience for all end users.

### Managed Quest devices and Conditional Access

If your organization chooses to manage Quest devices, you need to ensure the following components are in place:

- **Meta Horizon managed services** (formerly Quest for Business) for device enrollment and management.
- **Microsoft Intune** as the Mobile Device Management (MDM) provider for enforcing compliance and applying device-based policies.
- **Microsoft Entra ID** as the identity provider for authentication and conditional access. \*Alternatively, you can use your preferred identity and MDM provider.

Learn more and get started with Horizon managed services in the Meta for Work Help Center, [here](https://work.meta.com/help/258897560520071/?helpref=hc_fnav).

For those getting started with Quest enrollment, check out the Microsoft Intune [enrollment guide](/en-us/mem/intune/fundamentals/deployment-guide-enrollment).

#### Conditional Access for Teams Immersive on Quest

Once devices are enrolled and configured, create a [device-based Conditional Access policy](/en-us/mem/intune/protect/create-conditional-access-intune) to enforce sign-in conditions specific to your organization’s risk profile and usage scenarios.

Important

- **App protection policies (MAM)** are **not supported** for Quest devices. Device-level Conditional Access policies are supported for managed Quest devices.
- Organizations might need to **exclude app protection policies** targeting Graph and SharePoint to allow successful sign-in. We suggest testing sign-in before turning anything off.
- If enforcing **Phishing-Resistant MFA (PRMFA)**, exclude this requirement for Quest devices to avoid sign-in failures, as Meta Quest doesn't currently support Passkey or certificate-based authentication methods.

### Making exceptions for Quest devices

If your organization wants to allow Quest devices under specific conditions:

- Create a Conditional Access policy that aligns with your company’s risk tolerance while permitting Quest access.
- In **Intune admin center**, configure the following:

    - **Exclude Quest devices** by [filtering for device](/en-us/entra/identity/conditional-access/concept-condition-filters-for-devices) attributes (for example, model, manufacturer) in Conditional Access policies.
    - **Exclude the Teams Immersive app** from any [Android app protection policies](/en-us/mem/intune/apps/app-protection-policies).

Both options enable the use of immersive events. However, as stated earlier, it's recommended that organizations manage their Quest devices to ensure security and compliance. If neither action is taken and a user in your organization attempts to launch Microsoft Teams Immersive on Quest for an unmanaged device where conditional access policies are applied, they'll receive sign-in errors (examples include [AADSTS50199](/en-us/entra/identity-platform/reference-error-codes) and/or [AADSTS53003](/en-us/entra/identity-platform/reference-error-codes)).

For more information about Conditional Access, see:

- [Common ways to use Conditional Access with Intune](/en-us/mem/intune/protect/conditional-access-intune-common-ways-use)
- [How can I manage Quest VR headsets for my organization?](/en-us/mesh/resources/mesh-troubleshooting)