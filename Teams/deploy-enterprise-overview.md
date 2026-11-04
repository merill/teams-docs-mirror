---
layout: Conceptual
title: Microsoft Teams enterprise deployment overview - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/deploy-enterprise-overview
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.date: 2021-01-29T00:00:00.0000000Z
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
description: Learn how to deploy enterprise features of Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
locale: en-us
document_id: dadf811e-f1d5-1eeb-e0c7-76fac62b6bff
document_version_independent_id: d2d1204b-ca8f-a92d-bab2-c34df7b5cc95
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/deploy-enterprise-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: deploy-enterprise-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/deploy-enterprise-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 329024db-85f8-a032-ed01-558223d0f42d
---

# Microsoft Teams enterprise deployment overview - Microsoft Teams | Microsoft Learn

If you're a medium or large business, you need to think about things like:

- How you're going to roll out the Microsoft Teams service to your users.
- How you're going to deploy the Teams client to everyone.
- How your network design could impact the quality of real-time communication.

This article helps with pointers to articles to help you plan for Teams in your organization.

Important

We strongly suggest that you begin your Teams deployment with a pilot. A pilot allows you and a few early adopters to get familiar with Teams and its features before your planning and eventual rollout. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start).

After you read the following sections and are ready to start deploying Teams in your organization, see [Set up Microsoft Teams in your enterprise](deploy-enterprise-setup).

Tip

As a companion to this article, we recommend using the [Microsoft Teams automated setup guide](https://go.microsoft.com/fwlink/?linkid=2224815) when signed in to the Microsoft 365 admin center. This guide customizes your experience based on your environment. To review best practices without signing in and activating automated setup features, go to the [Microsoft 365 setup portal](https://go.microsoft.com/fwlink/?linkid=2222975).

## Architecture

Teams is tightly integrated into Microsoft 365 and uses many features to power chat, file sharing, meetings, telephony, video streaming, and more. Before you roll out Teams, check out [Microsoft Teams IT architecture and telephony solutions posters](teams-architecture-solutions-posters) to get familiar with how Teams works with the rest of Microsoft 365. This strategy creates a complete collaboration experience for your users.

## Workloads

Teams has three workloads that can be deployed independently of each other: **chat, teams, and channels**; **meetings and conferencing**; and **Phone System and PSTN (public switched telephone network) connectivity**. Each workload has its own section in our documentation to make it easier to find information about that workload, including deployment planning information.

To see deployment planning information for the workload you want to deploy, see the following articles:

- [Chat, teams, and channels](deploy-chat-teams-channels-microsoft-teams-landing-page)
- [Meetings and conferencing](deploy-meetings-microsoft-teams-landing-page)
- [Phone System and PSTN connectivity](cloud-voice-landing-page)

## Network planner

Network planning for Teams is extremely important when you have large numbers of users, complex networks, or both. Teams supports voice calling and video conferencing, both of which rely on real-time communications to provide the best experience possible for users. Networks must:

- Have sufficient bandwidth capacity to accommodate the number of concurrent voice calls, video conferences, meetings, screen sharing, and so on.
- Have network hardware that supports real-time communication protocols.
- Allow the required network ports between devices on your networks, Microsoft 365 services, and people outside the network.

See the following articles to help you understand Teams network requirements:

- [Prepare your organization's network for Microsoft Teams](prepare-network)
- [Proxy servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online)

To help you with your planning, Teams includes the Network planner. The Network planner asks you questions about the number and types of users you have, how many sites your organization has, the bandwidth capacity of your network links, and more. The Network planner uses this information to create a report that shows the bandwidth requirements for each activity, along with recommendations.

(You must be a Microsoft 365 Global admin or a Teams administrator to open the Network planner.)

For details about how the Network planner works, see [Use the Network planner for Microsoft Teams](network-planner).

To see an example of how Network planner can plan your network, see [Using Network Planner - example scenario](tutorial-network-planner-example).

## Teams advisor

The Teams advisor is a solution within Teams that brings together teams, channels, file sharing, and Planner, to create a deployment project for your organization. Teams advisor creates project plan, specific to the workload you select (such as chat, teams, and channels), that includes the recommended tasks you should perform during your deployment. Each task contains instructions, suggestions, and links to relevant articles, to guide you through the process. You can easily assign tasks to one or more individuals, and specify start and end dates for each task.

Tip

See how you can use Teams advisor to help you plan your Teams deployment by completing the [Roll out using the Teams advisor](/en-us/training/modules/m365-teams-rollout-using-advisor/) module on Microsoft Learn.

(You must be a [Microsoft 365 global admin](/en-us/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Teams advisor.)

For details about how the Teams advisor works, see [Use Advisor for Teams to help you roll out Microsoft Teams](use-advisor-teams-roll-out).

## Lifecycle and governance planning

As you plan your Teams deployment, you need to consider the lifecycle of teams, channels, files, and so on, in your organization. You should also think about what types of information to be stored in them. Teams may be created for a specific project, for a department, or they might be used as a central resource for the entire organization. Each of these uses has different requirements, which drive questions like:

- How long a teams environment could remain active?
- Who should own and manage the teams and their channels?
- Should certain compliance requirements apply to some teams, but not others?
- Should there be a naming policy to help users identify the right team?

Creating policies and guidelines as part of your initial deployment helps ensure that your users can find the information they need. Just as importantly, however, appropriate policies help protect your organization from information leakage, help you conform to regulatory requirements, and help you retain information as needed for archival purposes.

To learn more about lifecycle management and governance in Teams, see the following articles:

- [Plan for lifecycle management in Teams](plan-teams-lifecycle)
- [Plan for governance in Teams](plan-teams-governance)
- [Manage and monitor Teams](/en-us/microsoftteams/manage-teams-in-modern-portal)

## Adoption

To ensure that your organization and your users get the most out of Teams, you need an adoption program. An effective adoption program can mobilize early adopters who can:

- Articulate the benefits of Teams to their colleagues and to business or group leaders.
- Spark excitement in others who see how Teams improves collaboration and makes it easier to connect with each other.
- Help evaluate existing business processes and make recommendations for how Teams can be integrated into them.
- Help improve the adoption process by reporting both successes and difficulties back to the deployment team.

For details about setting up an adoption program, see [Adopt Microsoft Teams](adopt-microsoft-teams-landing-page).

## Teams analytics & reports

Teams reports in the Teams admin center give you insights into how Teams is used in your organization. Use the reports to get a view into Teams usage, user activity, and device usage across your organization.

To view these reports, you must be a global administrator or Teams administrator. Go to the Microsoft Teams admin center, in the left navigation, select **Analytics & reports**, and then under **Report**, choose the report you want to run.

For more information about available reports, see [Microsoft Teams analytics and reporting](teams-analytics-and-reports/teams-reporting-reference).