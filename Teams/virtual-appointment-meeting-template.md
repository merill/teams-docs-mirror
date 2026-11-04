---
layout: Conceptual
title: Manage the Virtual appointment meeting template in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/virtual-appointment-meeting-template
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: jewilcze
ms.date: 2024-11-11T00:00:00.0000000Z
search.appverid: MET150
audience: admin
description: Learn how to manage the Virtual appointment meeting template in Teams for your organization. Your users can use this template to schedule virtual appointments with external guests, such as customers, clients, and other people outside your organization.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365-frontline
- m365initiative-meetings
- m365-virtual-appointments
locale: en-us
document_id: 3f8e8b4f-1258-f7d0-2eee-6c53eb32c33c
document_version_independent_id: 3f8e8b4f-1258-f7d0-2eee-6c53eb32c33c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/virtual-appointment-meeting-template.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: virtual-appointment-meeting-template
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/virtual-appointment-meeting-template.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: ff084eb0-634b-c5af-0549-c85e4df5d478
---

# Manage the Virtual appointment meeting template in Microsoft Teams - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png) Meetings ![Image of a x for no](/en-us/office/media/icons/cancel-teams.png) Events

![Information icon](media/info.png)**Some features described in this article require [Teams Premium](teams-add-on-licensing/licensing-enhance-teams)**.

## Overview

The Virtual appointment template is a default meeting template in Microsoft Teams that your users can use to schedule virtual appointments with external guests, such as customers, clients, and other people outside your organization. For example, use it to schedule and conduct interviews, mentorship sessions, financial consultations, virtual shopping experiences, and more.

This article gives you an overview of how to manage the Virtual appointment meeting template.

## Template settings

The Virtual appointment meeting template comes with predefined settings. To learn more, see [Predefined meeting templates included with Teams Premium](predefined-meeting-template-reference).

## Use meeting template policies to specify which users can use the template

You use meeting template policies in the Teams admin center to control which meeting templates are available to users in your organization. By default, the Global policy allows users to see and use all meeting templates, including the Virtual appointment template and any custom templates that you created.

If you want to make the template available to specific users or groups of users in your organization, you can create a custom meeting template policy, and then assign it to those users or groups.

To learn more, see [Manage meeting templates in Teams](manage-meeting-templates).

## Manage access to SMS notifications in the template

![Information icon](media/info.png)**This is a [Teams Premium](teams-add-on-licensing/licensing-enhance-teams) feature. Meeting organizers must have a Teams Premium license to use this feature.**.

Note

This feature is currently available in Australia, Canada, the Netherlands, the United Kingdom, and the United States. Your users can send SMS text notifications to people who have a valid Australia (+61 country code), Canada (+1 country code), Netherlands (+31 country code), United Kingdom (+44 country code), or United States (+1 country code) phone number. The text notifications are sent in the language of the meeting organizer.

You can control whether your users can choose to send SMS text notifications to external guests in appointments that they schedule using the template. When this feature is enabled for a user, they see the SMS notifications option in the template.

- If the user chooses **Send text notifications** (the default setting), external guests will receive appointment confirmation, update, and reminder text messages that include the Teams meeting join link and appointment details.
- If the user chooses **Don't send text notifications**, external guests won't receive text messages about their appointment.

You manage access to this feature for your users through policies that you set using the following PowerShell cmdlets:

- [New-CsTeamsVirtualAppointmentsPolicy](/en-us/powershell/module/teams/new-csteamsvirtualappointmentspolicy)
- [Set-CsTeamsVirtualAppointmentsPolicy](/en-us/powershell/module/teams/set-csteamsvirtualappointmentspolicy)
- [Grant-CsTeamsVirtualAppointmentsPolicy](/en-us/powershell/module/teams/grant-csteamsvirtualappointmentspolicy)
- [Get-CsTeamsVirtualAppointmentsPolicy](/en-us/powershell/module/teams/get-csteamsvirtualappointmentspolicy)
- [Remove-CsTeamsVirtualAppointmentsPolicy](/en-us/powershell/module/teams/remove-csteamsvirtualappointmentspolicy)

To enable or disable SMS notifications, set the **EnableSMSNotifications** parameter in the policy to `$true` (the default value) or `$false`.

### Example

By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the SMS notifications feature in the template is enabled in the policy.

Say, for example, you want to allow all users in your organization to use SMS notifications in the template except for new hires in training. In this scenario, you create a custom policy to turn off SMS notifications and assign it to new hires. All other users in your organization automatically get the global policy with the feature turned on.

In this example, we create a custom policy named New Hire SMS Policy and we turn off SMS notifications.

```PowerShell
New-CsTeamsVirtualAppointmentsPolicy -Identity "New Hire SMS Policy" -EnableSMSNotifications $false
```

Here, we assign the policy to a user named daniela@contoso.com.

```PowerShell
Grant-CsTeamsVirtualAppointmentsPolicy -Identity daniela@contoso.com -PolicyName "New Hire SMS Policy"
```

You can assign the policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of. To learn about the different ways that you can assign policies to users, see [Assign policies in Teams](policy-assignment-overview).

### Things to know

- If a user doesn't have access to this feature, either through policy restrictions or if they don't have a Teams Premium license, the SMS notifications option isn't visible in the template when they schedule a new appointment or when they edit an existing appointment in which the feature was previously enabled.
- If a user who has access to this feature chose **Send text notifications** when they scheduled an appointment, and then their access is turned off, no additional text messages are sent to the external guest.
- For the Netherlands, the **Phone number** field on the form might require an 11-digit number to successfully send SMS notifications. If you experience issues, add zeros (0) to the beginning of the phone number to reach an 11-digit value.

### SMS notifications usage report

To get an overview of SMS notifications usage across your organization, view the [SMS notifications usage report](/en-us/microsoft-365/frontline/sms-notifications-usage-report) in the Teams admin center.

## Meeting options available to external guests

When users in your organization use the template to schedule a virtual appointment, external guests get a tailored meeting invitation that includes a **Join appointment as a guest** button and other appointment details. They can use this button to easily join from any device without having to download and install Teams.

Keep in mind that some Teams meeting options might not apply to external guests or to any person who joins using the **Join appointment as a guest** button. The following meeting options are supported for guests to join:

- **Who can bypass the lobby**: The **Everyone** setting allows external guests to bypass the lobby.
- **Choose co-organizers**
- **Record automatically**
- **Allow meeting chat**: Set to **Disabled** if you want to prevent a meeting chat before, during, and after the meeting.

People within your organization receive a meeting invitation, and the appointment appears in their Teams and Outlook calendar, from where they can easily join as in any other Teams meeting. All Teams meeting options apply to attendees who join using the Teams meeting link in the meeting invitation or from the Teams or Outlook calendar.

Note

External guests need pop-up notifications allowed on their mobile and web browser for the browser-based Teams experience to function properly. This setting will show a pop-up asking for permission to access the microphone and camera for the meeting, which is required for the meeting to begin.

To learn more about how to use the Virtual appointment meeting template and about the user experience, see [Use a Teams meeting template to create a Virtual Appointment](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747).