---
layout: Conceptual
title: Configure calling policies in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-calling-policy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-calling
ms.reviewer: jastark
ms.date: 2026-03-15T00:00:00.0000000Z
audience: admin
search.appverid: MET150
description: Learn how to create, modify, and add users to custom calling policies in Microsoft Teams, and discover various calling policy settings.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
- ContentFreshnessFY24
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
locale: en-us
document_id: 410fc30b-f530-8443-0602-9150c9cba115
document_version_independent_id: c5b33b25-147b-f7d4-056a-987088950e7c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-calling-policy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-calling-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-calling-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 47054cb5-cb2b-aa01-efb1-4b3ffcbd54af
---

# Configure calling policies in Microsoft Teams - Microsoft Teams | Microsoft Learn

In Microsoft Teams, calling policies control which calling and call forwarding features are available to users. Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.

You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.

## Create a custom calling policy

Follow these steps to create a custom calling policy.

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Calling policies**.
2. Select **Add**.
3. Turn on or turn off the features that you want to use in your calling policy.
    - For example, to control voicemail for inbound calls, select **On** or **Let users decide** to enable routing of calls to voicemail. To prevent routing to voicemail, select **Off**.
4. Select **Save**.

## Edit a calling policy

Follow these steps to edit an existing calling policy.

1. In the left navigation of the Microsoft Teams admin center, select **Voice** &gt; **Calling policies**.
2. Select the policy or policies that you want to modify, and then select **Edit**.
3. Make the changes that you want, and then select **Save**.

## Assign a custom calling policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

## Calling policy PowerShell cmdlets

To create, modify, retrieve, assign, and remove calling policies, use the following cmdlets:

- [New-CsTeamsCallingPolicy](/en-us/powershell/module/teams/new-csteamscallingpolicy)
- [Set-CsTeamsCallingPolicy](/en-us/powershell/module/teams/set-csteamscallingpolicy)
- [Get-CsTeamsCallingPolicy](/en-us/powershell/module/teams/get-csteamscallingpolicy)
- [Grant-CsTeamsCallingPolicy](/en-us/powershell/module/teams/grant-csteamscallingpolicy)
- [Remove-CsTeamsCallingPolicy](/en-us/powershell/module/teams/remove-csteamscallingpolicy)

## Calling policy settings

Here are the settings that you can configure for calling policies:

- **Make private calls** - This setting controls all calling capabilities in Teams. Turn this setting off to turn off all calling functionality in Teams.
- **[Cloud recording for calling](call-recording-transcription-captions)**
- **Require participant agreement for recording and transcription -** When this is on, participants must agree to be recorded and transcribed. Participants' audio, video, and content sharing are turned off until they agree to be included in the recording and transcript.
- **[Transcription](call-recording-transcription-captions)**
- **[Routing for PSTN calls](inbound-call-routing)**
- **[Routing for federated calls](inbound-call-routing)**
- **[Call forwarding and simultaneous ringing to people in your organization](user-call-settings)**
- **[Call forwarding and simultaneous ringing to external phone numbers](user-call-settings)**
- **[Voicemail for inbound calls](set-up-phone-system-voicemail)**
- **[Inbound calls can be routed to call groups](call-sharing-and-group-call-pickup)**
- **[Delegation for inbound and outbound calls](user-call-settings)**
- **[Prevent toll bypass and send calls through the PSTN](location-based-routing-enable)**
- **[Music on hold for calls](music-on-hold)**
- **[Busy on busy during calls](inbound-call-routing)**
- **Web PSTN calling** - This setting enables users to call PSTN numbers using the Teams web client. This setting is on by default.
- **[Real-time captions in Teams calls](call-recording-transcription-captions)**
- **Automatically answer incoming meeting invites** - This setting will answer the phone automatically when an inbound meeting invitation is sent to the user.
- **[Spam filtering](configure-call-spam-filtering)**
- **[SIP devices can be used for calls](sip-gateway-configure)**
- **[Open apps in browser for incoming PSTN calls](inbound-call-routing)**