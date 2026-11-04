---
layout: Conceptual
title: Admin setup of Parents in Teams for Education - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/edu-parents-app
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: reference
ms.service: msteams
ms.subservice: teams-education
audience: admin
ms.reviewer: 
ms.date: 2026-02-27T00:00:00.0000000Z
description: Microsoft Teams article documenting prerequisites and setup of Parents in Teams for Education.
ms.localizationpriority: Medium
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- tier2
ms.custom:
- admindeeplinkTEAMS
locale: en-us
document_id: 2d84a498-f519-2828-4979-efd79ab86d86
document_version_independent_id: b173c9d8-8cde-61a7-8a32-d74ce62af9bb
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/edu-parents-app.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: edu-parents-app
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/edu-parents-app.md
platformId: 9ab450ca-4680-2c5e-3f3f-9bbc3f142e8a
---

# Admin setup of Parents in Teams for Education - Microsoft Teams | Microsoft Learn

The Parent Connection in Teams for Education helps educators securely connect and engage with the parents and guardians of the students in their class teams using Teams.

This article provides guidance to education IT professionals on requirements and setup of the Parent Connection.

## Share guardian and educator resources

Here are some resources IT admins can share with guardians and educators on how they can get started using the Parent Connection.

- For guidance on getting guardians set up, see [Communicate with guardians in Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&amp;rs=en-us&amp;ad=us).
- For guidance on getting educators set up, see [Connect with educators in Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

## Benefits of Parent Connection

The Parents Connection allows educators and guardians to chat, email, and call using Teams.

- Educators can initiate chats with guardians.
    - If the guardian doesn't have a Teams consumer account or hasn't yet joined Teams, they'll receive the message from the educator along with an email invite to go to Teams. This only applies in cases where the invite limits haven't been reached, and the chat is a new chat or an existing chat that has been reentered from the Parent Connection.
- It works with Supervised chat. For more information, see [Use supervised chats in Microsoft Teams](supervise-chats-edu).
    - By default, guardians have restricted permissions, so they can't chat with students or remove users from chats.
    - This setting can be changed by the tenant admin.
- Educators can select a guardian's email to email them using their native email client.
- Educators can select a guardian's phone number to call them within Teams.

Important

For click to call functionality in Teams, your tenant needs:

- Public Branch Exchange (PBX) capabilities.
- Connection to the PSTN.

Microsoft 365 A1 and A3 plans don't include PBX capabilities nor PSTN connection. You can purchase [add-on licenses for each of these](/en-us/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

Microsoft 365 A5 plans only include PBX capabilities using Teams Phone System. You'll still need to [purchase a Teams Calling Plan or use a third-party solution](pstn-connectivity) to connect to external numbers on the PSTN.

For more information on all your options to get PSTN connectivity, see [PSTN connectivity options](pstn-connectivity).

For more information on Teams calling licensing, see [Teams add-on licensing options](/en-us/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## Turn on the Parents app in the Teams admin center

The Parents app is turned off by default, so the class team owners won't see it in their class teams until it's allowed through the Teams admin center. Administrators can control access to Parents app using [Allow apps blocked by developers](manage-apps#allow-or-block). Sign in to the Teams admin center and access **Teams apps** &gt; [Manage apps](https://admin.teams.microsoft.com/policies/manage-apps). Search for **Parents** on the **Manage** apps page to find the Parents app published by Microsoft, and select **Allow** or **Block** option.

At any time, the app can be turned off at the tenant level using [Allow and block apps](manage-apps#allow-or-block) in the Teams admin center. If it's turned off at the tenant level, it will be blocked for all users, even if user-level permissions are turned on.

The Parents app can also be turned off **at the user level** using [Manage app permission policies in Microsoft Teams](teams-app-permission-policies).

## Requirements

You need to use Microsoft Graph or School Data Sync (SDS) to populate each student's parent and guardian related contact information. If your school doesn't use SDS, you can allow teachers to manually update students’ parent contact information.

For any queries, contact us through [Microsoft Education Support](https://aka.ms/schoolconnectionsupport) and we're happy to assist you.

### Graph API

If you already use [Microsoft Graph PowerShell SDK](/en-us/powershell/microsoftgraph/overview) to create Student identities, you can easily include [relatedContact resource type](/en-us/graph/api/resources/relatedcontact).

### School Data Sync

Teams guardian contact data stays current with SIS using School Data Sync (SDS), when SDS is set up to sync regularly.

If guardian is removed from a *Student's* records, any existing chats involving them will contain a banner visible to chat owner. This banner will make the chat owner aware of the change, asking them to remove the guardian from the chat. Microsoft won't automatically update chat membership to remove the guardian.

- You need School Data Sync (SDS) to populate each student's parent and guardian **related contact** information.

    - [Deploy SDS](/en-us/schooldatasync/parents-and-guardians-in-sds)
- If you need assistance in setting up SDS and populating parent and guardian **related contacts** for the students in your tenant, contact the EDU Customer Success team by:

    - Completing the RFA process at [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
    - Opening a ticket at [Support](https://aka.ms/sdssupport).
- Currently, SDS only supports CSV-based data ingestion for Parent Contacts; however, you can use [PowerSchool API Sync](/en-us/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) or [OneRoster API Sync](/en-us/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) for all roster data, and just add Parent Contacts using CSV.

    - Create a second sync profile using the [SDS v1 CSV format](/en-us/schooldatasync/school-data-sync-format-csv-files-for-sds) or [SDS v2.1 CSV format](/en-us/schooldatasync/sds-v2.1-csv-file-format-classic).
    - Pull the two populated [Parent files](/en-us/schooldatasync/parent-contact-sync-file-format)with the rest of the v1/v2.1 files empty (just the headers).
        - User.csv
        - Guardianrelationship.csv
            - The *Role* value needs to be completed for each parent and guardian to indicate if they're a `parent` or `guardian`.
                - Only the values of `parent` or `guardian` are supported in the app. Other values will result in errors.
                - For the SDS v1 format, it will be labeled as **Role**, but for the SDS v2.1 format, it will be labeled as **relationshipRole**.
    - To view a sample set of the CSV files, see the [Minimum Required Attributes GitHub files](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
    - If you want to automate pulling in the CSV files after the initial sync, read our [CSV File Sync Automation document](/en-us/schooldatasync/csv-file-sync-automation).
    - For help with setting up your SDS data sync, reach out to [our customer success team](https://www.microsoft.com/fasttrack?rtc=1) or [open a support ticket](https://edusupport.microsoft.com/support?product_id=data_sync).

### Manually Update Parent Contact Information

Schools can allow teachers to update manually the parent contact information corresponding to each child. This feature is enabled by default. However, no teacher’s request goes through unless an admin 'approves' it. \*\*Once an admin approves the request, educators can use the parent contact information to easily contact parents and guardians through Teams.

If your school doesn't want to use this feature, you can disable it using PowerShell.

1. The teacher opens the parent app for the class inside the class team.
2. The teacher can add or edit existing parent contact details. To view the educator flow, see [Communicate with guardians in Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e#ID0EDDBHD).
3. Once the request is submitted, it's sent to admins for approval. For more information about Approvals app, see [What is Approvals?](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) and [Manage the Approvals app in Microsoft Teams](approval-admin).
4. Global admins and Teams admins are eligible to approve these requests. To check for admin roles, visit [Azure portal](https://ms.portal.azure.com/#view/Microsoft_AAD_IAM/AllRolesBlade). Search for the administrative role you want to check. Select Assignments from the Manage menu to view who are the admins.

    Note

    For an approval request to be created, not just one user, but **all** the Global admins and Teams admins in the tenant should be enabled. For enabled users, you can see the screenshot below.

    ![Screenshot of enabled users.](media/enabled-users.png)

    For more information on the power automate side, see [Enable or disable application users.](/en-us/power-apps/developer/data-platform/use-single-tenant-server-server-authentication#enable-or-disable-application-users)

    Use the following steps to enable the Global/Teams administrator:

    1. Open [Azure portal](https://portal.azure.com/).
    2. Go to [All roles - Microsoft Azure](https://portal.azure.com/#view/Microsoft_AAD_IAM/AllRolesBlade).
    3. Search for **Global Administrator** or **Teams Administrator**.
    4. Click the role and select the **Active assignments** tab. A list of all users assigned with the role is displayed.
    5. Navigate to [Users - Microsoft Azure](https://portal.azure.com/#view/Microsoft_AAD_UsersAndTenants/UserManagementMenuBlade/%7E/AllUsers) and check for all users individually. If any user is disabled, enable them.
5. Once the admin approves the request, the teacher can start communicating with parents using the newly updated contact details.

Both SDS and manually supplied parent information are stored in the substrate eventually. However, before the parent data approval request submitted by the educator is approved, in the interim, the data will be stored in Approval’s store (Dataverse).

If your school uses both SDS and manual ingestion, you may want to note the following points:

1. Manually updated information for parent contact details doesn't update the SDS contact information. It also doesn't update or tamper with the information stored in the SIS your school is using.
2. If there's a change in the parent contact details in SDS and is also updated manually, the latest change is considered and stored in the final data storage of the substrate.
3. If a class teacher or class student is deleted, the parent contact information is **not deleted automatically**. To delete the contact information for parent, see Delete student information from the Dataverse. If a teacher leaves the school, the teacher's pending requests will still persist and can be approved or rejected by the admins.

### Disable manual update of parent contact information

If your school doesn't want to give educators the capability to manually update parent information, you can disable the same using the following steps. An educator can add or update the parents data via manual ingestion using an admin setting `UpdateParentInformation`. The default value for the setting is enabled. However, to disable the setting, the tenant admin should install the latest TPM version &gt; [6.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/6.1.0). Once the latest TPM version is installed, 

1. Check if the setting is enabled for you or not, by following these [steps](/en-us/powershell/module/teams/get-csteamseducationconfiguration). Note the value of the 'Identity' property. It's required when you update the setting.
2. To update the setting on behalf of your tenant, use this [link](/en-us/powershell/module/teams/set-csteamseducationconfiguration) and follow the examples of `UpdateParentInformation` setting.

#### Delete student information from the Dataverse

To delete student data stored in the Dataverse:

1. Sign in to https://make.powerapps.com.
2. In the left panel, navigate to **Tables** under **Data**.

    [![Screenshot of selecting tables from Power Automate.](media/delete-data-verse/delete-student-1.png)](media/delete-data-verse/delete-student-1.png#lightbox)
3. Under **Tables**, select the **All** tab, and then select the **Approval** table.

    [![Screenshot of Tables view.](media/delete-data-verse/delete-student-2.png)](media/delete-data-verse/delete-student-2.png#lightbox)
4. In the **Approvals** table, add the **Partner Id Hash** column.

    [![Screenshot of Approvals table.](media/delete-data-verse/delete-student-3.png)](media/delete-data-verse/delete-student-3.png#lightbox)
5. Select the **Partner Id Hash** dropdown and select **Filter by**.
6. In the **Filter by window**, enter **student object ID** in the field, and select **Apply**.

    [![Screenshot of student ID column.](media/delete-data-verse/delete-student-4.png)](media/delete-data-verse/delete-student-4.png#lightbox)
7. From the displayed list, select the rows of student data to be deleted.

    [![Screenshot of displayed data.](media/delete-data-verse/delete-student-5.png)](media/delete-data-verse/delete-student-5.png#lightbox)

For more questions, see https://aka.ms/parentFeedback.

### Teams admin center policies

- Class team owners must have Teams chat turned on.
- Class team owners must have external access with **Teams accounts not managed by an organization**turned on.
    - This must be turned on at the tenant level and the user level. The tenant-level setting can be found in **Users &gt; External Access** in the Teams admin center. This setting can also be accessed via PowerShell. User-level external access policies can only be accessed via PowerShell. For more information, see the PowerShell commands below.
- To allow meeting creation from the Parent Connection app, the following policies must be turned on:
    - [Allow private meeting scheduling](meeting-policies-in-teams#allow-scheduling-private-meetings).
    - [Allow anonymous users to join the meeting](meeting-policies-participants-and-guests#who-can-bypass-the-lobby).

#### Parent and guardian restrictions

Parents and guardians are classified as *external* in the Parents Connection, meaning they don't have full tenant rights. They only have access to the chat or chats they're a part of and the files, images, and other content shared in the chat.

For external chats, both internal and external people can add users to the chat. To learn more about the external chat experience, see [Manage external meetings and chat in Microsoft Teams](manage-external-access).

Also, external people can see the presence (offline, available, busy, etc.) of your organization's users, but this can be turned off using PowerShell to protect users' privacy. In PowerShell, use [Set-CsPrivacyConfiguration](/en-us/powershell/module/skype/set-csprivacyconfiguration) and set `EnablePrivacyMode=true`.

Even though parents and guardians are external, their contributions to chats are discoverable. Learn how to conduct a Teams eDiscovery investigation by reading [Conduct an eDiscovery investigation of content in Microsoft Teams](ediscovery-investigation).

Important

IT admins should educate all Class Owners on best practices for sharing student information over chat, including risks to student privacy.

#### Blocking a parent or guardian in a chat

Educators can block a guardian in chat initiated in the Parent Connection.

The class owner can:

1. Open the guardian's profile card, select the ellipse and **Block User**.
2. Then, remove the guardian from the chat.

The blocked user won't be able to start other chats with the class owner.

## Allow external access with Teams accounts not managed by an organization

To allow educators to communicate with parents and guardians in Teams, the education tenant's IT admin needs to update the tenant's policies to allow external access for Teams accounts outside of the tenant. For more information on managing external access, view [Manage external access in Microsoft Teams](manage-external-access).

Here are the steps to turn on external access for parents and guardians.

1. Install the latest Microsoft Teams PowerShell module here https://www.powershellgallery.com/packages/MicrosoftTeams.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
2. Using credentials that have admin privileges, run the following commands:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    The policy setting that turns on external access with Teams accounts not managed by an organization at the user level (`EnableTeamsConsumerAccess`) is turned on by default for all user-level external access policies. Both the tenant-level setting and the user-level policy setting need to be turned on for a user to have external access with Teams accounts not managed by an organization. If you don't want every user in your tenant to have this access turned on, you should ensure that your tenant-level setting is turned off, update the user-level external access policies assigned to your users, and then turn on the tenant-level setting.

    To check which user-level external access policies exist and who they're assigned to, you can use the following steps:
3. Check that user-level external access policies exist.

    ```powershell
    Get-CsExternalAccessPolicy
    ```
4. For each policy other than the 'Global' policy, check which users have the policy assigned.

    Note

    Any users who don't have a specific policy assigned will fall back to the 'Global' policy. Any new users who are added to the tenant will have the 'Global' policy assigned.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Since all user-level external access policies have `EnableTeamsConsumerAccess` set to true by default, if you would like to adjust the `EnableTeamsConsumerAccess` setting for specific users, you can create/modify existing external access policies with adjusted settings and/or reassign users to new or existing policies using the following PowerShell cmdlets:

- Create a new external access policy: [New-CsExternalAccessPolicy](/en-us/powershell/module/teams/new-csexternalaccesspolicy)
- Customize an existing external access policy (including the 'Global' policy): [Set-CsExternalAccessPolicy](/en-us/powershell/module/teams/set-csexternalaccesspolicy)

Note

The following subscription default policies can't be modified: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. The 'FederationAndPICDefault' policy used to be assigned to all users by default, however new users are now assigned the 'Global' policy by default. If you need to change the policy settings for users who have these subscription default policies assigned, assign different policies with the correct settings to these users.

- Assign an external access policy to a single user: [Grant-CsExternalAccessPolicy](/en-us/powershell/module/teams/grant-csexternalaccesspolicy)
- Assign a policy to a set of users: [New-CsBatchPolicyAssignmentOperation](/en-us/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Once the user-level external access policies are set correctly for the users in your tenant, you can turn on the tenant-level setting (`AllowTeamsConsumer`) for the tenant using the following cmdlet:

- Set the federation configuration settings for your tenant: [Set-CsTenantFederationConfiguration](/en-us/powershell/module/teams/set-cstenantfederationconfiguration)

## Set a preferred invitation channel

Note

Effective June 30, 2025, we'll retire the SMS invitation option in the Parents app. Educators will no longer be able to invite parents to a Microsoft Teams chat using a text message. Educators can continue to use email as the preferred method to invite parents to Teams chats.

Admins can choose either email or SMS as their preferred Parent Connection invitation channel.

Messages sent to parents and guardians will be in plain text, without HTML, formatting, or styles applied.

If you choose SMS as the preferred channel for sending Parent Connection invites to parents and guardians, know that:

- Parent and guardian phone numbers must be E.164 formatted for SMS invites and profile look-up to work.
- For example, format phone numbers as `+[country code][area code][phone number]`, like `+12223334444`.
- Mobile carrier SMS rates may be charged to parents and guardians who receive SMS invitations.

### Set a preferred invite channel in the Teams admin center

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Go to **Education** &gt; **Parent and guardian settings**.
3. In the **Preferred contact method** field, select either **Email** or **Mobile phone - SMS**.
4. Save your changes.

### Set a preferred invite channel using PowerShell

1. Install the *4.9.0 version or greater* of the Teams PowerShell module at https://www.powershellgallery.com/packages/MicrosoftTeams.
2. Run the command below and sign in with admin credentials.

    ```powershell
    Connect-MicrosoftTeams
    ```
3. Run the command below to view the current value for `ParentGuardianPreferredContactMethod`.

    ```powershell
    Get-CsTeamsEducationConfiguration
    ```
4. Run one of the commands below to change the value.

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod Email
    ```

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod SMS
    ```

## More information

- [CsExternalAccessPolicy](/en-us/powershell/module/teams/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/en-us/powershell/module/teams/set-cstenantfederationconfiguration)