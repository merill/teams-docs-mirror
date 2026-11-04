---
layout: Conceptual
title: Evaluate third-party apps using security and compliance requirements - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/org-trust-standard
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: NickWalk
ms.author: nickwalk
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
ms.date: 2026-10-14T00:00:00.0000000Z
ms.reviewer: Orion.OMalley
description: Understand how admins can configure evaluation score settings and assess third-party apps using tenant-defined security and compliance requirements.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: b8eaaf0e-b610-6af0-4542-0b282edfecab
document_version_independent_id: b8eaaf0e-b610-6af0-4542-0b282edfecab
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/org-trust-standard.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: org-trust-standard
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/org-trust-standard.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: caaf76c7-8c47-bdaf-ee5c-e24f1e5f5158
---

# Evaluate third-party apps using security and compliance requirements - Microsoft Teams | Microsoft Learn

Microsoft Teams admin center provides admins with security, compliance, permission related information for third-party apps to help assess whether an app or agent meets organizational requirements. To make this evaluation easier and more consistent, admins can define an organization’s app approval criteria and use it to evaluate apps or agents before allowing them in their tenant.

The organization’s app approval criteria lets admins select the security, compliance, and permission related requirements that matter most to their organization and see how apps or agents measure up against those requirements. With this admins can quickly identify apps and agents that meet most or all requirements and make informed decisions when reviewing requests to allow them in the organization.

## Configure evaluation score settings

Admins configure evaluation score settings from the Microsoft Teams admin center. These settings define the evaluation criteria that Teams uses to evaluate eligible third-party apps.

### To configure evaluation score settings

1. Sign in to [Microsoft Teams admin center](https://admin.teams.microsoft.com/).
2. In the left navigation, go to **Teams apps**.
3. Select **Evaluation score settings**. [![Screenshot showing the Evaluation score settings page.](media/evaluation-score.png)](media/evaluation-score.png#lightbox)

From this page, admins can define and manage the organization’s evaluation criteria.

### Define an organization evaluation criteria

On the **Evaluation score settings** page, admins can:

- Review the predefined list of available security, compliance, and permission related requirements.
- Add, edit, or remove requirements to make the overall criteria relevant to their organization.
- Download the requirements set in CSV format.

#### Add requirements to the organization evaluation criteria

1. On the **Evaluation score settings** page, select **Add**. [![Screenshot showing the add requirements function.](media/add-requirement.png)](media/add-requirement.png#lightbox)
2. The **Add a requirement** page opens and displays a list of predefined security, compliance, and permission related requirements to choose from.
3. Select **Save** to save the selected requirements. ![Screenshot showing the add requirements page.](media/add-requirement-evaluation-score.png)

The selected requirements are used to calculate evaluation scores for eligible apps.

#### Edit or remove requirements

Admins can update the organization's app approval criteria at any time from the **Evaluation score settings** page.

- **To edit a requirement**:

    1. On the **Evaluation score settings** page, select the requirement you want to change.
    2. Select **Edit**. [![Screenshot showing the edit requirements function.](media/edit-evaluation-score.png)](media/edit-evaluation-score.png#lightbox)
    3. Make the necessary changes and select **Save**.
- **To remove a requirement**:

    1. On the **Evaluation score settings** page, select the requirement you want to remove.
    2. Select the remove icon. [![Screenshot showing the remove button.](media/remove-requirement-tab.png)](media/remove-requirement-tab.png#lightbox)

Note

Adding, editing, or removing requirements changes how evaluation scores are calculated. It doesn't change the underlying security, compliance, permission related data provided by the app or agent.

#### Download the selected predefined requirements

Admins can download the finalized set of organization requirements from the **Evaluation score settings** page.

1. On the **Evaluation score settings** page, select the excel icon.
2. Listed requirements will be downloaded in the CSV format.

## View evaluation scores in the Manage apps page

Based on the requirements that are configured on the **Evaluation score settings** page, your organization specific evaluation score is made available through a new **Evaluation score** column in the **Manage apps** page in the Teams admin center.

[![Screenshot showing the evaluation score column in the manage apps page.](media/evaluation-score-column.png)](media/evaluation-score-column.png#lightbox)

The **Evaluation score** column shows the percentage of selected requirements that are met for each eligible app or agent.

### How evaluation scores are displayed

- The evaluation score is displayed as a percentage.
- Evaluation scores reflect the security, compliance, permissions related metadata currently available and may change in future, if underlying data changes.

Depending on the app or agent, the evaluation score can include:

- Requirements that are **met**
- Requirements that are **not met**
- Requirements for which **no data** is available

Note

If a configured security, compliance, permission related parameter isn't available for the selected app or agent, the status is shown as **no data**.

### Eligibility for evaluation scores

Evaluation scores are shown only for apps and agents that meet all of the following conditions:

- The app or agent is a third-party application
- Security and compliance data is available for the app
- The app isn't already available in the organization for installation or use by anyone

### Sort and filter apps by evaluation score

Admins can use the **Evaluation score** column on the **Manage apps** page to quickly find apps and agents that meet all or most of their organization specific requirements.

#### Sort apps or agents by evaluation score

1. Go to the **Manage apps** page in the Teams admin center.
2. Click on the sort icon on the **Evaluation score** column header.

Apps and agents are sorted by their evaluation score in ascending or descending order, based on count of requirements that are met.

#### Filter apps or agents by evaluation score

Admins can filter apps and agents based on how many evaluation requirements they meet.

1. On the **Manage apps** page, select the Filter icon. [![Screenshot showing the filter option on the manage apps page.](media/filter-manage-apps.png)](media/filter-manage-apps.png#lightbox)
2. Select **Evaluation requirements met** value from the **Filter** dropdown.
3. Choose one of the following conditions:

    - Greater than a specified percentage
    - Equal to a specified percentage
4. Select the percentage value from the **Value** dropdown.
5. Select **Apply**. ![Screenshot showing the filtering criteria.](media/filter-requirements-page.png)

The Manage apps page updates to show only the apps or agents that meet the selected evaluation score criteria.

## View the detailed evaluation score report for an app or agent

Admins can view a detailed breakdown of how an app or agent meets the configured evaluation requirements.

### To view the evaluation score report

1. In the **Teams admin center**, go to **Teams apps** &gt; **Manage apps**.
2. Select an app or agent.
3. On the app details page, review the **Evaluation score** shown on the app card. [![Screenshot showing the evaluation score on the app card.](media/evaluation-score-app.png)](media/evaluation-score-app.png#lightbox)
4. Select the **Evaluation score report** tab. ![Screenshot showing app card with Evaluation score report tab selected.](media/evaluation-score-app-card.png)

The **Score requirements results** section provides a detailed breakdown of each configured requirement, including:

- **Name**: The configured requirement.
- **Requirement value**: The configured value of the requirement.
- **Status**: Whether the requirement is **Met**, **Not met**, or **No data**, based on the underlying metadata.

    [![Screenshot showing the score requirements report page.](media/score-requirements-results.png)](media/score-requirements-results.png#lightbox)

This detailed view helps admins understand exactly which requirements an app or agent satisfies and where gaps exist before deciding whether to make the app or agent available in the organization.