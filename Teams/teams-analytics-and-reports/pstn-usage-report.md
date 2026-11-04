---
layout: Conceptual
title: Microsoft Teams PSTN usage report - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-analytics-and-reports/pstn-usage-report
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
ms.reviewer: dantelo
ms.date: 2026-04-26T00:00:00.0000000Z
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use the Teams PSTN usage report in the Microsoft Teams admin center to get an overview of calling and audio conferencing usage in your organization.
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
locale: en-us
document_id: 0ad0c889-56d5-35fe-de15-177b6d922d07
document_version_independent_id: e4363647-33e1-b665-5881-169fb619a5b3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-analytics-and-reports/pstn-usage-report.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-analytics-and-reports/pstn-usage-report
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-analytics-and-reports/pstn-usage-report.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 757b6f99-74e4-b168-fc25-97abc0538662
---

# Microsoft Teams PSTN usage report - Microsoft Teams | Microsoft Learn

The Teams PSTN (Public Switched Telephone Network) usage report in the Microsoft Teams admin center gives you an overview of calling and audio conferencing activity in your organization. You can view detailed calling activity for Calling Plans if you use Microsoft as your telephony carrier and for Direct Routing if you use your own telephony carrier.

The **Calling Plans** tab groups PSTN calling information for both Calling Plans and Operator Connect. This shows information including the number of minutes that users spent in inbound and outbound PSTN calls and the cost of these calls. The **Direct Routing** tab shows you information including the call start and end times, SIP address, and SIP call flow for diagnosing issues between your organization's SBC and Microsoft's SIP Proxy. Use the information in this report to gain insight into PSTN usage in your organization and help you to investigate, plan, and make business decisions.

Note

If you have a Telstra calling plan, you will not see any call detail records in the PSTN usage report. Please contact Telstra for your reporting needs.

## View the PSTN usage report

1. In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** &gt; **Usage reports**. On the **View reports** tab, under **Report**, select **PSTN and SMS (preview) usage**.
2. Under **Date range**, select a predefined range of 7 or 28 days, or set a custom range, and then select **Run report**.

## Interpret the report

### Calling Plans

![Screenshot of the Calling Plans PSTN usage report in the admin center.](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)

| Callout | Description |
| --- | --- |
| **1** | The report can be viewed for trends over the last 7 days, 28 days, or a custom date range that you set. |
| **2** | Each report has a date for when it was generated. The reports usually reflect a 24 to 48 hour latency from time of activity. |
| **3** | The X axis is the selected date range for the specific report. The Y axis is the total number of calls over the selected time period. Hover over the dot on a given date to see the total calls on that date. |
| **4** | The table gives you a breakdown of PSTN usage per call. <br>- **Start time (UTC)** is the time the call started.<br>- **Display name** is the display name of the user. You can click the display name to go to the user's setting page in the Microsoft Teams admin center.<br>- **Username** is the user's sign-in name.<br>- **Phone number** is the number that received the call for inbound calls or the number dialed for outbound calls.<br>- **Caller ID** is the number that placed the call for inbound calls or the number that received the call for outbound calls. **Operator** is the PSTN carrier that connect Teams Phone to PSTN. For calls via Calling Plans, this will be Microsoft, for call via Operator Connect plans, this will be your existing PSTN carrier.<br>- **Call type** is whether the call was a PSTN outbound or inbound call and the type of call such as a call placed by a user or an audio conference. The calls types you may see include:**Teams user call types**<br>    - **user\_in** - the user received an inbound PSTN call<br>    - **user\_out** - the user placed an outbound PSTN call<br>    - **user\_out\_conf** - the user added two or more PSTN participants to the call such as a three-way conference call<br>    - **user\_out\_transfer** - the user transferred the call to a PSTN number<br>    - **user\_out\_forwarding** - the user forwarded the call to a PSTN number<br>    - **conf\_in** - an inbound call to the Audio Conferencing bridge<br>    - **conf\_out** - an outbound call from the Audio Conferencing bridge usually to add a PSTN number to the conference<br>    - **unassigned\_in** - an inbound PSTN call via Calling Plan to an unassigned number<br>    - **emergency\_in** - the user received an inbound PSTN emergency call<br>    - **emergency\_out** - the user placed an outbound PSTN emergency call<br>    - **fmc\_in** - the user received an inbound PSTN call from native dialer<br>    - **fmc\_out** - the user placed an outbound PSTN call to native dialer<br><br>**Teams bots call types**<br>    - **ucap\_in** - an inbound PSTN call to Teams bot such as auto attendant or call queue<br>    - **ucap\_out** - an outbound PSTN call from a Teams bot such as auto attendant or call queue<br>    - **ucap\_out\_conf** - a Teams bot such as auto attendant or call queue added two or more PSTN participants to the call such as a three way call conference<br>- **Called to** is the number dialed.<br>- **Destination dialed** is the country or region dialed.<br>- **Cost** is the amount of money or cost of the call that's charged to your account.<br>- **Currency** is the type of currency used to calculate the cost of the call.<br>- **Duration** is how long the call was connected.<br>- **Source of call duration** is the source Call Duration field is populated from.<br>- **Domestic/International** tells you whether the call was domestic (within a country or region) or international (outside a country or region) based on the user's location.<br>- **Call ID** is the call ID for a call. It's an identifier for the call you can use when calling Microsoft Support.<br>- **Number type** is the user's phone number type, such as a service of toll-free number.<br>- **User's location** is the user's country or region.<br>- **Conference ID** is the conference ID of the audio conference.<br>- **Capability**is the license used for the call. The license types you may see include:<br>    - **MCOEV or MCOEV\_VIRTUALUSER or MCOEV\_VIRTUALUSER\_GOV** - Voice Applications such as Auto-Attendant or Call Queues<br>    - **FREECALL** - In the event of a technical issue that prevents us from pricing a call, the call is provided for free and will appear with this capability<br>    - **MCOPSTN1 or MCOPSTN1BR or MCOPSTN1MX** - Domestic Calling Plan (3000 min US / 1200 min EU, BR, MX plans)<br>    - **MCOPSTN2 or MCOPSTN2BR or MCOPSTN2MX** - International Calling Plan (3000 min US, UK, CA, PR) / 1200 min BR, MX, others)<br>    - **MCOPSTN5** - Domestic Calling Plan (120 min calling plan)<br>    - **MCOPSTN6** - Domestic Calling Plan (240 min calling plan)<br>    - **MCOPSTN8** - Domestic Calling Plan 120 min per user (not pooled across users like the other calling plans are)<br>    - **MCOPSTN9** - International Calling Plan<br>    - **MCOPSTNCAP** - Common Area Phone<br>    - **MCOPSTNPP** - Communications Credits<br>    - **MCOMEETADD** - Audio Conferencing<br>    - **MCOMEETADD\_DIALOUT\_US** - Audio Conferencing US and Canada dial-out plan<br>    - **MCOMEETADD\_CN\_GLOBAL** - Audio Conferencing for non-China users<br>    - **MCOMEETADD\_TATA** - Tata Communications Connections<br>    - **MCOMEETACPEA** - Audio Conferencing Pay-Per-Minute<br>    - **MCOMEETACPEA\_TATA** - Tata Communications Connections Audio Conferencing Pay-Per-Minute<br>    - **MCOMEETACPEA\_GOV** - Audio Conferencing Pay-Per-Minute for Government<br><br> To see the information that you want in the table, make sure to add the columns to the table. |
| **5** | Select **Edit columns** to add or remove columns in the table. |
| **6** | Select **Filter** to filter the report by username or call type. |
| **7** | Select **Full screen** to view the report in full screen mode. |
| **8** | You can export the report to a CSV file for offline analysis. Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready. |

### Direct Routing

![Screenshot of the Direct Routing PSTN usage report in the admin center.](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)

| Callout | Description |
| --- | --- |
| **1** | The report can be viewed for trends over the last 7 days or 28 days. |
| **2** | Each report has a date for when it was generated. The reports usually reflect a 24 to 48 hour latency from time of activity. |
| **3** | The X axis is the selected date range for the specific report. The Y axis is the total number of calls over the selected time period.Hover over the dot on a given date to see the total calls on that date. |
| **4** | For any selected call, click **SIP Call Flow** to view the SIP call flow for diagnosing call flow issues between your organization's Session Border Controller (SBC) and Microsoft's Session Initiation Protocol (SIP) Proxy in Direct Routing deployments. By selecting SIP call flow you can see a visual, chronological sequence of the SIP signaling messages exchanged between SBC and SIP Proxy. For more information on the SIP call flow for Direct Routing, see [SIP call flow for Direct Routing in Teams Admin Center](/en-us/microsoftteams/direct-routing-monitor-sip-ladder). |
| **5** | The table gives you a breakdown of PSTN usage per call. <br>- **Display name** is the display name of the user. You can click the display name to go to the user's settings page in the Microsoft Teams admin center. The name can also be the name of a bot, for example the Call Queue or Cloud Auto Attendant.<br>- **Username** is the user's sign-in name.<br>- **Callee number** is the number of the user or the bot who received the call. On an inbound call to a Teams user it will be the Teams user, on an outbound call from a Teams user it will be the PSTN User.<br>- **Caller number** is the number of the user or the bot who made the call.<br>- **Call type** is whether the call was a PSTN outbound or inbound call and the type of call such as a call placed by a user or an audio conference. The call types you may see include:**Teams user call types**<br>    - **dr\_in** - the user received an inbound PSTN call<br>    - **dr\_out** - the user placed an outbound PSTN call<br>    - **dr\_out\_user\_conf** - the user added a PSTN participant to the call<br>    - **dr\_out\_user\_forwarding** - the user forwarded the call to a PSTN number<br>    - **dr\_out\_user\_transfer** - the user transferred the call to a PSTN number<br>    - **dr\_emergency\_out** - the user made an emergency call<br>    - **dr\_unassigned\_in** - an inbound PSTN call via Direct Routing to an unassigned number<br>**ByotIn**- inbound PSTN call towards Direct Routing licensed user- **ByotOut** - Outbound call made from Direct Routing licensed user<br>**ByotOutUserConf**- User escalating 1:1 call to meeting adding a PSTN participant and not having a CPC license- **ByotOutUserForwarding** - PSTN outbound call from forwarded user to tenant's Carrier<br>**ByotOutUserTransfer**- PSTN outbound call from transferred user to tenant's Carrier- **ByotOutEmergency** - PSTN outbound call from Direct Routing licensed user<br><br>**Teams bots call types**<br>- **dr\_in\_bot** - an inbound PSTN call to a Teams bot such as auto attendant or call queue<br>- **dr\_out\_bot** - an outbound PSTN call from a Teams bot such as auto attendant or call queue<br><br>- **Invite time (UTC)** is the time when the initial Invite was sent on an outbound call from a Teams user or bot call to the SBC, or received on an inbound call to a Teams or bot call by the SIP Proxy component of Direct Routing from the SBC.<br>- **Start time (UTC)** is the time when the SIP proxy received the final answer (SIP Message "200 OK") from the SBC on an outbound call (Teams/Bot to a PSTN User), or after the SIP Proxy send the Invite to the next hop within the Teams backend on an inbound call (PSTN User to a Teams/Bot).<br>- **Failure time (UTC)** is the time the call failed. For failed calls only. Final SIP Code, Final Microsoft Subcode, and Final SIP Phrase provide the reasons why the call failed and can help with troubleshooting.<br>- **End time (UTC)** is the time the call ended (for successful calls only).<br>- **Duration** is how long the call was connected, from invite to the call end or failure. For call forwarding, duration includes ringing in the Call Queue.<br>- **Number type** is the user's phone number type, such as a service of toll-free number.<br>- **Media bypass** indicates whether the trunk was enabled for media bypass.<br>- **SBC FQDN** is the fully qualified domain name (FQDN) of the Session Border Controller (SBC).<br>- **Azure region for Media** is the data center that was used as media path in a non-bypass call.<br>- **Azure region for Signaling** is the data center that was used for signaling for both bypass and non-bypass calls.<br>- **Event type** is the event type of the call. You'll see Success for successful calls and Attempt for failed calls.<br>- **Final SIP code** is the code with which the call ended. Select the Final SIP Code of the selected call to view the SIP call flow. For more information on the SIP call flow for Direct Routing, see [SIP call flow for Direct Routing in Teams Admin Center](/en-us/microsoftteams/direct-routing-monitor-sip-ladder).<br>- **Final Microsoft subcode** is a code that indicates specific actions that occurred.<br>- **Final SIP phrase** is the description of the SIP code and Microsoft subcode.<br>- **Correlation ID** is a unique identifier for the call that you can use when calling Microsoft Support.<br>- **Shared Correlation ID** is only visible in the downloadable CSV file and does not exist in the portal. The shared correlation ID exists in at least two calls which are related. Please see detailed description below.<br> To see the information that you want in the table, make sure to add the columns to the table. |
| **6** | Select **Edit columns** to add or remove columns in the table. |
| **7** | Select **Full screen** to view the report in full screen mode. |
| **8** | Select **Export to Excel** to download the data in a comma separated file (CSV) for offline analysis or to use it as input for your billing system. |

#### Caller/Callee fields considerations

Depending on the call direction, the Caller or Callee names can contain non-E164 numbers.

These fields can come from the customer SBC(s). There are three formats that the SBC can send to Direct Routing: E.164 numbers, non-E.164 numbers, and strings.

- E.164 phone number from a user who has an E.164 number to a user who also has an E.164 number.
- Call from a non-E.164 number. A user from a third-party PBX interconnected with Direct Routing makes a call to a Teams user. In this case, the caller number might be any non-E.164 number, for example +1001.
- A spammer calls and doesn't present a number, only a name, for example "Internal Revenue Service". This string will be shown in the reports.

#### Phone number obfuscation

Per-country/region privacy requirements include the obfuscation of the external (not owned by the customer) phone numbers. The three or four last digits of the phone number are replaced with asterisks (+123 456789\*\*\*).

For incoming calls, the caller number is obfuscated, for outgoing calls, the callee number is obfuscated. Note that these rules apply to the PSTN and Direct Routing reports in Tenant Admin Center, data export, and the PSTN call logs available via Microsoft Graph. Phone number obfuscation rules in other reports, such as Call Analytics and Call Quality Dashboard, may differ.

The obfuscation is based on the organization's location (country/region). Full phone numbers are shown for the countries/regions that are not listed in the following table:

| Country/Region | Number of obfuscation digits |
| --- | --- |
| BE – Belgium | 3 |
| CH – Switzerland | 4 |
| DE – Germany | 3 |
| DK – Denmark | 3 |
| ES – Spain | 3 |
| FI – Finland | 3 |
| FR – France | 4 |
| IT – Italy | 3 |
| NL – Netherlands | 3 |
| NO – Norway | 3 |
| SE – Sweden | 3 |

#### About Shared Correlation ID

The Shared Correlation ID only exists in the exported Excel file that you download and indicates that two or more calls are related. The following explains the different scenarios, and when Shared Correlation ID is present.

1. PSTN User 1 on a PSTN endpoint called Teams User 1 on Teams client, call type Dr\_In, correlation ID 57f28917-42k5-4c0c-9433-79734873f2ac, no shared correlation ID.
2. Teams User 1 on Teams client called PSTN User 1 on a PSTN endpoint, call type Dr\_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4, no shared correlation ID.
3. PSTN User 1 on a PSTN endpoint called a Teams User 2 on Teams client, call type Dr\_In f45e9a25-9f94-46e7-a457-84f5940efde9, shared correlation ID f45e9a25-9f94-46e7-a457-84f5940efde9.
4. Existing call 3 with correlation ID "f45e9a25-9f94-46e7-a457-84f5940efde9". PSTN User 1 in a call with Teams User 2. Teams User 2 transferred (blind or consultative) a call to Teams or PSTN User, call type Dr\_Out\_User\_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0, shared correlation ID f45e9a25-9f94-46e7-a457-84f5940efde9.

#### Data retention

Per-country regulatory requirements specify data retention of detailed call records. Per-country retention period in days is listed in the following table:

| Country | PSTN Calling Plans | Direct Routing |
| --- | --- | --- |
| CA – Canada | 150 | 150 |
| CH – Switzerland | 365 | 365 |
| DE – Germany | 180 | 150 |
| DK – Denmark | 365 | 365 |
| FI – Finland | 365 | 365 |
| FR – France | 365 | 365 |
| IT – Italy | 730 | 730 |
| MX – Mexico | 730 | 730 |
| NL – Netherlands | 180 | 180 |
| NO – Norway | 150 | 150 |
| SE – Sweden | 180 | 180 |
| UK – United Kingdom | 450 | 450 |
| All other countries | 365 | 150 |

Note that these rules apply to the PSTN and Direct Routing reports in Tenant Admin Center, data export, and the PSTN and Direct Routing call logs available via Microsoft Graph. Data retention in other reports, such as Call Analytics and Call Quality Dashboard, may differ. Data retention for the call history shown in Microsoft Teams may be accessed for a longer period of time. Requests to delete call history data shown in Microsoft Teams may be made by contacting customer support

The retention period is based on the user's location (country). If the tenant administrator does not set a user's location, the default value for the location of a user is the location of the tenant.

## Exporting the reports

The PSTN Usage Report supports exports for Calling Plans and Direct Routing.

Click **Calling plans** or **Direct Routing**

Click the **Excel** icon to trigger the download of the report to Excel. Export process can take from a few seconds to several minutes to complete, depending on the quantity of the data. The downloaded file will be saved to your default Downloads folder.

Open the .zip folder named "**Export.callingplans.`[identifier]`.zip**" or "**Export.directrouting.`[identifier]`.zip**", depending on which report you are downloading. The identifier used for the export file is a unique ID that can also be used for troubleshooting.

In addition to PSTN and Direct Routing files, the archive contains file "**parameters.json**", with the selected export time range and capabilities.

Exported files are in Comma Separated Values (CSV) format, compliant with [RFC 4180](https://tools.ietf.org/html/rfc4180) standard. The files can be opened in Excel or any other standards-compliant editor without requiring any transformations.

The first row of the CSV contains column names. All dates are UTC and in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.

### Exported PSTN usage report

You can export data up to one year from the current date unless country/region-specific regulations prohibit retention of the data for 12 months.

| # | Name | [Data type (SQL Server)](/en-us/sql/t-sql/data-types/data-types-transact-sql) | Description |
| --- | --- | --- | --- |
| 0 | UsageId | `uniqueidentifier` | Unique call identifier |
| 1 | Call ID | `nvarchar(64)` | Call identifier. Not guaranteed to be unique |
| 2 | Conference ID | `nvarchar(64)` | ID of the audio conference |
| 3 | User Location | `nvarchar(2)` | Country code of the user, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 4 | Microsoft Entra ObjectId | `uniqueidentifier` | Calling user's ID in Microsoft Entra ID. This and other user info will be null/empty for bot call types (ucap\_in, ucap\_out) |
| 5 | UPN | `nvarchar(128)` | UserPrincipalName (sign-in name) in Microsoft Entra ID.This is usually the same as user's SIP Address, and can be same as user's e-mail address |
| 6 | User Display Name | `nvarchar(128)` | Display name of the user |
| 7 | Caller ID | `nvarchar(128)` | Number that received the call for inbound calls or the number dialed for outbound calls. [E.164](https://en.wikipedia.org/wiki/E.164) format |
| 8 | Call Type | `nvarchar(32)` | Whether the call was a PSTN outbound or inbound call and the type of call such as a call placed by a user or an audio conference |
| 9 | Call Direction | `nvarchar(32)` | Whether the call was a PSTN outbound or inbound call |
| 10 | Number Type | `nvarchar(16)` | User's phone number type, such as a service of toll-free number |
| 11 | Domestic/International | `nvarchar(16)` | Whether the call was domestic (within a country or region) or international (outside a country or region) based on the user's location |
| 12 | Destination Dialed | `nvarchar(64)` | Country or region dialed |
| 13 | Destination Number | `nvarchar(32)` | Number dialed in [E.164](https://en.wikipedia.org/wiki/E.164) format |
| 14 | External Country | `nvarchar(16)` | Two digits country code dialed |
| 15 | Start Time | `datetimeoffset` | Call start time |
| 16 | End Time | `datetimeoffset` | Call end time |
| 17 | Duration Seconds | `int` | How long the call was connected |
| 18 | Connection Fee | `numeric(16, 2)` | Connection fee price |
| 19 | Charge | `numeric(16, 2)` | Amount of money or cost of the call that is charged to your account |
| 20 | Currency | `nvarchar(3)` | Type of currency used to calculate the cost of the call ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
| 21 | Capability | `nvarchar(32)` | The license used for the call |
| 22 | Operator | `nvarchar(32)` | Microsoft |
| 23 | Source of Call Duration | `nvarchar(32)` | Microsoft |
| 24 | Administrative Units | `uniqueidentifier` | Collection of administrative units associated to a call. |

### Exported Direct Routing usage report

You can export data up to five months (150 days) from the current date unless country/region-specific regulations prohibit retention of the data for that period.

| # | Name | [Data type (SQL Server)](/en-us/sql/t-sql/data-types/data-types-transact-sql) | Description |
| --- | --- | --- | --- |
| 0 | CorrelationId | `uniqueidentifier` | Call identifier. Multiple legs of the same call can share the same CorrelationId |
| 1 | Microsoft Entra ObjectId | `uniqueidentifier` | Calling user's ID in Microsoft Entra ID. This and other user info can be null/empty for bot call types |
| 2 | UPN | `nvarchar(128)` | UserPrincipalName (sign-in name, Microsoft Entra ID) of the user or bot that made or received the call.This is usually the same as user's SIP Address, and can be same as user's e-mail address |
| 3 | Display Name | `nvarchar(128)` | The name of a user or a calling bot (for example, Call Queue or Auto Attendant) as set in Microsoft 365 admin center |
| 4 | User country | `nvarchar(2)` | Country code of the user, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
| 5 | Invite time | `datetimeoffset` | When the initial Invite send on outbound from Teams user or bot call to the SBC, or received on inbound to Teams or bot call by the SIP Proxy component of Direct Routing from the SBC |
| 6 | Start time | `datetimeoffset` | Time when the SIP proxy received the final answer (SIP Message "200 OK") from the SBC on outbound (Teams/Bot to a PSTN User), or after the SIP Proxy send the Invite to the next hop within Teams backend on inbound call (PSTN User to a Teams/Bot).For failed and unanswered calls, this can be equal to invite or failure time |
| 7 | Failure time | `datetimeoffset` | Only exists for failed (not fully established) calls |
| 8 | End time | `datetimeoffset` | Only exists for successful (fully established) calls. Time when call ended |
| 9 | Duration (seconds) | `int` | Duration of the call, from invite to the call end or failure. For call forwarding, duration includes ringing in the Call Queue. |
| 10 | Success | `nvarchar(3)` | Yes/No. Success or attempt |
| 11 | Caller Number | `nvarchar(32)` | Number of the user or bot who made the call. On inbound to a Team user call it will be a PSTN User, on outbound from Teams user call it will be the Teams user number |
| 12 | Callee Number | `nvarchar(32)` | Number of the user or bot who received the call. On inbound to a Team user call it will be the Teams user, on outbound from Teams user call it will be the PSTN User |
| 13 | Call type | `nvarchar(32)` | Call type and direction |
| 14 | Call Direction | `nvarchar(32)` | Whether the call was a PSTN outbound or inbound call |
| 15 | Azure region for Media | `nvarchar(8)` | The datacenter used for media path in non-bypass call |
| 16 | Azure region for Signaling | `nvarchar(8)` | The datacenter used for signaling for both bypass and non-bypass calls |
| 17 | Final SIP code | `int` | The code with which the call ended, [RFC 3261](https://tools.ietf.org/html/rfc3261) |
| 18 | Final Microsoft subcode | `int` | In addition to the SIP codes, Microsoft has own subcodes that indicate the specific issue |
| 19 | Final SIP Phrase | `nvarchar(256)` | Description of the SIP code and Microsoft subcode |
| 20 | SBC FQDN | `nvarchar(64)` | Fully qualified domain name of the session border controller |
| 21 | Media bypass | `nvarchar(3)` | Yes/No. Indicates if the trunk was enabled for media bypass or not |
| 22 | Shared correlation ID | `uniqueidentifier` | Indicates that two or more calls are related |
| 23 | Administrative Units | `uniqueidentifier` | Collection of administrative units associated to a call. |
| 24 | Transfer or Correlation ID | `uniqueidentifier` | Indicates CorrelationId from call between Transferee and Transferor |