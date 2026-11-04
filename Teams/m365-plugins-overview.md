---
layout: Conceptual
title: Introduction to Microsoft 365 Plugins - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/m365-plugins-overview
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
description: In this article, you'll have Microsoft 365 plugins, plugin list and labels, Microsoft 365, and One Note interaction and more.
locale: en-us
document_id: 5208aa5d-71c1-e88e-b81b-18372ee2771f
document_version_independent_id: 5208aa5d-71c1-e88e-b81b-18372ee2771f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/m365-plugins-overview.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: m365-plugins-overview
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/m365-plugins-overview.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d41950d3-33ca-5f12-1465-38676497c6b5
---

# Introduction to Microsoft 365 Plugins - Microsoft Teams | Microsoft Learn

Microsoft 365 plugins provide integration between Moodle website and Teams. These plugins make it easy for user to schedule, deliver, and collaborate the course content. The plugins can be used independently, or in partnership as per the requirement.

## Plugin list and labels

The following table lists the plugins and GitHub labels to be used based on the requirements.

| Plugins to install | Description | GitHub label(s) |
| --- | --- | --- |
| **OpenID Connect** | Enables SSO for users who work using both Moodle and Teams. | auth\_oidc |
| **Microsoft 365 integration** | Create Teams instances for each course in Moodle, and sync faculty as owners, and students as team members. | local\_o365 |
| **Microsoft 365 Repository** | Supports Microsoft 365 OneDrive content for file repositories to reduce storage needs in Moodle. | repository\_office 365 |
| **Teams Meeting** | Enables Atto editor in Moodle to create Teams meeting links. | atto\_teamsmeeting |
| **Teams Theme** | Remove Moodle blocks and extra chrome within the Moodle iFrames for Teams, which applies while mapping courses to Teams instances. | themeboost\_o365teams |
| **OneNote** | Enable OneNote to be used for assignment, submission, and feedback. | local\_onenote, assignsubmission\_onenote, and assignfeedback\_onenote |
| **Microsoft Block** | Enables Microsoft 365 quick access blocks within Moodle with links to Microsoft 365 collaboration services and install links for Microsoft Office. | block\_microsoft |
| **oEmbed Filter** | Enable video links in Moodle. | Filter\_oembed |

Moodle LMS supports the following plugins:

## OpenID Connect

The OpenID Connect plugin allows users to authenticate any website or tool that supports necessary specification and provides single sign-on support (SSO) with Microsoft 365. The OpenID Connect plugin provides institutions with the following sign in options to meet their specific requirements:

- Users can enter their Microsoft 365 credentials, such as email and password to sign in directly or sign in using Moodle’s username and password fields, without signing into Microsoft 365.
- Users can select the link to sign in through Microsoft 365 or the OpenID Connect provider on Moodle page.

The following image displays the OpenID connect log in page:

![Screenshot shows the log in to open-id connect.](media/moodle-instructions/openid-connect.png)

## Microsoft 365 integration

Microsoft 365 integration consists of several apps with multiple functionalities, which allows users to stay connected and perform different actions as required. The plugin allows administrators to check the following actions:

- Check appropriate integration functions.
- Synchronize users between Microsoft 365 and Moodle.
- Configure required permissions for users.
- Set up SharePoint website for the course files.

The following image displays the Microsoft 365 integration setup page:

![Screenshot shows Microsoft 365 integration.](media/moodle-instructions/365-integration.png)

### User functions

The users can perform the following actions with Microsoft 365 integration:

- Check the overall functioning of all Microsoft 365 plugin integrations.
- Upload a CSV file, which compares Moodle to Microsoft 365 users.
- Check configurations for Microsoft Entra permissions.

## Microsoft 365 repository

The Microsoft 365 repository plugin allows users to store course files in OneDrive. Faculty can add files from the course file section of OneDrive or from their own personal space to the repository.

Microsoft 365 repository allows the user to use it as a file repository for an institution while keeping Moodle's data structure simple. The Microsoft 365 repository plugin provides the following services:

- The faculty can store the course files in OneDrive. Each course has its own folder created in OneDrive, which allows faculty to add files either from the course files area of OneDrive or from their own personal space.
- To add files to Moodle as a copy or create a link to the file. The linked file is displayed in a new application window or is embedded in the webpage.
- To upload files to OneDrive or SharePoint using the Moodle file picker.

The following image displays the Microsoft 365 file repository:

[![Screenshot shows M365 repository.](media/moodle-instructions/microsoft-365-repository.png)](media/moodle-instructions/microsoft-365-repository.png#lightbox)

## Teams meetings

Teams meetings plugin allows user to create meetings requests in calendar, assignments, forum posts, and also in the Atto editor as per availability.

After the plugin is installed, faculty and students can create an audio or video meeting using Moodle, which requires Microsoft 365 account and Moodle permissions.

Note

Teams meetings don't appear on Outlook or Teams calendar, however, individual student names can be added to the invite for the same.

The following image displays the Teams meeting sign in page:

![Screenshot shows sign in to teams meeting.](media/moodle-instructions/teams-meeting.png)

## Microsoft 365 Teams theme

The Microsoft 365 Teams theme plugin provides users with custom view of Moodle course home page and is available for viewing when user accesses their Moodle courses within Teams.

The theme plugin gives users a unified enhanced experience with the following features:

- Adapts to Microsoft Teams theme changes, such as default, dark, and high contrast.
- Provides focus on the course activities.
- Removes Moodle blocks, navigation, header, and footer.
- Provides Microsoft Team User Interface (UI) elements.

The following image displays the Teams theme set up by the user:

[![Screenshot shows the Microsoft Teams theme.](media/moodle-instructions/teams-theme.png)](media/moodle-instructions/teams-theme.png#lightbox)

## OneNote integration

The OneNote integration plugin provides users with options to browse notebooks, sections, and pages; where assignments are submitted, and faculty provides necessary feedback on corresponding assignments in OneNote. OneNote also enhances user experience by adding features beyond tests and links, while extending the capabilities to mobile using digital pens, photo or video media, and co-authoring with groups.

OneNote integration helps with access to texts, graphics, and audio repositories. The plugin provides the following advantages:

- Include browsing notebooks, sections, and pages, where students work on assignments and provide feedback on those assignments in OneNote.
- Combine digital binder for notes, assignments, and feedback for reference and review.
- Expand drafting capabilities beyond text and links, and extend mobile usage using digital pens, photo or video media, and co-authoring with groups.
- Include submission and feedback page for each assignment under the faculty's account. When such is saved within Moodle, a copy of the HTML and any associated pictures are packaged in a zip file.

Note

The submission or feedback events trigger OneNote creation with a section for each course the student has enrolled in.

## Microsoft block

Microsoft block plugin allows the user to access course SharePoint file location and view the course in OneNote notebook for submissions, along with the option to modify Microsoft 365 integration preferences. The administrators can configure the block to appear on all the course pages.

Microsoft block enhances user experience by providing a user interface to modify Microsoft 365 integration features and access to its numerous resources. Administrators can configure the block to view the modified changes to appear on each course page. The block allows the user to perform the following activities:

- Access the course SharePoint file location and OneNote notebook.
- View the course on OneNote notebook for submissions.
- Configure the Outlook calendar sync.
- Manages connection to Microsoft 365.
- Customize personal Microsoft 365 integration preferences.

The following image shows the Microsoft block user interface:

[![Screenshot shows Microsoft block.](media/moodle-instructions/microsoft-block-1.png)](media/moodle-instructions/microsoft-block-1.png#lightbox)

## oEmbed filter

oEmbed filter plugin simplifies and enhances user experience by simplifying inclusion of the external HTML content within Moodle. The following are the advantages of oEmbed filter.

- Reduces the time to embed videos to an HTML page.
- Enables embedding of multiple video content providers.
- Ensures a quicker method to copy and embed code from any of the supported services.
- Permits video embedding without an API key.

The following image shows inclusion of external HTML content within Moodle:

[![Screenshot shows the oEmbed filter page.](media/moodle-instructions/embed-filter.png)](media/moodle-instructions/embed-filter.png#lightbox)