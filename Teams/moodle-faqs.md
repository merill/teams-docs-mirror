---
layout: Conceptual
title: Moodle frequently asked questions - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/moodle-faqs
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: NickWalk
ms.author: nickwalk
manager: joglocke
ms.topic: article
ms.service: msteams
audience: admin
ms.date: 2026-08-11T00:00:00.0000000Z
description: In this article, check FAQS and answers on Moodle LMS with Microsoft Teams, including synchronization issues, SSO, user sync, and troubleshoot sign-in issues.
locale: en-us
document_id: 2ae00055-f4b1-bed2-3c52-949d2167841b
document_version_independent_id: 2ae00055-f4b1-bed2-3c52-949d2167841b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/moodle-faqs.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: moodle-faqs
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/moodle-faqs.md
platformId: d9873acc-252e-febc-e664-47e753704527
---

# Moodle frequently asked questions - Microsoft Teams | Microsoft Learn

Get answers to some of your queries when using Moodle LMS.

What should I do if one or more of the course teams weren't created after synchronization?

Each Moodle course must have at least one faculty and one student matched to a Microsoft 365 account username. The team can't be created, if the synchronization doesn't find a match.

Each team course instance must have an owner, and the synchronization sets the faculty as the owner, with assumption that the faculty has Teams license.

What should we do to remove Moodle login page when working from Teams? Can we force single sign-on (SSO)?

The users have multiple sign in options from the Moodle login page.

- To sign in exclusively using Microsoft 365 credentials, enable the **Force redirect** configuration settings for the **auth\_oidc plugin**. If the service is enabled, user can see the Microsoft sign in page.
- To sign in manually to the Moodle portal, see [Moodle](https://moodle.org/login/index.php).

How can I specify which users to sync? I don’t want all Microsoft Entra users synchronized with the Moodle website. 

Use the **User Creation Restriction** option to specify the users by synchronizing the configuration options of the **local\_o365** plugin. The dropdown menu to the left of the **filter** offers options such as Country or Region, Company Name, and Language.

Tip

Create a dynamic Microsoft 365 group to enable the **filter** option with multiple profile properties.

The following image shows user creation restrictions options:

![sync](media/moodle-instructions/faq-2.png)

![Microsoft Entra ID](media/moodle-instructions/faq-3.png)

We would like our faculty to be able to synchronize courses to Teams? Are Moodle administrators the only ones who can control synchronization of courses?

By default only Moodle administrators can configure synchronization. The team owner can control if a course is synchronized to Teams and **Allow configure course sync in course** is enabled. In this case, the team owner is the faculty. The block displays the configuration option to individuals with the appropriate owner permissions.

The following image shows the option **Allow configure course sync in course**:

![Admin](media/moodle-instructions/faq-4.png)

The following image shows synchronization of courses:

![Synchronization](media/moodle-instructions/faq-5.png)

We have followed the documentation, but the user accounts fail to sync Microsoft Entra ID and Moodle. What should we do?

The issue can be resolved before users perform the **Delta token clean up** as a final troubleshooting step.

The following table provides the actions and dependencies to be performed and checked:

| Dependency | Action | Reference |
| --- | --- | --- |
| Stable version | Verify that the version of Moodle is listed as a **stable**. | For more information, see [Version support](https://docs.moodle.org/dev/Releases#Version_support). |
| Permissions | Verify that the Azure application has the necessary permissions to run the synchronization. | For more information, see [Microsoft permissions](https://docs.moodle.org/311/en/Microsoft_365#Permissions). |
| Full sync | Verify that **Perform a full sync each run** is enabled, and review the **Task Logs** for **Sync users with Microsoft Entra ID**. | For more information, see [Enable full sync](https://docs.moodle.org/311/en/local_o365)For more information, see [Check task logs](https://docs.moodle.org/311/en/local_o365#Sync_users_with_Azure_AD). |
| Token refresh | Clean the **User sync delta token** in the local\_o365 plugin. | For more information, see, [Token refresh](https://docs.moodle.org/38/en/Office365). |

One or more users are unable to sign in using their Microsoft 365 credentials, although most users can sign in without an issue. What would be the cause of this inconsistency?

The reason for inconsistencies with users being able unable to sign using their Microsoft 365 credentials can be related to the user mapping operation during synchronization. To resolve the issue, perform the following steps:

- Check if the Moodle user authentication type is **OpenID**.
- Check if the Moodle **User Name** matches the Microsoft Entra username.
- Clean up the **Token Issue** and retry.
- Check if the users have **Permissions** to access the Azure application.

All users are unable to sign in using their Microsoft 365 credentials. What can we do to resolve this?

Users who were unable to sign in at the start need to report the issue and verify that the application **Client secret** hasn't expired.

The following image shows the error message received when user sign using their Microsoft 365 credentials:

![Report issue](media/moodle-instructions/faq-6.png)

The following image shows the error in Azure portal:

![Azure portal](media/moodle-instructions/faq-7.png)

If the **Client secret** has expired, then user needs to generate a new **Client secret**, and update the configuration found on page. Users can sign in again after the **Client secret** has been updated, which can take up to 24 hours to re-provision.

How to change the teams instance that is linked to a course?

Administrators can change the teams instance associated with a course through the **Manage Teams Connections** page. Select **Connect** next to the course to be changed and select teams instance. If you use course reset to archive a team, you can link it back to the previous team.

The following image shows the teams instance:

![Teams instance](media/moodle-instructions/faq-8.png)

Why isn’t the Atto Teams meeting integration showing up within the Atto editor?

The user can face Atto Teams meeting issue if the icon reference is missing in the **Toolbar config**, which displays the Teams icon within the Atto editor. User needs to add Teams meeting icon to the right of the links icon using the following steps:

- Install the plugin.
- Update **Toolbar config** with **teams meeting**.

The following images show Toolbar icon after Toolbar configuration adjustment:

![Tool bar](media/moodle-instructions/faq-9.png)

![Links icon](media/moodle-instructions/faq-10.png)

For more information on editing Atto toolbar, see:

- [Atto editor-ModdleDocs](https://docs.moodle.org/311/en/Atto_editor)
- [Atto editor-Icon mapping](https://docs.moodle.org/311/en/Atto_editor#:%7E:text=in%20the%20editor.-,Atto%20editor%20toolbar,-Atto%20Row%201)

Do the meetings scheduled through Microsoft integration appear in Outlook or in Teams calendars? What is the standard timeline for the meetings to be displayed?

The meetings scheduled through the app don't appear in the scheduler’s Outlook or Teams calendar as they're similar to Channel Meetings. All the members in the course channel can attend the meeting directly from the embedded channel link. For more information, see [Channel meetings](https://www.knowledgewave.com/blog/benefits-of-channel-meetings-in-microsoft-teams).

However, you can access the invite and manually add participant names to the **Required** or **Optional** fields of the meeting invitation to display the remote meeting on their calendars. The standard timelines are based on the date the user specifies when the meeting is created. For more information, see [Limits and specifications for Teams](/en-us/microsoftteams/limits-specifications-teams).

Is there any support site where we can get more help on products and other issues?

For support and help on the product and services issues or developer community help see, [Support and Feedback](/en-us/microsoftteams/platform/feedback).