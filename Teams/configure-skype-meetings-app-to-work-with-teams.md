---
layout: Conceptual
title: Configure the Skype Meetings App to work with Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/configure-skype-meetings-app-to-work-with-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: 
author: wlibebe
ms.author: wlibebe
manager: pamgreen
ms.date: 2019-06-21T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: Admins can use the Microsoft Teams admin center to configure the Skype Meetings App to work with Teams
ms.collection:
- M365-collaboration
- m365initiative-meetings
locale: en-us
document_id: 2e412595-1a6e-8f12-dd7b-d268513632d3
document_version_independent_id: b7f1f24e-f21d-3258-ced9-67590fef9b45
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/configure-skype-meetings-app-to-work-with-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-skype-meetings-app-to-work-with-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/configure-skype-meetings-app-to-work-with-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/49ce37d9-33ea-421e-9eb9-c852f2d9c13f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d2e24716-af9a-48e2-bf0d-f248d9cc672a
platformId: e4d3e692-5505-3100-2b23-bbaf5a6609bf
---

# Configure the Skype Meetings App to work with Teams - Microsoft Teams | Microsoft Learn

After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.

To specify the Skype for Meetings App as the preferred app:

1. Sign in to the Microsoft Teams admin center.
2. In the left pane, under **Teams**, select **Teams upgrade settings**.
3. On the Teams upgrade page, under **App preferences**, select **Skype Meetings App** from the **Preferred app for users to join Skype for Business meetings** drop-down list.

    ![Choose Preferred app for users to join Skype for Business meetings.](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## Known limitations

Users who use the Skype Meetings App with Teams are subject to the following limitations:

- Users can't change their video device.
- After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App isn't placed on hold. Instead, the user is connected to both calls.

## More information

- [What is Skype Meetings App (Skype for Business Web App)](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- [Skype Meetings App minimum network requirements](/en-us/previous-versions/office/communications/mt845808%28v=ocs.16%29)