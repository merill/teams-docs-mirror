---
layout: Conceptual
title: Manage transcript API access for Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-transcript-api-access
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to control whether agents and apps can access Teams meeting transcripts through Microsoft Graph APIs and Work IQ.
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: aaronda,siddamsettys,harazi,navali,yoren
ms.service: msteams
ms.subservice: meetings
ms.topic: how-to
ms.date: 2026-10-20T00:00:00.0000000Z
audience: admin
locale: en-us
document_id: 2daffe46-65b1-f6df-8a7e-9a1503f93d60
document_version_independent_id: 2daffe46-65b1-f6df-8a7e-9a1503f93d60
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-transcript-api-access.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-transcript-api-access
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-transcript-api-access.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 266335e4-de3f-249c-b899-47aa66e51e6b
---

# Manage transcript API access for Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Events

You can use the Teams admin center or PowerShell to control whether agents and apps can access Teams meeting transcripts through Microsoft Graph APIs, and whether the transcripts include speaker attribution. You can also control whether agents and apps can access real-time transcripts through Work IQ.

By default, Microsoft Graph access is off, so agents and apps can't access meeting transcripts, regardless of app-level permissions. Work IQ access is also off by default. For details, see Manage Work IQ access to real-time transcripts.

## Using the Teams admin center

To enable transcript API access by using the Teams admin center, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting settings**.
2. Under **Transcript API access**, turn the **Microsoft Graph access** toggle **On** to allow apps and agents to access meeting transcripts.

    [![Screenshot of Transcript API access setting in the Teams admin center.](media/transcript-api-access.png)](media/transcript-api-access-expand.png#lightbox)
3. Select **Configure**, and then do the following:

    - To include speaker attribution in transcripts accessed through Graph API, turn the **Include speaker attribution** toggle **On**. By default, this setting is off.
    - To allow or block individual apps and agents from accessing transcripts, use the link to the Microsoft Entra admin center to manage API permissions for each app.

## Using PowerShell

To configure transcript API access by using PowerShell, use the [Set-CsTeamsMeetingConfiguration](/en-us/powershell/module/microsoftteams/set-csteamsmeetingconfiguration) cmdlet with the following parameters:

- `-EnableGraphTranscriptAccess`: When set to **true**, agents and apps can access meeting transcripts through Graph APIs.
- `-EnableAttributedTranscripts`: When set to **true**, transcripts accessed through Graph APIs include speaker attribution.

For example, to enable Microsoft Graph access to meeting transcripts in your organization and include speaker attribution, run the following command:

```powershell
Set-CsTeamsMeetingConfiguration -EnableGraphTranscriptAccess $true -EnableAttributedTranscripts $true -Identity Global
```

## Manage Work IQ access to real-time transcripts

Work IQ lets agents and apps, including ones your organization builds, receive the transcript of a Teams meeting or call while it's in progress. The Work IQ access setting controls whether they can. It's independent of Microsoft Graph access, and it's off by default.

Important

Work IQ access takes effect on November 14, 2026. If apps in your organization already receive real-time transcripts through Work IQ, turn on Work IQ access before that date to keep them working.

Turning off Work IQ access doesn't turn off transcription or change Microsoft Graph access. Microsoft AI experiences in Teams, such as Microsoft 365 Copilot, Facilitator, and intelligent recap, keep working as configured.

### Turn on Work IQ access

In the Teams admin center, go to **Meetings** &gt; **Meeting settings**. Under **Transcript API access**, turn the **WorkIQ access** toggle **On**.

To use PowerShell, run the [Set-CsTeamsMeetingConfiguration](/en-us/powershell/module/microsoftteams/set-csteamsmeetingconfiguration) cmdlet with the `-EnableWorkIQTranscriptAccess` parameter. When set to **true**, agents and apps can access real-time transcripts through Work IQ. This parameter requires the latest version of the Teams PowerShell module.

```powershell
Set-CsTeamsMeetingConfiguration -EnableWorkIQTranscriptAccess $true -Identity Global
```

### When apps receive real-time transcripts

Turning on Work IQ access doesn't, by itself, give apps a transcript. An app receives a real-time transcript only when these conditions are also met:

- AI is allowed in the meeting, as shown in the following table.
- Transcription is running. Work IQ doesn't start transcription. For more information, see [Manage transcription and captions for Teams meetings](meeting-transcription-captions).
- The app acts on behalf of a signed-in user and has the permissions it needs in Microsoft Entra ID.
- Work IQ is enabled for that user's organization. For more information, see [Enable your tenant for Work IQ](/en-us/microsoft-365/copilot/extensibility/work-iq/enable-work-iq).

| Allow AI in all meetings | Work IQ access | Result |
| --- | --- | --- |
| Off | Off or On | No transcript is available. |
| On | Off | Work IQ requests are denied. Other AI experiences work as configured. |
| On | On | Agents and apps can receive the real-time transcript. |

### How the setting is applied

- **The organizer's organization decides.** Work IQ uses the setting of the organization that organized the meeting, not the setting of the app's organization or of the user the app acts for.
- **Transcripts in progress continue.** Turning off Work IQ access doesn't stop transcripts that apps are already receiving. They continue until the meeting or call ends. New requests are denied.
- **Changes aren't immediate.** It can take some time before a change applies to new requests.
- **Speaker names are included.** Real-time transcripts that apps receive through Work IQ include speaker names. The **Include speaker attribution** setting applies only to Microsoft Graph.