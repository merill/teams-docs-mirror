---
layout: Conceptual
title: Upgrade from Skype for Business Online to Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinessonline
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
ms.reviewer: landerl
ms.date: 2018-06-07T00:00:00.0000000Z
description: Learn how to upgrade your organization to Microsoft Teams from a Skype for Business Online deployment.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
locale: en-us
document_id: e763c267-2c3a-190d-29e2-b5c81448fc10
document_version_independent_id: 98b73595-54ea-503c-ac3c-9df176543e9e
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/upgrade-to-Teams-execute-SkypeforBusinessOnline.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: upgrade-to-teams-execute-skypeforbusinessonline
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/upgrade-to-Teams-execute-SkypeforBusinessOnline.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: be527ecf-6787-a516-1d0a-a57c721c0050
---

# Upgrade from Skype for Business Online to Microsoft Teams - Microsoft Teams | Microsoft Learn

![Upgrade journey diagram, emphasizing Deployment and Implementation.](media/upgrade-banner-deployment.png)

This article is part of Deployment and Implementation stage of your upgrade journey. Before proceeding, confirm that you've completed the following activities:

- [Enlisted your project stakeholders](upgrade-enlist-stakeholders)
- [Defined your project scope](upgrade-define-project-scope)
- [Understood coexistence and interoperability of Skype for Business and Teams](teams-and-skypeforbusiness-coexistence-and-interoperability)
- [Chosen your upgrade journey](upgrade-and-coexistence-of-skypeforbusiness-and-teams)
- [Prepared your environment](upgrade-prepare-environment)
- [Prepared your organization](upgrade-prepare-organization)
- [Conducted a pilot](pilot-essentials)

Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams. You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.

Important

Skype for Business Online was retired on July 31, 2021. To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today. Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.

## Assign the coexistence and upgrade mode

You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session. You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.

For more information, see [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools).

## Upgrade all users to Teams at one time

Follow these steps to upgrade all of your users to Teams at one time.

### Step 1: Notify the users of the change (optional)

1. In the Microsoft Teams admin center, select **Teams** &gt; **Teams upgrade settings**.
2. Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.

### Step 2: Set the coexistence mode to TeamsOnly for the organization

1. In the Microsoft Teams admin center, select **Teams** &gt; **Teams upgrade settings**.
2. Select **Teams Only** mode from the **Coexistence mode** drop-down list.

## Upgrade users in stages

Follow these steps if you want to gradually upgrade your users to TeamsOnly.

### Step 1: Identify groups of users for upgrade

Often organizations may choose to upgrade their organizations in success waves of users. You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center. Alternatively, you may want to use PowerShell to more efficiently do this. Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.

### Step 2: Set notification for the users in the current upgrade wave (optional)

If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:

1. In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.
2. Select **Edit settings** in the upper left corner of the listview.
3. In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**. Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.

Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell. For more information, see [Grant-CsTeamsUpgradePolicy](/en-us/powershell/module/teams/grant-csteamsupgradepolicy).

### Step 3: Set the coexistence mode for users to Teams Only

When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.

If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:

1. In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.
2. Select **Edit settings** in the upper left corner of the listview.
3. In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.

Alternatively, you may find it easier to upgrade groups of users at once using PowerShell. For more information, see [Grant-CsTeamsUpgradePolicy](/en-us/powershell/module/teams/grant-csteamsupgradepolicy).

### Step 4: Repeat steps 1-3 for successive waves of users

As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to more users.

## Phone System and PSTN connectivity options

Phone System with Teams is supported after the user is in TeamsOnly mode. (If the user is in Islands mode, Phone System is only supported with Skype for Business.)

### PSTN connectivity options

When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:

- A user in Skype for Business Online, with a Microsoft Calling Plan. Upon upgrade, this user will continue to have a Microsoft Calling plan. This is the simplest scenario requiring only a couple of steps. For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations#from-skype-for-business-online-with-microsoft-calling-plans).
- A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition. The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality. For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations#from-skype-for-business-online-with-on-premises-voice).