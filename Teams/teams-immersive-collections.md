---
layout: Conceptual
title: Manage immersive collections in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-immersive-collections
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to manage immersive collections in Microsoft Teams.
author: Sean-Kerawala
ms.author: sekerawa
manager: tyadams
ms.service: msteams
ms.subservice: teams-events
ms.topic: concept-article
ms.date: 2026-03-18T00:00:00.0000000Z
locale: en-us
document_id: 92b4c509-d9fe-4aa3-a47e-edc77f849185
document_version_independent_id: 92b4c509-d9fe-4aa3-a47e-edc77f849185
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-immersive-collections.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-immersive-collections
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-immersive-collections.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4bd7237a-092b-e520-1f52-b5c3fda9a9c1
---

# Manage immersive collections in Teams - Microsoft Teams | Microsoft Learn

Immersive Collections are a way to store, organize, and share templates for Teams immersive events. This article explains what Collections are, how to create and configure one, and how to manage the environments, templates, and members inside it.

## Key concepts

Before you set up a Collection, it helps to understand how the pieces fit together.

| Concept | Description |
| --- | --- |
| **Collection** | A shared workspace where owners and members store and manage immersive event templates. |
| **Template** | An environment combined with customizations (objects such as images, videos, and 3D models). Templates are reusable and can be refined over time. |
| **Environment** | A `.glb` file representing a 3D space. You can use a prebuilt environment or upload your own. |
| **Object** | Content added to an environment during a customization session, such as images, videos, 3D models, interactive elements, and more. |

A template is the combination of an environment and its objects. Collections let you save that work once and reuse it across events, so each event organizer starts from a ready-made experience rather than building from scratch.

## Why use Collections

Collections help your organization:

- **Centralize environments and templates** so event organizers can quickly find and reuse proven setups.
- **Standardize experiences** across teams or business groups without recreating work.
- **Iterate over time**. You can refine a template after each event and improve the experience incrementally.
- **Delegate ownership**. Multiple owners can manage a Collection, and members can run events using shared templates without needing to build or configure anything.

## Prerequisites

- **Teams desktop app**: Collections are created and managed in the Events app on Teams desktop.
- **Microsoft 365 group creation permission**: Creating a Collection requires the ability to create Microsoft 365 groups in your organization. If you don't have this permission, ask your IT admin to either grant it or create a Collection for you and add you as a member.

## Create a Collection

1. Open the Teams desktop app and go to the Events app.
2. Select **Manage**, then scroll down and select **View Immersive Collections**.
3. In the upper-right corner, select **Create collection**.
4. Fill in the following fields:

    | Field | Description |
    | --- | --- |
    | **Name** | A descriptive name for the Collection. |
    | **Description** | Optional context about the Collection's purpose or intended audience. |
    | **Sensitivity label** | If your organization uses Microsoft Purview sensitivity labels, select the appropriate label. Available labels depend on your organization's configuration. |
    | **Privacy** | Collections are **Private** by default. People must be explicitly added to view or use the Collection. |
5. Select **Create**.

    Note

    We recommend creating a small number of Collections organized around your org structure or experience type. For example, create one per team, business unit, or recurring event program. Keeping Collections focused makes it easier for organizers to find the right template and for owners to maintain content over time.

## Create templates

A template combines an environment with customizations (objects) so the full event setup is ready to reuse. There are two ways to create a template:

### Option 1: Via the Schedule form

Schedule an immersive event, and then go to **Manage event** &gt; **Customize immersive event**. In the customization session, you can add objects—images, videos, 3D models, interactive elements, and more—to the environment.

To save the template, go back to the schedule form, navigate to **Immersive experience template**, and then select "**...**" &gt; **Save as template**.

### Option 2: Via Collections &gt; Environments

You can upload a custom environment as a `.glb` file and create a template directly from it.

For guidance on building a custom environment, see [Use custom environments in Teams immersive events](teams-immersive-custom-environments).

**Upload a custom environment**

1. In the Events app, go to **Manage** &gt; **View Immersive Collections** &gt; **[*Collection name*]** &gt; **Environments**.
2. Select **Upload environment**.
3. Fill in the name and description, and then upload your `.glb` file.
4. Upload a thumbnail image to represent the environment in the picker.

Note

We recommend keeping environment files at 250 MB or less to avoid upload failures and ensure reliable event performance.

**Create a template from an environment**

Once uploaded, your environments appear in **Environments** under the Collection. Select "**...**" under **Actions**, then select **Create template**. This creates a baseline template you can further customize in a later session.

You can also use **Actions** to:

- **Edit**: Update the environment name, description, or thumbnail.
- **Delete**: Permanently remove the environment from the Collection.

Once created, a template is visible to all owners and members of the Collection and appears as an option when scheduling a new immersive event.

## Manage members

By default, a Collection is private. You control who can access and use it.

### Add members

1. Open the Collection, and then select **Add people** under **Members**.
2. Search for and select the people you want to add.
3. Assign a role:

    | Role | Capabilities |
    | --- | --- |
    | **Owner** | Full control. Create and delete environments, create and edit templates, manage members, and configure Collection settings. |
    | **Member** | Can use templates to schedule events, edit existing templates, and add new templates to the Collection. |