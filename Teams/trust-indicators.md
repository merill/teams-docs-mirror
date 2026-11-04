---
layout: Conceptual
title: Representation of users outside of your organization - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/trust-indicators
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Understanding how users outside of your organization are represented with badges.
author: sahibsingh2405
manager: daro
ms.author: sasingh
ms.service: msteams
ms.topic: feature-guide
ms.date: 2025-09-23T00:00:00.0000000Z
ms.subservice: msteams-admin
locale: en-us
document_id: 36bff020-fa28-8c0c-d204-a18beb95ae75
document_version_independent_id: 36bff020-fa28-8c0c-d204-a18beb95ae75
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/trust-indicators.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: trust-indicators
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/trust-indicators.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 525d47c7-d7fa-7dbc-f158-f3764ef4df06
---

# Representation of users outside of your organization - Microsoft Teams | Microsoft Learn

## Trust Indicators

**Trust Indicators** are visual labels (badges or icons) next to people’s names in Microsoft Teams that signal the person’s identity trust level. They're designed to help you immediately tell if someone in Teams is **external to your organization**, a **guest in your organization**, or an **anonymous meeting participant**, so you can avoid oversharing sensitive information with the wrong audience. 

Only people **outside** your organization, except multitenant organization (MTO) users, have a Trust Indicator. Internal colleagues have no badge. Teams displays these indicators wherever people’s names appear, like in chat messages, participant lists, calls, search results, notifications, activity list, and profile cards. 

### Trust Indicators come in different sizes

**Trust Indicators** in Teams are deliberately designed in multiple visual formats, so they remain effective yet unobtrusive across all experiences. There are **two badge variants:**

- Full badge
- Icon-only

These different variants ensure that the indicator can scale to different UI surfaces without losing meaning.

![main](media/trust-indicators/main1.png)

### Types of Trust Indicators and When They Appear

Whenever you interact with someone from outside your organization, Teams displays one of several Trust Indicator badges or icons next to their name. The label on the badge tells you the user’s category, and the exact badge you see depends on how that person is related to you or your organization.

#### 1. External-Familiar

**Who are they:** Someone outside your organization that you or your organization knows or trusts.

**Represented by:**

![](media/trust-indicators/familiar.png)

| Appears when the user is | Tooltip shown on hover or profile card |
| --- | --- |
| Part of an external organization that your organization trusts. [Learn more about specifying trusted Microsoft 365 organizations.](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings)**Note:** For cross-cloud tenants, this label appears only if you have a cross-cloud trust arrangement with that tenant. | "[Name] is part of a trusted organization." |
| Member of a shared channel with your organization. [Learn more about shared channels.](/en-us/microsoftteams/shared-channels)**Note 1:** For cross-cloud tenants, this label appears only if you have a cross-cloud trust arrangement with that tenant. **Note 2:** If you have B2B direct connect with an organization for Shared Channels but they're not part of your organization's allow list, you will see them as External-Unfamiliar outside of Shared Channels. | "[Name] is part of a trusted organization." |
| From an organization, with a cross-cloud trust arrangement with yours. [Learn more about cross-cloud meetings.](/en-us/microsoftteams/cross-cloud-meetings) | "[Name] is part of a trusted organization." |
| A phone number you added as a contact | "[Name] is not part of your organization but is someone you’ve added as a contact." |
| Using an ACS application trusted by your organization. [Learn more about allowed ACS resources.](/en-us/powershell/module/microsoftteams/set-csteamsacsfederationconfiguration?view=teams-ps) | "This person is not part of your organization, but is using an application your organization trusts." |

#### 2. External-Unfamiliar

**Who are they:** Someone from outside your organization that you or your organization doesn’t explicitly trust or recognize. 

**Represented by:**

![](media/trust-indicators/unfamiliar.png)

| Appears when the user is | Tooltip shown on hover or profile card |
| --- | --- |
| Outside of your organization and your organization has allowed communication from all external domains. [Learn more about external access settings.](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings) | "This person’s org hasn't yet been added to your org's trusted list." |
| From an organization that is not part of your organization's allow list. [Learn more about external access settings.](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings) | "This person’s org hasn't yet been added to your org's trusted list." |
| From an organization that is not part of your organization's block list. [Learn more about external access settings.](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings) | "This person’s org hasn't yet been added to your org's trusted list." |
| From an organization, that your organization blocks. Note: You can encounter such users only in meetings. [Learn more about external access settings.](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings) | "This person’s org has either been blocked by yours, or their org has blocked yours." |
| From an organization, that blocked your organization. Note: You can encounter such users only in meetings. [Learn more about external access settings.](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings) | "This person’s org has either been blocked by yours, or their org has blocked yours." |
| An unmanaged account (For example, a personal account). [Learn more about collaborating with unmanaged accounts.](/en-us/microsoftteams/trusted-organizations-external-meetings-chat?tabs=organization-settings) | "This person isn't using Teams with an org-managed account." |
| A phone number that’s not in your contacts | "This person is not part of your organization." |
| An email-based user not on Teams | "This person is not part of your organization." |

#### 3. Guest

**Who are they:** A person from outside your organization, added as a Microsoft Entra B2B Guest in your organization.

**Represented by:**

![](media/trust-indicators/guest.png)

| Appears when the user is | Tooltip shown on hover or profile card |
| --- | --- |
| When the person is added as a Microsoft Entra B2B guest in your organization. [Learn more about Microsoft Entra B2B guest access.](/en-us/microsoftteams/guest-access) | "[Name] has been added as a guest in your organization." |

#### 4. Unverified

**Who are they:** An anonymous user that Teams can’t verify. 

**Represented by:**

![](media/trust-indicators/unverified.png)

| Appears when the user is | Tooltip shown on hover or profile card |
| --- | --- |
| Someone who joins a meeting anonymously without signing in or verifying their email address. [Learn more about joining a meeting anonymously.](/en-us/microsoftteams/anonymous-users-in-meetings) | "This person doesn’t have a Teams account. We can’t verify their identity." |
| Using an ACS application not explicitly trusted by your organization. [Learn more about allowed ACS resources.](/en-us/powershell/module/microsoftteams/set-csteamsacsfederationconfiguration?view=teams-ps) | "This person is not part of your organization. We can't verify their identity." |

#### 5. Group Indicator

**Who are they:** A group level indicator for meeting chats, group chats, or channels that include someone from outside your organization.

**Represented by:**

![](media/trust-indicators/external-group.png)

| Appears when | Tooltip shown on hover or profile card |
| --- | --- |
| Shown when a Group Chat or a Meeting Chat you're a part of has any one of the following present in it: External-Familiar, External-Unfamiliar, Unverified, Email Verified | "This group has members that are not part of your organization." |

#### 6. Email Verified

**Who are they:** A person who verified ownership of an email address.

**Represented by:**

![](media/trust-indicators/email-verified.png)

| Appears when | Tooltip shown on hover or profile card |
| --- | --- |
| An external participant verifies their email address (for example, via a one-time passcode) before joining a meeting. [Learn more about verifying with an email code.](/en-us/microsoftteams/anonymous-users-in-meetings) | "This person has verified their email address before joining this meeting." |

#### 7. Multitenant Organization (MTO) Label

**Who are they:** Someone from an organization closely linked with yours (with a special trust relationship).**Note:** MTO users by default don't get any label unless the admin sets the label. 

| Appears when | Tooltip shown on hover or profile card |
| --- | --- |
| Your organization has a multitenant organization (MTO) partnership with another organization, and the person is from that partner organization. [Learn more about multitenant organization (MTO).](/en-us/entra/identity/multi-tenant-organizations/overview) | "[MTO Name]" |

### Supporting banners with the compose box

Beyond the Trust Indicator badges themselves, Teams introduces an **alert banner with the message compose box** in any chat, meeting, or channel that includes external participants. This banner acts as an extra safeguard, surfacing *at the moment you’re writing* a message to remind you of your audience. 

![A screenshot which shows the banner above the compose box.](media/trustindicators/banner-gray.png)