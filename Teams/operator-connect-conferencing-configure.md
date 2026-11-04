---
layout: Conceptual
title: Configure Operator Connect Conferencing - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/operator-connect-conferencing-configure
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.date: 2025-02-18T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-audio-conferencing
ms.reviewer: oscarr
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- m365initiative-meetings
- highpri
- Tier1
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Learn more about how to configure Operator Connect Conferencing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
locale: en-us
document_id: 995d82c4-dbee-bcc3-8f21-d2decf42ba37
document_version_independent_id: 995d82c4-dbee-bcc3-8f21-d2decf42ba37
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/operator-connect-conferencing-configure.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: operator-connect-conferencing-configure
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/operator-connect-conferencing-configure.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 8d28ea05-8c01-066a-8c5b-c346309c9983
---

# Configure Operator Connect Conferencing - Microsoft Teams | Microsoft Learn

This article details how to configure Operator Connect Conferencing for your organization and users.

Before configuring Operator Connect Conferencing, read [Plan for Operator Connect Conferencing](operator-connect-conferencing-plan) for information about benefits and licensing requirements.

## Set up an operator

You can set up, edit, and remove operators in the Teams admin center. In the left navigation pane, go to **Voice &gt; Operator Connect**.

To set up an operator:

1. **Choose an operator**: In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs. Then, select the operator you want to use. For Operator Connect Conferencing, verify that your operator has **Conferencing** listed as an available product.
2. Under **Operator settings**, select the countries/regions you want to enable with your selected operator.
3. **Operator can contact me using this information**: Enter your contact information, including your full name and email address, to share with your operator. You can change this information later. You need to provide company size, with the option to provide your phone number. Operators use this information to contact you with more details about Operator Connect Conferencing.
4. Accept the data transfer notice.
5. Select **Add as my operator** to save.

## Acquire numbers for your Audio Conferencing bridge

Your organization's Audio Conferencing bridge includes phone numbers available to all users in your organization to join Microsoft Teams meetings with Public Switched Telephone Network (PSTN) phone numbers. You can see the phone numbers associated with your organization's Audio Conferencing bridge in the Teams Admin Center under **Meetings &gt; Conference Bridges**.

To acquire phone numbers for your Audio Conferencing bridge, follow these steps:

1. **Audio Conferencing Standard subscription or Operator Connect Conferencing license.** Users that need Operator Connect Conferencing numbers to join the meetings that they organize need to have an Audio Conferencing Standard subscription license or an Operator Connect Conferencing license assigned to them. For more information, see [Plan for Operator Connect Conferencing](operator-connect-conferencing-plan).
2. **Acquire numbers.** Go to your operator's website to order and acquire phone numbers. For a list of operator websites, go to the [Microsoft 365 Operator Connect directory](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). You need to provide your tenant ID. If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/en-us/onedrive/find-your-office-365-tenant-id). Once your operator completes the order, they upload numbers to your tenant. You can view the numbers and the provider in the Teams admin center by going to **Voice &gt; Phone numbers**.
3. **Assign numbers to your Audio Conferencing bridge.** You can assign numbers to your Audio Conferencing bridge from the Teams admin center under **Meetings &gt; Conference Bridges &gt; Add**. For more information, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge).

Note

You can't assign Operator Connect Conferencing numbers as default numbers of a bridge. Once a phone number is assigned to your Audio Conferencing bridge, the number will be listed in the **Find a local number page** included in meeting invites of users in your organization with an Audio Conferencing license or an Operator Connect Conferencing license.

To route outbound calls through an operator, see the **Sending outbound calls from Teams meetings through an operator** section further down in this article.

## Change the default phone numbers that are included in the meeting invites of users

This step is optional.

A user's default phone numbers are the ones included in their meeting invites when they schedule a meeting. You can update the phone numbers included in the meeting invites of users in the Teams Admin Center under **Users &gt; Manage users**. To update the phone numbers included in the meeting invites of users, select the user, and select **Edit** in the **Audio Conferencing** section.

Once the changes are applied, organizers' new meeting invites include the new default phone numbers. However, existing meeting invites that were scheduled before the change keep the original default numbers.

## Sending outbound calls from Microsoft Teams meetings through an operator

With a Microsoft Audio Conferencing Standard subscription or an Operator Connect Conferencing license, you can configure outbound calls from Teams meetings to route through your operator by setting up an Audio Conferencing Routing policy.

Note

With an Operator Connect Conferencing license, outbound calls can only go through your operator. If you have Operator Connect Conferencing licenses, you need to configure the service as described to enable outbound calls from Teams meetings to telephone numbers.

You can apply Audio Conferencing Routing policies at the user level, meaning that your operator routes only the outbound calls from Teams meetings organized by users with the associated policy. You can also apply these policies at the global level, meaning that your operator routes outbound calls from Teams meetings organized by all users in your organization.

Using PowerShell, create your organization's new Audio Conferencing Routing policy. To specify an operator as the primary route for outbound calls from Teams meetings, follow these steps using the PowerShell commands indicated:

1. Step 1: Add a new string to the Online PSTN Usage policy
2. Step 2: Create a new Online Voice Route policy
3. Step 3: Create a new Online Audio Conferencing Routing policy
4. Step 4: Assign the new policy to users

### Step 1: Add a new string to the Online PSTN Usage policy

Read [Set-CsOnlinePstnUsage](/en-us/powershell/module/teams/set-csonlinepstnusage) for more information on using this cmdlet.

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### Step 2: Create a new Online Voice Route policy

Read [Set-CsOnlineVoiceRoute](/en-us/powershell/module/teams/set-csonlinevoiceroute) for more information on using this cmdlet.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### Step 3: Create a new Online Audio Conferencing Routing policy

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### Step 4: Assign the new policy to users

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

Note

To set an Audio Conferencing Routing policy as global and apply it to all users in your organization, you can use the `-Global` parameter instead of the `-Identity` parameter. For example, `Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"`.

When you create an Audio Conferencing Routing policy and apply it to a user, the operator that provides the phone number specified in the `BridgeSourcePhoneNumber` parameter routes Teams outbound calls to PSTN phone numbers. Additionally, the `BridgeSourcePhoneNumber` parameter specifies the phone number to use as the calling line identification phone number of outbound calls to PSTN phone numbers.

The pattern specified in the `NumberPattern` is of regex form, and it specifies which calls to route through your operator. The `"\d+"` pattern in the example matches all outbound calls from Teams meetings. You can also set the NumberPattern parameter as `"^\+1(425|206)(\d{7})$"`, which matches dialed numbers with the following formats: +1 425 XXX XX XX or +1 206 XXX XX XX, or `"^\+1(\d{10})$"`, which matches dialed numbers with the following format: +1 XXX XXX XX XX.

Once you assign an Audio Conferencing Routing policy to a user, all calls from their meetings to a phone number that matches the regex specified in their Audio Conferencing Routing policy routes through your operator, including **Call me at** calls and calls initiated through the **Invite someone or dial a number** meeting option.

## Manage your operators

From the **My operators** tab, you can view your operators, their status, and make the following changes to your selections:

- Manage operator services by country/region
- Suspend an operator
- Remove an operator

Note

Before removing an operator from your organization or from a country/region, you must remove all phone numbers assigned to the users and your Audio Conferencing bridge, then contact the operator to release the numbers.

## Release numbers from your Audio Conferencing bridge

To release phone numbers from your Audio Conferencing bridge from the Teams admin center, see **Steps when you are unassigning a service phone number for a conferencing bridge** in [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge#steps-when-you-unassign-a-service-phone-number-for-a-conferencing-bridge).