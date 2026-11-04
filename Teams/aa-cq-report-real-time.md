---
layout: Conceptual
title: Reporting - Auto attendant and Call queue real-time metrics - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/aa-cq-report-real-time
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
ms.date: 2026-08-31T00:00:00.0000000Z
ms.topic: reference
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
customer-intent: As a Teams Administrator, I want to learn about the real-time metrics that are available and who can see them.
description: Learn about the real-time metrics that are available for Auto attendants and Call queues.
locale: en-us
document_id: ce3c4674-3c2a-665f-c46a-2cb76e2f552d
document_version_independent_id: ce3c4674-3c2a-665f-c46a-2cb76e2f552d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/aa-cq-report-real-time.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: aa-cq-report-real-time
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/aa-cq-report-real-time.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d5320ee5-3c2d-beff-7726-bda0eebf913b
---

# Reporting - Auto attendant and Call queue real-time metrics - Microsoft Teams | Microsoft Learn

Important

Only some of the metrics outlined here are currently available to Queues App users.

For more information about Queues App, see [Manage the Queues app](manage-queues-app). For user documentation about Queues App, see [Use the Queues app for Microsoft Teams](https://support.microsoft.com/office/370ad83e-c2c1-4a9f-8a59-16c98be102e9).

## Auto attendant metrics

The following table contains real-time Auto attendant metrics. All metrics are whole numbers unless otherwise stated.

| Key | Feed | Available To | Description |
| --- | --- | --- | --- |
| tot\_callers | Current & Summary | Authorized Users Only | Total number of all accepted callersA caller can pass through an Auto attendant multiple times in a single call – this caller is only counted once |
| tot\_callers\_int | Current & Summary | Authorized Users Only | Total number of accepted internal callers |
| tot\_callers\_ext | Current & Summary | Authorized Users Only | Total number of accepted external callers |
| tot\_calls | Current & Summary | Authorized Users Only | Total number of all accepted callsA caller can pass through an Auto attendant multiple times in a single call – each individual pass is counted |
| tot\_calls\_int | Current & Summary | Authorized Users Only | Total number of accepted internal calls |
| tot\_calls\_ext | Current & Summary | Authorized Users Only | Total number of accepted external calls |
| tot\_0\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the zero menu option |
| tot\_1\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the one menu option |
| tot\_2\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the two menu option |
| tot\_3\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the three menu option |
| tot\_4\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the four menu option |
| tot\_5\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the five menu option |
| tot\_6\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the six menu option |
| tot\_7\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the seven menu option |
| tot\_8\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the eight menu option |
| tot\_9\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the nine menu option |
| tot\_star\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the star (\*) menu option |
| tot\_hash\_calls | Current & Summary | Authorized Users Only | Total number of times callers selected the hash (#) menu option |
| tot\_op\_calls | Current & Summary | Authorized Users Only | Total number of caller-initiated transfers to the auto attendant operator |
| tot\_app\_calls | Current & Summary | Authorized Users Only | Total number of caller-initiated transfers to another voice application (Auto attendant or Call queue) |
| tot\_extn\_calls | Current & Summary | Authorized Users Only | Total number of caller-initiated transfers to an external phone number |
| tot\_psrn\_calls | Current & Summary | Authorized Users Only | Total number of caller-initiated transfers to a Teams user |
| tot\_vm\_calls | Current & Summary | Authorized Users Only | Total number of caller-initiated transfers to shared voicemail |
| tot\_abandoned\_calls | Current & Summary | Authorized Users Only | Total number of user abandoned calls – caller doesn't select anything |
| tot\_sysxfer\_op\_calls | Current & Summary | Authorized Users Only | Total number of system-initiated transfers to the auto attendant operator |
| tot\_sysxfer\_app\_calls | Current & Summary | Authorized Users Only | Total number of system-initiated transfers to another voice application (Auto attendant or Call queue) |
| tot\_sysxfer\_extn\_calls | Current & Summary | Authorized Users Only | Total number of system-initiated transfers to an external phone number |
| tot\_sysxfer\_psrn\_calls | Current & Summary | Authorized Users Only | Total number of system-initiated transfers to a Teams user |
| tot\_sysxfer\_vm\_calls | Current & Summary | Authorized Users Only | Total number of system-initiated transfers to shared voicemail |
| tot\_sysdisconnected\_calls | Current & Summary | Authorized Users Only | Total number of system-initiated disconnects |
| avg\_call\_time | Current & Summary | Authorized Users Only | Average amount of time calls spent in the auto attendant (*Single-digit decimal*) |
| avg\_caller\_actions | Current & Summary | Authorized Users Only | Average number of caller actions in the auto attendant (*Single-digit decimal*) |

## Call queue metrics

The following table contains real-time Call queue metrics. All metrics are whole numbers unless otherwise stated.

| Key | Feed | Available To | Description |
| --- | --- | --- | --- |
| abandoned\_% | Current | Authorized UsersRepresentatives | Abandoned percentage (*Three-digit decimal*)`(tot_abandoned_calls / tot_offered_calls)` |
| calls\_waiting | Current | Authorized UsersRepresentatives | Number of calls currently waiting |
| calls\_waiting\_longest | Current | Authorized UsersRepresentatives | Longest wait time, in seconds, of oldest call in queueNote: To be deprecated. |
| longest\_waiting\_call\_enqueue\_time | Current | Authorized UsersRepresentatives | Timestamp of arrival time for longest waiting callOffset by UTC offset if supplied during registration.Format: `2024-03-19T11:55:09.9887885+00:00` |
| tot\_offered\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of accepted calls |
| tot\_answered\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of accepted calls answered by representatives |
| tot\_timeout\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of accepted calls that received the timeout treatment |
| tot\_overflowed\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of rejected calls that received the overflow treatment |
| tot\_no\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of accepted calls that received the no agents treatment |
| tot\_abandoned\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of accepted calls that abandoned |
| avg\_speed\_answer | Current & Summary | Authorized UsersRepresentatives | Average speed of answer`(total wait time of answered calls / total answered calls)` |
| tot\_\_presents | Current & Summary | Authorized UsersRepresentatives | Total number of presented but not answered calls |
| sl\_target | Current & Summary | Authorized UsersRepresentatives | Service level target number of seconds**null if not set** |
| sl\_tot\_answered\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of calls answered within the service level target**null if sl\_target is null** |
| sl\_tot\_abandoned\_calls | Current & Summary | Authorized UsersRepresentatives | Total number of calls that abandoned within the service level target**null if sl\_target is null** |
| sl\_met\_handled | Current & Summary | Authorized UsersRepresentatives | Percentage of answered calls that met the service level target (*Two-digit decimal*)`(sl_tot_answered_calls / tot_answered_calls)`**null if sl\_target is null** |
| sl\_met\_no\_abandon | Current & Summary | Authorized UsersRepresentatives | Percentage of answered/abandoned calls that met the service level target (*Two-digit decimal*) - abandoned calls within service level target don't affect service level percentage`(sl_tot_answered_calls / [tot_offered_calls – sl_tot_abandoned_calls])`**null if sl\_target is null** |
| sl\_met\_positive\_abandon | Current & Summary | Authorized UsersRepresentatives | Percentage of calls answered/abandoned that met service level target (*Two-digit decimal*) - abandoned calls within service level target positively affect service level percentage`([sl_tot_answered_calls + sl_tot_abandoned_calls] / tot_offered_calls)`**null if sl\_target is null** |
| sl\_met\_negative\_abandon | Current & Summary | Authorized UsersRepresentatives | Percentage of calls answered/abandoned that met service level target (*Two-digit decimal*) - abandoned calls within service level target negatively affect service level percentage`(sl_tot_answered_calls / tot_offered_calls)`**null if sl\_target is null** |

## Representative by queue metrics

The following table contains real-time representative metrics. All metrics are whole numbers unless otherwise stated.

| Key | Feed | Available To | Description |
| --- | --- | --- | --- |
| tot\_calls\_offered | Current & Summary | Authorized Users^1^Representatives^2^ | Total number of calls offered to the representative. |
| tot\_calls\_answered | Current & Summary | Authorized Users^1^Representatives^2^ | Total number of calls answered by the representative. |

### Notes

1. Authorized Users: for all representatives in the queue.
2. Representatives: for self only – not for all other representatives in the queue.

## Queues App users

Queues App users see real-time metrics based on the time zone set on their computer.