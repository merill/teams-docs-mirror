---
layout: Conceptual
title: Microsoft Teams analytics and reporting - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/teams-reporting-reference
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: jtremper
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
ms.date: 2026-08-03T00:00:00.0000000Z
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: In this article, learn about the Teams reports that are available in the Microsoft Teams admin center.
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 78ade1a4-092c-1132-44df-ee2c683fdd33
document_version_independent_id: 396b1aee-2f40-9895-9b00-07e38d11d31b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/teams-reporting-reference.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/teams-reporting-reference
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/teams-reporting-reference.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e32510e0-59dc-52f2-d806-873c7c82e95f
---

# Microsoft Teams analytics and reporting - Microsoft Teams | Microsoft Learn

An analytics and reporting experience for Microsoft Teams is available in the Microsoft Teams admin center. You can run different reports to get insights into how users in your organization are using Teams. For example, you can see how many users communicate through channel and chat messages and the kinds of devices they use to connect to Teams. Your organization can use the information from the reports to better understand usage patterns, help make business decisions, and inform training and communication efforts.

## How to access the reports

To access the reports, you must be assigned one of the following roles:

- Teams or Skype for Business administrator.
- Global reader (only tenant-level aggregate and no per-user or team data).

To learn more about Teams admin roles and which reports each admin role can access, see [Use Teams administrator roles to manage Teams](../using-admin-roles).

Go to the Microsoft Teams admin center, in the left navigation, select **Analytics & reports**, and then under **View Reports**, choose the report you want to run.

Note

The reports in the Microsoft Teams admin center are separate from the activity reports for Teams that are part of the Microsoft 365 reports in the Microsoft 365 admin center. For more information about the activity reports in the Microsoft 365 admin center, see [Microsoft 365 Reports in the admin center](/en-us/microsoft-365/admin/activity-reports/activity-reports).

## Teams reporting reference

Here's a list of the Teams reports available in the Microsoft Teams admin center across different environments and an overview of some of the information that's available in each report.

We're continually improving the Teams reporting experience and adding features and functionality. Over time, we'll be building additional capabilities into the reports and adding new reports in the Microsoft Teams admin center.

| Report | Public | GCC | GCCH | DoD | What's measured? |
| --- | --- | --- | --- | --- | --- |
| [Teams usage report](teams-usage-report) | Yes | Yes | Yes | Yes | Active usersActive users in teams and channelsActive channelsMessagesPrivacy setting of teamsActive guests in a team Active external users (in shared channels)Shared channel-specific details within a team (new) |
| [Teams user activity report](user-activity-report) | Yes | Yes | Yes | Yes | Active internal and external (In shared channels) users Messages a user posted in a team chatMessages a user posted in a private chat 1:1 calls a user participated in Number of meetings user organized Number of meetings user participated inMeetings Audio, Video and Screen sharing time Last activity date of a user Shared channel interactions of a user (new) |
| [Teams device usage report](device-usage-report) | Yes | Yes | Yes | Yes | Windows usersMac usersiOS usersAndroid phone users |
| [Teams events usage report](teams-events-usage-report) | Yes | No | No | No | Event IDEvent titleStatusStart timeEnd timeOrganizerCo-organizersPresentersEvent access typeTotal attendeesRegistration enabledDiscoverableRecordingRecording viewsRTMP |
| [Teams app usage report](app-usage-report) | Yes | Yes | No | No | Total active users of the appTotal active teams using the appTotal apps installed (new)Total inactive apps Total 1P vs 3P vs LoB app usage (new) |
| [Teams Premium feature usage report](teams-premium-usage-report) | Yes | No | No | No | Total reached usersTotal meetings |
| [Teams live event usage report](teams-live-event-usage-report) | Yes | Yes | No | No | Total viewsStart timeEvent statusOrganizerPresenterProducerRecording settingProduction type |
| [Teams PSTN blocked users report](pstn-blocked-users-report) | Yes | Yes | No | No | Display namePhone numberReasonAction typeAction date and time |
| [Teams PSTN minute pools report](pstn-minute-pools-report) | Yes | Yes | No | No | Country or regionCapability (license) Total minutesMinutes usedMinutes available |
| [Teams PSTN usage report - Calling Plans](pstn-usage-report#calling-plans) | Yes | Yes | No | No | Time stampUser namePhone numberCall type Called toTo country or region Called from From country or regionChargeCurrencyDurationDomestic/InternationalCall IDNumber typeCountry or regionConference IDCapability (license) |
| [Teams PSTN usage report - Direct Routing](pstn-usage-report#direct-routing) | Yes | Yes | Yes | Yes | Time stampDisplay nameSIP addressPhone number Call typeCalled toStart timeInvite timeFailure timeEnd timeDurationNumber typeMedia bypassSBC FQDNAzure regionEvent typeFinal SIP codeFinal Microsoft subcodeFinal SIP phraseCorrelation ID |
| [Teams information protection license report](information-protection-license-report) | Yes | Yes | No | No | Whether users have valid licenses to push their messages via change notificationsTotal number of change notification events triggered by a userWhat apps are listening to org-wide change notification events |
| [Frontline usage report](/en-us/microsoft-365/frontline/frontline-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json) | Yes | No | No | No | Total number of users on each team.Number of active users on each team. Last date on which the user signed in to Teams. |
| [Teams Virtual Appointments usage report](/en-us/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json) | Yes | Yes | No | No | Number of virtual appointmentsNumber of Bookings appointmentsNumber of Teams Electronic Health Records (EHR)-integrated appointmentsAverage duration of an appointmentAverage lobby wait time of attendeesStart timeMeeting IDLobby wait timeDurationStatusProduct typeAttendeesDepartmentSMS sentWhether the appointment used an advanced Virtual Appointments capability |
| [Teams Advanced Virtual Appointments activity report](/en-us/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json) | Yes | Yes | No | No | Number of users using advanced Virtual Appointments capabilitiesNumber of users who use SMS text notificationsNumber of users who conduct on-demand appointmentsNumber of users who use the queue |
| [Teams EHR connector Virtual Appointments report](/en-us/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json) | Yes | Yes | No | No | Start timeDurationPrimary (name of meeting organizer)Primary's email (email of meeting organizer)DepartmentAttendantsLobby wait timeWhether the appointment is within the allocation limit |
| [Walkie Talkie usage and performance report](walkie-talkie-usage-report) | Yes | Yes | No | No | Metrics include the number of push-to-talk (PTT) transmissions made and received, channel activity, transmission duration, and device and participant details. |
| [SMS notifications usage report](/en-us/microsoft-365/frontline/sms-notifications-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json) | Yes | No | No | No | Sent time  Sent from  SMS notification type  Product type  Status |
| [Teams client usage report](../teams-client-usage-report) | Yes | Yes | No | No | An overview of the Teams client desktops in your organization |
| [User reported security submissions report](../end-user-reported-security-signal) | Yes | No | No | No | **Calling**: Reported calls, including submission date and time, reporter, caller, phone number, call start time, duration, participants, and related call identifiers.**Chats and channels**: Reported chat and channel messages, including submission date and time, reporter, sender, message sent date, conversation identifiers, participants, and related message identifiers.**User**: Reported external users, including submission date and time, reporter, reported user, first contact date and time, conversation identifiers, and related user identifiers. |
| [Security detections report](security-detections-report) | Yes | No | No | No | Detection dateSender nameSender emailDetection typeRecipientRecipient actionSender MRIRecipient emailRecipient IDThread ID |

## Definitions

The Teams reports show data for active users and active channels. For example, if a user in your organization isn't active in Teams during the date range that you specified for a report, data for that user isn't included in that report.

| Item | Definition |
| --- | --- |
| Active user | Measures the number of unique users who perform an action in Teams during the specified date range for the user activity report. This represents active users across the tenant. However, for the Teams usage report, it represents active users only within active Teams. |
| Active channel | Measures the number of channels of a team in which users perform an action during the specified date range. |

## Make the user specific data anonymous

To make the identifiable information in usage reports anonymous, you have to be a Global administrator. The Global administrator can hide identifiable information (using MD5 hashes) such as display name, group name, email, and Microsoft Entra user ID in the report and its export.

1. In Microsoft 365 admin center, go to the **Settings** &gt; **Org Settings**, and under **Services** tab, choose **Reports**.
2. Select **Reports**, and then choose to **Display concealed user, group, and site names in all reports**. This setting gets applied both to the usage reports in Microsoft 365 admin center as well as Teams admin center.
3. Select **Save changes**.

Note

Enabling this setting de-identifies user, group, and site name information in the [Teams user activity report](user-activity-report), [Teams device usage report](device-usage-report), and [Teams usage report](teams-usage-report). From September 1, 2021, this setting is enabled by default for everyone as part of our ongoing commitment to help protect important information and enable companies to support their local privacy laws.

This setting also applies to Microsoft 365 usage reports in Microsoft 365 admin center, Microsoft Graph, and Power BI.