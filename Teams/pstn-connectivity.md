---
layout: Conceptual
title: PSTN connectivity options - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/pstn-connectivity
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.date: 2026-07-31T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: teams-calling
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
- highpri
- Tier1
ms.reviewer: filippse
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Learn more about Teams calling (PSTN connectivity) options and the decisions that you'll make for your organization.
locale: en-us
document_id: 0d3761e4-a357-f288-6a6e-ed6cb14a5c5c
document_version_independent_id: c6f9667a-8f1f-09f4-7478-738cc6d98e81
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/pstn-connectivity.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: pstn-connectivity
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/pstn-connectivity.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b7b8729c-1385-1ad5-7a0e-b04fcb5edb9c
---

# PSTN connectivity options - Microsoft Teams | Microsoft Learn

Microsoft Teams Phone enables organizations to connect phone numbers to Microsoft Teams, whether to support calling through Voice applications like Auto Attendants and Call Queues, or allowing users to make and receive Public Switched Telephone Network (PSTN) calls from the Teams app across desktop, mobile devices, certified Teams phones, and meeting room devices. Organizations can choose the PSTN connectivity option that best fits their business needs—from a fully Microsoft-managed solution to using an existing telecommunications provider or custom telephony infrastructure. Multiple PSTN connectivity options can also be used within the same Teams tenant to support different users, locations, and business requirements.

To learn more about Microsoft Teams Phone, including its features, capabilities, and business benefits, see the [Microsoft Teams Phone—Cloud Phone System](https://www.microsoft.com/microsoft-teams/microsoft-teams-phone) page.

This article describes the available PSTN connectivity options for Teams Phone and helps you choose the solution that best fits your organization's calling requirements.

Note

If you're unfamiliar with PSTN, see **What is the Public Switched Telephone Network (PSTN)?**.

## PSTN connectivity options

Microsoft’s Teams Phone is a highly flexible platform, supporting several methods to connect with the PSTN, and you can equip your tenant with as many of the available PSTN integrations as you’d like.

Choosing the right PSTN connectivity option depends on your organization's business and technical requirements. Factors such as how you want to manage your telephony services, whether you have an existing telecommunications provider, your users' calling patterns, and any existing telephony infrastructure can all influence which solution is the best fit.

![Diagram showing Teams Phone Comparison Chart.](media/pstn-connectivity/teams-phone-chart.png)

The highlights of the four PSTN connectivity models for Teams are as follows:

- [**Microsoft Teams Calling Plan**](calling-plans-for-office-365). A cloud based Phone System solution with Microsoft as your operator. Calling Plans are Microsoft licenses that can be tailored to the calling behavior of your user base. PSTN access, phone numbers, emergency screening service in the U.S., and support for your telephone service come from Microsoft, with a 99.999% reliability Service Level Agreement (SLA).

    - This option requires a Microsoft Teams Calling Plan license.
- [**Operator Connect**](operator-connect-plan). With the Operator Connect offer, take advantage of certified third-party landline operators who have already completed the PSTN integration with Microsoft. All that is required is a subscription from the certified service provider of your choice. You can easily enable their access to your tenant in the Teams Admin Center and assign their phone numbers to your Teams users. PSTN access, phone numbers, emergency screening service in the U.S., support, SLA and other products for your telephone service come from the certified Operator Connect partner.

    - This option requires a contract with a third-party service provider.
    - For a list of operators participating in the Microsoft Operator Connect Program and the countries or regions where their service is available, see the [Microsoft 365 Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/).
    - For this PSTN connectivity solution in India, see [Operator Connect for India](operator-connect-india-plan).
- [**Teams Phone Mobile**](operator-connect-mobile-plan). With Microsoft Teams Phone Mobile, take advantage of certified third-party mobile operators, who have already completed the PSTN integration with Microsoft. All that is required is a subscription from the certified mobile operator of your choice. You then administer mobile numbers that are assigned to the user’s mobile SIM to also be assigned as the user’s Teams phone number. PSTN access, phone numbers, emergency screening service in the U.S., support, SLA, and other products for your telephone service come from the certified Teams Phone Mobile partner.

    - This option requires a contract with a third-party service provider.
- [**Direct Routing**](direct-routing-plan). With the Direct Routing model, you can use any PSTN operator. Integration of your preferred PSTN operator’s access to your tenant is achieved through a certified Session Border Controller (SBC) that is procured, installed, and managed by you, your integrator, or a Direct-Routing-as-a-Service (DRaaS) provider. PSTN access, phone numbers, emergency screening service in the U.S., support, SLA, and other products for your telephone service come from a combination of your PSTN partner and you.

    - This option requires a contract with a third-party service provider and a session border controller solution.

Note

Teams Phone supports different phone number types depending on the PSTN connectivity option you use. Microsoft Calling Plan, Operator Connect, and Direct Routing support **user phone numbers**, **Audio Conferencing numbers**, and **voice application numbers** (such as Auto Attendants and Call Queues). Teams Phone Mobile supports **user phone numbers only** and doesn't support Audio Conferencing or voice application numbers.

## PSTN connectivity types comparison

The following table provides a high-level comparison of the available PSTN connectivity options for Teams Phone to help you determine which solution best fits your organization's needs.

| Feature | Microsoft Calling Plan | Operator Connect | Teams Phone Mobile | Direct Routing |
| --- | --- | --- | --- | --- |
| **Ideal for** | Organizations that want a fully Microsoft-managed calling solution with the simplest deployment experience. | Organizations that want to work with a participating telecommunications provider while managing users and phone numbers in Microsoft Teams. | Organizations with mobile-first employees who want one business phone number across both Microsoft Teams and their mobile devices. | Organizations that need advanced telephony integration, existing infrastructure support, or maximum deployment flexibility. |
| **Supports user phone numbers** | ✔ | ✔ | ✔ | ✔ |
| **Supports Audio Conferencing and voice application numbers** | ✔ | ✔ | ✖ | ✔ |
| **Management model** | Microsoft-managed | Shared between your participating telecommunications provider and Microsoft Teams | Participating mobile operator | Customer-managed Session Border Controller (SBC) |

## Use more than one PSTN connectivity type

You can also choose a combination of options, which enables you to design a solution for a complex environment and you can manage the PSTN integrations over time, in any order. For example, you might use an approach where you:

1. Set up **Microsoft Calling Plans** with *Shared Calling* for everyone
2. Circle back with more prescriptive PSTN connectivity options for different persona types in your enterprise, for example:
    1. **Teams Phone Mobile** for *mobile workers*,
    2. **Operator Connect** for *knowledge workers*, and
    3. **Direct Routing** for *workers in remote regions*.

Note

Organizations can use the same PSTN connectivity option with multiple operators or combine multiple PSTN connectivity options to meet different business and regional requirements. This flexibility helps support different user personas, geographic regions, and connectivity requirements within the same organization.

## What is the Public Switched Telephone Network (PSTN)?

The Public Switched Telephone Network (PSTN) is the global network of telephone lines, mobile networks, and switching infrastructure that enables telephone calls between phone numbers around the world.

Microsoft Teams Phone uses PSTN connectivity to allow users to make and receive calls outside of their organization. Each PSTN connectivity option connects Microsoft Teams to the PSTN using a different deployment model, allowing organizations to choose the solution that best fits their business, operational, and technical requirements.

In order to use PSTN telephony services with Teams Phone, the user account must be licensed with the Teams Phone application and also be equipped with a PSTN solution from your PSTN service provider of choice.

The PSTN service provider serves as your partner to provide Microsoft Teams users with:

- Access to the PSTN for making and receiving telephone calls. Phone numbers for users and supported calling scenarios.
- A secure PSTN integration with your Teams tenant is required before licensed Teams Phone users can make and receive telephone calls.

## What's next?

To start using Teams Phone with PSTN connectivity:

1. **Ensure you have the required Teams Phone licenses.** Before you can enable PSTN calling, verify that your users have the appropriate Teams Phone licenses. Some PSTN connectivity options also require a subscription or service agreement with Microsoft or a participating telecommunications provider.
2. **Choose a PSTN connectivity option.** Select the option that best fits your organization's business and technical requirements. For example, you can get phone numbers directly from Microsoft, continue working with an existing telecommunications provider, use existing mobile SIM numbers with Teams, or integrate Teams Phone with your existing telephony infrastructure.
3. **Configure your PSTN connectivity solution.** After selecting a PSTN connectivity option, follow the deployment guidance for your chosen solution to connect your Teams tenant to the PSTN, assign phone numbers to users, and complete any required configuration before users can make and receive external calls.