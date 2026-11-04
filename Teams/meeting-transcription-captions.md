---
layout: Conceptual
title: Admins- Manage transcription and captions for Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-transcription-captions
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: anahitab
ms.topic: article
ms.service: msteams
ms.subservice: meetings
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
- Tier1
- magic-ai-copilot
ms.reviewer: harinlee, fezuo
ms.date: 2026-07-06T00:00:00.0000000Z
ms.update-cycle: 180-days
search.appverid: MET150
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Learn how to configure transcription and caption policies for Teams meetings and events.
locale: en-us
document_id: a8e28688-73cd-6845-3fcf-a1e8ee9ea188
document_version_independent_id: a8e28688-73cd-6845-3fcf-a1e8ee9ea188
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-transcription-captions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-transcription-captions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-transcription-captions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 3edf6620-75ad-4589-28cb-706f3ece7cf7
---

# Admins- Manage transcription and captions for Teams meetings - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Note

When organizers turn off Microsoft Copilot in Teams meetings and events, recording and transcription are also turned off. To learn more about Copilot, see [Manage Microsoft Copilot in Teams meetings and events](copilot-teams-transcription).

Microsoft Teams offers transcription and live captions to enhance accessibility and engagement during meetings and events. Transcription creates a real-time written record of what was said during a meeting or event. Participants can view the transcript after the meeting along with timestamps and speaker attribution. Live captions provide real-time subtitles during the meeting, but Teams doesn't save captions.

As an admin, you can manage whether your users can use and access transcripts and captions for Teams meetings and events.

Transcripts are stored together with meeting recordings in OneDrive and SharePoint storage. To learn more about how transcripts are stored, see [Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint](tmr-meeting-recording-change) and [View, edit, and manage video transcripts and captions](https://support.microsoft.com/office/3cb9acb6-05b2-4f59-a50d-7df61123aa20#bkmk_how-captions-and-transcripts-are-stored).

For information on how your users can use transcription, see [View live transcription in a Teams meeting](https://support.microsoft.com/office/dc1a8f23-2e20-4684-885e-2152e06a4a8b). To learn how your end users can use live captions, see [Use live captions in a teams meeting](https://support.microsoft.com/office/4be2d304-f675-4b57-8347-cbd000a21260).

For details on how your organizers can create human-generated captions, see [Use CART captions in a Microsoft Teams meeting](https://support.microsoft.com/office/2dd889e8-32a8-4582-98b8-6c96cf14eb47).

## Live transcription

Transcription is both a per-organizer and per-user policy setting. For meetings and events to include transcripts, the organizer must have this setting turned on. The user who starts the recording or transcript must also have this setting turned on.

When live transcription is turned on, users have a real-time written copy of the meeting's conversation. After the meeting, users can find the searchable transcription stored with the meeting recording. If transcription was turned on for the recording, Stream plays the video with the transcript next to the recording, and shows who is speaking and when as the video plays.

If recording is turned on, but transcription is turned off, the recording doesn't have a transcript file stored next to it. Also, when viewing the recording playback in Stream, captions can't be turned on.

The transcription link remains for the lifetime of the file in most cases, but can be broken if the video file is copied within the same OneDrive or SharePoint site. This action would result in captions not displaying on the copied video file.

Note

English (US), English (Canada), English (India), English (UK), English (Australia), English (New Zealand), Arabic (Saudi Arabia), Arabic (United Arab Emirates), Albanian (Albania), Bulgarian (Bulgaria), Catalan (Catalan), Chinese (Simplified, China), Chinese (Traditional, Hong Kong SAR), Chinese (Traditional, Taiwan), Croatian (Croatia), Czech (Czechia), Danish (Denmark), Dutch (Belgium), Dutch (Netherlands), Estonian (Estonia), Filipino (Philippines), Finnish (Finland), French (Canada), French (France), German (Germany), German (Switzerland), Greek (Greece), Hebrew (Israel), Hindi (India), Hungarian (Hungary), Icelandic (Iceland), Indonesian (Indonesia), Italian (Italy), Japanese (Japan), Kazakh (Kazakhstan), Korean (Korea), Latvian (Latvia), Lithuanian (Lithuania), Malay (Malaysia), Maltese (Malta), Norwegian (Norway), Polish (Poland), Portuguese (Brazil), Portuguese (Portugal), Romanian (Romania), Russian (Russia), Serbian (Cyrillic, Serbia), Slovak (Slovakia), Slovenian (Slovenia), Spanish (Mexico), Spanish (Spain), Swedish (Sweden), Thai (Thailand), Turkish (Turkey), Ukrainian (Ukraine), Vietnamese (Vietnam), Welsh (United Kingdom).

### Meetings

You can use the Teams admin center or PowerShell to manage transcription for meetings.

To allow or prevent meeting transcription by using the Teams admin center, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy that you want to edit or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the **Global policy**. To exclude certain users from the global policy, create and assign a custom meeting policy.
3. Toggle **Transcription** **On** or **Off**. This setting is **On** by default for new policies.
4. Select **Save**.
5. To assign the policy:
    - **To specific users**: Select your policy &gt; select **Manage users** &gt; **Assign users** &gt; enter in the search bar the names of specific users and select **Add** &gt; select **Apply**.
    - **To groups**: Select **Group policy assignment** &gt; select **Add** &gt; enter the group's name and enter the policy's name &gt; select **Apply**.

To manage meeting transcription using PowerShell, use the **`-AllowTranscription`** parameter in [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy). For details, see the PowerShell section later in this article.

### Events

You can use the Teams admin center or PowerShell to manage transcription for:

- Events up to 1,000 attendees
- Events optimized for large audiences

#### Events up to 1,000 attendees

For events with up to 1,000 attendees, such as webinars, this policy controls whether users can start transcription when attending these events and whether transcription can be enabled for the events they organize.

To allow or prevent transcription for events with up to 1,000 attendees by using the Teams admin center, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select the policy that you want to edit or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the **Global policy**. To exclude certain users from the global policy, create and assign a custom events policy.
3. Turn the **Transcription for webinar** toggle **On** or **Off**. This setting is **On** by default.
4. Select **Save**.
5. To assign the policy:
    - **To specific users**: Select your policy &gt; select **Manage users** &gt; **Assign users** &gt; enter in the search bar the names of specific users and select **Add** &gt; select **Apply**.
    - **To groups**: Select **Group policy assignment** &gt; select **Add** &gt; enter the group's name and enter the policy's name &gt; select **Apply**.

To manage transcription for events with up to 1,000 attendees by using PowerShell, use the **`-TranscriptionForWebinar`** parameter in [Set-CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy). For more information, see the PowerShell section later in this article. The default value for the **`-TranscriptionForWebinar`** parameter is *Enabled*.

#### Events optimized for large audiences

For events [optimized for large audiences](plan-events), such as town halls, this policy controls whether users can start transcription when attending these events and whether transcription can be enabled for the events they organize.

To allow or prevent transcription for events optimized for large audiences by using the Teams admin center, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select the policy that you want to edit or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the Global policy. To exclude certain users from the global policy, create and assign a custom events policy.
3. Turn the **Transcription for town hall** toggle **On** or **Off**. This setting is **On** by default.
4. Select **Save**.
5. To assign the policy:
    - **To specific users**: Select your policy &gt; select **Manage users** &gt; **Assign users** &gt; enter in the search bar the names of specific users and select **Add** &gt; select **Apply**.
    - **To groups**: Select **Group policy assignment** &gt; select **Add** &gt; enter the group's name and enter the policy's name &gt; select **Apply**.

To manage transcription for events optimized for large audiences by using PowerShell, use the **`-TranscriptionForTownhall`** parameter in [Set-CsTeamsEventsPolicy](/en-us/powershell/module/teams/set-csteamseventspolicy). For more information, see the PowerShell section later in this article. The default value for the **`-TranscriptionForTownhall`** parameter is *Enabled*.

## Live translated transcription (Teams Premium)

By default, transcripts are shown in the language spoken during a meeting or event. Live translated transcription allows your users to translate the meeting or event transcript into the language they're most comfortable with. The meeting or event organizer must have a Teams Premium license for attendees to use live translated transcription.

To turn on **Live translated transcription**, **Transcription** must be set to '**On**' in the corresponding meeting policy in the Teams admin center. To turn off **Live translated transcription**, set **Transcription** to **Off**.

## Platform support for live translated transcription

To view the list of platforms that support live translated transcription, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-intelligent-meetings).

## Live captions

Teams can detect what was said in a meeting or event and present real-time captions along with speaker attribution.

This setting is a per-user policy and applies during a meeting. This setting controls whether the **Turn on live captions** option is available for the user to turn automatically generated live captions on or off in meetings that the user attends. These captions aren't saved alongside the video file.

[![This screenshot shows the menu initiated by selecting the ellipses icon. The option to Turn on live captions is highlighted.](media/meeting-policies-live-captions.png)](media/meeting-policies-live-captions.png#lightbox)

| Teams admin center policy option | Parameter value in PowerShell | Behavior |
| --- | --- | --- |
| Not enabled, but users can enable | DisabledUserOverride | **This value is the default setting.** Live captions are off by default, but users with this assigned policy can turn on live captions during meetings or events. |
| Off | Disabled | Users with this assigned policy can't use live captions in meetings or events. |

### Use the Teams admin center to manage live captions

To allow or prevent live captions in meetings, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy that you want to edit or create a new one. To apply changes to all users in your organization who don't have an existing policy assignment, use the **Global policy**. To exclude certain users from the global policy, create and assign a custom meeting policy.
3. From the drop-down for **Live captions**, select **Not enabled, but users can enable**(default value) or **Off**.
4. Select **Save**.
5. To assign the policy:
    - **To specific users**: Select your policy &gt; select **Manage users** &gt; **Assign users** &gt; enter in the search bar the names of specific users and select **Add** &gt; select **Apply**.
    - **To groups**: Select **Group policy assignment** &gt; select **Add** &gt; enter the group's name and enter the policy's name &gt; select **Apply**.

To manage live captions using PowerShell, use the **`-LiveCaptionsEnabledType`** parameter in [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/teams/set-csteamsmeetingpolicy). For details, see the PowerShell section later in this article.

## Live translated captions (Teams Premium)

Live translated captions allow your users to see captions translated into the language they’re most comfortable with. By default, live captions are displayed in the language spoken during a meeting or event. For events optimized for large audiences, such as town halls, organizers can preselect up to ten languages for attendees to use during the event without Teams Premium. The meeting or event organizer must have a Teams Premium license for attendees to use live translated captions.

To turn on live translated captions, you must set **Live captions** to **Not enabled, but users can enable** in the corresponding meeting policy in the Teams admin center. To turn off live translated captions, set **Live captions** to **Off**.

### Platform support for live translated captions

To view the list of platforms that support live translated captions, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience#platform-support-for-intelligent-meetings).

## Manage whether organizers can prevent participants from copying or forwarding meeting chat messages, live captions, and transcripts

As an admin, you can choose whether organizers in your organization can restrict participants from copying or forwarding meeting chat messages, live captions, transcripts, and AI-generated insights in the meeting recaps. This setting also restricts forwarding and sharing messages to Outlook. By default, this per-organizer setting is set **On**. To learn more, see [Manage chat for sensitive Teams meetings](manage-chat-sensitive-meetings).

Note that preventing participants from copying or forwarding chat messages isn't applicable to the chat available to everyone in an event optimized for a large audience.

## Check user's transcription permissions

You can run the Teams transcripts diagnostic tool in the Microsoft 365 admin center to verify if a user’s account meets the requirements to transcribe a Teams meeting.

Note

Diagnostics in the Microsoft 365 admin center aren't available for Microsoft 365 Government, Microsoft 365 operated by 21Vianet, or Microsoft 365 Germany.

To run the diagnostic tool for transcripts, follow these steps:

1. Select the **Run Tests** button to populate the diagnostic in the Microsoft 365 admin center:
2. In the **Username or Email** field, enter the email address of the affected user.
3. In the **Teams Meeting URL** field, enter the meeting URL.
4. Select **Run Tests**.
5. After the diagnostic runs, select the provided links to resolve the issues that were found.

## Manage whether transcripts automatically expire

To manage whether transcripts automatically expire, see [Manage Teams recording policies for meetings and events](manage-teams-recording-expiration-policy).

## PowerShell

For details on assigning policies to users and groups by using PowerShell, see [Assign policies to users and groups](assign-policies-users-and-groups).

### Manage transcription in PowerShell

You can use PowerShell to manage transcription for meetings and events in your organization.

#### Transcription for meetings

To allow everyone in your organization to transcribe meetings, events, and group calls, except users with an assigned custom meeting policy, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $true
```

To allow specific users in your organization to transcribe, run the following commands:

1. Create a new policy:

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity "Your Policy Name" -AllowTranscription $true
    ```
2. Assign specific users the policy:

    ```powershell
    Grant-CsTeamsMeetingPolicy -Identity "user@contoso.onmicrosoft.com" -PolicyName "Your Policy Name"
    ```

To allow specific groups in your organization to transcribe, run the following commands:

1. Create a new policy:

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity "Your Policy Name" -AllowTranscription $true
    ```
2. Assign specific groups the policy:

    ```powershell
    Grant-CsTeamsMeetingPolicy -Group "Group ID" -PolicyName "Your Policy Name"
    ```

#### Transcription for events with up to 1,000 attendees

To allow users with this policy to transcribe events with up to 1,000 attendees, such as webinars, run the following command. When these users organize these events, the events can be transcribed.

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -TranscriptionForWebinar $true
```

To prevent users with this policy from transcribing events with up to 1,000 attendees, run the following command. When these users organize these events, the events can't be transcribed.

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -TranscriptionForWebinar $false
```

#### Transcription for events optimized for large audiences

To allow users with this policy to transcribe events optimized for large audiences, such as town halls, run the following command. When these users organize these events, the events can be transcribed.

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -TranscriptionForTownhall $true
```

To prevent users with this policy from transcribing events optimized for large audiences, run the following command. When these users organize these events, the events can't be transcribed.

```PowerShell
Set-CsTeamsEventsPolicy -Identity <policy name> -TranscriptionForTownhall $false
```

### Manage live captions in PowerShell

To turn off live captions for users with this policy, run the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -LiveCaptionsEnabledType Disabled
```

To turn on live captions for users with this policy, run the following script:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -LiveCaptionsEnabledType DisabledUserOverride 
```