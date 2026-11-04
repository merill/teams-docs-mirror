---
layout: Conceptual
title: Manage the attendance and engagement report for meetings and events in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/meeting-attendance-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
audience: Admin
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: richardzhang
ms.date: 2026-10-06T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
description: Collect meeting and event attendance and engagement information from the attendance report in Microsoft Teams. The attendance report shows join times, leave times, and in-meeting duration by attendee. The engagement report shows how attendees reacted and interacted during the meeting or event.
locale: en-us
document_id: 9a8b1087-ae40-6813-16bc-a69c90e50d19
document_version_independent_id: b808e843-80d8-4a96-c6ed-e8175968eb73
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/meeting-attendance-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/meeting-attendance-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/meeting-attendance-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9d1e4bc8-0cb3-548c-1808-251f66cdb5a3
---

# Manage the attendance and engagement report for meetings and events in Microsoft Teams - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Events

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

The attendance and engagement report for Teams meetings and events provides detailed information about organizers and attendees. The report shows who attended a meeting or event, along with the exact times each attendee joined and left, and other engagement metrics.

Organizers can see engagement information that captures how attendees reacted and interacted during the meeting or event. The engagement data shows the total count of attendees that performed the following actions:

- Unmuted during the meeting or event
- Turned on their cameras
- Raised their hands
- Used each type of meeting reaction
- Initiated questions, answers, and discussions through Q&A.

During the meeting or event, organizers can find the attendance report in the **People** &gt; **Participants** pane of the meeting. After the meeting or event ends, organizers can view and download the attendance and engagement report under the **Attendance** tab of the invite. Organizers can also access the attendance report through the meeting or event's chat. To learn more about how meeting and event organizers can view and download the attendance and engagement report, see [Manage meeting attendance reports in Microsoft Teams](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

For education tenants, the attendance and engagement report can be used to track student attendance and engagement in online classes. For example, a teacher can download the attendance report at the start of class as a simple way to do a roll call. The teacher can also use the engagement report to see how many students reacted, raised their hand, unmuted, interacted with Q&A and turned on their cameras during the online class.

As an admin, you control whether organizers can view and download the attendance and engagement report, who can be included in the report, and what information can be included.

## Manage attendance report policies in Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy you want to update or create a new policy.
3. Go to the **Meeting scheduling** section.
4. Choose one of the following options for **Attendance and engagement report**:

    | Option | Behavior |
    | --- | --- |
    | On, but organizers can turn it off | **This is the default.** Organizers with this policy can view and download the attendance and engagement reports for all meetings and events they create. They can also disable the attendance report in their meeting options. |
    | Off | Organizers with this policy can't view or download attendance and engagement reports for meetings and events they organize. |
    | On | Organizers with this policy can view and download the attendance and engagement report for all meetings and events they create; organizers can't turn off attendance and engagement reports. |
5. For **Include attendees in the report**, choose one of the following options:

    | Option | Behavior |
    | --- | --- |
    | Yes, but attendees can opt out | **This is the default.** The attendance and engagement report initially includes all attendees with this policy. To opt out, attendees can set the **Identify me in attendance reports** toggle to **Off** in their Teams privacy settings. |
    | No, but attendees can opt in | The attendance and engagement report initially excludes all attendees with this policy. To opt in, attendees can set the **Identify me in attendance reports** toggle to **On** or **Off** in their Teams privacy settings. |
    | Always | The attendance and engagement report includes all attendees with this policy, and attendees can't opt out. |
    | Never | The attendance and engagement report excludes all attendees with this policy, and attendees can't opt in. |
6. For **Attendee information**, choose one of the following options:

    | Option | Behavior |
    | --- | --- |
    | Show everything | **This is the default.** Include attendees' join times, leave times, and in-meeting duration. |
    | Only show who attended | Excludes attendees' join times, leave times, and in-meeting duration. |
7. Select **Save**.

Note

As an admin, you can’t view the attendance and engagement report for meetings and events that you didn't organize. However, you can view attendees' details for a given meeting or event within 24 hours of that meeting or event. In the Teams admin center, go to **Users** &gt; **Manage users**. Choose the display name for the meeting organizer. Select the **Meetings & calls** tab, and then choose the appropriate meeting ID or call ID. Then, select **Participant details**.

## Manage attendance report policies with PowerShell

To manage attendance and engagement reports, you can use the **`-AllowEngagementReport`** parameter in the PowerShell [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

To turn off attendance and engagement reports, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

To turn on attendance and engagement reports that initially exclude all attendees, but provide attendees the ability to opt in, use the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport ForceEnabled
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowTrackingInReport DisabledUserOverride
```

To give organizers the option to turn attendance and engagement reports that only show who attended and exclude other data on or off, run the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Enabled
Set-CsTeamsMeetingPolicy -Identity <policy name> -InfoShownInReportMode identityOnly
```