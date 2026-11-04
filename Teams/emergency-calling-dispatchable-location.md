---
layout: Conceptual
title: Emergency addresses for remote locations - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/emergency-calling-dispatchable-location
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-09-17T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Learn how Microsoft supports dispatchable location information to support emergency calling.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 961b5563-e3bd-cb77-e411-80958052e0d1
document_version_independent_id: 961b5563-e3bd-cb77-e411-80958052e0d1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/emergency-calling-dispatchable-location.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: emergency-calling-dispatchable-location
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/emergency-calling-dispatchable-location.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5fb1bf06-5d41-b518-9bd5-a708e928cf5e
---

# Emergency addresses for remote locations - Microsoft Teams | Microsoft Learn

This article describes Microsoft's support for 911 emergency calling location information in the United States. This support ensures that the most precise dispatchable location information possible is provided for Teams users making emergency calls. Regardless of the caller's location—onsite or working from home—a caller's location information sent to the Public Safety Answering Point (PSAP) must be accurate.

This article includes information about Microsoft's compliance with the RAY BAUM’S Act for Multi Line Telephone Systems (MLTS). The RAY BAUM'S Act extends the Kari’s Law requirements, which went into effect in early 2021. For more information about the RAY BAUM'S Act and Kari's Law, see [Dispatchable Location for 911 Calls](https://www.fcc.gov/911-dispatchable-location) and [Multi-line Telephone Systems – Kari’s Law and RAY BAUM’S Act 911 Direct Dialing, Notification, and Dispatchable Location Requirements](https://www.fcc.gov/mlts-911-requirements).

This article is for administrators and IT professionals. It describes how you can configure user policies so that the users in your organization can set their own emergency addresses if applicable. For information about how your users can enable location services, see [Manage location sharing in Microsoft Teams](https://support.microsoft.com/teams/notifications-settings/manage-location-sharing-in-microsoft-teams).

Various device management applications can also enable location sharing. Enabling location sharing to Teams varies by operating systems.

Although this information applies to emergency 911 calling in the United States, user-entered locations are conveyed to the screening center in Canada as well.

This article contains the following sections:

- Support for emergency calling location information
- Location precedence
- Emergency address classification and routing
- Enable end users to configure their emergency address
- Notes and restrictions

## Support for emergency calling location information

To support these requirements, Teams uses the location services provided by the respective operating system to suggest an address--if granted permission by the administrator or user. The end user can confirm the location of a suggested address, edit it, or manually enter a new one. A confirmed, edited, or manually entered address is then saved on the Teams client so that the user-confirmed address is automatically used when the client is connected to that network. The user-saved addresses are automatically cleared when the Teams client is signed out.

## Location precedence

Emergency addresses for Teams can be categorized by different types. The following list shows the location precedence used when an emergency number is dialed:

1. A dynamically acquired address defined by the tenant administer in the Location Information Service.
2. An address the end user confirmed or edited which is associated to the local network the Teams client is connected to.
3. An address automatically suggested by the operating system.
4. An address the end user manually entered without service resolution.
5. An address the administrator statically associates to the phone number assigned to the user.

## Emergency address classification and routing

The following table shows the types of emergency addresses and associated routing methods for each type: whether the call is automatically routed to the serving PSAP or screened for accuracy before transferring to the serving PSAP. This routing behavior is supported in the United States for all Calling Plan users, Operator Connect partners, and Direct Routing certified emergency calling service providers.

| Type of emergency address | Emergency routing method |
| --- | --- |
| Dynamically acquired emergency address defined by administrator. | Direct to PSAP. |
| Emergency address obtained from the operating system **without confirmation for accuracy** by the user. | Screened and Transferred to PSAP. |
| Emergency address obtained from the operating system **with confirmation for accuracy** by the user. | Direct to PSAP. |
| Emergency address obtained from the operating system and edited through address autosuggest. | Direct to PSAP. |
| Emergency address obtained from the operating system and manually edited and confirmed by the user. | Screened and Transferred to PSAP. |
| Emergency address entered manually and confirmed by the user. | Screened and Transferred to PSAP. |
| Emergency address entered through address autosuggest and confirmed by the user. | Direct to PSAP. |
| Emergency address statically assigned to a Common Area Phone or Microsoft Teams Room. | Direct to PSAP. |
| Emergency address statically assigned to the user/number. | Screened and Transferred to PSAP. |
| Null | Screened and Transferred to PSAP. |

## Enable end users to configure their emergency address

### Using the Microsoft Teams admin center

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Emergency policies**.
2. Select **Add**.
3. Enter a name for the emergency calling policy, for example, "E911WFH".
4. Turn on **External location lookup mode**.
5. Select **Save**.

#### Assign a custom emergency calling policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

### Using PowerShell

To enable this feature for your end users, use the [New-CsTeamsEmergencyCallingPolicy](/en-us/powershell/module/microsoftteams/new-csteamsemergencycallingpolicy) PowerShell cmdlet, and set the `ExternalLocationLookupMode` parameter to `Enabled`. See the following example:

```PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

After you enable this feature for your end users, the user can add, edit, or confirm an emergency address on the **Calls** tab and display the address after it's set. For more information about how end users can set location services, see [Manage location sharing in Microsoft Teams](https://support.microsoft.com/teams/notifications-settings/manage-location-sharing-in-microsoft-teams).

On Windows, you can manage the Windows location service and whether applications have access to the location by using group policy or by using [mobile device management (MDM)](/en-us/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation).

For more information about Windows location service, see [Windows location service and privacy](https://support.microsoft.com/windows/privacy/windows-location-service-and-privacy).

## Notes and restrictions

Keep the following in mind:

- The work-from-home experience described is for Teams desktop on Windows and Mac.
- Teams phones don't support the work-from-home experience.
- Teams mobile supports automatic location detection but not the user entered experience.
- Privacy settings can conflict with automatic location detection - Mobile Device Management systems can be used.