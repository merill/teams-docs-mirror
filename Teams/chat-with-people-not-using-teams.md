---
layout: Conceptual
title: Chat with anyone not using Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/chat-with-people-not-using-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Microsoft Teams introduces a new capability allowing users to start a chat with anyone who has an email address, even if they're not currently using Teams
author: niteshgolchha85
ms.author: nigolc
manager: pamgreen
ms.reviewer: daro
ms.service: msteams
ms.topic: overview
ms.date: 2025-11-11T00:00:00.0000000Z
ms.subservice: teams-chat
locale: en-us
document_id: edc8ba36-121b-5ea1-5158-aecce3f2db74
document_version_independent_id: edc8ba36-121b-5ea1-5158-aecce3f2db74
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/chat-with-people-not-using-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: chat-with-people-not-using-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/chat-with-people-not-using-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 24d06035-461f-8474-6072-ec2e8fae32f8
---

# Chat with anyone not using Teams - Microsoft Teams | Microsoft Learn

Microsoft Teams allows users to start a chat with anyone who has an email address, even if they're not currently using Teams. This feature enables seamless communication and collaboration with external contacts without requiring them to download an app or create an account. Admins have full control over this feature and can disable it if necessary, ensuring compliance with organizational policies.

## Key Highlights

#### Simple and Secure

- Only tenant users can initiate the chat thread.
- Non-Microsoft 365 users are invited and created as B2B guests in your tenant and they can't initiate chats with users in your organization.
- All chat data resides within your tenant's security, compliance, and data residency perimeter.

#### Frictionless Experience

- No tenant switching for your users to chat with non-Microsoft 365 users.
- External participants join easily without a lengthy sign-up process.

#### Enterprise-grade Controls

- Admins can disable the feature entirely. All chat invitations to non-Microsoft 365 users continue to honor your organization's B2B policies.
- Full visibility and control over invitations, domains, and usage through existing B2B policies.

## How it Works

Employees can start secure chats with external contacts (customers, vendors, partners) without leaving your tenant. This feature utilizes Entra's B2B guest model, ensuring compliance and control while providing a simple user experience.

#### User Initiates Chat

Enter an external email of a user not on the Microsoft 365 network and start a 1:1 or group chat just like internal conversations.

#### Teams Checks Policies

Before the chat is initiated, Teams evaluates your organization's settings:

- If the [UseB2BInvitesToAddExternalUsers](/en-us/powershell/module/microsoftteams/set-csteamsmessagingpolicy?view=teams-ps&amp;preserve-view=true) policy is turned off, Teams checks the setting under [External Access &gt; People in my organization can communicate with unmanaged Teams accounts](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings). If this setting is enabled, Teams kicks-off chat with unmanaged accounts.
- If the [UseB2BInvitesToAddExternalUsers](/en-us/powershell/module/microsoftteams/set-csteamsmessagingpolicy?view=teams-ps&amp;preserve-view=true) policy is turned on, Teams enforces your organization's B2B Collaboration policies, including any configured allow-lists or deny-lists for external domains.

#### Just-in-Time Access

If permitted, Teams creates or reuses a B2B guest identity for that person in your tenant.

#### Chat Runs Inside Your Boundary

Messages, files, and Loop components stay under your security and compliance controls.

#### Scoped Sharing

External participants see only shared content in the chat and have no access to Teams, channels, or SharePoint unless explicitly granted.

#### Compliance Applies Automatically

Data Loss Prevention (DLP), retention, eDiscovery, sensitivity labels, and auditing all apply as they do for any other Entra B2B guests in your tenant.

#### Easy Offboarding

Remove the participant or revoke their guest account to cut off access instantly.

#### External User Experience

- Receives an invite and joins via link. No app download required.
- Chats in Teams normally but access is limited to the specific chats they were invited to.

## FAQs

#### How can admins disable the feature?

Admins can disable this feature through Teams Messaging Policies by running the following PowerShell command:

```powershell
Set-CsTeamsMessagingPolicy -Identity "Global" -UseB2BInvitesToAddExternalUsers $false
```

This command sets the **UseB2BInvitesToAddExternalUsers** flag to **$false**, preventing users from inviting external participants via this feature. It can be applied globally or to specific messaging policies for granular control. If chat with unmanaged users is disallowed, then users are no longer able to start chats with non-Microsoft 365 users using this feature. However, other external collaboration features (like channels) remain unaffected. Federation (external access) works independent of this feature.

#### Does disabling this feature affect existing B2B Collaboration?

Disabling this feature only stops chat-based B2B invitations. Existing B2B guest access for channels, files, and meetings remains unaffected. This feature is an extension of B2B for chat only—it doesn't override or remove existing B2B guest accounts or permissions.

#### Can external users initiate chats?

External users can't initiate chats with your organization's users. This feature ensures that only your tenant users can initiate external chats, maintaining control and compliance boundaries. External users can only respond to chat requests from your organization's users.

**Alternative Options for External Users:**

**Chat with external managed accounts:** If federation is enabled for their domain, external users can start a chat using standard Teams federation capabilities. [Learn More](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings)

- **Chat with external unmanaged accounts**: You can choose to enable or disable chats and meetings with external unmanaged Teams users (accounts not managed by an organization, such as Microsoft Teams (free)). If enabled, you can also control if people with unmanaged Teams accounts can start chats and meetings with users in your organization. [Learn more](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings)
- **B2B Guest Invitation in their tenant:** External organizations can invite your users as **B2B guests** into their own tenant, provided your outbound B2B policies allow it. [Learn More](/en-us/entra/external-id/cross-tenant-access-settings-b2b-collaboration)

#### Does this feature conflict with External Access settings?

This feature works independently of External Access (Federation) settings, governing B2B guest invitations for chat with non-Microsoft 365 users only. Both can coexist without conflict.

#### How is this experience different from the current experience?

Currently, external users can only be invited as B2B guests in Teams through Teams channels. With this feature, users can invite external participants directly into 1:1 or group chats without creating a team or channel. Additionally, non-Microsoft 365 external users invited through chat don't need to sign up for an unmanaged account to respond, ensuring a frictionless reply experience while keeping chats secure within the tenant's boundary.

#### Does this feature override the B2B Guest Access policy?

This feature respects your existing **B2B Guest Access policies**. If your tenant blocks guest invitations, this feature won't allow external chat invitations to non-Microsoft 365 users. If your tenant allows only users with admin roles to invite guests, then only those users can send the chat invitation to non-Microsoft 365 users.

#### Can in-tenant users chat with external users who aren't on the allowed federation list but are on Teams?

Your federation policies are respected as these policies govern how your users find and chat with Teams users. 

#### Can users share documents with the recipient?

Content sharing policies primarily depend on your SharePoint/OneDrive settings. You can further control file sharing with external customers in Teams chat. [Learn More](/en-us/powershell/module/microsoftteams/set-csteamsfilespolicy?view=teams-ps&amp;preserve-view=true)