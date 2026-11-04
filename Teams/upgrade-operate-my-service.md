---
layout: Conceptual
title: Operations for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/upgrade-operate-my-service
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: landerl
ms.date: 2018-06-04T00:00:00.0000000Z
description: Tasks and activities required for Teams service management, including monitoring service health, and assessing and ensuring network quality and usage
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
locale: en-us
document_id: 0d740bef-f87f-3120-a11b-8b0a9f54ebc6
document_version_independent_id: b7baaf84-dfac-cfd2-d3fa-1c130e97e926
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/upgrade-operate-my-service.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: upgrade-operate-my-service
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/upgrade-operate-my-service.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3b797fe7-e60d-7b7d-6ecf-a23cb85bcf91
---

# Operations for Microsoft Teams - Microsoft Teams | Microsoft Learn

![Upgrade journey diagram, emphasizing the Operational Excellence stage.](media/upgrade-banner-op-excellence.png)

This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you complete your upgrade from Skype for Business server to Teams.

This article gives an overview of the requirements for successfully operating Teams for your organization after you upgrade. By properly operating your Teams services, you can be sure you're providing a high-quality, reliable experience for your organization.

## Introduction to the Operations Guide

The Operations Guide gives you an overview of all the tasks and activities required as part of the service management function for Microsoft Teams.

Service management is a broad topic that covers day-to-day operations of the Microsoft Teams service after it has been deployed and enabled for users. The Teams service encompasses Microsoft 365 or Office 365 and the infrastructure components deployed on-premises (for example, networking).

The notion of service management is most likely not a new concept for most organizations. You might have already implemented processes and tasks that are associated with existing services. That said, you can probably augment your current processes when you plan for service management today to support Teams in the future.

Service management encompasses all the activities and processes involved in managing Teams end to end. As noted earlier, some components of service management—the infrastructure that the Microsoft 365 or Office 365 service itself comprises—are Microsoft's responsibility, whereas you, the customer, are accountable to your users to manage the various aspects of Teams, the network, and endpoints you provide.

The tasks and activities in this guide are grouped into eight categories as depicted in the following diagram. Each of these categories are expanded on in the following sections.

![A diagram depicting a list of categories of tasks and activities.](media/operate-my-service-image1.png)

| ![An icon depicting decision points](media/audio_conferencing_image7.png)Decision points | - Decide how you want to implement operations for Teams. |
| --- | --- |
| ![An icon depicting the next steps](media/audio_conferencing_image9.png)Next steps | - Review the Operations Guide in full.<br>- Implement an operations strategy that aligns with your organization's goals to deliver the quality and reliability of Teams workloads.<br>- Review the Quality of Experience Review guide.<br>- Implement an operations strategy to regularly perform Quality of Experience Reviews to make sure your Teams deployment is operating at its peak capabilities. |

### Operational role mapping

The planning you undertook for operations during the Envision phase is critical, because operations activities begin when the first pilot users are enabled. This guide lists the activities and tasks that must be performed on a daily, weekly, monthly, or as-needed basis to maintain a high-quality Teams deployment. This guide provides knowledge and guidance for how to perform these critical activities and tasks.

One crucial component of a successful deployment is to ensure that the planning you do early in the Envision phase includes determining who's responsible for performing specific activities. After you've figured out which tasks and activities apply to your deployment, they need to be understood and followed by the groups or individuals that you assign to them.

Each team you identify must review and agree on the tasks and responsibilities identified and start preparation. These tasks and responsibilities might include training and readiness, providing updates to the staffing plan, or ensuring that external providers are ready to deliver.

The activities and roles defined in this guide should be valid in most scenarios, but every Teams deployment is unique; therefore, you can use this guide as a starting point to customize the activities and default roles to meet your needs.

Ensure that each accountable team has a good understanding of the activities that are required to run the service. It's critical that each team accepts and signs off on their accountability in your organization before the first pilot begins.

After an agreement is in place, the corresponding teams should start to operationalize their roles.

| ![An icon depicting the next steps](media/audio_conferencing_image9.png)Next steps | - Use this document to facilitate the operational role mapping exercise.<br>- Meet with the respective support teams to assign names to each item in the list of required activities.<br>- Gain acceptance or sign-off on the assigned roles.<br>- Ensure that the corresponding teams have the appropriate training, readiness, and resources to complete the activities required of them. |
| --- | --- |

### Teams service dependencies

Microsoft Teams brings together technologies across Microsoft 365 and Office 365 to provide a hub for teamwork. Examples include:

- Microsoft Entra ID provides authentication and authorization services for Teams.
- Exchange Online provides advanced features like legal hold and e-discovery.
- SharePoint Online provides the ability to share files in channels, and OneDrive for Business provides a mechanism for sharing files within a private chat.

Organizations can also leverage existing investments in on-premises infrastructure. For example, existing on-premises Active Directory accounts can be used for authentication by leveraging Microsoft Entra Connect. Certain versions of Exchange Server can be used in place of Exchange Online.

These technologies come together to provide a rich, collaborative, and intelligent communications suite for users. This tight integration is a key benefit of Teams, but it also drives a requirement for service management across these technologies.

This guide covers the key areas of focus to manage the Teams service. Most likely, you have service management plans in place for the supporting technologies that Teams depends on. If not, you need to establish proper service management plans for those technology components (both on-premises and online) as well. These plans help ensure your users enjoy a high-quality, reliable experience with Teams.

#### References

- [Overview of Microsoft Teams](teams-overview)
- [How Exchange and Microsoft Teams interact](exchange-teams-interact)
- [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact)
- [Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability)

## Operations Guide activities

The following sections give an overview of the activities that are required to successfully operate the Microsoft Teams service. They include reference to tools, contextual information, and additional content to help you understand the activity and to assist in readiness initiatives.

## Monitor service health

It's important that you understand the overall health of the Microsoft Teams service so that you can proactively alert others in your organization of any event that affects the service. As described earlier, Teams is dependent on other Microsoft 365 and Office 365 services, such as Microsoft Entra ID, Exchange Online, SharePoint Online, and OneDrive for Business. Because of this dependence, it's equally important that you monitor the health of the dependent services.

Incorporate this activity into your incident management process to proactively inform users, the helpdesk, and your operations teams to prepare to handle user escalations.

The following sections describe the tools that you can leverage to monitor for [service incidents](/en-us/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) that affect the Teams service. A summary of the benefits of each tool, and when you should use each one, is included in the following table.

| Monitoring Tool | Benefits | When to use |
| --- | --- | --- |
| Microsoft 365 admin center | Available from any device with a supported browser. | Use when you don't need real-time notifications. |
| Microsoft 365 Admin app | Provides push notifications to your mobile device. | Use when you need to be notified of service incidents while you're on the go. |
| Microsoft System Center | Integration with Microsoft System Center. | Use when you need advanced monitoring capabilities and notification support. |
| Microsoft 365 Service Communications API | Programmatic access to Microsoft 365 or Office 365 service health. | Use when you need integration with a third-party monitoring tool or want to build your own solution. |

Note

Only individuals who are assigned the **global admin** or **service administrator** role can view service health.

### Monitoring with the Microsoft 365 admin center

The [Microsoft 365 admin center](https://portal.office.com/) provides a [Service Health dashboard](https://portal.office.com/adminportal/home#/servicehealth) where you can view the current health of the Teams service in addition to dependent services.

### Monitoring with the mobile app

The Microsoft 365 Admin app is available on Apple iOS, Android, and Windows (PC and mobile). The app provides administrators information about service health and upcoming changes. The app supports push notifications that can alert you almost immediately after an advisory has been posted. These push notifications help you stay current on the status, health, and any upcoming changes to the service. The notification support makes it the recommended monitoring tool for administrators. For more information, see:

- [Microsoft 365 Admin Mobile App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)
- [Download the Microsoft 365 Admin Mobile App](https://products.office.com/business/manage-office-365-admin-app)

### Monitoring with Microsoft System Center

Microsoft System Center is an integrated management platform that helps you manage datacenter, client devices, and hybrid cloud IT environments. Microsoft 365 or Office 365 administrators who use System Center now have the option to import the Management Pack, which enables them to view all service communications within Operations Manager in System Center. Using this tool gives you access to the status of your subscribed services, active and resolved service incidents, and your Message Center communications (upcoming changes). For more information, refer to the following [blog post](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/).

If you leverage System Center to monitor Teams service health (and dependent services), you can further customize the management pack to alert or notify specific groups or individuals who have been identified to react to incidents. These groups can include service owners, helpdesks, second-level and third-level support groups, and incident managers in your organization.

### Monitoring for advanced scenarios

You can monitor service health and upcoming changes by leveraging the Service Communications API to access service health and changes programmatically. Use this API to create your own monitoring tool, or connect your existing monitoring tools to Microsoft 365 or Office 365 service communications, potentially simplifying how you monitor your environment. For more information, see [Microsoft 365 or Office 365 for Enterprise developers](/en-us/office/developer-program/microsoft-365-developer-program-faq).

### Daily/weekly/monthly/as-needed tasks

| Activity | Description | Cadence |
| --- | --- | --- |
| Monitor service health | Proactively monitor Microsoft Teams service health, (and dependent services) by using the tools available. Dependent services include: Exchange Online, SharePoint Online, OneDrive for Business, Microsoft Entra ID. | Real-time |
| Incident notification | Notify internal stakeholders of events that affect the Teams service. Internal stakeholders can include users, helpdesks, and incident managers. | As needed |

### References

- [How to check Microsoft 365 or Office 365 service health](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)
- [Verify service health for Microsoft Teams](service-health)
- [Service Health and Continuity](/en-us/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

## Manage organizational change

Microsoft Teams is a cloud-based service. With that comes the ability to provide new features and functionality at a rapid pace. Delivering ongoing innovation provides an obvious benefit to organizations, but these changes need to be managed appropriately within your organization to avoid user resistance or escalations to your helpdesk.

Updates to Teams are rolled out automatically to your users. Your users always have the latest client and features available in the Teams service. It's not possible to manage the rollout of Teams updates to your users, therefore it's critically important to manage change through effective communication, training, and adoption programs. If your users are aware of the change, educated about the benefits, and empowered to leverage the new capabilities, they're able to adapt more quickly and welcome the change.

### Monitoring for change

The first step in change management is monitoring the changes that are planned for Teams. The best source for monitoring these changes is the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap), which lists features that are currently in development, being rolled out to customers, or have fully launched. You can search for Teams-specific features by using the filter provided, or you can download the roadmap to an Excel file for further analysis. For each feature, the roadmap gives a short description, along with the anticipated release date.

All features that are released are documented in the [Release Notes for Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de). Here you'll find a list of features that were released for desktop, web, and mobile devices. The same set of release notes are also available on the **What's new** tab in [Help](get-help-in-microsoft-teams).

Become familiar with the resources available, and ensure that you assign applicable owners to monitor for change.

### Planning for change

Now that you're aware of upcoming changes to the Teams service, the next step is to prepare and plan accordingly. Assess each change to determine which changes require communication to users, awareness campaigns, training for support teams or users, or feature evaluation and adoption campaigns. This role is the primary role of a change management team in your organization. Below is a collection of sample tables that can help you plan for change.

#### Feature: Meeting recording (Release date: January 2018)

**General track**

| Change readiness | Status | Notes/next steps | Owner |
| --- | --- | --- | --- |
| Legal review | Completed | This feature is a prerequisite to onboarding the training team. | Project team |

**Technical change management**

| Change readiness | Status | Notes/next steps | Owner |
| --- | --- | --- | --- |
| IT changes required | Yes | Admin needs to enable recording for identified users only. | Support team |
| Technical readiness complete | Yes |  | Support team |

**User change management**

| Change readiness | Status | Notes/next steps | Owner |
| --- | --- | --- | --- |
| User impact | Low |  |  |
| User readiness required | Yes |  |  |
| Communications ready | No | Communication email has been drafted—pending review. | Communications Team |
| Training ready | Yes | Training leverages existing Microsoft video. | Training Team |

**Status track**

| Change readiness | Status | Notes/next steps | Owner |
| --- | --- | --- | --- |
| Release status | In progress | Pending review by executive sponsor. | Change Management Team |
| Release sign-off |  |  |  |
| Release date |  |  |  |

For more information about planning for change management with Teams, see [Create a change management strategy for Microsoft Teams](change-management-strategy).

### Daily/weekly/monthly/as-needed tasks

| Activity | Description | Cadence | Team assigned |
| --- | --- | --- | --- |
| Monitor for change | Monitor for upcoming changes to Microsoft Teams service. | Daily |  |
| Planning for change | Evaluate and plan for new features and capabilities, including communication plans, awareness campaigns, and training. | As needed |  |
| User readiness | Perform targeted communication, awareness, or training campaigns to ensure users are ready for the upcoming change. | As needed |  |
| Support team readiness | Perform targeted communication, awareness, or training campaigns to ensure the support team is ready. Support teams can include the "white glove" team, helpdesks, Tier 2 or Tier 3 support, external partners, and so on. | As needed |  |

## Assess Teams usage

After the initial pilot begins, it's critical to establish a regular cadence for measuring actual Teams usage. This cadence enables your organization to gain insights into how actual usage aligns with the usage you predicted during the Envision phase. Although this section focuses on Teams usage, this cadence should be part of a broader effort to measure and assess Microsoft 365 or Office 365 usage overall.

Reviewing usage frequently early in the deployment gives you the opportunity to:

- Validate whether users are using Teams.
- Identify potential adoption challenges before they create critical issues across the organization.
- Understand whether there are discrepancies between the Envision phase requirements and actual usage.

If usage isn't what you expect, it could be due to a deployment issue, or the adoption plan isn't being executed properly, or some other problem. Depending on the actual reason behind the low usage, the administrator must collaborate with the related teams to help remove usage barriers.

### Measuring usage with the Microsoft 365 admin center

Usage data from Teams is available in the Reporting dashboard. Teams usage data can be found in three different reports. The first report provides a cross-product view of how users communicate and collaborate by using the various services in Microsoft 365 or Office 365. This report can be found here: [Microsoft 365 Reports in the admin center - Active Users](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D).

The other two reports are Teams-specific, and they provide further detail about Teams usage from a user and device perspective. Both reports can be found here:

- [Microsoft Teams device usage report](/en-us/microsoftteams/teams-analytics-and-reports/device-usage-report)
- [Microsoft Teams user activity report](/en-us/microsoft-365/admin/activity-reports/microsoft-teams-user-activity-preview)

#### Required permissions

The usage reports in the admin center can be accessed by people who have been assigned a **Global administrator** role, or a product-specific admin role (**Exchange administrator**, **Skype for Business administrator**, **SharePoint administrator**).

In addition, the **Reports reader** role is available for users who require access to the reports, but don't perform any tasks that require administrator-level permissions. You assign this role to provide usage reports to anyone who is a stakeholder, to monitor and drive adoption. For more information about the different roles available, see [About Microsoft 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### Assessing usage

After you've used the Reporting dashboard to measure usage, it's important to compare the measured usage against any key success indicators (KSIs) that you defined during the project's Envision phase. You can define a KSI that might be defined as active usage, or one that's indirectly linked to active usage.

It's important to identify any variances between actual and planned usage before resuming the rollout to additional sites or users. You may identify organizational learnings as part of this activity that you can leverage to ensure that the next batch of sites or users don't encounter the same issues.

First, pinpoint whether you have an adoption or technical problem. Begin by investigating the items below, in order, to determine where the problem is.

1. Validate quality by performing a [Quality of Experience Review](upgrade-monitor-quality).
2. Work with the helpdesk team to check that there are no trending technical issues preventing users from accessing or using the service. If issue trends do exist, use the endpoint troubleshooting section later in this article to try to solve the problem before engaging support.
3. Work with the training and adoption team to gather direct feedback from users (see Assess user sentiment later in this article), and to check the effectiveness of awareness and adoption activities.

### Daily/weekly/monthly/as-needed tasks

| Activity | Description | Cadence |
| --- | --- | --- |
| Measure usage (enablement phase) | Measure and assess Teams usage as sites continue to be onboarded during the enablement phase. Address usage issues as required. | Weekly |
| Measure usage | Measure and assess Teams usage in the Drive Value phase (after deployment has been completed). Address usage issues as required. | Biweekly |
| (drive value phase) |  |  |
| Update adoption plan | Update your adoption plan based on how measured usage compares to your planning targets. | As needed |

### References

- [About the Microsoft 365 admin center](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)
- [Activity Reports in the Microsoft 365 admin center](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

## Assess user sentiment

Understanding user sentiment can act as a key indicator for gauging the success of your Teams deployment. User feedback can drive changes in your organization, which might include changes to your communication plans, training programs, or the way that you offer support to your users.

It's important to get feedback early and continue with assessing user sentiment throughout the lifecycle of the project and beyond. Use the following guidance to determine the interval in which your organization can seek out feedback:

- **Beginning of the project**: By assessing user sentiment at the beginning of the project, you can get an early view into how your users feel about their Teams experience.
- **After major milestones**: By collecting feedback throughout the project lifecycle, you can gauge user sentiment on a continuous basis and make changes as needed. This feedback is especially useful after major milestones.
- **Project conclusion**: Assessing user sentiment at the end of a project tells you how well you've done and where work still needs to be done, and allow you to compare results against the previous survey.
- **Ongoing**: Continue to measure user sentiment indefinitely. Changes in user sentiment might be due to changes in your organization's environment or changes in the Teams service. By gauging user sentiment at regular intervals, you can understand how well your service management teams are performing and how your organization is responding to changes in the Teams service.

User sentiment can be assessed through many different methods. These can include email surveys, in-person or telephone-style interviews, or simply creating a feedback channel in Teams or Viva Engage. For more information, see [Best practices for user feedback methods in Microsoft Teams](best-practices-feedback).

You can also use an industry-wide approach to assess user sentiment called net promotor score (NPS), which is described in the following section.

### NPS

Net promoter score (NPS) is an industry-wide customer loyalty metric and a good approach to use to assess user sentiment. NPS can be calculated by asking two questions: "How likely are you to recommend Teams to a colleague?", followed by the freeform question, "Why?"

NPS is an index ranging from –100 to 100 that measures a customer's willingness to recommend a company's product or service. NPS is based on an anonymous survey that's delivered to users through email or other electronic means. NPS measures the loyalty between a provider and a consumer. It consists of only one question, which asks users to rate their experience from 1 through 10, with the option of providing additional comments. Users are then classified based on the following ratings:

- 9 or 10 are Promoters: Loyal enthusiasts who promote your service and fuel others.
- 7 or 8 are Passive: Satisfied but unenthusiastic, vulnerable to another service or offering.
- From 1 through 6 are Detractors: Unhappy customers who can damage your service and impede growth.

![A diagram that demonstrates the NPS scale.](media/operate-my-service-image2.png)

Although the base NPS number is useful, you get the most value from analyzing user comments. They help you understand why the user would (or wouldn't) recommend Teams to others. These comments can provide valuable feedback to help the project or service management teams understand the adjustments necessary to provide a quality service.

To provide NPS surveys to your organization, you can leverage your favorite online survey tool.

### Daily/weekly/monthly/as needed tasks

| Activity | Description | Cadence | Team assigned |
| --- | --- | --- | --- |
| Assess user sentiment | Capture and assess user sentiment by using surveys or interviews, or through a feedback channel in Teams or Viva Engage. | As needed |  |
| Update adoption plans | Drive change in your organization based on user feedback. You could see changes to your communication plans, training programs, or the way that you offer support to your users. | As needed |  |

### References

- [Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)
- [Using Viva Engage to collect feedback](https://techcommunity.microsoft.com/t5/yammer-Blog/The-Microsoft-Teams-team-uses-yammer/ba-p/55210)
- [Best practices for user feedback](best-practices-feedback)

## Manage network quality

Many core planning elements go into optimizing, right-sizing, and remediating your network infrastructure to ensure a high-quality, efficient path to the Microsoft Teams service. The planning tasks and requirements are covered in our [network readiness](prepare-network) guidance. Networks often evolve over time due to upgrades, expansion, or other business requirements. It's important that you account for your requirements for Teams in your network planning activities.

Although network planning is a critical aspect of a Teams deployment, it's equally important to ensure the network remains healthy and stays current, based on changing business or technical requirements.

To ensure the health of your network, a number of operations activities need to be performed at regular intervals.

### Daily/weekly/monthly/as-needed tasks

| Activity | Description | Cadence | Team assigned |
| --- | --- | --- | --- |
| Monitor Microsoft 365 or Office 365 IPs and URLs | Monitor any changes to the [Office 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges) by using the provided [RSS feed](https://go.microsoft.com/fwlink/p/?linkid=236301) and initiate a change request to applicable networking groups. | Daily |  |
| Update the network based on changes to Microsoft 365 or Office 365 IPs and URLs | Make updates to the applicable network components (firewalls, proxy servers, VPNs, client-side firewalls, and so on) to reflect changes to the [Office 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges). | As needed |  |
| Provide building data | Provide updated subnet information to the quality champion (or relevant stakeholders) to ensure that the [building definitions in CQD](/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) are kept up to date. | As needed |  |
| Implement change | Implement changes on the network to support changing Teams business and technical requirements. Network elements can include:<br>- Firewalls<br>- VPNs<br>- Wired and Wi-Fi networks<br>- Internet connectivity and ExpressRoute<br>- DNS | As needed |  |
| Network monitoring and reporting | Monitor the network end to end for availability, utilization, and capacity trends by using your existing third-party network management tools and reporting capabilities available from your network providers. Use trending data for network capacity planning. | Daily, weekly, monthly |  |
| Capacity planning | Collaborate with the Teams service owners to understand changing business and technical requirements that might drive additional capacity changes. | As needed |  |
| Network troubleshooting and remediation | Assist the Teams helpdesks, service owners, and key stakeholders to troubleshoot and remediate issues to related to Teams connectivity, reliability, or quality. Network elements can include:<br>- Firewalls<br>- VPNs<br>- Wired and Wi-Fi networks<br>- Internet connectivity and ExpressRoute<br>- DNS | As needed |  |
| Disaster recovery and high availability testing | Perform regular high availability and disaster recovery testing on the network infrastructure to ensure that it meets the stated service level objectives (SLOs) or service level agreements (SLAs) for the Teams service. | Monthly |  |

### References

- [Office 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges)
- [Building data schema](/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

## Assess and ensure quality

All organizations need a group or individual to be accountable for quality. This role is the most important role in service management. The Quality Champion role is assigned to a person or group who is passionate about their users' experience. This role requires the skills to identify trends in the environment and the sponsorship to work with other teams to drive remediation. The best candidate for the quality champion is typically the customer service owner. Depending on the organization's size and complexity, this role could be given to any person or group with a passion for ensuring a high-quality user experience.

The quality champion leverages existing tools and documented processes, such as Call Quality Dashboard (CQD) and [Improve and monitor call quality for Teams](monitor-call-quality-qos), to monitor user experience, identify quality trends, and drive remediation where needed. The quality champion should work with the respective teams to drive remediation actions and report to a steering committee about progress and any open issues.

[Improve and monitor call quality for Teams](monitor-call-quality-qos) includes activities that assess and provide remediation guidance in key areas that have the greatest impact on improving user experience. The guidance provided in the Quality Experience Review Guide focuses on using CQD Online as the primary tool to report and investigate each area, with a focus on audio to maximize adoption and impact. Any optimizations made to the network to improve the audio experience also directly translates to improvements in video and desktop sharing.

We strongly recommend that you nominate the quality champion early on. After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos) and associated training materials.

### Daily/weekly/monthly/as-needed tasks

| Activity | Description | Cadence |
| --- | --- | --- |
| Nominate and train quality champion(s) | Nominate and train a quality champion. | As needed |
| Perform Quality of Experience Reviews (QERs) | Perform a QER to identify trends in quality and reliability, review against defined targets, and report out to key stakeholders in the organization. | Monthly (weekly during deployments) |
| Drive remediation | Coordinate remediation efforts across the organization based on the QER assessments and findings. | As needed |
| Update building data in CQD | Update or add new building definitions in CQD when changes are made to the network (see [Upload Building information](/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | As needed |
| Fill the Quality Champion role | End-to-end responsibility for quality in the organization. This responsibility includes:<br>- Ensure that the QER is being conducted regularly.<br>- Report out to key stakeholders on quality status.<br>- Ensure the building data definitions are up to date.<br>- Coordinate remediation efforts across the organization to ensure that users have a high-quality experience with Teams. | Daily |

### References

- [Upload Building information](/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)
- [Improve and monitor call quality for Teams](monitor-call-quality-qos)

## Manage endpoints

Microsoft Teams endpoints can be defined as any PC, Mac, tablet, or mobile (or any other) device running the Teams client. The term *endpoint* not only encompasses the device itself, but how a user connects to the device—for example, by using the device's built-in mic or speaker, earbuds, or an optimized headset. After they're deployed, endpoints must not be forgotten. The Teams endpoints require ongoing care and maintenance. The following sections describe specific areas to focus on.

### Endpoint requirements

One of the key benefits of Teams is that the client is kept up to date automatically. The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle. The Teams mobile apps are kept current through their respective app stores.

The Teams client has minimum requirements in terms of the underlying software platform. These requirements might change over time, and therefore it's important that you monitor them for changes. For example, the Teams client has a minimum iOS version. If the client uses an internet browser, the browser needs to be kept current as well. A list of supported platforms can be found in [Teams client system requirements](teams-client-system-requirements).

### Endpoint firewalls

Client-side firewalls can have a significant impact on the user experience. Client-side firewalls can affect call quality and even prevent a call from being established. After the appropriate exclusions on the client firewall have been configured, they need to be kept up to date based on the information in [Office 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges). Your third-party vendor has specific guidance for how to update the exclusions.

### Wi-Fi drivers

Wi-Fi drivers might be problematic. As an example, a driver might have very aggressive roaming behaviors between access points that can induce unnecessary access-point switching, leading to poor call quality. A poorly performing Wi-Fi driver might be discovered through a Quality of Experience Review (see [Improve and monitor call quality for Teams](monitor-call-quality-qos) for more detail). It’s essential to implement a quality-driven process that monitors new Wi-Fi drivers and ensures that they're tested before being deployed to the general user population.

### Endpoint management

A catalog of supported endpoints and interface devices (such as headsets) should be available and maintained. This catalog includes a list of approved devices that were selected and validated as part of the Envision and Onboard phases. Typically, specific devices are selected for each persona type in your organization to meet the needs of that persona's attributes. All endpoints have a lifecycle, and you need to manage the vendor contracts, warranty, replacement, distribution, and repair policies associated with these devices.

### Endpoint troubleshooting

Even if you've followed the previous guidance, users in your organization still might run into issues with Teams. Although the problem might not be with the endpoint itself, the symptoms of the issue are typically surfaced through the client to the user. The following guidance is intended to provide general steps you can take to resolve the issue; it's not meant to be a comprehensive troubleshooting guide. The steps are provided in a specific order, but they don't have to be followed explicitly and might not be applicable, depending on the nature of the issue.

1. **Validate service health:** The issue a user might be experiencing can be related to an event that negatively affects the Teams service or its dependent services. As a first step, we recommend that you confirm there are no active service issues. Consult [How to check Microsoft 365 service health](/en-us/office365/enterprise/view-service-health). Remember to check for the status of dependent services (for example, Exchange, SharePoint, OneDrive for Business). Monitoring for service health is discussed in more detail in the previous section, Monitor service health.
2. **Validate client connectivity:** Connectivity issues cause functionality or sign-in issues in Teams. We recommend (especially for new sites or locations) that you validate connectivity to the service. Ensure the following [Office 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges) guidance is followed for each site. You can leverage the [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to perform a connectivity test to validate that the media ports have been opened correctly for Teams capabilities. Detailed steps on how to run the connectivity tests are provided in the [network readiness](prepare-network) guidance.
3. **Check the known issues list:** Consult [Teams Troubleshooting](/en-us/MicrosoftTeams/troubleshoot/teams) to determine whether the user has been negatively affected by one of these issues. Follow the workaround provided (if there is one) to resolve the issue.
4. **Visit the Microsoft Teams community:** The [Microsoft Teams community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) offers dedicated spaces for Teams. The Teams community provides a discussion list, blog posts, and announcements centered around Teams. You can post a question or search previous discussions for solutions to your issue.
5. **Contact Microsoft Support:** You can contact Microsoft Support for issues with Teams online or by phone. For information, see [Contact support for business products - Admin Help](/en-us/microsoft-365/admin/contact-support-for-business-products). For Premier customers, support requests can be initiated by following the guidance at [Contact support for Microsoft Teams (Premier customers)](https://support.microsoft.com/premier/contacts).

### Daily/weekly/monthly/as-needed tasks

| Activity | Description | Cadence |
| --- | --- | --- |
| Endpoint requirements | Ensure that the Teams endpoint continues to meet all the software requirements for Teams listed in [Teams client system requirements](teams-client-system-requirements). | Monthly |
| Endpoint firewalls | Maintain the appropriate exclusions on the endpoint firewall based on the information in [Office 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges). Your third-party vendor has specific guidance for how to maintain the exclusions. Subscribe to the [RSS feed](https://support.office.com/o365ip/rss) to be notified automatically of changes. | As needed |
| Wi-Fi drivers | Test and update Wi-Fi drivers on the PC. Validate the results by using CQD ([Improve and monitor call quality for Teams](monitor-call-quality-qos)). | As needed |
| Endpoint management | Maintain the catalog of supported endpoints and interface devices (such as headsets). Manage vendor contracts, warranty, distribution, replacement, and repair policies. | Monthly |
| Endpoint troubleshooting | Troubleshooting tasks can include verifying connectivity, consulting the known issues list, log gathering, analysis, and escalation to Microsoft Support or third-party vendors. | As needed |

### References

- [Office 365 URLs and IP address ranges](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges)
- [Microsoft Teams client](teams-client-desktop-admin)
- [Microsoft Teams community](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)
- [Teams Troubleshooting](/en-us/MicrosoftTeams/troubleshoot/teams)
- [Verify service health for Microsoft Teams](service-health)
- [Contact support for business products - Admin Help](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Contact Premier support](https://support.microsoft.com/premier/contacts)
- [Troubleshooting Teams video](https://www.youtube.com/watch?v=4O4d_7uZTQY)

## Manage Teams

After the Microsoft Teams service has been deployed, you need to perform several activities relating to its administration. The activities range from administering the service and individual users to capacity planning and provisioning licensing and telephone numbers. The following sections cover some of these common administration tasks.

### Service administration

The Teams service has multiple settings that can be configured tenant-wide. Changes made to the tenant settings affect all users who have been enabled for Teams. For a detailed list of these settings, see [Manage Microsoft Teams settings for your organization](enable-features-office-365).

### User administration

To support users, an organization might require any number of related tasks—the specific tasks vary from one organization to the next. Ultimately, these tasks need to be managed by a support team that has been assigned these operational duties. The following tasks are commonly required to support users in Teams.

#### General tasks

[Manage user access to Microsoft Teams](user-access)

### Team creation (optional)

By default, all users with a mailbox in Exchange Online have permissions to create Microsoft 365 groups and, therefore, a team in Microsoft Teams. If you want to have tighter control and [restrict the creation of new teams](assign-roles-permissions) (and thus the creation of new Microsoft 365 groups), you can delegate group creation and management rights to a set of administrators. If your organization wants to pursue this option, see the process described in this article to allow users to submit requests that are processed by an assigned team.

### Daily/weekly/monthly/as-needed tasks

| Activity | Description | Cadence |
| --- | --- | --- |
| Service administration | Administration of tenant-wide Teams settings. | As needed |
| User administration | Administration of user-based settings and licensing in Teams. | As needed |
| License management | Plan for current and future needs for both user and consumption-based licensing (Calling Plans and Communication Credits) by leveraging the [PSTN usage report](/en-us/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) and [PSTN minute pools](/en-us/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) report. | Weekly |
| Telephone number management | Manage the telephone numbers available for future growth, and adjust inventory levels to meet your organizational needs. | Weekly |
| Team creation (optional) | Review and process requests for team creation. | As needed |