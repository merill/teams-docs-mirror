---
layout: Conceptual
title: Use Conditional Access to protect Microsoft Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/granular-conditional-access-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: smahadevan
ms.date: 2026-11-25T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
audience: admin
f1.keywords:
- NOCSH
ms.custom:
- security
description: Learn how to set up and configure Granular Conditinal Access to protect Microsoft Teams meetings.
locale: en-us
document_id: 7737df91-f58b-f881-6d37-9cb18ad7d0b8
document_version_independent_id: 7737df91-f58b-f881-6d37-9cb18ad7d0b8
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/granular-conditional-access-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: granular-conditional-access-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/granular-conditional-access-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/57eae307-c3a1-4cac-b645-1a899934bac8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/ee561821-1ac7-45a8-9409-6ba5eb7a5b97
platformId: 0cdfdd10-e870-b27f-7cc0-84616150001b
---

# Use Conditional Access to protect Microsoft Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Events ![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Calls

Important

Granular Conditional Access for Teams meetings is currently in public preview. Features and steps described in this article are subject to change before general availability.

## Overview

Some meetings need stronger access controls than others. Executive reviews, incident response discussions, financial reviews, and regulated communications often call for an extra layer of verification that would be unnecessary friction for everyday meetings. Granular Conditional Access for Teams meetings lets administrators apply Microsoft Entra Conditional Access policies to specific meetings, so that participants must satisfy an additional verification requirement before they can join.

This article explains how the feature works, what you need before you start, how to configure it in the Microsoft Entra admin center and the Teams admin center, and what organizers and participants experience.

## How it works

Granular Conditional Access applies Microsoft Entra Conditional Access policies to individual meetings rather than only at Teams sign-in. Administrators decide which authentication requirements are available, meeting organizers select an approved requirement when they set up a meeting, and participants must satisfy the associated Conditional Access policy before they can join. The result is an additional verification step for the conversations that need it most, without raising the bar for every meeting in your organization.

The feature is built on Microsoft Entra authentication contexts. An authentication context is a label that a Conditional Access policy can target. When an application requests that context, Microsoft Entra evaluates the policies attached to it. Teams requests the context selected for a meeting at the moment a participant tries to join.

Setup and use involve the following three stages.

| Stage | Where it happens | Who does it | Outcome |
| --- | --- | --- | --- |
| 1. Configure authentication contexts and Conditional Access policies | Microsoft Entra admin center | Global Administrator or Conditional Access Administrator | Contexts exist and at least one policy enforces each one |
| 2. Publish selected authentication contexts to Teams | Teams admin center | Teams Administrator | The chosen contexts become available to organizers |
| 3. Apply a published requirement to a specific meeting | Teams meeting options | Meeting organizer | Participants are verified before joining that meeting |

### What happens when a participant joins

When a participant joins a protected meeting, Teams evaluates the selected authentication context and enforces the associated Conditional Access policy before the participant is allowed in. Requirements that can be enforced this way include:

- Multifactor authentication (MFA)
- Device compliance
- Trusted network locations
- Identity verification, using the Require identity verification grant control
- Other Conditional Access grant controls

### Session persistence

After a participant satisfies an authentication context, that context persists until the next token refresh, or until a new context is requested that the existing one doesn't fulfill. In practice, a participant who completes MFA for one protected meeting might not be prompted again for another meeting that uses the same context within that token lifetime. Keep this in mind when you test the feature, so that the behavior isn't mistaken for an enforcement failure.

## Prerequisites

Before you begin, make sure the following are in place:

- Microsoft Entra Conditional Access is configured in your tenant.
- You have the administrator roles listed in the next section.
- If you plan to use the Require identity verification grant control, an identity verification profile with the purpose set to Verification is configured in Microsoft Entra Verified ID.
- Teams meeting policies allow organizers to use meeting authentication requirements.
- The organizers and participants who will use the feature are identified and grouped so that policies can target them.
- Users are registered for the methods your policies require, for example MFA methods or compliant devices.

### Required administrator roles

- The Microsoft Entra steps are typically completed by a Global Administrator or Conditional Access Administrator.
- The Teams steps are completed by a Teams Administrator.

Use the least-privileged role that can complete each step.

## Plan your deployment

Start with a short list of meeting scenarios where stronger verification clearly matters. Create a matching authentication context for each scenario, and begin with a small group of organizers who hold those meetings regularly. Starting narrow makes it easier to separate configuration issues from expected behavior.

### Recommended scenarios and authentication contexts

The following table suggests descriptive context names and controls for common sensitive-meeting scenarios. Adapt the names and controls to your own policies. The goal is that an organizer can tell at a glance which requirement fits their meeting.

| Scenario | Suggested context name | Suggested Conditional Access control | Notes |
| --- | --- | --- | --- |
| Executive reviews and board preparation | Teams meeting - Require MFA | Require multifactor authentication | A good first context with the lowest friction for participants |
| Highest-sensitivity meetings that need verified identities | Require High Assurance | Require identity verification | Requires an identity verification profile in Microsoft Entra Verified ID |
| Incident response discussions | Teams meeting - Compliant device | Require device to be marked as compliant | Keeps response discussions on managed devices |
| Financial reviews, earnings, or M&A discussions | Teams meeting - Trusted locations | Block access outside named trusted locations | Confirm that remote attendees can reach a trusted network |
| Regulated communications | Teams meeting - Strong authentication | Require authentication strength, for example phishing-resistant MFA | Confirm that all expected participants have registered strong methods |

### Step 1: Create an identity verification profile (optional)

Complete this step only if you plan to use the Require identity verification grant control for Teams meetings.

1. In the Microsoft Entra admin center, go to **Verified ID** &gt; **ID Verification Profiles** &gt; **Profiles**.
2. Select **Create profile**.
3. Enter a name and a description, and set the profile purpose to **Verification**.
4. For **Profile mode**, select **Production**.
5. Select the target user group.
6. For the verification method, select **Identity verification provider** or **Tenant issued credentials**.
7. Optionally, turn on additional checks with custom extensions.
8. Save the profile.

Tip

The **Conditional Access policy** pane can prefill a policy template for the profile, which you can then complete. Alternatively, create the policy manually as described in step 3.

### Step 2: Create an authentication context in Microsoft Entra

1. In the Microsoft Entra admin center, go to **Protection** &gt; **Conditional Access** &gt; **Authentication contexts**.
2. Select **New authentication context**.
3. Enter a name and a description. Organizers see these values, so make them self-explanatory.
4. Select **Publish to apps**.
5. Save the authentication context.

Example values:

| Setting | Value |
| --- | --- |
| Name | Require High Assurance |
| Description | Users must complete Verified ID flows before joining this meeting |

Tip

Create one context for each protection level you intend to offer, rather than one context for each meeting or team. A small, well-named set is easier for organizers to choose from and easier for administrators to govern.

### Step 3: Create a Conditional Access policy that targets the context

1. In the Microsoft Entra admin center, go to **Protection** &gt; **Conditional Access**.
2. Select **New policy**.
3. Under **Users**, select the users or groups the policy applies to. When you first roll out the feature, scope the policy to a small group.
4. Under **Target resources**, select **Authentication context**, and then choose the context you created in step 2.
5. Configure **Conditions** as needed, for example locations or device platforms.
6. Under **Grant**, select the control you want to enforce, for example **Require identity verification**.
7. Enable the policy.

Example values:

| Setting | Value |
| --- | --- |
| Authentication context | Require High Assurance |
| Users | All employees |
| Grant control | Require identity verification |

Tip

Consider starting the policy in report-only mode, reviewing the sign-in logs, and then turning it on. If guest users will attend protected meetings and you expect them to be challenged, make sure they're included in the policy scope.

### Step 4: Publish authentication contexts to Teams

After authentication contexts are created in Microsoft Entra, they must be published to Teams before meeting organizers can use them.

1. In the Teams admin center, go to **Meetings** &gt; **Authentication contexts**.
2. Review the available authentication contexts.
3. Select one or more contexts.
4. Select **Publish to Teams**.
5. Save your changes.

Published contexts become available to meeting organizers. For each context, the Teams admin center displays the context name, description, identifier, and publication status. Use the identifier to match a published context to its Conditional Access policy when you troubleshoot.

### Step 5: Turn on meeting authentication requirements in meeting policies

Administrators control whether meeting organizers can use authentication requirements through Teams meeting policies.

1. In the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select a policy. When you first roll out the feature, we recommend a dedicated policy assigned to the organizers who will use it.
3. Turn on **Authentication required**.
4. Save the policy.

The policy can be applied globally or to specific users. Allow time for policy changes to take effect before you test.

## Supported lobby settings

Granular Conditional Access requires an authenticated identity to evaluate Conditional Access requirements. For this reason, authentication requirements are available only with the following lobby settings. If an unsupported lobby option is selected, the authentication requirement option isn't available in meeting options.

| Who can bypass the lobby | Supported |
| --- | --- |
| People in my organization | Yes |
| People in my organization and guests | Yes |
| Everyone | No |
| People who were invited | No |
| Only organizers and co-organizers | No |

If you use meeting templates or set default lobby settings in meeting policies, check that the defaults for your organizers are one of the two supported values. Otherwise, organizers need to change the lobby setting before the verification option appears.

## Protect a meeting (organizers)

When authentication requirements are turned on for an organizer, they can protect individual meetings from meeting options.

1. Create a Teams meeting.
2. Open **Meeting options**.
3. Confirm that **Who can bypass the lobby** is set to a supported value.
4. Locate **Additional verification required**.
5. Select a published authentication requirement.
6. Save the meeting options.

Organizers choose from the requirements their administrator published. For example:

| Authentication requirement | When an organizer might choose it |
| --- | --- |
| None | Standard meetings that need no additional verification |
| Require High Assurance | Sensitive internal discussions such as executive reviews |
| Trusted locations | Discussions that should only be joined from corporate networks |
| Strong authentication | Regulated communications that require phishing-resistant methods |

Note

Meeting invitations don't currently display authentication requirements. We recommend that organizers add a short note to the invitation telling attendees that additional verification is required to join.

## Participant experience

When participants join a protected meeting, Teams displays a message indicating that additional verification is required. Participants can complete the required authentication or wait in the lobby if the meeting configuration permits it.

If the participant satisfies the Conditional Access requirements (for example, completing MFA, passing a device compliance check, or connecting from a trusted location), they join the meeting normally.

If the participant doesn't meet the Conditional Access requirements:

- Microsoft Entra denies access.
- The participant sees the standard Conditional Access error experience.
- The participant can return and try again to satisfy the requirements.
- If the meeting configuration permits lobby access, the participant can wait in the lobby for the organizer to admit them.

### Supported participant types

| Participant type | Supported |
| --- | --- |
| Internal users | Yes |
| B2B guest users | Yes |
| Microsoft Entra authenticated users | Yes |

## Best practices

- Use descriptive authentication context names so that organizers understand exactly what each option requires.
- Publish only the contexts intended for meeting protection, not every context in your tenant.
- Test policies with a small group of users before broad deployment.
- Keep a simple register that maps each published context to its Conditional Access policy, owner, and intended scenario.