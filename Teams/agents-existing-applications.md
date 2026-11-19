---
layout: Conceptual
title: Manage recommended agents for existing applications in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/agents-existing-applications
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to review agent recommendations based on application sign-in activity and manage user access to recommended agents in the Teams admin center.
ms.topic: how-to
author: NickWalk
ms.author: nickwalk
manager: prkosh
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 2026-11-19T00:00:00.0000000Z
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: high
locale: en-us
document_id: cb3164ea-ca04-9336-234e-32ba33bf2dd5
document_version_independent_id: cb3164ea-ca04-9336-234e-32ba33bf2dd5
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/agents-existing-applications.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: agents-existing-applications
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/agents-existing-applications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: bfa4b772-c0d0-8256-811b-b89d1f5cd1fd
---

# Manage recommended agents for existing applications in Teams - Microsoft Teams | Microsoft Learn

Admins can now use agent recommendations in the Teams admin center to identify Teams apps associated with applications your users already access with their work accounts.

From the recommendations, you can make an app available or deploy it to users in your organization who accessed or signed in to applications using their work accounts outside Teams.

This helps you bring relevant apps into Teams so users can access the services they already use without switching between applications.

Note

Agent recommendations are turned off by default. To enable them, your organization must consent to sharing sign-in activity data. For more information, see Enable agent recommendations.

## Find agent recommendations

To find agent recommendations for existing applications in your organization:

1. Navigate to the Teams admin center.
2. In the left navigation, select **Teams apps** &gt; **Manage apps**.
3. In the **Filter by action** dropdown, select **Agents from applications used in your org**. A card titled **Agents from applications used in your org** appears at the top of the page and shows how many agents are available and how many users are active in the related applications.
4. Select **Review** on the card to see the list of recommended agents based on your users' sign-in activity.

## Enable agent recommendations

Agent recommendations are turned off by default. To generate recommendations, the Teams admin center uses sign-in activity data from Microsoft Purview Audit to identify applications that users in your organization access with their work accounts. You must consent to the use of this data before recommendations are generated. The data is used only to recommend Teams agents associated with applications already used in your organization.

To enable agent recommendations:

1. In the Teams admin center, go to **Teams apps** &gt; **Manage apps**.
2. Next:

- On the **Get relevant agent recommendations** card, select **Agree and unlock insights**.
- Alternatively, select the **Agents from applications used in your org** filter, and then select the option to opt in to agent recommendations.

[![Screenshot showing the option to enable agent recommendations in the Teams admin center.](media/enable-agent-recommendation.png)](media/enable-agent-recommendation.png#lightbox)

Note

You can change this setting at any time. To opt out of agent recommendations, go to **Manage apps** &gt; **Actions** &gt; **Org-wide app settings** &gt; **Privacy and data usage**. After you opt out, agent recommendations are no longer displayed.

## Review recommended agents

After you enable agent recommendations, the list shows Teams agents for applications that users in your organization actively sign in to but don't yet have access to in Teams.

The list provides the following details for each recommended agent.

| Column | Description |
| --- | --- |
| Name | The Teams agent or app. |
| App status | Whether the agent is unblocked or blocked in your organization. |
| User opportunity | The number of users who sign in to the application but don't have the agent available in Teams. Select the download icon to export the list of users. |
| Application name | The application that users sign in to with their work accounts. |

## Enable an agent for users

You can make a recommended agent available to everyone, specific users or groups, or users who recently accessed the related application.

To enable an agent:

1. In the recommended agents list, select the agent, and then select **Add users** to proceed to the **Users** step.
2. Select the users you want to:

- Install the agent for.
- Make the agent available to, so they can install it themselves.

[![Screenshot showing how to enable an agent for users in the Teams admin center.](media/enable-an-agent.png)](media/enable-an-agent.png#lightbox)

You can target specific users who accessed the related application in the last month.

1. Select **Next** to proceed to the **Permissions** step.
2. Review the required permissions and grant consent. If you're a Teams Administrator, ask a Global Administrator to grant consent.
3. On the **Review and finish** step, review your selections.
4. Select **Apply**. Your selections are applied, and the agent is enabled for the specified users. It might take a few hours for the changes to take effect.

## Enable users to be added automatically

When you select users who access an application in your organization, the Teams admin center creates a security group for those users. You can review the group on the **Review and finish** step and on the agent's **Users and groups** tab.

Note

These selections are added to the agent's existing availability and installation settings. Existing assignments aren't affected.

To automatically add future users to the group, select **Add new users to this group when they sign in to the application** on the **Review and finish** step for an app. The agent is then made available to or installed for those users based on your configuration.

Clear this option to limit the group to users identified when you configure the agent.

**You can turn off automatic addition at any time**. In the Teams admin center, go to **Manage apps** &gt; Select the app &gt; **Users and Groups** tab. Turn off automatic addition to prevent future users who sign in to the related application from being added automatically.