---
layout: Conceptual
title: Control which apps appear on Phone Devices - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/appselection
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Article describing how to remove select apps from Phone Devices via Teams Admin Center
author: pbadkur1
ms.author: prashibadkur
manager: kponnus
ms.service: msteams
ms.subservice: itpro-devices
ms.topic: blog
ms.date: 2026-05-11T00:00:00.0000000Z
locale: en-us
document_id: b951c673-cb67-8d3a-4050-c3e9d6a9fcb4
document_version_independent_id: b951c673-cb67-8d3a-4050-c3e9d6a9fcb4
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/appselection.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/appselection
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/appselection.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
platformId: 4ad0ac01-be30-01d5-58ba-4ddccecbd698
---

# Control which apps appear on Phone Devices - Microsoft Teams | Microsoft Learn

IT admins can now disable specific apps on Teams-certified desk phones so they don't appear in the user experience.

## Overview

Teams desk phones ship with a set of supported apps enabled by default based on the license and sign-in mode — such as People, Line Keys, Voicemail, Walkie Talkie, Shared Line, Calendar and Queues App. App selection lets you turn off individual apps from that default set, so they don't appear on the phone's home screen. You cannot use this feature to add or enable apps beyond what is already available for a given device type or sign-in mode. This feature gives you tighter control over shared or common area deployments and removes the need for custom backend workarounds. To review the default set of apps supported based on the license and sign in mode, read here [How to deploy Teams Phone devices](https://techcommunity.microsoft.com/blog/microsoftteamsblog/how-to-deploy-teams-phone-devices/3994979).

## Before you begin

- **Requires:** Teams Admin Center access; Teams-certified desk phones enrolled in your organization
- **Supported devices:** Teams-certified desk touch phones (personal and common area)

Note

You can only disable apps that are already available on the device. Device type, sign-in mode, and license determine app availability — app selection cannot override those constraints.

## Configure app selection in Teams Admin Center

1. Go to **Teams Admin Center** &gt; **Teams devices** &gt; **Phones**.
2. Select **Configuration profiles**.
3. Create a new profile or open an existing one to edit.
4. Under **App settings**, you see all the apps that are currently supported across different licenses. All available apps are on by default.
5. Toggle off any apps you want to remove from the phone UI.
6. Save the profile.
7. Assign the profile to the phones or phone groups you want to target.

The phones update automatically after the profile is applied.

Note

If a disabled app was pinned on a phone's home screen, the phone falls back to the default home screen layout. Core calling behavior is not affected — only app visibility changes.

## What to do if a phone still shows a disabled app

- Confirm the configuration profile is correctly assigned to that device in Teams Admin Center.
- Allow a few minutes for the profile to propagate after saving.
- If the app persists, restart the Teams app on the phone or reboot the device.

## Frequently asked questions

1. **Can I use this feature to add an app that isn't already on the phone?**

    No. App selection only controls apps that are already part of the phone's supported experience. You cannot use it to enable apps that aren't available for a given device type, sign-in mode, or license.
2. **What happens if I disable an app in a configuration profile and assign it to a phone that doesn't have that app?**

    Nothing. If the app isn't present on the phone to begin with, the setting has no effect. The profile applies silently and the phone's experience remains unchanged.
3. **Will disabling an app in the profile affect all phones it's assigned to the same way?**

    Only phones that actually have the app are affected. Phones where that app was never available are unaffected, even if they share the same configuration profile.