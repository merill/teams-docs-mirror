---
layout: Conceptual
title: Microsoft Teams apps/Line of Business (LOB) app support on Teams panels - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/app-support-on-teams-panels
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: eviegrimshaw
ms.date: 2025-01-17T00:00:00.0000000Z
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Describes the support for Teams apps/LOB apps.
locale: en-us
document_id: 558d6f47-4ed9-9667-14cb-9aa038f0ebb5
document_version_independent_id: 626710b8-543b-2bf9-47a5-c1d368fab5c0
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/app-support-on-Teams-panels.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: app-support-on-teams-panels
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/app-support-on-Teams-panels.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b2835494-4ea3-53d2-030f-1fa7fbea963c
---

# Microsoft Teams apps/Line of Business (LOB) app support on Teams panels - Microsoft Teams | Microsoft Learn

Teams panels support [Teams apps/Line of Business (LOB) apps](/en-us/microsoftteams/platform/overview). This enables enterprises to add more experiences on the panels to meet your organization's needs. This release supports static web content.

Important

Currently LoB apps aren't displayable on the panel device and only "nearby rooms" is enabled as an app. Our team is investigating plans to bring back support of LOB apps on Teams panels. We appreciate your patience as we resolve this.

## Teams app experience on Teams panels

![Screenshot of the Teams admin center showing which section will allow users to navigate to apps.](media/tac1update.png)

*The Teams panels home screen includes app navigation options, outlined in the screenshot in red. These are example icons and might not be available for use.*

![Screenshot of the app canvas where apps can be added.](media/appscreen.png)

*When an end-user taps on one of the app icons, they see the Teams app screen displayed in the previous screenshot. The gray rectangle in the screenshot is where apps are displayed on the Teams panel. The app bar is fixed and part of the Teams panels app.*

## Set up and manage Teams panels apps in Teams admin center

Microsoft Teams apps bring key information, common tools, and trusted processes to where people gather, learn, and work. Teams apps work [through integrated capabilities](/en-us/microsoftteams/platform/concepts/capabilities-overview). Now, as an IT administrator, you have the choice of which apps to include in your organization's Teams panels device and customize permissions via the [Teams admin center](https://admin.teams.microsoft.com/).

You can now use the Teams apps on Teams panels and customize the user experience based on your organization's needs. You can decide which web app your users can access and use and prioritize the app views. Some options, like the bot and messaging capabilities, aren't supported at this time. Learn more about [the Teams apps](/en-us/microsoftteams/platform/overview) and [how to manage your devices in Microsoft Teams](/en-us/microsoftteams/devices/device-management).

## Manage apps on Teams panels in Teams admin center

**Note**: You must be a Teams service admin to access the [Teams admin center](https://admin.teams.microsoft.com/).

End users can view but not install apps on Teams panels. As an admin, you can view and manage all Teams apps for your organization via the Teams admin center. Learn more about how you can [manage your apps in the Microsoft Teams admin center](/en-us/microsoftteams/manage-apps) via the **Manage apps** page. The **Manage apps** page within the Teams admin center is also where you can upload [custom apps](/en-us/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store).

After setting up apps, you can use [app permission policies](/en-us/microsoftteams/teams-app-permission-policies) and [app setup policies](/en-us/microsoftteams/teams-app-setup-policies) to configure the app experience for specific room accounts in your organization.

## Pin apps on Teams panels with app setup policies

Since Teams offers the capability to display a wide range of apps, admins can decide on which apps are most essential for the organization and pin only these for the Teams panels **Home** screen for quick access. If there are more than five pinned apps or any unpinned apps, they appear under the **More** screen. Microsoft recommends creating a custom policy in app setup policy specifically for Teams panels.

![User interface screenshot of the app setup policies page.](media/appsetup1.png)

To manage pinned apps displayed on the Teams panels, sign in to the Teams admin center for your organization and navigate to **Teams apps** &gt; **Setup policies** &gt; **Select or Create a new policy** &gt; **Pinned apps**.

![Screenshot of pinned apps section within the user interface.](media/appsetup2.png)

*Apps included in this image are only examples and might not be available for use.*

Microsoft recommends you turn off **Upload custom apps** and **User pinning** for the best Teams app experience on Teams panels.

For more about pinning apps, see [Manage app setup policies](/en-us/microsoftteams/teams-app-setup-policies).

## Manage apps display order in Teams panels

![Screenshot of apps section within the user interface.](media/appsetup3.png)

*Apps included in this image are only examples and may not be available for use.*

To manage the order in which apps are displayed on the Teams panels, sign in to the Teams admin center for your organization and navigate to **Teams apps** &gt; **Setup policies** &gt; **Select the Policy** &gt; **Pinned apps:** **Move-up/down**.

## Assigning setup policies to a room resource account

After creating the setup policy, the admin will need to assign this policy to the room resource account that will be signed into the Teams panels. For more information, refer to [Assign policies to users and groups](/en-us/microsoftteams/assign-policies-users-and-groups).

## FAQ

### How long does it take for Teams panels to get the new or updated app setup policies?

After editing or assigning new policies in the Teams admin center, it can take up to 24 hours for changes to take effect. Admins can try to sign-out/sign-in from the panel, tap the **Settings** icon, and go back to the **Home** screen to try to refresh the policies.

### What is the ordering of the apps on the "More" screen?

On the **More** apps page, the pinned apps appear first. Then, any other installed apps appear in alphabetical order.

### Why are bot apps not showing up on Teams panels?

Only static tabs web content is supported at this time.

### Why are native Teams apps, such as Calendar and Tasks, not appearing on Teams panels?

Native Teams apps, such as Calendar and Tasks, aren't shown on Teams panels.

### In the Teams admin center, under the setup policies section, what is the difference between installed apps and pinned apps?

For Teams panels, Microsoft recommends using pinned apps, so the admin is able to select the desired app and rearrange its ordering.

**Note:** Some apps don't support app pinning. Please contact the app developer to enable app pinning functionality.

### Why are other apps appearing in the "More" screen even though they are not part of the installed or pinned apps in the Teams app setup policy section?

If apps were previously installed via other app policies or manually in the Teams desktop/web clients for the room resource account used on Teams panels, the admin may need to sign in to the room resource account in Teams and manually uninstall the apps by right-clicking the app, then selecting **Uninstall**.

### Why can't I find an app in the "Add pinned apps" pane?

Not all apps can be pinned to Teams through an app setup policy. Some apps may not support this functionality. To find apps that can be pinned, search for the app in the **Add pinned apps** pane. For more information, please refer to [the FAQ in Working with app setup policies](/en-us/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane).

### Why am I seeing an "User pinning" pop-up in the setup policies panel after I turn off "User pinning?"

![Screenshot of the setup policy section within the user interface with a pop-up confirming user pinning is active.](media/appsetup4.png)

*Apps included in this image are only examples and may not be available for use.*

This behavior is expected for a device in a shared space and helps prevent unintentional app pinning.