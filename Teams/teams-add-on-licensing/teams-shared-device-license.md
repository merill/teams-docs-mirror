---
layout: Conceptual
title: Microsoft Teams Shared Space licensing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-add-on-licensing/teams-shared-device-license
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: altonk
manager: sohailta
ms. reviewer: benconlin, drewblundell
ms.date: 2026-07-08T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- tier1
audience: Admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
description: Learn about the Microsoft Teams Shared Space licensing for common area phones, Teams panels, and desk docks, as well as Shared Space - Single Space licensing for bookable desks and BYOD rooms
locale: en-us
document_id: f9a9a9e9-73ee-8b05-9086-3d4b3116eb4e
document_version_independent_id: f9a9a9e9-73ee-8b05-9086-3d4b3116eb4e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-add-on-licensing/teams-shared-device-license.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-add-on-licensing/teams-shared-device-license
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-add-on-licensing/teams-shared-device-license.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 44efe795-ac62-0a69-e0a9-7c4830907c37
---

# Microsoft Teams Shared Space licensing - Microsoft Teams | Microsoft Learn

Microsoft Teams supports hybrid work scenarios and enables users to work in flexible spaces. The **Microsoft Teams Shared Space** license designate certain devices including Teams Phone devices deployed in common areas, Teams panels, desk docks, and Android mobile phones as shared devices and license the extra software running on them with a shared use model. Prior to April 2026, this license was called **Microsoft Teams Shared Devices** license.

Aside from Teams devices, a single $8 Shared Space license can be used to enable 4 bookable desks or [bring your own device (BYOD) rooms](/en-us/microsoftteams/rooms/bring-your-own-device). When a Teams Shared Space license is provisioned for a bookable desk or BYOD room, the admin will see three additional $0 **Microsoft Teams Shared Space - Single Space** licenses that can be allocated to three additional bookable desks or BYOD rooms. For more information, see [Microsoft Places overview](/en-us/microsoft-365/places/places-overview).

## Use for BYOD rooms

The Teams Shared Space license includes [BYOD rooms](/en-us/microsoftteams/rooms/bring-your-own-device), such as focus or huddle rooms. Associating a Teams Shared Space license or Teams Shared Space – Single Space license to these room accounts enables valuable usage analytics in Teams Rooms Pro Management portal and Places Management Web app. These usage reports can help IT teams optimize BYOD rooms throughout the organization and gain valuable intelligence for planning and budgeting. Additionally, [autorelease can be enabled for BYOD rooms](/en-us/microsoft-365/places/enable-auto-release) to optimize utilization when no one checks in to a room reservation.

Customers who use a Teams Shared Space licensed device in a BYOD room, such as a Teams panel, are already granted access to autorelease capability and usage analytics for the BYOD room. No additional Shared Space - Single Space license is required.

## Use for bookable desks

In April 2026 individual desk booking changed from a per-user to a per-space licensing model. Instead of requiring a Teams Premium license for users to book a desk, either a Teams Shared Space or Teams Shared Space - Single Space license can be applied to an individual desk to make it bookable by any Teams user in the organization. IT admins can view usage analytics for bookable desks on the Teams Rooms Pro Management portal as well as the Places Management Web app.

## Use for Teams devices

Teams Shared Space license can be used for the following Teams device types:

· Teams Phone devices deployed in common areas

· Teams panels for BYOD rooms

· Desk dock for bookable desks

· Android mobile phones as shared devices

Note that each license enables one device. When a Teams Shared Space license is used for a device, you cannot use it to acquire additional Shared Space - Single Space licenses for BYOD rooms or bookable desks.

For information about other Teams add-on licenses, see [Microsoft Teams add-on licenses](/en-us/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

The **Microsoft Teams Shared Space** license includes the following service plans:

- Microsoft Teams Phone (Previously known as *Phone System*)
- Microsoft Intune P1
- Exchange Online Plan 2 (Cloud-based voicemail capabilities only)
- Specialty devices
- Managed Space

\*Teams Phone is *not* included in Microsoft Teams Shared Space – Single Space license; all other service plans are included.

Note

The **Exchange Online (Plan 2)** license is only to support cloud voicemail. Email and calendar aren't supported. If you don't want your Teams enabled shared device to have voicemail, you can deselect the Exchange Online (Plan 2) license or disable the user account's voicemail using the following Teams PowerShell command:

```
`Set-CsOnlineVoicemailUserSettings -Identity`` user1@contoso.com`` -VoicemailEnabled`` ``$false`
```

## Teams Shared Space license availability

The **Teams Shared Space** license is available to purchase worldwide to commercial, public sector, GCC, GCC High, and DoD tenants.

To purchase the **Teams Shared Space** license, you can choose your preferred purchasing channel: EA, EAS, EES, CSP, Web Direct, MCA - Customer led, and MCA - Partner led.

## Acquire Teams Shared Space licenses

Purchase the **Teams Shared Space** license in the [Microsoft admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), go to **Billing** &gt; **Purchase services**.
2. Find the **Purchase from Microsoft** section, and select **View products**.
3. Select the **Collaboration and communication** filter.
4. In the product list, find **Microsoft Teams Shared Space**, and select **Details**.
5. Enter the number of licenses you need and the billing frequency.
6. Select **Buy**.

Once a **Teams Shared Space** license is purchased, up to **3 Teams Shared Space - Single Space** licenses can be acquired at no additional cost in the Microsoft admin center. If you can’t find the Single Space license, make sure you’re using a **Microsoft Customer Agreement (MCA)** billing account (not a **Microsoft Online Services Agreement (MOSA)** billing account), because the Single Space license is only available for purchase with an MCA billing account. For information about billing account types, see [the article here](/en-us/microsoft-365/commerce/subscriptions/manage-self-service-purchases-admins?view=o365-worldwide#before-you-begin).