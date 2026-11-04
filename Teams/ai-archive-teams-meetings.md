---
layout: Conceptual
title: Memory for Microsoft Teams Meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/ai-archive-teams-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Memory for Teams Meetings is an AI-generated artifact that stores the essential knowledge from a meeting’s discussion and metadata.
ms.date: 2026-10-26T00:00:00.0000000Z
author: gracemaz
manager: shaannarang
ms.author: grculver
ms.reviewer: grculver
ms.topic: feature-guide
ms.service: msteams
ms.subservice: msteams-admin
locale: en-us
document_id: 6a67c43a-d7e1-74ab-8d03-1ce1a3a6862d
document_version_independent_id: 6a67c43a-d7e1-74ab-8d03-1ce1a3a6862d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/ai-archive-teams-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: ai-archive-teams-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/ai-archive-teams-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 798c18b0-77c1-0935-05cc-3e8d83ef7186
---

# Memory for Microsoft Teams Meetings - Microsoft Teams | Microsoft Learn

Generating and storing memory for meetings is a powerful way to empower Microsoft’s AI tools like Copilot and Facilitator to be smarter and more useful in your organization, giving the tools durable knowledge and context from previous meetings. The meeting memory (formerly called AI meeting archive) is an AI-generated artifact that condenses and stores the essential knowledge from a meeting’s discussion and metadata so Facilitator, Copilot, and other downstream AI systems can ground their reasoning without storing raw user content. Copilot and Facilitator use meeting memory to answer questions about a meeting. The memory file is stored within a Teams-owned SharePoint Embedded container rather than a particular user's space and isn't visible or accessible by users in your organization. Meeting memory generation is default on for your organization.

Note

Meeting memory is in preview and only available to organizations in the Teams TAP program.

### What’s included in meeting memory?

Meeting memory is stored as a file with the **.meeting** extension and includes meeting metadata, such as the meeting title, date and invite list, as well as a summary of the key insights and meeting discussion.

Note

No raw user data or transcript excerpts are included in meeting memory, only AI-generated content.

### When is meeting memory created?

When enabled in the Teams Admin Center, meeting memory is generated for meetings where:

1. Intelligent recap was turned on for the meeting,
2. A Copilot-licensed participant was invited to the meeting

Through the Teams Admin Center, you can control whether memory is generated for all meetings, generated only for meetings where transcript is turned on, or off. Memory won't be created for meetings with sensitivity labels which include encryption, meetings with end-to-end encryption, or meetings where copying and forwarding content is restricted.

### How is meeting memory used?

Facilitator, Copilot, and other downstream Microsoft AI tools reason over meeting memory to improve the quality of responses.

- Content in meeting memory is only accessible through Copilot, Facilitator, and other Microsoft AI tools. Users can't open or view the memory file directly.
- If AI uses meeting memory to generate a response, the response includes a citation that links to the meeting recap or meeting invite.
- Meeting memory files are indexed for search. Opening a memory file from a search point redirects the user to the meeting recap page or meeting invite.
- The memory file can't be moved, renamed, or modified.
- Facilitator, Copilot, and other AI never shares insights from a meeting with users who don't have access to the meeting.

### Who has access to meeting memory?

Meeting memory is only available to users invited to the meeting and users who are given access by sharing the meeting recap. Users can't directly open or view the meeting memory file, but Copilot, Facilitator, and other Microsoft AI tools use memory to answer questions about the meeting for users who have access.

### How can meeting memory be deleted?

The meeting organizer can delete meeting memory by deleting the meeting recap. First, navigate to the meeting recap. Then, open the **…** menu, and select **Delete recap content**.

Note

Meeting memory won't automatically be deleted if the transcript or recording is deleted or expired.

A Microsoft Teams admin can also delete a meeting memory file through PowerShell:

1. Open PowerShell.
2. Run Connect-MicrosoftTeams and sign in with your Teams admin account.
3. Run the following command (ThreadId is required; CallId is optional)

> 
> Remove-AIGeneratedKnowledge -ThreadId &lt;String&gt; -CallId &lt;String&gt;

### Managing Meeting Memory Generation for your Organization

#### Turning Off Meeting Memory Generation

Meeting memory is enabled by default for each tenant, and memory will be created for meetings where Intelligent Recap is turned on. In the Teams Admin Center, you can disable meeting memory for your organization or change the setting to only for meetings with transcription. Navigate to the **Meeting memory** (formerly "Allow AI to archive meetings with .meeting file generation") setting in the **Meeting Policies** section of the Teams Admin Center.

Meeting memory is enabled by default for every tenant. When meeting memory is enabled, memory is created for any meeting that has Intelligent Recap enabled. Admins can change this setting in the Teams Admin Center:

1. Go to **Meetings** &gt; **Meeting policies**.
2. Find the **Meeting memory** setting. It was previously called "Allow AI to archive meetings with .meeting file generation."
3. Choose one of these options:

    1. On for all meetings (default): Memory is created for meetings with Intelligent Recap.
    2. Only for meetings with transcription: Memory is created for meetings with Intelligent Recap that are transcribed.
    3. Off: Memory is turned off for your organization.

Memory generation can be turned off for a specific meeting by turning off Intelligent Recap in the meeting options.

There is no impact to existing Teams features and functionality if memory generation is turned off. Meeting memory is an optimization and enhancement that will help improve the quality of Copilot and Facilitator's meeting-related responses and may allow Copilot and Facilitator to continue answering questions about meetings beyond transcript retention periods, depending on the memory expiration date and retention policies set for your organization.

#### Setting Default Expiration of Meeting Memory Files

Default expiration of memory files is controlled through the Teams Admin Center. The default expiration time for memory files is five years (1,825 days), but admins can customize the expiration time as needed for their organization. Once a memory file expires, the file is deleted and can't be used by Copilot, Facilitator, and other AI to answer questions about the meeting. Microsoft recommends setting longer default expiration times to enhance Facilitator and Copilot’s functionality.

Microsoft Purview retention policies can also be configured to manage retention and deletion of meeting memory files. Purview retention policies will take precedence over the meeting memory expiration setting in the Teams Admin Center. See below section Setting Retention Policies.

### Meeting Memory Storage

Meeting memory is built on SharePoint Embedded and files are stored using Teams-owned Microsoft 365 File Storage Containers, or Containers for short. SharePoint Embedded is an API-only file and document management system. For more information about SharePoint Embedded, see [Overview of SharePoint Embedded](/en-us/sharepoint/dev/embedded/overview). The first memory file created for your organization creates a new Container. Each additional memory file uses an existing Container if that Container has available space or creates a new Container if it doesn't. Containers are dedicated to memory files and don't store other kinds of data. The memory file will be stored in Container in the preferred data location of the meeting organizer for multi-geo organizations.

#### Finding Meeting Memory File Container URLs

In certain Purview tools, such as eDiscovery or Retention policies, you may need meeting memory container URLs. A specific memory file container URL can be found by the Teams admin through PowerShell:

1. Open PowerShell.
2. Run Connect-MicrosoftTeams and sign in with your Teams admin account.
3. Run the following command (ThreadId is required; CallId is optional).

> 
> Get-AIGeneratedKnowledgeContainer -ThreadId &lt;String&gt; -CallId &lt;String&gt;

Note

Meeting memory files use a different container model than Loop, Copilot Pages, and Copilot Notebooks. Memory files are stored in different SharePoint Embedded containers and are lifetime managed by the Teams infrastructure. Loop My workspace, Copilot Pages, and Copilot Notebooks are stored in **user-owned** containers whose application name appears as `Loop` in the SharePoint admin center.

#### eDiscovery and Legal Hold through Purview

Admins can perform eDiscovery searches on all SharePoint Embedded content using the **All SharePoint Sites** workload. Admins can also specify specific meeting memory containers using container URLs. eDiscovery admins can perform eDiscovery Hold and Export on memory file content. [Learn more about Security and Compliance for SharePoint Embedded Containers](/en-us/sharepoint/dev/embedded/compliance/security-and-compliance).

#### Setting Retention Policies

Retention policies on memory files are managed in the Purview Data lifecycle management tool. Meeting memory sites included in **SharePoint classic and communication sites**, so no other configuration is needed to target memory files with the same retention policy as other SharePoint content. To target memory with a different policy, you can use the **include** or **exclude** settings to scope your search to your meeting memory container URLs.

Purview retention policies will take precedence over the meeting memory expiration setting in the Teams Admin Center.

#### Information Barriers

Meeting memory files do not yet support [Information Barriers](/en-us/purview/information-barriers).

#### Are Admins able to use SharePoint Embedded APIs to directly manage meeting memory containers?

Meeting memory containers are fully managed in Microsoft Teams' services. Admins can't directly use SharePoint Embedded APIs to manage meeting memory containers.

#### What happens to a meeting memory file when the organizer of that meeting is deactivated?

Since meeting memory files are stored in Teams-owned Microsoft 365 File Storage Containers rather than a specific user's space, the meeting memory still exists even if the meeting organizer's account is deactivated. The memory remains until the default expiration time specified in the Teams Admin Center, unless Purview retention policies are set. When the expiration time is reached, the memory file is deleted and can't be recovered.