---
layout: Conceptual
title: Manage Teams with policies - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-teams-with-policies
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.date: 2026-08-03T00:00:00.0000000Z
description: Lean about Teams policies.
audience: admin
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- essentials-manage
ms.custom:
- teams-chat-and-channels
locale: en-us
document_id: c6c42acc-76a1-25fc-0ead-8b6dc73648a2
document_version_independent_id: 908b483c-3c88-b384-5cd5-7ab9d14e4b70
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-teams-with-policies.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-teams-with-policies
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-teams-with-policies.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 4aa29ebc-2e63-7ca8-7674-540bb6fe7bc0
---

# Manage Teams with policies - Microsoft Teams | Microsoft Learn

Policies are an important part of managing Teams. Use this article to navigate how to use policies to benefit your organization.

## What you use policies for

Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications. Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.

Note

Policies are managed through the Teams Admin Center or the Teams PowerShell module, and changes may take up to 24 hours to take effect.

## How to assign policies

Policies can be assigned in several different ways depending on what your organization is trying to accomplish. You can make and view assignments in the Teams admin center.

[![Screenshot of Teams group policy assignment.](media/group-policy-assignment-small.png)](media/group-policy-assignment.png#lightbox)

Learn more about assigning policies [here](policy-assignment-overview).

Note

To unassign policies, you can remove assignments in bulk for all users directly assigned to a policy. To learn more, read [Unassign policies in bulk](assign-policies-users-and-groups#unassign-policies-in-bulk).

## How to manage policies

Policies are managed with the Microsoft Teams admin center or [using PowerShell](teams-powershell-managing-teams#manage-policies-via-powershell).

For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar. These policies are configured in the Teams admin center.

[![Screenshot of app setup policy.](media/app-setup-policy-small.png)](media/app-setup-policy.png#lightbox)

Each policy has multiple controls which you can use to choose the options you want to use for your organization. For example, meeting policies allow you to specify meeting scheduling options for the people in your organization.

[![Screenshot of meeting policy.](media/teams-meetings-policies-global-general.png)](media/engineering-meeting-policy.png#lightbox)

### Teams for Education

You can also use the [Teams for Education policy wizard](easy-policy-setup-edu) to easily set up and manage policies for your learning environment.

[![Screenshot of Teams for Education policy wizard.](media/easy-policy-setup-quick-setup-small.png)](media/easy-policy-setup-quick-setup.png#lightbox)

## Types of policies

The following policies can be managed with Microsoft Teams.

| Policy type | Description |
| --- | --- |
| [Policy packages](manage-policy-packages) | A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization. |
| [Meeting policies](meeting-policies-overview) | A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization. Meeting policies include the following topics. - Audio and video policies - Content and screen sharing policies - Participants, guests, and access policies - General policies |
| [Voice and calling policies](voice-and-calling-policies) | Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID. |
| [App policies](app-policies) | App policies are used to control applications in Microsoft Teams. Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users. |
| [Messaging policies](messaging-policies-in-teams) | Messaging policies control chat and channel feature availability. |

This video is about differences between policies and settings.