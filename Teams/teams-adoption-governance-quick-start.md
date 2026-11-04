---
layout: Conceptual
title: Governance quick start for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-adoption-governance-quick-start
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: Admin
ms.topic: quickstart
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: karuanag
ms.date: 2026-07-21T00:00:00.0000000Z
ms.localizationpriority: medium
search.appverid: MET150
description: Quick start that covers the key decisions you need to make for phase 2 of your Microsoft Teams adoption plan.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
locale: en-us
document_id: 630d8bc9-ba1d-8d41-f3b1-00a1ea03a43d
document_version_independent_id: 3d15b49e-5fe1-dba7-9ba8-9c4eac728e14
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-adoption-governance-quick-start.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-adoption-governance-quick-start
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-adoption-governance-quick-start.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 100fceaa-6635-afc0-7f1a-e2c790ddcf8a
---

# Governance quick start for Microsoft Teams - Microsoft Teams | Microsoft Learn

The following activities happen simultaneously, and they might involve all or part of your key team. As a best practice, defer large-scale governance and security conversations for after you complete your initial experimentation with Teams. It's important to understand how governance decisions might impact the end-user experience and will simplify the decisions you need to make at that later date. For this phase there are some decisions that need to be made. To successfully make them you first need to answer the following questions:

- Which stakeholder from your earlier assessment is a good candidate to participate in this limited business onboarding?
- Has this individual (or group of individuals) suggested use cases that would be good candidates for this phase?
- Do they have enough interest from employees in their organization to be early adopters and give you meaningful and regular feedback?

To learn more, read [Plan for governance in Teams](plan-teams-governance) and [Plan for lifecycle management in Teams](plan-teams-lifecycle).

## ![An icon representing a decision point.](media/teams-adoption-decision-icon.png)Decisions

Make the following decisions (at this point, these decisions apply only to Phase 2):

### Decision 1: Who can create teams

For the purposes of this phase you can restrict who is able to create teams to the early adopter population in addition to your core project team. This allows your early adopters to create other teams if needed. Monitoring this behavior gives you the key information for your broad deployment.

### Decision 2: Teams naming conventions

You'll likely want to implement some naming conventions for your broad deployment of Teams, and check for duplicate names. In Phase 2 we suggest that you implement a manual naming convention for your initial projects only. The best practice for this is to conduct an interactive onboarding with the early adopter project team and allow them to select their own name. This gives you insight into how employees think about their work and will be essential in creating a larger scale naming convention at a later time. (Additional information on the elements of an interactive onboarding appears later in this guide.) Here is the link to learn how to apply these naming conventions - [Enforce a naming policy on Microsoft 365 groups & Teams](/en-us/entra/identity/users/groups-naming-policy).

### Decision 3: Guest access

Depending on the scope and type of your project and the nature of your industry, enabling secure collaboration with partners or vendors may be an essential capability you want to test. You can limit who can add guests to teams by using the appropriate tenant controls, and limit which teams are open to guests by using sensitivity labels. You can additionally ensure that guests adhere to organizational security requirements such as the use of Multi-Factor Authentication (MFA).

### Decision 4: Approved apps

The best case use of Teams includes the integration of other apps into the experience. At a minimum your technical team should enable the first party and featured apps in your Teams experience. Depending on your use case and other apps used in your organization, you may opt to include additional apps as a part of your controlled experiment. Be sure to vet any third party apps to ensure they adhere to your organization’s security and compliance requirements.

### Decision 5: Are meetings included in your test?

The Teams meeting experience is high quality, supports video chatting, and brings your employees together to be more effective. Consult with your technical team to make sure that your environment is ready to include simple VoIP meetings. Enabling audio conferencing or voice services would normally be excluded from this phase of your experimentation; however, that depends on your core project team, your technical readiness, and the state of other voice/meeting services in your organization. Technical readiness should include things such as meeting room equipment, end-user devices and accessories, and the network. We recommend including video chats and VoIP meetings in your experimentation to gain more value from your Teams implementation. Refer to this document to understand the tenant configurations for best practices - [Best Practices configuration dashboard for Teams meetings](/en-us/microsoftteams/best-practice-dashboard)

### Decision 6: Content management and structure

Teams works best when users work end-to-end within the platform - instead of requiring them to continually switch back to legacy systems and services - and offers new ways of working that differ from how users are accustomed. As part of your experiment, work with your participants to consider team structures and channels that embrace the multi-modal ways of collaborating within Teams, and avoid simply replicating existing folder and storage structures. Additionally, consider any compliance requirements for content stored outside of existing supported systems such as records management or backup systems.

### Decision 7: Data security

In preparation for your broad deployment you may opt to use security labels to classify the types of teams in your environment. For the purposes of this experiment we recommend that you refer to [Plan for Governance in Teams](plan-teams-governance) and ensure that a basic retention policy has been set on Teams data in your Microsoft 365. You may need to coordinate this work with your technical team because Microsoft 365 administrator rights are required to complete this work.

### Decision 8: Length of your experiment

A successful Teams implementation proceeds at a healthy pace to ensure appropriate momentum, focus, and learnings. We recommend that this phase of your project be 60 days in length to ensure that your early adopters complete sufficient business cycles. Extending experimentation for too lengthy a time increases the risk of a failed change program; however, this time will vary for every organization.

![An icon representing the next step.](media/teams-adoption-next-icon.png) Next: [Define usage scenarios](teams-adoption-define-usage-scenarios)