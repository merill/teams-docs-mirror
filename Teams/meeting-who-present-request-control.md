---
layout: Conceptual
title: Manage who can present and request control in Teams meetings and events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/meeting-who-present-request-control
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: nakulm, bryannyce
ms.date: 2025-04-30T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- Tier2
- m365initiative-meetings
f1.keywords:
- NOCSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: Learn to manage who can present and take control in Teams meetings.
locale: en-us
document_id: c84fd97b-30f5-a80a-7d09-5691928d46b6
document_version_independent_id: c84fd97b-30f5-a80a-7d09-5691928d46b6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/meeting-who-present-request-control.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: meeting-who-present-request-control
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/meeting-who-present-request-control.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 83c5a04f-1229-e7e1-5694-6199caf9d13c
---

# Manage who can present and request control in Teams meetings and events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

As an admin, you can manage who can present in meetings and events and whether participants and external participants can request control of the presentation.

Note

In Teams events, this feature is available only in events with up to 1,000 attendees.

## Manage who can present and request control

To manage who can present and request control, follow these steps:

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select the policy that you want to edit or create a new one.
3. Go to the **Content sharing** section.
4. Select the values you want for **Who can present**, **Participants can give or request control**, and **External participants can give or request control** settings.
5. Select **Save**.

### Manage who can present

**Who can present** lets organizers choose who can be presenters in a meeting or event. To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/office/c16fa7d0-1666-4dde-8686-0a0bfe16e019).

This setting is a per-user policy that lets you choose the default value for the **Who can present** setting that organizers see in their Meeting options. The **Who can present** policy setting affects all meetings and events, including Meet Now meetings.

To specify the default value of the **Who can present** setting in Teams, select one of the following settings in the **Who can present** policy:

| Option | Behavior |
| --- | --- |
| Only organizers and co-organizers | Only the organizer and chosen co-organizers can present during the meeting or event. All the other participants join the meeting or event as attendees. |
| People in my org and guests | Authenticated users in your org, including guests, join the meeting or event as a presenter and can present. |
| Everyone | **This is the default.** Everyone attending the meeting or event joins as a presenter and can present. This setting corresponds to the **Everyone** setting in Teams. |

After you set the default value, organizers can still change this setting through their Meeting options in Teams to choose who can present in their meetings and events.

### Participants can give or request control

This setting is a per-user policy that controls whether users with this assigned policy can give, be given, or request control of the shared desktop or window. To give control, your users can hover over the top of the screen.

You can toggle this setting **On** or **Off** in the Teams admin center or manage this policy in PowerShell.

When this assigned policy is **On** for a user, the **Give Control** option is displayed in the top bar during a sharing session.

When this assigned policy is **Off** for a user, the **Give Control** option isn't available.

Let's look at the following example.

| User | Meeting policy | Allow participant to give or request control |
| --- | --- | --- |
| Daniela | Global | On |
| Adele | Location1MeetingPolicy | Off |

Daniela can give control of the shared desktop or window to other participants in a meeting or event Adele organizes. However, Adele can't give control to other participants.

#### PowerShell

Use the **`-AllowExternalParticipantGiveRequestControl`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet to control whether external participants can give, be given, and request control during meetings and events.

To allow users to give, be given, and request control during meetings and events, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowParticipantGiveRequestControl $True
```

To prevent users from giving, being given, and requesting control during meetings and events, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowParticipantGiveRequestControl $False
```

### External participants can give or request control

This setting is a per-user policy. This policy controls whether external participants can give, be given, or request control of the sharer's screen in meetings and events that organizers with this policy create.

You can toggle this setting **On** or **Off** in the Teams admin center or manage this policy in PowerShell.

**External participants can give or request control** doesn't control what external participants can do in meetings and events they attend. The organizer's **Who can present** and **Who can bypass the lobby** settings in their **Meeting options** determines what external participants can do in their meeting or event.

External participants in Teams meetings can be categorized as follows:

- Anonymous participant
- Guests
- External access users

For external access users to give control to other external participants, both you and the other org's admin must have this policy set to **On**.

#### PowerShell

Use the **`-AllowExternalParticipantGiveRequestControl`** parameter within the PowerShell [**CsTeamsMeetingPolicy**](/en-us/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet to control whether external participants can give, be given, and request control during meetings and events.

For external participants to give, be given, and request control in meetings and events organizers with this policy create, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowExternalParticipantGiveRequestControl $True
```

To prevent external participants from being given, giving, and requesting control in meetings and events organizers with this policy create, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowExternalParticipantGiveRequestControl $False
```