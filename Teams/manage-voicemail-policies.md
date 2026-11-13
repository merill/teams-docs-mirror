---
layout: Conceptual
title: Manage Voicemail Policies - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-voicemail-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: vijurtse, colongma
ms.date: 2026-03-24T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Learn how to manage Cloud Voicemail policies for your users.
locale: en-us
document_id: 85634d87-7729-6449-9663-556097e75504
document_version_independent_id: b75446bd-07af-a7f2-d346-fe7634634548
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-voicemail-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-voicemail-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-voicemail-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8ee12725-1ab5-fc80-4f44-a17502f464ee
---

# Manage Voicemail Policies - Microsoft Teams | Microsoft Learn

Warning

For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.

Voicemail policies allow you to configure and assign existing or new voicemail policies to groups of users for features such as call answering rules, voicemail transcription, transcription profanity masking, transcription translation, voicemail pre-triage with AI and system prompt language.

Before specifying policies, you should read [Set up Cloud Voicemail](set-up-phone-system-voicemail). For information on managing settings for individual users, see [Manage Voicemail settings](manage-voicemail-settings).

To manage voicemail policies, you can use the Teams admin center or the New-CsOnlineVoicemailPolicy PowerShell cmdlet.

The default policies for users are:

- Voicemail transcription is enabled.
- Voicemail transcription translation is enabled.
- Voicemail transcription profanity masking isn't enabled.
- The maximum recording duration is set to five minutes.
- Editing call answering rules is enabled.
- Primary and secondary system prompt languages are set to null and the user's voicemail language setting is used.
- No pre- or postamble configured.
- Voicemails pre-triage with AI isn't enabled.

You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.

Important

The voicemail service in Microsoft 365 caches voicemail policies and updates the cache every 5 minutes. So, policy changes that you make can take up to 5 minutes to be applied.

## Use Teams admin center

Note

Managing Voicemail Policies through the Teams admin center isn't currently available in GCC High and DoD environments.

### Create a custom voicemail policy

Follow these steps to create a custom voicemail policy.

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** &gt; **Voicemail policies**.
2. Select **Add**.
3. Turn on or turn off the features that you want to use in your voicemail policy.
4. Select **Save**.

### Edit a voicemail policy

Follow these steps to edit an existing voicemail policy.

1. In the left navigation of the Microsoft Teams admin center, select **Voice** &gt; **Voicemail policies**.
2. Select next to the policy that you want to modify, and then select **Edit**.
3. Make the changes that you want, and then select **Save**.

Important

You can't edit or remove the pre-configured policy instances called TranscriptionDisabled and TranscriptionProfanityMaskingEnabled.

### Assign a custom voicemail policy to users

You can assign a policy directly to users, either individually or at scale through a batch assignment (if supported for the policy type), or to a group that the users are members of (if supported for the policy type).

To learn about the different ways that you can assign policies to users, see [Assign policies to your users in Teams](policy-assignment-overview).

## Use PowerShell

You can also use PowerShell to configure and assign existing or new voicemail policies. To manage policies by using PowerShell, use the following cmdlets:

- [New-CsOnlineVoicemailPolicy](/en-us/powershell/module/teams/new-csonlinevoicemailpolicy)
- [Set-CsOnlineVoicemailPolicy](/en-us/powershell/module/teams/set-csonlinevoicemailpolicy)
- [Get-CsOnlineVoicemailPolicy](/en-us/powershell/module/teams/get-csonlinevoicemailpolicy)
- [Grant-CsOnlineVoicemailPolicy](/en-us/powershell/module/teams/grant-csonlinevoicemailpolicy)
- [Remove-CsOnlineVoicemailPolicy](/en-us/powershell/module/teams/remove-csonlinevoicemailpolicy)

## Voicemail policy settings

- **Users can edit call answering rules** - This setting controls whether the user is allowed to configure voicemail call answering rules in Microsoft Teams.
- **Maximum recording duration** - The maximum recording length controls the maximum time a voicemail can be recorded. The default is 5 minutes.
- **Primary prompt language** and **Secondary prompt language** - By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail. If there is a business requirement to have the voicemail system prompts presented in two languages, a primary and secondary language can be set.
- **Voicemail transcription** - This setting controls whether the Cloud Voicemail service generates a text transcription of the recorded voicemail and include it in the voicemail message. The transcription is done based on the language detected in the recorded voicemail.
- **Translation for transcriptions** - This setting controls whether the Cloud Voicemail service translates the transcription of the recorded voicemail. The translation is attempted in the preferred language of the voicemail receiver.
- **Mask profanity in voicemail transcription** - This setting controls whether the Cloud Voicemail service masks profanity found in the transcription of the voicemail.
- **Users can share data for service improvement** - This setting is deprecated and no longer has any effect. Its value is ignored by the service and is retained only for backward compatibility. Historically it specified whether voicemail and transcription data was shared with the service for training and improving accuracy.
- **Play preamble audio file before voicemail greeting** - The audio file to play to the caller before the user's voicemail greeting is played.
- **Play postamble audio file after voicemail greeting** - The audio file to play to the caller after the user's voicemail greeting has played and before the caller is allowed to leave a voicemail message.
- **Disconnect the call if preamble or postamble audio can't be played** - Is playing the Pre- or Postamble mandatory before the caller can leave a message.

Important

The following configuration parameter is available through the Microsoft Frontier Program. General Availability for this functionality has not been determined at this time.

- **Personal voicemail AI triage** - Specifies whether AI-powered triage is enabled for personal voicemail. When enabled, personal voicemail messages for eligible users are enriched with AI-generated metadata from voicemail transcription, including a summary, suggested actions, a category, and an importance classification. This feature requires a Microsoft 365 Copilot license and a configured spending policy for usage-based billing.

Note

When transcription is turned off, the email users receive contains a message indicating that the audio quality wasn't good enough for transcription to take place.