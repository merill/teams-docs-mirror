---
layout: Conceptual
title: Manage the Shifts app for your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal0201
ms.author: vikasalmal
manager: jtremper
ms.date: 2026-05-22T00:00:00.0000000Z
ms.topic: how-to
ms.reviewer: harrywong
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Learn how to set up and manage the Shifts app in Teams for frontline workers in your organization.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
- teams-1p-app-admin
- highpri
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 58ea9573-59b1-1499-fb83-517d0ee0f034
document_version_independent_id: bf98f739-ff51-0b90-dbc5-c594d3dacecd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 04e8ffe8-f85a-9402-26bc-f924a3f6d398
---

# Manage the Shifts app for your organization - Microsoft Teams | Microsoft Learn

## Overview of Shifts

The Shifts app in Microsoft Teams keeps frontline workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams. Frontline workers and their managers can use their mobile devices to manage schedules and keep in touch.

- Managers create, update, and manage shift schedules for their teams. They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes"). They can also send policy documents, news bulletins, and videos.
- Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.

It's important to know that Shifts currently doesn't support guests. This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.

Note

For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## Licensing

Users must have a Teams license to use Shifts.

Note

Shifts is available in Government Community Cloud (GCC) environments, but not in GCC High or DoD environments.

## Location of Shifts data

Shifts data is stored in one of the following region geographies: Asia Pacific (APAC), European Union (EU), or United States. Additionally, Shifts offers data residency locally in Australia, Canada, France, Japan, and the United Kingdom.

To learn more about Shifts data, including data storage location, security and compliance, and access control, see [Shifts data FAQ](shifts-data-faq).

## Deploy Shifts

For an overview of deploying Shifts in your organization, see [Shifts for your frontline organization](/en-us/microsoft-365/frontline/shifts-for-teams-landing-page).

## Set up Shifts

### Enable or disable Shifts in your organization

Shifts is enabled by default for all Teams users in your organization. You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps) page in the Microsoft Teams admin center.

1. In the left navigation of the Teams admin center, go to **Teams apps** &gt; **Manage apps**.
2. In the list of apps, search for the Shifts app, select it, and then switch the **Status** toggle to **Blocked** or **Allowed**.

### Enable or disable Shifts for specific users in your organization

To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps) page. Then create a custom policy for app permissions and assign it to those users. To learn more, see [Use app permission policies to control user access to apps](../../teams-app-permission-policies).

### Pin Shifts to Teams

#### Use the Tailored frontline app experience to pin Shifts and other apps to Teams

The tailored frontline app experience in Teams pins the most relevant apps in Teams for users who have an [F license](https://www.microsoft.com/microsoft-365/enterprise/frontline-plans-and-pricing). Pinned apps include Shifts, Walkie Talkie, Tasks, and Approvals. By default, this feature is on, giving your frontline workers an out-of-the-box experience tailored to their needs.

The apps are pinned to the app bar—the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients—where users can quickly and easily access them.

To learn more, including how the experience works with app policies that you set, see [Tailor Teams apps for your frontline workers](/en-us/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json).

#### Use an app setup policy to pin Shifts to Teams

App setup policies let you customize Teams to pin the apps that are most important for your users.

You can create a [custom policy in app setup policy](../../teams-app-setup-policies) by adding the Shifts app, and then [assign the policy](../../assign-policies-users-and-groups) to your users. Or, you can use the app setup policy that's part of the Frontline Worker and Frontline Manager policy packages.

A [policy package](../../manage-policy-packages) in Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization. The set of policies in the Frontline Worker and Frontline Manager policy packages include an app setup policy that pins the Shifts app and other apps that support communication and collaboration activities for that role.

We recommend using the Frontline Worker and Frontline Manager policy packages as they simplify, streamline, and help provide consistency when managing policies for your frontline workforce. To learn more, see [Teams policy packages for frontline workers](../../policy-packages-flw).

### Enable shift-based tags in Teams

[Tags](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e) in Teams let users easily connect with a subset of people on a team. With shift-based tags, people are automatically assigned tags that match their schedule and shift group name in Shifts. The tag can be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.

Shift-based tags let your users reach people who are on-shift in real time. Notifications are sent only to those people who are on-shift at the time the tag is used in a chat or channel post. For example:

- A store manager uses the @Cashiers tag to post an announcement to a channel for all on-shift cashiers.
- A nurse uses the @CardiologistsOnCall tag to start a chat with all on-call cardiologists.

You can turn the feature on or off in the Microsoft Teams admin center. To learn more, see [Manage tags in Teams](../../manage-tags).

## Search the audit log for Shifts events

You can search the audit log to view Shifts activity in your organization. To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events).

Before you can search the audit log, you have to first turn on auditing in the Microsoft Purview portal. To learn more, see [Turn audit log search on or off](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Keep in mind that audit data is only available from the point at which you turned on auditing.

## Give feedback or report an issue

To send feedback or report an issue, select **Settings and more** (**…**) in Teams, and then choose **Help** &gt; **Give feedback**. Enter your feedback or details about the issue you're experiencing. Indicate at the beginning of your feedback report that you're sending feedback about Shifts so we can easily identify Shifts issues.