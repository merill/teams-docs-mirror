---
layout: Conceptual
title: Manage Microsoft 365 connectors and custom connectors - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/m365-custom-connectors
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
ms.date: 2026-04-13T00:00:00.0000000Z
ms.collection:
- M365-collaboration
ms.reviewer: vivg
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn how connectors keep your team updated by frequently delivering content and updates directly into a Teams channel for services you use.
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: 76456782-494f-0c6c-11d6-19032e3e498c
document_version_independent_id: 76456782-494f-0c6c-11d6-19032e3e498c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/m365-custom-connectors.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: m365-custom-connectors
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/m365-custom-connectors.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1ae5c491-970a-4062-8301-6336e69f9026
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/f2c3e52e-3667-4e8a-bf11-20b9eaccdc8c
platformId: 20b23c77-b45d-b4b2-d5a2-f42e7744bc04
---

# Manage Microsoft 365 connectors and custom connectors - Microsoft Teams | Microsoft Learn

Important

Microsoft 365 Connectors (previously called Office 365 Connectors) are nearing deprecation, and the creation of new Microsoft 365 Connectors will be blocked soon. For more information on the deprecation schedule and how the Workflows app provides a more flexible and secure experience, see [retirement of Microsoft 365 connectors within Microsoft Teams](https://devblogs.microsoft.com/microsoft365dev/retirement-of-office-365-connectors-within-microsoft-teams/).

**How can you create a webhook in Teams?** To automatically post to a chat or channel when a webhook request is received, use the predefined workflow templates or create a workflow from scratch using the **When a Teams webhook request is received** trigger. For more information, see [send messages in Teams using incoming webhooks](https://support.microsoft.com/en-us/office/send-messages-in-teams-using-incoming-webhooks-323660ec-12ca-40b1-a1d3-a3df47e808c4).

For more information about the When a Teams webhook request is received trigger, see [Microsoft Teams - Webhook](/en-us/connectors/teams/?tabs=text1%2Cdotnet).

**If you've already built Office 365 Connectors:**

- Create a Power Automate connector: Power Automate enhances the widely used Workflows apps in Teams. It's the scalable and secure approach to transmit data programmatically into and out of Teams. If you adopt this method, you can create workflow templates for posting alerts from your product to Teams channels. This approach simplifies user adoption of the new method. For more information, see [Power Automate for enterprise developers, ISVs, and partners](/en-us/power-automate/developer/dev-enterprise-intro).
- Update your Teams app: You can enhance your current Teams app. For example, you can enable users to set up proactive messages based on trigger events within your system. For more information, see [how bots can post to channels through proactive messages](/en-us/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?tabs=dotnet).

**Known issues**

- Workflows app can post as a flow bot in shared channels. Support for posting as a flow bot in private channels is under development. Workflows can currently post messages on behalf of a user.
- Workflows support both Adaptive Cards and Message Card format (button rendering won't be supported). You can choose to convert Message Cards to Adaptive Card, see how to [convert connector message card format to Adaptive Card](https://github.com/OfficeDev/Microsoft-Teams-Samples/tree/main/tools/message-card-to-ac-transformation).

**Limitations**

Workflows are linked only to specific users (referred to as owners of the workflow) and not to a Teams team or channel. Workflows can become orphan flows in the absence of an owner if no co-owners assigned. To maintain continuity in the business process automated by the flow, admins can add one or more co-owners and grant them full control over the workflow. They can also add authentication for connections, if any, and enable the flow if it has been disabled. For more information, see [manage orphan flows](/en-us/troubleshoot/power-platform/power-automate/flow-management/manage-orphan-flow-when-owner-leaves-org).

Connectors in Microsoft Teams deliver content and service updates directly from third-party services into a Teams channel. By using connectors, users can receive updates from popular services such as Azure DevOps Services, Trello, Wunderlist, GitHub, and more. Connectors post these updates directly into the chat stream. This functionality makes it easy for all the team members to stay in sync and quickly receive the relevant information.

Teams and Microsoft 365 groups use connectors. You can use the same connectors in Teams and Microsoft Exchange.

Any team member can add a connector to a channel, if the team permissions allow it. The updates from the service, that the connector fetches information from, notifies all the team members.

Important

Developers can't register new connectors on the [Connector developer portal](https://aka.ms/connectorsdashboard).

## Update connectors URL

Note

This guidance applies only to existing connector configurations created before deprecation.

The [Teams connectors are transitioning](https://devblogs.microsoft.com/microsoft365dev/retirement-of-office-365-connectors-within-microsoft-teams) to a new URL to enhance security. During this transition, you may receive notifications to update your configured connector to use the new URL. We strongly recommend that you update your connector immediately to prevent any disruption to connector services.

This change is needed only for webhook-based Connectors such as Incoming Webhook and third-party connectors. The change isn't required for polling connectors such as RSS. You must update the URL for the connector to continue posting notifications into Teams after December 31, 2024.

Tip

We recommend that you note the URL that you update. After it is updated, you can’t view the previous URL anymore. An old URL can be useful to find and identify the systems still using it that you must update with the new URL.

To update the URL, follow these steps:

1. Go to the **Posts** tab in a Teams channel, select **Open channel details**, select **Manage channel**, select **Edit** under the **Connectors** option, and select **Configured** section. Check the existing connector connections on this page.

    ![Screenshot showing Manage channel.](media/m365-custom-connectors/managechannel3.png)![Screenshot showing Edit button.](media/m365-custom-connectors/edit2.png)

    ![Screenshot showing the configured section for the existing connector connections in a team.](media/manage-channel-option2.png)
2. Update only those connections that display `Attention required` under the **Manage** option.

    ![Screenshot showing the configured connections in a Teams channel that need attention.](media/connectors-attention-required.png)
3. Do one of the following:

    - For connectors that contain a webhook URL, select **Manage** and **Update URL**.

        ![Screenshot showing the option to update a webhook URL.](media/connectors-update-url.png)

        Note

        If the **Update URL** button is greyed out and you're unable to update the URL, create a new connector configuration.
    - For other types of connectors, remove the connector and recreate the connector configuration.
4. Use the updated URL or the new connection in the systems that were posting to the old URL. The Configure page displays that the URL is updated.

    ![Screenshot showing a confirmation after URL update.](media/connectors-url-updated.png)

To know more or to share more information with your app developers, see [Connectors deprecation information](/en-us/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).

## Enable or disable connectors in Teams

The Exchange Online PowerShell v2 module uses modern authentication and works with multifactor authentication (MFA) to connect to all Exchange related PowerShell environments in Microsoft 365. Admins can use Exchange Online PowerShell to disable connectors for an entire organization or a specific group mailbox. If a connector is disabled, it affects all users in that org or mailbox. You can't disable a connector for a few specific users.

Note

Admins can continue to manage connector availability for existing deployments until the feature is retired.

The organization setting overrides the group setting. For example, if an admin enables connectors for the group and disables the same connectors for the organization, then the connectors are disabled for the group. To enable a connector in Teams, [connect to Exchange Online PowerShell](/en-us/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&amp;preserve-view=true) using modern authentication with or without MFA.

To enable or disable a connector, execute the following commands in Microsoft Exchange Online PowerShell:

1. Open PowerShell as an administrator.
2. Use the command `Import-Module ExchangeOnlineManagement` to import the Microsoft Exchange module.
3. To disable connectors in your organization, use the command `Set-OrganizationConfig -ConnectorsEnabled:$false`.
4. To connect the admin account, use the command `Connect-ExchangeOnline -UserPrincipalName UPN -ExchangeEnvironmentName O365USGovGCCHigh`. Replace `UPN` with your User Principal Name.
5. To enable connectors for Teams, use the following commands. To disable connectors or actionable messages, set the value to `false` instead of `true` in the following commands.

    - `Set-OrganizationConfig -ConnectorsEnabled:$true`
    - `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
    - `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

For more information about PowerShell module exchange, see [Set-OrganizationConfig](/en-us/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&amp;preserve-view=true). To enable or disable Outlook connectors, [connect apps to your groups in Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab). To know more about User Principal Name (UPN), see [what is UPN in Microsoft 365](/en-us/entra/identity/hybrid/connect/plan-connect-userprincipalname#what-is-userprincipalname).

Note

It takes up to 24 hours for these changes to propagate.

## Publish connectors for your organization

To make a custom connector available to your organization's users, upload a custom connector app to your org's app catalog. Users within the org can install, configure, and use the connector in a team.

Important

Custom connectors are not available in Government Community Cloud (GCC), Government Community Cloud-High (GCCH), and Department of Defense (DOD) environments. This section applies only to previously published connectors. You can continue to manage and use existing custom connectors until the feature is retired. To use connectors in a team or a channel, open the More Options menu from the upper right corner of a channel. From the menu, select **Connectors** and then locate or search for the required connector. Configure the selected connector if necessary.

![Screenshot that shows add connectors to your channel in Teams from the More options in the upper right corner of the channel.](media/connectors-selection-ui.png)

## Use connectors in GCC or GCCH

Note

Use of connectors in GCC and GCCH environments is supported only for existing configurations until the feature is retired.

Connectors are disabled by default in the Government Cloud Community (GCC) and Government Community Cloud-High (GCCH) environments. To let your users use connectors in GCC or GCCH environments, follow these steps:

1. You must enable connectors in Teams.
2. To set the parameters, connect to the [Exchange Online PowerShell](/en-us/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&amp;preserve-view=true).
3. To use an incoming webhook in Teams, create a custom app using the following `manifest.json`. To use icons in the custom app, follow the [guidelines to create app icons](/en-us/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines#app-icons).

    ```json
    {
      "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",
      "manifestVersion": "1.5",
      "id": "203a1e2c-26cc-47ca-83ae-be98f960b6b2",
      "version": "1.0.0",
      "packageName": "com.incomingwebhook.microsoft",
      "developer": {
        "name": "Microsoft Corporation",
        "websiteUrl": "https://go.microsoft.com/fwlink/?linkid=837668",
        "privacyUrl": "https://privacy.microsoft.com/privacystatement",
        "termsOfUseUrl": "https://www.microsoft.com/servicesagreement"
      },
      "description": {
        "full": "The Incoming Webhook connector enables external services to notify you about activities that you want to track.",
        "short": "Send data from a service to your Microsoft 365 group in real time. "
      },
      "icons": {
        "outline": "outline.png",
        "color": "color.png"
      },
      "connectors": [
        {
          "connectorId": "203a1e2c-26cc-47ca-83ae-be98f960b6b2",
          "scopes": ["team"]
        }
      ],
      "name": {
        "full": "Incoming Webhook",
        "short": "Incoming Webhook"
      },
      "accentColor": "#FFFFFF",
      "permissions": ["identity", "messageTeamMembers"]
    }
    ```
4. [Upload the custom app](teams-custom-app-policies-and-settings#upload-a-custom-app-using-teams-admin-center) in your Teams admin center.

## Considerations when using Connectors in Teams

- Connectors are disabled by default in the Government Cloud Community (GCC) environments and Government Community Cloud-High (GCCH). To enable connectors, set the `ConnectorsEnabled` or `ConnectorsEnabledForTeams` parameters to `$true` with the `SetOrganizationConfig` cmdlet. To set the parameters, connect to the [Exchange Online PowerShell](/en-us/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&amp;preserve-view=true).
- If the user who added a connector to a team leaves the team, the connector continues to work.
- You can't configure new connections for the following connectors:

    - Aha!
    - Airbrake
    - Aircall
    - App Links
    - AppSignal
    - Beanstalk
    - Bitbucket
    - Buddy
    - Buildkite
    - CATS
    - Chatra
    - CircleCI
    - CodeShip
    - Constant Contact
    - GetResponse
    - Ghost Inspector
    - Groove
    - Heroku
    - Honeybadger
    - Intercom
    - Logentries
    - Mailchimp
    - Microsoft Forms
    - Opsgenie
    - PagerDuty
    - Papertrail
    - Pivotal Tracker
    - Raygun
    - Runscope
    - SatisMeter
    - Semaphore
    - Sentry
    - Simple In/Out
    - Stack Exchange
    - SUBVERSION
    - TestFairy
    - Travis CI
    - Trello
    - Uptodown
    - Userlike
    - Wrike
    - XP-Dev
    - Zendesk