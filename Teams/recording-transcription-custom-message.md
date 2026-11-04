---
layout: Conceptual
title: Custom in-meeting notification for recording and transcription - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/recording-transcription-custom-message
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Instruction on how IT admin can customize the recording and transcription banner/notification/message
author: ShuhanDong0903
manager: yujin1
ms.author: shuhandong
ms.service: msteams
ms.topic: article
ms.date: 2025-12-01T00:00:00.0000000Z
ms.subservice: meetings
locale: en-us
document_id: 97f6eed3-1974-1eef-b736-bb11eb16046c
document_version_independent_id: 97f6eed3-1974-1eef-b736-bb11eb16046c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/recording-transcription-custom-message.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: recording-transcription-custom-message
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/recording-transcription-custom-message.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1fddd731-86ce-afbc-c4ee-2dd6fa705dc6
---

# Custom in-meeting notification for recording and transcription - Microsoft Teams | Microsoft Learn

## Overview

IT admins can customize the **Recording and Transcription message** and the **URL of the privacy policy** used to notify implicitly or gain explicit consent from meeting participants for the use of recording and transcription during the meeting:

**Notification Banner (Implicit or [Explicit Consent](participant-agreement-recording-transcription)):** When recording or transcription starts, Teams displays a notification banner composed of four elements. Only the following are customizable:

- **Consent message (#3):** Supports plain text and HTML &lt;a&gt; tags for adding multiple custom links.
- **Resource (Privacy policy) URL (#4):** Only the URL can be changed. The display text "Privacy policy" is fixed and cannot be modified.

    [![Diagram of the in-meeting notification combination that shows which parts are customizable.](media/recording-transcription-custom-message/notification-combination.png)](media/recording-transcription-custom-message/notification-combination.png#lightbox)

**Notification Dialog ([Explicit Consent](participant-agreement-recording-transcription) only):** For meetings that require explicit consent, Teams displays a consent dialog when a user unmutes/turns on the camera. Due to its instructional nature, customization is limited to:

- **Customizable consent message (#3):** Only supports plain text, HTML &lt;a&gt; tag is not supported.
- **Resource (Privacy policy) URL (#4):** Only the URL can be changed. The display text "Privacy policy" is fixed and cannot be modified.

[![Diagram of the consent dialog combination that shows which parts are customizable.](media/recording-transcription-custom-message/dialog-combination.png)](media/recording-transcription-custom-message/dialog-combination.png#lightbox)

Note

About how to customize the **Resource (privacy policy)**, refer to [Set a custom privacy policy URL](meeting-recording#set-a-custom-privacy-policy-url).

## How to customize

To customize the consent message, follow the steps:

1. Go to the [Teams admin center](https://admin.teams.microsoft.com/). Navigate to **Meetings → Meeting policies**. Select or create a meeting policy where you want to enable custom messages.
2. In the **Recording & transcription** section, find the new setting: **Show customized in-meeting notification for recording and transcription**. Use the toggle to enable or disable custom messages for this policy.

    [![Screenshot that shows the Meeting policy setting in the Teams admin center for customizing recording and transcription messages.](media/recording-transcription-custom-message/admin-meeting-policy.png)](media/recording-transcription-custom-message/admin-meeting-policy.png#lightbox)
3. Click the **Customize notification** button to set your custom message.
4. Download the CSV template from the customization panel.
5. Open the downloaded template, and fill in your custom messages for each scenario and language as needed. (Refer here to learn more about how to fill the template.)
6. Upload the completed CSV using the **Select a file** button.
7. Use the **Preview** button to see how your changes appear.
8. Save the changes. 

    [![Screenshot that shows the Customize notification panel in the Teams admin center where admins can edit custom recording and transcription messages.](media/recording-transcription-custom-message/admin-panel.png)](media/recording-transcription-custom-message/admin-panel.png#lightbox)

## How to fill the CSV template

Warning

In some **non-English system languages** (for example, German, French, Spanish, Italian, Portuguese, and other European locales), Excel uses a different default CSV delimiter based on regional settings.

To avoid formatting issues, admins using these system languages should edit the CSV template using another **plain text editor**. Please **do not edit or re-save the CSV file using Excel**.

The template includes:

- **First column:** Supported languages (refer here to see all the supported languages).
- **First row:** Notification scenarios you can customize.

    - **initiator\_implicit:** For users who start recording or transcription in an implicit consent meeting.
    - **participant\_implicit:** For users who join an implicit consent meeting where another participant started recording or transcription.
    - **initiator\_explicit:** For users who start recording or transcription in an [explicit consent](participant-agreement-recording-transcription) meeting.
    - **participant\_explicit\_requested:** For users who join an explicit consent meeting where recording or transcription started by others and have **not yet provided consent**.
    - **participant\_explicit\_provided:** For users who join an explicit consent meeting where recording or transcription started by others and have **already provided consent**.
    - **agreement\_dialogue:** The consent dialog is shown in explicit consent meetings when a user unmutes/turns on the camera.

The message you set appears in the notification for the corresponding scenarios, along with fixed information (such as the initiator’s name and privacy policy) that is always included.

For more details, you can preview your changes by clicking the **Preview** button before uploading the CSV. 

Note

If you don’t want to display any message (excluding the fixed information), you can insert `<empty>` for the specific language or scenario. In this case, the notification shows only the fixed information.

Note

Custom messages **can't exceed 200 characters**; longer messages aren't permitted. 

## How It Works in Teams

Once the custom message is enabled for a meeting policy, all users assigned to that policy see the custom notifications in meetings they organize. All participants in those meetings follow the organizer’s custom message settings.

The message displayed depends on the scenario and the participant’s client language. If there's no custom message for a specific language or scenario, the user sees the default message in Teams.

Note

Custom messages are supported on **Teams Windows**, **macOS**, and **Web** clients. **iOS** and **Android** currently support plain text only, with full message customizability coming soon.

Custom messages are **not supported in 1:1 calls**.

#### Example case 1: Implicit consent

1. **Edit .csv template:** Admins can add custom strings for each implicit scenario and language.

    [![Screenshot that shows the CSV template for implicit consent scenarios with columns for language and notification scenarios.](media/recording-transcription-custom-message/implicit-case-template.png)](media/recording-transcription-custom-message/implicit-case-template.png#lightbox)
2. **Preview:** Once uploaded, the policy preview displays customized strings, with differences highlighted compared to the system defaults.

    [![Screenshot that shows the preview dialog highlighting customized strings compared to system defaults.](media/recording-transcription-custom-message/implicit-case-preview.png)](media/recording-transcription-custom-message/implicit-case-preview.png#lightbox)
3. **Enabled:** Customized strings are visible to meeting participants when the recording or transcription is turned on.

    [![Screenshot that shows the final in-meeting behavior displaying the customized implicit consent message to participants.](media/recording-transcription-custom-message/implicit-case-final.jpg)](media/recording-transcription-custom-message/implicit-case-final.jpg#lightbox)

#### Example case 2: Explicit consent

1. **Turn on explicit consent:** With this on, users see the "explicit consent scenario" notifications.

    [![Screenshot that shows the Meeting policy setting that enables explicit consent for recording and transcription.](media/recording-transcription-custom-message/explicit-case-setting.png)](media/recording-transcription-custom-message/explicit-case-setting.png#lightbox)
2. **Edit .csv template:** Admins can locate the scenario key of the explicit scenarios and add custom strings as needed.

    [![Screenshot that shows the CSV template for explicit consent scenarios with scenario keys and language columns.](media/recording-transcription-custom-message/explicit-case-template.png)](media/recording-transcription-custom-message/explicit-case-template.png#lightbox)
3. **Preview:** Once uploaded, the policy preview displays customized strings, with differences highlighted compared to the system defaults.

    [![Screenshot that shows the preview dialog for explicit consent scenarios highlighting differences from defaults.](media/recording-transcription-custom-message/explicit-case-preview.png)](media/recording-transcription-custom-message/explicit-case-preview.png#lightbox)
4. **Enabled:** Customized strings are visible to meeting participants when the recording or transcription is turned on.

    [![Screenshot that shows the final in-meeting behavior displaying the customized explicit consent notification to participants.](media/recording-transcription-custom-message/explicit-case-final.jpg)](media/recording-transcription-custom-message/explicit-case-final.jpg#lightbox)

#### Example case 3: Multiple languages and scenarios

- User A with an implicit policy has custom messages set to:

| Scenarios | initiator\_implicit | participant\_implicit | initiator\_explicit | participant\_explicit\_requested | participant\_explicit\_provided | agreement\_dialogue |
| --- | --- | --- | --- | --- | --- | --- |
| English (United States) | [1] Let everyone know they're being included. | [2] By attending this meeting, you agree to be included. | [3] Started by you. We've asked everyone if they'll agree to be included. |  |  | [4] Do you agree to allow your content to be processed for features? |
| Chinese (Simplified, China) |  | [5] 参加此会议即表示你同意被包含在内。 |  | [6] 你必须同意被包含在内。若要继续，请取消静音、打开摄像头或共享屏幕。 |  |  |

- User A and B have Teams language set to English (United States), User C uses Chinese (Simplified, China), and User D uses Spanish (Spain).
- User A creates a meeting and invites participants B, C, and D.
- User A starts recording in the meeting.

    - **User A**: sees "[1] Let everyone know they're being included."
    - **User** **B**: sees "[2] By attending this meeting, you agree to be included."
    - **User C**: sees "[5] 参加此会议即表示你同意被包含在内。"
    - **User D**: sees the default notification text because no custom message was added for `participant_implicit` in **Spanish (Spain)**.

## Supported Languages and Codes

| Language name | Code |
| --- | --- |
| Afrikaans (South Africa) | af-ZA |
| Arabic (Saudi Arabia) | ar-SA |
| Azerbaijani (Latin, Azerbaijan) | az-Latn-AZ |
| Bulgarian (Bulgaria) | bg-BG |
| Bosnian (Latin) (Bosnia and Herzegovina) | bs-Latn-BA |
| Catalan (Spain) | ca-ES |
| Valencian (Spain) | ca-Es-VALENCIA |
| Czech (Czech Republic) | cs-CZ |
| Welsh (United Kingdom) | cy-GB |
| Danish (Denmark) | da-DK |
| German (Germany) | de-DE |
| Greek (Greece) | el-GR |
| English (United Kingdom) | en-GB |
| English (United States) | en-US |
| Spanish (Spain) | es-ES |
| Spanish (Mexico) | es-MX |
| Estonian (Estonia) | et-EE |
| Basque (Spain) | eu-ES |
| Persian (Iran) | fa-IR |
| Finnish (Finland) | fi-FI |
| Filipino (Philippines) | fil-PH |
| French (Canada) | fr-CA |
| French (France) | fr-FR |
| Galician (Spain) | gl-ES |
| Hebrew (Israel) | he-IL |
| Hindi (India) | hi-IN |
| Croatian (Croatia) | hr-HR |
| Hungarian (Hungary) | hu-HU |
| Indonesian (Indonesia) | id-ID |
| Icelandic (Iceland) | is-IS |
| Italian (Italy) | it-IT |
| Japanese (Japan) | ja-JP |
| Georgian (Georgia) | ka-GE |
| Kazakh (Kazakhstan) | kk-KZ |
| Korean (Korea) | ko-KR |
| Lithuanian (Lithuania) | lt-LT |
| Latvian (Latvia) | lv-LV |
| Macedonian (North Macedonia) | mk-MK |
| Malay (Malaysia) | ms-MY |
| Maltese (Malta) | mt-MT |
| Norwegian Bokmål (Norway) | nb-NO |
| Dutch (Netherlands) | nl-NL |
| Norwegian Nynorsk (Norway) | nn-NO |
| Polish (Poland) | pl-PL |
| Portuguese (Brazil) | pt-BR |
| Portuguese (Portugal) | pt-PT |
| Romanian (Romania) | ro-RO |
| Russian (Russia) | ru-RU |
| Slovak (Slovakia) | sk-SK |
| Slovenian (Slovenia) | sl-SI |
| Albanian (Albania) | sq-AL |
| Serbian (Cyrillic, Serbia) | sr-Cyrl-RS |
| Serbian (Latin, Serbia) | sr-Latn-RS |
| Swedish (Sweden) | sv-SE |
| Thai (Thailand) | th-TH |
| Turkish (Turkey) | tr-TR |
| Ukrainian (Ukraine) | uk-UA |
| Vietnamese (Vietnam) | vi-VN |
| Chinese (Simplified, China) | zh-CN |
| Chinese (Traditional, Taiwan) | zh-TW |