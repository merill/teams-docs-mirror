---
layout: Conceptual
title: Configure routing options for unassigned phone numbers - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/routing-calls-to-unassigned-numbers
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: roykuntz
ms.date: 2026-09-21T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
audience: Admin
ms.localizationpriority: Medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Learn how to configure routing options for unassigned phone numbers in Microsoft Teams.
locale: en-us
document_id: 8ed4beab-bb0d-fba4-814e-147d22fd97e5
document_version_independent_id: 8ed4beab-bb0d-fba4-814e-147d22fd97e5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/routing-calls-to-unassigned-numbers.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: routing-calls-to-unassigned-numbers
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/routing-calls-to-unassigned-numbers.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 132d8672-b79d-0f68-be82-0e3813bb6893
---

# Configure routing options for unassigned phone numbers - Microsoft Teams | Microsoft Learn

As an administrator, you can route calls to unassigned numbers in your organization. For example, you might want to route calls to unassigned numbers as follows:

- Route all calls to a given unassigned number to a custom announcement.
- Route all calls to a given unassigned number to the main switchboard.

You can route calls to unassigned numbers to a user, to a resource account associated with an Auto attendant or a Call queue, or to an announcement service that will play a custom audio file to the caller.

You can define the routing rules for unassigned numbers individually or as a group by using a regular expression. If a large quantity of phone numbers needs to be routed, it's best to configure as a single rule with a range of numbers instead of one rule per number.

You can configure routing of unassigned numbers by using the Microsoft Teams admin center or by using PowerShell.

## Use Teams admin center

1. In the left navigation of the Teams admin center, go to **Voice** &gt; **Phone Numbers**.
2. On the **Routing rules** tab, select **Add**.
3. Enter a name and description for the rule, and specify the evaluation order for the rule.
4. Decide which kind of rule you want to add. You can select rules where the type of phone number pattern is preconfigured, and you complete the pattern and the routing option. You can also select advanced setup, where you directly enter the regular expression for the phone number pattern and the routing option.
5. Select **Save**.

You can also create a routing rule directly for an unassigned phone number.

1. In the left navigation of the Teams admin center, go to **Voice** &gt; **Phone Numbers**.
2. On the **Numbers** tab, select an unassigned phone number and select **Route** at the top of the view.
3. Enter a name and description for the rule, and specify the evaluation order for the rule.
4. Select the routing option.
5. Select **Save**.

You can test your routing rules by using the Test number feature.

1. In the left navigation of the Teams admin center, go to **Voice** &gt; **Phone Numbers**.
2. On the **Routing rules** tab, select **Test number**.
3. Enter a phone number directly or select **Select a number**, and select one of your unassigned phone numbers from the drop-down.
4. Select **Test**.

## Use PowerShell

To route calls to an unassigned number, use the New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment cmdlet available in Teams PowerShell module 2.5.1 or later.

You need to specify the called number or range of numbers and the associated routing for calls to these numbers. For example, the following command specifies that all calls to the number +1 (555) 222-3333 are routed to the resource account aa@contoso.com:

```PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

The next example specifies that all calls to the number range +1 (555) 333-0000 to +1 (555) 333-9999 are routed to the announcement service, which then plays the audio file MainAnnouncement.wav to the caller.

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## Notes

- Tenants might experience delays in call routing when configuring thousands of rules that match only single numbers. Instead, configure a smaller quantity of rules that match against number ranges.
- To route calls to unassigned Microsoft Calling Plan subscriber numbers, your tenant needs to have available [Communications Credits](what-are-communications-credits).
- To route calls to unassigned Microsoft Calling Plan service numbers, your tenant needs to have at least one **Microsoft Teams Phone Resource Account** license.
- If routing to an announcement, the audio file is played once to the caller. The custom audio file-supported formats are WAV (uncompressed, linear PCM with 8/16/32-bit depth in mono or stereo), WMA (mono only), and MP3. The audio file content can't be more than 5 MB.

    Note

    You're responsible for independently clearing and securing all necessary rights and permissions to use any music or audio file with your Microsoft Teams service. This might include intellectual property and other rights in any music, sound effects, audio, brands, names, and other content in the audio file from all relevant rights holders. Holders can include artists, actors, performers, musicians, songwriters, composers, record labels, music publishers, unions, guilds, rights societies, collective management organizations, and any other parties who own, control or license the music copyrights, sound effects, audio and other intellectual property rights.
- Both inbound calls to Teams and outbound calls from Teams have the called number checked against the unassigned number range.
- If a specified pattern/range contains phone numbers that are assigned to a user or resource account in the tenant, calls to these phone numbers are routed to the appropriate target and not routed to the specified unassigned number treatment. There are no other checks of the numbers in the range. If the range contains a valid external phone number, outbound calls from Teams to that phone number are routed according to the treatment.