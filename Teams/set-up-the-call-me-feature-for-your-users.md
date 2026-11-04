---
layout: Conceptual
title: Set up the Call me feature for your users - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-the-call-me-feature-for-your-users
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
ms.reviewer: oscarr
ms.date: 2026-10-06T00:00:00.0000000Z
manager: pamgreen
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: teams-audio-conferencing
audience: admin
search.appverid: MET150
description: Learn how to set up the Call me feature in Teams so that users can join the audio portion by phone when using their computer for audio might not be possible.
ms.localizationpriority: medium
ms.collection:
- Tier1
- m365initiative-meetings
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: b759f354-bf74-3cff-0c96-3b28a27ee997
document_version_independent_id: fb2d8a68-f35a-bbee-a306-72ee20a450a3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-the-call-me-feature-for-your-users.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-the-call-me-feature-for-your-users
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-the-call-me-feature-for-your-users.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 52f82522-72b3-2c51-2c66-8a73ba5f46e4
---

# Set up the Call me feature for your users - Microsoft Teams | Microsoft Learn

In Microsoft Teams, the **Call me** feature allows participants to join meeting audio through their phone, which is useful when they can't use computer audio. Participants listen to the meeting audio on their phone and watch the meeting content that others share through their computer.

Note

We are frequently updating how you can manage features, so the steps here might be a little different from what you see.

## Setting up the call me feature

Your users can use the **Call me** feature once you set up the following prerequisites:

- Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers). To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams).
- Meeting organizer can dial-out from meetings. To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams).

If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other participants can't receive a call to join them to the meeting. For participants with dial-out enabled, once they join the meeting, they can join others dialing their number from the **Show participants** icon.

## The user experience

### Join a meeting by using phone for audio

Select **Join** to join a meeting &gt; **Phone audio** on the **Choose your video and audio options** screen &gt; select **Join now**. From here, participants can join the meeting call or dial in manually to the meeting.

![Screen shot of the Phone audio option.](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

#### Use phone for audio

Users have two ways to join the meeting audio via phone.

##### 1. Receive a call

On the **Use phone for audio** screen, the user enters their phone number, and then selects the **Call me** button. The meeting calls the user to join the meeting.

![Screen shot of the Call me option on the Use phone for audio screen.](media/set-up-the-call-me-feature-for-your-users-call-me.png)

##### 2. Dial in manually

Another way to join is to dial in directly to the meeting. On the **Use phone for audio** screen, select **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.

![Screen shot of the Dial in manually option.](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### Receive a meeting callback for audio issues

If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio. Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.

Here's an example of the message and the **Call me back** option that Teams displays when no microphone is detected:

![Screen shot of the Call me back option.](media/set-up-the-call-me-feature-for-your-users-no-mic.png)

The user selects the **Call me back** button, which brings up the **Use phone for audio** screen. From here, they can enter their phone number and select **Call me back**, or select **Dial in manually**.