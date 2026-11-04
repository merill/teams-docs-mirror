---
layout: Conceptual
title: Plan for Operator Connect - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/operator-connect-plan
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to plan your Operator Connect deployment for Microsoft Teams Phone, including prerequisites, onboarding guidance, and planning considerations.
author: rosaswaby
ms.author: rosaswaby
manager: obaidshah
ms.topic: how-to
ms.service: msteams
ms.date: 2026-08-24T00:00:00.0000000Z
locale: en-us
document_id: 30fbee95-7a4d-7e50-efb2-52726553229c
document_version_independent_id: 60136744-9919-50a1-c371-d3e467700922
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/operator-connect-plan.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: operator-connect-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/operator-connect-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
platformId: bace35e2-7e30-daa1-38b3-c6f534e1574f
---

# Plan for Operator Connect - Microsoft Teams | Microsoft Learn

Operator Connect enables organizations to connect Microsoft Teams Phone to the Public Switched Telephone Network (PSTN) through a Microsoft-certified operator. It provides a simplified deployment experience by allowing operators to manage the PSTN infrastructure while administrators configure and manage users directly from the Teams admin center.

If you're evaluating Teams Phone connectivity options, Operator Connect is a good choice when you want a managed PSTN solution without deploying and maintaining your own Session Border Controllers (SBCs), or when you want to continue working with an existing operator that offers Operator Connect for Teams Phone.

To find participating operators and review their available services and regions, see the [Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/).

## Onboarding

If you're deploying Operator Connect for the first time, follow these recommended planning steps to prepare your environment and ensure a smooth deployment.

### Step 1: Verify prerequisites

Before you begin, make sure that:

- Users have the required Microsoft Teams Phone licenses.
- Users are configured in Teams Only mode.
- You have the appropriate administrator permissions to manage Teams Phone.
- A Microsoft-certified Operator Connect provider is available in the countries or regions where you'll deploy the service.

### Step 2: Choose a certified operator

Review the list of Microsoft-certified operators and select the provider that best meets your organization's business, geographic, and telephony requirements.

When evaluating providers, consider factors such as:

- Country and regional availability
- Phone number availability and porting support
- Calling plans and service offerings
- Existing business relationships

### Step 3: Plan your phone numbers

Determine how users will receive phone numbers. Depending on your deployment, you can:

- Purchase new phone numbers from your operator.
- Port existing phone numbers.
- Migrate users from another Teams Phone PSTN connectivity option, if applicable.

Planning your numbering strategy ahead of time can help simplify deployment and reduce disruption for users.

### Step 4: Configure Operator Connect

Once planning is complete, enable your selected operator in the Teams admin center, assign phone numbers to users, and complete your Teams Phone deployment.

For deployment instructions, see [Configure Operator Connect](operator-connect-configure).

## Benefits

Operator Connect provides a simplified approach to connecting Microsoft Teams Phone to the Public Switched Telephone Network (PSTN). Compared to traditional telephony deployments, Operator Connect reduces deployment complexity while allowing organizations to continue working with their preferred telecommunications provider.

Key benefits include:

- Simplified deployment and management through the Teams admin center.
- Microsoft-certified operators that meet Microsoft's technical and operational requirements.
- Operator-managed PSTN infrastructure, reducing administrative overhead.
- Support for acquiring new phone numbers and porting existing numbers.
- Integrated management experience for Teams Phone administrators.

Note

Operator Connect is one of several PSTN connectivity options available for Microsoft Teams Phone. For guidance on selecting the appropriate option for your organization, see [Plan your Teams voice solution](cloud-voice-landing-page).

## Requirements

Before deploying Operator Connect, verify that:

- Your organization has the required Microsoft Teams Phone licenses.
- Teams is configured appropriately for voice services.
- Your selected Operator Connect provider supports the countries or regions where your users require PSTN connectivity.
- Your network and firewall configuration meets Microsoft Teams networking requirements.

Tip

Verifying licensing, regional availability, and operator support before deployment can help avoid delays during implementation.

## Quick links

Use the following resources to help plan, deploy, and manage Operator Connect.

| Resource | Description |
| --- | --- |
| [Plan your Teams voice solution](cloud-voice-landing-page) | Compare Microsoft Teams PSTN connectivity options and determine which solution best fits your organization. |
| [Configure Operator Connect](operator-connect-configure) | Configure Operator Connect in the Teams admin center. |
| [Operator Connect directory](https://microsoftpartners.microsoft.com/abs/Operator-Directory/) | Browse participating Operator Connect providers and review service availability by country or region. |
| [Manage phone numbers for Teams](manage-phone-numbers-landing-page) | Assign, manage, and port Teams Phone numbers. |
| [Microsoft Teams Phone licensing](teams-phone-licensing) | Review Teams Phone licensing requirements. |
| [Teams admin center](https://admin.teams.microsoft.com) | Manage Teams Phone users, policies, and voice settings. |

## Support boundaries

Operator Connect is a shared responsibility between Microsoft and the participating operator.

Microsoft is responsible for:

- Microsoft Teams services.
- Teams Phone administration.
- Teams admin center functionality.
- Integration between Microsoft Teams and Operator Connect.

Your Operator Connect provider is responsible for:

- PSTN connectivity.
- Telephone number provisioning and porting.
- Calling services.
- PSTN-related support and troubleshooting.

For operator-specific support, contact your Operator Connect provider directly.