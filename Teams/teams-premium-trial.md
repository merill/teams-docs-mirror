---
layout: Conceptual
title: Roll out a Teams Premium trial - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-premium-trial
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: install-set-up-deploy
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: margidesai
audience: admin
ms.date: 2026-04-01T00:00:00.0000000Z
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365initiative-meetings
- highpri
- Tier1
description: Learn how to set up a Teams Premium trial to understand and test premium capabilities in your organization.
locale: en-us
document_id: 89daab79-5c8a-4693-2218-50027e1249b2
document_version_independent_id: 89daab79-5c8a-4693-2218-50027e1249b2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-premium-trial.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-premium-trial
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-premium-trial.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 0f66fb7d-5679-9b9d-7da8-8f32eaf8ff21
---

# Roll out a Teams Premium trial - Microsoft Teams | Microsoft Learn

Important

**Licensing update for Teams Premium and Teams Enterprise**

As of April 1, 2026, some features that were previously only available with Teams Premium are now included with Teams Enterprise. Teams Premium continues to offer advanced meeting protection, advanced communication (like the Queues app), branding and personalization, and intelligence capabilities. [Learn more](https://techcommunity.microsoft.com/blog/microsoftteamsblog/licensing-updates-extend-access-to-advanced-capabilities-in-microsoft-teams-and-/4488312).

Customers who purchased Teams Premium licenses before April 1, 2026 will continue to have access to all the previously included Teams Premium features and product experiences included with these licenses until they expire.

To manage Teams Premium features, your tenant must have at least one active [Teams Premium license](/en-us/microsoftteams/teams-add-on-licensing/licensing-enhance-teams).

As an admin, you can try [Teams Premium](enhanced-teams-experience) for free by adding the Teams Premium trial to your organization's Microsoft 365 subscription. The Teams Premium trial provides 25 licenses for 30 days.

Before you start the trial, it's important to plan who will be provided with licenses. You should decide what use cases you want to validate during the trial, and how to collect feedback while the trial is underway.

The following are the basic steps involved in a trial:

1. **Pre-trial planning** - Including defining test cases, choosing users, and deciding which feature settings and policies you want to use.
2. **Add the trial** - Including assigning licenses to users in your organization.
3. **Administrative setup** - Including creating meeting templates, uploading logos and backgrounds, and assigning policies to users. If your organization uses sensitivity labels, setup also includes creating meeting sensitivity labels in the Microsoft Purview portal.
4. **Start the trial** - Including notifying the trial participants to begin testing the use cases you defined and providing feedback to stakeholders.

To better assist with planning for your Teams Premium trial, you can download the [Teams Premium Trial Guide](https://adoption.microsoft.com/files/microsoft-teams/teams-premium-trial-guide.pdf) from Microsoft Adoption and watch [Running a Successful Teams Premium Trial](https://www.youtube.com/watch?v=b7z3re0GPd4) on YouTube.

This article covers pre-trial planning and how to add the trial to your tenant and assign licenses. Specific steps for administrators to set up features for the trial are covered in each feature's article, which we link to in the following sections. For a full list of Teams Premium features and links to their documentation, see [Microsoft Teams Premium - Overview for admins](enhanced-teams-experience).

## Determine trial participants and stakeholders

Teams Premium provides various enhancements to Teams meetings. We recommend that you find participants from around your organization who can make use of the Teams Premium features in the normal course of their work, including stakeholders and specialists who can validate the features for your business, branding, and compliance needs. These participants might include:

- People who need to present sensitive information in meetings
- Branding and corporate communications specialists
- Compliance and governance specialists
- People who present to large audiences

Not all trial participants need a Teams Premium license. Some people, such as business stakeholders who help define use cases, might not need to test the features themselves.

The following table lists potential trial participants and their roles. For details on roles, see [About admin roles in the Microsoft 365 admin center](/en-us/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles).

| Who | Their role in the trial | Trial license needed? |
| --- | --- | --- |
| License or User Administrator | Assign Teams Premium trial licenses to trial participants. | No |
| Teams Administrator | Configure Teams Premium settings and policies | If using the Advanced Virtual Appointments activity report |
| Compliance Administrator | Set up and publish sensitivity labels if needed | No |
| Meeting organizers | Schedule meetings where participants can test Teams Premium features | Yes |
| Meeting participants | People in the organization who can attend meetings that use Teams Premium features and give feedback on them | No |
| Compliance specialists | Compliance or governance specialists who can validate use cases for compliant meetings | Yes |

You can use security groups to easily specify who can use specific sensitivity labels.

### Collect feedback from trial participants

We recommend creating a team in Microsoft Teams to gather all the trial participants and stakeholders in one place where they can communicate and share ideas and feedback. You can use channels to organize participants around the different use cases that you want to test.

Beyond Teams chat, there are several options for gathering feedback from trial participants, including [polling attendees during a Teams meeting](https://support.microsoft.com/office/9923b7d4-ea97-4aa2-b8b8-b45fefe7d454) and [adding a poll to your Teams channel or chat](https://support.microsoft.com/office/a3f9112c-01e1-4ee4-bd88-25e4e243b80b).

## Define use cases

The following sections describe the areas where Teams Premium offers enhanced meeting capabilities for your organization. As you prepare for the trial, review each area and determine the use cases that you want to test.

### Compliant meetings

To help meet your compliance requirements for meetings, Teams Premium provides the following options for meeting organizers:

- Watermarks for attendee video and content shared on screen
- End-to-end encryption
- Options for who can record the meeting

These options are available to meeting organizers with a Teams Premium license.

Teams Premium also includes custom meeting templates and extra options for sensitivity labels that you can use to control many of the [meeting settings that are available to meeting organizers](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e).

If your organization uses sensitivity labels, you can create a combination of sensitivity labels and meeting templates to define meeting experiences for meetings with different sensitivity levels. For ideas on how to use labels and meeting templates for different types of meetings, read [Configure Teams meetings with three tiers of protection](/en-us/microsoftteams/configure-meetings-three-tiers-protection).

Sensitivity labels are defined in Microsoft Purview and you can use them in meetings directly or specify them as part of a meeting template.

If your organization doesn't use sensitivity labels, you can control many of the same features by using custom meeting templates alone.

For the trial, define the different types of meeting experiences that you want to validate. Next, determine how you want to use sensitivity labels (if applicable) and meeting templates to make these meeting experiences available to trial participants.

If you use sensitivity labels, we suggest creating temporary labels for the trial and publishing them to your trial participants. This way you don't need to update production labels that are available widely within the organization.

For your trial group, you might want to include people who need to present sensitive information in meetings and compliance specialists who can validate the features and settings used with respect to your business requirements.

For more information about using Teams Premium for meeting compliance, see the following references:

- [Manage end-to-end encryption for Microsoft Teams meetings and one-to-one calls](teams-end-to-end-encryption) (Meeting organizers must have Teams Premium to use end-to-end encrypted meetings. Teams Premium isn't required for one-to-one calls.)
- [Require a watermark for sensitive Teams meetings](watermark-meeting-content-video)
- [Overview of custom meeting templates in Microsoft Teams](custom-meeting-templates-overview)
- [Use Teams meeting templates, sensitivity labels, and admin policies together for sensitive meetings](meeting-templates-sensitivity-labels-policies)
- [Configure Teams meetings with three tiers of protection](configure-meetings-three-tiers-protection)

#### Custom meetings

Teams Premium allows organizations to extend their visual identities across the meeting experience by adding logos and backgrounds that are displayed in the meeting lobby background and other places in Teams.

There are three primary ways to customize meetings in Teams Premium:

- **Themes** - logos, images, and colors that represent your organization
- **Backgrounds** - images that people can use as meeting backgrounds when they attend Teams meetings
- **Templates** - preset lists of meeting options for different meeting types

Meeting themes and backgrounds are made available to users through meeting customization policies.

As you test themes, you might want to change images, colors, and logos as you go. We recommend that you have a Teams Administrator available who can change theme settings quickly throughout the trial. You can also test multiple themes by creating extra meeting customization policies and assigning them to different trial participants.

Meeting organizers with a Teams Premium license can create meetings using the theme you add, which are visible to all meeting participants.

For more information about using custom themes and backgrounds in Teams Premium meetings, see the following references:

- [Teams Premium meetings customization options](custom-meetings-overview)
- [Custom meeting backgrounds for Teams Meetings](custom-meeting-backgrounds)
- [Meeting themes for Teams meetings](meeting-themes)

You can use custom meeting templates to preset many of the options that are available to meeting organizers, including security, audio and video, recording and transcription, and meeting engagement settings. You can enforce settings by locking the templates or meeting organizers can be allowed to change them. Review the options in [Create a custom meeting template in Microsoft Teams](create-custom-meeting-template) as you determine what meeting templates you want to create for the trial.

#### Advanced Virtual Appointments

Teams Premium includes more features to help your workforce get the most out of the [Virtual Appointments app](/en-us/microsoft-365/frontline/virtual-appointments-app). These features include:

- SMS notifications to remind attendees of meetings.
- Meeting organizers can view and manage both scheduled and on-demand appointments in the queue.
- Organizational and departmental analytics help you see and understand how your users are working with Virtual Appointments.

Consider which of your meeting organizers should get a license to test SMS notifications and managing appointments in the queue.

Use the [Virtual Appointments usage report](/en-us/microsoft-365/frontline/virtual-appointments-usage-report) to understand how your team members are using basic Virtual Appointments features. You can compare this with the [Advanced Virtual Appointments activity report](/en-us/microsoft-365/frontline/advanced-virtual-appointments-activity-report), which shows how much your users are utilizing the features in Virtual Appointments that are only available with Teams Premium. You can use these two reports to understand which features are the most useful for your team, and gain insight into the adoption of advanced features within your organization.

The Teams Administrator requires a trial license to access the Advanced Virtual Appointments activity report.

#### Custom policy packages

A policy package is a collection of predefined policies that you can assign to users or groups who have similar roles in your organization. Teams includes several predefined policy packages and Teams Premium allows you to create your own.

If you want to test custom policy packages as part of your trial, see [Managing policy packages in Teams](manage-policy-packages) for information.

## Get started with the trial

When you complete your pre-trial planning, the next step is to add the Teams Premium trial to your Microsoft 365 subscription.

Once you add the trial, you can do the administrative setup steps to get the trial ready for your users:

- Create the meeting templates that you want to test, both for compliance and custom meetings.
- Create the meeting customization policies that you want to use to test your themes and backgrounds.
- Assign the template and customization policies to the appropriate trial participants.
- If you're using sensitivity labels, create the labels that you want to test and publish them to the trial participants.

Once the administrative setup is complete, notify your trial participants that the trial is underway and have them start testing their use cases.

### Add the Teams Premium trial to your organization and assign licenses

You use the Microsoft 365 admin center to add the Teams Premium trial.

To add the Teams Premium trial to Microsoft 365, follow these steps:

1. In the Microsoft 365 admin center navigation pane, select **Marketplace**.
2. Select the **All products** tab and search for *Microsoft Teams Premium*.
3. *Microsoft Teams Premium* is under the **Collaboration and communication section**. Select **Details**.
4. Next to the **Buy** button, select **Start free trial**.
5. Enter your information on the checkout page and select **Try now**.
6. Select **Continue**.

Note

You can also start your trial within the Teams admin center. To learn more, see [Manage Teams Premium for your organization](teams-premium-dashboard).

For information about how to assign the licenses to your users, see [Assign Microsoft 365 licenses to users](/en-us/microsoft-365/admin/manage/assign-licenses-to-users).

It might take up to 72 hours for Teams Premium sensitivity label settings to be available in the Microsoft Purview portal.