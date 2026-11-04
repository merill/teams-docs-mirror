---
layout: Conceptual
title: Tenant Administration control for voice recognition (voice profile) in Teams Rooms - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/voice-recognition
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: parisataheri
ms.date: 2026-08-27T00:00:00.0000000Z
ms.update-cycle: 180-days
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
- magic-ai-copilot
search.appverid: MET150
ms.localizationpriority: medium
description: Learn about how admins can control for voice recognition (voice profile) in Teams meeting rooms.
locale: en-us
document_id: 9ec8f04d-0386-3141-ff03-0149589fe876
document_version_independent_id: 2dd04344-50a7-7214-fc5f-0f92eafcf8ac
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/voice-recognition.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/voice-recognition
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/voice-recognition.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/a8711e05-df51-442a-970f-935304535b39
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/3d3c20d8-79ed-4203-aee0-ffb9c9bafe72
platformId: f0cfe3b0-611e-d7de-a994-7a648be3e7ed
---

# Tenant Administration control for voice recognition (voice profile) in Teams Rooms - Microsoft Teams | Microsoft Learn

This article provides guidance on how admins can enable voice recognition and live transcription for meetings that are held. As an admin, you have the ability to adjust the extent to which your organization lets users utilize voice recognition and Intelligent Speakers capabilities.

Intelligent Speaker is available in all countries and regions. See Supported transcription languages for a list of the locales currently supported for biometric enrollment and in-meeting transcription.

Note

- **Teams Rooms:** Intelligent Speakers are available to customers with Teams Room Pro licenses. (Select devices under legacy Microsoft Teams Rooms Premium licenses continue to be supported.)​​
- **BYOD Rooms:** Intelligent Speakers available in rooms where the room host has either a Microsoft Teams Premium or Copilot license.

## What is Intelligent Speaker recognition?

When using Intelligent Speaker for Microsoft Teams Rooms, the meeting transcript is able to not only distinguish between different speakers in the room, but also identify them and attribute them to the correct person. Intelligent Speaker enables critical use cases for Copilot and intelligent recap.

Speaker recognition is enabled by intelligent speakers certified for Teams. Certified intelligent speakers are designed with multiple microphones to provide high-quality audio, maximize accuracy in recognition and transcription, and boast an industry-leading reduction of what is referred to as 'word error rate'.

Originally, Intelligent Speaker required unique hardware, we've since expanded to support all Teams Rooms devices. While we're delighted to extend the capability of speaker recognition to more rooms, it's important to note the quality may not match that of an intelligent speaker certified device. So, it's essential to evaluate the advantages of incorporating a certified intelligent speaker, especially in crucial spaces where attaining the highest quality transcription and attribution is vital.

## Maintain your identity in meetings optimized for Copilot and meeting recap

The most essential input for Copilot in Teams is the identity of each speaker. Copilot needs a meeting transcript, with attribution for every speaker, to deliver meeting summaries, insights, and action items. In a hybrid meeting, without speaker recognition, the video, and audio feed for people in the room would be attributed to the space (for example, Conference Room 1), not the individuals speaking, making it difficult to query individuals’ contributions, summarize everyone’s perspectives, and tackle those to-do items.

Teams Rooms and BYOD Rooms use advanced technology called speaker recognition to analyze the distinct vocal characteristics of each speaker, such as pitch, tone, and speaking style, to create a voiceprint for each participant, akin to a fingerprint for their voice.

With speaker recognition, speakers can be identified during live transcription in shared meeting rooms, ensuring clear and precise voice capture for every participant. This allows you to effortlessly track who said what during the meeting through intelligent meeting recap and Copilot.

To enable speaker recognition for your employees, you can set up a voice profile in seconds using the Teams Desktop app. Each person gets a unique voice signature, stored securely in your organization's tenant in the Microsoft Cloud to assure that every contribution is accurately captured in every meeting, enabling Copilot and intelligent meeting recap – and helping you drive your work forward.

[![Screenshot showing a meeting in progress.](media/voice-recognition/image.png)](media/voice-recognition/image.png#lightbox)

## Step 1: Confirm requirements for Intelligent Speaker recognition

#### Teams Rooms:

- Teams Rooms on Windows or Teams Rooms on Android
- Teams Room resource account with a Teams Room Pro license assigned.
- To ensure best precision for the transcript, we suggest limiting the number of in person attendees to 10 people although additional participants are supported.
- People to be identified in the room, need to be enrolled with their voice profile and be invited to the scheduled meeting.
- The limitation for people invited with a voice profile is 50 invitees (regardless of the quantity of participants in the room).
- To support high-quality audio and video during meetings, we recommend that the meeting room has an [upload speed of 10 Mbps](/en-us/microsoftteams/devices/qos-on-teams-devices#how-much-bandwidth-does-a-microsoft-teams-rooms-device-use).

#### BYOD Rooms:

- Teams Desktop Client on Windows or macOS.
- Room hosts should have either Teams Premium or Copilot license. The room host is the person who connects their laptop to the Intelligent Speaker.
- To ensure best precision for the transcript, we suggest limiting the number of in person attendees to a maximum of 10 people.
- Users can use any speaker microphone in a room and can connect it through USB to their laptops.
- Users need to make sure that their Teams client is updated.
- The current limitation for people invited with voice profile is currently 50.
- Intelligent Speakers available in rooms where the room host has either a Microsoft Teams Premium or Copilot license.

## Additional requirements for either room type:

- Identification features are supported only when the meeting organizer’s mailbox is in Exchange Online. They aren't supported for on-premises Exchange or third-party calendars (for example, Google Calendar).
- Hybrid deployments are supported only if Teams can access the organizer’s calendar in the cloud. BYOD scenarios aren't supported for identification features.

## Step 2: Enable Intelligent Speaker recognition

**End users** must have their voice profile enrolled to be identified in a meeting space. See [enable voice and face enrollment](/en-us/microsoftteams/rooms/voice-and-face-recognition) for guidance on enabling end user enrollment.

**Teams Rooms** devices must be configured to utilize an end users biometric profile to identify who is speaking. See [enable people recognition on Teams Rooms](/en-us/MicrosoftTeams/rooms/teams-rooms-people-recognition) for guidance on enabling Teams Rooms to identify speakers.

Speaker attribution using the meeting invite list begins when someone other than a Teams Room device joins the meeting.

Identification requires transcription to be enabled.

For a **BYOD meeting space**, the `CsTeamsAIPolicy` must be configured to allow identification of speakers within that space. See [Set-CsTeamsAIPolicy](/en-us/powershell/module/microsoftteams/set-csteamsaipolicy) for specific enablement guidance.

```powershell
Set-CsTeamsAiPolicy -Identity Global -SpeakerAttributionForBYOD Enabled
```

| Policy | Description | Values and Behavior |
| --- | --- | --- |
| roomAttributeUserOverride | Control the voice-based user identification in meeting rooms. This setting is required for Rooms accounts, and BYOD user accounts. | **Off**<br>- The Room device won't send audio stream-saving bandwidth from the room.<br>- Meeting room users won't be attributed or distinguished, and their voice signatures won't be retrieved or used at all.<br>- Meeting room users are unknown.<br><br>**Attribute**<br>- Rooms users will be attributed based on their enrollment status.<br>- Users who are enrolled are shown with their name in the transcription.<br>- Users who aren't enrolled show as Speaker.<br><br>**Distinguish**<br>- Rooms users will be distinguished and separated as speaker 1, speaker 2, ....speaker in the transcription.<br>- Irrespective of enrollment status of the user, their name won't show in the transcription. |

Note

After a policy is assigned, it can take up to 48 hours to take effect. To get the policy to take effect sooner, accounts must be signed out and signed back in.

### Supported transcription languages

Once an end-user enrolls, their voice can be recognized during meetings and identified in the transcription when the meeting is set to one of the following languages:

English (US), English (Canada), English (India), English (UK), English (Australia), English (New Zealand), Arabic (Arab Emirates), Arabic (Saudi Arabia), Chinese (Simplified China), Chinese (Traditional, Hong Kong SAR), Chinese (Traditional, Taiwan), Czech (Czechia), Danish (Denmark), Dutch (Belgium), Dutch (Netherlands), French (Canada), French (France), Finnish (Finland), German (Germany), Greek (Greece), Hebrew (Israel), Hindi (India), Hungarian (Hungary), Italian (Italy), Japanese (Japan), Korean (Korea), Norwegian (Norway), Polish (Poland), Portuguese (Brazil), Portuguese (Portugal), Romanian (Romania), Russian (Russia), Slovak (Slovakia), Spanish (Mexico), Spanish (Spain), Swedish (Sweden), Thai (Thailand), Turkish (Türkiye), Ukrainian (Ukraine), Vietnamese (Vietnam), Welsh (United Kingdom)

## Frequently asked questions (FAQ)

Please review the [face and voice enrollment](/en-us/microsoftteams/rooms/voice-and-face-recognition) document if you have more questions regarding voice profile data usage and storage