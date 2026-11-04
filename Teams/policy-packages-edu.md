---
layout: Conceptual
title: Manage Microsoft Teams policies and policy packages for education - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/policy-packages-edu
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.reviewer: 
ms.date: 2019-10-02T00:00:00.0000000Z
ms.topic: how-to
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-education
audience: Admin
ms.collection:
- M365-collaboration
- remotework
- essentials-manage
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- admindeeplinkTEAMS
ms.localizationpriority: high
search.appverid: MET150
description: Learn about policies in an educational setting and how to use and manage policy packages in Microsoft Teams.
locale: en-us
document_id: bcfef917-dc74-3fd7-eef8-5af66583a04d
document_version_independent_id: 9d1958bc-e321-06b8-91d6-a0ec291190eb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/policy-packages-edu.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: policy-packages-edu
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/policy-packages-edu.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: cfd72f77-6999-2c99-28f3-6e693750279a
---

# Manage Microsoft Teams policies and policy packages for education - Microsoft Teams | Microsoft Learn

This article is for IT admins who need to manage Microsoft Teams for Education policies and policy packages.

For an overview of managing all Teams policies, see [Assign policies to your users in Microsoft Teams](policy-assignment-overview).

Important

You can run the [Teams for Education Policy Wizard](easy-policy-setup-edu) to easily apply policies for your students, educators and staff.

## Get started with Microsoft Teams policy management

You can use policies to control the Teams features available to users and create a safe learning environment.

The main capability policy areas for Teams are:

- [Meetings](meeting-policies-overview)
- [Live events](teams-live-events/configure-teams-live-events)
- [Calling](teams-calling-policy)
- [Messaging](messaging-policies-in-teams)
- [Teams](teams-policies)
- [App permissions](teams-app-permission-policies)

You can manage all Teams policies in the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) after signing in with admin credentials.

### Where to find Microsoft Teams policies

Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage.

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) using admin credentials.
2. On the left rail navigation, find the Teams capability you'd like to adjust policies for.
3. For some capabilities, you'll need to expand its dropdown menu to find its policy page.
4. Select the capability's policy page in the menu.

### How to create and update a policy definition

Policy definitions define a set of custom policy settings for specific capabilities areas, like messaging and apps.

Before you assign policies to your users, first create policy definitions for each capability area in Teams.

#### Policy definition tips

- Set different policy definitions for your students and educators.
- Every new user (student or educator) is assigned the **Global (Org-wide default)** policy definition for each capability area.

    - Use **Global (Org-wide default)** for your strictest set of policy definitions, usually for students.

#### Steps to create policy definitions

Follow these steps to **create new policy definitions**:

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851) using admin credentials.
2. In the left rail navigation, select the policy page for the Teams capability you'd like to adjust.
3. Select **Add** to create a new policy definition.
4. On the new page, name your custom policy definition and add an optional description.
    1. For example, you may name the policy definition **Educators** for policy settings just for educators.
5. Go through the list of policy settings and adjust them according to users' needs.
6. When you're finished, select **Save** at the bottom of the page.

To **adjust an existing policy definition**:

1. In the Teams admin center, navigate to the appropriate Teams capability's policy page.
2. In the list of policy definitions, find the policy definition you want to adjust and select its name.
3. On the new page, adjust the policy settings.
4. When you're finished, select **Save** at the bottom of the page.

### Assigning policy definitions

There are multiple methods to assign policy definitions to users.

- Individual user policy assignment
- Group policy assignment
- Batch policy assignment

In most cases, we recommend that you use group policy assignment to assign policies to your users. This method allows for faster and more seamless policy application. When a user is added to a group that has a policy definition assigned to it, the new user automatically inherits the policies of the group. This allows for easier policy management when large numbers of users are added and removed to the environment, for example at the beginning and ending of a school term.

For large organizations, we also recommend batch policy assignment, which is tailored for cases where you need to assign policies to large sets of users. To learn more about these application methods, refer to [Assign policies to large sets of users in your school](batch-group-policy-assignment-edu).

If you have a smaller institution or have a need to update an individual student or educator's policy settings, follow the instructions below.

Important

Policy assignments given at the individual user level override any group policies assigned to the user. Ensure that you are only using individual policy assignments when you desire to override group policy settings.

#### How to assign a policy definition to a user

Note

Assigning a policy definition may take a while to propagate out to all the users and clients. You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.

Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** on the policy page, searching for the desired user, then applying the policy.

You can also assign a policy to a user by navigating to **Users**, selecting the user you wish to update policies for, selecting **Policies**, then **Edit**. From there, you can select the policy definition you’d like to assign to the user for each capability area.

### Policy packages in Microsoft Teams

Note

For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.

A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution. Policy packages simplify, streamline, and help provide consistency when managing policies. In normal practice, you assign each of your users a policy package, and redefine the policies in each package as needed to suit the needs of that user group. When you update settings in a package, all users assigned to that package are changed as a bulk update.

Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students. For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment. You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.

Important

Our primary recommendation is that you use the Global (Org-wide default) policy definition for students instead of a policy package. This ensures that new users in your organizations always have the strictest set of policies appropriate for students. If this recommendation does not meet the needs of your institution, one of the student policy packages below may be a good alternative.

Just like the policy list earlier in this article, policy packages predefine policies for:

- Meetings
- Live events
- Calling
- Messaging
- App permissions

Microsoft Teams currently includes the following policy packages:

| Package name listed in Microsoft Teams Admin center | Best used for | Description |
| --- | --- | --- |
| **Education\_Teacher** | Educators and staff | Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams. |
| **Education\_PrimaryStudent** | Primary school aged students | Younger, primary school aged students within your institution may need more limits within Microsoft Teams. Use this set of policies and policy settings to limit capabilities like meetings creation and management, chat management, and private calling. |
| **Education\_SecondaryStudent** | Secondary school aged students | Secondary school aged students within your institution may need more limits within Microsoft Teams. Use this set of policies and policy settings to limit capabilities like meetings creation and management, chat management, and private calling. |
| **Education\_HigherEducationStudent** | Higher education students | Higher education students within your institution may need fewer limits than younger students, but some limitations may be recommended. You can use this set of policies and policy settings to give access to chat, calling, and meetings within your organization, but limit how your students use Microsoft Teams with external participants. |
| **Education\_PrimaryTeacher\_RemoteLearning** | Educators and staff | Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning. |
| **Education\_PrimaryStudent\_RemoteLearning** | Primary school aged students | Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning. |
|  |  |  |

Each individual policy is given the name of the policy package so you can identify policies linked to a policy package. For example, when you assign the Education\_Teacher policy package to educators in your educational institution, a policy named Education\_Teacher is created for each policy in the package.

Note

If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group. You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.

## Manage policy packages

### View

View the settings of each policy in a policy package before you assign a package. In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.

Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.

### Customize

Customize the settings of policies in the policy package, as needed, to fit the needs of your organization. Any changes you make to policy settings are automatically applied to users who are assigned the package. To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.

Keep in mind that you can also change the settings of policies in a package after you assign the policy package. To learn more, see [Customize policies in a policy package](manage-policy-packages#customize-policies-in-a-policy-package).

### Assign

Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.

#### Assign a policy package to one or several users

To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.

![Screenshot of how to assign a policy package in the admin center.](media/policy-packages-healthcare-assign.png)

To learn more, see [Assign a policy package](assign-policy-packages).

If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.

#### Assign a policy package to a group

**This feature is in private preview.**

Policy package assignment to groups lets you assign multiple policies to a group of users, such as a security group or distribution list. The policy assignment is propagated to members of the group according to precedence rules. As members are added to or removed from a group, their inherited policy assignments are updated accordingly. This method is recommended for groups of up to 50,000 users but will also work with larger groups.

To learn more, see [Assign a policy package to a group](assign-policy-packages#assign-a-policy-package-to-a-group).

#### Assign a policy package to a large set (batch) of users

Use batch policy package assignment to assign a policy package to large sets of users at a time. You use the [New-CsBatchPolicyPackageAssignmentOperation](/en-us/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign. The assignments are processed as a background operation and an operation ID is generated for each batch.

A batch can contain up to 5,000 users. You can specify users by their object ID, UPN, SIP address, or email address. To learn more, see [Assign a policy package to a batch of users](assign-policy-packages#assign-a-policy-package-to-a-batch-of-users).

## Policies that should be assigned for student safety

For more information on the steps you need to take to protect students in your environment, carefully review [Keeping students safe while using Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).