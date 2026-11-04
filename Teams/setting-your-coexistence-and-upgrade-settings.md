---
layout: Conceptual
title: Set your coexistence and upgrade settings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/setting-your-coexistence-and-upgrade-settings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: upgrade-and-migration-article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
ms.date: 2018-05-11T00:00:00.0000000Z
search.appverid: MET150
description: Learn about how to set coexistence and upgrade settings for all users in your organization at once, or for a single or set of users in your organization.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
locale: en-us
document_id: ffbf0bfd-c15e-b10b-0cc9-6a27ac1e6634
document_version_independent_id: 58575371-9e09-fadb-76f6-7491df8580a3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/setting-your-coexistence-and-upgrade-settings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: setting-your-coexistence-and-upgrade-settings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/setting-your-coexistence-and-upgrade-settings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: d6e03ca5-06d4-4662-6e52-a053997b7a83
---

# Set your coexistence and upgrade settings - Microsoft Teams | Microsoft Learn

When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users. You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization. Note that older versions of Skype for Business clients may not honor these settings. For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](/en-us/skypeforbusiness/software-updates).

You can get a better understanding of the modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability) or [Coexistence with Skype for Business](coexistence-chat-calls-presence).

Important

Having the option to upgrade doesn’t necessarily mean your organization is ready for this change. For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.

## Set upgrade options for all users in your organization

**Using the Microsoft Teams admin center**

1. In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Teams** &gt; **Teams upgrade settings**.
2. At the top of the **Teams upgrade** page, modify the following options as desired.

    - Set the **Coexistence** mode.

        - **Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.
        - **Skype for Business only** - Use this setting if you want your users to only use Skype for Business.
        - **Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).
        - **Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.
        - **Teams only** - Use this setting if you want your users to use only Teams. Note that even with this setting, users can still join meetings hosted in Skype for Business.

            Important

            You can only assign TeamsOnly mode to the entire tenant after both of the following steps have been completed:

            - All on-premises users have been moved to Teams Only using Move-CsUser in the Skype for Business Server on-premises toolset.
            - You have updated any Skype for Business DNS records to point to Microsoft 365.

            For more detail, see [Disable your hybrid configuration to complete migration to Teams Only](/en-us/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
    - Set **Notify Skype for Business users that Teams is available for upgrade**. If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.
    - Set the **Preferred app for users to join Skype for Business meetings**. This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.

        - **Skype Meetings app**
        - **Skype for Business with limited features**
    - Set whether to **Download the Teams app in the background for Skype for Business users**. This setting silently downloads the Teams app for users running Skype for Business on Windows. It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.
3. Click **Save** after you make your changes.

## Set upgrade options for a single user in your organization

**Using the Microsoft Teams admin center**

1. In the left navigation, go to **Users** &gt; **Manage users**, and then select the user from the list.
2. On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.
3. You can set the **Coexistence mode**. Modes other than Teams Only can only be applied to users homed in Skype for Business Server on-premises, and conversely only users homed in the cloud can have TeamsOnly mode. Choose from the following options:
    - **Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.
    - **Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.
    - **Skype for Business only** - Use this setting if you want the user to use Skype for Business.
    - **Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).
    - **Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.
    - **Teams only** - Use this setting if you want the user to use only Teams. The user will still be able to join Skype for Business meetings.
4. If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon. You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.
5. Click **Save** after you make your changes.

### Related topics

[Plan the journey](upgrade-plan-journey)

[Understand the coexistence and upgrade journey for Skype for Business and Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams)

[Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype)

[Decommission your on-premises Skype for Business environment](/en-us/skypeforbusiness/hybrid/decommission-on-prem-overview)