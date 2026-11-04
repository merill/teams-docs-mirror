---
layout: Conceptual
title: Create a custom team template in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/create-a-team-template
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: aaglick
ms.date: 2024-06-13T00:00:00.0000000Z
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: teams-chat
search.appverid: MET150
description: Learn how to create a custom team template in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- chat-teams-channels-revamp
- teams-chat-and-channels
ms.collection:
- M365-collaboration
locale: en-us
document_id: 8da3d209-eb82-1a62-9bd5-81ba18792cd4
document_version_independent_id: 94dca200-ab33-7a57-1504-e3ee7e5c610a
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/create-a-team-template.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: create-a-team-template
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/create-a-team-template.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: cd265e78-196e-f2b6-29b3-757356ca7814
---

# Create a custom team template in Microsoft Teams - Microsoft Teams | Microsoft Learn

A custom team template is a predefined team structure with a set of channels, tabs, and apps. You can develop a template that helps you create the right collaboration space quickly. Your custom team template uses your preferred settings.

To get started:

1. Sign in to the Teams admin center.
2. In the left navigation, expand **Teams** &gt; **Team templates**.
3. Select **Add**.

    ![An image of the Team templates dialog with Add highlighted.](media/team-templates-new.png)
4. In the **Team templates** section, select **Create a brand new template**.
5. In the **Template settings** section, complete the following fields and then select **Next**:

    - Template name
    - Template short and long descriptions
    - Locale visibility

    ![An image of the Team templates settings naming dialog.](media/template-add-a-name.png)
6. In the **channels, tabs, and apps** section, add any channels and apps that your team needs.

    1. In the **Channels** section, select **Add**.
    2. In the **Add** dialog, name the channel.
    3. Add a description.
    4. Decide if the channel should be shown by default.
    5. Search for an app name that you want to add to the channel.
    6. Select **Apply** when finished.

    ![An image of the Team templates channels, tabs, and apps screen.](media/template-channels-tabs-apps.png)
7. Select **Submit** when completed.

Your new template is displayed in the **Team templates** list. The template can be used to create a team in Teams.

Note

It can take up to 24 hours for teams users to see a custom template change in the gallery.

## Customizing Website Tab apps

Note

This feature is in early preview

You might want to specify URLs for website tabs for channels in custom team templates. End users who create teams with templates will have website tabs that are preset to the specified site URL.

To get started:

1. Create a new team template or edit an existing team template.
2. In the Channels section, add a new channel or select an existing channel and select **Edit**.
3. In the **Add an app for this template** section, add a Website app.

    ![add an app for this template option.](media/add-an-app-template.png)
4. Select the edit icon and input the URL of your choice.

    ![add an app url.](media/add-url-app-template.png)
5. Select **Save** for your tab app edits, and then select **Apply** to save your changes.

## Known issues

**Problem**: If you created a team from a custom template that contained additional custom tabs, you might see blank tabs in place of your custom tab apps. Your default tabs (such as **Posts**, **Files**, and **Wiki**) will appear as expected.

**Solution**: To fix this issue, remove the custom tab and add a new tab with the same app. If you don't have permissions to remove the custom tab and add a new tab, contact the team owner for assistance.

We're currently working on a fix for future teams created from custom templates.

**Problem**: When you use Teams in the browser, some websites don't support being rendered within a Teams tab.

![browser error message.](media/browser-error-message.png)

**Solution**: If you have trouble viewing the contents of the website tab, you'll be redirected to either open the tab in a separate webpage, or open Teams in the desktop app instead to view your website tab app.