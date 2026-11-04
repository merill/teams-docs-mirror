---
layout: Conceptual
title: Unified external collab settings management - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/unified-external-collab-settings-management-experience
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Manage external collab org settings using a guided setup
author: MJMicrosoft
ms.author: majaisin
manager: daro
ms.service: msteams
ms.subservice: teams-chat
ms.topic: module-guided-project
ms.date: 2025-11-07T00:00:00.0000000Z
locale: en-us
document_id: 528478aa-575c-9eeb-f524-6db86689faa1
document_version_independent_id: 528478aa-575c-9eeb-f524-6db86689faa1
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/unified-external-collab-settings-management-experience.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: unified-external-collab-settings-management-experience
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/unified-external-collab-settings-management-experience.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c8a8ccfc-f659-9313-eb5b-45cab17df715
---

# Unified external collab settings management - Microsoft Teams | Microsoft Learn

Microsoft Teams now offers a streamlined experience for configuring external collaboration settings through Teams Admin Center. This update enables IT admins to configure external collaboration for all users securely and efficiently. Admins can select from predefined modes for quick set up or customize settings when more flexibility is required.

## What is the unified external collab settings management experience?

The External Collaboration section in the Teams Admin Center (TAC) left rail provides a unified location to manage all external collaboration settings. The section includes:

1. **Overview:** The overview page provides a snapshot of the organization's external collaboration posture at a glance. It also offers a simplified management experience that allows IT admins to setup external collaboration policies across the organization while keeping custom user or group settings intact.
2. **External access:** This is the existing page to manage configuration of federation and communication with external domains, including unmanaged and trial tenants.
3. **B2B Guest Access:** This is the existing page to manage guest access settings for external users invited to Teams and channels.
4. **B2B Member Access:** This is an existing page to manage copilot settings for B2B member users invited to the organization.

Note

B2B guest access and member access pages aren't displayed for organizations using unified policies and settings management in Teams Admin Center.

## Overview of External Collaboration Modes

Admins can now manage their external collaboration settings by choosing between two predefined modes—Open and Controlled—or opt for a Custom mode if the defaults don't meet their organization's needs. The custom settings experience also highlights the relationships between different settings, helping admins understand how changes to one setting may impact others. Additionally, tenants can manage certain settings that exist outside of TAC, such as B2B Direct Connect, to enable shared channels. The experience always reflects the current state of settings, including changes made via PowerShell or other management interfaces, and dynamically adjusts the tenant's mode based on the active configuration.

- **Open (Mode 1)** – This predefined mode is recommended for organizations that are open to external collaboration across chats, calls, meetings, and teams and channels (including shared channels). This mode enables broad access and interaction with external users, including:
- Chats, calls, and meetings with all external domains and Teams personal accounts using federation or Teams external access.
- Teams and channels collaboration with all Microsoft and non-Microsoft partners using B2B collab and B2B direct connect.
- **Controlled (Mode 2)** – This predefined mode offers a balanced yet meaningful external collaboration engagement posture. Recommended for organizations that prefer limited external collaboration and want to manage or enable it selectively. This mode:

    - Aligns with current defaults for M365 enterprise and education tenants.
    - Enables chats, calls, and meetings with all external domains using federation or external access but blocks collab in shared channels.
- **Custom** – Recommended for organizations whose collaboration needs aren't met by Open or Controlled modes. This mode:
- Provides full control over each external collaboration setting

    - Allows admins to configure org-wide external collab policies manually across chats, calls, meetings, and teams and channels (including shared channels)

Note

Any changes made in custom mode only apply to the Global org-wide policies & Org-wide settings. These settings don't impact (or) change any of the custom policies.

## Setting details and values:

Settings are divided into two buckets:

**Who gets access**: These settings control enabling or disabling external collaboration for users in your organization and guests.

| Modality | Setting Name | Value in Open mode | Value in Controlled mode |
| --- | --- | --- | --- |
| Teams and channels | Guest access | On | On |
| Shared channels | B2B direct connect inbound | Allowed for all users and applications | Blocked for all users and applications |
|  | B2B direct connect outbound | Allowed for all users and applications | Blocked for all users and application |
|  | Invite external users to shared channels | On | On |
|  | Join external shared channels | On | On |
| Chats, calls, and meetings (external access) | Teams and Skype for Business users in external organizations | Allow all external domains | Allow all external domains |
|  | People in my organization can communicate with personal Teams accounts | On | On |
|  | People in my organization can communicate with accounts in trial Teams tenant | Off | Off |

**What external users can do**: These settings control what guests or users engaged in external collaboration can do in different external collab surfaces.

| Modality | Setting Name | Value in Open and Controlled mode |
| --- | --- | --- |
| Teams and channels | Tagging -&gt; Who can manage tags | Microsoft default |
| Shared channels | Provide a link to my support request page | Off |
| Calls | Routing for PSTN calls | Use default settings |
|  | Routing for federated calls | Use default settings |
|  | Spam filtering | On |
| Meetings | Who can register for meeting | Everyone |
|  | Anonymous users can join a meeting | On |
|  | Anonymous users and dial-in callers can start a meeting | People in my org and guests |
|  | Who can bypass the lobby | Everyone |
|  | People can join external meetings hosted by | Anyone |
|  | Anonymous users can interact with apps in meetings | On |
|  | Meeting chat | On for everyone |
|  | External meeting chat (When on, people can read or write messages in external meeting chats from untrusted organizations) | On |
|  | Who can present | Everyone |
|  | External participants can give or request control | Off |
|  | Participants can share content in external meeting hosted by | Any Org |

## Using guided set up to manage external collaboration settings:

#### View external collab settings summary:

The new experience is enabled for all customers. To use the new unified settings experience, navigate to the "Overview" page under external collaboration settings section on the left rail. The Overview page shows your organization’s external collaboration mode at the tenant level, giving admins quick visibility into global settings. The page reflects tenant's current setup and updates based on changes made to settings.

![Screenshot that shows the external collaboration settings for the organization.](media/unified-external-collab-settings-management-experience/external-collab-overview.png)

#### View details or change settings:

To view details or change settings at the org level, admins can navigate to "Change mode" experience. From the modes experience, admins can either select one of the preset modes or navigate to custom mode to manage external collaboration settings for their organization.

![Screenshot that shows the external collaboration setting modes. Admins can pick from preset modes or customize settings.](media/unified-external-collab-settings-management-experience/external-collab-modes.png)

After making changes, admins click next and can view, compare existing and new changes and confirm new configuration.

![Screenshot that shows the list of settings modified by the admin and asks for confirmation.](media/unified-external-collab-settings-management-experience/external-collab-setting-change-confirmation.png)

Admins can see the confirmation page of all the settings applied on their behalf. An error shall be shown in case there's an error and one or more settings couldn't be applied.

![Screenshot that shows the confirmation of settings updated after confirmation.](media/unified-external-collab-settings-management-experience/setting-update-confirmation.png)

#### Copying settings from Open or Controlled mode:

Admins don't have to start from scratch to customize settings. Admins who prefer the Open or Controlled preset but require additional changes can copy the preset’s settings and adjust them within the custom settings experience.

![Screenshot that shows the option to copy settings from preset modes if an admin would want to make some changes to the preset settings available.](media/unified-external-collab-settings-management-experience/copy-external-collab-setting-modes.png)

## Role-Based Access

Since the new experience can also manage B2B direct connect settings, global admin role may be required. Table below summarizes the permissions for each admin role.

| Role | Permissions |
| --- | --- |
| Global Admin | Full access to configure all external collaboration settings and modes |
| Teams Admin | Can view settings and modify Teams related configurations. Can't change B2B direct connect or select Open mode |