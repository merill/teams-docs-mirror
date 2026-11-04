---
layout: Conceptual
title: Manage retention policies for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/retention-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: DivySri-RK
ms.author: divyasrirk
ms.reviewer:
- anwara
- prvijay
ms.date: 2025-02-19T00:00:00.0000000Z
manager: prgholve
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
description: Use retention policies for Microsoft Teams to keep messages that your organization needs to comply with internal policies, industry regulations, or legal requirements, and to delete messages that are considered a liability or has no legal business value.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- tier1
- purview-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: f55c52a5-5841-b9c9-1607-2013dc3f2e20
document_version_independent_id: 16d93458-5e01-646f-dac5-31306cc7f3fb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/retention-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: retention-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/retention-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f51b0f8b-0a17-520a-4927-bc00efcd9a26
---

# Manage retention policies for Microsoft Teams - Microsoft Teams | Microsoft Learn

Note

If you're seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

The information on this page is for IT administrators who manage these retention policies.

Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization. You can configure retention settings to keep data needed to comply with your organization's internal policies, industry regulations, or legal requirements. You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.

Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it. The start of the retention period for these actions is always based on when a message is created. You can apply a Teams retention policy to your entire organization or to specific users and teams. Retention labels aren't supported for Teams.

Note

[Shared channels](shared-channels) are supported by retention policies.

To learn more about retention solutions in Microsoft 365, see [Learn about retention policies and retention labels](/en-us/purview/retention).

Users who are subject to a retention policy for Teams must have an appropriate license, such as Office 365 E3 or Office 365 A3. For other licensing options for these retention policies, see the [Microsoft Purview Data Lifecycle Management](/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management) section from [Microsoft 365 licensing guidance for security & compliance](/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). To learn more about licensing for Teams, see [Microsoft Teams service description](/en-us/office365/servicedescriptions/teams-service-description).

## How Teams retention policies support retain and delete actions

If you configure a Teams retention policy to retain chats or channel messages, users can still edit and delete their messages in their Teams app. Although users no longer see their edited or deleted messages in Teams, data from these messages is stored in a secured location designed for eDiscovery searches by compliance administrators. Permanent deletion of this data doesn't happen before the end of the configured retention period, or if another retention policy is configured to retain this data, or it's subject to an [eDiscovery hold](/en-us/purview/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).

When a retention policy is configured to delete chats and channel messages, these messages become eligible for automatic deletion. If the messages are still displayed in the Teams app, they disappear from there and users are informed that a retention policy has deleted these messages. If the messages were previously subject to a retain action and have been edited or deleted by users, these messages will now be deleted from the secured location and no longer returned in eDiscovery searches.

For detailed information about how these policies work depending on your policy configuration and user actions, and what message data is included and excluded for Teams retention policies, see [Learn about retention for Microsoft Teams](/en-us/purview/retention-policies-teams). That page also explains why you might sometimes experience delays when retention policies delete messages. For example, messages can be visible to users in the Teams app up to seven days after the expiration period you've configured in the retention policy.

If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts. For example:

- If there's a conflict between retaining or deleting the same content, the content is always retained in the secured location so that it remains searchable with eDiscovery for compliance administrators.

    This principle also applies to messages that are under eDiscovery holds for legal or investigative reasons.
- If there's a conflict in how long to retain the same content, it's retained in the secured location for the longest retention period.

These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/en-us/purview/retention#the-principles-of-retention-or-what-takes-precedence)

## Troubleshooting info

Note

Audience: This guidance is for IT administrators and compliance administrators who manage Teams retention policies and investigate missing messages.

Determine whether missing messages were deleted by a retention policy

Before contacting support about missing Teams chat or channel messages, verify the following:

1. Check the message displayed in Teams. When a retention policy deletes older private or group chat messages, Teams displays a message stating that older messages were deleted because of the organization’s retention policy. For channel messages, Teams displays a retention-policy deletion notice in place of the deleted parent message.
2. Confirm that the retention policy applies. Verify that the policy includes the affected user or team, the applicable message location, and the message creation date. Teams retention periods are calculated from the date the message was created.
3. Check whether the user edited or deleted the message. Users can edit or delete messages while a retention policy preserves a compliance copy in a secured location. The retained copy can remain available to eDiscovery even though the original message is no longer visible in Teams.
4. Review Microsoft Purview eDiscovery results. If the message is returned in eDiscovery but is no longer visible in Teams, the message might be retained because of a retention policy or eDiscovery hold. A retained compliance copy is not expected to remain visible in the Teams conversation.
5. Review policy conflicts and holds. Another retention policy or eDiscovery hold might retain the message for longer than the policy being investigated.
6. Allow for deletion processing. Messages can remain visible in Teams for up to seven days after the configured retention period expires.

## When to use retention policies for Teams

In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.

You can efficiently configure a single retention policy for all Teams messages. Or, for more fine-grained control, you can:

- Have separate retention policies for private chats (1:1 or 1: many chats), messages from standard channels, or messages from private channels.
- Apply the policies only to specific users or teams in your organization. For Teams chats and private channels, you can select which users the policy applies to. For Teams channel messages, you can select which teams the policy applies to.

For example, for standard channel messages: Create a retention policy for specific teams in your organization and configure that policy with a delete action after one year. Then create another retention policy for standard channel messages for all other teams and configure that policy with a delete action after three years.

## Create and manage retention policies for Teams

To create or edit a retention policy for Teams messages, use the instructions from [Create and configure a retention policy](/en-us/purview/create-retention-policies?tabs=teams-retention#create-and-configure-a-retention-policy) and the **Retention policy for Teams** tab.

That page has additional information about creating and managing retention policies for other workloads in Microsoft 365. For example, you might want to also create a retention policy for Microsoft 365 groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.

Data can be stored in the form of screenshots in an end user's local drive through the Windows Recall feature and is managed separately. See the [Manage Windows Recall](/en-us/windows/client-management/manage-recall) article for more information.

## End-user experience

For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.

For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire. the user sees "This message has been deleted because of a Retention Policy" in place of the parent message.

Note

The displayed messages that users see as a result of deleted messages aren't configurable at this time.

The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b). This documentation for end users helps to answer basic questions about why their messages have been deleted. However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.