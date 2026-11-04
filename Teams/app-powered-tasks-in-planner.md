---
layout: Conceptual
title: Manage app-powered tasks in Planner for tailored task experiences - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/app-powered-tasks-in-planner
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: anahitab
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
ms.reviewer: andfried
ms.date: 2026-02-06T00:00:00.0000000Z
search.appverid: MET150
audience: admin
description: Learn how to create and manage app-powered tasks in the Planner app in Teams to provide tailored task experiences.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
- teams-1p-app-admin
- highpri
locale: en-us
document_id: ed6ac0bb-5cf9-0cea-969c-ca9d237e37b6
document_version_independent_id: ed6ac0bb-5cf9-0cea-969c-ca9d237e37b6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/app-powered-tasks-in-planner.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-powered-tasks-in-planner
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/app-powered-tasks-in-planner.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d191e75b-e2c8-b745-c059-6f1dc2db1652
---

# Manage app-powered tasks in Planner for tailored task experiences - Microsoft Teams | Microsoft Learn

Note

This feature is currently in public preview.

## Overview

The app-powered tasks feature offers your organization more control over what users see when they open their tasks in the Planner app within Microsoft Teams. Instead of showing only the standard set of task fields, you can provide users with an experience tailored to the task at hand. That experience might be a workflow-specific set of fields or step-by-step guidance to walk the user through a workflow from beginning to end. To achieve this, you integrate a Teams app with the task and create these tasks programmatically.

Say, for example, users in your organization use a Teams app to track and complete inspections. You can integrate this inspections app with tasks so that a Planner task is created for each inspection tracked in the system.

- When a user opens one of these tasks from the Planner app in Teams, they see a simplified screen with a button to jump directly to the inspection experience powered by your inspections app.
- When they complete the task and close the inspections experience, they're right back in Planner where they started.

Users get the tailored experience that a Teams app provides right from within their assigned tasks. They don't have to navigate to a different app to get work done or lose context of where they were when working with their tasks.

In addition to these benefits when users complete tasks, the app-powered tasks feature allows organizations to reflect required line-of-business processes and workflows as tasks, so employees can see all the work they're accountable for from a single place.

This experience is supported in the Planner app on Teams web, desktop, and mobile. You can provide tailored task experiences for your users with any Teams app that meets the following requirements.

## Requirements

App-powered tasks is an extensibility feature that relies on programmatic creation and management of tasks. The requirements to use this feature are as follows.

- Each app-powered task points to an experience in a destination Teams app, which requires you to provide a reference URL to that experience. We recommend that you point this reference URL to the specific item or screen the user should be working on. This reference URL must be added to the task in a specific way. To learn more, see the Step 1: Configure the reference URL section of this article.
- Tasks must be created and updated using the [business scenarios](/en-us/graph/api/resources/businessscenario-planner-overview) API in Microsoft Graph.
- Users who need to work with the task must have access to the destination app in Teams, as governed by the app policies you set in the Teams admin center. To learn more, see [Overview of app management and governance in Teams admin center](manage-apps).
- The destination Teams app is responsible for managing the task lifecycle, which includes the following actions:

    - Create the task. See [Create businessScenarioTask](/en-us/graph/api/businessscenarioplanner-post-tasks).
    - Assign the task. See [Update businessScenarioTask](/en-us/graph/api/businessscenariotask-update).
    - Update the task, if properties change. See [Update businessScenarioTask](/en-us/graph/api/businessscenariotask-update).
    - Mark the task as Completed when all steps are done. See [Update businessScenarioTask](/en-us/graph/api/businessscenariotask-update).
    - Delete the task. See [Delete businessScenarioTask](/en-us/graph/api/businessscenarioplanner-delete-tasks).

This feature allows your destination Teams app to govern the task lifecycle because some workflows might not have deterministic flows. As a result, the Planner app doesn't know whether all required steps are completed. For example, a finding during an inspection might result in the inclusion of several more steps in the inspection. Similarly, users are prevented from updating task fields or marking the task as Completed. These actions might result in users making changes that conflict with what's reflected in your destination Teams app.

## Create an app-powered task

This section covers how to use the [Create businessScenarioTask](/en-us/graph/api/businessscenarioplanner-post-tasks) API to create an app-powered task.

Use the following HTTP POST request. Here's what the request looks like, with placeholders for the properties that you specify.

**Request**

```http
POST https://graph.microsoft.com/beta/solutions/businessScenarios/{your-business-scenario-ID}/planner/tasks 

{ 
"title": "{Task title}", 
    "target": { 
        "@odata.type": "#microsoft.graph.businessScenarioGroupTarget", 
        "taskTargetKind": "group", 
        "groupId": "{group ID of the team where you want to create the task}" 
    }, 
    "businessScenarioProperties": { 
        "externalObjectId": "{any unique ID, for example, the ID of the object in your destination app}", 
        "externalBucketId": "{any bucket ID from planConfiguration of your business scenario}" 
    }, 
    "assignments": { 
        "{user ID of user you want to assign the task to}": { 
            "@odata.type": "#microsoft.graph.plannerAssignment", 
            "orderHint": " !" 
        } 
    }, 
    "details": { 
        "references": { 
            "{reference URL}": { 
                "@odata.type": "microsoft.graph.plannerExternalReference", 
                "alias": "{destination app name}", 
                "previewPriority": " !", 
                "type": "TeamsHostedApp" 
            } 
       } 
    } 
} 
```

The following sections walk through how to form the request in more detail.

### How to define the properties in the request

A specific type of attachment differentiates an app-powered task from a standard task. The attachment must be of type `TeamsHostedApp` and must contain a specially formatted link (reference URL) to the destination experience in the Teams app. This signifies to Planner that the task is an app-powered task.

Keep in mind that the API refers to these attachments as [references](/en-us/graph/api/resources/plannerexternalreferences).

First, you configure the reference URL to point to the destination experience. Then, specify the reference URL along with other required properties for the attachment in the request body.

#### Step 1: Configure the reference URL

The reference URL uses a specific format. Follow these steps to construct and then encode the URL.

##### Step 1a: Construct the URL

The reference URL to the destination experience must use [Stageview Modal link syntax](/en-us/microsoftteams/platform/tabs/open-content-in-stageview) in the following format:

`https://teams.microsoft.com/l/stage/{Teams-app-Id}/0?context={"contentUrl":"URL-to-destination-experience"},"name":"{page-title}","openMode":"modal"}`

To construct the reference URL, specify the following parameters.

| Parameter | Description |
| --- | --- |
| `Teams-app-Id` | The app ID of the Teams app you're integrating with the task. |
| `URL-to-destination-experience` | The URL that points to the target experience in your destination Teams app that you want users to see when they open the task. For security reasons, the URL must point to a valid domain associated with the Teams app, which is represented by the app ID you provide. |
| `page-title` | The title that should appear at the top of the screen when the user is shown the URL to the destination experience. |

Here's an example of a reference URL before encoding:

`https://teams.microsoft.com/l/stage/com.microsoft.teamspace.tab.youtube/0?context={"contentUrl":"https://tabs.teams.microsoft.com/youtubeContentStage?videoId=HBGmSy1iVmY","name":"Security%20talk","openMode":"modal"}`

In this example:

- `Teams-app-Id` is the app ID of the YouTube app in Teams (`com.microsoft.teamspace.tab.youtube`). Keep in mind that most Teams app IDs are alphanumeric and might look different.
- `URL-to-destination-experience` points to the experience within the destination Teams app (`https://tabs.teams.microsoft.com/youtubeContentStage?videoId=HBGmSy1iVmY`).
- `page-title` is the name of the screen title (`Security talk`) when loading the URL.

If the YouTube app in Teams is available to you, you can send this URL to yourself and confirm it opens.

##### Step 1b: Encode the URL

You need to encode the reference URL before you can use it in the attachment. Percent encoding ensures the link is in a compatible format for programmatic use.

Follow these steps to encode the reference URL. We use the example reference URL described earlier to demonstrate how to encode the URL.

1. Percent encode the part of the URL that comes after `0?context=`. Don't encode `https://` or `=` (the equal symbol), or any of the characters in between.

    `https://teams.microsoft.com/l/stage/com.microsoft.teamspace.tab.youtube/0?context=%7B%22contentUrl%22%3A%22https%3A%2F%2Ftabs.teams.microsoft.com%2FyoutubeContentStage%3FvideoId%3DHBGmSy1iVmY%22%2C%22name%22%3A%22Security%2520talk%22%2C%22openMode%22%3A%22modal%22%7D`

    Tip

    This is the last step where the link can be easily validated in Teams chat. After you complete this step, you can test the URL by sending it to yourself in a Teams chat. The link should open on Teams desktop, web, or mobile for any user who has access to the destination app in Teams.
2. Replace *all*`.` characters in the reference URL with `%2E`. You must do this across all characters in the reference URL, from beginning to end. If you skip this step, the reference URL might not work.

    The following URL is ready for programmatic use.

    `https://teams%2Emicrosoft%2Ecom/l/stage/com%2Emicrosoft%2Eteamspace%2Etab%2Eyoutube/0?context=%7B%22contentUrl%22%3A%22https%3A%2F%2Ftabs%2Eteams%2Emicrosoft%2Ecom%2FyoutubeContentStage%3FvideoId%3DHBGmSy1iVmY%22%2C%22name%22%3A%22Security%2520talk%22%2C%22openMode%22%3A%22modal%22%7D`

    Note

    If your URL points to a Power App, make sure it includes the `&source=teamstab` parameter to make single sign-on (SSO) work for Power Apps and the `&skipMobileRedirect=1` parameter to skip the screen that prompts users to open the standalone Power App player.

#### Step 2: Define the attachment

To define the attachment, specify the following properties in `"references"` in the request body.

```http
        "references": { 
            "{reference-URL}": { 
            "@odata.type": "microsoft.graph.plannerExternalReference", 
            "alias": "{destination app name}", 
            "previewPriority": " !", 
            "type": "TeamsHostedApp" 
         } 
       } 
```

| Property | Description |
| --- | --- |
| `reference-URL` | The URL to the destination experience, in Stageview Modal link syntax. For details on how to construct and encode the URL, see the Step 1: Configure the reference URL section of this article. |
| `alias` | The name of your Teams app. When a user opens the task, they see a message that says, “Complete this task in &lt;alias&gt;, and a **Start task** button to jump to the destination experience. |
| `previewPriority` | Leave as `!`. |
| `type` | Set to `TeamsHostedApp`. This is what signifies to Planner that the task is an app-powered task. |

## Example

This example shows how to create an app-powered task named "Review security practices presentation" and assign it to a user named Adele Vance (user ID 44ee44ee-ff55-aa66-bb77-88cc88cc88cc). This request uses the example reference URL from the Step 1: Configure the reference URL section of this article.

**Request**

```http
POST https://graph.microsoft.com/beta/solutions/businessScenarios/ccd5aa8aebd048bd839a4fa5b7420631/planner/tasks

{
"title": "Review security practices presentation",
    "target": {
        "@odata.type": "#microsoft.graph.businessScenarioGroupTarget",
        "taskTargetKind": "group",
        "groupId": "769bbf41-70b7-4ea6-a044-a7037358883e"
    },
    "businessScenarioProperties": {
        "externalObjectId": "SP-202418",
        "externalBucketId": "Security practices"
    },
    "assignments": {
        "44ee44ee-ff55-aa66-bb77-88cc88cc88cc": {
            "@odata.type": "#microsoft.graph.plannerAssignment",
            "orderHint": " !"
        }
    },
    "details": {
        "references": {
            "https://teams%2Emicrosoft%2Ecom/l/stage/com%2Emicrosoft%2Eteamspace%2Etab%2Eyoutube/0?context=%7B%22contentUrl%22%3A%22https%3A%2F%2Ftabs%2Eteams%2Emicrosoft%2Ecom%2FyoutubeContentStage%3FvideoId%3DHBGmSy1iVmY%22%2C%22name%22%3A%22Security%2520talk%22%2C%22openMode%22%3A%22modal%22%7D": {
                "@odata.type": "microsoft.graph.plannerExternalReference",
                "alias": "Security practices presentation",
                "previewPriority": " !",
                "type": "TeamsHostedApp"
             }
        }
    }
}
```

Note

This example reference URL was chosen as an easy way to test the app-powered tasks experience using an app that's available in many organizations' environments. Keep in mind that with this example reference URL, users won't be able to complete the task. This is because the YouTube app isn't integrated with app-powered tasks and doesn't make an API call to mark the task complete after the video is played.

### What this looks like in the Planner app

Here's what the user sees when they open the task in the Planner app in Teams. Selecting the **Start task** button takes the user to the destination experience in the Teams app. In this example, the destination experience is a security practices video in the YouTube app in Teams.

[![Screenshot of an example of an app-powered task in My Tasks in the Planner app in Teams.](media/app-powered-tasks-in-planner.png)](media/app-powered-tasks-in-planner.png#lightbox)

To learn more about the user experience, see [Work with app-powered tasks in the Planner app in Teams](https://support.microsoft.com/topic/16d2f882-aad5-4346-a459-4dfd9fc9a457).