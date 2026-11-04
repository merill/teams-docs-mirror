---
layout: Conceptual
title: Reporting - Historical Table Field Definitions - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-report-historical-table-field-definitions
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
ms.topic: reference
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
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to understand the table field definitions in the Teams historical reporting.
description: Reference for the table and field definitions used in the Teams Phone Agent, Auto Attendant, and Call Queue historical Power BI reports.
locale: en-us
document_id: 66b8d3d7-92d6-b3fa-503f-ab87526fc6e8
document_version_independent_id: 66b8d3d7-92d6-b3fa-503f-ab87526fc6e8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-report-historical-table-field-definitions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-report-historical-table-field-definitions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-report-historical-table-field-definitions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c4797f74-4179-47d4-8dca-c1b537088d5a
---

# Reporting - Historical Table Field Definitions - Microsoft Teams | Microsoft Learn

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

## Historical reports field definitions

### Cloud Teams Phone Agent Analytics report

Expand to see the TeamsPhoneAgent table field descriptions

| Name | Data Type | Description |
| --- | --- | --- |
| AACallerActionCounts | Whole number | Summarized: SumCount of actions selected by caller in Auto Attendant during the call |
| AACallDurationSeconds |  |  |
| AACallResultLegendCode | Whole number | See `AutoAttendantCallResult` in [Auto Attendant dimensions -&gt; AutoAttendantCallResult](aa-cq-report-historical-custom#auto-attendant-dimensions) - converted to numeric codes |
| AACallResultLegendString | Text | Localized string for AACallResultLegendCodeEnglish values are:<br>- **Terminated (No Caller Action)** - Call was disconnected - the caller didn't make any selections<br>- **Terminated (With Caller Action)** - Call was disconnected - the caller made selections<br>- **Terminated (Disconnected)** - Call was disconnected per the auto attendant configuration<br>- **Terminated (No Operator)** - Call was disconnected as there was no operator to transfer the call to<br>- **Terminated (Transfer Failed)** - Call was disconnected as the configured transfer failed<br>- **Transferred (AA)** - Call was transferred to another Auto Attendant<br>- **Transferred (CQ)** - Call was transferred to a Call Queue<br>- **Transferred (Operator)** - Call was transferred to the Operator<br>- **Transferred (Voicemail)** - Call was transferred to Shared Voicemail<br>- **Transferred (External)** - Call was transferred to an External Number<br>- **Transferred (User)** - Call was transferred to a Person in the organization<br>- **Other** - Some other condition occurred |
| AAChainDurationSeconds | Decimal number | Teams Phone Agent + Microsoft Copilot Studio total call duraiton |
| AAConnectivityTypeCode | Whole number | See `PSTNConnectivityType` in [Common dimensions -&gt; PSTNConnectivityType](aa-cq-report-historical-custom#common-dimensions) - converted to numeric codes |
| AAConnectivityTypeString | Text | Localized string for AAConnectivityTypeCodeEnglish values are: <br>- **Calling Plan** - Calling Plan<br>- **Direct Routing** - Direct Routing<br>- **Teams Phone Mobile** - Teams Phone Mobile<br>- **ACS Call** - ACS |
| AADirectorySearchMethodLegendCode | Whole number | See `AutoAttendantDirectorySearchMethod` in [Auto Attendant dimensions -&gt; AutoAttendantDirectorySearchMethod](aa-cq-report-historical-custom#auto-attendant-dimensions) - converted to numeric codes |
| AADirectorySearchMethodLegendString | Text | Localized string for AADirectorySearchMethodLegendCodeEnglish values are: <br>- **DTMF** - Caller used the telephone dial pad to search for the user's name<br>- **Voice** - Caller used voice input to search for the user's name |
| AAGUID | Text | Teams Phone Agent or Auto Attendant unique identifier |
| AAPSTNMinutes | Whole number | Summarized: SumTotal minute usage |
| AASlicerDate | Date | Teams Phone Agent or Auto Attendant call start date - used for the date slicer |
| AASlicerName | Text | Admins: AAGUID or Resource account usernameAdmins or Auth Users: Auto attendant name |
| AAStartHourLocal | Whole number | Teams Phone Agent or Auto Attendant call start hour - Local (based on selected UTC Offset) |
| AAStartTimeLocal | Date/time | Teams Phone Agent or Auto Attendant call start time - Local (based on selected UTC Offset) |
| AAStartTimeUTC | DateTimeZone | Teams Phone Agent or Auto Attendant call start time - UTC |
| AATotalCallCount | Whole number | Summarized: SumAlways 1 - used to provide sum of all calls |
| AIAgentId | Text | Microsoft Copilot Studio Agent unique identifier |
| AIAgentName | Text | Microsoft Copilot Studio Agent name (not currently populated) |
| AppointmentCancelled | Whole number | 0: Appointment was not cancelled1: Appointment was cancelled |
| AppointmentModified | Whole number | 0: Appointment was not modified1: Appointment was modified |
| AppointmentRequestStarted | Whole number | 0: Appointment process was not started1: Appointment process was started |
| AppointmentReviewed | Whole number | 0: Appointment was not reviewed1: Appointment was reviewed |
| AppointmentScheduled | Whole number | 0: Appointment was not scheduled1: Appointment was scheduled |
| CallAuthenticated | Whole number | 0: Caller was not authenticated1: Caller was authenticated |
| Category | Text | The Teams Phone Agent category for the call. This is the configured Voice Command |
| ConferenceID (Per Call only) | Text | Call IDUsed for troubleshooting purposes - provide this information when opening a ticket |
| Contained | Whole number | 0: Call was not contained1: Call was contained |
| MADurationInSeconds | Whole number | Teams Phone Agent total call duration (does not include Microsoft Copilot Studio Agent time) |
| MaToolUsageDetails | Text | JSON blob of the actions and tools used |
| MCSUsed | Whole number | 0: Microsoft Copilot Studio was not used1: Microsoft Copilot Studio was used |
| QandAToolUtilized | Whole number | 0: Questions and Answers was not used1: Questions and Answers was used |

### Cloud Auto Attendant Analytics report

Expand to see the AutoAttendant table field descriptions

| Name | Data Type | Description |
| --- | --- | --- |
| AACallDurationSeconds | Whole number | Summarized: SumCall duration in seconds |
| AACallDurationSecondsAVG (Measure) | Whole number | Average call duration in seconds |
| AACallerActionCounts | Whole number | Summarized: SumCount of actions selected by caller in Auto Attendant during the call |
| AACallerActionCountsAVG (Measure) | Whole number | Average of AACallerActionCounts - zero instead of blank |
| AACallFlowString | Text | Localized - see `AutoAttendantCallFlow` in [Auto Attendant dimensions -&gt; AutoAttendantCallFlow](aa-cq-report-historical-custom#auto-attendant-dimensions) |
| AACallResultLegendCode | Whole number | See `AutoAttendantCallResult` in [Auto Attendant dimensions -&gt; AutoAttendantCallResult](aa-cq-report-historical-custom#auto-attendant-dimensions) - converted to numeric codes |
| AACallResultLegendString | Text | Localized string for AACallResultLegendCodeEnglish values are:<br>- **Terminated (No Caller Action)** - Call was disconnected - the caller didn't make any selections<br>- **Terminated (With Caller Action)** - Call was disconnected - the caller made selections<br>- **Terminated (Disconnected)** - Call was disconnected per the auto attendant configuration<br>- **Terminated (No Operator)** - Call was disconnected as there was no operator to transfer the call to<br>- **Terminated (Transfer Failed)** - Call was disconnected as the configured transfer failed<br>- **Transferred (AA)** - Call was transferred to another Auto Attendant<br>- **Transferred (CQ)** - Call was transferred to a Call Queue<br>- **Transferred (Operator)** - Call was transferred to the Operator<br>- **Transferred (Voicemail)** - Call was transferred to Shared Voicemail<br>- **Transferred (External)** - Call was transferred to an External Number<br>- **Transferred (User)** - Call was transferred to a Person in the organization<br>- **Other** - Some other condition occurred |
| AAChainDuration | Decimal number | Summarized: SumDuration of call in Auto Attendant |
| AAChainDurationAVG (Measure) | Decimal number | Average of AAChainDuration - zero instead of blank |
| AAConnectivityTypeCode | Whole number | See `PSTNConnectivityType` in [Common dimensions -&gt; PSTNConnectivityType](aa-cq-report-historical-custom#common-dimensions) - converted to numeric codes |
| AAConnectivityTypeString | Text | Localized string for AAConnectivityTypeCodeEnglish values are: <br>- **CallingPlan** - Calling Plan<br>- **DirectRouting** - Direct Routing<br>- **TeamsPhoneMobile** - Teams Phone Mobile<br>- **ACS Call** - ACS |
| AADirectorySearchMethodDTMFCOUNT (Measure) | Whole number | Count of calls that used DTMF to search the directory - zero instead of blank |
| AADirectorySearchMethodLegendCode | Whole number | See `AutoAttendantDirectorySearchMethod` in [Auto Attendant dimensions -&gt; AutoAttendantDirectorySearchMethod](aa-cq-report-historical-custom#auto-attendant-dimensions) - converted to numeric codes |
| AADirectorySearchMethodLegendString | Text | Localized string for AADirectorySearchMethodLegendCodeEnglish values are: <br>- **DTMF** - Caller used the telephone dial pad to search for the user's name<br>- **Voice** - Caller used voice input to search for the user's name |
| AADirectorySearchMethodVoiceCOUNT (Measure) | Whole number | Count of calls that used Voice to search the directory - zero instead of blank |
| AAGUID | Text | Auto Attendant unique identifier |
| AAPSTNMinutes | Whole number | Summarized: SumTotal minute usage |
| AASlicerDate | Date | Teams Phone Agent or Auto Attendant call start date - used for the date slicer |
| AASlicerName | Text | Admins: AAGUID or Resource account usernameAdmins or Auth Users: Auto attendant name |
| AAStartHourLocal | Whole number | Auto Attendant call start hour - Local (based on selected UTC Offset) |
| AAStartTimeLocal | Date/time | Auto Attendant call start time - Local (based on selected UTC Offset) |
| AAStartTimeUTC | Date/time | Auto Attendant call start time - UTC |
| AATotalCallCount | Whole number | Summarized: SumAlways 1 - used to provide sum of all calls |
| AATotalCallCountSUM (Measure) | Whole number | Sum of TotalCallCount |
| ConferenceID (Per Day only) | Text | Used for troubleshooting purposes - provide this information when opening a ticket |
| MM-DD | Text | Auto Attendant call month-day |

### Cloud Call Queue Analytics report

Expand to see the CallQueue table field descriptions

| Name | Data Type | Description |
| --- | --- | --- |
| ConferenceID (Per Call only) | Text | Used for troubleshooting purposes - provide this information when opening a ticket |
| CQAgentCount | Whole number | Summarized: SumNumber of agents configured in the Call queue |
| CQAgentOptInCount | Whole number | Summarized: SumNumber of agents opted-in to the Call queue |
| CQCountAbandoned | Whole number | Summarized: SumNumber of abandoned calls |
| CQCallCountAbandonedSUM (Measure) | Whole number | Call Count Abandoned - zero instead of blank |
| CQCallDurationSeconds | Decimal number | Summarized: SumCall duration |
| CQCallDurationSecondsAVG (Measure) | Whole number | Average Call Duration Seconds |
| CQCallResultLegendCode | Whole number | See `CallQueueCallResult` in [Call Queue dimensions -&gt; CallQueueCallResult](aa-cq-report-historical-custom#call-queue-dimensions) - converted to numeric codes |
| CQCallResultLegendString | Text | Localized string for CQCallResultLegendCodeEnglish values are:<br>- **Abandoned** - the caller hung up before an agent could answer or before timeout occurred<br>- **Agent Answered** - the caller was answered by an agent<br>- **Overflowed** - the call overflow exception occurred<br>- **Timed Out** - the call timeout exception occurred<br>- **No Agents** - the no agents exception occurred<br>- **Other** - some other condition occurred |
| CQCallStartDateLocal | Date | Call start date - Local (based on selected UTC Offset) |
| CQCallStartTimeLocal | Date/time | Call start time - Local (based on selected UTC Offset) |
| CQCallStartTimeUTC | Date/time | Call start time - UTC |
| CQConnectivityTypeCode | Whole number | See `PSTNConnectivityType` in [Common dimensions -&gt; PSTNConnectivityType](aa-cq-report-historical-custom#common-dimensions) - converted to numeric codes |
| CQConnectivityTypeString | Text | Localized string for CQConnectivityTypeCodeEnglish values are: <br>- **CallingPlan** - Calling Plan<br>- **DirectRouting** - Direct Routing<br>- **TeamsPhoneMobile** - Teams Phone Mobile<br>- **ACS Call** - ACS |
| CQGUID | Text | Call Queue unique identifier |
| CQHour | Whole number | Summarized: SumCall queue call start hour |
| CQPSTNTotalMinutes | Decimal number | Summarized: SumTotal minutes usage for PSTN calls |
| CQRAIdentity | Text | Name of resource account attached to Call QueueIf the full Resource Account name is **cq\_test@microsoft.com**, then this value is: **cq\_test** |
| CQSlicer | Text | Admins: CQGUID or Resource account usernameAuth Users: Call queue name |
| CQTargetTypeLegendCode | Whole number | See `CallQueueTargetType` in [Call Queue dimensions -&gt; CallQueueTargetType](aa-cq-report-historical-custom#call-queue-dimensions) - converted to numeric codes |
| CQTargetTypeLegendString | Text | Localized string for CQTargetTypeLegendCodeEnglish values are: <br>- **Abandoned** - the caller hung up before an agent could answer or before timeout occurred<br>- **Agent Answered (Call)** - the caller was answered by an agent<br>- **Agent Answered (Callback)** - the callback was answered by an agent<br>- **Overflowed (Application)** - the call overflow exception occurred - call routed to another application<br>- **Overflowed (Disconnect)** - the call overflow exception occurred - call disconnected<br>- **Overflowed (External)** - the call overflow exception occurred - call was transferred externally<br>- **Overflowed (User)** - the call overflow exception occurred - call was transferred to a Person in the organization<br>- **Overflowed (Voicemail)** - the call overflow exception occurred - call was transferred to shared voicemail<br>- **Timed Out (Application)** - the call timeout exception occurred - call routed to another application<br>- **Timed Out (Disconnect)** - the call timeout exception occurred - call was disconnected<br>- **Timed Out (External)** - the call timeout exception occurred - call was transferred externally<br>- **Timed Out (User)** - the call timeout exception occurred - call was transferred to a Person in the organization<br>- **Timed Out (Voicemail)** - the call timeout exception occurred - call was transferred to shared voicemail<br>- **No Agents (Application)** - the no agents exception occurred - call was routed to another application<br>- **No Agents (Disconnect)** - the no agents exception occurred - call was disconnected<br>- **No Agents (External)** - the no agents exception occurred - call was transferred externally<br>- **No Agents (User)** - the no agents exception occurred - call was transferred to a Person in the organization<br>- **No Agents (Voicemail)** - the no agents exception occurred - call was transferred to shared voicemail |
| CQTotalCallCount | Whole number | Summarized: SumNumber of calls |
| CQTotalCallCountSUM (Measure) | Whole number | Call Count Sum - zero instead of blank |
| DateTimeCQName | Text | Unique key for filtering on fCallQueueFinalStateAction |
| DialogID (Per Call only) | Text | Used for troubleshooting purposes - provide this information when opening a ticket |

Expand to see the CallQueueFinalStateAction table field descriptions

| Name | Data Type | Description |
| --- | --- | --- |
| CQAvgCallDuration | Decimal number | Summarized: SumAverage waiting time in seconds |
| CQAvgCallDurationSeconds | Whole number | Summarized: SumAverage waiting time in seconds |
| CQCallResultLegendCode | Whole number | See `CallQueueCallResult` in [Call Queue dimensions -&gt; CallQueueCallResult](aa-cq-report-historical-custom#call-queue-dimensions) - converted to numeric codes |
| CQCallResultLegendString | Text | Localized string for CQCallResultLegendCodeEnglish values are: <br>- **Abandoned** - the caller hung up before an agent could answer or before timeout occurred<br>- **Agent Answered (Call)** - the caller was answered by an agent<br>- **Agent Answered (Callback)** - the callback was answered by an agent<br>- **Overflowed (Disconnect)** - the call overflow exception occurred - call disconnected<br>- **Overflowed (Xferred)** - the call overflow exception occurred - call was transferred externally<br>- **Overflowed (Voicemail)** - the call overflow exception occurred - call was transferred to shared voicemail<br>- **Timed Out (Callback)** - the callback timed out - callback didn't occur<br>- **Timed Out (Disconnect)** - the call timeout exception occurred - call was disconnected<br>- **Timed Out (Xferred)** - the call timeout exception occurred - call was transferred externally<br>- **Timed Out (Voicemail)** - the call timeout exception occurred - call was transferred to shared voicemail<br>- **No Agents (Disconnect)** - the no agents exception occurred - call was disconnected<br>- **No Agents (Xferred)** - the no agents exception occurred - call was transferred externally<br>- **No Agents (Voicemail)** - the no agents exception occurred - call was transferred to shared voicemail |
| CQCallStartTimeLocal | Date/time | Call start time - Local (based on selected UTC Offset) |
| CQCallStartTimeUTC | Date/time | Call start time - UTC |
| CQSlicer | Text | Admins: CQGUID or Resource account usernameAuth Users: Call queue name |
| CQTotalCallCount | Whole number | Summarized: SumNumber of calls |
| DateTimeCQName | Text | Unique key for filtering on fCallQueueFinalStateAction |

### Cloud Call Queue Agent Timeline report

Expand to see the AgentTimeline table field descriptions

| Name | Data Type | Description |
| --- | --- | --- |
| AgentCallDurationMinutes | Decimal number | Summarized: SumTotal call duration of answered Call queue calls in minutes |
| AgentCallDurationSeconds | Decimal number | Summarized: SumTotal call duration of answered Call queue calls in seconds |
| AgentCallDurationSecondsAVG (Measure) | Decimal number | Average of AgentCallDurationSeconds |
| AgentTimelineAnalyticsSummaryLink | Text | Used to link with fAgentTimelineAnalyticsSummary for the pop-up tooltip |
| AgentTotalCallCountSUM (Measure) | Whole number | Total number of calls answered by agent |
| Call Duration (HH:MM:SS) | Text | Call Duration (Minutes) converted to HH:MM:SS |
| ConferenceID | Text | Used for troubleshooting purposes - provide this information when opening a ticket |
| CQAgentName | Text | User UPNIf the full username is **user@microsoft.com**, then this value is: **user** |
| CQCallStartHour | Whole number | Call start hour |
| CQCallStartTimeLocal | Date/time | Call start time - Local (based on selected UTC Offset) |
| CQCallStartTimeUTC | Date/time | Call start time - UTC |
| CQGUID | Text | Call Queue unique identifier |
| CQSlicer | Text | Admins: CQGUID or Resource account usernameAuth Users: Call queue name |
| CQTotalCallCount | Whole number | Summarized: SumNumber of calls presented to agent |
| Date | Date | Date of call |
| DateTime | Date/time | Date of call |
| DialogID | Text | Used for troubleshooting purposes - provide this information when opening a ticket |
| MM-DD | Text | Call queue call month-day |

Expand to see the AgentTimelineSummary table field descriptions

| Name | Data Type | Description |
| --- | --- | --- |
| AgentAverageCallDurationSeconds | Decimal number | Summarized: SumThe average duration of answered Call queue calls in seconds |
| AgentAverageCallDurationSeconds\_Formatted (Measure) | Decimal number | The average duration of answered Call queue calls in seconds - zero instead of blank |
| AgentAverageCalls (Measure) | Decimal number | The average number of calls answered by the agent |
| AgentTimelineAnalyticsLink | Text | Used to link with fAgentTimelineAnalytics for the pop-up tooltip |
| CQAgentName | Text | User UPNIf the full username is **user@microsoft.com**, then this value is: **user** |
| CQSlicer | Text | Admins: CQRANameAuth Users: CQName |
| Date | Date/time | Date of call |
| Hour | Whole number | Hour of call |
| MM-DD | Text | Month and day of call |
| Total Call Duration (HH:MM:SS) | Text | Call Duration (Minutes) converted to HH:MM:SS |
| TotalCallCountSUM (Measure) | Whole number | Total number of calls answered by the agent |