---
layout: Conceptual
title: Public preview in Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/public-preview-doc-updates
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: article
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: shvarshney
ms.date: 2026-09-01T00:00:00.0000000Z
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn how to use public preview in Microsoft Teams to try out new features and provide feedback.
ms.localizationpriority: medium
locale: en-us
document_id: e5f1cdd1-09ff-f95d-6d50-e7880d34020f
document_version_independent_id: 59219640-305b-30c1-bc10-87e2633d95db
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/public-preview-doc-updates.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: public-preview-doc-updates
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/public-preview-doc-updates.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 27ab2226-ef09-d6e6-0300-f8210c222304
---

# Public preview in Microsoft Teams - Microsoft Teams | Microsoft Learn

Note

Features included in preview might not be complete and could undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. The preview features aren't supported in Office 365 Government Community Cloud (GCC).

Public preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public preview. The public preview feature is enabled per Team user, so you don't need to worry about this feature affecting your entire organization.

For a list of what's available in the Teams Public preview, visit [Microsoft Teams Public preview tech notes](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview).

Tip

As a companion to this article, we recommend using the [Microsoft Teams Setup Guide](https://go.microsoft.com/fwlink/?linkid=2270034) when signed in to the Microsoft 365 admin center. This guide customizes your experience based on your environment. To review best practices without signing in and activating automated setup features, go to the [Microsoft 365 setup portal](https://go.microsoft.com/fwlink/?linkid=2270204).

## Set the Update policy

Public preview is enabled on a per-user basis, and the option to turn on Public preview is controlled in an admin policy. Update policies are used to manage Teams and Office Preview users who see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't overwrite the global policy.

Important

Device policies are not applied in Teams web, so "On for users in Current Channel (Preview)" will be treated as "Off" in the web client.

1. Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).
2. Select **Teams** &gt; **Teams Update policies**.
3. Select an existing policy or select **Add** to create a new one.

    ![Screenshot of update policy panel in the Teams admin center.](media/new-update-policy.png)
4. Name the update policy and add a description.
5. Select the setting for **Show Teams preview features**:

    - **On for users in Current Channel (Preview)** (default)

        - This default option turns on Teams Public preview features for any user enrolled in Office Current Channel (Preview).
        - Users enrolled in Office Current Channel (Preview) can't turn off Teams Public preview.
    - **Users can opt in**

        - This option enables Teams Public preview regardless of whether a user is enrolled in Office Current Channel (Preview).
        - The users must turn on Teams Public preview in their Teams app because it isn't enabled by default for them.
    - **Off**

        - Teams Public preview features aren't available to users.
    - **On for everyone**

        - This option turns on Teams Public preview regardless of whether a user is enrolled in Office Current Channel (Preview).
        - Users can't turn off Teams Public preview.
6. Select **Apply**.

You can also set the policy using the PowerShell `Set-CsTeamsUpdateManagementPolicy` cmdlet.

## Enable Public preview

To enable Public preview on a desktop or web client, perform the following tasks:

Note

This option is only available when **Show Teams preview features** is set to **Users can opt in** or [Custom app upload](/en-us/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant#enable-custom-teams-apps-and-turn-on-custom-app-uploading) is enabled.

1. Select **Settings and more** (**...**) next to your user profile.
2. Select **Settings** &gt; **About Teams**.
3. Under **Early access**, select the **Public preview** checkbox.

Users who are in Teams client see early Access indicator under Settings -&gt; About Teams.

## Public preview for Microsoft Teams Rooms on Windows

Public preview is turned off by default. When Public preview is turned on, users have access to features that are in public preview on enabled Teams Rooms. To turn on Public preview, add `<EnablePublicPreview>True</EnablePublicPreview>` to your XML configuration file. For more information about the XML file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](/en-us/microsoftteams/rooms/xml-config-file).

We recommend enrolling 5-10 devices to public preview.

All public preview features are announced at [Microsoft Teams Public preview - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-teams-public-preview/bd-p/MicrosoftTeamsPublicPreview).