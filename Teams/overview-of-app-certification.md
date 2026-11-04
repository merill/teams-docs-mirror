---
layout: Conceptual
title: Know about high quality Microsoft certified Teams apps - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/overview-of-app-certification
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn about the Microsoft 365 app compliance program for security, compliance, and privacy of third-party apps.
ms.topic: concept-article
author: vikasalmal0201
ms.author: vikasalmal
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 2025-10-07T00:00:00.0000000Z
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: 5e2745e9-5876-8469-7152-6d63a14f42e0
document_version_independent_id: 5e2745e9-5876-8469-7152-6d63a14f42e0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/overview-of-app-certification.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: overview-of-app-certification
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/overview-of-app-certification.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 17dd7cf7-8cdd-9e1f-048b-148dbe9625de
---

# Know about high quality Microsoft certified Teams apps - Microsoft Teams | Microsoft Learn

Microsoft 365 app compliance program checks and audits an app against controls that are derived from leading industry-standard frameworks. The program demonstrates that strong security and compliance practices are in place to protect customer data. The program has the following phases:

- Publisher verification
- Publisher attestation
- Microsoft 365 certification

To help you evaluate app trustworthiness more efficiently, the Teams admin center will soon surface security and compliance data, when available, for apps beyond Microsoft 365 certified or publisher-attested ones. Data from Microsoft Defender for Cloud Apps (MDA) supports quicker assessments against organizational trust requirements. For more information, see [MDA documentation](/en-us/defender-cloud-apps/).

Important

This is associated with Microsoft 365 Roadmap IDs [503100](https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=&amp;searchterms=503100), [503102](https://www.microsoft.com/en-in/microsoft-365/roadmap?filters=&amp;searchterms=503102), and [502842](https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=&amp;searchterms=50284202).

## Publisher verification

Before an app developer can submit their app to Microsoft, the developer is required to undergo a verification. A developer verifies their identity using their Microsoft Partner Network (MPN) account and associates this MPN account with their app registration. Publisher verification helps admins and users understand the authenticity of application developers. Publisher verification provides the following benefits:

- Increased transparency and risk reduction for customers: This capability helps customers understand which apps being used in their organizations are published by developers they trust.
- Improved branding: A `verified` badge appears on the Microsoft Entra consent prompt, Enterprise Apps page, and other user interfaces used by users and admins.
- Smoother enterprise adoption: Admins can configure user consent policies, with publisher verification status as a primary policy criteria.

## Publisher attestation

Publisher attestation is the next tier in the app compliance program. Publisher attested apps provide confidence to admins about security and compliance measures of an app. It also helps reduce the time to review this information for an app. The attestation reflects an app's security, data handling, and compliance practices against more than 80 risk factors identified by [MDA](/en-us/defender-cloud-apps/). Publisher attestation process can start before Publisher verification is complete.

App developers are asked to complete a self-assessment that includes questions frequently asked by customers and IT admins to evaluate the security and compliance of an app. Microsoft then publishes this information for easier and more timely evaluation. To know more, see [attestation guide](/en-us/microsoft-365-app-certification/docs/userguide).

Admins can quickly check for Published attested apps in three different ways.

- When gathering more information about an app, see the details of a specific app at its link at [Microsoft Teams apps security and compliance](/en-us/microsoft-365-app-certification/teams/teams-apps). Alternately, select the `Publisher attestation` link in [Teams admin center](https://admin.teams.microsoft.com/).

    ![In Teams admin center, select the Publisher attestation link to view details of the attestation of an app.](media/attested-app-tac3.png)
- In Teams admin center, when checking the details of an app from the **[Manage App](https://admin.teams.microsoft.com/policies/manage-apps)** page, see the publisher attested icon on the banner in the app's detail page.

    ![In Teams admin center, Publisher attested icon is displayed on all attested apps.](media/attested-app-tac1.png)
- In Teams admin center, before you [grant consent to app permissions](manage-consent-app-permissions), a blue checkmark in front of the app name indicates it's a publisher attested app. All Microsoft 365 apps also go through publisher attestation, so a blue checkmark displays for Microsoft 365 apps as well.

    ![In Teams admin center, on the dialog to grant permissions, the blue checkmark indicates publisher attested app.](media/attested-app-tac2.png)

    The attestation details page for an attested or certified app lists the following details.

    ![Detailed information provided for attested apps.](media/attested-app-doc-details.png)

## Microsoft 365 certification

App certification is achieved through:

- Approval of a comprehensive assessment centering on an app's security and compliance frameworks, processes, and procedures.
- A qualified analyst's review.

We check the app against a series of security controls derived from leading industry-standard frameworks. Developers demonstrate following strong security and compliance practices to protect customer data when their app is used in an organization. More information about how admins and users benefit from the certification is available at [overview of Microsoft 365 app compliance program](/en-us/microsoft-365-app-certification/overview).

Administrators can find Microsoft 365 certified apps and information about such apps in the following ways:

- When evaluating an app, you can access app's security and compliance information and in some cases detailed evidences for this information. Developers provide answers to a questionnaire as part of their [Teams app's security and compliance information](/en-us/microsoft-365-app-certification/teams/teams-apps) for Publisher Attestation and for Microsoft 365 certification.

    ![View the Microsoft 365 certification information in the detailed help article about security and compliance of an app](media/attested-app-doc-details.png)

    Developers of some Microsoft 365 certified apps and Copilot agents can choose to provide detailed evidences to help your organization quickly assess their app. Developers submit the comprehensive details as part of the audits done during certification. If developers agree to share the detailed evidences, then you can download these app trust evidences from the app details page in the Teams admin center. The download option is available only in commercial tenants.

    [![Screenshot showing the option to download detailed evidence provided by developers of certified apps.](media/m365-cert-download-evidence.png)](media/m365-cert-download-evidence.png#lightbox)
- When checking an application in [Teams admin center](https://admin.teams.microsoft.com/policies/manage-apps), sort the list of apps using the Certification column. To access the app-specific page, see the shield icon and optionally, select the link:

    [![View Microsoft 365 certification status of an app in the Teams admin center.](media/m365cert-apps-list1.png)](media/m365cert-apps-list2.png#lightbox)
- When viewing the details of an app, see the Microsoft 365 certified icon in the app banner.

    ![View Microsoft 365 certification information in the app banner when managing a specific app in Teams admin center](media/m365cert-app-details-banner.png)
- In Teams admin center, before you [grant consent to app permissions](manage-consent-app-permissions), a blue checkmark in front of the app name indicates it's a publisher attested app. All Microsoft 365 apps also go through publisher attestation, so a blue checkmark displays for Microsoft 365 apps as well.

    ![In Teams admin center, on the dialog to grant permissions, admins can check the blue checkmark to be assured that the app is Microsoft 365 certified](media/attested-app-tac2.png)

## View security, compliance, and privacy information

You can find information about security, privacy, compliance, and behaviors for an attested or certified app in [Microsoft documentation](/en-us/microsoft-365-app-certification/teams/teams-apps) and [Teams admin center](https://admin.teams.microsoft.com/policies/manage-apps).

### Microsoft documentation

You can find the details about security, privacy, compliance, and more for each app listed it the app-specific help articles linked from [Microsoft Teams apps security and compliance](/en-us/microsoft-365-app-certification/teams/teams-apps).

![Detailed information that is provided for apps that undergo Microsoft compliance program.](media/attested-app-doc-details.png)

### Teams admin center

Teams admin center provides enhanced tools and expanded security and compliance insights to streamline app and agent evaluations. You can view security and compliance data, when available, for apps beyond Microsoft 365 certified or publisher-attested ones, powered by MDA. Trust-based filters help narrow choices by industry-standard attributes such as SOC 2, ISO 27001, HIPAA, and GDPR, enabling faster, more informed approval decisions.

Important

For timelines, see [503100](https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=&amp;searchterms=503100), [503102](https://www.microsoft.com/en-in/microsoft-365/roadmap?filters=&amp;searchterms=503102), and [502842](https://www.microsoft.com/en-us/microsoft-365/roadmap?filters=&amp;searchterms=50284202).

### Security and compliance information on Teams admin center

Teams admin center helps you quickly assess security and compliance-related information for agents and apps. This information includes industry-standard data such as SOC 2, HIPAA, ISO 27001, GDPR, CCPA, and FedRAMP, plus Microsoft Entra ID integration for Single Sign-On, Penetration Testing, and CSA STAR compliance. You'll also see privilege-level insights and permission risk ratings powered by MDA.

Here's how you can view the security and compliance information:

1. Sign in to [Microsoft Teams admin center](https://admin.teams.microsoft.com/).
2. Go to [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps) to view and govern apps that are available in your organization's app catalog.
3. Use the **Security and compliance info** column to see industry standard attributes and sort apps by the desired attributes.

    [![Screenshot showing the newly added column displaying trust-based attributes.](media/security-compliance-info-manage-apps.png)](media/security-compliance-info-manage-apps.png#lightbox)
4. Select the **Filter** icon located between the Excel and Settings icons in the top-right corner to filter apps by compliance attributes.

    [![Screenshot showing the filter option for the security compliance info column, displaying compliance attributes.](media/security-and-compliance-info-filter.png)](media/security-and-compliance-info-filter.png#lightbox)
5. Select **Apply** to see all the filtered compliance attributes.

    [![Screenshot showing the detailed filters, displaying apply button.](media/filtered-security-and-compliance-info-detailed.png)](media/filtered-security-and-compliance-info-detailed.png#lightbox)

    Alternatively, you can select any particular agent or app under the **All apps** section and go to the **Security and compliance** tab to view information about the particular agent or app.

    [![Screenshot showing an individual app and the security and compliance tab.](media/individual-app-security-and-compliance-revised.png)](media/individual-app-security-and-compliance-revised.png#lightbox)

#### View Microsoft 365 certified apps and download evidence

The **Manage apps** page shows an enhanced tile for apps that are Microsoft 365 certified, Certified with evidence, and Publisher attested, that you might allow in your organization.

[![Screenshot showing the tile with three trust-based attributes.](media/tile-manage-apps-evidence-docs.png)](media/tile-manage-apps-evidence-docs.png#lightbox)

## View privacy policy and terms of use of an app

In Teams admin center, each app page links to the privacy statement and terms of use of the app.

[![From Teams admin center, admins can access the link to the privacy policy and terms of use for every app.](media/tac-app-tou-privacy-info1.png)](media/tac-app-tou-privacy-info2.png#lightbox)