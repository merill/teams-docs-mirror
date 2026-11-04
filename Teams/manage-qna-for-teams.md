---
layout: Conceptual
title: Manage Q&A in Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-qna-for-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: v-rgrace
ms.author: wlibebe
ms.reviewer: sameer.sitaram, pallaviverma, jserna
ms.date: 2026-04-30T00:00:00.0000000Z
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- Tier2
- m365initiative-meetings
audience: Admin
description: Learn about how IT Admins can set up, use, and manage Q&A in Q&A for Teams meetings and events. Learn about Q&A, a structured approach to gathering questions and organizing discussions. Learn how to delete individual Q&A messages. Learn about using available languages for Q&A. Understand the data lifecycle and data retention and deletion policies for Q&A.
locale: en-us
document_id: e3b814e8-f9e4-7396-b016-62b8bd385585
document_version_independent_id: e3b814e8-f9e4-7396-b016-62b8bd385585
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-qna-for-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-qna-for-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-qna-for-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/e4f48d48-dfb7-4973-a019-e504674667cb
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/c6f99e62-1cf6-4b71-af9b-649b05f80cce
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/495840e0-c52f-49d2-a584-185aefeb98c7
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3f56b378-07a9-4fa1-afe8-9889fdc77628
platformId: aa84cb7a-674d-8620-0251-28f09f693d62
---

# Manage Q&A in Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

Q&A allows presenters, organizers, and co-organizers to take questions from attendees and answer them in real time. This feature is best suited for large, structured meetings and events–like all hands, and trainings.

In Teams events, organizers and co-organizers can allow presenters to manage the Q&A sessions. They can also turn on moderation to review and approve questions before they appear in the Q&A feed. Moderators can respond or post either as themselves or as **Organizer**, ensuring a unified voice across all moderators. Additionally, organizers and co-organizers can export the event's questions and answers to a CSV file.

As an admin, you can control whether an organizer can use Q&A in their meetings and events.

To learn more about Q&A for your users, see [Q&A in Microsoft Teams meetings](https://support.microsoft.com/office/q-a-in-microsoft-teams-meetings-f3c84c72-57c3-4b6d-aea5-67b11face787).

Note

Q&A is available in GCC and GCC-High.

## Prerequisites

- Verify that access to [Viva Engage’s IPs and URLs](/en-us/microsoft-365/enterprise/urls-and-ip-address-ranges)isn't blocked.
    - If you have a GCC environment, verify that your firewall isn't blocking access to GCC services hosted from `https://web.gov.yammer.com` and `https://*.rt.gov.yammer.com`.
- To allow users in your organization to add Q&A to Teams meetings and events, you must confirm that sign-ins for the Office 365 Viva Engage service are enabled in Microsoft Entra ID. Follow these steps to confirm that sign-ins are enabled:
    - Go to the **Microsoft Entra admin center** &gt; **Identity** &gt; **Applications** &gt; **Enterprise Applications** &gt; **Viva Engage** &gt; **Properties**.
    - For the **Enabled for users to sign-in?** option, select **Yes** if necessary.

When you enable Q&A, organizers can turn on Q&A in their Meeting options when creating or updating meetings and events. Through Teams and Outlook meeting options, organizers can also remove Q&A from meetings where it was previously added to prevent attendees from using the feature.

## Manage Q&A

### Teams admin center

Follow these steps to control which organizers can use Q&A in their meetings and events:

1. Open the Teams admin center.
2. Expand **Meetings** from the navigation pane.
3. Under **Meetings**, select **Meeting policies**.
4. Either select an existing policy or create a new one.
5. Navigate to the **Meeting Engagement** section and toggle the **Q&A** setting **On** or **Off**.
6. Select **Save**.
7. Assign the policy to specific groups, users, or subscriptions that you want to allow or prevent from setting up Q&A.

### PowerShell

To manage whether organizers can use Q&A in their meetings and events, use the **`-QnAEngagementMode`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet.

To allow organizers with this policy to use Q&A in meetings and events they create, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

To prevent organizers with this policy from using Q&A in meetings and events they create, use the following script:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Disabled
```

## Available languages for Viva Engage vs Teams

Q&A defaults to the user’s language for Teams. When there’s a difference in the languages available for Teams versus Viva Engage, the following language defaults occur:

- **Nearest Primary Language**- Viva Engage defaults to the nearest primary language, if available. For example, Viva Engage doesn’t have a French Canadian (fr-CA) version, so it displays content in French (fr-FR) instead.
- **Unsupported Language**- If Viva engage doesn't support the language at all, Viva Engage defaults to US English (en-US).

## eDiscovery

eDiscovery for Q&A works the same as eDiscovery for any other Viva Engage content.

- If you use Q&A in your organization's Teams application, this content is available in eDiscovery regardless of the configuration of your Viva Engage network.
- When you perform eDiscovery, you can determine whether messages were generated in Viva Engage or through Q&A in Teams. In the File Metadata section, you can find that information in the Item Class field.
- If your organization uses the Q&A, powered by Viva Engage, the content Q&A generates is considered Viva Engage content and is discoverable. For more information about eDiscovery in Microsoft 365 apps, see [eDiscovery solutions in Microsoft 365.](/en-us/microsoft-365/compliance/ediscovery)
- If the meeting organizer enables anonymous posting, the questions attendees post are ingested into the organizer’s mailbox for eDiscovery.
- When external participants from a different organization (users from an external organization using external access), or guests join a Teams meeting hosted in your organization, any questions they post into Q&A are ingested within your organization.

## Data Storage

Q&A messages created as part of the meeting are stored as Viva Engage messages. These messages are stored in Viva Engage and ingested for eDiscovery. Files are always stored in SharePoint, which handles all the data rest policies and locations.

The following guidance explains how messaging data is stored:

- Q&A content is searchable via eDiscovery at the user level.
- Teams Q&A data for GCC and GCC-H customers is stored in Microsoft's GCC and GCC-H data centers.
- If your Viva Engage network location and your Teams and Microsoft 365 Tenant location is in North America, your Teams Q&A message data is stored North America by default. If your Teams and Microsoft 365 Tenant is located in the EU, your Teams Q&A message data is stored in the EU by default regardless of your Engage network location.
- For customers without an existing Viva Engage network, the Q&A Viva Engage network is created in the United States or EU region to match the customer's base Teams and Microsoft 365 tenant.
- **Regional data storage**: Teams Q&A stores message data only in the core Microsoft 365 regions listed in the [Microsoft Product Terms](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all). (See Teams Terms of Service). These regions are: Australia, Brazil, Canada, the European Union, France, Germany, India, Japan, Norway, Qatar, South Africa, South Korea, Sweden, Switzerland, the United Kingdom, the United Arab Emirates, and the United States. Refer to the Microsoft Product Terms for the authoritative list. If your Teams tenant was moved to one of these core regions as part of a GoLocal migration, then your Teams Q&A message content is stored in the same region as your Teams tenant.
- **Note that** Teams Q&A isn't currently included in the ADR SKU and doesn't support any additional regions for Teams beyond those called out in the [Microsoft Product Terms](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all).
- Similar to OneNote tabs, removing the Q&A from a meeting doesn't delete the meeting data. Removing Q&A from the meeting only removes access to the data from the meeting. If your users add the Q&A tab back, they can see the meeting conversations again.

For details on the Advanced Data Residency (ADR) add-on license, see [Advanced Data Residency in Microsoft 365](/en-us/microsoft-365/enterprise/advanced-data-residency).

## Data subject requests and Q&A

When you complete a data subject request through the Microsoft 365 Admin Center, it automatically removes users’ contact information from all their content in the Q&A.

For more information on data subject requests, see [Azure Data Subject Requests for the GDPR and CCPA](/en-us/compliance/regulatory/gdpr-dsr-Azure).

For more information about GDPR, see the [GDPR section of the Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview) and the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

## Data lifecycle for Q&A in Teams

The lifecycle of data generated by Q&A in Teams depends on your Viva Engage Data Retention settings in the Microsoft Purview portal. If you hard delete all users in the meeting who receive a copy of the Q&A messages in their substrate shard via Microsoft Entra ID, Viva Engage deletes its copy of the Q&A content for that meeting within 30 days of user deletion.

## Retention and deletion

Retention of content follows the retention policies set for Viva Engage – whether or not you have different policies set for Viva Engage and Teams.