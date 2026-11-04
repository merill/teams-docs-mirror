---
layout: Conceptual
title: Teams for Education Policy Wizard to easily apply policies for safe learning - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/easy-policy-setup-edu
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: shajohri, angch
ms.date: 2025-05-30T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-education
audience: Admin
ms.collection:
- M365-collaboration
- remotework
- tier2
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use the Teams for Education policy wizard to easily apply policies for students and educators to keep your learning environment safe.
f1keywords: 
locale: en-us
document_id: 0ebe30d6-2b8f-b8fd-3a22-0cbb1f7fabcb
document_version_independent_id: 99e96c91-d183-f794-0825-db150fefa7aa
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/easy-policy-setup-edu.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: easy-policy-setup-edu
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/easy-policy-setup-edu.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1c16e659-f3c5-360a-a0ca-ff576c2029ee
---

# Teams for Education Policy Wizard to easily apply policies for safe learning - Microsoft Teams | Microsoft Learn

## Overview

The Microsoft Teams for Education Policy Wizard simplifies managing policies for your students and educators. Use it to easily and quickly apply the most important set of policies relevant to creating a safe and productive learning experience.

Policies in Teams let you control how Teams behaves in your environment and what features are available to users. For example, there are calling policies, meeting policies, and messaging policies, to name a few, and each policy area can be customized to meet your organization's needs.

To maintain a safe and focused learning environment, it's important to set policies to control what students can do in Teams. For example, you can use policies to control who can use private chat and private calling, who can schedule meetings, and what content types can be shared. You can also use policies to turn on Teams features that enrich the learning experience.

Policies must be adjusted for both students and educators to keep the learning experience safe. Policies for students need to be more restrictive to reduce their risk of receiving inappropriate levels of access. Educators and staff need a separate set of policies that can be more permissive to enable them to be successful. For example, allow educators to schedule meetings and restrict students from doing so.

![Screenshot of wizard.](media/easy-policy-setup-institution-type.png)

This article walks you through how to run the wizard.

Important

The policies applied by the wizard will satisfy the needs of most Teams for Education customers. The wizard adjusts the Global (Org-wide default) definition of a core set of policies with settings that we recommend for student safety, and applies it to students. The wizard also creates and assigns a set of custom policies to educators and staff. Most Teams for Education customers won't need to use other policy assignment methods after running this wizard. Use other policy assignment methods *only* if you want to manually create and manage policies for your students, educators, and staff.

## Teams for Education Policy Wizard

The wizard applies a set of core policy definitions to students and a separate set of core policy definitions to educators and staff, with settings that are appropriate for each. Here's what happens when you run the wizard.

The wizard sets up policies based on educational institution type (**Primary or Secondary** or **Higher education**). You select your institution type, and the wizard does the following:

- **Students**: The wizard adjusts the Global (Org-wide default) policy definition of each policy area covered by the wizard with new default settings that are appropriate to keep your students safe. This ensures that your current students and all new students get the most restrictive set of policies.
- **Educators and staff**: The wizard creates a set of custom policy definitions for each policy area covered by the wizard with settings tailored to the needs of educators and staff. Then, it assigns the policy definitions to the group of educators and staff that you choose. In this way, your educators and staff get a more permissive set of policies to enable them to be successful.

You only need to run the wizard one time. New students automatically get the Global (Org-wide default) policy definitions applied by the wizard and new staff that you add to the group you selected are automatically assigned the custom policies.

Also, whenever a new feature is added to Teams, the appropriate EDU relevant default value of the policy for that feature will be automatically added to the Global (Org-wide default) without requiring any admin intervention. This helps to ensure that the right policies are in place to keep students secure and engaged.

Note

See Policies applied by the wizard for a detailed list of policy definitions applied by the wizard.

Now, let's get started!

## Run the wizard

Follow these steps to run the wizard.

1. If you're new to Teams, the wizard automatically starts. Otherwise, you can start the wizard anytime from the dashboard. In the left navigation of the Microsoft Teams admin center, go to **Home**, and then in the **Easy policy setup for a safe learning environment** tile, select **Quick setup**.

    ![Screenshot of the wizard in the dashboard.](media/easy-policy-setup-quick-setup.png)
2. Select your educational institution type (**Primary or Secondary** or **Higher education**), and then select **Next**.

    ![Screenshot of the page in wizard to select institution type.](media/easy-policy-setup-institution-type.png)
3. Search for and select groups that contain your educators and staff, and then select **Next**. If you don't have any groups set up yet for your educators and staff, [create a group](/en-us/microsoft-365/admin/create-groups/create-groups), and then rerun the wizard. You can select up to three groups. Educators and staff in the groups you select will be assigned a set of custom policies tailored to their needs. Remember that this set of policies is separate from the policies applied to students.

    ![Screenshot of page in wizard to select educator and staff groups.](media/edu-policy-wizard-add-3-groups.png)
4. Review your selections.

    ![Screenshot of page in wizard to review selections.](media/edu-policy-wizard-3-groups-review.png)
5. Select **Apply** to apply your changes. This may take a few minutes to complete.The Global (Org-wide default) policy definitions are immediately applied to students. For your educators and staff, it could take a few hours for the custom policies to be assigned to each member of the groups you selected, depending on the size of the groups. This happens in the background, after you successfully complete this step.
6. You're on your way, but you're not done yet! There are a few more things to consider. Next, check out the steps in the What to do after running the wizard section of this article.

    ![Screenshot of page in wizard for next steps.](media/easy-policy-setup-on-way.png)

## What to do after running the wizard

### Step 1: Remove existing policy assignments that conflict with policies applied by the wizard

Important

**Complete this step only if you have existing policies assigned to students or educators and staff *before* you ran the wizard**. If you're new to Teams and don't have any existing policies other than the policies created by the wizard, skip this and go to step 2.

In Teams, for a given policy area, a policy can be applied to a user in the following ways:

- Direct assignment to the user
- Assignment to a group the user is a member of
- If the user isn't directly assigned a policy or isn't a member of any group that's assigned a policy, the user automatically gets the Global (Org-wide default) policy

If more than one of these policy assignments exist for a user, Teams uses the following order to determine which policy assignment takes effect. For more info, see [Which policy takes precedence](policy-assignment-overview#which-policy-takes-precedence) or [Precedence rules for groups](assign-policies-users-and-groups#precedence-rules).

| Policy assignments of a user | Policy that takes effect |
| --- | --- |
| Policy assigned to group: No <br> Policy assigned directly to user: No | Global (Org-wide) default policy |
| Policy assigned to group: No <br> Policy assigned directly to user: Yes | Policy assigned directly to user |
| Policy assigned to group: Yes <br> Policy assigned directly to user: Yes | Policy assigned directly to user |
| Policy assigned to group: Yes <br> Policy assigned directly to user: No | Policy assigned to group <br> If the user is a member of multiple groups and each group is assigned a policy of the same policy area, the policy that has the highest [group assignment ranking](assign-policies-users-and-groups#group-assignment-ranking) takes effect. |

Because of this order, the policies created by the wizard won't take effect if a user has existing direct assignments or group assignments. This means that you'll have to remove the existing policy assignments from the user so the policy applied by the wizard takes effect.

For each policy area applied by the wizard, do the following:

- Remove all existing direct assignments and group assignments from your students so that the Global (Org-wide default) policy definition applied by the wizard takes effect.
- Remove any conflicting direct assignments for your educators and staff so that the custom policy definition created by the wizard takes effect. Use the above table to determine the scenarios that apply to you. 
     Keep in mind that the wizard assigns policies to your educators and staff group using a [group assignment ranking](assign-policies-users-and-groups#group-assignment-ranking) of 1, which is the highest ranking. If your educators and staff group has an existing policy of the same policy area assigned to it, that existing policy is moved to a lower ranking and the policy assigned by the wizard takes effect.

[Learn more](batch-group-policy-assignment-edu#remove-a-policy-that-was-directly-assigned-to-users) about how to remove policies that are directly assigned to users.

For example, you assigned a meeting policy directly to educators and your students have the Global (Org-wide default) meeting policy. In this scenario, remove the meeting policy that you directly assigned to educators so that the custom policy definition for the meeting policy created by the wizard takes effect. You don't have to do anything with the existing Global (Org-wide default) meeting policy for students because no other meeting policies conflict with it.

### Step 2: Check for additional measures that you can take for student safety

The wizard automatically adjusts and applies these policies. There are few more measures, which you may want to take based on the needs of your institution to stay safe.

See [Keeping students safe while using Teams for distance learning](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) for more safety recommendations.

### Step 3: Check Message Center for policy updates

Currently, the wizard applies our recommended policies when you run it. It's important to know that as new policies become available in Teams, the Global (Org-wide default) settings for student safety are automatically updated by the wizard.

But do check the [Message Center](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (in the Microsoft 365 admin center) frequently to stay up to date on new features and their policies and policy settings in Teams.

## Make changes in the wizard

If you need to make changes after you run the wizard, you can rerun it and change your selections.

1. In the left navigation of the Microsoft Teams admin center, go to **Home**, and then in the **Easy policy setup for a safe learning environment** tile, select **Change**.
2. From here, continue through each page of the wizard to make your changes. You can change your institution type, the groups of educators and staff to which you want to assign policies, or both.

    The following table summarizes what happens when you make a change in the wizard.

    | Type of change | Policy behavior |
    | --- | --- |
    | Change both the educational institution type and the educators and staff groups | - **Students**: The Global (Org-wide default) policy definitions based on the new educational institution type are applied to students.<br>    - **Educators and staff**: A set of custom policy definitions based on the new educational institution type is created and assigned to the new educator and staff groups. The previous custom policy definitions are removed from the previous educators and staff groups. |
    | Change only the educational institution type | - **Students**: The Global (Org-wide default) policy definitions based on the new educational institution type are applied to students.<br>    - **Educators and staff**: A set of custom policy definitions based on the new educational institution type is created and assigned to the educators and staff groups. The custom policy definitions created for the previous educational institution type are removed from the educators and staff groups. |
    | Change only the educators and staff groups | - **Students**: No change to the Global (Org-wide default) policy definitions applied to students.<br>    - **Educators and staff**: The custom policy definitions are assigned to the new educators and staff groups and removed from the previous educators and staff groups. |

## Policies applied by the wizard

### Policy areas

Here's the policy areas and corresponding policy names covered by the wizard. To find these policies, go to the Microsoft Teams admin center, and then in the left navigation, go to each policy area page.

# [Students](#tab/students)
| Policy area | Primary or Secondary policy name | Higher education policy name |
| --- | --- | --- |
| Teams policy | Global (Org-wide default) | Global (Org-wide default) |
| Meeting policy | Global (Org-wide default) | Global (Org-wide default) |
| Live events policy | Global (Org-wide default) | Global (Org-wide default) |
| App setup policy | Global (Org-wide default) | Global (Org-wide default) |
| App permission policy | Global (Org-wide default) | Global (Org-wide default) |
| Messaging policy | Global (Org-wide default) | Global (Org-wide default) |
| Calling policy | Global (Org-wide default) | Global (Org-wide default) |

# [Educators and staff](#tab/educators)
| Policy area | Primary or Secondary policy name | Higher education policy name |
| --- | --- | --- |
| Teams policy | Primary or Secondary Educators and Staff - Teams | Higher Education Educators and Staff - Teams |
| Meeting policy | Primary or Secondary Educators and Staff - Meeting | Higher Education Educators and Staff - Meeting |
| Live events policy | Primary or Secondary Educators and Staff - Live events | Higher Education Educators and Staff - Live events |
| Messaging policy | Primary or Secondary Educators and Staff - Messaging | Higher Education Educators and Staff - Messaging |
| Calling policy | Primary or Secondary Educators and Staff - Calling | Higher Education Educators and Staff - Calling |

### Policy settings

Here's a summary of the settings applied by the wizard for each policy area.

Note

Only team owners can create shared channels.

Shared channels with other organizations require configuration of [Microsoft Entra B2B direct connect](/en-us/azure/active-directory/external-identities/b2b-direct-connect-overview) which is disabled by default. See [Collaborate with external participants in a channel](/en-us/microsoft-365/solutions/collaborate-teams-direct-connect) to enable this feature.

# [Students](#tab/student-settings)
Here's a list of the Global (Org-wide default) policy definitions adjusted by the wizard and applied to students.

| Policy area | Subarea | Policy setting | Primary or Secondary | Higher education |
| --- | --- | --- | --- | --- |
| Teams policy |  | Create private channels | Off | On |
|  |  | Create shared channels | On | On |
|  |  | Share channel with external participants | On | On |
|  |  | Participate in an external shared channel | On | On |
| Meetings policy | General | Allow Meet now in channel meetings | Off | On |
|  |  | Allow the Outlook add-in | Off | On |
|  |  | Allow channel meeting scheduling | Off | On |
|  |  | Allow scheduling private meetings | Off | On |
|  |  | Allow meeting registration | On | On |
|  |  | Who can register | People in my organization | People in my organization |
|  | Audio & video | Transcription | On | On |
|  |  | Meeting recording | Off | On |
|  |  | Mode for IP audio | Outgoing and incoming audio enabled | Outgoing and incoming audio enabled |
|  |  | Mode for IP video | Outgoing and incoming video enabled | Outgoing and incoming video enabled |
|  |  | IP video | On | On |
|  |  | Allow NDI streaming | Off | Off |
|  |  | Media bit rate (KBs) | 50,000 | 50,000 |
|  | Content sharing | Screen sharing mode | Entire screen | Entire screen |
|  |  | Allow a participant to give or request control | On | On |
|  |  | Allow an external participant to give or request control | On | On |
|  |  | PowerPoint sharing | On | On |
|  |  | Whiteboard | On | On |
|  |  | Shared notes | On | On |
|  | Participants & guests | Anonymous users and dial-in callers can start a meeting | Off | On |
|  |  | Roles that have presenter rights in meetings | People in my organization and guests | People in my organization and guests |
|  |  | Who can bypass the lobby | People in my org | People in my org |
|  |  | People dialing in can bypass the lobby | Off | Off |
|  |  | Meet now in private meetings | Off | On |
|  |  | Live captions | Off, but organizers and coorganizers can turn them on | Off, but organizers and coorganizers can turn them on |
|  |  | Meeting chat | On | On |
| Live events policy |  | Live events scheduling | Off | Off |
|  |  | Transcription for attendees | On | On |
|  |  | Who can join scheduled live events | People in my organization | People in my organization |
|  |  | Who can record an event | Always | Always |
| Messaging policy |  | Owners can delete sent messages | Off | On |
|  |  | Delete sent messages | Off | On |
|  |  | Edit sent messages | Off | On |
|  |  | Read receipts | User controlled | User controlled |
|  |  | Chat | Off | On |
|  |  | Giphys in conversations | Off | On |
|  |  | Giphy content rating | Strict | Strict |
|  |  | Memes in conversations | On | On |
|  |  | Stickers in conversations | On | On |
|  |  | URL previews | On | On |
|  |  | Translate messages | On | On |
|  |  | Immersive reader for messages | On | On |
|  |  | Send urgent messages using priority notifications | Off | On |
|  |  | Create voice messages | Allowed in chats and channels | Allowed in chats and channels |
|  |  | On mobile devices, display favorite channels above recent chats | Enabled | Enabled |
|  |  | Remove users from group chats | Off | On |
| App permission policy |  | Microsoft apps | Block specific apps and allow all others &gt; Walkie Talkie blocked | Allow all apps |
|  |  | Third-party apps | Allow all apps | Allow all apps |
|  |  | Custom apps | Allow all apps | Allow all apps |
| App setup policy |  | Upload custom apps | Off | Off |
|  |  | User pinning | On | On |
|  |  | Installed apps | None | None |
|  |  | Pinned apps | Activity, Calendar, Teams | Activity, Chats, Teams, Calendar, Calling, File |
| Calling policy |  | Make private calls | Off | On |
|  |  | Call forwarding and simultaneous ringing to people in your organization | Off | On |
|  |  | Call forwarding and simultaneous ringing to external phone numbers | Off | On |
|  |  | Voicemail is available for routing inbound calls | User controlled | User controlled |
|  |  | Inbound calls can be routed to call groups | Off | On |
|  |  | Allow delegation for inbound and outbound calls | Off | On |
|  |  | Prevent toll bypass and send calls through the PSTN | Off | Off |
|  |  | Busy on busy is available when in a call | Off | Off |
|  |  | Allow web PSTN calling | Off | On |

# [Educators and staff](#tab/educator-settings)
Here's a list of the custom policy definitions assigned to the educators and staff groups that you choose in the wizard.

| Policy area | Subarea | Policy setting | Primary or Secondary | Higher education |
| --- | --- | --- | --- | --- |
| Teams policy |  | Create private channels | On | On |
|  |  | Create shared channels | On | On |
|  |  | Share channel with external participants | On | On |
|  |  | Participate in an external shared channel | On | On |
| Meetings policy | General | Allow Meet now in channel meetings | On | On |
|  |  | Allow the Outlook add-in | On | On |
|  |  | Allow channel meeting scheduling | On | On |
|  |  | Allow scheduling private meetings | On | On |
|  |  | Allow meeting registration | On | On |
|  |  | Who can register | People in my organization | People in my organization |
|  | Audio & video | Transcription | On | On |
|  |  | Meeting recording | On | On |
|  |  | Mode for IP audio | Outgoing and incoming audio enabled | Outgoing and incoming audio enabled |
|  |  | Mode for IP video | Outgoing and incoming video enabled | Outgoing and incoming video enabled |
|  |  | IP video | On | On |
|  |  | Allow NDI streaming | Off | Off |
|  |  | Media bit rate (KBs) | 50,000 | 50,000 |
|  | Content sharing | Screen sharing mode | Entire screen | Entire screen |
|  |  | Allow a participant to give or request control | On | On |
|  |  | Allow an external participant to give or request control | On | On |
|  |  | PowerPoint sharing | On | On |
|  |  | Whiteboard | On | On |
|  |  | Shared notes | On | On |
|  | Participants & guests | Anonymous users and dial-in callers can start a meeting | On | On |
|  |  | Roles that have presenter rights in meetings | OrganizerOnlyUserOverride | OrganizerOnlyUserOverride |
|  |  | Who can bypass the lobby | Only organizers and coorganizers | Only organizers and coorganizers |
|  |  | People dialing in can bypass the lobby | Off | Off |
|  |  | Meet now in private meetings | On | On |
|  |  | Live captions | Disabled but user can override | Disabled but user can override |
|  |  | Meeting chat | On | On |
| Live events policy |  | Live events scheduling | On | On |
|  |  | Transcription for attendees | On | On |
|  |  | Who can join scheduled live events | People in my organization | People in my organization |
|  |  | Who can record an event | Always record | Always record |
| Messaging policy |  | Owners can delete sent messages | On | On |
|  |  | Delete sent messages | On | On |
|  |  | Edit sent messages | On | On |
|  |  | Read receipts | User controlled | User controlled |
|  |  | Chat | On | On |
|  |  | Giphys in conversations | On | On |
|  |  | Giphy content rating | Strict | Strict |
|  |  | Memes in conversations | On | On |
|  |  | Stickers in conversations | On | On |
|  |  | URL previews | On | On |
|  |  | Translate messages | On | On |
|  |  | Immersive reader for messages | On | On |
|  |  | Send urgent messages using priority notifications | On | On |
|  |  | Create voice messages | Allowed in chats and channels | Allowed in chats and channels |
|  |  | On mobile devices, display favorite channels above recent chats | Enabled | Enabled |
|  |  | Remove users from group chats | On | On |
| Calling policy |  | Make private calls | On | On |
|  |  | Call forwarding and simultaneous ringing to people in your organization | On | On |
|  |  | Call forwarding and simultaneous ringing to external phone numbers | On | On |
|  |  | Voicemail is available for routing inbound calls | User controlled | User controlled |
|  |  | Inbound calls can be routed to call groups | On | On |
|  |  | Allow delegation for inbound and outbound calls | On | On |
|  |  | Prevent toll bypass and send calls through the PSTN | Off | Off |
|  |  | Busy on busy is available when in a call | Off | Off |
|  |  | Allow web PSTN calling | On | On |

---