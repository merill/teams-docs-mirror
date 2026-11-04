---
layout: Conceptual
title: Configure security desk notifications - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/emergency-calling-security-desk-notifications
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: pavellatif
manager: roykuntz
ms.reviewer: pavellatif
ms.date: 2026-10-20T00:00:00.0000000Z
ms.topic: how-to
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
description: Learn how to configure security desk notifications for emergency calling.
locale: en-us
document_id: 7b74b230-607e-d1f2-56ba-b2ae575bda65
document_version_independent_id: 7b74b230-607e-d1f2-56ba-b2ae575bda65
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/emergency-calling-security-desk-notifications.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: emergency-calling-security-desk-notifications
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/emergency-calling-security-desk-notifications.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: f6023c2c-2857-bd19-f58f-bbcf62b9e143
---

# Configure security desk notifications - Microsoft Teams | Microsoft Learn

This article is for administrators and IT professionals who are configuring security desk notifications for emergency calling. Before reading this article, be sure to read [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing).

Security desk notifications are available with Microsoft Calling Plans, Operator Connect, and Direct Routing.

You can configure who to notify during an emergency call and how to notify them. Teams notification recipients can receive a chat notification only or also be conferenced into the call. You can also specify an external PSTN number to call and join the emergency call when you select either conference mode.

The notification mode determines how Teams and PSTN notification recipients join the call:

| Notification mode | Teams notification recipients | PSTN notification recipient |
| --- | --- | --- |
| **Conferenced in but are muted** (`ConferenceMuted`) | Join muted and can't unmute. | Joins muted and can't unmute. |
| **Conferenced in and are unmuted** (`ConferenceUnMuted`) | Join muted and can unmute to participate. | Joins unmuted and can participate. |

Important

When **Conferenced in and are unmuted** (`ConferenceUnMuted`) is selected, PSTN notification recipients join unmuted, unlike Teams notification recipients, who join muted and can unmute. PSTN recipients who want to mute their audio must use their phone's local mute control.

During an emergency call, a security desk is conferenced into the call, and the security desk user experience is determined by the Teams emergency calling policy. A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification. If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.

You can also configure extended notification settings per emergency number. For example, you can specify how a call to the emergency test number 933 is handled without notifying the security desk.

## Configure security desk notifications

You configure security desk notifications by using emergency calling policies, which you set by using the Teams admin center or by using PowerShell.

You can grant an emergency calling policy to a Teams user account, assign to a network site, or both. When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:

- If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.
- If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.
- If the Teams client is unable to obtain an emergency calling policy, then the user isn't enabled for security desk notification.

### Use Teams admin center

To configure security desk notifications by using the Teams admin center, go to **Voice** &gt; **Emergency policies**, select the **Calling policies** tab, and then select **Add**.

For each emergency number, specify the **Emergency dial string**, the **Number to dial for emergency notifications**, the **Notification mode**, and the associated **Users and groups for emergency calls Notification.**

For more information about using the Teams admin center, see [Manage emergency calling policies](manage-emergency-calling-policies).

### Use PowerShell

To configure security desk notifications by using PowerShell, use the [Set-CsTeamsEmergencyCallingPolicy](/en-us/powershell/module/teams/set-csteamsemergencycallingpolicy) cmdlet.

The following example modifies an existing policy instance with identity TestECP and specifies the notification groups 123@contoso.com and 567@contoso.com:

```PowerShell
Set-CsTeamsEmergencyCallingPolicy -Identity "TestECP" -NotificationGroup "123@contoso.com;567@contoso.com"
```

## Configure extended notifications

By using extended notifications, you can configure specific notification settings for each emergency number. For example, you can specify settings for the emergency number 911 and for the test emergency number 933. By using this functionality, you can avoid notifying your security desk for test emergency calls.

- For each emergency number, set values for **Emergency dial string**, **Number to dial for emergency notifications**, **Notification mode**, and associated **Notification group**.
- You can define an extended notification for the test emergency number 933. Because this is a test emergency number, no notifications are sent to the security desk.
- You can have more than one notification group per number.
- You can only enter a number in the **Number to dial for emergency calls notifications**, if you select Conferenced in but are muted or conferenced in and are unmuted in the **Notification mode.**

**Emergency calling policy example** In the following example, you configure the emergency calling policy with full security desk configuration. Set extended notifications for the test emergency number 933 to null.

- Notification group: alert@contoso.com
- Notification Dial Out Number: 14255551234
- Notification Mode: Conferenced in and are unmuted
- External Lookup Mode: On

The settings are:

| Emergency dial string | Notification groups | Number to dial for emergency notifications | Notification mode |
| --- | --- | --- | --- |
| default | alert@contoso.com | 14255551234 | Conferenced in and are unmuted |
| 933 |  |  | None |

Note

If you configure any extended notifications with a Notification Mode of Conferenced in, muted or unmuted, then a default emergency number, no dial string specified, must be set with at least one user, group, or PSTN number and a Notification Mode of Conferenced in. See the example above.

If you're using Calling Plan or Operator Connect, the emergency numbers are predefined (in our example, 911 and 933). If you're using Direct Routing, you need to define the numbers in an emergency call routing policy for Direct Routing. For more information, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies).

### Use the Teams admin center

To configure the extended notifications example by using the Teams admin center, go to **Voice &gt; Emergency policies**, select the **Calling policies** tab, and then select **Add**.

For each emergency number, specify the **Emergency dial string**, the **Number to dial for emergency notifications**, the **Notification mode**, and the associated **Users and groups for emergency calls Notification.**

For more information about using the Teams admin center, see [Manage emergency calling policies](manage-emergency-calling-policies).

### Use PowerShell

To configure the extended notifications by using the [New-CsTeamsEmergencyCallingPolicy](/en-us/powershell/module/teams/new-csteamsemergencycallingpolicy) cmdlet, see the following examples:

**Emergency Calling Policy example**

```powershell
$en1 = New-CsTeamsEmergencyCallingExtendedNotification -EmergencyDialString "933"
New-CsTeamsEmergencyCallingPolicy -Identity ECP1 -Description "Test ECP1" -NotificationGroup "alert@contoso.com" -NotificationDialOutNumber "+14255551234" -NotificationMode ConferenceUnMuted -ExternalLocationLookupMode Enabled -ExtendedNotifications @{add=$en1}
```