---
layout: Conceptual
title: ServiceNow Incident Integration for Pro Management Portal - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/microsoft-teams-rooms-configure-servicenow
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: kimmatlock
ms.date: 2026-06-05T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: Medium
description: Learn about configuring the ServiceNow Incident integration from the Teams Rooms Pro Management portal
f1keywords: 
locale: en-us
document_id: 99171a71-5bc9-731e-fbd2-2234bc0c68c5
document_version_independent_id: 3a0b7200-97ba-9467-97b7-bac6ca16e9fa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/microsoft-teams-rooms-configure-servicenow.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/microsoft-teams-rooms-configure-servicenow
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/microsoft-teams-rooms-configure-servicenow.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/97159432-14a9-4307-a469-d2f2c75f0e33
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/50565c62-5f6b-4687-be38-323113c72c2e
platformId: e033873b-994d-5929-a58b-4f03dbf09f72
---

# ServiceNow Incident Integration for Pro Management Portal - Microsoft Teams | Microsoft Learn

This article describes the prerequisites and steps to configure your ServiceNow environment to accept incident notifications from the Teams Rooms Pro Management portal.

Tip

For other IT Service Management (ITSM) tools besides ServiceNow or for more granular control over the alerts, the [Incident Notification Webhook](/en-us/microsoftteams/rooms/pmp-incident-webhook-integration) should be used.

## Watch: Microsoft Teams Rooms Pro Management — Service Now Incident Integration

### Microsoft Prerequisites

- You must have an assigned Service Administrator role. For more information, see [Role-based access control with Microsoft Teams Rooms Pro Management](rooms-pro-rbac).
- This ServiceNow integration is only available in the Commercial Cloud. For government clouds, it's recommended that customers consider using email notifications and your ITSM email ingest features.

### ServiceNow prerequisites

- A Basic Authorization sign-in, OR an [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) sign-in. For more information, see [Creating Credentials](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) in ServiceNow.
- A ServiceNow instance and its instance host name and API URI
- A role of incident\_manager or higher
- A software version of ServiceNow that supports Table API

## Configure your environment

How your environment is configured is highly customizable and depends on your organization's needs. The following steps walk through how to copy your existing configuration in ServiceNow to the Teams Rooms Pro Management portal.

1. Open the ServiceNow instance you want to copy. You need to reference this as you complete the configuration form in the Teams Rooms Pro Management portal.
2. In a new browser tab, go to the [Teams Rooms Pro Management portal](https://portal.rooms.microsoft.com/) and go to **Settings**. Then, select **ServiceNow** in the left navigation menu to open the configuration form.
3. Select an authentication method to sign in and enter your ServiceNow Instance Host and API URI.
4. All required items in the ServiceNow Field column of the Field Mapping section should be prefilled. The table below contains each ServiceNow field and its corresponding Microsoft Teams Rooms field. Complete the action for each row of the Field Mapping section. For definitions of each ServiceNow field, see ServiceNow field definitions.

| ServiceNow field | Microsoft Teams Rooms field | Action |
| --- | --- | --- |
| short\_description | Incident description | No action needed. The Teams Rooms field is autofilled. |
| description | First Message | No action needed. The Teams Rooms field is autofilled. |
| assignment\_group | Room group | Copy the assignment\_group value in your ServiceNow instance and paste it into the ServiceNow value field in the configuration form. If you have more than one assignment\_group, select **Add Room Group** for each other custom value. |
| severity | Rings | Severity is a custom value in ServiceNow. It's the fourth item in the second column of your ServiceNow instance. Copy the value and paste it into the ServiceNow value field in the configuration form. If you have more than one severity value, select **Add Ring** for each other custom value. |
| Comments (optional) | Custom value\* | To add a comments field to the configuration form, select **Add** at the top of the field mapping section. Copy the comment value in your ServiceNow instance and paste it to the ServiceNow field in the configuration form. Assign it a Microsoft Teams Room field from the dropdown menu, and copy and paste the ServiceNow value. |
| state (resolved) | Custom value\* | Copy the resolution state from your ServiceNow instance and paste it into the ServiceNow value field in the configuration form. |
| close\_code | Custom value\* | In the **Resolution Information** tab of your ServiceNow instance, copy the close code and paste it into the ServiceNow value field into the configuration form. |

\*Select custom values from the dropdown menu

Note

If you can't locate your custom values, contact your ServiceNow administrator.

To add extra required fields to Resolve Incident section, select **Add**.

## Test and enable

After completing the configuration form, select **Test** at the bottom of the page. Testing is required to submit your configuration.

Once your test passes successfully, select **Submit** to save your changes. Once you're ready to enable ServiceNow for your organization, switch the **Do you want to enable ServiceNow?** toggle to **On**.

## ServiceNow field definitions

- **short\_description**: The short description field in ServiceNow is a brief, 160-character alphanumeric value that provides a summary of the incident. Short description is equivalent to incident description in the Teams Rooms Pro Management portal.
- **description**: The description field in ServiceNow is the first value in the conversation history of a ServiceNow incident. Description is equivalent to First message in the Teams Rooms Pro Management portal.
- **assignment\_group**: The assignment group field in ServiceNow is used to organize incidents. Assignment groups are equivalent to Room groups in the Teams Rooms Pro Management portal. By default, there's one room group, and more can be added. You decide how many groups there are and how to group your incidents. For example, you might choose to organize your incidents by location.
- **severity**: The severity field in ServiceNow is used to organize incidents by priority. The values that designate priority are customizable. Severity is equivalent to the Ring field in the Teams Rooms Pro Management portal. To customize rings in the Teams Rooms Pro Management portal, go to **Updates** in the left navigation menu. Then go to the **Rings** tab and select **Add ring**.
- **comments**: Comments are an optional field in ServiceNow that is used to include custom required fields from your ServiceNow instance in your Teams Rooms Pro Management portal configuration. The equivalent of comments is a custom value in the Teams Rooms Pro Management portal.
- **state (resolved)**: The state (resolved) field in ServiceNow is used to designate how an incident was resolved and is required to close an incident. The state (resolved) value is customizable. The equivalent of state (resolved) is a custom value in the Teams Rooms Pro Management portal.
- **close\_code**: A close code must be assigned to an incident once it's resolved. This value is customizable in ServiceNow. The equivalent of close code is a custom value in the Teams Rooms Pro Management portal.