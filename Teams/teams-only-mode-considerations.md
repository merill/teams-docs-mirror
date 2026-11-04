---
layout: Conceptual
title: Teams Only mode considerations - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-only-mode-considerations
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: jtremper
author: jacktremper
manager: serdars
ms.date: 2019-01-09T00:00:00.0000000Z
ms.topic: concept-article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: landerl
description: Admin can learn about how to prepare for an upgrade to Microsoft Teams Only mode in the Microsoft Teams admin center.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
locale: en-us
document_id: 1a2fc46c-d6fb-fd8b-e2aa-fdee7c742230
document_version_independent_id: e0d36a99-2823-68a2-7e97-0c1ba66efd51
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-only-mode-considerations.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-only-mode-considerations
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-only-mode-considerations.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5f9436f4-5f1a-00d4-2374-12266dd35729
---

# Teams Only mode considerations - Microsoft Teams | Microsoft Learn

Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.

Important

Skype for Business Online operated by 21Vianet in China was retired on October 1, 2023. If you haven't upgraded your Skype for Business Online users to Teams, they are automatically scheduled for an [assisted upgrade](/en-us/microsoftteams/upgrade-assisted). If you want to upgrade your organization to Teams yourself, we strongly recommend that you begin planning your upgrade path today. Remember that a successful upgrade aligns technical and user readiness, so be sure to use our [upgrade guidance](/en-us/microsoftteams/upgrade-start-here) as you navigate your journey to Teams.

Skype for Business Online, excluding the service operated by 21Vianet in China, was retired on July 31, 2021.

Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience. Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.

Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way. For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.

Important

If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here) guide.

**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs. Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa. To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business. Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams. Users who are upgraded to Teams Only can still join Skype for Business meetings.

Important

For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability). For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop).

**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization. In particular, we are still working on addressing scenarios for users whose primary device is VDI-based. For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

Note

Before you move to Teams Only mode you need to replace or update devices that don't support Teams.

Important

**Remember**: The move to Teams is more than a technical migration. A successful upgrade assesses both technical readiness and end-user readiness. Review our Skype for Business to Teams [upgrade guidance](upgrade-framework) for more information on planning an implementing your upgrade to Teams.