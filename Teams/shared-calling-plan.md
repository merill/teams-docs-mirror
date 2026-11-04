---
layout: Conceptual
title: Plan for Shared Calling - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/shared-calling-plan
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.reviewer: roykuntz, jastark
ms.date: 2024-09-17T00:00:00.0000000Z
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.topic: concept-article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
- Tier1
audience: Admin
ms.localizationpriority: medium
ms.custom:
- Phone System
description: In this article, you'll learn about Teams Phone Shared Calling.
locale: en-us
document_id: dae4f3dc-c617-d8b8-8a6b-bda47a6e9755
document_version_independent_id: dae4f3dc-c617-d8b8-8a6b-bda47a6e9755
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/shared-calling-plan.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: shared-calling-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/shared-calling-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3a451963-b192-ce47-f7c9-200cb606cace
---

# Plan for Shared Calling - Microsoft Teams | Microsoft Learn

This article describes what you need to know before configuring Shared Calling for Teams Phone.

If you have users who aren't heavy users of the Public Switched Telephone Network (PSTN), they might not need a dedicated assigned phone number. Instead, for these users, you should consider Shared Calling as a simpler, easier-to-implement phone solution for your organization. Shared Calling greatly simplifies phone number management for some users. Shared Calling also reduces costs for your organization because you don't need a dedicated phone number for every user. Optionally, you can also configure extension dialing support for Shared Calling users.

Note: Shared Calling is currently available in public clouds only.

Let's start with some definitions that you need to know for Shared Calling:

| Term | Definition |
| --- | --- |
| Auto attendant | Directs a caller to an appropriate person or department based on the caller's input to the provided menu options--for example, dial by name. The Auto attendant phone number used is specified by the resource account associated with the Auto attendant.For more information about using Auto attendants, see [Plan for Auto attendants](aa-cq-plan-overview) and [Set up Auto attendants](aa-cq-setup-auto-attendant). |
| Inbound calls | An incoming call that comes from a PSTN to a user in your organization. When a Shared Calling user receives an inbound PSTN call, the call connects to the Auto attendant. |
| Outbound calls | An outgoing call by a user in your organization to a PSTN. When a Shared Calling user makes an outbound call to the PSTN, the recipients see the caller ID of the Auto attendant. |

With Shared Calling, instead of assigning a phone number to every user, you use the phone number of a resource account associated with an Auto attendant for inbound and outbound PSTN calls. The Shared Calling policy configures the resource account used for outbound calls and emergency numbers that are used as emergency callback numbers.

To set up Shared Calling, you need to perform the following steps. These steps are described in detail in [Configure Shared Calling](shared-calling-setup).

1. Assign Teams Phone licenses and enable users for voice. Don't assign a phone number to any Shared Calling enabled user.
2. Assign number to resource account for inbound and outbound calling.
3. Associate resource account with Auto attendant for inbound calling.
4. Assign a location to the resource account for emergency calling.
5. Configure resource accounts with service numbers. Communication Credits might be required if your calling plan is a Microsoft Online Subscription Agreement (MOSA), or you don't want to post-pay for calls.
6. Create voice routing policy without PSTN usages.
7. Enable emergency calling for users.
8. Create your Shared Calling policy.
9. Assign the Shared Calling policy to users.
10. Configure extension dialing support for Shared Calling enabled users (optional).

Shared Calling can be configured with the Teams admin center and PowerShell. You must have Teams PowerShell Module version 5.5.0 or higher to use the new [TeamsSharedCallingRoutingPolicy](/en-us/powershell/module/teams/set-csteamssharedcallingroutingpolicy) cmdlets. You can use these cmdlets to create and manage Shared Calling policies.