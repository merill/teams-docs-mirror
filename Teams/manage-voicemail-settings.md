---
layout: Conceptual
title: Manage Cloud Voicemail settings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-voicemail-settings
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
ms.date: 2026-03-15T00:00:00.0000000Z
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
description: Manage Voicemail settings for your users.
locale: en-us
document_id: 13b2de67-48a2-5348-1185-88b4dfa1793d
document_version_independent_id: 13b2de67-48a2-5348-1185-88b4dfa1793d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-voicemail-settings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-voicemail-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-voicemail-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8254471d-c9bb-156f-b6b9-5d084a02b7a8
---

# Manage Cloud Voicemail settings - Microsoft Teams | Microsoft Learn

Voicemail settings allow you to configure voicemail settings for individual users.

Before configuring voicemail settings for your users, you should read [Set up Cloud Voicemail](set-up-phone-system-voicemail). For information about setting policies for groups of users, see [Manage Voicemail policies](manage-voicemail-policies).

The default settings for Cloud Voicemail are:

- Voicemail is enabled.
- The prompt language is set to the user's preferred language.
- The out-of-office greeting isn't enabled.
- The out-of-office greeting, when automatic replies are set in Outlook, isn't enabled.
- The out-of-office greeting, when the calendar in Outlook shows out-of-office, isn't enabled.
- Sharing of voicemail and transcription data with the service for training and improving accuracy purposes isn't enabled.
- The call answering rule is set to Regular Voicemail.
- The default greeting prompt overwrite isn't set.
- The default out-of-office greeting prompt overwrite isn't set.
- The transfer target isn't set.
- Play out-of-office greetings isn't enabled.

To manage Cloud Voicemail features for your users, you can use the Teams admin center or PowerShell. Your end users can also configure these settings in the Teams client by going to **Settings -&gt; Calls -&gt; Manage Voicemail.**

## Use Teams admin center

In the Teams admin center:

1. In the left navigation, go to **Users &gt; Manage users** and select the user.
2. On the user details page, go to the **Voicemail** tab.
3. Change the settings.
4. Select **Save**.

## Use PowerShell

You can also use PowerShell to manage voicemail settings as follows:

- To manage Cloud Voicemail settings for individual users, use the [Set-CsOnlineVoicemailUserSettings](/en-us/powershell/module/teams/set-csonlinevoicemailusersettings) cmdlet.
- To view settings, use the [Get-CsOnlineVoicemailUserSettings](/en-us/powershell/module/teams/get-csonlinevoicemailusersettings) cmdlet.
- You can disable Cloud Voicemail for a user by using the [Set-CsOnlineVoicemailUserSettings](/en-us/powershell/module/teams/set-csonlinevoicemailusersettings) cmdlet and setting the `-VoicemailEnabled` parameter to `$false`.

## Voicemail settings

- **Voicemail** - This setting controls whether Cloud Voicemail is enabled for the user. If the setting is false, Cloud Voicemail service isn't available for the user, and a voicemail isn't recorded for the user.
- **Prompt language** - This setting specifies the language used for the prompts in the Cloud Voicemail. For more information, see [Change the default language for greetings and emails](change-the-default-language-for-greetings-and-emails).
- **Call answering mode**- This setting specifies the call answering rule. The rule can be:
    - *Caller can leave a voicemail* - The relevant greeting (normal or out-of-office) is played and the caller can leave a voicemail.
    - *Play an outgoing message to the caller* - Only the relevant greeting (normal or out-of-office) is played. The caller can't leave a voicemail.
    - *Service declines the call with no message* - The system disconnects the caller.
- **Call transfer** - This setting specifies the user or phone number that the caller is transferred to.
- **Default greeting prompt** - This setting specifies the text-to-speech greeting that plays if the user doesn't have a greeting recorded.
- **Default out-of-office prompt** - This setting specifies the text-to-speech greeting that plays if the user is out-of-office and doesn't have a recorded out-of-office greeting recorded.
- **Play out-of-office greetings** - This setting specifies whether or not to play the out-of-office greeting in a voicemail deposit scenario where a user has automatic replies set in Outlook.
- **Share data for service improvements** (PowerShell only) - This setting specifies whether voicemail and transcription data is shared with the service for training and improving accuracy. If set to false, voicemail data isn't shared, regardless of user choice.