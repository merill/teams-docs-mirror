---
layout: Conceptual
title: Step 4 - Configure mailbox properties - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/hybrid-meetings-device-config-mailbox
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: sohailta
ms.date: 2025-01-17T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- m365solution-teamshybrid
- m365solution-scenario
- m365initiative-meetings
- teams-rooms-devices
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
ms.localizationpriority: high
description: Configure mailbox properties of a resource account mailbox for use with Teams Rooms.
locale: en-us
document_id: dd204a0b-f2b0-a297-9a27-5040b57676a3
document_version_independent_id: dd204a0b-f2b0-a297-9a27-5040b57676a3
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/hybrid-meetings-device-config-mailbox.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: hybrid-meetings-device-config-mailbox
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/hybrid-meetings-device-config-mailbox.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: e818fce4-53fc-fbab-10fa-ffb8d772fd5c
---

# Step 4 - Configure mailbox properties - Microsoft Teams | Microsoft Learn

![IT Pro audience](media/hybrid-audience-itpro-small.png)

Based on organizational requirements, you may wish to customize how the resource account responds to and processes meeting invitations. Using Exchange PowerShell, you can set many properties, review the [Set-CalendarProcessing](/en-us/powershell/module/exchange/mailboxes/set-calendarprocessing) cmdlet for all available configurations. The following are recommended for Teams Rooms:

- **AutomateProcessing: `AutoAccept`** Meeting organizers receive the room reservation decision directly without human intervention.
- **AddOrganizerToSubject: `$false`** The meeting organizer isn't added to the subject of the meeting request on the resource account calendar.
- **AllowRecurringMeetings: `$true`** Recurring meetings are accepted.
- **DeleteAttachments: `$true`** Teams Rooms devices can't access meeting attachments, deleting attachments ensures they're not stored on the resource account calendar.
- **DeleteComments: `$false`** Keep any text in the message body of incoming meeting requests which is required to create join buttons for [third-party meetings](/en-us/microsoftteams/rooms/third-party-join) on a Teams Rooms device.
- **DeleteSubject: `$false`** Keep the subject of incoming meeting requests on the resource accounts calendar.
- **ProcessExternalMeetingMessages: `$true`** Specifies whether to process meeting requests organized outside your Exchange environment. This option is required for meeting invites sent directly by an external organizer as well external organized meetings forwarded by an internal user.
- **RemovePrivateProperty: `$false`** Ensures the private flag that sent by the meeting organizer in the original meeting request remains as specified.
- **AddAdditionalResponse: `$true`** The text specified by the AdditionalResponse parameter is added to meeting requests.
- **AdditionalResponse: "This is a Microsoft Teams Meeting room!"** The text to add to the meeting acceptance body. You can also format HTML content in the automatic reply if you wish.

To configure these properties, you need to connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](/en-us/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&amp;preserve-view=true).

The following example sets the properties for the `ConferenceRoom01` resource account:

```PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowRecurringMeetings $true -DeleteAttachments $true -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```