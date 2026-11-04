---
layout: Conceptual
title: Upgrade strategies for IT administrators - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/upgrade-to-teams-on-prem-implement
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: upgrade-and-migration-article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: bjwhalen
ms.date: 2020-07-23T00:00:00.0000000Z
description: The article is for IT administrators and describes strategies for implementing their upgrade from Skype for Business to Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
locale: en-us
document_id: e8d016d8-4eb4-13f7-9832-681f1d03756d
document_version_independent_id: 94e303d7-b21c-24f1-5487-ec4b6900ceec
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/upgrade-to-Teams-on-prem-implement.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: upgrade-to-teams-on-prem-implement
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/upgrade-to-Teams-on-prem-implement.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/74b1e9df-8124-4d0c-b310-50c3bf3ff02b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/7c78426a-2d2c-4bce-8e97-c1c9ab1c453e
platformId: 5085841f-1dc5-2dc9-8b96-092229d4af85
---

# Upgrade strategies for IT administrators - Microsoft Teams | Microsoft Learn

![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage.](media/upgrade-banner-deployment.png)

This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.

Before implementing your upgrade, we recommend the following articles, which describe important upgrade concepts and coexistence behaviors:

- [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability)
- [Coexistence modes - Reference](migration-interop-guidance-for-teams-with-skype)
- [Teams client experience and conformance to coexistence modes](teams-client-experience-and-conformance-to-coexistence-modes)

## Upgrade options

This section describes how to implement your upgrade by using one of the following upgrade options:

- Overlapping capabilities upgrade (using Islands mode)
- A select capabilities upgrade for an organization that hasn't yet started using Teams
- A select capabilities upgrade for an organization that is already using Teams in Islands mode

If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams).

## Overlapping capabilities upgrade (using Islands mode)

For the overlapping capabilities upgrade option:

- Consider this option if you can do a fast upgrade for your overall organization. Since there's potential risk of confusion for end users with running both clients, it's best if you can minimize the time period during which users must run both clients. You should ensure your users know to run both clients.
- This option is the out-of-the-box model, and doesn't require administrator action to get started with Teams except to assign the Teams license. If your users already are using Skype for Business Online, you may already be in this model.
- It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly. Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams. If you have users that haven't started using Teams, they are exposed to missing messages. Furthermore, they will not see the TeamsOnly users online in Skype for Business. Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.

## A select capabilities upgrade for an organization that has not yet started using Teams

If your organization doesn't yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab. Users who haven't yet started using Teams won't notice any difference in behavior. However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with nonupgraded users. Once you have identified your pilot users you can upgrade them to TeamsOnly. If they're on-premises, use Move-CsUser. If they're online, assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy. By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.

Following are the key commands:

1. Set the tenant-wide default to mode SfbWithTeamsCollab as follows:

    ```PowerShell
    Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
    ```
2. Upgrade the pilot users to TeamsOnly as follows:

    - For a user who is online:

        ```PowerShell
        Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
        ```
    - For a user who is on-premises:

        ```PowerShell
        Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
        ```

**Notes**:

- Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings. This causes all users to schedule all new meetings in Teams.
- By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.

Note

In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams. It is no longer required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises directly to TeamsOnly. Previously, if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged. Now when moving a user from on-premises to the cloud with `Move-CsUser`, users are automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified. This behavior is available on all versions of Skype For Business Server and Lync Server 2013 (which never had support for `-MoveToTeams`).

The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams. The height of the bars represents number of users. During any phase of the upgrade, all users can communicate with each other. Skype for Business users communicate with TeamsOnly users using Interop, and vice versa. Users in Islands mode must be sure to run both clients.

![Diagram showing select capabilities upgrade with no prior use of Teams.](media/teams-upgrade-1.png)

## A select capabilities upgrade for an organization that is already using Teams in Islands mode

If some users in your organization are actively using Teams in Islands mode, you probably don't want to remove functionality from existing users. Therefore, an extra step is required before changing the tenant-wide policy. The solution is to "grandfather" these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab. Once you are done that, you can proceed with deployment as above, however, you'll have two groups of users who are moving to TeamsOnly: the users who were active in Teams are in Islands mode, and the remaining users are in SfbWithTeamsCollab mode. You can progressively move these users to TeamsOnly mode.

1. Find users who are active in Teams as follows:

    1. From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.
    2. In the "Select a report" dropdown, choose Microsoft Teams, and then User Activity. This provides an exportable table of users who have been active in Teams.
    3. Select Export, open Excel, and filter to show only the users who are active in Teams.
2. For each active Teams user found in step 1, assign them Islands mode in remote PowerShell. This allows you to go to the next step, and ensures you don't change the user experience.

    ```PowerShell
    $users=get-content "C:\MyPath\users.txt"
     foreach ($user in $users){
     Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
    ```
3. Set the tenant-wide policy to SfbWithTeamsCollab:

    ```PowerShell
    Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
    ```
4. Upgrade selected users to TeamsOnly mode. You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.

    For users homed in Skype for Business Online:

    ```PowerShell
    Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
    ```

    For users homed in Skype for Business Server on-premises:

    ```PowerShell
    Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
    ```

The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start. The height of the bars represents the number of users. During any phase of the upgrade, all users can communicate with each other. Skype for Business users communicate with TeamsOnly users using interop, and vice versa.

![Diagram showing select capabilities upgrade with active users in Islands mode.](media/teams-upgrade-2.png)

## Related links

[Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype)

[Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](/en-us/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Move users between on-premises and cloud](/en-us/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings)

[Grant-CsTeamsUpgradePolicy](/en-us/powershell/module/teams/grant-csteamsupgradepolicy)

[Using the Meeting Migration Service (MMS)](/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)