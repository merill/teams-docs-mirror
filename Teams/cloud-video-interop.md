---
layout: Conceptual
title: Manage and set up Cloud Video Interop for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/cloud-video-interop
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: meetings
audience: admin
search.appverid: MET150
ms.reviewer: adam.jacobs
ms.date: 2026-09-22T00:00:00.0000000Z
f1.keywords:
- NOCSH
description: Use Cloud Video Interop(CVI) as an intermediate solution to allow third-party meeting room devices to join Microsoft Teams meetings and events. This article explains how you can plan and set up Cloud Video Interop(CVI) for users in your organization and has release notes. Presenters can join and present in Teams events using their own Video Teleconferencing (VTC) devices, even if they're not Teams Rooms devices. Organizers can share CVI join codes directly from the event's share event dialog with presenters.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
- Tier1
- m365initiative-meetings
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
locale: en-us
document_id: b092db56-a877-6c2f-b2e5-87dbccf35a90
document_version_independent_id: 32dcfd3e-c8d6-94e8-8114-5ae83fc36a53
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/cloud-video-interop.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: cloud-video-interop
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/cloud-video-interop.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fbc8377a-914b-488f-3619-9934c2947a55
---

# Manage and set up Cloud Video Interop for Microsoft Teams - Microsoft Teams | Microsoft Learn

Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party SIP and H.323 video room devices (VTCs) to join Microsoft Teams meetings. As an admin, you can manage CVI for your organization.

With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing. This collaboration can be enjoyed through the desktop and web client, and through many partner devices that integrate natively with Microsoft Teams. However, many customers are already invested in video communication devices, which can be expensive to upgrade. CVI provides an easy solution, which allows you to keep using your existing solutions until you're ready to upgrade.

With CVI, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.

## Is CVI for me?

CVI uses Teams endpoints to provide an intermediate service while you transition to a full native Microsoft Teams Solution. The service provided should be part of your migration path.

CVI is intended for customers who meet the following criteria:

- Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that aren't qualified for direct integration with Microsoft Teams.
- Are supported by one of our CVI partners.
- Want to retain the value of their investment in their current meeting room devices and personal video devices while transitioning to a Microsoft Teams solution.

While CVI provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Rooms Systems, for the long term.

### Office 365 US Government and third-party services

Office 365 allows you to integrate third-party apps into SharePoint sites, Skype for Business, Teams, Office apps included in Microsoft 365 Apps for enterprise (such as Word, Excel, PowerPoint, and Outlook), and Outlook Web App. In addition, Office 365 supports integration with third-party service providers. These third-party apps and services might involve storing, transmitting, and processing your organization's customer data on third-party systems. The Office 365 compliance and data protection commitments don't cover third-party systems outside of the Office 365 infrastructure. **You should review the privacy and compliance statements from the third parties when assessing the appropriate use of these services for your organization.**

Note

The Pexip Teams Connector must be hosted in the Arizona or Texas Azure regions for GCC High. The Virginia Azure region doesn't support the hosting of the Pexip Teams Connector for GCC High.

## CVI overview

Our partners offer CVI, a third-party service that provides interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.

The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.

The following diagram shows the high-level architecture of our partner solutions.

![Diagram describing a Teams CVI partner solution.](media/teams-cloud-video-interop-partner-solution.png)

### Partners certified for Microsoft Teams

The following partners have video interop solutions for Microsoft Teams. Your company might choose to work with any combination of these partners within your enterprise and choose the best support plan these partners offer for their CVI solution.

Warning

Only the CVI partners listed in the following table are certified by Microsoft for video interoperability within Teams meetings. Microsoft doesn't support granting other third parties with Graph API permissions that provide similar capabilities.

| Partner | Partner solution |
| --- | --- |
| ![The logo representing Pexip Infinity.](media/pexip.png) | [Pexip Infinity for Microsoft Teams](https://aka.ms/PexipInfinity) |
| ![The logo representing Cisco CVI.](media/cisco.png) | [Cisco Webex Video Integration for Microsoft Teams](https://aka.ms/CiscoCVI) |
| ![The logo representing HP Poly CloudConnect.](media/hppoly.png) | [Poly CloudConnect powered by Pexip](https://aka.ms/PolyCloudConnect) |

## Deploy CVI

When deploying a CVI solution, it's important to understand that you're deploying a partner solution. You need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization. The general steps you should take to deploy CVI are listed in the following diagram.

![Diagram describing deploying CVI in your organization, which is outlined in the following steps.](media/deploying-cvi.png)

### 1. Plan

Follow these steps to plan for your deployment:

1. **Pick a deployment model/hosted model for your use**- During the plan phase, you should identify the devices that you aren't replacing with a native Teams device, and find a CVI partner that can support these devices.
2. **Select the license plan ideal for your organization**- You need a license for each user who schedules meetings in which you want a CVI-enabled device to join. You can get the exact licensing requirements from your CVI partner. Licensing must be clear before you start your deployment.
3. **If you're self-hosting your video interop infrastructure, plan for capacity of VMs.**

### 2. Configure

To configure CVI, follow these steps.

1. **Obtain configuration info from your chosen partners (tenant key, appIds...)**- You can use one or more video interop partners in your organization. The partner that you chose for your CVI deployment provides you with a full deployment document that consists of all the steps needed to deploy successfully within your organization. This document includes firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.
2. **Ensure that your network is configured correctly**- Configure your standards-based video firewall for perimeter network traversal to support. For example:

    - Cisco VCS-e
    - Polycom RPAD
3. **Configure integrated rooms with exchange and OTD**- In most cases, extra relay would need to be set up and configured in your environment.

### 3. Provision

During the provision phase, you assign licenses to the appropriate users according to the partner configuration guide. You must go through the Azure Consent process to provide the partner access to your Teams environment. For more information about the Azure consent process, see [Permissions and consent in the Microsoft identity platform endpoint](/en-us/azure/active-directory/develop/v2-permissions-and-consent).

The tenant key is the dial out to the partner service. In the following example, 'teams@rtcdevices.com' is the tenant key.

[![Example of the tenant key.](media/cvi-ui-small.png)](media/cvi-ui-expand.png#lightbox)

To learn about PowerShell cmdlets you can use, see the PowerShell for CVI section in this article.

#### 3.1. Consent

You must provide permission consent for the video teleconferencing devices (VTCs) to join your organization's meetings via the partner service. Your partner provides the consent link.

| Name | Application Permission Short Description | Description |
| --- | --- | --- |
| Calls.JoinGroupCall.All | Join Group Calls and Meetings as an app | Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user. The app is joined with the privileges of a directory user to meetings in your tenant. |
| Calls.JoinGroupCallasGuest.All | Join Group Calls and Meetings as a guest | Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user. The app is joined as a guest to meetings in your tenant. |
| Calls.AccessMedia.All | Access media streams in a call as an app | Allows the app to get direct access to media streams in a call, without a signed-in user. |
| OnlineMeetings.Read.All | Read Online Meeting details | Allows the app to read Online Meeting details in your organization, without a signed-in user. |

### 4. Schedule

After you enable CVI for a user, any Teams meeting they schedule through the Teams Meeting Add-in for Outlook, Teams Client, or OWA include necessary details for compatible devices to join.

Next, schedule Teams meeting with video interop coordinates. The enabled user can schedule teams meetings via:

- [Teams Meeting add-in for Outlook](outlook-add-in-authentication-policy-requirements)
- [Teams client desktop and mobile](teams-client-desktop-admin)

### 5. Join

Depending on the partner solution, there are several ways to join a CVI-enabled meeting. Your CVI partner provides exact meeting join scenarios. Here are a few example scenarios:

- **IVR (Interactive Voice Response)**

    - You can dial in to the partner's IVR using the tenantkey@domain.
    - When you're in the partner IVR, you're prompted to enter the VTC conferenceId, which connects you to the Teams meeting.
- **Direct dial**

    - You can directly dial in to the Teams meeting without interacting with the partner's IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.
- **One-touch dial**

    - If you integrated the VTC room calendar, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).

## SIP Guest Join

SIP Guest Join (SGJ) is a new CVI capability, offered by select certified CVI partners. It allows organizations to use their existing CVI subscriptions to join meetings hosted by external organizations—something that was previously not possible due to the following limitations:

1. The CVI partner application wasn't located or consented to within the external organization
2. The Teams meeting initiation wouldn't contain CVI join coordinates

Due to the absence of CVI join coordinates within the external organization's Teams meeting invitations, you need to configure One Touch Join calendaring for VTCs enabled for SGJ. Once the CVI partner calendaring solution parses the Teams meeting invitation, their respective services join the external meeting as a guest. **There is no lobby bypass capability for SGJ-enabled meetings**.

\*Refer to CVI release notes for partners offering SGJ.

## Manage CVI

After CVI is deployed, you can manage the devices using our partners' solutions. Each partner provides you with an administrative interface that includes both license and device management.

Reporting is also available directly from the partner administrative interface. For more information on reporting capabilities, contact the partner of your choice.

### Troubleshoot CVI

CVI is a partner-provided service. If you're experiencing issues, the first step is to connect a device that has the Teams Client installed. Next, connect it to the same segment as the CVI device that's causing problems.

If Teams functions correctly on this segment, and you followed all the networking and configuration guidelines your partner provided, you should contact the partner for further troubleshooting.

## CVI in Teams events

Note

In Teams events, this feature is available only in events [optimized for large audiences](/en-us/microsoftteams/plan-events).

Presenters can join and present in Teams events optimized for large audiences using their own Video Teleconferencing (VTC) devices, even if they're not Teams Rooms devices. Organizers can share CVI join codes directly from the share event dialog with presenters. When a trusted CVI device uses the join code, it enters the event as an attendee, gets promoted to a presenter, and then moves to the green room or live session. These presenters can also collaborate in the green room before the event begins and use all supported features like private event chat.

Organizers can access and share event CVI coordinates by following these steps:

### New calendar

1. Select **Calendar** in Teams.
2. Select an upcoming event.
3. Select **Edit**.
4. Select **Share event**.
5. Under **Joining details for organizer, co-organizer and presenter**, select **Copy**.
6. Share the copied details with co-organizers and presenters separately through chat or email.

### Classic calendar

1. Select **Calendar** in Teams.
2. Right-click or open the context menu on an upcoming event.
3. Select **Manage event**.
4. Select **Share event**.
5. Under **Joining details for organizer, co-organizer and presenter**, select **Copy**.
6. Share the copied details with required organizers, co-organizers, and presenters separately over chat or email.

## PowerShell for CVI

The following PowerShell cmdlets are available for you to (partially) automate the CVI deployment.

- [**Get-CsTeamsVideoInteropServicePolicy**](/en-us/powershell/module/teams/get-csteamsvideointeropservicepolicy): Microsoft provides preconstructed policies for each of our supported partners that allow you to designate which partners to use for CVI.This cmdlet allows you to identify the preconstructed policies that you can use in your organization. You can assign this policy to one or more of your users by using the Grant-CsTeamsVideoInteropServicePolicy cmdlet.
- [**Grant-CsTeamsVideoInteropServicePolicy**](/en-us/powershell/module/teams/grant-csteamsvideointeropservicepolicy): This cmdlet allows you to assign a preconstructed policy for use in your organization or assign the policy to specific users.
- [**New-CsVideoInteropServiceProvider**](/en-us/powershell/module/teams/new-csvideointeropserviceprovider): Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.
- [**Set-CsVideoInteropServiceProvider**](/en-us/powershell/module/teams/set-csvideointeropserviceprovider): Use this cmdlet to update information about a supported CVI partner that your organization uses.
- [**Get-CsVideoInteropServiceProvider**](/en-us/powershell/module/teams/get-csvideointeropserviceprovider): Use this cmdlet to get all of the providers that you configured for use within the organization.
- [**Remove-CsVideoInteropServiceProvider**](/en-us/powershell/module/teams/remove-csvideointeropserviceprovider): Use this cmdlet to remove all provider information about a provider that your organization no longer uses.

## CVI Release Notes

Microsoft continues to work with CVI partners to make meetings between Microsoft Teams and other services more seamless for users. The table below details which features are available or planned.

| Release Date | Feature Name | Feature Description | Microsoft Status | Cisco | Pexip |
| --- | --- | --- | --- | --- | --- |
| CY22Q3 | PowerPoint Notifications | CVI participants are notified when PowerPoint is being shared via Teams participants | Delivered to CVI Partners | Available | Available |
| CY22Q4 | CVI Telemetry | Enable identification of CVI calls within Call Quality Dashboard (CQD) metrics | Delivered to CVI Partners | Available | TBD |
| CY22Q4 | Alignment of lobby between CVI and Teams meetings | Alignment of CVI Lobby with Teams Meeting Scheduling, specifically: "People who were invited" and "Only me and co-organizers," now ensures VTC is held in lobby even when VTC lobby bypass is configured. **Note:***as a result of this change, VTCs (used within Teams live events as a presenter) must be admitted via the lobby* | Delivered to CVI Partners | Available | Available |
| CY22Q4 | Support for Long Term Reference Frame (LTRF) | Improved support for video packet loss recovery within CVI | Delivered to CVI Partners | TBD | TBD |
| CY23Q1 | Support for Microsoft Teams Premium, "Watermark Feature" | Watermark support, CVI Partners will create Watermark overlay with both video and content displayed. **Note:***at this time Teams meetings only support Watermark for trusted VTCs, i.e., Lobby Bypass must be enabled* | Delivered to CVI Partners | Available | Available |
| CY23Q2 | SIP Guest Join | The ability to join Teams Meetings with VTCs when CVI coordinates aren't present within the invite | Delivered to CVI Partners | Available | Available |
| CY23Q3 | SIP and H.323 Calling with Teams Rooms | Teams Rooms Pro calling feature, which creates the ability to perform bi-directional calling between Teams Rooms on Windows and VTC devices | Delivered to CVI Partners | TBD | [Available](https://azuremarketplace.microsoft.com/marketplace/apps/pexip.pexip_teams_room_sip_calling?tab=Overview) |
| CY24Q2 | Support for Microsoft Teams video retransmission (RTX) | Microsoft Teams now supports video retransmission or RTX. This video packet loss mechanism provides more media resiliency for Teams call legs | Delivered to CVI Partners | Available | Available |
| CY25Q2 | CVI Support for Teams town halls | Presenters can join and present in Teams town halls using their own Video Teleconferencing (VTC) devices | Delivered to CVI Partners | Available | Available |
| CY25Q3 | CVI Support for PowerPoint live | VTCs are now able to see still content snapshots when Teams participants are presenting PowerPoint live in Teams meetings | Delivered to CVI Partners | Available | Available |
| CY26Q3 | Teams Meeting add-in for Google Calendar | The official Microsoft Teams add-in for Google Calendar now supports CVI and provides the additional meeting coordinates to facilitate VTC join | Delivered to CVI Partners | Available | Available |
| CY26Q3 | Raise Hands | VTCs now have the ability to raise and lower their "hands", previously they were only able to consume this treatment from Teams clients | Delivered to CVI Partners | TBD | TBD |
| CY26Q3 | Lobby Controls | Trusted VTCs are now able to view and admit/deny access to Teams meetings where a lobby is configured | Delivered to CVI Partners | TBD | TBD |