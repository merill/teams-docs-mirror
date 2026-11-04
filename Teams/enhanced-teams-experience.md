---
layout: Conceptual
title: Microsoft Teams Premium - Overview for admins - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/enhanced-teams-experience
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: spraveen, margidesai
ms.date: 2026-04-10T00:00:00.0000000Z
ms.topic: overview
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
audience: Admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
description: Learn about Microsoft Teams Premium for administrators and IT Professionals.
locale: en-us
document_id: 7a5338e6-ae08-bb92-3769-4af2932bf02c
document_version_independent_id: 7a5338e6-ae08-bb92-3769-4af2932bf02c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/enhanced-teams-experience.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: enhanced-teams-experience
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/enhanced-teams-experience.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: aecfe48c-188a-b977-5993-ea4ab9610d34
---

# Microsoft Teams Premium - Overview for admins - Microsoft Teams | Microsoft Learn

![Information icon](media/info.png)**The features described in this article require Teams Premium.** Teams Premium licenses aren't a replacement for Teams licenses. Users must have both a Teams license and a Teams Premium license for Teams and Teams Premium features to work properly. For more information about feature availability and licensing, see [Teams Premium licensing](teams-add-on-licensing/licensing-enhance-teams).

Teams Premium is an add-on license that provides the following enhancements to Teams:

- Enhanced meeting experiences for your end users
- Enhanced security and protection for meetings
- Enhanced administrative and telemetry support

This article, written for IT Pros and admins who are deploying and configuring Teams Premium, describes the available features and provides links to more detailed documentation.

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

Note

We'll continue to update this article. Check back often for links to new content.

## Protection and advanced management

Teams Premium provides more ways to safeguard and monitor users' Teams experiences with the following key features:

- **Advanced collaboration analytics** - View your organization's external collaboration habits. These reports include information about your teams, trusted domains, channels, guests, and internal users. You can also find information on inactive teams and inactive external domains.
- **Audio quality alerts** - Set up alerts for in-progress meeting audio issues and get notified immediately when your specified users experience issues.
- **Custom user policy packages** - Create policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.
- **Detect sensitive content during screen sharing** - When sensitive content is detected in a meeting, both the presenter and organizer receive notifications to stop sharing. The presenter sees a **Stop sharing** button.
- **End-to-end encryption** - Enforced through a sensitivity label, end-to-end encryption provides increased security for meetings that require a higher level of protection.
- **External domain activity report** - Understand how your organization communicates with trusted external organizations over chat.
- **Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcript** - Control whether organizers can restrict participants from copying or forwarding meeting chat messages, live captions, transcripts, and AI-generated insights in the meeting recaps. This setting also restricts forwarding and sharing messages to Outlook.
- **Require unverified participants to verify their info before joining** - Meeting organizers can turn on a setting that requires unverified users to enter a one-time passcode sent to their email before they can join the meeting.
- **Screen sharing quality alerts** - Set up alerts for in-progress meeting screen sharing issues and get notified immediately when your specified users experience issues.
- **Sensitivity labels** - Extended capabilities for sensitivity labels to control meeting settings normally controlled by the organizer. These capabilities include new settings to control lobby, chat, chat copy, presentation, and recording functions. You can also automatically apply or recommend that the meeting is labeled with the highest priority sensitivity label from files shared for the meeting.
- **Real time telemetry and retention** - Real-time telemetry is gathered automatically for all users who have a Teams Premium license and retained for seven days.
- **Priority account chat controls​** - Assign a policy to specific users to allow them to block incoming 1:1 chats from users in your organization.
- **Teams Premium feature usage report** - View aggregated usage of Teams Premium features by users in your org.
- **Video quality alerts** - Set up alerts for in-progress meeting video issues and get notified immediately when your specified users experience issues.
- **Watermarking** - Enforced through a sensitivity label, watermarks display the email address of a meeting participant. Watermarks are useful for protecting confidential information shared in meetings.
- **Who can record and transcribe** - Organizers can control who can record and transcribe their meetings through their meeting options. You must use a sensitivity label or meeting template to manage this feature.

    | Feature/Task | Can admins turn this feature on/off? | Documentation for admins | Documentation for your end users |
    | --- | --- | --- | --- |
    | Advanced collaboration analytics | No, contact support for assistance. | [Advanced Collaboration Analytics for Microsoft Teams](advanced-collaboration-analytics) | No end-user control |
    | Audio quality alerts | Yes, you can add or remove users. | [Alerts for in-progress meeting audio quality issues](/en-us/MicrosoftTeams/alerts/alerts-in-progress-meeting-audio) | No end-user control |
    | Custom user policy packages | Yes | [Managing policy packages in Teams](manage-policy-packages) | No end-user control |
    | Detect sensitive content during screen sharing | Yes | [Manage whether meetings in your organization can detect sensitive content during screen sharing](detect-sensitive-content) | [Sensitive content detection in Microsoft Teams meetings](https://support.microsoft.com/office/sensitive-content-detection-in-microsoft-teams-meetings-11f235f9-a170-4490-8bcb-703019d20a63) |
    | End-to-end encryption (E2EE)^1^ | Yes | [Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls](teams-end-to-end-encryption) | [Use encryption](https://support.microsoft.com/office/use-end-to-end-encryption-for-teams-meetings-a8326d15-d187-49c4-ac99-14c17dbd617c) |
    | External domain activity report | No, contact support for assistance. | [Microsoft Teams external domain activity report](/en-us/microsoftteams/teams-analytics-and-reports/external-domain-activity-report) | No end-user control |
    | Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcript | Yes, use the Teams admin center to manage content copying restrictions in your meeting templates or policies. Use the Microsoft Purview portal to turn labels with chat content copying restrictions on or off. | [Manage chat for sensitive Teams meetings](manage-chat-sensitive-meetings) | No end-user control |
    | Prevent users from sharing content in external meetings | Yes | [Prevent users from sharing content in external meetings](block-external-content-share) | No end-user control |
    | Priority account chat controls | Yes | [Allow users to block Microsoft Teams chat messages](block-incoming-chats) | No end-user documentation |
    | Real-time telemetry and retention | No, contact support for assistance. | [Use real-time telemetry to troubleshoot poor meeting quality](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality#where-to-find-per-user-real-time-troubleshooting-telemetry) | No end-user control |
    | Require unverified participants to verify their info before joining | Yes | [Manage anonymous participant access to Teams meetings and events (IT admins)](anonymous-users-in-meetings#anonymous-users-can-join-a-meeting-after-verifying-with-an-email-code-teams-premium) | [Meeting options in Microsoft Teams](https://support.microsoft.com/office/meeting-options-in-microsoft-teams-53261366-dbd5-45f9-aae9-a70e6354f88e) |
    | Screen sharing quality alerts | Yes, you can add or remove users. | [Alerts for in-progress meeting screen sharing issues](/en-us/MicrosoftTeams/alerts/alerts-in-progress-meeting-screen-sharing) | No end-user control |
    | Sensitivity labels | Yes, use the Microsoft Purview portal to turn labels on or off. | [Use sensitivity labels to protect calendar items, Teams meetings and chat](/en-us/purview/sensitivity-labels-meetings) | [Sensitivity labels for Teams meetings](https://support.microsoft.com/office/sensitivity-labels-for-teams-meetings-2b244d1d-72d0-471e-8e58-c41079e190fb) |
    | Teams Premium feature usage report | No, contact support for assistance. | [Teams Premium feature usage report](/en-us/microsoftteams/teams-analytics-and-reports/teams-premium-usage-report) | No end-user control |
    | Templates, labels, and policies | Yes, use the Teams admin center to add or delete meeting templates. Use the Microsoft Purview portal to turn labels on or off. | [Templates, sensitivity labels, and policies](meeting-templates-sensitivity-labels-policies) | [Use custom templates](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f) |
    | Video quality alerts | Yes, you can add or remove users. | [Alerts for in-progress meeting video quality issues](/en-us/MicrosoftTeams/alerts/alerts-in-progress-meeting-video) | No end-user control |
    | Watermarks | Yes | [Require a watermark for meetings](watermark-meeting-content-video) | [Watermarks for meetings](https://support.microsoft.com/office/watermark-for-teams-meetings-a9166432-f429-4a19-9a72-c9e8fdf4f589) |
    | Who can record and transcribe | Yes, use the Teams admin center to add or delete recording restrictions in your meeting templates. Use the Microsoft Purview portal to turn labels with recording restrictions on or off. | [Manage recordings for sensitive meetings](manage-meeting-recording-options) | [Record a meeting](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24?storagetype=stage#bkmk_whocanstartorstoparecording) |

    ^1^ Meeting organizers must have a Teams Premium license to use E2EE in meetings. Teams Premium isn't required for E2EE in one-to-one calls.

### Platform support for advanced management for meetings

The following table describes platform support for Teams Premium advanced management for meetings features:

| Feature | Windows | MAC | Mobile | Web | Microsoft Teams Rooms- Windows | Microsoft Teams Rooms- Android | Touch boards for Teams Rooms | Direct guest join | CVI | View-only mode | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Advanced collaboration analytics | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A |
| Audio quality alerts | Yes | Yes | Yes | Yes | Yes | Yes | Yes | N/A | N/A | Yes | N/A | N/A | Yes | Yes | Yes |
| Custom user policy packages | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A |
| End-to-end encryption (E2EE) | Yes | Yes | Yes | No (users can't join) | Yes | Yes | Yes | No (users can't join) | No (users can't join) | No (users can't join) | Yes | No | No | Yes | Yes |
| External domain activity report | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A |
| Organizer can restrict participants from copying or forwarding meeting chat messages, live captions, and transcripts | Yes | Yes | Yes^1^ | Yes | N/A | N/A | N/A | No | N/A | N/A | Yes | Yes | Yes | Yes | Yes |
| Real-time telemetry and retention | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A |
| Screen sharing quality alerts | Yes | Yes | Yes | Yes | Yes | Yes | Yes | N/A | N/A | Yes | N/A | N/A | Yes | Yes | Yes |
| Sensitivity labels | Yes | Yes | Yes | Yes | Yes | Yes | Yes | No | No | No | No | No | Yes | Yes | No |
| Teams Premium feature usage report | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A |
| Video quality alerts | Yes | Yes | Yes | Yes | Yes | Yes | Yes | N/A | N/A | Yes | N/A | N/A | Yes | Yes | Yes |
| Watermarks | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes | No | No | No | No | No | Yes |
| Who can record and transcribe | Yes | Yes | Yes | Yes | No | No | No | No | No | N/A | Yes | N/A | Yes | Yes | N/A |

## Personalized meetings

Teams Premium provides more ways to personalize your Teams meeting experiences with the following key features. For an overview on personalized meetings, see [Custom meetings overview](custom-meetings-overview):

- **Custom meeting backgrounds for organizations** - Create and define custom meeting backgrounds that your users can use during meetings.
- **Meeting templates** - Control meeting settings that the meeting organizer normally controls. With templates, you can create consistent meeting experiences in your organization and help enforce compliance requirements and business rules.
- **Meeting themes** - Create custom organization themes to customize the visual appearance of the meeting invite, pre-join screen, and lobby, and branded meeting reactions that participants use during meetings. Organizers can use these themes for their meetings.

    | Feature/Task | Can admins turn this feature on/off? | Documentation for admins | Documentation for your end users |
    | --- | --- | --- | --- |
    | Custom meeting backgrounds for organizations | Yes | [Meeting backgrounds](custom-meeting-backgrounds) | [Use meeting themes](https://support.microsoft.com/office/use-meeting-themes-for-teams-meetings-fbfd826d-1112-4790-918a-5a82cac8250e) |
    | Meeting templates | Yes | - [Overview](custom-meeting-templates-overview)- [Create a custom meeting template](create-custom-meeting-template)- [Set a custom meeting template as the default](custom-meeting-templates-set-default) | [Use custom templates](https://support.microsoft.com/office/use-custom-templates-for-teams-meetings-78279be9-3283-4999-b24e-96fb0da2fb4f) |
    | Meeting themes | Yes | [Themes for Teams meetings](meeting-themes) | [Use meeting themes](https://support.microsoft.com/office/use-meeting-themes-for-teams-meetings-fbfd826d-1112-4790-918a-5a82cac8250e) |

### Platform support for personalized meetings

The following table describes platform support for Teams Premium personalized meeting features:

| Feature | Windows | MAC | Mobile | Web | Microsoft Teams Rooms- Windows | Microsoft Teams Rooms- Android | Touch boards for Teams Rooms | Direct guest join | CVI | View-only mode | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Custom meeting backgrounds for organizations | Yes | Yes | Yes | Yes | N/A | N/A | N/A | N/A | N/A | N/A | Yes | N/A | N/A | Yes | Yes |
| Meeting templates | Yes | Yes | No | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | No | Yes | No |
| Meeting themes | Yes | Yes | Yes | Yes | No | No | No | No | No | N/A | Yes | Yes | N/A | Yes | Yes |

## Intelligent meeting features

Teams Premium provides the following key AI-powered meetings features:

- **Decorate my background** - Your users can use AI to decorate their backgrounds.
- **Intelligent meeting recap** - Give your users a more personalized rundown of their meetings with intelligent meeting recap.
- **Live translated captions** - For meetings, your users can see captions translated into the language they’re most comfortable with.
- **Live translated transcripts** - For meetings, your users can understand each other better during a meeting by translating the transcript into the language they're most comfortable with.

    | Feature/Task | Can admins turn this feature on/off? | Documentation for admins | Documentation for your end users |
    | --- | --- | --- | --- |
    | Decorate my background | No, contact support for assistance. | No admin control | [Decorate your background](https://support.microsoft.com/office/change-your-background-in-microsoft-teams-meetings-f77a2381-443a-499d-825e-509a140f4780) |
    | Intelligent meeting recap | No, contact support for assistance.^1^ | [Intelligent recap for Teams calls and meetings](intelligent-recap-calls-meetings) | [Meeting recap in Microsoft Teams](https://support.microsoft.com/office/meeting-recap-in-microsoft-teams-c2e3a0fe-504f-4b2c-bf85-504938f110ef#bkmk_intelligent_meeting_recap) |
    | Live translated captions | Yes | [Configure transcription and captions for Teams meetings](meeting-transcription-captions) | [Use live captions in Microsoft Teams meetings](https://support.microsoft.com/office/use-live-captions-in-microsoft-teams-meetings-4be2d304-f675-4b57-8347-cbd000a21260) |
    | Live translated transcripts | Yes | [Configure transcription and captions for Teams meetings](meeting-transcription-captions) | [View live transcription in Microsoft Teams meetings](https://support.microsoft.com/office/view-live-transcription-in-microsoft-teams-meetings-dc1a8f23-2e20-4684-885e-2152e06a4a8b) |

^1^If you toggle the **Transcription** setting to **Off** in your **Meeting policies**, intelligent meeting recap isn't available for users with this policy.

### Platform support for Intelligent meetings

The following table describes platform support for Intelligent meeting features:

| Feature | Windows | MAC | Mobile | Web | Microsoft Teams Rooms- Windows | Microsoft Teams Rooms- Android | Touch boards for Teams Rooms | Direct guest join | CVI | View-only mode | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Decorate my background | Yes | Yes | No | No | N/A | N/A | N/A | N/A | N/A | N/A | Yes | N/A | No | No | N/A |
| Intelligent meeting recap | Yes | Yes | Yes | Yes | N/A | N/A | N/A | N/A | N/A | N/A | Yes | N/A | Yes | Yes | N/A |
| Live translated captions | Yes | Yes | Yes | Yes | N/A | N/A | N/A | N/A | N/A | N/A | Yes | N/A | Yes | Yes | N/A |
| Live translated transcripts | Yes | Yes | Yes | Yes | N/A | N/A | N/A | N/A | N/A | N/A | Yes | N/A | Yes | Yes | N/A |

## Advanced Bookings and virtual appointments

With any Microsoft 365 license, your end users can use basic Bookings and virtual appointments capabilities to schedule and join business-to-customer meetings. For example, users can schedule appointments in the Bookings calendar and external attendees can join through a browser without having to download Teams.

To learn more about Bookings and virtual appointments, see [Appointments with Microsoft Teams](/en-us/microsoft-365/frontline/virtual-appointments) and [Microsoft Bookings](/en-us/microsoft-365/bookings/bookings-overview).

Teams Premium provides advanced Bookings and virtual appointment capabilities, such as:

- Consumption and usage analytics for admins in the Teams admin center
- Queue of appointments
- Short Message Service (SMS) notifications

    | Feature/Task | Can admins turn this feature on/off? | Documentation for admins |
    | --- | --- | --- |
    | Reporting | No, contact support for assistance. | [Bookings and virtual appointments usage report](/en-us/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json)[Advanced Bookings and virtual appointments activity report](/en-us/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json) |
    | SMS notifications | Yes | [SMS text notifications](bookings-app-admin#sms-text-notifications) |
    | Meeting themes | Yes | [Themes for Teams meetings](meeting-themes) |

### Platform support for Premium advanced Bookings and virtual appointments features

The following table describes platform support for Teams Premium Bookings and virtual appointments features:

| Feature | Windows | MAC | Mobile | Web | Microsoft Teams Rooms- Windows | Microsoft Teams Rooms- Android | Touch boards for Teams Rooms | Direct guest join | CVI | View-only mode | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SMS | Yes | Yes | No | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | Yes | Yes | Partial |
| SMS reminder in Queue | Yes | Yes | No | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | Yes | Yes | No |
| Queue view | Yes | Yes | No | Yes | N/A | N/A | N/A | N/A | N/A | N/A | N/A | N/A | Yes | Yes | No |

## Calls

### Intelligent call recap

**Intelligent call recap** provides AI-powered insights and recaps to Public Switched Telephone Network (PSTN) and 1:1 Teams calls.

- To use this feature for PSTN calls, you must assign a Teams Phone license and either Teams Premium license or a Microsoft Copilot license to users. For more information on Teams Phone licensing, see [Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).
- To use this feature with 1:1 Teams calls, you must assign a Teams Premium license or Microsoft Copilot license to users.

| Feature/Task | Can admins turn this feature on/off? | Documentation for admins | Documentation for end users |
| --- | --- | --- | --- |
| Intelligent call recap | No, contact support for assistance.^1^ | [Intelligent recap for Teams calls and meetings](intelligent-recap-calls-meetings) | No end user documentation |

^1^If you turn off **Transcription**, intelligent call recap isn't available for users with this policy.

### Queues app

Teams Premium and Teams Phone provide access to Queues app, a Teams-native solution that unlocks a set of advanced call functionalities for Teams Phone Call queues and Auto attendants, such as:

- **Call queue management**: Admins can now delegate authorized users, also known as leads or supervisors, to manage and configure Call queues and Auto attendants directly from the Teams client. Authorized users can configure Call queues and Auto attendants from Call settings and they can opt agents into and out of the queue from Queues app.
- **Real-time metrics**: The number of waiting calls, average wait time, longest call waiting time metrics, and more are included in real-time metrics within the Queues app. The analytics report shows activity made in the queue from 12:00 AM local time of the signed in user. For more information on real-time reports, see [Auto attendant and Call queue real-time reports](aa-cq-report-real-time).
- **Historical reporting**: View historical metrics for call queues, and auto attendants, and agent queue actions. Historical metrics report up to the past 45 days. For more information on historical reports, see [Auto attendant and Call queue historical reports](aa-cq-report-historical).
- **Monitor, Whisper, Barge, Takeover** - Authorized users can enter into a monitoring session with selected agents for private coaching. Authorized users can listen to customer calls, whisper to agents with private messages, even barge into or takeover the calls. For information about configuring Monitor, Whisper, Barge, and Takeover, see [Manage voice applications policies in Microsoft Teams](aa-cq-manage-voice-applications-policies).

    | Feature/Task | Can admins turn this feature on/off? | Documentation for admins | Documentation for end users |
    | --- | --- | --- | --- |
    | Call queue management | Yes, with [voice application policies](aa-cq-manage-voice-applications-policies) for Authorized users | [Manage the Queues app for Microsoft Teams](manage-queues-app) | [Use the Queues app for Microsoft Teams](https://support.microsoft.com/office/370ad83e-c2c1-4a9f-8a59-16c98be102e9) |
    | Real-time metrics | Yes, with [voice application policies](aa-cq-manage-voice-applications-policies) for Authorized users | [Auto attendant and Call queue real-time reports](aa-cq-report-real-time) | No, end users can view reports if authorized. |
    | Historical reporting | Yes, with voice application policies for Authorized users | [Auto attendant and Call queue historical reports](aa-cq-report-historical) | No, end users can view reports if authorized. |
    | Monitor, Whisper, Barge, Takeover | Yes, with voice application policies for Authorized users | [Manage voice applications policies in Microsoft Teams](aa-cq-manage-voice-applications-policies) |  |

Queues app is now generally available and is enabled by default for all Teams users in your organization who are assigned both a Teams Premium and Teams Phone license and who are voice enabled.

For more information about Queues app, see [Manage the Queues app for Microsoft Teams](manage-queues-app). For end user documentation, see [Use the Queues app for Microsoft Teams](https://support.microsoft.com/office/370ad83e-c2c1-4a9f-8a59-16c98be102e9).

#### Platform support for Queues app

The following table describes platform support for Queues app:

| Feature | Windows | Mac | Mobile | Web | Microsoft Teams Rooms - Windows | Microsoft Teams Rooms - Android | Touch boards for Teams Rooms | Direct guest join | CVI | View-only mode | External communication with unmanaged Teams users | Anonymous users support | VDI WebRTC classic optimization | VDI SlimCore-based optimization | Exchange on-premises |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Queues app | Yes | Yes | No | No | No | No | No | N/A | No | N/A | N/A | N/A | Yes | Yes | Partial |