---
layout: Conceptual
title: Manage custom dictionaries for Microsoft Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/copilot-custom-dictionary
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: fezuo
author: wlibebe
ms.reviewer: fei.zuo
manager: pamgreen
ms.date: 2026-04-16T00:00:00.0000000Z
ms.update-cycle: 180-days
audience: Admin
ms.topic: how-to
ms.subservice: meetings
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- m365initiative-meetings
- m365copilot
- magic-ai-copilot
description: Learn about how to upload and manage a Copilot custom dictionary for Microsoft Teams meetings and events to enhance the quality of transcripts.
locale: en-us
document_id: e630ff93-262e-7c86-a2eb-e935149c7c71
document_version_independent_id: e630ff93-262e-7c86-a2eb-e935149c7c71
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/copilot-custom-dictionary.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: copilot-custom-dictionary
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/copilot-custom-dictionary.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
platformId: 9d0ab103-ef7e-a200-1e68-f5575ab73342
---

# Manage custom dictionaries for Microsoft Teams meetings and events - Microsoft Teams | Microsoft Learn

![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Events

## Overview

Organizations often use their own special terms, acronyms, and jargon, like product names, department-specific language, and industry-specific terms. The AI models powering Teams transcription are trained using general datasets that might not recognize these specialized terms. When you import a custom dictionary, the model dynamically adapts during meetings and performs post-correction once the meeting ends, ensuring accurate transcription of these specialized terms.

As an admin, you can upload a custom dictionary in the Microsoft 365 admin center to enhance entity recognition and improve transcription accuracy across Teams meetings and events.

## Prerequisites

### Admin

You must meet the following requirements to upload and manage custom dictionaries:

- You must have the AI administrator role. To learn more about admin roles, see [About admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles).

### Your users

Users in your organization must meet the following requirements to use custom dictionaries:

- An eligible *Microsoft 365*base license.
    - For the list of eligible base licenses, see [Understand licensing requirements for Microsoft Copilot](/en-us/microsoft-365/copilot/microsoft-365-copilot-licensing).
- An eligible *Microsoft Teams*license.
    - Teams licenses might be included in your *Microsoft 365* subscription, or you might need to purchase a separate Teams license if you have *Microsoft 365 (no Teams)* licenses.
- A *Microsoft Copilot*license.
    - For information on how to acquire *Microsoft Copilot* licenses, see [Where can I get Microsoft Copilot?](https://support.microsoft.com/topic/where-can-i-get-microsoft-copilot-40a622db-6d25-4266-b008-4bbcb55cf52f).

## Understand custom dictionaries

The custom dictionary captures organization-specific terminology to improve transcript accuracy and help the AI model better recognize and understand key entities. You upload and manage custom dictionaries manually at the tenant level. This feature doesn't currently support group or user specific dictionaries. Its purpose is to give you a centralized way to maintain terminology for your organization. All meetings and events created by your users in your organization with a Microsoft Copilot license automatically benefit from these terms when used, without any negative impact if they aren't.

Important

The custom dictionary enhances transcription for meetings organized or initiated by users with a Microsoft Copilot license.

### Who can update custom dictionaries?

As an admin, you're the only one who can create and update the custom dictionary with new terms from your organization. Uploading a new dictionary replaces the existing one in the same language. Your users can't add terms to the dictionary; they must ask you to upload an updated dictionary with new terms.

### Dictionary content

The dictionary is presented in a flat list format, with optional fields for recording the "Sounds like" and "Long form of the term," and a comments section to provide more context. This helps you manage and collect entries from systems or product groups in your organization. Each custom dictionary includes the following columns:

| Column | Definition |
| --- | --- |
| Term *(required)* | The display form of the term or phrase. This field is required to validate an entry. **This field is required**. |
| Sounds like | A column to record how the word was pronounced in a meeting. This field is optional. |
| Long form of the term *(for acronyms)* | A column to clarify potential acronyms or abbreviations. This field is optional. |
| Definition and context | A column to provide more context or definition of the term. This field is optional. |

Note

Currently, the custom dictionary only enhances the meeting transcript. The 'Long form of the term' and 'Definition and context' will be applied in future AI enhancements for Intelligent Recap and Copilot responses.

### Dictionary sample

The following are examples of dictionary entries. The first column, **Term**, is the most important and should be mapped to your expected format from the transcription output.

| Term*(required)* | Sounds like | Long form of the term*(for acronyms)* | Definition and context |
| --- | --- | --- | --- |
| TAC | Tee-Ay-Cee | Teams Admin Center | Admin portal managing Teams |
| TAT | Tee-Ay-Tee | Turn Around time | Metric the support team uses and must meet |
| Viva Glint | Vee-Vah-Glint |  | Part of Microsoft Viva |

Tip

The **Term** column is required, while all other columns are optional.

### Dictionary sample (Japanese)

Japanese meetings commonly mix multiple scripts — **kanji** (漢字), **katakana** (カタカナ), and **Latin alphabet**. Enter the **Term** in the exact script you want to appear in the transcript. Use the **Sounds like** column for phonetic guidance in hiragana or katakana.

| Term*(required)* | Sounds like | Long form of the term*(for acronyms)* | Definition and context |
| --- | --- | --- | --- |
| Azure | アジュール |  | クラウドプラットフォーム |
| コパイロット | こぱいろっと | Microsoft Copilot | AI アシスタント機能 |
| TAC | ティーエーシー | Teams Admin Center | Teams 管理センターの略称 |
| 多要素認証 | たようそにんしょう | MFA | セキュリティ認証方式 |
| Teams 文字起こし | チームズもじおこし |  | 会議のトランスクリプト機能 |

#### Guidelines for Japanese dictionary entries

- **Enter terms in the expected script form.** The Term column should native Japanese pronunciation rules of spoken term. The transcript output is biased toward the script form you provide — for example, entering **コパイロット** (katakana) guides the model to produce katakana output, while entering **Copilot** (Latin) guides it to produce Latin output.
- **Do not add spaces within terms.** Follow standard Japanese writing conventions. Japanese text is processed at the character level, so enter terms without word spacing — for example, **多要素認証**.
- **Mixed Kana and Latin terms are supported.** Terms that combine scripts are accepted, but they should still follow natural pronunciation patterns. For example, **Teams文字起こし** reflects how the term is naturally spoken.

### Dictionary file format and language

You should create the dictionary in a CSV plain-text format with UTF-8 encoding and comma-delimited format. We recommend the Excel output format option "CSV UTF-8 (comma delimited)." Each dictionary can contain up to 1000 terms/entries. You can upload one dictionary per language, which is applied to the target Teams transcription language(region) setting as described in the following table.

| Custom dictionary Language | Teams transcription Language |
| --- | --- |
| English | English (United States) |
| English | English (United Kingdom) |
| English | English (Australia) |
| English | English (Canada) |
| English | English (India) |
| Spanish | Spanish (Spain) |
| Spanish | Spanish (Mexico) |
| Japanese | Japanese (Japan) |
| French | French (France) |
| French | French (Canada) |
| German | German (Germany) |
| Portuguese | Portuguese (Brazil) |
| Italian | Italian (Italy) |
| Chinese (Simplified) | Chinese (Simplified, China) |
| Chinese (Traditional) | Chinese (Traditional, Taiwan) |
| Dutch | Dutch (Netherlands) |
| Korean | Korean (Korea) |
| Thai | Thai (Thailand) |
| Turkish | Turkish (Turkey) |

## Upload a custom dictionary

### Navigate through the Microsoft 365 admin center

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).
2. From the navigation pane, select **Copilot**, and go to **Settings**.
3. Under the **Name** column, select **Copilot Custom Dictionary** to open the custom dictionary management pane.
4. Select **Upload Dictionary**.

### Create the custom dictionary with a CSV file

1. Select the option to download the **CSV template with header only** from the portal.
2. Open the template with Excel, open with UTF-8 and comma-delimited format.
3. Fill in your custom terms in the **Term *(required)*** column as a flat list.
4. *(optional)* To learn how to populate the additional information, download the **template with sample dictionary info** (available in **English** or **Japanese**).
5. *(optional)* Fill in additional information in the **Sounds like**, **Long form of the term *(for acronyms)***, and **Definition and context** columns.
6. Save the file as CSV UTF-8 (Comma delimited) (.csv).

### Upload your custom dictionary

1. Return to the uploading view and select your CSV file in the **Upload CSV file with terms** field.
2. Select the target language for this dictionary, then select **Upload**.

Note

The language you select must match the intended language for transcription.

1. After the loading page, a message appears at the top of the view, indicating if the upload was successful. If successful, your dictionary appears in the dictionary list in the management view.
2. Wait for up to 24 hours for the dictionary to become available for Teams meetings in your organization.

## Optimize your custom dictionary

To optimize your custom dictionary, follow these best practices:

- Include frequently mentioned terminology, acronyms, product names, project codes, team names, and industry-specific language relevant to your meetings.
- Allowed symbols in term- Don't include punctuation in the **Term** column and use fewer symbols. Symbols allowed in the middle of terms are: **-'/&·ㆍ**.
- Localize dictionaries- To create dictionaries in the corresponding languages, you should collect custom terms from each local group. For example, in the Japanese dictionary, some terms might remain in their English Latin form, while others might have local variants. Include all these terms in the Japanese custom dictionary to benefit meetings where Japanese is the primary language.
- Break down multi-word names- For names with multiple words, consider splitting them into individual parts. For example, instead of "Copilot in Power Platform and Dynamics 365," create separate entries for "Copilot," "Power Platform," and "Dynamics 365."
- Use Copilot for extra fields- Use Copilot to generate entries for **Sounds like**, **Long form of the term *(for acronyms)***, and **Definition and context**, then review and modify the entries as needed.
- Avoid short words: Avoid using short terms like "AB."
- Avoid numeric terms: Avoid including terms that are purely numeric like "123."
- Avoid repeated chars: Avoid using terms with repeated chars like "AAA."

## Maintain your custom dictionary

You can keep your custom dictionary up to date as your organization’s terminology evolves (for example, new project names, acronyms, or product releases). There are two common maintenance approaches:

#### Option 1: Replace an existing dictionary (full overwrite)

If you updated your existing dictionary by editing the original CSV (for example, adding new terms or removing outdated terms), upload the updated CSV again using the **Upload a custom dictionary** flow. Uploading a dictionary in the same language replaces the existing dictionary for that language.

#### Option 2: Add entries to an existing dictionary (incremental update)

If you only collected **new incremental terms** (a smaller CSV containing only the new rows you want to add), you can append them to the existing dictionary without reuploading the full file:

1. In the custom dictionary management view, locate the dictionary you want to update.
2. Select the three dots (more actions) next to the dictionary.
3. Select **Add entries**, and upload a CSV that contains only the new terms you want to append.

## Data safety

- Custom dictionary should be restricted to tenant-specific terms that are relevant to the tenant's needs and must not contain any confidential, sensitive, or personal information.
- Custom dictionary data is used solely within your organization for meetings. Nobody else accesses the data and it isn't included in any AI model training.

## Supported scenarios

### Supported

Custom Dictionary enhances entity recognition for Teams transcription in the following scenarios:

- Scheduled meetings
- Events

### Not supported

Custom Dictionary isn't supported in the following scenarios:

- Group and 1:1 calls