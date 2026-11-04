---
layout: Conceptual
title: Manage meeting policies for content sharing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-policies-content-sharing
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: kamila.korsec, mario.novoselec
ms.date: 2025-05-29T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- Tier2
- m365initiative-meetings
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
description: Learn to manage meeting policy settings in Teams for content sharing.
locale: en-us
document_id: 9e8bc321-43b2-5155-536c-2be64e26e345
document_version_independent_id: 625609b4-e633-7e26-367f-da17f3e4f54b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-policies-content-sharing.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-policies-content-sharing
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-policies-content-sharing.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: bf1c4f2e-746a-797d-dad2-8a2d1bfd3bcb
---

# Manage meeting policies for content sharing - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Content sharing settings control how users present a screen or app during a chat, meeting, or event. You can configure admin settings for screen sharing mode, PowerPoint sharing, whiteboard, and shared notes. For information about how to manage who can present and who can request control, see [Manage who can present and request control in Teams meetings](meeting-who-present-request-control).

In events [optimized for large audiences](plan-events), only presenters, organizers, and co-organizers can use shared notes and screen sharing.

## Manage content sharing policies

To manage content sharing policies, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy that you want to edit.
3. Go to the **Content sharing** section.
4. Select the settings you want to use. These settings are described in the Screen sharing mode, PowerPoint Live, Whiteboard, Live share, and Shared notes sections in this article.
5. Select **Save**.

### Use PowerShell to manage content sharing

You can also use the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet to control the content sharing settings. Set the following parameters:

- ScreenSharingMode
- AllowPowerPointSharing
- AllowWhiteboard
- AllowCollaborativeAnnotations
- AllowDocumentCollaboration
- AllowSharedNotes

## Screen sharing mode

This setting is a per-user policy. The setting controls whether a user can share a desktop and window in a Teams meeting.

| Setting value | Behavior |
| --- | --- |
| **Entire screen** | Full desktop sharing and application sharing are allowed in the meeting. |
| **Single application** | Application sharing is allowed in the meeting. If your users are using Teams in a web browser and are assigned this value, this setting functions as **Not enabled**. |
| **Not enabled** | Screen sharing and application sharing turned off in the meeting. |

## PowerPoint Live

This is a per-user policy. This setting controls whether the user can share PowerPoint presentations in a meeting. External participants, including anonymous, guest, and external access users, inherit the policy of the meeting organizer. For details on how your users use PowerPoint Live, see [Present from PowerPoint Live in Microsoft Teams](https://support.microsoft.com/office/present-from-powerpoint-live-in-microsoft-teams-28b20e74-7165-499c-9bd4-0ad975d448ad).

Let's look at the following example.

| User | Meeting policy | PowerPoint Live |
| --- | --- | --- |
| Daniela | Global | On |
| Amanda | Location1MeetingPolicy | Off |

Amanda can't share PowerPoint presentations in meetings even if she's the meeting organizer. Daniela can share PowerPoint presentations even if Amanda organizes the meeting. Amanda can view the PowerPoint presentations shared by others in the meeting, even though she can't share PowerPoint presentations.

## Whiteboard

Microsoft Whiteboard is a free-form, digital canvas where people, content, and ideas come together. Whiteboard integration in Microsoft Teams meetings is powered by the Whiteboard web app, which lets Teams meeting participants draw, sketch, and write together on a shared digital canvas.

Users can share a whiteboard to make it available to all participants in a Teams meeting. That same whiteboard is simultaneously available in all the Whiteboard applications on Windows 10, iOS, and the web app.

To turn the Whiteboard app on or off, see [Enable Microsoft Whiteboard for your organization](/en-us/microsoft-365/whiteboard/manage-whiteboard-access-organizations). Keep in mind that this setting enables or disables Whiteboard for your entire organization, and not just for Teams.

Whiteboards are created in the OneDrive of the person who starts the whiteboard. For more information, see [Manage data for Microsoft Whiteboard](/en-us/microsoft-365/whiteboard/manage-data-organizations).

The **Whiteboard** setting for Teams meetings is a per-user setting. This setting controls whether a user can share the Whiteboard in a meeting. External participants, including anonymous, guest, and external access users, inherit the meeting organizer's policy.

Let's look at the following example.

| User | Meeting policy | Whiteboard |
| --- | --- | --- |
| Daniela | Global | On |
| Amanda | Location1MeetingPolicy | Off |

Amanda can't share the whiteboard in a meeting even if she's the meeting organizer. Daniela can share the whiteboard even if Amanda organizes a meeting.

To enable Whiteboard using PowerShell, set the **`-IsWBFluidEnabled`** parameter to $true from [Set-SPOTenant](/en-us/powershell/module/sharepoint-online/set-spotenant):

```powershell
Set-SPOTenant -IsWBFluidEnabled $true
```

For information for your end users about how to use Whiteboard, see [Use Whiteboard in Microsoft Teams](https://support.office.com/article/7a6e7218-e9dc-4ccc-89aa-b1a0bb9c31ee).

### Whiteboard on Surface Hub

Before trying to use Microsoft Whiteboard, make sure that the Whiteboard app is installed on your Surface Hub device. If Whiteboard isn't installed, on the Surface Hub device, go to the Microsoft Store app, and get [Microsoft Whiteboard](https://www.microsoft.com/p/microsoft-whiteboard/9mspc6mp8fm4?activetab=pivot:overviewtab). For more information, see [Enable Microsoft Whiteboard on Surface Hub](https://support.office.com/article/enable-microsoft-whiteboard-on-surface-hub-b5df4539-f735-42ff-b22a-0f5e21be7627).

### Collaborative annotations

To enable **Collaborative annotations**, a per-user policy, you must first enable **Whiteboard**. When you **Collaborative annotations** enable for users with an assigned policy, these users can use annotations, a feature that allows participants to collaborate while sharing their screen in a Teams meeting. If **Whiteboard** or **Collaborative annotations** are disabled, users don't have access to annotations.

To enable **Collaborative Annotations** using PowerShell, set the **`-AllowCollaborativeAnnotations`** parameter to $true from [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy):

```powershell
Set-CSTeamsMeetingPolicy -AllowCollaborativeAnnotations $true
```

## Live share

Users can edit a document from within the Teams meeting window. This allows real time coauthoring in the context of a meeting.

To enable **Collaborative annotations** using PowerShell, set the **`-AllowDocumentCollaboration`** parameter to $true from [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy):

```powershell
Set-CSTeamsMeetingPolicy -AllowDocumentCollaboration $true
```

## Shared notes

This setting is a per-user policy. This setting controls whether a user can create and share notes in a meeting. External participants, including anonymous, guests, and external access, inherit the policy of the meeting organizer. The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.

Let's look at the following example.

| User | Meeting policy | Shared notes |
| --- | --- | --- |
| Daniela | Global | On |
| Amanda | Location1MeetingPolicy | Off |

Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.

To enable **Shared notes** using PowerShell, set the **`-AllowSharedNotes`** parameter to $true from [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy):

```powershell
Set-CsTeamsMeetingPolicy -AllowSharedNotes $true
```