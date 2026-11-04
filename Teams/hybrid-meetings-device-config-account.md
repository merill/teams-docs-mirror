---
layout: Conceptual
title: Step 2 - Create a resource account - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/hybrid-meetings-device-config-account
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
ms.localizationpriority: high
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
description: Create a resource account for use with Teams Rooms devices.
locale: en-us
document_id: 8ccc5e95-049b-4132-3353-85804949edeb
document_version_independent_id: 8ccc5e95-049b-4132-3353-85804949edeb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/hybrid-meetings-device-config-account.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: hybrid-meetings-device-config-account
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/hybrid-meetings-device-config-account.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 003b8b31-e535-0fa4-f10a-131763f9afb4
---

# Step 2 - Create a resource account - Microsoft Teams | Microsoft Learn

![IT Pro audience](media/hybrid-audience-itpro-small.png)

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