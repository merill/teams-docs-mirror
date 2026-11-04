---
layout: Conceptual
title: Use the Teams App Submission API to submit and approve your custom apps - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/submit-approve-custom-apps
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal0201
ms.author: vikasalmal
manager: prkosh
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 2026-06-01T00:00:00.0000000Z
ms.reviewer: mhayrapetyan
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: Learn how to approve your custom apps that are submitted using the Teams App Submission API in Microsoft Teams.
locale: en-us
document_id: 1869cfc3-db39-95c3-1509-141224197bf3
document_version_independent_id: 7e6b4267-b1c3-4616-d44d-2b0def64b65b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/submit-approve-custom-apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: submit-approve-custom-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/submit-approve-custom-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2d7569e0-1f50-67e3-7b72-b505e58fb3dd
---

# Use the Teams App Submission API to submit and approve your custom apps - Microsoft Teams | Microsoft Learn

This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery. You'll get an overview of the connected experiences that Teams provides across the app lifecycle to streamline how to develop, deploy, and manage custom apps in your organization's app store.

Developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for you to review and approve. You can set policies to manage apps for users in your organization and your users discover these apps in Teams client.

![Screenshot showing the overview of your app from development to deployment.](media/custom-app-lifecycle.png)

When you publish a custom Teams app, it's available to users in your organization's app store. There are three ways to publish a custom app and your approval method depends on how you receive the app from the app developer.

- Developer submits the app using the Teams App Submission API.
- Developer sends you an [app package in .zip format](teams-custom-app-policies-and-settings). The approve app widget isn't available in GCC tenants.
- [Developer uploads custom app using Teams client](/en-us/microsoftteams/platform/m365-apps/publish#single-tenant-distribution) for your approval.

## App developer submits the app

When the app is ready for use in production, the developer can submit the app using the Teams App Submission API, which can be called from [Graph API](/en-us/graph/api/teamsapp-publish?view=graph-rest-beta&amp;tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&amp;preserve-view=true), an integrated development environment (IDE) such as Visual Studio Code, or a platform such as Power Apps and Power Automate. Doing this makes the app available on the [Manage apps](/en-us/microsoftteams/manage-apps) page of the Teams admin center, where you can review and approve it.

The Teams App Submission API, [built on Microsoft Graph](/en-us/graph/api/teamsapp-publish?tabs=http&amp;view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&amp;preserve-view=true), allows your organization to develop on the platform of your choice and automates the submission-to-approval process for custom apps on Teams.

Here's an example of what this app submission step looks like in Visual Studio Code:

![Screenshot of app submission in Visual Studio Code.](media/custom-app-lifecycle-submit-app.png)

Keep in mind that this doesn't publish the app to your organization's app store yet. This step submits the app to the Teams admin center where you can approve it for publishing to your organization's app store.

For more information about using the Graph API to submit apps, see [here](/en-us/graph/api/teamsapp-publish?tabs=http&amp;view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&amp;preserve-view=true).

## Notification for app submissions

You can turn on notifications so you know when developers submit a new application for review and approval. You'll also get notifications when developers submit app updates. To enable app submission notifications in the Teams admin center, go to **Notifications & alerts** &gt; **[Rules](https://admin.teams.microsoft.com/notifications/rules)** &gt; **App submissions**, and activate the rule by changing the status to **Active**. By default, this setting is turned off. You must be a Teams admin to turn on this setting.

After you turn on this setting, you'll get notifications in the **Admin Alerts and Notifications** team under a new channel named **App submissions**. Alternatively, you can choose an existing team and channel to get notifications delivered to a specified team and channel. To do this, follow these steps:

1. In the **App submissions** rule, select the **Channel alert** checkbox under **Actions**.
2. Choose the **Select channel** button.
3. Search for a team to add.
4. Search for a channel to add.
5. Select **Apply**.

    [![Screenshot showing the custom channel alert notification checkbox.](media/channel-alert.png)](media/channel-alert.png#lightbox)

Note

Select the **Default channel alert** checkbox to receive notifications to the **Admin Alerts and Notifications** team in the **App Submissions** channel.

[![Screenshot showing the default channel alert notification checkbox.](media/default-channel-alert.png)](media/default-channel-alert.png#lightbox)

You can also set up notifications to an external webhook by specifying a public webhook URL after you select the **Webhook** checkbox. A JSON notification payload will be sent to your webhook URL.

[![Screenshot showing app submission notification.](media/app-submission-notification.png)](media/app-submission-notification.png#lightbox)

After you set up the app submissions rule, you can review notification cards in the specified channel to see app details and select **View details** to open apps in the Teams admin center.

## Approve the submitted app

The [Manage apps](/en-us/microsoftteams/manage-apps) page in the Teams admin center (in the left navigation, go to [**Teams apps** &gt; **Manage apps**](https://admin.teams.microsoft.com/manage-apps)), gives you a view into all Teams apps for your organization. The **Pending approval** widget at the top of the page lets you know when a custom app is submitted for approval.

In the table, a newly submitted app automatically shows a **Publishing status** of **Submitted** and **Status** of **Blocked**. You can sort the **Publishing status** column in descending order to quickly find the app.

[![Screenshot showing the publishing status of an app.](media/custom-app-lifecycle-validate-app.png)](media/custom-app-lifecycle-validate-app.png#lightbox)

Select the app name to go to the app details page. On the **About** tab, you can view details about the app, including description, status, submitter, and app ID.

[![Screenshot showing the app details page for a submitted app.](media/custom-app-lifecycle-app-details.png)](media/custom-app-lifecycle-app-details.png#lightbox)

For more information about using the Graph API to check the **Publishing status**, see [here](/en-us/graph/api/appcatalogs-list-teamsapps?tabs=http&amp;view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&amp;preserve-view=true).

## Publish the app to your users

When you're ready to make the app available to users, publish the app.

1. Sign-in to Teams admin center and go to **Teams apps** &gt; **[Manage apps](https://admin.teams.microsoft.com/policies/manage-apps)**.
2. Select the app name to go to the app details page, and then in the **Publishing status** box, select **Publish**.

    [![Screenshot showing the Publish button on the app detail page.](media/submitted-app-pending-action.png)](media/submitted-app-pending-action.png#lightbox)

After you publish the app, the **Publishing status** changes to **Published** and the **Status** changes to **Allowed**.

## Set up and manage

### Control access to the app

By default, all users in your organization can access the app in your organization's app store. To restrict and control who has permission to use the app, you can create and assign an app permission policy. To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies).

### Pin and install the app for users to discover

By default, for users to find the app they have to go to your organization's app store and browse or search for it. To make it easy for users to get to the app, you can pin the app to the app bar in Teams. To do this, create an app setup policy and assign it to users. To learn more, see [Manage app setup policies in Teams](teams-app-setup-policies).

### Search the audit log for Teams app events

You can search the audit log to view Teams apps activity in your organization. To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see [Search the audit log for events in Teams](audit-log-events).

Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://sip.protection.office.com/). To learn more, see [Turn audit log search on or off](/en-us/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&amp;preserve-view=true). Keep in mind that audit data is only available from the point at which you turned on auditing.

## Discover and adopt

Users who have permissions to the app can find it in your organization's app store. In the Teams client, in the Apps page, these apps are available in the **Built for your org** section.

[![Screenshot of Apps page showing published app.](media/custom-app-lifecycle-discovery.png)](media/custom-app-lifecycle-discovery.png#lightbox)

You can create an app setup policy and assign it to all or a few users to pin one ore more apps in Teams client. It improves easy of access and app adoption for the apps that are relevant to the needs of your users.

## Update a custom app

When the developer submits an update to a published custom app, you get notified in the **Pending approval** widget on the [Manage apps page](https://admin.teams.microsoft.com/policies/manage-apps) in admin center. In app listing on Manage apps page, the **Publishing status** of the app is set to **Update submitted**.

[![Screenshot shows Manage apps page with a pending request and status of a newly submitted app.](media/custom-app-lifecycle-update-submitted.png)](media/custom-app-lifecycle-update-submitted.png#lightbox)

To review and publish an app update:

1. In the left navigation of the Teams admin center, go to **Teams apps** &gt; **Manage apps**.
2. Select the app name to go to the app details page, and then select **Update available** to review details of the update.

    [![Screenshot showing the app details page for an update.](media/custom-app-lifecycle-update-app.png)](media/custom-app-lifecycle-update-app.png#lightbox)
3. When you're ready, select **Publish** to publish the update. Doing this replaces the existing app, updates the version number, and changes the **Publishing status** to **Published**. All app permission policies and app setup policies remain enforced for the updated app.

    If you reject the update, the earlier version of the app remains published.

Keep in mind the following:

- When an app is approved, any one can submit an update to the app. This means other developers, including the developer who originally submitted the app, can submit an update to the app.
- When a developer submits an app and the request is pending, only that same developer can submit an update to the app. Other developers can submit an update only after the app is approved.

For more information about using the Graph API to update apps, see [here](/en-us/graph/api/teamsapp-update?view=graph-rest-1.0&amp;tabs=http&amp;preserve-view=true).