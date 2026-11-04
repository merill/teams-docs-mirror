---
layout: Conceptual
title: Microsoft Teams apps permissions and consent - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/app-permissions
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
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- m365initiative-voice
- M365-collaboration
- Tier1
search.appverid: MET150
ms.date: 2026-05-22T00:00:00.0000000Z
ms.reviewer: Orion.OMalley
description: Understand permissions that Teams apps request to access your organization and user information.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: cd0f81b0-eb71-1c7c-aa8c-25f114e57fd0
document_version_independent_id: 9103c060-c536-b3cc-170a-10c2fbfbc834
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/app-permissions.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-permissions
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/app-permissions.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/1433a524-c01f-4b87-beab-670c040dea4f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/312f1f05-a431-4193-8a4d-e6245d5966de
platformId: b11ca56e-ed42-291f-271b-1f8d59bf90bc
---

# Microsoft Teams apps permissions and consent - Microsoft Teams | Microsoft Learn

Depending on their functionality, Teams apps might access your user's or your organization's information to work as intended.

- Some apps don't seek access to organization's information and hence don't require any approval. Users can use such apps without admin approval or consent as organization's information is secured from such apps.
- Some apps require your organization's or user's information to work or to process the information. Such apps can't work unless you allow such an app to access your org's information.

You must evaluate the compliance, security, and data handling information of an app and also understand the permissions requested by the app before you allow an app to be used by your users. To do so, you need to understand about permissions, consent, and the controls available to you. For more information on security, compliance, and privacy information, see [App compliance program for security, data handling, and privacy](overview-of-app-certification).

Permissions enable apps to access privileged resources and act on behalf of the user. This capability allows developers to create rich features in apps that boost user productivity. You must clearly understand the permissions, their scope, and implications. In Microsoft Teams admin center, you can review app permission risks and privilege levels. You also see details about what each app can do in Teams. For more information, see View app permission risks and privilege levels.

## How apps access organization's information using permissions

Teams provides safeguards so that your organization's or user's information can't be accessed without your consent. For an app to access any information, the following actions must happen:

1. App developers declare permissions and [app capabilities](apps-in-teams#understand-app-capabilities) when they create apps.
2. Admins understand and analyze the permissions required by the app in admin portals.
3. Data access is granted in two ways. When you add the app to Teams, it gains access to some basic capabilities that might include access to basic information. When you grant consent, the app receives access to some data of user and organization or both, based on app permissions that it requested consent for.

## Understand data access by apps and the required permissions

An application can access an organization's information in the following two ways:

- **Delegated access**: An application accesses the resource on behalf of the user. This access requires delegated permissions. The application can access only the information that the user can access.
- **Application access**: An application acts on its own with no user signed in, when it's undesirable to have a specific user signed in or when the data required can't be scoped to a single user. This access requires application permissions. If granted consent, an application can access data associated with the permission.

| Admin consideration | Delegated permissions | Application permissions |
| --- | --- | --- |
| How can apps access information | On behalf of a signed-in user. | On their own, using their own identity. |
| What information is accessed | Permissions that app is granted consent to and the information associated with that permission that the signed-in user has access to. | Any info that a consented permission is associated with |
| What roles can consent | Admins or users or group owners depending on Microsoft Entra ID configuration | Only admins |
| Can users consent | Users can consent depending on Microsoft Entra ID configuration | Only admins can consent |

For each app, you can see its permissions in the app details page in the admin center.

| App permission type | Access context | Declaration source | When is consent required? | Who can consent? |
| --- | --- | --- | --- | --- |
| Microsoft Entra ID for Graph and legacy endpoint access | Delegated | Microsoft Entra ID | App sign-in | Global Admin, Cloud Admin, and Application Admin |
| Microsoft Entra ID for Graph and legacy endpoint access | Application | Microsoft Entra ID | App sign-in | Global Admin, Cloud Admin, and Application Admin |
| RSC for information of teams, chats, and users | Delegated | App manifest file | Adding app to a team, chat, meetings | Resource owner |
| RSC for information of teams, chats, and users | Application | App manifest file | Adding app to a team, chat, meetings | Resource owner |
| Other permissions and data access | Delegated via SDKs | Manifest properties define it | Add app in a client | Consent is implied at install |

Use a lower privilege role to accomplish tasks where possible. Use Global Administrator role only when necessary.

## Where can admins see all permissions of an app

Go to the **Permissions** tab of the app details page to view all the required permissions, accesses, and privilege levels. You can also download all the permissions in a .csv file for further analysis.

[![Screenshot showing the  Permissions tab on the app details page and the option to download the Excel file.](media/app-permissions-details.png)](media/app-permissions-details.png#lightbox)

To understand what apps can do in Teams, see Basic capabilities and interactions with user and data accessed by apps. To learn how you can permit the use of an app, see [grant, and manage consent to Teams app permissions](manage-consent-app-permissions).

## View app permission risks and privilege levels

To view the permission privilege information, follow these steps:

1. Sign in to [Microsoft Teams admin center](https://admin.teams.microsoft.com/).
2. Go to [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) to view and govern apps in your organization’s catalog and select any particular app.
3. Use the **Privilege level** column to see each app's privilege level. Sort apps by the desired level.

    [![Screenshot showing the privilege level info column.](media/privilege-level-info-column.png)](media/privilege-level-info-column.png#lightbox)

    The three types of app privilege levels are as follows:

    - **High**: The app has at least one high-privileged permission.
    - **Medium**: The app has least one medium privileged permission and no high-privileged permission.
    - **Low**: The app has no high or medium privileges.

    The overall privilege level for an app is computed using the same principle as App Governance in MDA.

    Alternatively, select any app under the **All apps** section and go to the **Permissions** tab to view and review the required permissions.

    [![Screenshot showing the individual app's permission tab.](media/permissions-tab-individual-app.png)](media/permissions-tab-individual-app.png#lightbox)

    Note

    Permission risk levels and privilege level enhancements don't apply to first-party (Microsoft) apps.

## Microsoft Entra ID permissions

Microsoft Graph lets developers access your organization's Microsoft 365 information and data but only with the appropriate Microsoft Entra ID permissions. An app declares these permissions upfront and admins must consent to these permissions before the app can access the info. If you grant admin consent to such a permission in a Teams app, then all allowed users of your org can use the app and let the app access org's information. These permissions are defined in Microsoft Entra ID portal.

App developers choose appropriate permissions from a wide variety of Microsoft Graph APIs so that the apps get the necessary information to work. Before you grant consent to these permissions, you can view the specific permissions requested by an app. It helps you evaluate the impact of granting consent to an app's permissions. To view the Microsoft Entra ID permissions, follow these steps:

1. Access Teams admin center and open the **Teams apps** &gt; **[Manage apps](https://admin.teams.microsoft.com/policies/manage-apps)** page.
2. Search for the required app and select its name to open the app details page.
3. Select **Permissions** tab and select **Review permissions and consent**.
4. In the dialog, view the permissions required by the app. For more information about the information available in the dialog, see [information available in the consent prompt](/en-us/entra/identity-platform/application-consent-experience).

    ![Screenshot of permissions requested by an app.](media/app-consent-entra-dialog.png)

A complete list of all the possible permissions is documented in the [Microsoft Graph permissions reference](/en-us/graph/permissions-reference).

## Resource-specific consent permissions

Resources in Teams can be a team, a chat, or a user. Use these permissions to let apps access the information of only a specific resource. With RSC permissions, an app doesn't have to request access to org-wide information and can limit the scope of its access. Define these RSC permissions in the app's manifest file. Only users who have access to the resources can consent to these permissions. Developers define these permissions in the app itself, in the app manifest file.

RSC permissions let users give consent to apps for scope-specific information. Such consent lets apps access and modify only a team's or a chat's information. Such an app can't access the information of a chat or a team in which it isn't added. Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.

RSC permissions limit the scope of the app permissions to a specific resource as opposed to org-wide Graph permissions that can let apps access org-wide information. The resources on which RSC permissions can apply are chats and meetings, teams and channels, and users.

Define RSC permissions in the app manifest and not in Microsoft Entra ID. You grant consent to RSC permissions when you add the app to a team. For more information, see [Resource-specific consent (RSC)](/en-us/microsoftteams/platform/graph-api/rsc/resource-specific-consent).

To view RSC permissions for an app, follow these steps:

1. Access Teams admin center and go to **Teams apps** &gt; **[Manage apps](https://admin.teams.microsoft.com/policies/manage-apps)**.
2. Search for the app you want, select the app name to go to the app details page, and then select the **Permissions** tab.
3. Under **Resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.

## What can apps do in Teams

When developers create Teams apps, they use some capabilities defined in the development framework. These capabilities are high-level functionalities that apps can have. For example, an app can contain a bot that converses with the user. When an app uses a capability, it automatically gets some basic privileges. For example, if the app containing a bot is allowed for a user, then the bot can send and receive messages. These privileges exist in apps based on what functionality the app developer added to an app and aren't permissions that require consent to be effective. Developers don't explicitly define these permissions but these permissions are implicitly added when developers build any app functionality.

As an admin, you manage Teams apps and not their capabilities. [Teams apps have capabilities](apps-in-teams#understand-app-capabilities) that allow apps to accomplish their core use case and accomplish some tasks. The [capabilities are provided by SDKs](/en-us/microsoftteams/platform/concepts/build-and-test/tool-sdk-overview) and the consent is implied when the app is installed. The tasks that apps can accomplish that are associated with capabilities are different from the permissions that require consent by an admin. You as an admin must consider what an app can do and how it interacts with users based on the following capabilities.

- Bots and Messaging extensions
- Tabs
- Connectors
- Outgoing webhooks

Note

Apps might not use all the following capabilities, unless the app is a complex app catering to multiple use cases. The tasks that app can do depend on the capabilities used in it by the app developer.

### Bots and messaging extensions

Consider the following types of user interaction, required permissions, and data access by bots and messaging extensions:

- A bot can receive messages from users and reply to them. Bots only receive messages in chats where users explicitly mention a bot by its name. This data leaves the corporate network.
- After a user sends a message to a bot, the bot can send the user direct or proactive messages at any time.
- Some bots only send messages. They're called notification-only bots and the bot doesn't offer a conversational experience.
- A bot added to teams can get a list of names and IDs of the channels in a team.
- When using it in a channel, in a personal chat, or a group chat, the app's bot can access basic identity information of team members. The information includes first name, last name, user principal name (UPN), and email address.
- It's possible for an app's bot to send direct or proactive messages to team members even if they don't interact with the bot.
- Depending on settings and functioning of an app that is a bot, it can send and receive files in personal chat only. It isn't supported for group chats or channels.
- Bots only have access to teams to which the bots are added or to users who add the bots app.
- When a user converses with a bot, if the bot stores the user's ID, it can send the user direct messages at any time.
- If necessary, a user or an admin can block a bot. Microsoft can also remove a bot from the store. [App verification and validation checks](overview-of-app-validation) ensures high quality apps are available in Teams store and that bots don't spam their users.
- A bot can retrieve and store basic identity information for the team members the app is added to, or for individual users in personal or group chats. To get further information about these users, the bot must require them to sign in to Microsoft Entra ID.
- Bots can retrieve and store the list of channels in a team. This data leaves the corporate network.
- By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in. As soon as the user signs in, the bot has an access token with which it can perform other tasks. The tasks depend on the bot and where the user signs in: a bot is a Microsoft Entra app registered at `https://apps.dev.microsoft.com/` and can have its own set of permissions.
- When a file is sent to a bot, the file leaves the corporate network. Sending and receiving files requires user approval for each file.
- Bots are informed whenever users are added to or deleted from a team.
- Bots don't see users' IP addresses or other referrer information. All information comes from Microsoft. (There's one exception: if a bot implements its own sign-in experience, the sign-in UI sees users' IP addresses and referrer information.)
- Messaging extensions, on the other hand, can see users' IP addresses and referrer information.

Note

- If a bot has its own sign-in, there's a different consent experience the first time the user signs in.
- Users can search apps with the `botId` that was available in the app. While users can view the app name, they can't interact with such bots.

### Tabs

A tab is a website running inside Teams. It can be a tab in a meeting, a chat, or a channel.

Consider the following types of user interaction or data access for Tabs:

- Users opening a tab in a browser or in Teams is exactly the same. The website itself can't access any organization's information on its own.
- A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Microsoft Entra Object ID for the current user, the ID of the Microsoft 365 group in which it resides (if it's a team), the tenant ID, and the current locale of the user. However, to map these IDs to a user's information, the tab must make the user sign in to Entra ID.

### Connectors

A connector posts messages to a channel when events in an external system occur. The required permission for Connectors is the ability to post messages in a channel. An optional permission for Connectors is the permission to reply to a message. Some connectors support actionable messages, which allow users to post targeted replies to the connector message. For example, by adding a response to a GitHub issue or adding a date to a Trello card. Consider the following types of user interaction, required permissions, and data access by Connectors:

- The system that posts connector messages doesn't know who it's posting to or who receives the messages. No information about the recipient is disclosed. Microsoft is the actual recipient and not the organization. Microsoft does the actual posting to the channel.
- No data leaves the corporate network when Connectors post messages in a channel.
- Connectors that support actionable messages also don't see IP address and referrer information; Microsoft receives this information and then routes it to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.
- Each time a Connector is configured for a channel, a unique URL for that connector instance is created. If you delete that connector instance, you can't use the URL.
- Connector messages can't contain file attachments.
- Treat the Connector instance URL as secret or confidential. Anyone who has the URL can post to it. If necessary, team owners can delete the connector instance.
- If necessary, an administrator can prevent new Connector instances from being created and Microsoft can block all usage of a Connector app.

### Outgoing webhooks

Team owners or team members create outgoing webhooks. Outgoing webhooks receive messages from users and reply to them. Consider the following types of user interaction, required permissions, and data access by outgoing webhooks:

- Outgoing webhooks are similar to bots but have fewer privileges. They must be explicitly mentioned, just like bots.
- When you register an outgoing webhook, the process generates a secret. This secret allows the outgoing webhook to verify that the sender is Teams as opposed to a malicious attacker. Keep this secret; anyone who has access to it can impersonate Teams. If the secret is compromised, delete and re-create the outgoing webhook to generate a new secret.
- Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.
- Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, and they can't do anything else that bots can do except receive and reply to messages.