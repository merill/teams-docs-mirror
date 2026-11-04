---
layout: Conceptual
title: Introduction to Microsoft Teams for admins - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.topic: concept-article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: divyasrirk
ms.date: 2026-08-14T00:00:00.0000000Z
description: Find the right path to rolling out Microsoft Teams in your organization. Learn about the Teams infrastructure and using Teams with Microsoft 365 or Office 365.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
- essentials-overview
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.allteamsdocuments
- intro-overview
- teams-chat-and-channels
locale: en-us
document_id: a795a46e-52eb-c338-8bd2-fd0133cfcfd0
document_version_independent_id: 1d64ea4b-376b-4845-c5e0-ce90f8ed6089
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/Teams-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/Teams-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: fe92bb73-e579-57b6-ce84-46c54967d632
---

# Introduction to Microsoft Teams for admins - Microsoft Teams | Microsoft Learn

If you're the admin for Microsoft Teams in your organization, you're in the right place. When you're ready to get going with Teams, start with [Teams deployment overview](deploy-overview) and [Set up secure file sharing and collaboration with Microsoft Teams](/en-us/microsoft-365/solutions/setup-secure-collaboration-with-teams).

If you're looking for end user Teams help, select **Help** on the left side of the app or go to [Microsoft Teams help & learning](https://support.office.com/teams). For training, go to [Microsoft Teams training](training-microsoft-teams-landing-page).

Important

For details about Teams feature availability and licensing, see [Teams add-on licensing options](/en-us/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## Teams architecture

Teams is built on Microsoft 365 groups, Microsoft Graph, and the same enterprise-level security, compliance, and manageability as the rest of Microsoft 365. Teams uses identities stored in Microsoft Entra ID.

When you create a team, here's what gets created:

- A new [Microsoft 365 group](office-365-groups).
- A [SharePoint](/en-us/sharepoint/teams-connected-sites) site and document library to store team files.
- An [Exchange Online](exchange-teams-interact) shared mailbox and calendar.
- A OneNote notebook.
- Ties into other Microsoft 365 apps such as Planner and Power BI.

When you create a team from an existing group, that group's membership, site, mailbox, and notebook appear in Teams.

To customize and extend Teams, add third-party apps by using [app management tasks](apps-in-teams). With Teams, you can include people from outside your organization by adding them as a [guest or an external user](communicate-with-users-from-other-organizations), depending on what you need. Teams offers a robust [development platform](/en-us/microsoftteams/platform) so you can build the teamwork hub you need for your organization.

Tip

For a deep dive into Teams architecture, watch the videos on the [Teams Platform Academy](https://aka.ms/TeamsPlatformAcademy).

## Managing Teams

As the admin, you manage Teams through the Teams admin center.

To learn how to manage Teams in the Teams admin center, see:

- [Use Teams admin roles to manage Teams](using-admin-roles)
- [Manage and monitor Teams as an IT administrator](manage-teams-overview)
- [Manage Teams settings](settings-policies-reference#teams-settings)
- [Manage teams in the Teams admin center](manage-teams-in-modern-portal)

To stay on top of what's coming for Teams and all other Microsoft 365 products and services in your organization, check [Message center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) and the [Teams roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&amp;filters=Microsoft%20Teams). You get announcements about new and updated features, planned changes, and issues to help keep you informed and prepared.

Alternatively, you can stay up to date on the latest Teams features and updates across the Teams admin center and the Teams client through **What's new** in the Teams admin center. To access it, select **What's new** (the lightning bolt icon) in the upper-right corner.

[![Screenshot showing the What's new pane in the Teams admin center.](media/teams-overview-whats-new.png)](media/teams-overview-whats-new.png#lightbox)

## Teamwork

Every team is different; there's no one-size-fits-all approach to collaboration. When deciding which apps and services to use, think about the work your organization does and the types of conversations your teams need to have:

- **Teams**, as the hub for teamwork, is where people—including people outside your organization—can actively connect and collaborate in real time to get things done. Have a conversation right where the work is happening, whether coauthoring a document, having a meeting, or working together in other apps and services. Teams is the place to have informal chats, iterate quickly on a project, work with team files, and collaborate on shared deliverables.
- **Outlook** for collaborating in the familiar environment of email and in a more formal, structured manner or when targeted and direct communication is required.
- **SharePoint** for sites, portals, intelligent content services, business process automation, and enterprise search. SharePoint keeps content at the center of teamwork, making all types of content easily shareable and accessible across teams. Tight integration with Outlook, Viva Engage, and Teams enables seamless content collaboration across conversation experiences.
- **OneDrive** for storing files and sharing them with people that a user invites. Content that a user saves to OneDrive is private until the user shares it with others, making it the best option for storing personal and draft documents that aren't intended to be shared or not ready to be shared.
- **Viva Engage** to connect people across the organization. Drive company-wide initiatives, share best practices, and build communities around common topics of interest or areas of practice. Crowd source ideas to foster open discussions with people across the company.
- **Office apps** are all the familiar tools that people know and use regularly, including Word, Excel, PowerPoint, and OneNote.