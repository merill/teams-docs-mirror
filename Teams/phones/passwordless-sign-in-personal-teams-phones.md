---
layout: Conceptual
title: Passwordless sign-in for personal Teams phones without DCF - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/passwordless-sign-in-personal-teams-phones
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MattSlomka
ms.author: mattslomka
manager: kimmatlock
ms.reviewer: srpall
ms.date: 2026-11-11T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: Medium
description: Learn how to set up Microsoft Authenticator passwordless phone sign-in for personally assigned Teams phones so users don't need device code flow.
locale: en-us
document_id: f3a72c41-7963-339c-6008-60f1bf870a46
document_version_independent_id: f3a72c41-7963-339c-6008-60f1bf870a46
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/passwordless-sign-in-personal-teams-phones.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/passwordless-sign-in-personal-teams-phones
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/passwordless-sign-in-personal-teams-phones.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/b5267373-9b61-4d5a-a4ac-5d03f8f8800f
- https://authoring-docs-microsoft.poolparty.biz/devrel/5686b492-7c45-4088-8291-ecc0458747d3
- https://authoring-docs-microsoft.poolparty.biz/devrel/fcc3cd4a-59ea-47a2-9cc1-784142a5a25d
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/bcd4f3ef-c612-47a8-aa4a-7f9bedc3a98c
- https://authoring-docs-microsoft.poolparty.biz/devrel/838f4f15-80c1-4d49-b873-501fe4ed2d28
- https://authoring-docs-microsoft.poolparty.biz/devrel/d7a55faf-a992-4e27-aa3a-eadc9830e778
platformId: d48cf2db-e1ab-c7de-e864-aeaf53db4a06
---

# Passwordless sign-in for personal Teams phones without DCF - Microsoft Teams | Microsoft Learn

If your organization uses personally assigned Microsoft Teams phones and wants to reduce or remove its dependency on device code flow (DCF) for security reasons, this article describes an alternative.

Native passkey support for Teams phones is in development. Until it's available, you can use Microsoft Authenticator passwordless phone sign-in as an interim option. With this method, users don't type their password on the phone screen.

This approach uses Microsoft Entra ID authentication and requires authentication method registration and Conditional Access configuration.

## Prerequisites

Before you begin, make sure that:

- The user has a Microsoft Entra ID account.
- Microsoft Authenticator is installed on the user's iOS or Android mobile device.
- Your organization's security policies allow Microsoft Authenticator passwordless phone sign-in.

Important

Microsoft Authenticator passwordless phone sign-in doesn't meet the phishing-resistant authentication strength requirement. If your organization enforces phishing-resistant authentication, evaluate whether this interim approach meets your security policies.

## Configure passwordless sign-in

### Step 1: Enable passwordless authentication

In the [Microsoft Entra admin center](https://entra.microsoft.com/):

1. Go to **Authentication methods** &gt; **Policies**.
2. Select **Microsoft Authenticator**.
3. For all users or the Microsoft Entra ID group you want, set the authentication mode to **Any** or **Passwordless**.
4. Select **Save**.

### Step 2: Have the user register for passwordless sign-in

The user completes these steps on their mobile device:

1. In **Microsoft Authenticator**, select the registered account.
2. Select **Set up Passwordless sign-in requests**.
3. Follow the instructions in the app to finish registering the account for passwordless phone sign-in.

### Step 3: Check Conditional Access policies

Microsoft recommends creating separate Conditional Access policies for Teams phone sign-in. Use device filters so the policies apply only to Teams phones. To learn more about device filters, see [Authentication best practices for Teams phones](authentication-best-practices-phones).

Review the Conditional Access policies that apply to the user and to Teams phone sign-in. Make sure the authentication strength allows Microsoft Authenticator passwordless phone sign-in by not requiring phishing-resistant authentication.

### Step 4: Sign in to the Teams phone

1. On the Teams phone, select **Sign in on this device**.
2. Enter the user's email address.
3. If Microsoft Authenticator passwordless sign-in is offered, select it.
4. Approve the sign-in request in Microsoft Authenticator on the user's mobile device.
5. Confirm that the Teams phone signs in without using DCF.

## Troubleshooting

### Microsoft Authenticator isn't offered as a sign-in option

- Make sure the user registered for passwordless phone sign-in, not only Authenticator push notifications for multifactor authentication (MFA).
- Check whether Conditional Access authentication strength requirements exclude this method.
- Review the Microsoft Entra sign-in logs for authentication failures or policy restrictions.
- Confirm that the Teams phone model, software version, and sign-in flow support this method.

### The user is still prompted for a password

- Check the user's passwordless registration and the authentication methods available to them.
- Check whether the sign-in flow supports Microsoft Authenticator passwordless authentication.
- Review the Conditional Access policies that apply and the Microsoft Entra sign-in logs.

## Security considerations

Microsoft Authenticator passwordless phone sign-in removes the need to enter a password, but it isn't classified as phishing-resistant authentication. Don't treat it as equivalent to passkeys or FIDO2 authentication.

Before you deploy broadly, test these scenarios: first sign-in, later sign-ins, sign-out, device restart, and device reset.