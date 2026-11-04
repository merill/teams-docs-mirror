---
layout: Conceptual
title: Manage the registration form for Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-registration-form-events
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
audience: admin
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-events
ms.reviewer: justle, absri
ms.date: 2026-07-06T00:00:00.0000000Z
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Learn how to manage the registration form for Teams events in your organization. Admins can control whether organizers can require attendees to answer standard and custom questions on the form.
locale: en-us
document_id: d1cc4f03-68f6-833d-0ab5-f3cb7ee3b3e3
document_version_independent_id: d1cc4f03-68f6-833d-0ab5-f3cb7ee3b3e3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-registration-form-events.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-registration-form-events
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-registration-form-events.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3642b210-34d9-a0a0-a821-bb7329384477
---

# Manage the registration form for Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a x for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

## Overview

The registration form enables organizers to collect information from attendees when they register for Teams events. As an admin, you can manage whether organizers can require attendees to answer standard and custom questions on the registration form.

The registration form includes three categories of questions.

- **Required questions**: All attendees must answer these questions. Organizers can't remove the following default questions.

    - First name
    - Last name
    - Microsoft consent field
- **Standard questions**: Organizers can't edit these preset questions. Attendees aren't required to answer predefined questions, but you can allow organizers to make them required.

    - Address
    - City
    - State
    - Zip or postal code
    - Country/region
    - Industry
    - Job title
    - Organization
    - Legal terms
- **Custom questions**: Organizers create custom questions using the following formats. Attendees aren't required to answer custom questions, but you can allow organizers to make them required.

    - Text input
    - Choices
    - Checkbox (Yes/No)

## Manage the registration form

You can use the Teams admin center or PowerShell to manage the types of questions an organizer can require attendees to answer when registering for events.

| Teams admin center policy option | Parameter value in PowerShell | Behavior |
| --- | --- | --- |
| **Required only** | `DefaultOnly` | Organizers with this assigned policy can require attendees to only answer required questions on the registration form. |
| **Standard and required only** | `DefaultAndPredefinedOnly` | Organizers with this assigned policy can require attendees to only answer standard and required questions on the registration form. |
| **Custom, standard, and required** | `AllQuestions` | **This is the default value**. Organizers with this assigned policy can require attendees to answer standard, required, and custom questions on the registration form. |

### Use the Teams admin center to manage the registration form

To manage the registration form questions by using the Teams admin center, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. Next to the **Webinar registration form questions** setting, choose one of the following options in the dropdown list:

    - **Required only**
    - **Standard and required**
    - **Custom, standard, and required**
4. Select **Save**.

## Use PowerShell to manage the registration form

To manage the registration form questions, use the **`-AllowedQuestionTypesInRegistrationForm`** parameter in the **CsTeamsEventsPolicy** cmdlet.

To enable organizers to only require the required questions on the registration form, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedQuestionTypesInRegistrationForm DefaultOnly
```

To enable organizers to require standard and required questions on the registration form, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedQuestionTypesInRegistrationForm DefaultAndPredefinedOnly
```

To enable organizers to require standard, required, and custom questions on the registration form, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -AllowedQuestionTypesInRegistrationForm AllQuestions
```