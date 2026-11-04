---
layout: Conceptual
title: Set a custom meeting template as the default in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/custom-meeting-templates-set-default
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: v-lanchin
author: LanaChin8
manager: v-jesserowe
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: maahma
ms.date: 2026-10-30T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
description: Learn how to set a custom meeting template as the default template in Microsoft Teams to automatically apply meeting settings when users schedule meetings in the Teams calendar or Outlook.
locale: en-us
document_id: 038d8bf8-7490-11e9-f2e7-ad47f153d87a
document_version_independent_id: 038d8bf8-7490-11e9-f2e7-ad47f153d87a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/custom-meeting-templates-set-default.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: custom-meeting-templates-set-default
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/custom-meeting-templates-set-default.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 9e467f4b-7e18-5dae-2f84-2b09f89f5f3d
---

# Set a custom meeting template as the default in Microsoft Teams - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

## Overview

As an admin, you can set a custom meeting template as the default to automatically apply your organization's preferred meeting settings when users schedule Teams meetings through the Teams calendar or Outlook. Default meeting templates help you consistently apply meeting settings, including meeting protection settings for security and compliance, and reduce the need for organizers to manually configure meeting options.

Organizers must have a Teams Premium license to use default meeting templates.

After you [create a custom meeting template](create-custom-meeting-template), you can set it as the default in a Teams meeting template policy. When users who are assigned the policy schedule new meetings, the default template is automatically applied, retaining the custom template's default values and any locked or hidden meeting options.

Note

Only custom meeting templates can be set as the default. Predefined meeting templates included in Teams can't be set as the default.

## Set the default meeting template

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting template policies**.
2. Select an existing policy or create a new one.
3. In the list of templates, choose the custom template you want to set as the default, and then select **Set as default**.

    [![Screenshot of the **Set as default** option to set a custom meeting template as the default in a meeting template policy.](media/custom-meeting-templates-set-as-default-small.png)](media/custom-meeting-templates-set-as-default.png#lightbox)
4. In the dialog, select **Set as default** to confirm.

    After you set the template as the default, a **Default** tag appears next to the template in the list.

    [![Screenshot of a custom template set as the default, showing the **Default** tag.](media/custom-meeting-templates-default-tag-small.png)](media/custom-meeting-templates-default-tag.png#lightbox)

## User experience

Here's an overview of the user experience when you set a default meeting template.

### Organizer experience

When an organizer schedules a new meeting in the Teams calendar or Outlook, the default meeting template is automatically applied. Organizers:

- Can change meeting options that have a default value but aren't locked.
- Can't change meeting options that are locked.
- Can't see meeting options that are hidden.

### Attendee experience

Any meeting settings enforced through the default meeting template apply to attendees.

## Remove a template as the default

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting template policies**.
2. Select the policy you want to configure.
3. In the list of templates, select the template that's set as the default, and then select **Remove as default**.

    After you remove the template as the default, it's no longer automatically applied to new meetings.

## Platform support

Default meeting templates are supported in the Teams calendar and Outlook on Teams desktop (Windows and Mac) and web. Both new Outlook and classic Outlook are supported.

## Known issue

Users might encounter errors in certain meeting scenarios when using a default meeting template if the **Copilot** setting in the Teams meeting policy is set to **On with saved transcript required**. This issue is related to the Copilot meeting policy and not the default meeting template. Until the issue is resolved, we recommend using a different Copilot setting.