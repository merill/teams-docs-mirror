---
layout: Conceptual
title: Use the Network planner for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/network-planner
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.date: 2026-05-26T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: snchatur
audience: admin
description: Admin can learn how to use the Network Planner to determine network requirements for Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
locale: en-us
document_id: 18f0a6ad-85d4-1d26-2e7c-496f0699e418
document_version_independent_id: c1283d82-a691-19aa-9fb9-be51031f0f39
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/network-planner.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: network-planner
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/network-planner.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 7553c3d4-a3a1-f5d9-7801-ad41fc334805
---

# Use the Network planner for Microsoft Teams - Microsoft Teams | Microsoft Learn

Network Planner is a new tool that is available in the Teams admin center. It can be found by going to **Planning** &gt; **Network planner**. In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization. When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.

![Screenshot of Network planner.](media/network-planner.png)

Network planner allows you to:

- Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams Rooms System).

    Note

    The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns. However, you can create up to three custom personas in addition to the three recommended personas.
- Generate reports and calculate bandwidth requirements for Teams usage.

To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.

## Create a custom persona

Follow these steps to create a custom persona:

1. Go to the Network planner in the Microsoft Teams admin center.
2. On the **Personas** tab, click **+ Custom persona**.
3. In the **New custom persona** pane, add a name and description for the new persona.
4. Select the permissions that this persona will use within the organization.
5. Click **Save**.

## Build your plan

Follow these steps to begin building your network plan:

1. Go to the Network planner in the Microsoft Teams admin center.
2. On the **Network Plan** tab, click **Add a network plan**.
3. Enter a name and description for your network plan. The network plan will appear in the list of available plans.
4. Click the plan name to select the new plan.
5. Add sites to create a representation of your organization's network setup.

    Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else. Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections. For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.

    To create a site:

    1. Add a name and description for your site.
    2. Under **Network settings**, add the number of network users at that site (required).
    3. Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).

    Note

    You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.

    1. Click **Save**.

## Create a report

After you add all sites, you can create a report, as follows.

1. On the **Reports** tab, click **Start a report**.
2. For each site you create, distribute the number of users across the available personas. If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).
3. After you complete the distribution, click **Generate report**.

    The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:

    - A table with individual calculations will display bandwidth requirements for each permitted activity.
    - An additional view will show the overall bandwidth needs with recommendations.
4. Click **Save**. Your report will be available on the reports list for later viewing.

## Example scenario

For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://download.microsoft.com/download/e/e/9/ee9db569-fdcc-4e87-bbf8-215f7760bc53/network-planner-how-to.pptx) (English only).