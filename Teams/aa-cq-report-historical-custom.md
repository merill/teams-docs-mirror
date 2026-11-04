---
layout: Conceptual
title: Reporting - Historical Reporting - Custom - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-report-historical-custom
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
customer-intent: As a Teams Administrator, I want to learn how to build custom historical reports outside of Power BI for Teams Phone Agent, Auto Attendant, and Call Queue.
description: Learn how to use the Voice Applications Analytics Collector (VAAC) API to build custom historical reports outside of Power BI.
locale: en-us
document_id: d0fcf1c5-076a-c963-a480-860da3b842a6
document_version_independent_id: d0fcf1c5-076a-c963-a480-860da3b842a6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-report-historical-custom.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-report-historical-custom
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-report-historical-custom.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 659128eb-9fda-5da0-1c96-6b770ea817d0
---

# Reporting - Historical Reporting - Custom - Microsoft Teams | Microsoft Learn

Note

Help shape the future of **Teams Voice Applications Historical Reporting**. [Share quick feedback](https://go.microsoft.com/fwlink/?LinkId=2375135) on the reports, setup documentation, translations, or languages you’d like supported. Your input will be reviewed by Microsoft and used to improve the product, documentation, and localization experience for everyone.

This article is for IT pros and Teams administrators who want to build custom historical reports outside of Power BI for Teams Phone Agents, Auto Attendants, and Call Queues.

## Planning and licensing review

### Planning

- [Overview of Teams Phone Agent, Auto Attendant, and Call Queue](aa-cq-plan-overview)
- [Authorized users](aa-cq-plan-authorized-users)
- [Nesting call flows](aa-cq-plan-nesting)
- [Reporting considerations](aa-cq-plan-reporting)

### Licensing

- [Auto Attendant and Call Queue](aa-cq-reference-prerequisites-licensing#base-licensing)

## Overview

The Voice Applications Analytics Collector (VAAC) service enables accessing all the Teams Phone Agent, Auto Attendant, and Call Queue historical data with any tool that supports connecting to HTTP endpoints.

There are three steps:

1. Authentication
2. Constructing a valid query
3. Reading the result

### Step 1 - Authentication

An access token must be retrieved and then submitted with all subsequent requests.

Authentication URL:

```https
https://login.microsoftonline.com/{{tenantID}}/oauth2/token
```

Replace {{tenantID}} with your tenant ID.

The body of the request must contain the following:

| Field name | Value |
| --- | --- |
| client\_id |  |
| scope | user\_impersonation |
| userName | The Teams username |
| password | The Teams password for the username |
| grant\_type | password |
| resource | `https://api.interfaces.records.teams.microsoft.com` |

### Step 2 - Constructing a valid query

A valid query consists of several attributes in a JSON object:

```json
{
   "Filters":[
      {
         "DataModelName":"Date",
         "Value":"2022-04-01",
         "Operand":4
      },
      {
         "DataModelName":"Date",
         "Value":"2022-04-30",
         "Operand":6
      }
   ],
   "Dimensions":[
      {
         "DataModelName":"AutoAttendantIdentity"
      },
      {
         "DataModelName":"AutoAttendantDirectorySearchMethod"
      }
   ],
   "Measurements":[
      {
         "DataModelName":"PSTNTotalMinutes"
      },
      {
         "DataModelName":"TotalCallCount"
      }
   ],
   "Parameters":{
      "UserAgent":"VAAC Custom Query"
   },
   "LimitResultRowsCount":100000
}
```

#### Required fields

- **Filters**: used to filter data returned by VAAC - any dimension where `Filters Support` is `Y`can be filtered on
    - DataModelName should be one of the supported dimensions
    - Value should be in the correct format (datetime, string, number, etc.)
    - *Operands*:
        - 0 - Equals
        - 1 - Not Equals
        - 2 - Contains
        - 3 - Begins With
        - 4 - Greater Than
        - 5 - Greater Than or Equal To
        - 6 - Less Than
        - 7 - Less Than or Equal To
        - 8 - Does Not Contain
        - 9 - Does Not Begin With
- **Dimensions**:
    - DataModelName should be one of the supported Common, Auto Attendant, or Call Queue dimensions.
- **Measurements**:
    - DataModelName should be one of the supported measurements.
- **Parameters**: Currently only UserAgent is supported.
- **LimitResultRowsCount**: the max count of rows returned by VAAC

Note

When you submit a query that searches by `Date`, and the search criteria include both date and time (ISO 8601 format), the time portion is ignored.

Important

Requests into the system are throttled based on the IP address making the call, the recognized tenant identity in the auth header, and the calling service, to prevent a single client, tenant, or service from monopolizing the resources.

#### Compress the JSON query

The VAAC API only accepts GZIP-compressed or Base64-encoded strings as input.

Use any website that can compress the JSON blob using GZIP or Base64. For example:

- [GZIP](https://www.multiutil.com/text-to-gzip-compress/)
- [Base64](https://www.multiutil.com/text-to-base64-converter/)

GZIP output should look like this:

```console
H4sIAAAAAAAACq2SQWsCMRCF7/6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif+9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf+xJLIGhIo12CjXKPM0o+2cLn2BjEjKVZQM1Gqjhhfy+QQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3/hUBqPKya/WyD41bpCXpP+tzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa/Y2Tk/wI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA=
```

Base64 output should look like this:

```console
ew==
IkZpbHRlcnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0wMSIs
Ik9wZXJhbmQiOjQ=
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0zMCIs
Ik9wZXJhbmQiOjY=
fQ==
XSw=
IkRpbWVuc2lvbnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg==
fQ==
XSw=
Ik1lYXN1cmVtZW50cyI6Ww==
ew==
IkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg==
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI=
fQ==
XSw=
IlBhcmFtZXRlcnMiOns=
IlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai
fSw=
IkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA=
fQ==
```

#### URL-Encode the compressed JSON query

The GZIP or Base64 compressed JSON query must be [URL encoded](https://meyerweb.com/eric/tools/dencoder/).

GZIP URL encoded output looks like this:

```console
H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
```

Base64 URL encoded output looks like this:

```console
%0Aew%3D%3D%0AIkZpbHRlcnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0wMSIs%0AIk9wZXJhbmQiOjQ%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0zMCIs%0AIk9wZXJhbmQiOjY%3D%0AfQ%3D%3D%0AXSw%3D%0AIkRpbWVuc2lvbnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg%3D%3D%0AfQ%3D%3D%0AXSw%3D%0AIk1lYXN1cmVtZW50cyI6Ww%3D%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg%3D%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI%3D%0AfQ%3D%3D%0AXSw%3D%0AIlBhcmFtZXRlcnMiOns%3D%0AIlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai%0AfSw%3D%0AIkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA%3D%0AfQ%3D%3D
```

The final request URL will look similar to the following:

```https
https://api.interfaces.records.teams.microsoft.com/Teams.VoiceAnalytics/getanalytics?query=H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
```

### Step 3 - Reading the result

After you submit your input, there are a couple of possible results:

- If the input is invalid, an error message with the actual reason is returned
- If the input is valid, the result looks like this:

    [![Screenshot showing query result with the dataResult field.](media/aa-cq/historical-report-postman-04.png)](media/aa-cq/historical-report-postman-04.png#lightbox)

    In this case, the data is in the "dataResult" field in the same order requested in the query dimension and measurements attributes.

## Available dimensions and measurements

The following dimensions and measurements are available to be used.

### Common dimensions

These dimensions are common to both Auto attendants and Call queues:

| Name (Type) | Possible Values | Filters Support | Description |
| --- | --- | --- | --- |
| ConferenceId(Text) | GUID | Y | Call identifier |
| Date(DateTime) |  | Y | Date of call (UTC) |
| DialogId(Text) | GUID | Y | Call identifier |
| DocumentId(Text) | GUID | Y | Call identifier |
| Duration(Whole Number) |  | Y | Duration of call, in seconds |
| EndTime(DateTime) |  | Y | Time call ended (UTC) |
| FirstIsCaller(Boolean) |  | Y | [First and Second endpoint classification](dimensions-and-measures-available-in-call-quality-dashboard) |
| FirstUPN(Text) |  | N | The user principal name (UPN) of the first endpoint's user |
| FirstUserObjectId(Text) | GUID | Y | Object Id of the FirstUPN |
| Hour(Text) |  | Y | Hour call started (UTC) |
| Minute(Text) |  | Y | Minute call started (UTC) |
| PSTNCallDuration(Whole Number) |  | Y | Duration of the call |
| PSTNCallType(Text) |  | Y |  |
|  | External |  | Call is coming from outside the tenant |
|  | Internal |  | Call is coming from within the tenant |
| PSTNConnectivityType(Text) |  | Y |  |
|  | CallingPlan |  | The call arrived on a Calling Plan number |
|  | DirectRouting |  | The call arrived on a Direct Routing number |
|  | TeamsPhoneMobile |  | The call arrived on a Teams Phone Mobile number |
|  | ACS Call |  | The call arrived from the web (Click2Call on report) |
| Second(Text) |  | Y | Second call started (UTC) |
| SecondUPN(Text) |  | N | The user principal name (UPN) of the second endpoint's user |
| SecondUserObjectId(Text) | GUID | Y | Object Id of the SecondUPN |
| Timestamp(DateTime) |  | Y | Time record was written (UTC) |
| UserStartTimeUTC(DateTime) |  | Y | Time call started (UTC) |

### Teams Phone Agent dimensions

| Name (Type) | Possible Values | Filters Support | Description |
| --- | --- | --- | --- |
| AIAgentId(Text) | GUID | Y | The GUID of the Microsoft Copilot Studio agent |
| AIAgentName(Text) |  | N | The name of the Microsoft Copilot Studio agent*Not currently populated* |
| AppointmentCancelled(Boolean) |  | Y | Was an appointment cancelled |
| AppointmentModified(Boolean) |  | Y | Was an appointment modified |
| AppointmentRequestStarted(Boolean) |  | Y | Was the Appointments tool started |
| AppointmentReviewed(Boolean) |  | Y | Was an appointment reviewed |
| AppointmentScheduled(Boolean) |  | Y | Was an appointment scheduled |
| CallerAuthenticated(Boolean) |  | Y | Was the caller successfully authenticated |
| Category(Text) |  | N | The Voice command field from the Teams Phone Agent configuration |
| HasMA(Boolean) |  | Y | Is Teams Phone Agent involved in the call |
| MADurationInSeconds(Decimal number) |  | Y | The duration of the call in Teams Phone Agent |
| MaToolUsageDetails(Text) |  | N | JSON blob of Teams Phone Agent features used and result |
| MCSDurationInSeconds(Decimal number) |  | Y | The duration of the call in MCS |
| QandAToolUtilized(Boolean) |  | Y | Was the Questions and Answers tool used |

### Auto attendant dimensions

| Name (Type) | Possible Values | Filters Support | Description |
| --- | --- | --- | --- |
| AutoAttendantCallFlow(Text) |  | Y | Encapsulates the different states of Auto Attendant call |
|  | abs\_search |  | A dial-by-name search occurred |
|  | announcement |  | An announcement was played |
|  | automatic\_menu |  | Default call routing |
|  | call\_termination |  | Call was ended, see AutoAttendantCallResult |
|  | call\_transfer |  | Call was transferred, see AutoAttendantCallResult |
|  | first\_level\_menu |  | Transition state - can be ignored |
|  | main\_menu |  | Greeting message was played |
|  | speech\_input\_confirmation |  | Caller used voice input |
|  | user\_selection |  | Caller used touch tone key entry |
| AutoAttendantCallResult(Text) |  | Y | Final call result |
|  | failed\_to\_establish\_media |  | The media portion of the call couldn't be established |
|  | failover\_to\_operator |  | Call transferred to operator typically due to a system error |
|  | oaa\_chain\_too\_long |  | Too many legs in the AA |
|  | oaa\_session\_too\_long |  | AA session lasted too long |
|  | service\_declined |  | AA didn't accept the call |
|  | service\_terminated |  | AA configuration disconnects the call or call hung up |
|  | terminated\_automatic\_selection |  | AA configuration disconnects the calls |
|  | terminated\_no\_operator |  | Call terminated due to an error - no operator defined |
|  | terminated\_transfer\_failed |  | Call terminated as transfer failed - typically to external number |
|  | transfer\_in\_progress |  | AA-&gt;AA transfer |
|  | transferred\_to\_operator |  | Call was transferred to operator |
|  | transferred\_to\_cq |  | Call was transferred to Call queue |
|  | transferred\_to\_receptionist |  | Same as transferred\_to\_operator |
|  | transferred\_to\_self |  | Call was returned to the start of the AA |
|  | transferred\_to\_shared\_voicemail |  | Call was transferred to shared voicemail |
|  | transferred\_to\_user |  | Call was transferred to a user |
|  | unknown |  | An unknown condition occurred |
|  | user\_terminated |  | Caller hung up |
| AutoAttendantCallerActionCounts(Whole Number) |  | Y | The number of actions (touch tone key or voice entries) the caller performed |
| AutoAttendantChainDurationInSecs(Real Number) |  | Y | The number of seconds the call remained in this portion of the call flow |
| AutoAttendantChainIndex(Whole Number) |  | Y |  |
| AutoAttendantChainStartTime(DateTime) |  | Y | The start time of this portion of the call flow |
| AutoAttendantCount(Whole Number) |  | Y | How many auto attendants the call transitioned through |
| AutoAttendantDirectorySearchMethod(Text) |  | Y | Directory search method |
|  | abs\_search\_dtmf |  | Touch tone |
|  | abs\_search\_voice |  | Voice |
| AutoAttendantId(Text) |  | Y | Auto Attendant GUID |
| AutoAttendantIdentity(Text) |  | N | Resource account URI the call arrived on |
| AutoAttendantTransferAction(Text) |  | Y | Call transfer target type |
|  | AA |  | Transferred to an AA |
|  | CQ |  | Transferred to a CQ |
|  | external\_pstn |  | Transferred to an external number |
|  | shared voicemail |  | Transferred to shared voicemail |
|  | Unknown |  | Unknown action |
| HasAA(Boolean) |  | Y | Is AA involved in call |

### Call queue dimensions

| Name (Type) | Possible Values | Filters Support | Description |
| --- | --- | --- | --- |
| CallQueueAgentCount(Whole Number) |  | Y | Number of agents in Call queue |
| CallQueueAgentOptInCount(Whole Number) |  | Y | Number of agents opted-in to Call queue |
| CallQueueCallResult(Text) |  | Y | Call queue call final state |
|  | agent\_joined\_conference |  | Call answered - conference mode CQ |
|  | callback\_call\_timed\_out |  | Call back call timed out |
|  | declined |  |  |
|  | disconnected |  |  |
|  | error |  |  |
|  | failed |  |  |
|  | invalid |  |  |
|  | overflown |  | Overflow condition met |
|  | timed\_out |  | Timeout condition met |
|  | no\_agent |  | No Agent condition met |
|  | transferred\_to\_agent |  | Call answered - transfer mode CQ |
|  | transferred\_to\_callback\_caller |  | Callback call answered by agent |
| CallQueueDurationSeconds(Real Number) |  | Y | Call duration in the Call queue |
| CallQueueFinalStateAction(Text) |  | Y | Call queue final action |
|  | disconnect |  | time\_out calls |
|  | disconnect\_with\_busy |  | overflown calls |
|  | failed\_to\_accept\_call |  | Call queue couldn't accept the call |
|  | forward |  | Call was forwarded to a Person in the organization or externally |
|  | shared\_voicemail |  | Call was sent to shared voicemail |
|  | other |  | Some other condition occurred |
|  | voicemail |  | Call was sent to personal voicemail |
| CallQueueId(Text) |  | Y | Call queue GUID |
| CallQueueIdentity(Text) |  | N | Resource account URI the call arrived on |
| CallQueueTargetType(Text) |  | Y | Call redirection target |
|  | ApplicationEndpoint |  | Another voice application |
|  | Mailbox |  | Shared voicemail |
|  | Other |  | Some other condition occurred |
|  | Phone |  | External transfer |
|  | User |  | User in the tenant |
| HasCQ(Boolean) |  | Y | Is CQ involved in call |
| TransferredFromCallQueueId(Text) |  | Y | Call queue GUID call was transferred from |
| TransferredFromCallQueueIdentity(Text) |  | N | Resource account URI the call was transferred from |

### Measurements

| Name (Type) | Possible Values | Description |
| --- | --- | --- |
| AvgAutoAttendantChainDurationSeconds(Real Number) |  | The average call duration within each portion of the auto attendant call flow |
| AvgCallDuration(Real Number) |  | The average call duration in seconds |
| AvgCallQueueDurationSeconds(Real Number) |  | The average call queue duration in seconds |
| PSTNTotalMinutes(Real Number) |  | Total call duration in minutes |
| TotalAudioStreamDuration(Real Number) |  | Total audio stream duration in minutes |
| TotalCallCount(Whole Number) |  | Total number of calls |

## Example

Any application that can access RESTful web services can use the VAAC API to retrieve historical data. In the following example, [Postman](https://www.postman.com/) is used.

### Preparation

1. Download and install [Postman](https://www.postman.com/).
2. Download and expand the [postman.zip](https://www.microsoft.com/download/details.aspx?id=104623) file.
3. Import the folder `postman` into Postman.

    [![Screenshot showing import completed.](media/aa-cq/historical-report-postman-01.png)](media/aa-cq/historical-report-postman-01.png#lightbox)

### Accessing VAAC using Postman

1. Select **VAAC - msit** on the top right ***No Environment*** dropdown.
2. Select **Environments** on the left-hand rail menu.
3. Select **VAAC - msit** under **Globals**.
4. Replace **userName**, **password**, and **tenantId** with the applicable credentials.
5. Select **Reset All** in the top right corner.
6. Select **Save**.

    [![Screenshot showing username, password, and tenant ID fields configured.](media/aa-cq/historical-report-postman-02.png)](media/aa-cq/historical-report-postman-02.png#lightbox)
7. Select **Collections** on the left-hand rail menu.
8. Select **Config API Access Token - Prod** and navigate to the **Body** tab.
9. Select **Send**.

    An access token is returned.

    [![Screenshot showing result with access token returned.](media/aa-cq/historical-report-postman-03.png)](media/aa-cq/historical-report-postman-03.png#lightbox)

    If an access token isn't returned, check your credentials to make sure they have [sufficient permissions](aa-cq-report-historical#access-permissions).
10. Select **VAAC ConfigAPI Prod** and navigate to the **Params** tab.

    - Compress the query as outlined
    - URL encode the compressed result as outlined
11. Fill in your query string.
12. Select **Send**.