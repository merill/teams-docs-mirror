---
layout: Conceptual
title: User requests for admins - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/user-requests-approve-apps
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal
ms.author: vikasalmal
manager: prkosh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 2026-07-06T00:00:00.0000000Z
ms.collection:
- M365-collaboration
- tier2
- highpri
ms.reviewer: eddieqiao
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Learn how to manage and configure user request for approval of the apps that are blocked in an organization.
ms.localizationpriority: high
locale: en-us
document_id: f07d46fc-fafd-b775-be7c-667d1e090565
document_version_independent_id: f07d46fc-fafd-b775-be7c-667d1e090565
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/user-requests-approve-apps.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: user-requests-approve-apps
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/user-requests-approve-apps.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: c00f7ab0-3673-23bf-7957-02630308f330
---

# User requests for admins - Microsoft Teams | Microsoft Learn

Apps are essential for productivity and collaboration in Teams. However, some apps may not meet your organization's security and compliance requirements. To ensure that users can only use apps that are approved by your organization, you can review them for approval and blocking.

The apps that are blocked in your organization may affect user productivity and collaboration. Users can't use blocked apps but can view such apps and app information in the Teams store. Teams lets users request an approval from admins to allow the usage of blocked apps. You can evaluate these apps and choose to approve blocked apps as well.

The app approval functionality provides you with a signal about the demand for an app within your organization. You can easily view the aggregate number of requests for each requested app. It helps you make an informed decision about which apps to evaluate for allowing.

Here are the options for handling user requests:

- When a user requests an app, the request is sent to the Teams admin center. You can view user requests and approve and deny requests.

    ![Screenshot showing the option to request an admin to approve a blocked app.](media/user-request-blocked-apps.png)
- Admin center lets you optionally configure the user request experience that is best suited for your organization. You can provide a custom message for additional instructions that displays for each blocked app, and/or a custom URL that will route users to the external link.

    ![Screenshot showing the user experience for apps in store when an admin redirects the allow app request URL to an org-specific URL.](media/user-request-blocked-apps-redirected.png)

Note

The feature isn't supported in Government Community Cloud (GCC), GCC-High, and Department of Defense (DoD) tenants. It isn't supported for custom apps.

## View user requests in Teams admin center

You can view user requests in the Teams admin center from the following locations:

- Dashboard widget
- Manage apps widget
- All apps table (Manage apps page)
- User requests tab (App details page)

### Dashboard widget

On your [Teams admin center dashboard](https://admin.teams.microsoft.com/dashboard), the **Review user app requests**\* widget displays requested apps.

1. Click **See all app requests** to land on the **Manage apps** page with the **Most requested apps** card.

    [![Screenshot showing the Manage apps page with the Most requested apps card.](media/tac-dashboard-review-user-app-requests.png)](media/tac-dashboard-review-user-app-requests.png#lightbox)
2. Click **See all app requests** to view the list of requested apps.

\*If you are unable to see the **Review user app requests** widget, you can add it to your dashboard by clicking the ![](media/edit-icon.png) icon.

### Manage apps widget

Any request from users for an app lands on a **Most requested app** card on your [Teams admin center dashboard](https://admin.teams.microsoft.com/dashboard).

[![Screenshot showing the user request review option on the admin center dashboard.](media/tac-dashboard-user-requests.png)](media/tac-dashboard-user-requests-large.png#lightbox)

Select **See all app requests** to view the list of requested apps. You can sort the app list by name, app status or the number of requests. The list is sorted in descending order by default.

You can also click **Review** to start acting on the user request.

### All apps table (Manage apps page)

On the [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) page, you can view the list of requested apps under the **All apps** table. The **Filter by action** option is set at **All** by default.

[![Screenshot shows the all apps table on the Manage apps page.](media/tac-dashboard-all-apps.png)](media/tac-dashboard-all-apps.png#lightbox)

You can change the **Filter by action** option to **Apps requests** to view the list of requested apps. You can sort the app list by name, app status or the number of requests. The list is sorted in descending order by default.

When you change the **Filter by action** option to **Apps requests**, a new option appears. You can use this to set up a rule for a notification to be sent when a user requests an app. For more information, see Set up notifications for user requests.

### User requests tab (App details page)

You can view the app requests and email contact of each requester of an app by going to the **User requests** tab in the app details page.

[![Screenshot showing the user requests tab in the app details page and the admin actions needed to allow an app.](media/user-request-allow-apps-options.png)](media/user-request-allow-apps-options.png#lightbox)

## Set up notifications for user requests

On the **Manage apps** page, you can set up a rule to receive notifications when a user requests an app. A user can also trigger a similar flow from the **Rules** page.

To set up the notification, follow these steps:

1. Navigate to **See all app requests**. A list of requested apps appears, along with a notification **To make it easier to see app requests, set up a Teams channel alert in Rules**.

    ![Screenshot shows the notification for admins to set up alerts on a channel whenever user requests for an app.](media/tac-dashboard-set-up-app-request-alerts.jpg)
2. Select **Set up alert**. The **Rules** page appears with a list of existing rules.

    [![Screenshot shows the Rules page with a list of existing rules.](media/tac-dashboard-add-rule.png)](media/tac-dashboard-add-rule.png#lightbox)
3. Select **Requests to use an app**. The **App requests** rule page appears. Here you can set up the rule conditions to receive new app notifications in a Teams channel.

    [![Screenshot shows the App requests rule page where you can set up the conditions to receive new app notifications in a Teams channel.](media/tac-dashboard-add-rule-app-request-page.png)](media/tac-dashboard-add-rule-app-request-page.png#lightbox)

Once your rule is set up, you receive notifications in the specified Teams channel whenever a user requests an app. The notification includes the name of the requested app and the number of requests received for that app.

[![Screenshot shows the notification in a Teams channel for an admin when a user requests an app.](media/tac-dashboard-notification-on-channel.png)](media/tac-dashboard-notification-on-channel.png#lightbox)

## Act on the user requests to approve or deny available apps

After you evaluate an app, you can either approve or deny the requests.

### Approve a single request

To approve a single request for an app:

1. On the **Manage apps**, **Most requested apps** card, select **Review**. The app details page appears with the **User requests** tab highlighted. This tab lists the names and email addresses of all requesters for the app.

    The available actions at this stage are **Approve all** and **Deny all**.
2. Select the available radio button for the request you want to approve. The available actions at this stage changes to **Approve** and **Deny**.

    [![Screenshot shows the option to approve a single request for an app.](media/tac-dashboard-approve-single-request.png)](media/tac-dashboard-approve-single-request.png#lightbox)
3. Select **Approve** to approve the request.

### Approve multiple requests

To approve multiple requests for an app, repeat the above steps. However, select the available radio buttons for specific requests which you want to approve before selecting **Approve**.

[![Screenshot shows the option to approve multiple requests for an app.](media/tac-dashboard-approve-multiple-requests.png)](media/tac-dashboard-approve-multiple-requests.png#lightbox)

### Approve all requests

To approve all requests for an app or approve the app for the entire organization:

1. On the **Manage apps**, **Most requested apps** card, select **Review**. The app details page appears with the **User requests** tab highlighted. This tab lists the names and email addresses of all requesters for the app.

    The available actions at this stage are **Approve all** and **Deny all**.
2. Select **Approve all**. A popup appears with the options for you to approve all the requests or approve the app for the entire organization.

    - If you select **Approve**, all the app requests are approved and the available list is cleared.

        [![Screenshot shows the option to approve all requests for an app.](media/tac-dashboard-approve-all.png)](media/tac-dashboard-approve-all.png#lightbox)

        App availability changes to **Select users and groups**.

        [![Screenshot shows the option to approve a request for select users and groups.](media/tac-dashboard-approve-request-for-select-users-and-groups.png)](media/tac-dashboard-approve-request-for-select-users-and-groups.png#lightbox)
    - If you select **Approve for the organization**, the app is approved for all users in your organization and the available list is cleared.

        App availability changes to **Everyone**.

        [![Screenshot shows the option to approve a request for the entire organization.](media/tac-dashboard-approve-request-for-organization.png)](media/tac-dashboard-approve-request-for-organization.png#lightbox)

After you approve an app, the following happens:

- Users can see the **Add** option for the approved app in the Teams app store.
- Users get a notification on their Teams when their request is approved.
- The **Users and groups** tab will either show 'everyone' if approved for your org, or the general group that all users are added to once their request is approved.

### Deny a single request for an app

To deny a single request for an app:

1. On the **Manage apps**, **Most requested apps** card, select **Review**. The app details page appears with the **User requests** tab highlighted. This tab lists the names and email addresses of all requesters for the app.

    The available actions at this stage are **Approve all** and **Deny all**.
2. Select the available radio button for the request you want to deny. The available actions at this stage changes to **Approve** and **Deny**.

    [![Screenshot shows the option to deny a single request for an app.](media/tac-dashboard-deny-single-request.png)](media/tac-dashboard-deny-single-request.png#lightbox)
3. Select **Deny** to deny the request.

### Deny multiple requests for an app

To deny multiple requests for an app, repeat the above steps. However, select the available radio buttons for specific requests which you want to deny before selecting **Deny**.

[![Screenshot shows the option to deny multiple requests for an app.](media/tac-dashboard-deny-multiple-requests.png)](media/tac-dashboard-deny-multiple-requests.png#lightbox)

### Deny all requests for an app

To deny all requests for an app:

1. On the **Manage apps**, **Most requested apps** card, select **Review**. The app details page appears with the **User requests** tab highlighted. This tab lists the names and email addresses of all requesters for the app.

    The available actions at this stage are **Approve all** and **Deny all**.
2. Select **Deny all**. The options to select **Deny** or **Cancel** the action appears.

    - If you select **Deny**, all the app requests are denied and the list is cleared.

    [![Screenshot shows the option to deny all requests for an app.](media/tac-dashboard-deny-all-requests.png)](media/tac-dashboard-deny-all-requests.png#lightbox)

    - If you select **Cancel**, you can review all requests individually.

After you deny an app, the following happens:

- Users can see the **Request approval** option for the denied app in the Teams app store.
- Teams informs the requesters that their request has been dismissed.
- Users can again request the same app to be allowed, after a few hours of you dismissing requests.

## Act on user requests to approve blocked apps

For apps which are blocked for an organization, in addition to approving requests, admins will need to unblock the apps to make them available and usable by users. If the request is approved, but the app remains in a blocked state, the user is unable to use the app.

### Approve a single request for a blocked app

1. On the **Manage apps**, **Most requested apps** card, select **Review**. The app details page appears with the **User requests** tab highlighted. This tab lists the names and email addresses of all requesters for the blocked app.

    The available actions at this stage are **Approve all** and **Deny all**.
2. Select the available radio button for the request you want to approve. The available actions at this stage changes to **Approve** and **Deny**.
3. Select **Approve**. A popup appears with the options **Approve and unblock** and **Approve and keep blocked**.

    - Select **Approve and unblock** to approve the request and unblock the app for the user. User is notified on Teams.

    [![Screenshot shows the option to approve a request and unblock the app.](media/tac-dashboard-approve-request-and-unblock-app.png)](media/tac-dashboard-approve-request-and-unblock-app.png#lightbox)

    - Select **Approve and keep blocked** to approve the request but keep the app blocked for the user. End user notifications are withheld until the app is unblocked.

    [![Screenshot shows the option to approve a request but keep the app blocked.](media/tac-dashboard-approve-request-but-keep-app-blocked.png)](media/tac-dashboard-approve-request-but-keep-app-blocked.png#lightbox)

### Approve all requests for a blocked app

The procedure and end result for approving all requests for a blocked app is similar to approving a single request for a blocked app. The only difference is that you select **Approve all** at step 2 instead of selecting a single request.

## Receive user requests on your custom webpage

Teams provides a default message for users to request approval to an app. You can modify the default setting to add a custom message with instructions, org-specific URL, or both. The modifications are displayed for each app in Teams store.

To configure a custom message and redirect users to an org-specific URL, follow the steps:

1. Sign into the Teams admin center and go to **Teams apps** &gt; [**Manage apps**](https://admin.teams.microsoft.com/policies/manage-apps).
2. At the upper-right corner, select **Org-wide app settings**.
3. To display a custom message or instruction in Teams store, enter a text message in text field under **User requests configuration**. The field has a limit of 300 characters.
4. To provide an org-specific URL to collect user requests, follow the steps:

    1. Turn on the **Redirect requests to external link** toggle.
    2. Provide your org-specific URL.

        ![Screenshot to toggle the customization of URL for the user requests in the Org-wide app settings UI.](media/user-request-config-org-wide-setting.png)
5. Select **Save**.

If you choose to use this custom method to receive requests, the methods to evaluate apps and govern the requested apps remain the same.

## Related article

- [Overview of how to manage third-party apps](manage-apps)