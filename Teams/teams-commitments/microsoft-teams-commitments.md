---
layout: Conceptual
title: Microsoft Teams Commitments - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-commitments/microsoft-teams-commitments
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: dansimp
author: Dansimp
manager: dansimp
ms.date: 2025-10-22T00:00:00.0000000Z
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
description: Understand Microsoft Teams commitments and Microsoft 365 app interoperability.
locale: en-us
document_id: c1b67dc9-ed62-84da-ba3c-3fda53f4db3c
document_version_independent_id: c1b67dc9-ed62-84da-ba3c-3fda53f4db3c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-commitments/microsoft-teams-commitments.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-commitments/microsoft-teams-commitments
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-commitments/microsoft-teams-commitments.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
platformId: 37210a2d-ef98-41c3-a6a4-5942a066ac95
---

# Microsoft Teams Commitments - Microsoft Teams | Microsoft Learn

Microsoft has long provided interoperability information, interfaces, and tools to help our vibrant ecosystem of partners integrate their products and services with Microsoft 365 productivity applications. This ecosystem includes communication and collaboration solution providers that compete with Microsoft Teams. Alongside these resources, we have also offered data portability solutions to our customers to allow them to move between services. In keeping with these values, Microsoft entered into agreement with the European Commission (Microsoft’s "**Commitments**"), which formalized many of those interoperability and data portability practices. Those Commitments can be found [here](https://ec.europa.eu/competition/antitrust/cases1/202537/AT_40721_7173.pdf).

This web site provides a summary of interoperability that Microsoft makes available to meet its obligations under the Commitments. If you have difficulty using any of the interoperability information on this page or have any questions or feedback, you can reach out to [Interoperability Questions or Feedback](https://aka.ms/TeamsCommitmentsFeedback).

Any Teams Competitor can request a dedicated point of contact to help facilitate technical support by reaching out through [Dedicated Support Request](https://aka.ms/TeamsCommitmentsSupport).

## Interoperability with Microsoft Products and Services through Microsoft Graph

We believe that customers should have full control over their data. The Commitments formalize Microsoft’s practice of making APIs available to Teams Competitors that provide functionality and access all related data, effectively equivalent to what Teams gets from Microsoft Products and Services. The Microsoft Products and Services covered by the Commitments are Exchange Online, Entra ID (previously known as Azure Active Directory), Microsoft Planner Basic, SharePoint Online, OneDrive, Windows 10/11 Desktop, and certain Microsoft 365 Apps (Microsoft Word, Excel, PowerPoint and Outlook for Windows, Web and macOS). The [Microsoft Graph](/en-us/graph/overview) is how Microsoft meets these interoperability commitments.

Microsoft Graph offers a single endpoint, https://graph.microsoft.com, that allows customers to securely expose their Microsoft 365 data to internal applications and independent software vendors (ISVs). Customers can selectively authorize ISVs to interact with their business’s data using granular permission scopes and consent frameworks, ensuring that access is tightly controlled and aligned with organizational policies. This capability supports interoperability, enabling ISVs to build solutions that enhance productivity while respecting privacy, security, and compliance standards.

You can find more details on how Microsoft provides interoperability with Exchange Online, SharePoint Online and OneDrive, Activity Feeds and Notifications, Entra ID, and Microsoft Planner Basic below.

### Exchange Online APIs

Microsoft provides access to APIs that allow Teams Competitors and ISVs to interoperate with Exchange Online to integrate with its contacts and calendar, including synchronization, creation, and management of appointments and meetings as well as to access emails and tasks. You can find documentation and code samples at: Microsoft Graph APIs for [Mails, Contacts, Calendar, and Tasks](/en-us/exchange/client-developer/exchange-web-services/office-365-rest-apis-for-mail-calendars-and-contacts).

### SharePoint Online and OneDrive APIs

Microsoft provides access to APIs that allow Teams Competitors and ISVs to interoperate with SharePoint Online and OneDrive to retrieve and store files in SharePoint Online and OneDrive. You can find documentation and code samples at: Microsoft Graph APIs for [SharePoint Online and OneDrive](/en-us/onedrive/developer/rest-api/?view=odsp-graph-online).

### Presence APIs

Microsoft provides access to APIs that allow Teams Competitors and ISVs to interoperate with the Presence system. These APIs allow them to share and receive information about the users’ presence and status, such as whether they're away, on a call, or out of the office. You can find documentation and code samples at: Microsoft Graph APIs for [presence](/en-us/graph/api/resources/presence?view=graph-rest-1.0).

### Activity Feeds and Notifications APIs

Microsoft provides access to APIs that allow Teams Competitors and ISVs to interoperate with the Activity Feeds and Notifications system to send and receive notifications to and from other Microsoft Products and Services. You can find documentation and code samples at: Microsoft Graph APIs for [Activity Feeds and Notifications](/en-us/graph/teams-send-activityfeednotifications?tabs=desktop%2Chttp).

### Entra ID APIs

Microsoft provides access to APIs that allow Teams Competitors and ISVs to interoperate with Microsoft Entra ID to access the information stored in Entra ID (previously known as Azure Active Directory). These APIs can be used to authenticate users against other Microsoft 365 Products and Services and to access the relationships and resources relevant to users, such as group memberships, organizational hierarchy, a user photo, and similar customer information associated with a user stored in Microsoft Entra ID. This access includes the information and permissions that are necessary for Teams Competitors to take effective advantage of the interoperability provided in the APIs described above. You can find documentation and code samples at: Graph APIs for [Microsoft Entra ID](/en-us/graph/identity-network-access-overview).

### Microsoft Planner Basic APIs

Microsoft provides access to APIs that allow Teams Competitors and ISVs to interoperate with Planner (Basic). You can find documentation and code samples at: Microsoft Graph APIs for [Planner (Basic)](/en-us/graph/api/resources/planner-overview?view=graph-rest-1.0).

### Microsoft Windows 11 and Windows 10 Desktop

In addition to the Microsoft Graph APIs, Microsoft also provides access to API that allows ISVs to interoperate with Windows 11 and Windows 10 Desktop. You can find documentation, the Windows SDK, and the Windows App SDK at: [API reference for Windows desktop apps](/en-us/windows/apps/api-reference/).

### Feedback and Questions on Interoperability APIs

If you have feedback or questions on interoperability with Microsoft’s APIs, you can reach out [here](https://Aka.ms/TeamsAPIInteropFeedback).

## Enabling Customers to Switch from Microsoft Teams

Microsoft enables customers to access their data for many purposes, including to switch to a Teams Competitors if desired. The Commitments formalize this practice and require that Microsoft enable European Economic Area (EEA) Customers, and entities acting on behalf of EEA Customers, to extract all their Teams messaging data and Teams-specific memberships and permissions for use in another communication and collaboration application. The Commitments also require that Microsoft provide a tool to facilitate the export of Teams data for EEA customers with 500 or fewer users. Microsoft complies with this by providing data export APIs and, for smaller businesses, a Teams data export tool.

### Teams Data Export APIs

Microsoft provides customers the ability to export their data through Teams data export APIs. These Teams data export APIs enable customers to export all of their Teams messaging data, including messaging content for standard, private, and shared channels; direct, group, and meeting chats; as well as the information on structure and content necessary to understand the channel and team structures associated with the messaging data. You can find information on switching from Teams with data export APIs [here](/en-us/microsoftteams/migration-from-teams#access-the-teams-export-apis).

### Teams Data Export Tool

For customers with 500 users or fewer in their respective tenant, Microsoft provides an automated tool to facilitate the export of Teams data, specifically messages in chats and channels, team and channel structure, meeting transcription and recording links, user roster, and list of apps installed for Teams. You can find information on switching from Teams with the Teams data export tool [here](/en-us/microsoftteams/migration-from-teams#steps-to-access-the-teams-data-export-tool).

### OneDrive and SharePoint Retrieval APIs

In addition, Microsoft provides customers with the ability to retrieve their files stored in SharePoint Online and OneDrive for Business through Microsoft Graph APIs. The Commitments formalize this practice for EEA Customers. You can find information on retrieving files in SharePoint Online and OneDrive for Business for switching with export APIs [here](/en-us/onedrive/developer/rest-api/?view=odsp-graph-online).

### Switching at No Cost

When an EEA Customer informs Microsoft of their intent to use the data export APIs to extract their Teams, SharePoint Online, and OneDrive for Business data to switch from Teams to a Teams Competitor, Microsoft does not charge for this export. You can find information on switching from Teams with data export APIs at no cost [here](/en-us/microsoftteams/migration-from-teams#steps-to-access-the-teams-data-export-tool). The [Teams data export tool](/en-us/microsoftteams/migration-from-teams) is also available to customers at no cost for switching.

### Fee Limits for In Parallel Use

In addition, EEA Customers who want to use the data export APIs to access their Microsoft Teams data for use with a communication and collaboration solution offered by a Teams Competitors can do so at a charge not to exceed cost of goods sold (COGS).

## Integrating with Microsoft 365 Apps and Teams

ISVs can use Microsoft’s add-in model to enable integrations between Microsoft 365 Apps or Teams and third-party solutions. The Commitments formalize this practice by which Teams Competitors can develop add-ins subject to standard terms. Teams Competitors can develop add-ins for Microsoft 365 Apps designed for Windows, MacOS, or the version hosted on the web. You can find documentation, code samples, and other useful information here: [Office Add-Ins](/en-us/office/dev/add-ins/).

Microsoft maintains the Microsoft Marketplace (previously AppSource Marketplace) as a distribution channel for add-ins for Microsoft 365 Apps and Teams on standard [terms](/en-us/legal/marketplace/msft-publisher-agreement), for developers who choose to use this channel. You can find documentation, code samples, developer tool, and support resources for Microsoft Marketplace [here](/en-us/marketplace/appsource-overview).

## Enabling the Embedding of the Microsoft Office Web Applications

To better serve our shared customers and in support of the Commitments, the Microsoft 365 Document Collaboration Partner Program enables Teams Competitors to embed Office Web Applications (Word, Excel, PowerPoint) in their Windows, MacOS, and web applications. This includes support for viewing, editing, collaboration, presentation functionality, and live experiences. You can find the software development kit (SDK), technical documentation, and information on how to participate in this program and other details at: [Microsoft 365 Document Collaboration Partner Program](https://aka.ms/m365/dcpp).

### Accuracy of Documentation and How to Notify Microsoft

Microsoft is committed to complying with the Commitments. If any necessary technical documentation or information is missing or inaccurate, you can provide formal notification to Microsoft by using the online notice form available [here](https://Aka.ms/SubmitNotice). Describe your use case, objective, and the specific feature or data you need access to in as much detail as possible. This notice form is accessible worldwide. Note that the response time and resolution plan might vary depending on the nature and complexity of your request. Microsoft strives to provide you with clear and timely communication throughout the process.