---
layout: Conceptual
title: Voice applications historical reports for GCCH and DoD - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-cqd-historical-reports-v164
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
ms.date: 2026-09-30T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ROBOTS: NOINDEX, NOFOLLOW
description: Use the Auto Attendant & Call Queue Historical Report to view historical data for GCCH and DoD customers.
locale: en-us
document_id: ea236a16-80c1-b835-94ea-a870ffa70d7c
document_version_independent_id: ea236a16-80c1-b835-94ea-a870ffa70d7c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-cqd-historical-reports-v164.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-cqd-historical-reports-v164
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-cqd-historical-reports-v164.md
platformId: c1754ba7-01bb-150d-3ec7-01d647471bf4
---

# Voice applications historical reports for GCCH and DoD - Microsoft Teams | Microsoft Learn

Caution

All customers should use V3.x.x of [Voice Applications Historical Reports](aa-cq-report-historical).

Support for the v1.xx templates for Government Community Cloud High (GCCH) and Department of Defence (DoD) customers ended on July 8,2026

This documentation will be removed on December 28, 2026.

## V1.64 published on July 14, 2023

The **Teams Auto Attendant & Call Queue Historical Report Power BI Template** provides the following three reports:

- The [Auto Attendant](media/aa-cq/historical-report-sample-v164-aa.png) report shows analytics for calls coming into your auto attendants.
- The [Call Queue](media/aa-cq/historical-report-sample-v164-cq.png) report shows analytics for calls coming into your call queues.
- The [Agent Timeline](media/aa-cq/historical-report-sample-v164-at.png) report shows a timeline view of agents being active in call queue calls.

These reports use data from the [Call Quality Dashboard (CQD)](cqd-power-bi-query-templates) data store.

## V1.64 Prerequisites

### Power BI Desktop

You need to have Power BI Desktop installed. You can install and use the free version from the [Microsoft Windows Store](https://aka.ms/pbidesktopstore).

The minimum compatible version is 2.85.681.0 (September 2020).

### Permissions to access the CQD pipeline

The account you use to view the historical report needs to have permissions to access the CQD data pipeline. For more information, see [CQD access role](turning-on-and-using-call-quality-dashboard#assign-admin-roles-for-access-to-cqd).

## V1.64 Installation

The following steps assume you installed Power BI Desktop on your computer and your account has the necessary permissions to access the CQD data pipeline.

Perform the following steps:

1. Download and save the [CQD Power BI Query Templates](https://www.microsoft.com/download/details.aspx?id=102291) zip file on your computer.
2. Open the zip file.
3. Navigate to the AACQ subfolder.
4. Open the `CQD Teams Auto Attendant & Call Queue Historical Report V1.64.pbit` template file. Power BI Desktop should launch.
5. Once prompted to select the CQD data pipeline region, choose the region where your tenant is located.

    ![Screenshot selecting the CQD data pipeline region.](media/aa-cq/historical-report-v164-01.png)

    Public Cloud Customers (not supported but works):
6. The region where your tenant is located can be obtained by using the [Get-CsTenant](/en-us/powershell/module/teams/get-cstenant) cmdlet.

    ```powershell
    (Get-CsTenant).ServiceInstance
    
    microsoftcommunicationsonline/noam-4a-s7
    ```

    The region is displayed after the **/** as in the above example where the region is `noam`.

    GCCH and DoD Customers:
7. Select the appropriate CQD data pipeline from the drop-down list:

    - GCCH: `cqd.gov.teams.microsoft.us/data`
    - DoD: `cqd.dod.teams.microsoft.us/data`
8. The report launches with sample data.
9. To see your own data, select **Refresh** on the **Home** tab under **Queries** in Power BI Desktop.

    ![Screenshot selecting the refresh option.](media/aa-cq/historical-report-v164-02.png)
10. When prompted to sign in, select **Organizational account**, and then select **Sign in**.

    ![Screenshot showing login for V1.63.](media/aa-cq/historical-report-v164-03.png)
11. After you select **Connect**, the data refreshes.

## Data latency for Auto Attendant (AA) and Call Queue (CQ) analytics

Data is typically available within 30 minutes of the call completing; however, there are occasions where it might take several hours for data to appear.

You have to refresh the data to see any new data.

## Auto attendant and call queue historical reports definitions

### Cloud Auto Attendant Analytics report

#### Report description

| Report Section | Description |
| --- | --- |
| Incoming Call Source^1^ | Distribution of calls by Internal/External call source |
| Directory Search Method | Distribution of calls by search type |
| Caller Action Count | Distribution of calls by number action used during the call |
| Average Seconds in AA | Average number of seconds callers spend in the AA |
| Average Caller Actions | Average number of actions callers perform in the AA |
| Call Results | Distribution of calls by final call state |
| Lower section of report | Call flow breakdown |

#### Report to CQD table and field mapping

| Report Tab | Report Table Name | Source Table Name | Global Filter |
| --- | --- | --- | --- |
| Auto Attendant | fAutoAttendant | AutoAttendant | None |

| Report Section | Field(s) Used | Filters Applied |
| --- | --- | --- |
| Date selector | AAStartTime | None |
| Time Range selector | AAStartHour | None |
| Auto Attendant | AA Name | None |
| Incoming Call Source^1^ | Call TypeSum of TotalCallCount (Measure) | External Calls: Call Type is ExternalInternal Calls: Call Type is Internal |
| Directory Search Method | AADirectorySearchMethodTotalCallCount | AADirectorySearchMethod is abs\_search\_dtmf or abs\_search\_name |
| Caller Action Count | AACallerActionCountTotalCallCount | None |
| Average Seconds in AA | AAChainDuration (Measure) | None |
| Average Caller Actions | AACallerActionCount (Measure) | None |
| Call Results | AACallResultAACallResultLegendTotalCallCount | None |
| Lower section of report | AA NameAACallFlowAACallResultAAChainDurationCall TypeMM-DDTotalCallCount | None |

#### fAutoAttendant CQD fields description

| Name | Data Type | Description |
| --- | --- | --- |
| AA Name | Text | Name of resource account attached to Auto AttendantIf the full Resource Account name is **aa\_test@microsoft.com**, then this value is: **aa\_test** |
| AACallerActionCount | Whole number | Summarize: SumCount of actions selected by caller in Auto Attendant during the call |
| AACallerActionCount (Measure) | Whole number | Same as above except this displays as 0 instead of being blank if there are no calls |
| AACallFlow | Text | Encapsulates the different states of Auto Attendant Call--possible values:- abs\_search- announcement- automatic\_menu- call\_termination- call\_transfer- first\_level\_menu- main\_menu- speech\_input\_confirmation- user\_selection |
| AACallResult | Text | Final call result--possible values:- failed\_to\_establish\_media (the media portion of the call couldn't be established)- failover\_to\_operator (call transferred to operator typically due to a system error)- oaa\_chain\_too\_long (too many legs in the AA)- oaa\_session\_too\_long (AA session lasted too long)- service\_declined (AA didn't accept the call)- service\_terminated (AA configuration disconnects the call or call hung up)- terminated\_automatic\_selection (AA configuration disconnects the calls)- terminated\_no\_operator (call terminated due to error no operator defined) - terminated\_transfer\_failed (call terminated as transfer failed - typically to external number)- transfer\_in\_progress (AA-&gt;AA transfer)- transferred\_to\_operator (call was transferred to operator - typically due to user error)- transferred\_to\_receptionist (same as transferred\_to\_operator)- transferred\_to\_self (call was returned to the start of the AA - typically from a menu announcement option)- transferred\_to\_shared\_voicemail (call was transferred to shared voicemail)- transferred\_to\_user (call was transferred to a user - includes call queues)- unknown (an unknown condition occurred)- user\_terminated (caller hung up) |
| AA Call Legend | Text | Sets up legend items based on AACallResult |
| AAChainDuration | Decimal number | Summarize: SumDuration of call in Auto Attendant |
| AAChainDuration (Measure) | Decimal number | Same as above except displays as 0 instead of blank if there are no calls |
| AAChainIndex | Text |  |
| AAConnectivityType | Text | Type of call--possible values:- ExternalCall- InternalCall |
| AACount | Text | Number of Auto Attendants involved in call |
| AADirectorySearchMethod | Text | Last address book search method--possible values:- abs\_search\_dtmf- abs\_search\_extension\_x- abs\_search\_name |
| AAStartHour | Decimal number | Auto Attendant call start hour |
| AAStartTime | Date/time | Auto Attendant call start time |
| AATransferAction | Text | Call transfer target type--possible values:- application - voice application entity- external\_pstn- hunt\_group - Call Queue entity- orgaa - Auto Attendant entity- shared\_voicemail- unknown- user |
| Call Type^1^ | Text | Type of call--possible values:- External- Internal |
| IsAAInvolved | Text | Always 1 |
| MM-DD | Text | Auto Attendant call month-day |
| PSTNMinutes | Whole number | Summarize: SumTotal minute usage |
| TotalCallCount | Whole number | Summarize: SumAlways 1 - used to provide sum of all calls |
| Sum of TotalCallCount (Measure) | Whole number | Same as above except displays as 0 instead of blank if there are no calls |

### Cloud Call Queue Analytics report

#### Report description

| Report Section | Description |
| --- | --- |
| Incoming Call Source^1^ | Distribution of calls by Internal/External call source |
| Average Wait Time (seconds) | Wait time for answered and abandoned calls |
| Call Volume and Agent Opt-in Count | Distribution of calls by call queues / Maximum agent opt-in count |
| Call Results | Distribution of calls by call result |
| Abandoned Calls | Distribution of abandoned calls by call queues |
| Average Session Length (seconds) | Call length in seconds grouped by call result |
| Call Overflow/Timeout Destinations | Distribution of calls that timed out or overflowed |

#### Report to CQD table and field mapping

| Report Tab | Report Table Name | Source Table Name | Global Filter |
| --- | --- | --- | --- |
| Call Queue | fCallQueueAnalyticsfCallQueueFinalStateAction | CallQueueAnalyticsCallQueueFinalStateAction | None |

| Report Section | Table -&gt; Field(s) Used | Filters Applied |
| --- | --- | --- |
| Date selector | fCallQueueAnalytics -&gt; Date | None |
| Time Range selector | fCallQueueAnalytics -&gt; CQHour | None |
| Call Queue Resource Account | fCallQueueAnalytics -&gt; CQ Name | None |
| Incoming call source^1^ | fCallQueueAnalytics -&gt; Sum of Call Count (Measure)fCallQueueAnalytics -&gt; Call Type | External Calls: Call Type is ExternalInternal Calls: Call Type is Internal |
| Avg Wait Time (seconds)-Before Answered | fCallQueueFinalStateAction -&gt; Avg of Average CQ Duration (Measure) | Call Queue Call Result is agent\_joined\_conference or transferred\_to\_agent |
| Avg Wait Time (seconds)-Before Abandoned | fCallQueueFinalStateAction -&gt; Avg of Average Call Duration (Measure) | Call Queue Call Result isn't agent\_joined\_conference, transferred\_to\_agent, overflown, timed\_out |
| Call Volume and Agent Opt-In Count | fCallQueueAnalytics -&gt; Call CountfCallQueueAnalytics -&gt; Call Queue Agent Opt In CountfCallQueueAnalytics -&gt; CQ NamefCallQueueAnalytics -&gt; Date | None |
| Abandoned Calls | fCallQueueAnalytics -&gt; DatefCallQueueAnalytics -&gt; TotalCallCount | Call Queue Call Result Legend is Abandoned |
| Average Session Length (seconds) | fCallQueueFinalStateAction -&gt; Average Call Queue Duration (Sec)Call Queue Call Result Legend | Average Call Queue Duration (Sec) &gt; 0 |
| Call Overflow/Timeout Destinations | fCallQueueAnalytics -&gt; Call CountfCallQueueAnalytics -&gt; Call Queue Target TypefCallQueue Target Type Legend | Call Queue Target Type Legend doesn't contain Abandoned and Agent Answered |

#### fCallQueueAnalytics CQD fields description

| Name | Data Type | Description |
| --- | --- | --- |
| Call Count | Whole number | Summarize: SumNumber of calls |
| Call Queue Agent Count | Whole number | Summarize: SumNumber of agents configured in the call queue |
| Call Queue Agent Opt In Count | Whole number | Summarize: SumNumber of agents opted-in to the call queue |
| Call Queue Call Result | Text | Call queue call final state--possible values:- agent\_joined\_conference (answered conference mode calls)- declined- disconnected- error- failed- invalid- overflown (overflow condition met)- timed\_out (timeout condition met)- transferred\_to\_agent (answered transfer mode calls {default}) |
| Call Queue Call Result Legend | Text | Sets up legend items based on Call Queue Result |
| Call Queue Target Type | Text | ***Call redirection target type--possible values:***- ApplicationEndpoint- Mailbox- Other- User |
| Call Queue Target Type Legend | Text | Sets up legend items based on Call Queue Target Type |
| Call Type^1^ | Text | Type of call--possible values:- External- Internal |
| CQ Name | Text | Name of resource account attached to Call QueueIf the full Resource Account name is **cq\_test@microsoft.com**, then this value is: **cq\_test** |
| CQ Hour | Whole Number | Call queue call start hour |
| Date | Date/time | Call queue call start date and time (hour) |
| DateTimeCQName | Text | Unique key for filtering on fCallQueueFinalStateAction |
| PSTN Connectivity Type | Text | Type of call--possible values:- ExternalCall- InternalCall |
| PSTN Total Minutes | Whole number | Summarize: SumTotal minutes usage for PSTN calls |
| Sum of Call Count (Measure) | Whole number | Same as Call Count except displays as 0 if there are no calls |
| TotalCallCount (Measure) | Whole Number | Summarize: SumCall Count |

#### fCallQueueFinalStateAction CQD fields description

| Name | Data Type | Description |
| --- | --- | --- |
| Average Call Duration (Seconds) | Decimal number | Summarize: SumAverage call duration in seconds for abandoned calls |
| Average Call Queue Duration (Sec) | Decimal number | Summarize: SumAverage waiting in seconds for answered calls |
| Avg of Average Call Duration (Measure) | Whole number | Same as Average Call Duration (Seconds) however displays as 0 if there are no calls |
| Avg of Average CQ Duration (Measure) | Whole number | Same as Average Call Queue Duration (Sec) however displays as 0 if there are no calls |
| Call Count | Whole number | Summarize: SumNumber of calls |
| Call Queue Call Result | Text | Call queue call final state--possible values:- agent\_joined\_conference (answered conference mode calls)- declined- disconnected- error- failed- invalid- overflown (overflow condition met)- timed\_out (timeout condition met)- transferred\_to\_agent (answered transfer mode calls {default}) |
| Call Queue Call Result Legend | Text | Sets up legend items based on Call Queue Call Result |
| Call Queue Final State Action | Text | Call queue final action--possible values:- disconnect (timed\_out calls)- disconnect\_with\_busy (overflown calls)- failed\_to\_accept\_call- forward- shared\_voicemail- other- voicemail |
| CQ Name | Text | Name of resource account attached to Call QueueIf the full Resource Account name is **cq\_test@microsoft.com**, then this value is **cq\_test** |
| Date | Date/time | Call Queue call start date and time (hour) |
| DateTimeCQName | Text | Unique key for filtering on fCallQueueFinalStateAction |
| IsAbandoned | True/false | True if agent doesn't answer a call |

### Cloud Call Queue Agent Timeline report

#### Report description

| Report Section | Description |
| --- | --- |
| Number of Calls by Agent | Distribution of calls by call queue and agent |
| Distribution by Agent and all Queue | Distribution of calls by agent and call queue |
| Table (bottom right) | Distribution of calls by agent with average and total call duration |
| Average Call Duration (seconds) by Agent | Average duration (seconds) of call by agent |

#### Report to CQD table and field mapping

| Report Tab | Report Table Name | Source Table Name | Global Filter |
| --- | --- | --- | --- |
| Agent Timeline | fAgentTimelineAnalytics | fAgentTimelineAnalytics | None |

| Report Section | Field(s) Used | Filters Applied |
| --- | --- | --- |
| Date selector | DateTime | None |
| Agent Username selector | Agent Name | None |
| Call Queue Resource Accounts selector | CQ Name | None |
| Number of Calls by Agent | Agent NameCall CountHour | None |
| Distribution by Agent and Call Queue | Agent NameAverage Calls Duration (Seconds)Call CountCQ Name | None |
| Bottom Left | Agent NameAverage Call Duration (Seconds)Call CountCall Duration (Minute)CQ NameHourMM-DD | None |
| Average Call Duration (Seconds) by Agent | Agent NameAverage Call Duration (Seconds) | None |

#### fAgentTimelineAnalytics CQD fields description

| Name | Data Type | Description |
| --- | --- | --- |
| Agent Name | Text | User UPNIf the full username is **user@microsoft.com**, then this value is **user** |
| Average Call Duration (Seconds) | Decimal number | Summarize: SumThe average duration of answered call queue calls in seconds |
| Call Count | Whole number | Summarize: SumNumber of calls answered by the agent |
| Call Duration (Minutes) | Whole number | Summarize: SumTotal call duration of answered call queue calls in minutes (rounded down to nearest minute) |
| CQ Name | Text | Name of resource account attached to Call QueueIf the full Resource Account name is **cq\_test@microsoft.com**, then this value is **cq\_test** |
| Date | Date | Date of call |
| DateTime | DateTime | Date of call |
| Hour | Whole number | Hour of call |
| MM-DD | Text | Month and day of call |

Note

When a call arrives at the first call queue, if the number of calls already waiting in that queue has reached the **Call overflow handling** limit and if the redirect option sends new calls to a second call queue, then the agents in the second call queue show as being in the first call queue on this report.

## Known issues

- Auto attendant resource account IDs are being masked which prevents reporting by individual auto attendants. Support is investigating.
- Call queue and auto attendants are shown by the resource account's ID instead of call queue/auto attendant names. To show all the traffic for an auto attendant or call queue, you must select all the resource accounts assigned to the auto attendant or call queue.
- Only 28 days of history are available in the dashboard as call queue/auto attendant data is considered personal data and is subject to data privacy retention policies.
- In some scenarios, the agent answered call count on the **Cloud Call Queue Agent Timeline** report might be different than the number of calls shown in the Teams client call history. The Teams client call history is correct. Support is investigating, but there's no estimated time to repair available at this time.
- ^1^**Incoming call source** in the auto attendant and call queue graphs show the final call leg source rather than the initial call leg source. For example, if an auto attendant receives an external call and transfers the call to another auto attendant or call queue, the **Incoming call source** is reported as Internal.

## Version 1.xx history

Refer to **CQD Teams Auto Attendant & Call Queue Historical Reports - Change Log.docx** in the downloaded zip file for a detailed list of changes

| Version | Date Published | Filename | Description |
| --- | --- | --- | --- |
| 1.64 | July 14, 2023 | CQD Teams Auto Attendant & Call Queue Historical Report V1.64.pbit | Support for GCCH and DoD clouds |
| 1.63 | August 24, 2022 | CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit |  |
| 1.60 | July 22, 2022 | CQD Teams Auto Attendant & Call Queue Historical Report V1.60.pbit |  |
| 1.00 | November 5, 2020 | CQ and AA combined Analytics 20201105.pbit | Initial release |