---
layout: Conceptual
title: Intelligent recap in Teams meetings without saving transcripts - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/intelligent-recap-without-saving-transcripts
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: xiale
ms.date: 2026-10-26T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
audience: admin
f1.keywords:
- NOCSH
description: Learn how to manage intelligent recap without transcript retention. This feature lets Copilot-licensed organizers generate AI meeting summaries without saving transcripts.
locale: en-us
document_id: 46f17cec-5072-318c-96e4-9e9ab0cd9ab1
document_version_independent_id: 46f17cec-5072-318c-96e4-9e9ab0cd9ab1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/intelligent-recap-without-saving-transcripts.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: intelligent-recap-without-saving-transcripts
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/intelligent-recap-without-saving-transcripts.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
platformId: 885eedf8-382d-ed44-7ce9-c88126e433aa
---

# Intelligent recap in Teams meetings without saving transcripts - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Events ![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Calls

## Overview

Intelligent recap without saving transcripts provides AI-generated meeting summaries for organizations that don't allow meeting transcripts or recordings, or that need to limit transcript and recording retention for compliance reasons. Organizers with a Microsoft Copilot license can generate AI summaries of Teams meetings without saving a recording or persistent transcript.

With this feature, an AI summary is generated even when recording and transcription aren't enabled. Organizers in your organization with a Copilot license can generate the summary, and attendees in your organization who have a Copilot license can view it on the **Recap** tab after the meeting. No meeting transcript or recording is saved as part of this experience. The AI summary is stored as a read-only Word document in the organizer's OneDrive. For more information about the user experience, see [Use intelligent recap in Microsoft Teams meetings without transcription](https://support.microsoft.com/teams/meetings/use-intelligent-recap-microsoft-teams-meetings-without-transcription).

This feature is supported for scheduled meetings only.

As an admin, you can manage whether this feature is available in meetings and how long AI summary documents are retained before they expire.

Note

This article covers intelligent recap without transcript retention. For information about the full intelligent recap experience that includes transcription and recordings, see [Intelligent recap for Teams calls, meetings, and events](intelligent-recap-calls-meetings).

## Manage intelligent recap without saving transcripts

### Enable intelligent recap without saving transcripts

Intelligent recap without saving transcripts is automatically available to users who have a Microsoft Copilot license and are assigned a Teams meeting policy with Copilot enabled. For more information about enabling Copilot in Teams meetings for users, see [Manage Microsoft Copilot in Teams meetings and events](copilot-teams-transcription).

When intelligent recap without saving transcripts is available:

- Organizers with a Copilot license can turn it on or off in **Meeting options** before the meeting.
- Organizers, co-organizers, and presenters with a Copilot license can turn it on or off during the meeting by using the meeting controls.

### Turn off intelligent recap

There isn't a separate policy setting for intelligent recap without saving transcripts. To prevent users from using this feature while keeping Copilot enabled, turn off intelligent recap in the Teams meeting policy.

Important

Turning off intelligent recap disables intelligent recap for all meetings, regardless of whether transcripts are saved.

To turn off intelligent recap, use the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/microsoftteams/set-csteamsmeetingpolicy) cmdlet and set the `-AllowIntelligentRecap` parameter to `$false`.

Example:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policyname> -AllowIntelligentRecap $false
```

## Configure expiration for AI summary documents

AI summary documents are stored in the Meetings folder of the meeting organizer's OneDrive and, by default, expire after 120 days. You can configure a different expiration period in the Teams admin center or by using PowerShell.

### Use the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing policy or create a new one.
3. Under **AI memory and archive**, next to **Set a default expiration time for Intelligent recap docx**, enter the number of days that documents are retained. You can specify a value from **1** to **9999** days, or **-1** for no expiration.
4. Select **Save**.

### Use PowerShell

Use the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/microsoftteams/set-csteamsmeetingpolicy) cmdlet with the `-IntelligentRecapDocxFileExpirationDays` parameter.

The following example sets the default expiration time to 180 days.

```powershell
Set-CsTeamsMeetingPolicy -Identity <policyname> -IntelligentRecapDocxFileExpirationDays 180
```

## Compliance

- AI summary documents support Microsoft Purview eDiscovery. The document title, keywords, and content are indexed for search.
- AI summary documents support Microsoft Purview legal hold.

## FAQ

### How can I enable or disable this feature?

- Enable: Intelligent recap without saving transcripts is automatically available to users who have a Copilot license and a meeting policy with Copilot enabled.
- Disable: Use the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/microsoftteams/set-csteamsmeetingpolicy) cmdlet with the `-AllowIntelligentRecap` parameter to turn off intelligent recap while keeping Copilot enabled. Turning off intelligent recap disables intelligent recap for all meetings, regardless of whether transcripts are saved, and the related settings are unavailable in Teams.

### Is an AI summary generated for scheduled meetings, unscheduled meetings, and calls?

AI summaries are generated for scheduled meetings only.

### While a recap is being generated from live meeting data, where is the transcription data temporarily stored?

During recap generation, transcription data is temporarily stored in a service-managed cache used by the recap service to generate the AI summary. Meeting participants don't have access to this temporary data. The cached data is automatically purged within one day. No meeting transcript is saved or retained after the meeting.

### Who can access the AI summary?

Attendees in the same organization as the meeting organizer who have a Copilot license can access the AI summary. Guests and external attendees can't access it.

### Can organizers delete an AI summary?

Yes. Meeting organizers can delete the AI summary from the **Recap** tab or the corresponding Word document in OneDrive. Deleting the AI summary from either location also deletes it from the other location.