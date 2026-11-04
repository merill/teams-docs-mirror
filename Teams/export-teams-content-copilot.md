---
layout: Conceptual
title: Export content with Copilot - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/export-teams-content-copilot
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.date: 2025-06-04T00:00:00.0000000Z
description: In this article, you learn about how to export Teams content using Copilot.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
locale: en-us
document_id: 7539c5b0-24da-a073-7b27-13a234af8672
document_version_independent_id: 7539c5b0-24da-a073-7b27-13a234af8672
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/export-teams-content-copilot.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: export-teams-content-copilot
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/export-teams-content-copilot.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: bb94ea4a-3cb2-cdf5-0fc5-4a7dd9d5d69e
---

# Export content with Copilot - Microsoft Teams | Microsoft Learn

The Copilot Activity Export API allows you to export Copilot interactions data, which includes the user prompt to Copilot and the Copilot response back to the user. This API captures the user intent and Copilot accessed resources and the response back to the user across Microsoft Copilot apps such as Teams, Word, and Outlook.

## How to access Copilot Activity Export APIs

- **Example 1** is a simple query to retrieve all the Copilot interactions without any filters:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/copilot/users/{id}/interactionHistory/getAllEnterpriseInteractions 
    ```
- **Example 2** is a simple query to retrieve all the Copilot interactions with appclass filters:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/copilot/users/{id}/interactionHistory/getAllEnterpriseInteractions?$filter=appClass eq 'IPM.SkypeTeams.Message.Copilot.Teams or appClass eq 'IPM.SkypeTeams.Message.Copilot.BizChat'
    ```

## Prerequisites to access Copilot Activity Export APIs

Application permissions are used by apps that run without a signed-in user present. Only an administrator can approve application permissions. The following permissions are needed:

- *AiEnterpriseInteraction.Read.All*: enables access to all Copilot interactions across Microsoft 365 apps and Microsoft 365 Chat
- A **Microsoft Copilot license** is required for accessing the new Copilot Activity Export API.

## Supported appClass filters

The following appClass filters are supported:

- `IPM.SkypeTeams.Message.Copilot.Word`
- `IPM.SkypeTeams.Message.Copilot.Excel`
- `IPM.SkypeTeams.Message.Copilot.Teams`
- `IPM.SkypeTeams.Message.Copilot.BizChat`
- `IPM.SkypeTeams.Message.Copilot.WebChat`
- `IPM.SkypeTeams.Message.Copilot.CoworkChat`

These filters allow you to specify the type of Copilot interactions you want to retrieve based on the app class. The rest of the interactions aren't supported.

Learn more about the [aiInteractionHistory: getAllEnterpriseInteractions](/en-us/graph/api/aiinteractionhistory-getallenterpriseinteractions?view=graph-rest-1.0&amp;preserve-view=true) that enables exporting Copilot interactions.

#### Known issue

For some interactions in Teams Meeting Copilot, the `contexts[]` might be missing in the `aiResponse` interactions. The corresponding user prompt, however, always includes the `contexts[]` to ensure accurate context retrieval. The development team is aware of this problem and is working on a resolution. The following example shows a userprompt, aiResponse pair that has valid contexts[] in the userprompt and missing contexts[] in the corresponding aiResponse.

```json
[
    {
        "id": "1746757256660",
        "sessionId": "19:-SMwOyVjy2H3_BnsIO6WGUTXwuN1_BIw4U2TP4UcCwo1@thread.v2",
        "requestId": "db42bee0-7cfb-451f-8eb6-f929762ee970",
        "appClass": "IPM.SkypeTeams.Message.Copilot.Teams",
        "interactionType": "userPrompt",
        "conversationType": "appchat",
        "etag": "1746757256660",
        "createdDateTime": "2025-05-09T02:20:56.66Z",
        "locale": "en-us",
        "contexts": [
            {
                "contextReference": "https://microsoft.teams.com/threads/19:meeting_MTQ4ZDdkMzktYjhkZC00ODdlLTkwN2UtYzcwYjVmOWIxYTNm@thread.v2",
                "displayName": "Teams Meeting Copilot",
                "contextType": "TeamsMeeting"
            }
        ],
        "from": {
            "@odata.type": "#microsoft.graph.chatMessageFromIdentitySet",
            "application": null,
            "device": null,
            "user": {
                "@odata.type": "#microsoft.graph.teamworkUserIdentity",
                "id": "886cb6c8-eb73-4f72-ad99-69ebf43f70ad",
                "displayName": "8:orgid:886cb6c8-eb73-4f72-ad99-69ebf43f70ad",
                "userIdentityType": "aadUser",
                "tenantId": "bcefad10-7e12-4123-8457-f3ac71b098db"
            }
        },
        "body": {
            "contentType": "text",
            "content": "what was this meeting about?&lt;attachment id=\"19:meeting_MTQ4ZDdkMzktYjhkZC00ODdlLTkwN2UtYzcwYjVmOWIxYTNm@thread.v2\"&gt;&lt;/attachment&gt;"
        },
        "attachments": [
            {
                "attachmentId": "19:meeting_MTQ4ZDdkMzktYjhkZC00ODdlLTkwN2UtYzcwYjVmOWIxYTNm@thread.v2",
                "contentType": "reference",
                "contentUrl": "https://microsoft.teams.com/threads/19:meeting_MTQ4ZDdkMzktYjhkZC00ODdlLTkwN2UtYzcwYjVmOWIxYTNm@thread.v2",
                "content": null,
                "name": "Teams Meeting Copilot"
            }
        ],
        "links": [],
        "mentions": []
    },
    {
        "id": "1746757257162",
        "sessionId": "19:-SMwOyVjy2H3_BnsIO6WGUTXwuN1_BIw4U2TP4UcCwo1@thread.v2",
        "requestId": "db42bee0-7cfb-451f-8eb6-f929762ee970",
        "appClass": "IPM.SkypeTeams.Message.Copilot.Teams",
        "interactionType": "aiResponse",
        "conversationType": "appchat",
        "etag": "1746757257162",
        "createdDateTime": "2025-05-09T02:20:57.162Z",
        "locale": "en-us",
        "contexts": [],
        "from": {
            "@odata.type": "#microsoft.graph.chatMessageFromIdentitySet",
            "device": null,
            "user": null,
            "application": {
                "@odata.type": "#microsoft.graph.teamworkApplicationIdentity",
                "id": "fb8d773d-7ef8-4ec0-a117-179f88add510",
                "displayName": "Copilot in Teams",
                "applicationIdentityType": "bot"
            }
        },
        "body": {
            "contentType": "text",
            "content": "I need to hear more discussion before I can get to work. Please try again in a few minutes."
        },
        "attachments": [],
        "links": [],
        "mentions": []
    }
]

```

**Not in scope for Copilot Interactions Export APIs:**

- Delta function call isn't supported.
- Certain Copilot‑generated presentation metadata isn't included in the Copilot Interactions Export API responses. The following metadata isn't included:
    1. Editable Copilot Microsoft 365 chat display names.
    2. Outlook message subject lines that are automatically generated or suggested by Copilot.

Note

- To understand throttling limits for the Copilot Interactions Export API, refer to [Teams Export APIs throttling limits](/en-us/graph/throttling-limits).
- For optimal performance, the recommended $top value is 100.
- This API can be used to retrieve the supported Copilot Interactions for deleted users.
- Deleted Copilot interactions for the supported app classes can be retrieved using this API.
- If a user prompt is edited, it's considered as a new interaction and can be retrieved using this API.