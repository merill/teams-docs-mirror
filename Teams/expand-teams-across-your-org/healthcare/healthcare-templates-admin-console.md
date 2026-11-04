---
layout: Conceptual
title: Use healthcare team templates - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/expand-teams-across-your-org/healthcare/healthcare-templates-admin-console
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
audience: ITPro
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- highpri
ms.reviewer: yinchang
ms.date: 2020-09-10T00:00:00.0000000Z
description: Learn how to manage and use the healthcare team templates in the Teams admin center and with Microsoft Graph to quickly and easily create teams for your healthcare organization.
ms.custom: seo-marvel-mar2020
locale: en-us
document_id: eb17d752-d62d-1d41-fa98-5eafe2c057d9
document_version_independent_id: 3ced31b7-2ac5-e140-b848-f97eee63a52f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: expand-teams-across-your-org/healthcare/healthcare-templates-admin-console
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 3d585620-911e-d704-65c1-41c968421b3e
---

# Use healthcare team templates - Microsoft Teams | Microsoft Learn

Team templates in Microsoft Teams allow you to quickly and easily create teams by providing a predefined team structure of settings, channels, and pre-installed apps.

For healthcare organizations, team templates can be especially powerful, as they help you to quickly deploy consistent teams across your organization. Templates also help staff to get oriented with how to effectively use Teams.

Teams includes templates designed specifically for healthcare organizations. Use these pre-built templates to quickly create teams for staff to communicate and collaborate on patient care or operational needs. In this article, we introduce you to each of these templates and recommend how to use them.

How you manage and work with team templates depends on whether you're an admin or developer.

| If you're: | Then, you: |
| --- | --- |
| An admin or IT pro | Manage team templates in the Teams admin center. View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| A developer | Use Microsoft Graph to create teams from team templates. |

## Manage team templates in the Teams admin center

As an admin, you can manage team templates in the Microsoft Teams admin center. Here, you can view details about each template. You can also [create and assign templates policies](../../templates-policies) to your staff to control which templates they see in Teams for [creating teams](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

To learn more about team templates in general, see [Get started with team templates in the Teams admin center](../../get-started-with-teams-templates-in-the-admin-console).

We currently offer the following pre-built healthcare team templates. To view them, in the left navigation of the Teams admin center, go to **Teams** &gt; **Team templates**.

### Patient Care

Streamline healthcare communication and collaboration within a ward, pod, or department. Use this template to facilitate patient management and the operational needs of a ward. For example, post ward announcements in the *Announcements* channel and manage shifts in the *Staffing* channel.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Patient Care | `healthcareWard` | Channels:<br>- General<br>- Announcements<br>- Huddles<br>- Rounds<br>- Staffing<br>- Training<br><br> Apps: <br>- Approvals<br>- Bulletins<br>- Inspection<br>- Lists<br>- Shifts<br>- Planner<br>- Wiki |

### Hospital

Streamline communication and collaboration between multiple wards, pods, and departments within a hospital. This template includes a set of channels for hospital operations, and can be extended for further customization.

| Template type | TemplateId | Properties that come with this template |
| --- | --- | --- |
| Hospital | `healthcareHospital` | Channels: <br>- General<br>- Announcements<br>- Compliance<br>- Custodial<br>- Human Resources<br>- Pharmacy<br><br> Apps: <br>- Approvals<br>- Bulletins<br>- Employee ideas<br>- Inspection<br>- Lists<br>- Shifts<br>- Planner<br>- Wiki |

## Use team templates with Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates), [Microsoft Teams API overview](/en-us/graph/teams-concept-overview), and [teamsTemplate resource type](/en-us/graph/api/resources/teamstemplate).

Here are the pre-built healthcare team templates.

### Patient Care

This template is meant for communication and collaboration within a ward, pod, or department. Use this template to facilitate patient management and the operational needs of a ward. For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*. If you're looking to streamline your ward operations, then this template is for you.

| Template Type | TemplateId | Template channels |
| --- | --- | --- |
| Healthcare - Ward | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')` | GeneralAnnouncements²  Huddles²  Rounds²  Staffing²  Training² |

²Auto-favorited channels

### Hospital

This template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital. It includes several operational channels such as *Announcements*, *Custodial*, and *Pharmacy*. We also provide a script that you can use to extend the template with more departments or specialty channels. You can edit it to fit your needs.

For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, you can adapt the script to include an *Endocrinology* channel and remove the *Ophthalmology* channel. We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation. Users generally favorite any channels that they find relevant.

| Template type | TemplateId | Template channels |
| --- | --- | --- |
| Healthcare - Hospital | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')` | GeneralAnnouncements²  Compliance²  Custodial  Human Resources  Pharmacy |

²Auto-favorited channels

### How to use team templates with Microsoft Graph

To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIds above. For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a team](/en-us/graph/api/team-post).

Note

The channels in the template will be automatically created under the **General** tab.

#### Example: Hospital template extension script

```Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### Related articles

- [Create a team from a template](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Get started with team templates in the Teams admin center](../../get-started-with-teams-templates-in-the-admin-console)
- [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates)
- [Get started with Teams for Healthcare organizations](/en-us/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&amp;toc=%2fmicrosoftteams%2ftoc.json)