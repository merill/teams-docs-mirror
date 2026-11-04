---
layout: Conceptual
title: Reporting - Voice applications historical reports - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-report-historical
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: CLYVR
ms.author: colongma
manager: roykuntz
ms.reviewer: colongma
ms.date: 2026-10-25T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
- ContentFreshnessFY24
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to learn about historical reporting for Teams Phone Agent, Auto Attendant, and Call Queue so I can enable my business leads to report on their call flows and representative performance.
description: Learn how to install, configure, and interpret the Power BI historical reports for Teams Phone Agent, Auto Attendant, and Call Queue.
locale: en-us
document_id: f10dcb86-8529-c107-a208-36e09a27cd9b
document_version_independent_id: f10dcb86-8529-c107-a208-36e09a27cd9b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-report-historical.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-report-historical
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-report-historical.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/d3197845-b4ce-44c6-a237-cd4be160e76c
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/aea905fb-0a9d-4d46-b30f-e9cbaf772d1b
platformId: c81df42d-9204-ebc7-b0bd-5e62c0484186
---

# Reporting - Voice applications historical reports - Microsoft Teams | Microsoft Learn

Note

Help shape the future of **Teams Voice Applications Historical Reporting**. [Share quick feedback](https://go.microsoft.com/fwlink/?LinkId=2375135) on the reports, setup documentation, translations, or languages you’d like supported. Your input will be reviewed by Microsoft and used to improve the product, documentation, and localization experience for everyone.

This article is for IT pros and Teams administrators who want to report on the calls handled by Teams Phone Agents, Auto Attendants, and Call Queues.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Authorized users](aa-cq-plan-authorized-users)
- [Nesting call flows](aa-cq-plan-nesting)
- [Reporting considerations](aa-cq-plan-reporting)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## V3.3.2 published on September 29, 2026

What's new in this release:

- New Call Flow Details report shows how calls move through voice applications to a representative (agent).
- New Teams Phone Agent drill through report replaces the tooltip.
- Teams Phone Agent report now available in all supported languages.
- Simplified report color customization.
- Ability to provide feedback on the reports.
- Reports renamed to Teams Voice Applications Historical Reports.
- Performance enhancements - reduced load and refresh times by over 60%.
- Four new languages/locales supported:
    - Bangla (Bangladesh)
    - Filipino (Philippines)
    - Irish (Ireland)
    - Maltese (Malta)

## Overview

The Teams Voice Applications Historical Reports Power BI template provides five reports that allow organizations to report on the number of calls processed by Teams Phone Agents, Auto Attendants, and Call Queues. It also provides representative (agent) performance insights.

These reports use data from the Voice Applications Analytics Collector (VAAC) service.

The Teams Voice Applications Historical Reports Power BI template contains the following five reports:

Cloud Teams Phone Agent Analytics (expand to see sample report)

The Cloud Teams Phone Agent Analytics report shows analytics for calls coming into your Teams Phone Agents.

[![Screenshot showing an example of the Teams Phone Agent report.](media/aa-cq/historical-report-sample-v332-teams-phone-agent.png)](media/aa-cq/historical-report-sample-v332-teams-phone-agent.png#lightbox)

In addition, when hovering over a call in table at the bottom of the report, the option for drill-through will appear. Selecting this will show the Cloud Teams Phone Agent Usage Details report for that call.

[![Screenshot showing an example of the Teams Phone Agent Usage Details report.](media/aa-cq/historical-report-sample-v332-teams-phone-agent-usage-details.png)](media/aa-cq/historical-report-sample-v332-teams-phone-agent-usage-details.png#lightbox)

Cloud Auto Attendant Analytics (expand to see sample report)

The Cloud Auto Attendant Analytics report shows analytics for calls coming into your Auto Attendants.

[![Screenshot showing an example of the Auto Attendant report.](media/aa-cq/historical-report-sample-v332-auto-attendant.png)](media/aa-cq/historical-report-sample-v332-auto-attendant.png#lightbox)

Cloud Call Queue Analytics (expand to see sample report)

The Cloud Call Queue Analytics report shows analytics for calls coming into your Call Queues.

[![Screenshot showing an example of the Call Queue report.](media/aa-cq/historical-report-sample-v332-call-queue.png)](media/aa-cq/historical-report-sample-v332-call-queue.png#lightbox)

Cloud Agent Timeline Analytics (expand to see sample report)

The Cloud Agent Timeline Analytics report shows a timeline view of representatives (agents) being active in Call Queue calls.

[![Screenshot showing an example of the Agent Timeline report.](media/aa-cq/historical-report-sample-v332-agent-timeline.png)](media/aa-cq/historical-report-sample-v332-agent-timeline.png#lightbox)

**New** Cloud Call Flow Details (expand to see sample report)

The Cloud Call Flow Details report shows each leg of the call as it moves through voice applications to a representative.

[![Screenshot showing an example of the Call Flow Details report.](media/aa-cq/historical-report-sample-v332-call-flow-details.png)](media/aa-cq/historical-report-sample-v332-call-flow-details.png#lightbox)

## V3.x.x prerequisites

### Power BI Desktop

You need to have Power BI Desktop installed. You can install and use the free version from the [Microsoft Windows Store](https://aka.ms/pbidesktopstore)

Important

Power BI Desktop is updated and released on a monthly basis, incorporating customer feedback and new features. Only the most recent version of Power BI Desktop is supported. Customers who contact support for Power BI Desktop are asked to upgrade to the most recent version. You can get the most recent version of Power BI Desktop from the [Microsoft Windows Store](https://aka.ms/pbidesktopstore), or as a single executable containing all supported languages that you [download](https://www.microsoft.com/download/details.aspx?id=58494) and install on your computer.

### Access permissions

Use one of the following methods to control access to the historical reports:

- Voice applications policy

    To let users run reports on Auto attendants, Call queues, and Representatives (Agents) without giving them access to the Teams admin center, assign them a voice applications policy that allows historical reporting. Then assign the user as an authorized user for the relevant Auto attendants and Call queues. Admins can create this policy in the Teams admin center or with PowerShell.

    For more information about creating a voice applications policy, see [Manage voice applications policies in Microsoft Teams](aa-cq-manage-voice-applications-policies).

    Tip

    We recommend using the voice applications policy to control access to historical reports. With a voice applications policy and authorized users, it's possible to control which Auto attendants, Call queues, and Representatives (Agents) a user can report on. If necessary, the policy still allows a user to report on all Auto Attendants, Call Queues, and Representatives (Agents) without providing access to the Teams admin center.
- Call Quality Dashboard (CQD) pipeline [legacy]

    If you want the user to report on **all** the Auto Attendants, Call Queues, and Representatives (Agents) in the tenant and you want to grant the user access to the Teams admin center to run other Usage reports, assign the user a CQD access role with both **View Reports** and **View EUII fields** set to **Yes**.

    For more information, see [CQD access role](turning-on-and-using-call-quality-dashboard#assign-admin-roles-for-access-to-cqd).

    Note

    If a user is assigned to a CQD access role and a voice applications policy, the CQD role takes precedence and the user can see all the Auto Attendants, Call Queues, and Representatives (Agents) in the tenant.

## V3.x.x desktop installation

Expand to see the desktop installation steps

Important

The following steps assume that:

- Power BI Desktop is installed
- Your Teams account is either:
    - Set up as an [authorized user](aa-cq-plan-authorized-users).
    - Assigned a [CQD access role](turning-on-and-using-call-quality-dashboard#assign-admin-roles-for-access-to-cqd).

Perform the following steps:

1. Download and save the [Teams Voice Applications Historical Reports V3.3.2.pbit](https://www.microsoft.com/download/details.aspx?id=104623) file on your computer.
2. Open the `Teams Voice Applications Historical Reports V3.3.2.pbit` template file. Power BI Desktop should launch.
3. Select the **Tenant Location**, **Language**, and **UTC Offset**.

    [![Screenshot showing the Location, Language, and UTC Offset selections.](media/aa-cq/historical-report-setup-01-v332-desktop-initial-page.png)](media/aa-cq/historical-report-setup-01-v332-desktop-initial-page.png#lightbox)

    - **Tenant Location**: Select the tenant cloud location.
        - Public Cloud includes Government Community Cloud (GCC) tenants.
    - **Language**: Select the language and report level.
        - Select `Per Call` to retrieve all the individual call records.
        - Select `Per Day` to retrieve an aggregated total for each day.
    - **UTC Offset**: Select the UTC offset that represents the time zone the reports are presented in. Only valid when the **Report Level** is `Per Call`.

#### Per Day vs Per Call

    - **Per Call** reporting retrieves the individual call records for each Teams Phone Agent, Auto Attendant, Call Queue, and Representative (Agent) the user is authorized for. Per Call reporting also allows call records to be displayed in the local time zone selected by the user. For some customers, especially those using the CQD access role to control access, Per Call reporting might result in hitting the 150,000 default per query record limit. See Data limits.
    - **Per Day** reporting retrieves one daily summary record for each Auto Attendant, Call Queue, and Representative (Agent). This reporting results in fewer records being returned to the client, reducing the possibility of hitting the 150,000 default per query record limit. Per Day reporting is based on a UTC-00:00 day (00:00:00-23:59:59 UTC) only, and any UTC offset supplied by the user is ignored.

**Steps 4-7 are only performed once, the first time the template is loaded.**

1. Configure the data sources authentication.

    1. Select **File**, then **Options and settings**, and then **Data source settings**.

    [![Screenshot showing data sources for v3.2.x.](media/aa-cq/historical-report-setup-02-desktop-datasources.png)](media/aa-cq/historical-report-setup-02-desktop-datasources.png#lightbox)
2. Do the following steps for each of the two data sources shown in the group based on your tenant location:

    - Group 1: Department of Defense (DoD)
    - Group 2: Government Community Cloud High (GCCH)
    - Group 3: Public Cloud (including Government Community Cloud (GCC) tenants)

    1. Select the data source.
    2. Select **Edit Permissions**, and then **Edit**.
    3. Select **Organizational account** and then **Sign in** (or **Sign in as different user**).

        [![Screenshot showing data source sign in screen.](media/aa-cq/historical-report-setup-03-desktop-access-web-content.png)](media/aa-cq/historical-report-setup-03-desktop-access-web-content.png#lightbox)
    4. Sign in with your Teams user or Teams admin account.
3. Select **Save**, then **OK**, and then **Close**.
4. Select **Refresh** in the ribbon bar and the data refreshes.

    Depending on your Power BI Desktop settings, the following pop-up window might also appear:

    [![Screenshot showing data privacy screen.](media/aa-cq/historical-report-setup-04-desktop-privacy-levels.png)](media/aa-cq/historical-report-setup-04-desktop-privacy-levels.png#lightbox)

    Enable the **Ignore Privacy Levels** checkbox. All the data is coming from the historical report database. No undesirable data transfer is taking place.

## V3.x.x Power BI service installation

Expand to see the Power BI service installation steps

Important

The report must be installed and working in Power BI Desktop before it can be [published to the Power BI service](/en-us/power-bi/create-reports/desktop-upload-desktop-files).

Once published, perform the following steps in the Power BI service:

1. Go to the dataset **Settings**.
2. Expand the **Data source credentials** section.

    [![Screenshot showing the data source credentials section of the template in the Power BI service.](media/aa-cq/historical-report-setup-05-service-datasources-01.png)](media/aa-cq/historical-report-setup-05-service-datasources-01.png#lightbox)

    - Group 1: Public Cloud (including Government Community Cloud (GCC) tenants)
    - Group 2: Government Community Cloud High (GCCH)
    - Group 3: Department of Defense (DoD)
3. Do the following steps for the two data sources in the group based on your tenant location:

    - Select **Edit credentials**.
    - Set the **Authentication method** to `OAuth2`.
    - Set the **Privacy level setting for this data source** to `Organizational`.
    - Ensure **Skip test connection** is enabled.
    - Select **Sign in** and provide your credentials.

    [![Screenshot showing the configured data source credentials for selected tenant location.](media/aa-cq/historical-report-setup-05-service-datasources-02.png)](media/aa-cq/historical-report-setup-05-service-datasources-02.png#lightbox)
4. Do the following steps for the data sources in the other two groups:

    - Select **Edit credentials**.
    - Set the **Authentication method** to `Anonymous`.
    - Set the **Privacy level setting for this data source** to `Organizational`.
    - Ensure **Skip test connection** is enabled.
    - Select **Sign in**.

    [![Screenshot showing the configured data source credentials for the remaining locations.](media/aa-cq/historical-report-setup-05-service-datasources-03.png)](media/aa-cq/historical-report-setup-05-service-datasources-03.png#lightbox)

When completed, you're able to [configure a scheduled refresh](/en-us/power-bi/connect-data/refresh-scheduled-refresh) of the dataset.

## Data latency

The historical data is typically available within 30 minutes of the call being completed, but there are cases where it can take several hours for the data to appear.

**You have to refresh the report to see any new data.**

The reports are based on diagnostic telemetry. The information shown in these reports is only as complete as the telemetry data received from clients participating in a call. There are several reasons why complete telemetry might not be received, such as network outages, or [firewall or proxy misconfigurations](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges). There's ongoing work to improve the reliability and resiliency with which Teams clients deliver telemetry to the service.

With that in mind, using these reports for auditing, compliance, or payroll-related reporting scenarios isn't supported.

## Interpreting the reports, notes, and known issues

### Cloud Teams Phone Agent Analytics

Expand to see how to interpret the Cloud Teams Phone Agent Analytics report, for notes and known issues
[![Screenshot showing sample Cloud Teams Phone Agent Analytics report.](media/aa-cq/historical-report-sample-v332-teams-phone-agent-callouts.png)](media/aa-cq/historical-report-sample-v332-teams-phone-agent-callouts.png#lightbox)

| Callout | Title | Description |
| --- | --- | --- |
| 1 | Version | The report version and link to this documentation. |
| 2 | Language | The selected language and locale. |
| 3 | Report Level | The selected report level.^See Note 1^ |
| 4 | UTC Offset | The selected UTC offset. |
| 5 | Feedback | Provide your feedback on the reports. |
| 6 | Date | The start and end date of the report.Use this slider to select the date range to report on. |
| 7 | Time Range | The start and end hour of the report. The report spans all dates/times from start date/start hour to the end date/end hour.Use this slider to select the time range to report on. |
| 8 | Teams Phone Agent Resource AccountTeams Phone Agent | **Admins:** The Resource Accounts to report on.^See Note 2^**Admins or Auth Users:** The Teams Phone Agent to report on.^See Note 3^Default: All |
| 9 | Messages | Informational messages |
| 10 | Quick Stats -&gt; Incoming Calls | The breakdown shows the total number of calls received between the start date/start hour and end date/end hour.<br>- **External** - the call originated from outside the tenant<br>- **Internal** - the call originated from inside the tenant<br>- **Click2Call** - the call originated from the web<br>- **Other** - the call originated from some other method |
|  | Quick Stats -&gt; Usage Statistics | The breakdown shows how the Teams Phone Agent was used.<br>- **Calls Contained** - The number of calls that hung up after successfully booking, changing, or canceling an appointment, or where a question was successfully answered<br>- **Percent Contained** - The percentage of calls contained.*Calls Contained / Total Calls*<br>- **Q&A Used** - The number of calls that used the Questions and Answers feature.<br>- **Appts Scheduled** - The number of calls that scheduled an appointment.<br>- **Copilot Calls** - The number of calls that used the Microsoft Copilot Studio agent.<br>- **Avg. Call Seconds** - The average amount of time a call spent in Teams Phone Agent.<br>- **Total Call Duration [HH:MM:SS]** - The total amount of time all calls during the reporting period spent in Teams Phone Agent |
| 11 | Call Results | Breakdown showing the final call result.<br>- **Appointment (Authentication failed)** - Caller attempted to book a meeting and was not successfully authenticated<br>- **Appointment (Authentication successful)** - Caller attempted to book a meeting and was successfully authenticated<br>- **Appointment (Fetch failed)** - Unable to retrieve open time slots<br>- **Appointment (Fetch successful)** - Retrieved open time slots<br>- **Appointment (Booking failed)** - Appointment booking failed<br>- **Appointment (Booking successful)** - Appointment booking successful<br>- **Appointment (Change failed)** - Appointment change failed<br>- **Appointment (Change successful)** - Appointment change successful<br>- **Appointment (Cancel failed)** - Appointment cancel failed<br>- **Appointment (Cancel successful)** - Appointment cancel successful<br>- **Q&A (Failed)** - Question and answer failed (caller's question was not answered)<br>- **Q&A (Successful)** - Question and answer successful (caller's question was answered)<br>- **Terminated (Disconnected)** - Call was disconnected per the auto attendant configuration<br>- **Terminated (No Operator)** - Call was disconnected as there was no operator to transfer the call to<br>- **Terminated (User)** - Caller hung up<br>- **Transferred (Auto Attendant)** - Call was transferred to another Auto Attendant<br>- **Transferred (Agent)** - Call was transferred to a Microsoft Copilot Studio agent<br>- **Transferred (Call Queue)** - Call was transferred to a Call Queue<br>- **Transferred (Operator)** - Call was transferred to the Operator<br>- **Transferred (RA)** - Call was transferred to a Resource Account<br>- **Transferred (User)** - Call was transferred to a Person in the organization<br>- **Other** - Some other condition occurred |
| 12 | Categories | Categories are the voice commands configured on the Teams Phone Agent menu. |
| 13 |  | Breakdown showing the date and time of each Teams Phone Agent call, including the final call result.<br>- **Start Time** - The date and time the call started<br>- **Teams Phone Agent Resource Account** or **Teams Phone Agent**<br>    - **Admins** - Teams Phone Agent Resource Account^See Note 2^<br>    - **Admins or Auth Users** - Teams Phone Agent^See Note 3^<br>- **Call Result** - The end result of the call (see #12 Call Results)<br>- **Category** - The categories for the call.<br>- **Conference ID** - The unique ID for the call.<br><br>*TIP: Hover over any metric in this section to display the drill-through option to get a breakdown on how the call progressed through Teams Phone Agent.* |

#### Teams Phone Agent Analytics Notes

1. The report is only available in Per-Call mode. ↩

2. Admins without a voice applications policy or with a voice applications policy where the auto attendant historical reporting permissions are set to `None` or `Only authorized auto attendants`: ↩

- Reporting is by the Resource Account username.
- Nested Teams Phone Agents or Auto attendants that receive calls through a `Voice App` transfer report those calls under the Teams Phone Agent or Auto Attendant GUID.
- To see the calls for a specific Teams Phone Agent, select the resource accounts assigned to that Teams Phone Agent.
- Resource accounts are shown by their username.
    - For example: If the full Resource Account name is **tpa\_test@microsoft.com**, then this value is: **tpa\_test**.

3. Admins with a voice applications policy where the auto attendant historical reporting permissions are set to `All` or Authorized users: ↩

- Reporting is by Teams Phone Agent name.

4. This report is not currently available for Queues App users.

#### Teams Phone Agent Analytics Known issues

No known issues.

### Cloud Teams Phone Agent Usage Details

Expand to see how to interpret the Cloud Teams Phone Agent Usage Details report, for notes and known issues

[![Screenshot showing sample Cloud Teams Phone Agent Usage Details report.](media/aa-cq/historical-report-sample-v332-teams-phone-agent-usage-details-callouts.png)](media/aa-cq/historical-report-sample-v332-teams-phone-agent-usage-details-callouts.png#lightbox)

| Callout | Title | Description |
| --- | --- | --- |
| 1 | Version | The report version and link to this documentation. |
| 2 | Language | The selected language and locale. |
| 3 | Report Level | The selected report level. |
| 4 | UTC Offset | The selected UTC offset. |
| 5 | Feedback | Provide your feedback on the reports. |
| 6 |  | The details for the selected call.<br>- **Teams Phone Agent Resource Account** or **Teams Phone Agent**<br>    - **Admins** - Teams Phone Agent Resource Account.^See Note 1^<br>    - **Admins or Auth Users:** Teams Phone Agent.^See Note 2^<br>- **Voice** - the voice configured on the Teams Phone Agent.<br>- **Conference ID** - the unique ID for the call.<br>- **Schedule** - the schedule Teams Phone Agent was following. |
| 7 |  | Breakdown showing the date and time of each action taken and the end result of that action.<br>- **Start Time** - The start time of the specific step.<br>- **Action** - The specific action invoked in Teams Phone Agent^See Known Issue 1^.<br>    - **Find Person By Name** - dial by name request.<br>    - **Find Person By Name With Recognizer** - dial by name request.<br>    - **Find Person By Extension** - dial by extension request.<br>    - **Transfer Call** - call was transferred.<br>    - **Fallback To DTMF** - Teams Phone Agent reverted to touch-tone mode.<br>    - **Initiate Caller Authentication** - authentication for appointment booked was started.<br>    - **Authenticate Caller** - caller was authenticated.<br>    - **Get Available Appointments** - a list of available appointments was retreived.<br>    - **Book Appointment** - an appointment was booked.<br>    - **Get All Appointments For Caller** - the caller's existing bookings were retrieved.<br>    - **Cancel Appointment** - an existing appointment was cancelled.<br>    - **Modify Appointment** - an existing appointment was changed.<br>    - **Question Answer** - question and answer tool was used.<br>    - **Spam Likely Detection** - the call was identified as spam.<br>    - **Other** - some other action was taken.<br>- **Menu Option** - The voice command as configured on the Teams Phone Agent menu option associated with the action.<br>- **Menu Option Description** - The menu option description as configured on the Teams Phone Agent menu option associated with the action.<br>- **Result** - The end result of the action.^See Known Issue 1^ |

#### Teams Phone Agent Usage Details Notes

1. Admins without a voice applications policy or with a voice applications policy where the auto attendant historical reporting permissions are set to `None` or `Only authorized auto attendants`: ↩

- Reporting is by the Resource Account username.
- Nested Teams Phone Agents or Auto attendants that receive calls through a `Voice App` transfer report those calls under the Teams Phone Agent or Auto Attendant GUID.
- To see the calls for a specific Teams Phone Agent, select the resource accounts assigned to that Teams Phone Agent.
- Resource accounts are shown by their username.
    - For example: If the full Resource Account name is **tpa\_test@microsoft.com**, then this value is: **tpa\_test**.

2. Admins with a voice applications policy where the auto attendant historical reporting permissions are set to `All` or Authorized users: ↩

- Reporting is by Teams Phone Agent name.

3. This report is not currently available for Queues App users.

#### Teams Phone Agent Usage Details Known issues

1. These fields are not localized. ↩

### Cloud Auto Attendant Analytics

Expand to see how to interpret the Cloud Auto Attendant Analytics report, for notes and known issues

[![Screenshot showing sample Cloud Auto Attendant Analytics report.](media/aa-cq/historical-report-sample-v332-auto-attendant-callouts.png)](media/aa-cq/historical-report-sample-v332-auto-attendant-callouts.png#lightbox)

| Callout | Title | Description |
| --- | --- | --- |
| 1 | Version | The report version and link to this documentation. |
| 2 | Language | The selected language and locale. |
| 3 | Report Level | The selected report level. |
| 4 | UTC Offset | The selected UTC offset. |
| 5 | Feedback | Provide your feedback on the reports. |
| 6 | Date | The start and end date of the report.Use this slider to select the date range to report on. |
| 7 | Time Range | The start and end hour of the report. The report spans all dates/times from start date/start hour to the end date/end hour.Use this slider to select the time range to report on. |
| 8 | Auto Attendant Resource AccountAuto Attendant | **Admins:** The Resource Accounts to report on.^See Note 1^**Admins or Auth Users:** The Auto Attendant to report on.^See Note 2^Default: All |
| 9 | Messages | Informational messages |
| 10 | Quick Stats -&gt; Incoming Calls | The breakdown shows the total number of calls received between the start date/start hour and end date/end hour.<br>- **External** - the call originated from outside the tenant<br>- **Internal** - the call originated from inside the tenant<br>- **Click2Call** - the call originated from the web<br>- **Other** - the call originated from some other method<br><br>*TIP: Hover over any metric in this section to display a tooltip with the individual calls that make up the total.* |
| 11 | Quick Stats -&gt; Usage Statistics | The breakdown shows the average call duration in the Auto Attendant and the average number of caller actions. |
| 12 | Quick Stats -&gt; Directory Search Method | The breakdown shows how the Directory Search option was used by callers.This section of the report is blank if the Auto Attendant isn't configured for this service or if callers don't use it.<br>- **DTMF** - Caller used the telephone dial pad to search for the user's name<br>- **Voice** - Caller used voice input to search for the user's name |
| 13 | Caller Action Count | The breakdown on the number of caller actions (key presses, voice commands) |
| 14 | Call Results | The breakdown shows the call treatment received by callers.<br>- **Terminated (No Caller Action)** - Call was disconnected - the caller didn't make any selections<br>- **Terminated (With Caller Action)** - Call was disconnected - the caller made selections<br>- **Terminated (Disconnected)** - Call was disconnected per the auto attendant configuration<br>- **Terminated (No Operator)** - Call was disconnected as there was no operator to transfer the call to<br>- **Terminated (Transfer Failed)** - Call was disconnected as the configured transfer failed<br>- **Transferred (AA)** - Call was transferred to another Auto Attendant<br>- **Transferred (CQ)** - Call was transferred to a Call Queue<br>- **Transferred (Operator)** - Call was transferred to the Operator<br>- **Transferred (Voicemail)** - Call was transferred to Shared Voicemail<br>- **Transferred (External)** - Call was transferred to an External Number<br>- **Transferred (User)** - Call was transferred to a Person in the organization<br>- **Other** - Some other condition occurred<br><br>*TIP: Hover over any metric in this section to display a tooltip with the individual calls that make up the total.* |
| 15 |  | Breakdown showing the caller paths through the auto attendant and the final call result.<br>- **MM-DD** - The month and day of the call<br>- **Start Hour** - The hour the call started<br>- **Name** - The Resource Account name<br>- **Call flow** - The call flow the call followed. See [Auto Attendant dimensions -&gt; AutoAttendantCallFlow](aa-cq-report-historical-custom#auto-attendant-dimensions)<br>- **Call Type** - The connectivity method for the call. CallingPlan, DirectRouting, or TeamsPhoneMobile<br>- **Call Result** - The end result of the call (see #12 Call Results)<br>- **Call Count** - The number of calls that followed this same path<br>- **Average Call Duration (seconds)** - The average number of seconds the call spent in the Auto Attendant<br><br>*TIP: Hover over any metric in this section to display a tooltip with the individual calls that make up the total.* |

#### Auto Attendant Analytics Notes

1. Admins without a voice applications policy or Admins with a voice applications policy where the Auto attendant historical reporting permissions are set to `None` or `Only authorized auto attendants`: ↩

- Reporting is by the Resource Account name.
- Nested Auto attendants that receive calls through a `Voice App` transfer report those calls under the Auto attendant GUID.
- To see the calls for a specific Auto attendant, select the resource accounts assigned to that Auto attendant.
- Resource accounts are shown by their username.
    - For example: If the full Resource Account name is **aa\_test@microsoft.com**, then this value is: **aa\_test**.

2. Admins with a voice applications policy where the Auto attendant historical reporting permissions are set to `All` or Authorized users: ↩

- Reporting is by Auto Attendant name.

3. Queues App users:

- Reporting is by the Resource Account username.
- Reports are in UTC.

#### Auto Attendant Analytics Known issues

No known issues.

### Cloud Call Queue Analytics

Expand to see how to interpret the Cloud Call Queue Analytics report, for notes and known issues

[![Screenshot showing sample Cloud Call Queue Analytics report.](media/aa-cq/historical-report-sample-v332-call-queue-callouts.png)](media/aa-cq/historical-report-sample-v332-call-queue-callouts.png#lightbox)

| Callout | Title | Description |
| --- | --- | --- |
| 1 | Version | The report version and link to this documentation. |
| 2 | Language | The selected language and locale. |
| 3 | Report Level | The selected report level. |
| 4 | UTC Offset | The selected UTC offset. |
| 5 | Feedback | Provide your feedback on the reports. |
| 6 | Date | The start and end date of the report.Use this slider to select the date range to report on. |
| 7 | Time Range | The start and end hour of the report. The report spans all dates/times from start date/start hour to the end date/end hour.Use this slider to select the time range to report on. |
| 8 | Call Queue Resource AccountCall Queue | **Admins:** The Resource Accounts to report on.^See Note 1^**Admins or Auth Users:** The Call Queue to report on.^See Note 2^Default: All |
| 9 | Messages | Informational messages |
| 10 | Quick Stats -&gt; Incoming Calls | The breakdown shows the total number of calls received between the start date/start hour and end date/end hour.<br>- **External** - the call originated from outside the tenant<br>- **Internal** - the call originated from inside the tenant<br>- **Click2Call** - the call originated from the web<br>- **Other** - the call originated from some other method<br><br>*TIP: Hover over any metric in this section to display a tooltip with the individual calls that make up the total.* |
| 10 | Quick Stats -&gt; Average Wait Time (seconds) | The breakdown shows the average call duration in the Call Queue before a caller is answered or they abandon. |
| 11 | Call Results | The breakdown shows the call treatment received by callers.<br>- **Abandoned** - Caller disconnected before a representative (agent) answered or before Call Timeout occurred<br>- **Agent Answered** - Caller was answered by a representative (agent)<br>- **Overflowed** - The Call Overflow exception handling condition occurred<br>- **Timed Out** - The Call Timeout exception handling occurred<br>- **No Agents** - The No Agent exception handling condition occurred<br>- **Other** - Some other condition occurred<br><br>*TIP: Hover over any metric in this section to display a tooltip with the individual calls that make up the total.* |
| 12 | Call Volume, Abandoned Calls, Agent Opt-in Count | The breakdown shows the number of calls received and abandoned per hour and the maximum number of representatives (agents) that were opted into the call queue at that time |
| 13 | Average Session Length (seconds) | The breakdown shows how long calls waited before each call result.<br>- **Agent Answered (Call)** - for calls answered by a representative (agent)<br>- **Agent Answered (Callback)** - for callbacks answered by a representative (agent)<br>- **Abandoned** - for calls abandoned before a representative (agent) answered or before Call Timeout occurred<br>- **Overflowed (Disconnect)** - for calls where the Call Overflow exception handling occurred and the treatment was to disconnect<br>- **Overflowed (Xferred)** - for calls where the Call Overflow exception handling occurred and the treatment was to transfer the caller to a Person in the organization or externally<br>- **Overflowed (Voicemail)** - for calls where the Call Overflow exception handling occurred and the treatment was to send the call to shared voicemail<br>- **Timed Out (Disconnect)** - for calls where the Call Timeout exception handling occurred and the treatment was to disconnect<br>- **Timed Out (Xferred)** - for calls where the Call Timeout exception handling occurred and the treatment was to transfer the caller to a Person in the organization or externally<br>- **Timed Out (Voicemail)** - for calls where the Call Timeout exception handling occurred and the treatment was to send the call to shared voicemail<br>- **No Agents (Disconnect)** - for calls where the No Agents exception handling occurred and the treatment was to disconnect<br>- **No Agents (Xferred)** - for calls where the No Agents exception handling occurred and the treatment was to transfer the caller to a Person in the organization or externally<br>- **No Agents (Voicemail)** - for calls where the No Agents exception handling occurred and the treatment was to send the call to shared voicemail<br>- **Other** - for calls where some other condition occurred |
| 14 | Call Overflow/Timeout/No Agents Destinations | The breakdown shows where the calls that received the Call Overflow, Call Timeout, or No Agents exception handling treatment were sent.<br>- **ApplicationEndpoint** - call was transferred to another Auto Attendant or Call Queue<br>- **Mailbox** - call was transferred to shared voicemail<br>- **Other** - some other condition occurred<br>- **Phone** - call was transferred externally<br>- **User** - call was transferred to a Person in the organization |

#### Call Queue Analytics Notes

1. Admins without a voice applications policy or Admins with a voice applications policy where the Call queue historical reporting permissions are set to `None` or `Only authorized auto attendants`: ↩

- Reporting is by the Resource Account name.
- Nested Call queues that receive calls through a `Voice App` transfer report those calls under the Resource Account username that performs the transfer.
- To see the calls for a specific Call queue, select the resource accounts assigned to that Call queue or, if nesting, the resource accounts that perform the transfers.
- Resource accounts are shown by their username.
    - For example: If the full Resource Account name is **aa\_test@microsoft.com**, then this value is: **aa\_test**.

2. Admins with a voice applications policy where the Call queue historical reporting permissions are set to `All` or Authorized users: ↩

- Reporting is by Call queue name.

3. Queues App users:

- Reporting is by the Resource Account username.
- Reports are in UTC.

#### Call Queue Analytics Known issues

No known issues.

### Cloud Call Queue Agent Timeline

Expand to see how to interpret the Cloud Call Queue Agent Timeline report, for notes and known issues

[![Screenshot showing sample Cloud Call Queue Agent Timeline report - inside.](media/aa-cq/historical-report-sample-v332-agent-timeline-callouts.png)](media/aa-cq/historical-report-sample-v332-agent-timeline-callouts.png#lightbox)

| Callout | Title | Description |
| --- | --- | --- |
| 1 | Version | The report version and link to this documentation. |
| 2 | Language | The selected language and locale. |
| 3 | Report Level | The selected report level. |
| 4 | UTC Offset | The selected UTC offset. |
| 5 | Feedback | Provide your feedback on the reports. |
| 6 | Date | The start and end date of the report.Use this slider to select the date range to report on. |
| 7 | Agent Username | The representatives (agents) to report on. If the full username is **user@microsoft.com**, then this value is: **user**Default: All |
| 8 | Call Queue Resource AccountCall Queue | **Admins:** The Resource Accounts to report on.^See Note 1^**Admins or Auth Users:** The Call Queue to report on.^See Note 2^Default: All |
| 9 | Messages | Informational messages |
| 10 | Quick Stats -&gt; Incoming Calls | The breakdown shows the total number of calls answered, the average number of calls answered per representative (agent), and the average call length of answered calls handled.^See Known Issue 1^*TIP: Hover over any metric in this section to display a tooltip with the individual calls that make up the total.* |
| 11 |  | The breakdown shows how many calls each representative (agent) in the queue answered and the average call duration for those calls. |
| 12 | Calls Answered (by date) | The breakdown shows the number of agent-answered calls by date |
| 13 | Calls Answered (by hour) | The breakdown shows the number of agent-answered calls by hour |
| 14 |  | The breakdown shows the number of calls answered by a representative (agent), by Call Queue.<br>- **MM-DD** - The month and day of the call<br>- **Hour** - The hour the call was answered<br>- **CQ Name** - The Resource Account name<br>- **Agent Name** - The URI name of the agent who answered the call<br>- **Calls Answered** - The number of calls answered by this representative (agent) from this Call Queue<br>- **Average Call Duration (Seconds)** - The average call duration of each call in seconds<br>- **Total Call Duration (Minutes)** - The total call duration for all calls<br>- **Total Call Duration (HH:MM:SS)** - The total call duration for all calls |

#### Agent Timeline Analytics Notes

1. Admins without a voice applications policy or Admins with a voice applications policy where the Call queue historical reporting permissions are set to `None` or `Only authorized auto attendants`: ↩

- Reporting is by the Resource Account name.
- Nested Call queues that receive calls through a `Voice App` transfer report those calls under the Resource Account username that performs the transfer.
- To see the calls for a specific Call queue, select the resource accounts assigned to that Call queue or, if nesting, the resource accounts that perform the transfers.
- Resource accounts are shown by their username.
    - For example: If the full Resource Account name is **aa\_test@microsoft.com**, then this value is: **aa\_test**.

2. Admins with a voice applications policy where the Call queue historical reporting permissions are set to `All` or Authorized users: ↩

- Reporting is by Call queue name.

3. Queues App users:

- Reporting is by the Resource Account username.
- Reports are in UTC.

#### Agent Timeline Analytics Known issues

1. The agent's UPN name instead of their name is shown. ↩

2. If a representative (agent) answers a redirected call from another queue due to Call Overflow, the call counts towards the original queue where the overflow happened, not the queue where it was answered.

3. Callback calls handled by representatives (agents) aren't tracked, so the Call Queue report and Agent Timeline report show different numbers of answered calls.

4. If the user is not authorized to see agent metrics, the Agent Timeline report is blank and no message is displayed.

### Cloud Call Flow Details

Expand to see how to interpret the Cloud Call Flow Details report, for notes and known issues

[![Screenshot showing sample Cloud Call Flow Details report - inside.](media/aa-cq/historical-report-sample-v332-call-flow-details-callouts.png)](media/aa-cq/historical-report-sample-v332-call-flow-details-callouts.png#lightbox)

| Callout | Title | Description |
| --- | --- | --- |
| 1 | Version | The report version and link to this documentation. |
| 2 | Language | The selected language and locale. |
| 3 | Report Level | The selected report level.^See Note 1^ |
| 4 | UTC Offset | The selected UTC offset. |
| 5 | Feedback | Provide your feedback on the reports. |
| 6 | Date | The start and end date of the report.Use this slider to select the date range to report on. |
| 7 | Messages | Informational messages. |
| 8 |  | Breakdown showing each leg of every call.<br>- **Start Time** - the start time of the call.<br>- **Leg** - the leg or segment of the call.<br>- **Teams Phone Agent / Auto Attendant Resource Account** or **Teams Phone Agent / Auto Attendant**<br>    - **Admins** - Teams Phone Agent / Auto Attendant Resource Account.^See Note 2^<br>    - **Admins or Auth Users** -- Teams Phone Agent / Auto Attendant.^See Note 3^<br>    - **Call Duration (seconds)** - the call duration in the Teams Phone Agent / Auto Attendant portion of the call.<br>    - **Call Result** - the Teams Phone Agent / Auto Attendant call result.<br>    - **Call Queue Resource Account** - **Admins** --- put stuff here**Admins or Authorized Users** --- put stuff here<br>    - **Call Queue Call Duration (seconds)** - the call duration in the Call Queue portion of the call.<br>    - **Call Queue Call Result** - the Call Queue call result.<br>    - **Agent Username** - the username of the agent who answered the call.<br>    - **Talk Time (seconds)** - the amount of time the agent spoke with the caller. |

#### Call Flow Details Notes

1. The report is only available in Per-Call mode. ↩

2. Admins without a voice applications policy or Admins with a voice applications policy where the Call queue historical reporting permissions are set to `None` or `Only authorized auto attendants`: ↩

- Reporting is by the Resource Account name.
- Nested Call queues that receive calls through a `Voice App` transfer report those calls under the Resource Account username that performs the transfer.
- Resource accounts are shown by their username.
    - For example: If the full Resource Account name is **aa\_test@microsoft.com**, then this value is: **aa\_test**.

3. Admins with a voice applications policy where the Call queue historical reporting permissions are set to `All` or Authorized users: ↩

- Reporting is by Call queue name.

4. This report is not currently available for Queues App users.

#### Cloud Call Flow Details Known issues

1. If there are 4900 or more agent call records, a message is displayed about not being authorized and, the agent data is not shown on the report.

## Reporting by representative's name vs UPN

Caution

This is only supported when the reports are running in Power BI Desktop.

Publishing a report with this modification to the Power BI service disables the ability to schedule refreshes.

This customization results in the Agent Timeline report showing representative names instead of usernames.

This customization requires registering an Entra ID application.

Expand to see customization steps

These instructions assume that you have the AA/CQ Historical Reports templates installed and working on your desktop.

### Register an Entra ID application

In the Azure portal:

1. Go to **Microsoft Entra ID** &gt; **App registrations**.
2. Select **New registration**.
3. Copy the following values:
    - Tenant ID
    - Client ID
4. Create a client secret.
    - Make sure to copy this client secret immediately after creating it, as there's no way to retrieve it once you leave the creation page.
5. Grant Microsoft Graph permissions such as:
    - User.Read.All
    - Group.Read.All
6. Grant admin consent.

### Set up the Power BI report

1. Open the reports.
2. Select **Transform data**.
3. Under **Queries**:
    - Select **TenantID** and paste in the value from step 3 above.
    - Select **ClientID** and paste in the value from step 3 above.
    - Select **ClientSecret** and paste in the value from step 4 above.
4. Select **TeamsUsers**.
5. Select **Advanced Editor**.
6. Delete all the text that shows.
7. Copy the text below.
8. Paste it into the Power BI editor.

```
let
    TeamsUserInvalidConfig = if Text.Length(TenantID) = 0 or Text.Length(ClientID) = 0 or Text.Length(ClientSecret) = 0 then true else false,

    GetAllPagesURL = if #"Tenant Location" = "Department of Defence (DoD)" then
                "https://dod-graph.microsoft.us/v1.0/users?$select=displayName,userPrincipalName,id"
            else if #"Tenant Location" = "Government Community Cloud High (GCCH)" then
                "https://graph.microsoft.us/v1.0/users?$select=displayName,userPrincipalName,id"
            else  // Public Cloud
                "https://graph.microsoft.com/v1.0/users?$select=displayName,userPrincipalName,id",
    
    TokenResponse = if TeamsUserInvalidConfig then
            null
        else
            if #"Tenant Location" = "Department of Defence (DoD)" then
                Json.Document(
                    Web.Contents(
                        "https://login.microsoftonline.us",
                        [
                            RelativePath = TenantID & "/oauth2/v2.0/token",
                            Headers = [
                                #"Content-Type" = "application/x-www-form-urlencoded"
                            ],
                            Content =
                                Text.ToBinary(
                                    Uri.BuildQueryString([
                                        client_id = ClientID,
                                        scope = "https://graph.microsoft.com/.default",
                                        client_secret = ClientSecret,
                                        grant_type = "client_credentials"
                                    ])
                                )
                        ]
                    )
                )
            else if #"Tenant Location" = "Government Community Cloud High (GCCH)" then
                 Json.Document(
                    Web.Contents(
                        "https://login.microsoftonline.us",
                        [
                            RelativePath = TenantID & "/oauth2/v2.0/token",
                            Headers = [
                                #"Content-Type" = "application/x-www-form-urlencoded"
                            ],
                            Content =
                                Text.ToBinary(
                                    Uri.BuildQueryString([
                                        client_id = ClientID,
                                        scope = "https://graph.microsoft.com/.default",
                                        client_secret = ClientSecret,
                                        grant_type = "client_credentials"
                                    ])
                                )
                        ]
                    )
                )
            else // Public Cloud
                Json.Document(
                    Web.Contents(
                        "https://login.microsoftonline.com",
                        [
                            RelativePath = TenantID & "/oauth2/v2.0/token",
                            Headers = [
                                #"Content-Type" = "application/x-www-form-urlencoded"
                            ],
                            Content =
                                Text.ToBinary(
                                    Uri.BuildQueryString([
                                        client_id = ClientID,
                                        scope = "https://graph.microsoft.com/.default",
                                        client_secret = ClientSecret,
                                        grant_type = "client_credentials"
                                    ])
                                )
                        ]
                    )
                ),

    AccessToken = if TeamsUserInvalidConfig then
            null
        else
            TokenResponse[access_token],

    GetPage = if TeamsUserInvalidConfig then
            null
        else
            (url as text) =>
            let
                Source = Json.Document(
                    Web.Contents(
                        url,
                        [
                            Headers = [
                                Authorization = "Bearer " & AccessToken
                            ]
                        ]
                    )
                )
            in
                Source,

    GetAllPages = if TeamsUserInvalidConfig then
            null
        else
            (url as text) =>
            let
                Pages =
                    List.Generate(
                        () => GetPage(url),
                        each _ <> null,
                        each
                            if Record.HasFields(_, "@odata.nextLink")
                            then GetPage(_[#"@odata.nextLink"])
                            else null,
                        each _[value]
                    ),

                Combined = List.Combine(Pages)
            in
                Combined,

    Result = if TeamsUserInvalidConfig then
            Table.FromRows(
                {
                    { "", "", "" }
                },
                { "displayName", "userPrincipalName", "id"}
            )
        else
            GetAllPages(GetAllPagesURL),

    UsersTable = if TeamsUserInvalidConfig then
            Result
        else
            Table.FromRecords(Result),

    // converting to lower case as AgentTimeline is all lower case
    LowerCaseColumn = Table.TransformColumns(
        UsersTable,
        {{"userPrincipalName", Text.Lower, type text}}
    )

in
    LowerCaseColumn
```

## Localization

Expand to see the list of supported locales and known localization issues

### Supported locales

| Languages (Locales) | Languages (Locales) |
| --- | --- |
| Arabic (Saudi Arabia) | Irish (Ireland) |
| Bangla (Bangladesh) | Italian (Italy) |
| Bulgarian (Bulgaria) | Japanese (Japan) |
| Catalan (Catalan) | Korean (Korea) |
| Chinese (Simplified, Hong Kong SAR) | Latin (Vatican City) |
| Chinese (Traditional, Taiwan) | Latvian (Latvia) |
| Croatian (Croatia) | Lithuanian (Lithuania) |
| Czech (Czechia) | Maltese (Malta) |
| Danish (Denmark) | Norwegian Bokmål (Norway) |
| Dutch (Netherlands) | Norwegian Nynorsk (Norway) |
| English (Australia) | Polish (Poland) |
| English (United Kingdom) | Portuguese (Brazil) |
| English (United States) | Portuguese (Portugal) |
| Esperanto (World) | Romanian (Romania) |
| Estonian (Estonia) | Russian (Russia) |
| Filipino (Philippines) | Serbian (Latin, Serbia) |
| Finnish (Finland) | Slovak (Slovakia) |
| French (Canada) | Slovenian (Slovenia) |
| French (France) | Spanish (Mexico) |
| German (Germany) | Spanish (Spain, International Sort) |
| Greek (Greece) | Swedish (Sweden) |
| Hebrew (Israel) | Thai (Thailand) |
| Hindi (India) | Turkish (Türkiye) |
| Hungarian (Hungary) | Ukrainian (Ukraine) |
| Icelandic (Iceland) | Vietnamese (Vietnam) |
| Indonesian (Indonesia) | Welsh (United Kingdom) |

Note

Translations/localizations were performed by Artificial Intelligence and may contain errors.

Use the [Teams Voice Applications Historical Reporting Feedback](https://go.microsoft.com/fwlink/?LinkId=2375135) form to report any translation/localization issues.

### Localization known issues

1. The selected language applies to the reports only and not the Power BI components or tooltips. Power BI defaults to the same language as the Windows desktop.

    To change the Power BI language, select:

    - File
    - Options and Settings
    - Options
    - Regional Settings
    - Application Language
        - Default set to "Use Windows default display language."
        - Select the desired language from the dropdown. 
            Note

            The list of languages shown here might be different than languages available for the report template.
2. The name of the zip file and the actual report template files are in English only.
3. The splash screen shows the filename (see #2) and the words "Tenant Location," "Language," and "UTC Offset" in English only.
4. The refresh screen shows the table names in English only.
5. The report tab names are in English only.
6. The documentation link uses the language set in your browser, which might be different than the language selected for the report.
7. The legend on the **Call Queue - Call Volume, Abandoned Calls and Agent Opt-in Count** visual is in English only.
8. The following customer provided information isn't localized:

    - Resource account names
    - Teams Phone Agent, Auto Attendant, and Call Queue names
    - Teams Phone Agent Analytics -&gt; Categories
        - These come from the Voice Commands configuration
    - Teams Phone Agent Usage Details
        - Voice
        - Schedule
        - Menu Option and Menu Option Description
            - These comes from the Voice Commmand and Description configuration

    Issues 2-6 are limitations of file naming conventions, screens in Power BI, and how browsers work. These issues won't be addressed.

## Data limits

Each report tab retrieves data for all Teams Phone Agents, Auto Attendants, Call Queues, or agents the user is authorized for in the tenant for the selected date range. This data retrieval occurs regardless of the selections on the report. Filtering to show only the requested information occurs locally.

**Each report tab is restricted to retrieving 150,000 rows.**

If there's a large number of calls being processed each day, it's possible that the report doesn't show all calls for all days within the selected date range. There's no notification when this exclusion occurs. Try shortening the date range to avoid this issue.

If shortening the date range isn't sufficient, it's possible to increase the number of rows that can be retrieved by modifying the report as follows:

1. Select **Transform data** in the ribbon bar to open the Power Query Editor.
2. Select **ReportRowCountLimit** on the left-hand side.
3. Change the value in the field to the right to a larger number.
4. Close the Power Query Editor window.
5. Select **Yes** when prompted to apply the changes now. The report should automatically refresh.
6. Save your report.

There's no limit to the number of rows that can be retrieved. However, increasing the row count might lead to longer execution and response times, which can impact desktop performance.

## Report execution time limits

Increasing the maximum number of rows that can be returned results in longer execution and response times, meaning the report might time out before the data can be returned. The report execution time can be increased by modifying the report as follows:

1. Select **Transform data** in the ribbon bar to open the Power Query Editor.
2. Select **ReportExecutionMinutes** on the left-hand side.
3. Change the value in the field to the right to a larger number.
4. Close the Power Query Editor window.
5. Select **Yes** when prompted to apply the changes now. The report should automatically refresh.
6. Save your report.

## Customization

The colors used for the visual text, background, and data points can be fully customized through the **ReportTheme** settings.

Expand for details on how to customize the visual text, background, and data points

The 16 base color settings are:

| Variable name | HEX color code |
| --- | --- |
| \_black | #000000 |
| \_aqua | #00FFFF |
| \_blue | #0000FF |
| \_fuchsia | #FF00FF |
| \_gray | #808080 |
| \_green | #008000 |
| \_lime | #00FF00 |
| \_maroon | #800000 |
| \_navy | #000080 |
| \_olive | #808000 |
| \_purple | #800080 |
| \_red | #FF0000 |
| \_silver | #C0C0C0 |
| \_teal | #008080 |
| \_white | #FFFFFF |
| \_yellow | #FFFF00 |

### Report titles

- Teams Phone Agent

    [![Screenshot showing the Teams Phone Agent titles from the reports.](media/aa-cq/historical-report-customization-title-teams-phone-agent.png)](media/aa-cq/historical-report-customization-title-teams-phone-agent.png#lightbox)
- Teams Phone Agent Usage Details

    [![Screenshot showing the Teams Phone Agent Usage Details titles from the reports.](media/aa-cq/historical-report-customization-title-teams-phone-agent-usage-details.png)](media/aa-cq/historical-report-customization-title-teams-phone-agent-usage-details.png#lightbox)
- Auto Attendant

    [![Screenshot showing the Auto Attendant titles from the reports.](media/aa-cq/historical-report-customization-title-auto-attendant.png)](media/aa-cq/historical-report-customization-title-auto-attendant.png#lightbox)
- Call Queue

    [![Screenshot showing the Call Queue titles from the reports.](media/aa-cq/historical-report-customization-title-call-queue.png)](media/aa-cq/historical-report-customization-title-call-queue.png#lightbox)
- Agent Timeline

    [![Screenshot showing the Agent Timeline titles from the reports.](media/aa-cq/historical-report-customization-title-agent-timeline.png)](media/aa-cq/historical-report-customization-title-agent-timeline.png#lightbox)
- Call Flow Details

    [![Screenshot showing the Call Flow Details titles from the reports.](media/aa-cq/historical-report-customization-title-call-flow-details.png)](media/aa-cq/historical-report-customization-title-call-flow-details.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_titleBackgroundPublicCloud | \_navy |
    | \_titleBackgroundGCCH | \_blue |
    | \_titleBackgroundDoD | \_purple |
    | \_titleText | \_white |
    | \_titleIcon | \_white |

### Report slicers

- Date

    [![Screenshot showing the date slicer from the reports.](media/aa-cq/historical-report-customization-slicer-date.png)](media/aa-cq/historical-report-customization-slicer-date.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_slicerDate | #8661C5 |

- Time

    [![Screenshot showing the time slicer from the reports.](media/aa-cq/historical-report-customization-slicer-time.png)](media/aa-cq/historical-report-customization-slicer-time.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_slicerTime | #006CF0 |

- Agent username

    [![Screenshot showing the agent slicer from the reports.](media/aa-cq/historical-report-customization-slicer-agent.png)](media/aa-cq/historical-report-customization-slicer-agent.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_slicerAgent | #006CF0 |

[![Screenshot showing the Teams Phone Agent slicer from the reports.](media/aa-cq/historical-report-customization-slicer-teams-phone-agent.png)](media/aa-cq/historical-report-customization-slicer-teams-phone-agent.png#lightbox)[![Screenshot showing the auto attendant slicer from the reports.](media/aa-cq/historical-report-customization-slicer-auto-attendant.png)](media/aa-cq/historical-report-customization-slicer-auto-attendant.png#lightbox)[![Screenshot showing the call queue slicer from the reports.](media/aa-cq/historical-report-customization-slicer-call-queue.png)](media/aa-cq/historical-report-customization-slicer-call-queue.png#lightbox)

| Variable Name | HEX color Code |
| --- | --- |
| \_slicerApp | #464EB8 |

### Messages box

[![Screenshot showing the messages box section from the reports.](media/aa-cq/historical-report-customization-messages-box.png)](media/aa-cq/historical-report-customization-messages-box.png#lightbox)

| Variable Name | HEX color Code | Notes |
| --- | --- | --- |
| \_messageBackground | \_white |  |
| \_messageBorder | \_black |  |
| \_messageTitle | \_black |  |
| \_messageTextNotAuth | \_red |  |
| \_messageTextTemplateCurrent | \_messageBackground | Feature not available yet |
| \_messageTextTemplateOutdated | \_messageBackground | Feature not available yet |
| \_messageTextDefault | \_black |  |

### Quick stats

- Teams Phone Agent

    [![Screenshot showing the Teams Phone Agent quick stats section from the reports.](media/aa-cq/historical-report-customization-quick-stats-teams-phone-agent.png)](media/aa-cq/historical-report-customization-quick-stats-teams-phone-agent.png#lightbox)
- Auto Attendant

    [![Screenshot showing the Auto Attendant quick stats section from the reports.](media/aa-cq/historical-report-customization-quick-stats-auto-attendant.png)](media/aa-cq/historical-report-customization-quick-stats-auto-attendant.png#lightbox)
- Call Queue

    [![Screenshot showing the Call Queue quick stats section from the reports.](media/aa-cq/historical-report-customization-quick-stats-call-queue.png)](media/aa-cq/historical-report-customization-quick-stats-call-queue.png#lightbox)
- Agent Timeline

    [![Screenshot showing the Agent Timeline quick stats section from the reports.](media/aa-cq/historical-report-customization-quick-stats-agent-timeline.png)](media/aa-cq/historical-report-customization-quick-stats-agent-timeline.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_qsBackground | \_white |
    | \_qsBorder | \_black |
    | \_qsTitle | \_black |
    | \_qsMetricBackground | \_white |
    | \_qsMetric | \_black |
    | \_qsMetricTitle | \_black |
    | \_qsInfoBackground | \_white |
    | \_qsInfoBorder | \_gray |
    | \_qsInfoTitle | \_gray |

### Bar chart visuals

- Teams Phone Agent

    [![Screenshot showing the Teams Phone Agent bar chart visuals from the reports.](media/aa-cq/historical-report-customization-visuals-teams-phone-agent-bar-chart.png)](media/aa-cq/historical-report-customization-visuals-teams-phone-agent-bar-chart.png#lightbox)
- Auto Attendant

    [![Screenshot showing the Auto Attendant bar chart visuals from the reports.](media/aa-cq/historical-report-customization-visuals-auto-attendant-bar-chart.png)](media/aa-cq/historical-report-customization-visuals-auto-attendant-bar-chart.png#lightbox)
- Call Queue

    [![Screenshot showing the Call Queue bar chart visuals from the reports.](media/aa-cq/historical-report-customization-visuals-call-queue-bar-chart.png)](media/aa-cq/historical-report-customization-visuals-call-queue-bar-chart.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_barChartText | \_black |
    | \_barChartBars | "#E9DEFB" |
    | \_barChartsDataLabels | \_black |
    | \_barChartTitle | \_black |
    | \_barChartBackground | \_white |
    | \_barChartBorder | \_black |

### Line cluster visuals

- Call Queue

    [![Screenshot showing the Call Queue line and clustered column visuals from the reports.](media/aa-cq/historical-report-customization-visuals-call-queue-line-clustered-column-chart.png)](media/aa-cq/historical-report-customization-visuals-call-queue-line-clustered-column-chart.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_lineClusterText | \_barChartText |
    | \_lineClusterLegendText | \_lineClusterText |
    | \_lineClusterDataLabels | \_barChartsDataLabels |
    | \_lineClusterTitle | \_barChartTitle |
    | \_lineClusterBackground | \_barChartBackground |
    | \_lineClusterBorder | \_barChartBorder |

### Stacked column visuals

- Agent Timeline

    [![Screenshot showing the Agent Timline stacked column visuals from the reports.](media/aa-cq/historical-report-customization-visuals-agent-timeline-stacked-column-chart.png)](media/aa-cq/historical-report-customization-visuals-agent-timeline-stacked-column-chart.png#lightbox)

    | Variable Name | HEX color Code |
    | --- | --- |
    | \_stackedColumnText | \_barChartText |
    | \_stackedColumnBars | \_barChartBars |
    | \_stackedColumnDataLabels | \_barChartsDataLabels |
    | \_stackedColumnTitle | \_barChartTitle |
    | \_stackedColumnBackground | \_barChartBackground |
    | \_stackedColumnBorder | \_barChartBorder |

## Version 3.x.x history and support status

Refer to Teams Auto Attendant & Call Queue Historical Reports - Change Log.docx in the downloaded zip file for a detailed list of changes.

| Version | Date Published | Supported | Filename | Description |
| --- | --- | --- | --- | --- |
| 3.3.2 | Sepetember 29, 2026 | Yes | Teams Voice Applications Historical Reports V3.3.2 | New Call Flow Details report, new Teams Phone Agent Usage Details report, simplified report color customization, report feedback option, performance enhancements, four new langauges/locales supported, bug fixes. |
| 3.3.1 | July 20, 2026 | No | Teams Auto Attendant & Call Queue Historical Reports V3.3.1 | Support for Teams Phone Agent, Power BI desktop users can report by agent name instead of username, bug fixes. |
| 3.3.0 | July 6, 2026 | No | Teams Auto Attendant & Call Queue Historical Reports V3.3.0 | Support for Government Community Cloud High (GCCH) and Department of Defense (DoD) tenants. |
| 3.2.6 | March 5, 2026 | No | Teams Auto Attendant & Call Queue Historical Reports V3.2.6 | Corrected a problem that prevented scheduling on the Power BI service, accessibility improvements. |
| 3.2.5 | February 4, 2026 | No | Teams Auto Attendant & Call Queue Historical Reports V3.2.5 | Corrected a problem that prevented the Auto Attendant and Call Queue templates from loading when a `TeamsPhoneMobile` service phone number was used. |
| 3.2.4 | February 2, 2026 | No | Teams Auto Attendant & Call Queue Historical Reports V3.2.4 | Corrected a problem that prevented scheduling on the Power BI service, accessibility improvements. |
| 3.2.3 | January 12, 2026 | No | Teams Auto Attendant & Call Queue Historical Reports V3.2.3 | Introduced `Tenant Location` dropdown selection in preparation for more cloud locations, sequential loading of queries, code rewrite. |
| 3.2.2 | August 25, 2025 | No | Teams Auto Attendant & Call Queue Historical Reports V3.2.2 | Bug fixes, increased default row limit and execution time. |
| 3.2.1 | June 23, 2025 | No | Teams Auto Attendant & Call Queue Historical Reports V3.2.1 | Bug fixes. |
| 3.2.0 | March 21, 2025 | No | Teams Auto Attendant & Call Queue Historical Reports V3.2.0 | Localization in 45 languages, reporting by Auto Attendant and Call Queue name for authorized users. |
| 3.1.8 | August 12, 2024 | No | Teams Auto Attendant & Call Queue Historical Reports V3.1.8 | Bug fix for Date slicer on Call Queue tab. |
| 3.1.7 | July 15, 2024 | No | Teams Auto Attendant & Call Queue Historical Reports V3.1.7 | Improved support for authorized users, removed original reporting templates. |
| 3.1.6 | April 15, 2024 | No | Teams Auto Attendant & Call Queue Historical Reports V3.1.6 | Support click2call, callback, authorized users, and some visuals changed due to deprecation. |
| 3.1.5 | January 29, 2024 | No | Teams Auto Attendant & Call Queue Historical Reports V3.1.5 | Corrected an error with the Per Day query logic for fAgentTimelineAnalytics and fAgentTimelineAnalyticsSummary. |
| 3.1.4 | January 24, 2024 | No | Teams Auto Attendant & Call Queue Historical Reports V3.1.4 | Per day reporting for large volume customers, accessibility improvements for screen readers. |