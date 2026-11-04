---
layout: Conceptual
title: Sign out of Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/sign-out-of-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: Admin
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
ms.reviewer: 
ms.date: 2025-06-30T00:00:00.0000000Z
description: Learn how to sign out of Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- trust-pod
f1.keywords:
- NOCSH
locale: en-us
document_id: a4d56b6e-a220-710c-f051-6e78bf0883fe
document_version_independent_id: d1aa0964-725e-0b99-00c0-7ddcfad46920
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/sign-out-of-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sign-out-of-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/sign-out-of-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 007cde7e-b110-b7d6-4885-973b381c42c7
---

# Sign out of Microsoft Teams - Microsoft Teams | Microsoft Learn

It's a good idea to remain signed in to Microsoft Teams to ensure you don't miss incoming calls, chat messages, meeting starts, and other notifications. The Teams desktop app supports multiple accounts side-by-side, removing the need to sign out and sign back in. [Learn more about Teams](/en-us/microsoftteams/teams-client-desktop-admin).

However, there are times where users might need to sign out of Teams, for example when they’re using a device that's shared with another person. Users should always initate signing out from inside the Teams app, and Microsoft recommends against using custom scripts that attempt to programmatically sign out users. Things are a bit different for Shared Device Mode: Global sign in and sign out for Frontline, which is described later in this article.

## Sign out of Teams on the web

To sign out of Teams in a browser, users should select their profile picture at the top of the app, then select **Sign out**. They're signed out from all Microsoft 365 applications in a given browser profile. The next time they sign in to Teams or other Microsoft 365 applications, their username is shown on the sign-in page. In most cases, they need to reenter their credentials, and can remove their account from the list by selecting **Forget**.

If this computer is a shared computer and you don’t want usernames to be visible to others, we recommend using browsers in InPrivate/Incognito mode.

## Sign out of Teams on desktop (Windows or macOS)

To sign out of the Teams desktop app, users should select their profile picture at the top of the app, and then select **Sign out**. If multiple accounts were added, they need to sign out of each account individually.

### Account sharing between apps

Modern operating systems allow sharing of accounts between different apps on a device. This functionality is called single sign-on (SSO), and is designed to help users seamlessly navigate between different apps with the same account.

SSO has an important impact on sign out: when users sign out of the Teams desktop app, the data associated with their account is removed from the Teams app but the account itself isn’t removed from the device. Users need to reenter their credentials if they sign back in to Teams with the same account, but other apps on the device may still have access to their account. This functionality means that signing out of Teams doesn't prevent other users from accessing the data associated with your account.

### "This app only" mode on Windows

On Windows, users may see an option to sign in to **this app only**. When this option is selected, and users later sign out of Teams, their account is removed from the PC. However, their username may continue to be shown on sign-in pages.

![Screenshot: User interface of sign in to all apps with a link to only sign into this app only.](media/sign-in-to-all-apps.png)

Note

When users select **this app only** when signing in to Teams, other apps on the PCs won’t be able to use this account. Practically, this means that links to files or websites selected in Teams may not properly open in Microsoft 365 apps or in the browser, and users may be prompted to sign in again. In other words, **this app only** prevents SSO from working correctly between Windows, Teams and other applications, and as such isn't recommended when signing in to Teams.

### Best practices for multiple users on a shared desktop device

If different users share a desktop computer, we recommend setting it up with separate accounts to sign in to Windows or macOS and training users to lock the computer when they walk away. This configuration allows each user to enjoy SSO between apps in a given operating system session and keep their account and data separated from other users'.

In cases where a single desktop computer is shared between multiple Frontline Workers, we recommend using cloud computers, as described here: [Frontline worker for Windows devices in Microsoft Intune](/en-us/mem/solutions/frontline-worker/frontline-worker-overview-windows).

## Sign out of Teams on mobile devices

On mobile, users can sign out of Teams by selecting their profile icon, selecting **Settings**, and then **Sign out**. Once a user signs out, they need to reenter their credentials the next time they launch Teams.

## Shared Device Mode: Global sign-in and sign-out for Frontline

Microsoft’s Shared Device Mode (SDM) allows Frontline Workers to have mobile devices optimized for fast check-in/check-out. When a device is enabled for SDM, sign out work differently on Teams.

With SDM, users can pick any device from a shared device pool and sign in as usual to "make it theirs" during their shift. At the end of the shift, they should select **Sign out** as usual. With SDM a global sign out is initiated on the device, which should remove the user's account and data from the device, so it can return to the device pool.

**Android**: To learn how to set up android devices in Shared Device Mode, see [How to use a shared device mode in Android](/en-us/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

**iOS**: To set up Shared Device Mode on iOS, see [How to use shared device mode on iOS](/en-us/azure/active-directory/develop/msal-ios-shared-devices).

![Screenshot of Sign-out-section.](media/signout.png)