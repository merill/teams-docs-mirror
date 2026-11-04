---
layout: Conceptual
title: Change phone numbers on Audio Conferencing bridge - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/change-the-phone-numbers-on-your-audio-conferencing-bridge
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: oscarr
ms.date: 2025-01-28T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- m365initiative-meetings
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Learn the steps required to assign a new service phone number to your conference bridge to expand coverage for your users.
locale: en-us
document_id: 485c3bcb-41f9-6873-bd04-2f4110d07655
document_version_independent_id: df1cd65a-1636-73b7-3245-674dfb6b86cf
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/change-the-phone-numbers-on-your-audio-conferencing-bridge.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: change-the-phone-numbers-on-your-audio-conferencing-bridge
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/change-the-phone-numbers-on-your-audio-conferencing-bridge.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: e77fb23d-15a1-98b5-440f-51871caea6eb
---

# Change phone numbers on Audio Conferencing bridge - Microsoft Teams | Microsoft Learn

When you purchase **Audio Conferencing** licenses, Microsoft hosts your audio conferencing bridge for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.

In addition to the phone numbers already assigned to your conferencing bridge, you can [get more service numbers](getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations. You can assign these numbers to the conferencing bridge so you can expand coverage for your users.

Note

To assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number. You can see the type of number it is by navigating to **Voice** &gt; **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column. Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.

## Steps when you're assigning a new service phone number to your conference bridge

Note

Except where it's called out otherwise, you must perform all these steps in the Microsoft Teams admin center.

### Step 1 - Assign the new phone number to your audio conferencing bridge

1. In the navigation pane, go to **Voice** &gt; **Phone numbers**.
2. Select the phone number from the list, and select **Edit**.
3. On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** &gt; **Apply**.

### Step 2 - Change the default phone number of your conference bridge (optional)

The default phone number of your conference bridge determines the caller ID used when a participant or the organizer places an outbound call from within a meeting.

You can only set a service toll number as the default number for your conferencing bridge. **You can't set service toll-free numbers as the default number of your conferencing bridge**. If you're assigning a service toll number and you'd like to set it as the new default number for your audio conferencing bridge, follow these steps:

1. In the navigation pane, go to **Meetings** &gt; **Conference bridges**.
2. Highlight the service toll number that you want to configure as the default.
3. Select **Set as default**.

### Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)

For instructions, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams).

Note

You can also set phone numbers by adding them to the *TeamsAudioconferencingpolicy* and assigning the policy to your users. Toll and toll-free phone numbers added to the policy take precedence over the phone numbers set individually for users via the audio conferencing settings pane. If no phone numbers are added to the *Teamsaudioconferencingpolicy*, then the phone number set individually for users via the audio conferencing settings pane is displayed in Microsoft Teams meeting requests. [Audio Conferencing policy settings for toll and toll-free numbers](audio-conferencing-toll-free-numbers-policy) has more information.

### Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)

For the next two steps, you need to start Windows PowerShell.

If you changed the default phone numbers included in meeting invites for some or all users, you can use the Meeting Migration Service to update already sent invites with the new numbers. For more information, see [Setting up the Meeting Migration Service (MMS)](/en-us/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

- Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2. To run MMS, use the following command:

    ```PowerShell
    Start-CsExMeetingMigration user@contoso.com
    ```
- You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in *Pending* or *In-Progress* state.

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
    ```

## Steps when you unassign a service phone number for a conferencing bridge

When you unassign a phone number from a conferencing bridge, users can't join any meetings using that phone number anymore. Because the phone number is changing, you should update all users with a changing phone number as their default. Update their meeting invites before the phone number is unassigned from the conferencing bridge.

If the phone number is removed without updating the users and their meetings, their existing meeting invites could have a phone number that doesn't work for joining their meetings.

For the first three steps, you need to start Windows PowerShell. For more information on how to start Windows PowerShell, see [Getting started with PowerShell](/en-us/powershell/scripting/learn/ps101/01-getting-started).

### Step 1 - Update users who have the phone number to be unassigned as one of their default numbers

To replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings, follow these steps:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

Important

You can also change the default toll or toll-free number of users in the Microsoft Teams admin center. However, this doesn't automatically reschedule their meetings.

For more information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams).

Note

Depending on the size of your organization, this could take some time to complete.

### Step 2 - View meeting migration status using Windows PowerShell

All meetings are rescheduled once there are no operations in *Pending* or *In-Progress* state. To view the meeting migration status, run the following command:

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/en-us/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

### Step 3 - Unassign the old phone number from the audio conferencing bridge

To use the Unregister-CsOnlineDialInConferencingServiceNumber cmdlet to unregister a Toll or Toll free number from a conference bridge, run the following command:

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

To find the Conference Bridge ID, run Get-CsOnlineDialInConferencingBridge.

Important

After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.

### Save time and automate

To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](/en-us/powershell/module/teams/Set-CsOnlineDialInConferencingUser) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.

- Use the [Set-CsOnlineDialInConferencingUser](/en-us/powershell/module/teams/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.

    - To change the default toll-free number for a user, run:

        ```PowerShell
        Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
        ```
- Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.

    Note

    To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.

    - To set the default toll-free number for all users without one to 8005551234, run:

        ```PowerShell
        Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
        ```
    - To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:

        ```PowerShell
        Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
        ```
    - To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:

        ```PowerShell
        Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
        ```

        Note

        The location you use needs to match the user's contact information that's set in the Microsoft 365 admin center.

## Troubleshooting

### The Unassign button isn't available

You want to unassign a number, but the button isn't available. When you hover the number, you're redirected to contact Support with the following message: "Default or shared numbers can't be unassigned from the bridge. To unassign dedicated toll numbers contact support."

To get more information about the bridges, run the following PowerShell:

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.

**Example**, to unassign, the DefaultServiceNumber "8005551234"

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234
```