---
layout: Conceptual
title: How to create and configure resource accounts for Teams Rooms and panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/create-resource-account
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: srpall
ms.date: 2026-02-20T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Read this article for information on how to create resource accounts for Teams rooms and shared devices. These devices include Microsoft Teams Rooms, Teams panels, and Surface Hub.
locale: en-us
document_id: a560986f-99b6-9e5e-a3a3-2a10309d4247
document_version_independent_id: a560986f-99b6-9e5e-a3a3-2a10309d4247
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/create-resource-account.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/create-resource-account
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/create-resource-account.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c9f54a1f-c7f2-ce44-a468-ef3bb9a350a2
---

# How to create and configure resource accounts for Teams Rooms and panels - Microsoft Teams | Microsoft Learn

This article provides steps to create resource accounts for shared spaces and devices, and it includes steps to configure resource accounts for Microsoft Teams Rooms on Windows, Teams Rooms on Android, & Teams panels.

Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room or projector. These resource accounts can automatically respond to meeting invites using rules you define when they're created. For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room which automatically accepts or declines meeting invites depending on its calendar availability.

Every resource account is unique to a single Microsoft Teams Rooms installation or Teams device implementation.

Important

Microsoft 365 resource accounts used for Teams devices aren't the same as Teams resource accounts. Teams resource accounts can be used with call queues and auto attendants to accept phone calls from external phone numbers. Microsoft 365 resource accounts are tied to an Exchange Online mailbox and enable booking of shared resources, such as rooms, projectors, and so on.

If you want to know more about Teams resource accounts, see [Manage resources accounts in Microsoft Teams](../manage-resource-accounts).

Note

If using Microsoft Teams panels, the same Teams Rooms resource account signs in to the Teams Rooms device and any associated Teams panels.

## Before you begin

### Requirements

You may need one or more roles to create, license, and configure resource accounts.

| Environment | Required Roles |
| --- | --- |
| Microsoft Entra ID | Global admin or User admin |
| On-premises Active Directory | Active Directory Enterprise Admins, Domain Admins, or have delegated rights to create users |
| Exchange Online | Global Administrator or Exchange Administrator |
| Exchange Server | Exchange Organization Management or Recipient Management |
| Licensing | Global admin or Billing admin |
| Teams | Global admin or Teams admin |

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Get the right license

In the next step, you'll create a resource account for each your Teams Rooms device. Before you do that, you need to purchase licenses, each resource account you want to associate with a Teams Rooms device needs a Teams Rooms license.

Follow these steps to purchase a Teams Rooms Basic or Teams Rooms Pro license that you can assign to a resource account in a later step. For a comparison between the Teams Rooms Basic and Teams Rooms Pro licenses, see [Teams Meeting Rooms Licenses](rooms-licensing).

1. Go to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) and log in with an account that has license admin permissions.
2. In the admin center, go to the **Billing** &gt; [Purchase services](https://go.microsoft.com/fwlink/p/?linkid=868433) page.
3. On the **Purchase services** page, type in **Teams Rooms** in the search box and press enter.
4. Select **Details** under either **Teams Rooms Basic** or **Teams Rooms Pro**.
5. Select the number of licenses you want to purchase in **Select license quantity**.
6. Select how often you want to be billed under **Select billing frequency** and then click **Buy**.

## Create resource account & assign the license

Note

Teams has two distinct resource account types, those for Teams devices and those to support call queues and auto attendants.

Resource accounts used for shared space devices with a Teams Room or Teams phone are created similarly to standard user accounts but with a different licensing and [security posture](/en-us/microsoftteams/rooms/conditional-access-and-compliance-for-devices) compared to a user identity.

For information on resource accounts for Phone System call queues and auto attendants: [Click Here](/en-us/microsoftteams/manage-resource-accounts)

Tip

We recommend that you create all resource accounts as cloud only using Microsoft Entra ID and Exchange Online. If using Exchange on-premise, you must be in hybrid for the Teams Rooms device to read the calendar.

Each Microsoft Teams Rooms device needs its own resource account. The Teams Rooms device uses the resource account to log into Microsoft 365 and it's what users in your organization invite in Exchange to book the room.

Tip

When naming your resource accounts, we recommend using a standard naming convention to the beginning of the e-mail address. This will help with creating dynamic groups to ease management. For example, you could use "mtr-" for all resource accounts that will be associated with Microsoft Teams Rooms.

Create a resource account using a method from one of the following tabs:

# [In Microsoft 365 admin center](#tab/m365-admin-center)
1. Sign in to the Microsoft 365 admin center with administrative credentials for your Microsoft 365 tenant.
2. Go to **Resources** in the left panel, and then select **Rooms & equipment**. (If these options aren't available in the panel, you may need to select **Show all** first.)
3. Select **Add resource** to create a new resource account. Enter a name, email address, and capacity for the account, then select **Save**.
4. By default, resource accounts are configured with the following settings:

    - Allow repeat meetings
    - Automatically decline meetings outside of the following limits
        - Booking window (days): 180
        - Maximum duration (hours): 24
    - Auto accept meeting requests

    If you want to change them, select **Edit booking options** before you select **Close**. If you want to change them later, go to **Resources** &gt; **Rooms & equipment**, select the resource account. Then under **Booking options**, select **Edit**.
5. Go to **Users** &gt; **Active users**, and select the room you created to open the properties panel.
6. Next, assign a password to the resource account. In the panel, select **Reset password**.
7. Requiring a password change on first login for a Teams Rooms device causes sign in problems. Uncheck **Require this user to change their password when they first sign in**, and select **Reset password**.
8. Assign the Teams Rooms license, purchased in the earlier step. In the panel, select **Licenses and apps**.
9. Check the box next to **Microsoft Teams Rooms Pro** or **Microsoft Teams Rooms Basic**, and select **Save changes**

# [With Exchange Online PowerShell](#tab/exchange-online)
1. Connect to [Exchange Online PowerShell](/en-us/powershell/exchange/connect-to-exchange-online-powershell).

    ```PowerShell
    Connect-ExchangeOnline
    ```
2. Room mailboxes don't have accounts associated by default. Add an account when you create a room mailbox so it can authenticate with Microsoft Teams.

    If you're creating a new resource mailbox:

    ```PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    This example creates a new room mailbox with the following settings:

    - Account: ConferenceRoom01@contoso.com
    - Name: ConferenceRoom01
    - Alias: ConferenceRoom01
    - Account password:

    ```PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```
3. To assign the Teams Rooms license, purchased in the earlier step, sign in to the Microsoft 365 admin center with administrative credentials for your Microsoft 365 tenant.
4. Go to **Users** &gt; **Active users**, and select the room you created to open the properties panel. In the panel, select **Licenses and apps**.
5. Check the box next to **Microsoft Teams Rooms Pro** or **Microsoft Teams Rooms Basic**, and select **Save changes**

# [With Exchange Server](#tab/exchange-server)
1. Connect to Exchange Management Shell. [Open the Exchange Management Shell](/en-us/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/en-us/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).
2. To create a new room mailbox:

    ```PowerShell
    New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    This example creates a new room mailbox with the following settings:

    - Account: ConferenceRoom01@contoso.com
    - Name: ConferenceRoom01
    - Alias: ConferenceRoom01
    - Account password:

    ```PowerShell
    New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```
3. To assign the Teams Rooms license, purchased in the earlier step, sign in to the Microsoft 365 admin center with administrative credentials for your Microsoft 365 tenant.
4. Go to **Users** &gt; **Active users**, and select the room you created to open the properties panel. In the panel, select **Licenses and apps**.
5. Check the box next to **Microsoft Teams Rooms Pro** or **Microsoft Teams Rooms Basic**, and select **Save changes**

Important

You must be in operating in an Exchange hybrid configuration for a Teams Rooms device to access the Exchange calendar. In hybrid, you'll also need to add an email address for your on-premises domain account. For more information, see [sync on-premises and Office 365 user accounts directories](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

# [Modify an existing Exchange room mailbox](#tab/existing-account)
To modify an existing room mailbox to become a resource account, use the following syntax:

```PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

This example enables the account for the existing room mailbox that has the alias value ConferenceRoom02.

```PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

For detailed syntax and parameter information, see [New-Mailbox](/en-us/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/en-us/powershell/module/exchange/mailboxes/set-mailbox).

1. To assign the Teams Rooms license, purchased in the earlier step, sign in to the Microsoft 365 admin center with administrative credentials for your Microsoft 365 tenant.
2. Go to **Users** &gt; **Active users**, and select the room you created to open the properties panel. In the panel, select **Licenses and apps**.
3. Check the box next to **Microsoft Teams Rooms Pro** or **Microsoft Teams Rooms Basic**, and select **Save changes**

Important

You must be in operating in an Exchange hybrid configuration for a Teams Rooms device to access the Exchange calendar. In hybrid, you'll also need to add an email address for your on-premises domain account. For more information, see [Sync on-premises and Office 365 user accounts directories](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

---

Important

- The default time zone for resource accounts is Pacific Standard Time. You must change the time zone setting of the resource account to match the time zone where the physical resource is located. Go to [Time zone settings are incorrect or missing for multiple mailboxes in Microsoft 365](/en-us/exchange/troubleshoot/user-and-shared-mailboxes/incorrect-missing-time-zone-settings) for more information on changing the time zone of resource accounts.
- If you're creating resource accounts for Teams Rooms, the resource account's UPN must match the SMTP address of the resource account.

## Configure Exchange mailbox properties

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

## Turn off password expiration

Based on organization policies, resource account passwords may be set to expire automatically after a period of time. If the resource account password expires, the Teams Rooms device with sign out and can't sign in again without manual intervention.

Note

Setting **Password never expires** is a requirement for shared Microsoft Teams devices. If your organization prohibits passwords that don't expire, you'll need to create an exception for Teams device resource accounts.

To turn off password expiration, follow the steps in one of the following tabs:

# [Microsoft Graph PowerShell](#tab/graph-powershell-password)
1. Connect to [Microsoft Graph PowerShell](/en-us/microsoft-365/enterprise/connect-to-microsoft-365-powershell):

    ```PowerShell
       Connect-MgGraph -Scopes "User.ReadWrite.All"
    ```
2. Set the password to never expire, this example sets the password for the account ConferenceRoom01@contoso.com to never expire.

    ```PowerShell
    Update-MgUser -UserId ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
    ```

# [Active Directory (On-premises)](#tab/active-directory1-password)
1. Connect to [Active Directory PowerShell](/en-us/powershell/module/activedirectory):

    ```PowerShell
       Import-Module ActiveDirectory
    ```
2. Set the password to never expire, this example sets the password for the account ConferenceRoom01@contoso.com to never expire.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---