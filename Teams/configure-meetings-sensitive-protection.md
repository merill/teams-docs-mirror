---
layout: Conceptual
title: Configure Teams meetings with protection for sensitive data - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/configure-meetings-sensitive-protection
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: yilin.yang
ms.date: 2024-12-13T00:00:00.0000000Z
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
- Tier1
description: Learn how to configure Teams meetings for protection for sensitive information by using templates and sensitivity labels.
locale: en-us
document_id: 058bf83d-0bff-bf14-89a2-41cb5d76ede6
document_version_independent_id: 058bf83d-0bff-bf14-89a2-41cb5d76ede6
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/configure-meetings-sensitive-protection.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: configure-meetings-sensitive-protection
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/configure-meetings-sensitive-protection.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 649978a7-25d6-f780-a16d-c6792e2c31e7
---

# Configure Teams meetings with protection for sensitive data - Microsoft Teams | Microsoft Learn

![Information icon.](media/info.png)**Some features described in this article require [Teams Premium](/en-us/MicrosoftTeams/enhanced-teams-experience).**

For the *sensitive* level of protection, we restrict who can bypass the lobby, who can present, and who can record. You can restrict other actions as well if your organization requires it.

The following table describes which actions we restrict for sensitive meetings and where those options are configured.

| Feature | Option | Location | Enforced |
| --- | --- | --- | --- |
| Allow camera for attendees | **On** | Template | No |
| Allow mic for attendees | **On** | Template | No |
| Apply a watermark to everyone's video feed | **Off** | Template | No |
| Apply a watermark to shared content | **Off** | Template | No |
| End-to-end encryption | **Off** | Template | No |
| Detect sensitive content during screen sharing | **Off** | Template | No |
| Manage what attendees see | **On** | Template | Yes |
| Meeting chat | **On** | Template | No |
| People dialing in can bypass the lobby | **Off** | Label | Yes |
| Prevent copying chat content to clipboard | **Off** | Label | No |
| Record automatically | **Off** | Template | No |
| Who can bypass the lobby? | **People who were invited** | Label | Yes |
| Who can present | **People in my org and guests** | Label | Yes |
| Who can record | **Organizer and co-organizers** | Label | Yes |

Note

You can also automatically apply or recommend that the meeting is labeled with the highest priority sensitivity label from files shared for the meeting.

The sensitivity label or meeting template enforces options that are listed as enforced. The meeting organizer can change Options that aren't enforced. To learn more about how your users can apply sensitivity labels to their meetings, see [Sensitivity labels for Teams meetings](https://support.microsoft.com/office/sensitivity-labels-for-teams-meetings-2b244d1d-72d0-471e-8e58-c41079e190fb).

Note

Meeting options in sensitivity labels and custom meeting templates require Teams Premium.

## Video demonstration

Watch this video for a walkthrough of the procedures described in this article. 

## Presentation options for sensitive meetings

For the *sensitive* level of protection, we enforce specific options for who can present, and how content is shared.

By turning on **Manage what attendees can see**, we ensure that meeting organizers can vet shared content before it's brought on screen for participants. In this example, we're using a template to turn this on by default, but you can also use the template to enforce the value if you need to.

By setting **Who can present** to **People in my organization and guests** in the sensitivity label, we remove the chance of anonymous participants presenting in the meeting. You can further restrict this to **Only organizers and co-organizers** if you need to. (We do that for the *highly sensitive* level of protection.)

We also restrict recording to organizer and co-organizers by using the sensitivity label.

## Lobby options for sensitive meetings

We use the sensitivity label to prevent anyone other than invited attendees (people directly invited by the organizer, or to whom an invitation was forwarded) from bypassing the lobby. This gives an extra level of protection by letting the organizer vet anyone not directly sent an invite before admitting them to the meeting. You can further restrict this option by choosing **Only organizers and co-organizers**. (We do that for the *highly sensitive* level of protection.)

## Sensitivity labels

For the sensitive level of protection, we use a sensitivity label that you can use directly in a meeting or as part of a meeting template. Depending on the configuration you choose, this label can also be used to classify teams and individual files.

If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy. You can change the name or settings if needed to meet the needs of your organization. If you already have a label that you use for sensitive information, you can edit the label and add Teams meetings to it.

1. Open the [Microsoft Purview portal](https://purview.microsoft.com).
2. Under **Solutions**, expand **Information protection**, and then select **Labels**.
3. Select **Create a label**.
4. Give the label a name. We suggest **Sensitive**, but you can choose a different name if **Sensitive** is already taken.
5. Add a display name and description, and then select **Next**.
6. On the **Define the scope for this label** page, make sure **Files & other data assets**, **Emails**, and **Meetings** are selected. You can select other options if you want to use this label for other purposes.
7. Select **Next**.
8. On the **Choose protection settings for types of items you selected** page, select **Protect Teams meetings and chats**, and then select **Next**.
9. On the **Settings for Teams meetings and chats** page, choose the following values:

    1. Select **Control who can bypass the lobby** and choose **People who were invited** from the dropdown list.
    2. Clear the **People dialing in can bypass the lobby** check box.
    3. Select **Control who can present** and choose **People in my org and guests** from the dropdown list.
    4. Select **Control who can record and transcribe** and choose **Organizers and co-organizers** from the dropdown list.
    5. Configure any other settings that you need for your organization.

        ![Screenshot of meeting sensitivity label settings showing configuration in this procedure.](media/teams-meeting-sensitivity-label-sensitive-small.png)
10. Select **Next**.
11. Complete the wizard with any other settings you want to use, select **Create label**, and then select **Done**.

Once you create the label, you need to publish it to the users who will use it. For sensitive protection, we make the label available to all users. You publish the label in the Microsoft Purview portal, on the **Label policies** page under **Information protection**. If you have an existing policy that applies to all users, add this label to that policy. If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](/en-us/purview/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

For more information about using sensitivity labels with meetings, see [Use sensitivity labels to protect calendar items, Teams meetings, and chat](/en-us/purview/sensitivity-labels-meetings).

## Meeting templates

An advantage of using templates is that you can create multiple templates that use the same sensitivity label but which lock different options. For example, for sensitive presentations with minimal attendee interaction, create a template that turns off attendee video and chat, and another template that lets the meeting organizer decide on these options. Both templates would use the *Sensitive* label.

In the *sensitive* level of protection, we use the template to set **Manage what attendees see** to **On** and enforce that value. (This option isn't available in sensitivity labels.) This allows the meeting organizer to manage how content is shown to meeting participants. If there are certain types of meetings where you want to allow the organizer to change this option, consider using a separate template with the same label for those meetings.

To create a custom meeting template

1. In the Teams admin center, expand **Meetings** and select **Meeting templates**.
2. Select **Add**
3. Type a name and description for the template.
4. In the **Apply sensitivity label** section, choose the label you created above.
5. Select **Apply sensitivity label**, and then select **Lock**.
6. Under **Meeting engagement**, set **Manage what attendees see** to **On**, then select it and select **Lock**.
7. Change any other options if desired.
8. To prevent the meeting organizer from changing an option, select the option and then select **lock**.
9. To prevent the meeting organizer from seeing an option, select the option and then select **Hide**.
10. Select **Save**.