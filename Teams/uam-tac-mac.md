---
layout: Conceptual
title: Unified agent and app availability management across Microsoft 365 and Teams Admin Centers - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/uam-tac-mac
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: vikasalmal0201
ms.author: vikasalmal
manager: prkosh
ms.topic: how-to
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- m365initiative-voice
- M365-collaboration
- Tier1
search.appverid: 
ms.date: 2026-04-14T00:00:00.0000000Z
ms.reviewer: shrutidhir
description: Streamline agent and app availability across Teams, Outlook, and Microsoft Copilot
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.custom: seo-marvel-apr2020
locale: en-us
document_id: e094d5e2-dec8-a9ca-f2a3-a273e4273141
document_version_independent_id: e094d5e2-dec8-a9ca-f2a3-a273e4273141
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/uam-tac-mac.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: uam-tac-mac
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/uam-tac-mac.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/68e4b2d8-b70c-4019-b49a-d1f8881e2aea
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/67b2ba1a-6f74-4044-a48a-f0f8ad076b8f
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: c78db376-5c9c-0078-27d8-7a9b4c87cea3
---

# Unified agent and app availability management across Microsoft 365 and Teams Admin Centers - Microsoft Teams | Microsoft Learn

Unified agent and app management helps you unify agents, apps availability across Teams admin center (TAC) and Microsoft 365 admin center (MAC). After your tenant is unified, all changes to org-wide settings, agent app, status, or availability in TAC are automatically synchronized in MAC and vice versa. This unification:

- Ensures org-wide defaults for both admin centers are in sync and governs app availability across Teams, Outlook, and Microsoft Copilot apps
- Ensures consistent and synchronized agent and app behavior across platforms, as changes to app availability settings in one admin center are automatically synced with the other
- Avoids mismatched configurations
- Streamlines governance and improves app management efficiency

Important

- For timelines, see Microsoft 365 Roadmap ID [485712.](https://www.microsoft.com/en-in/microsoft-365/roadmap?filters=&amp;searchterms=485712)
- For more information, see the Message Center Post [MC796790](https://admin.cloud.microsoft/?source=applauncher&amp;ref=MessageCenter/:/messages/MC796790).

Depending on the app availability status across TAC or MAC, you can unify your tenant's agent or app settings, based on either of the two configuration scenarios:

- Tenant with default settings in the admin center
- Tenant with modified settings in the admin center

## Tenant with default settings in the admin center

If your tenant never modified its org-wide defaults, app availability, or app block or unblock settings in either TAC or MAC, then your tenant's app availability policies are automatically unified. To learn more, follow these steps:

1. Sign in to [Teams admin center](https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=2ddfbe71-ed12-4123-b99b-d5fc8a062a79&amp;redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com%2fsignin-oidc&amp;response_type=code+id_token&amp;scope=openid+profile&amp;response_mode=form_post&amp;nonce=638917658808672430.YWRiYzMxZGItZjEzNC00NWI3LWJiYzEtNWY4NzZkODIyYWY2NGRjMzExMmEtNmIzNS00ODUzLTljNjYtZTM4NTQyNGIyN2U4&amp;post_logout_redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com&amp;msafed=0&amp;state=CfDJ8IHoJtwqQy9LlMNbw5zXYQhIf4GeP5tAJy87P-1rWtCUKdBuDZv0d5_iEc4tXqKavemC71QDLfznNlzL7Cnp7glApqFO9WBHkOLTvs9hTN3WCnysRBqygBnOp1iDtx_IjqNXxS8sBksi61bg2O8OBStOzw7BIH8fTF-JfbLH99OYna3UEUAJlAwhnqIWZhifubxj-jP9pz3A00vbtdNxOkz1f_jPlV8pNMuDlGh2pG3KIsKOQWRm80pDqmZG35FYXHVoyoPDNpWX4lisjZIFNag0gi5YCM5GmU7DydmIx96fDbcOciqeYxLF2t5EgnZ-177bfvEEFu7gS_lekvPqAaorvTnN6h2Hzl2ACgVc_plpIDiHQAHzb0YkAbGlNUbwlw&amp;x-client-SKU=ID_NET8_0&amp;x-client-ver=8.5.0.0&amp;sso_nonce=AwABEgEAAAADAOz_BQD0__1wpMWjufmyGkDH4GfzvQ4v-3Qrr5oR_7Roaasgh0cU3usNuIyMYV_sI4mfF88fPF8jL8ZPfH0qp7qgCr5M57UgAA&amp;client-request-id=118a4361-3ebe-4a41-ab17-0c7552b1c7dc&amp;mscrid=118a4361-3ebe-4a41-ab17-0c7552b1c7dc).
2. Go to **Teams apps** &gt; **Manage apps** to explore the unified agent and app management experience.

    [![Screenshot shows the default phase and no action required from admins.](media/default-tenants-phase-updated.png)](media/default-tenants-phase-updated.png#lightbox)

## Tenant with modified settings in the admin center

If your tenant's org-wide default settings, app availability, or app block and unblock settings in either TAC or MAC are previously modified, then you can unify your tenant's agent or app settings, via either of the following two configurations:

- Tenants with custom app changes but no availability differences across admin centers
- Tenants with custom app changes and availability differences across admin centers

After unification, changes made to the app status, org-wide settings, and user assignment in either admin center are synchronized in the other.

### Tenants with custom app changes but no availability differences across admin centers

If your tenant has custom app changes but no differences in app availability:

1. Go to **Teams apps** &gt; **Manage apps**.
2. Select **Move to unified app management**. A dialog box appears to ask for your consent to move to the unified agent and app management experience.

    [![Screenshot shows the default consent screen of the unified-app-management-experience on the Manage Apps homepage.](media/unified-app-management-experience-default-consent.png)](media/unified-app-management-experience-default-consent.png#lightbox)

    Important

    Only a Global admin can give consent and apply the final changes.

### Tenants with custom app changes and availability differences across admin centers

If your tenant has agent and app availability differences across MAC & TAC, then follow the steps to resolve differences:

1. Go to [Teams admin center](https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=2ddfbe71-ed12-4123-b99b-d5fc8a062a79&amp;redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com%2fsignin-oidc&amp;response_type=code+id_token&amp;scope=openid+profile&amp;response_mode=form_post&amp;nonce=638917658808672430.YWRiYzMxZGItZjEzNC00NWI3LWJiYzEtNWY4NzZkODIyYWY2NGRjMzExMmEtNmIzNS00ODUzLTljNjYtZTM4NTQyNGIyN2U4&amp;post_logout_redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com&amp;msafed=0&amp;state=CfDJ8IHoJtwqQy9LlMNbw5zXYQhIf4GeP5tAJy87P-1rWtCUKdBuDZv0d5_iEc4tXqKavemC71QDLfznNlzL7Cnp7glApqFO9WBHkOLTvs9hTN3WCnysRBqygBnOp1iDtx_IjqNXxS8sBksi61bg2O8OBStOzw7BIH8fTF-JfbLH99OYna3UEUAJlAwhnqIWZhifubxj-jP9pz3A00vbtdNxOkz1f_jPlV8pNMuDlGh2pG3KIsKOQWRm80pDqmZG35FYXHVoyoPDNpWX4lisjZIFNag0gi5YCM5GmU7DydmIx96fDbcOciqeYxLF2t5EgnZ-177bfvEEFu7gS_lekvPqAaorvTnN6h2Hzl2ACgVc_plpIDiHQAHzb0YkAbGlNUbwlw&amp;x-client-SKU=ID_NET8_0&amp;x-client-ver=8.5.0.0&amp;sso_nonce=AwABEgEAAAADAOz_BQD0__1wpMWjufmyGkDH4GfzvQ4v-3Qrr5oR_7Roaasgh0cU3usNuIyMYV_sI4mfF88fPF8jL8ZPfH0qp7qgCr5M57UgAA&amp;client-request-id=118a4361-3ebe-4a41-ab17-0c7552b1c7dc&amp;mscrid=118a4361-3ebe-4a41-ab17-0c7552b1c7dc).
2. Go to **Teams apps** &gt; **Manage apps**. The **Manage apps** page appears.

    [![Screenshot shows the move to unified app management banner on the Manage apps homepage.](media/manage-apps-banner.png)](media/resolve-org-wide-settings-unified-app-management.png#lightbox)
3. Select **Move to unified app management**. The **Align org-wide app settings** page appears. Here you can select the org-wide default settings that you want to apply across TAC and MAC.

    [![Screenshot shows align org-wide app settings on the Manage apps homepage.](media/resolve-org-wide-settings-unified-app-management.png)](media/resolve-org-wide-settings-unified-app-management.png#lightbox)
4. Apply settings from the drop-down list, to resolve any setting differences.
5. Select **Next** after you decide the relevant selections on the screen, to see all apps that have different availability policies across both the admin centers. You can resolve all differences in app availability and **Align app-level settings** in the following three ways:

    [![Screenshot shows the individual app level settings under align app-level settings.](media/individual-app-alignment.png)](media/individual-app-alignment.png#lightbox)

    - Individual app-alignment: Select any individual app and review the **App status** and **Availability**. Go to Review settings for the selected app to check the App status and Availability. Select the admin center’s settings that you want to apply from the **Apply settings from** drop-down list and select **Apply settings**.

        [![Screenshot shows the individual app level settings under review settings.](media/review-settings-apply.png)](media/review-settings-apply.png#lightbox)
    - Bulk app resolution: Select multiple apps at a time and select either Teams admin center or Microsoft 365 admin center from the **Apply settings from** drop-down list. Use this setting to apply changes in bulk across all apps from either one of the admin centers.

        [![Screenshot shows the bulk app level settings under align app-level settings.](media/bulk-app-availability-excel-settings.png)](media/bulk-app-availability-excel-settings.png#lightbox)
    - Download the CSV file: Select the Excel icon in the top-right corner to download the App status and Availability settings as a CSV file.

        [![Screenshot shows the export to csv icon to download the offline report under align app-level settings.](media/export-to-csv-app-alignment.png)](media/export-to-csv-app-alignment.png#lightbox)
6. Select **Next** after resolving all differences in the app availability. The **Review summary** page appears, where you can review all changes made. Select **Apply changes**, as shown:

    [![Screenshot shows the review summary page with Org-wide app settings and App-level settings.](media/review-summary-settings.png)](media/review-summary-settings.png#lightbox)

    Note

    Any Teams or Global admin can make updates upto the **Review summary** page.
7. Provide consent in the consent box to move to the unified state and select **Accept and finish**.

    [![Screenshot shows the pop-up box to provide consent to move to the unified state.](media/consent-movement-unified-app-management.png)](media/consent-movement-unified-app-management.png#lightbox)

    Important

    **Only a Global admin can give consent and apply the final changes.**

    All the aligned app settings are now applied. With unified agent app management, you can now manage agents and apps via the Teams admin center or Integrated apps page in the Microsoft 365 admin center. Any changes made in either admin center are automatically synchronized.

### Manage apps in TAC and MAC

After your organization is migrated to unified agent or app management, you can go to either of the following admin centers:

- TAC: Manage agents and apps via [app centric management](app-centric-management)
- MAC: Manage agents and apps via [agents or apps](/en-us/microsoft-365/admin/manage/teams-apps-work-on-outlook-and-m365?view=o365-worldwide&amp;preserve-view=true)

Your changes in TAC are synchronized in MAC too.

## View top apps in tenants with unified agents and apps

After your tenant is migrated to the unified agents and apps experience, you can see the **Popular apps in your org** widget on the **Manage apps** page. With this widget, you can see two of the most-used third-party apps that your users use the most, that aren't already installed for everyone in the organization. These apps are in the top 40% of usage in the last 90 days and are displayed in descending order by usage.

You can analyze the apps usage and install them for selected users or everyone in the organization, to increase adoption.

To view the **Popular apps in your org** widget and analyze two of the most-used third-party apps:

1. Sign in to [Teams admin center](https://login.microsoftonline.com/common/oauth2/v2.0/authorize?client_id=2ddfbe71-ed12-4123-b99b-d5fc8a062a79&amp;redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com%2fsignin-oidc&amp;response_type=code+id_token&amp;scope=openid+profile&amp;response_mode=form_post&amp;nonce=638917658808672430.YWRiYzMxZGItZjEzNC00NWI3LWJiYzEtNWY4NzZkODIyYWY2NGRjMzExMmEtNmIzNS00ODUzLTljNjYtZTM4NTQyNGIyN2U4&amp;post_logout_redirect_uri=https%3a%2f%2fadmin.teams.microsoft.com&amp;msafed=0&amp;state=CfDJ8IHoJtwqQy9LlMNbw5zXYQhIf4GeP5tAJy87P-1rWtCUKdBuDZv0d5_iEc4tXqKavemC71QDLfznNlzL7Cnp7glApqFO9WBHkOLTvs9hTN3WCnysRBqygBnOp1iDtx_IjqNXxS8sBksi61bg2O8OBStOzw7BIH8fTF-JfbLH99OYna3UEUAJlAwhnqIWZhifubxj-jP9pz3A00vbtdNxOkz1f_jPlV8pNMuDlGh2pG3KIsKOQWRm80pDqmZG35FYXHVoyoPDNpWX4lisjZIFNag0gi5YCM5GmU7DydmIx96fDbcOciqeYxLF2t5EgnZ-177bfvEEFu7gS_lekvPqAaorvTnN6h2Hzl2ACgVc_plpIDiHQAHzb0YkAbGlNUbwlw&amp;x-client-SKU=ID_NET8_0&amp;x-client-ver=8.5.0.0&amp;sso_nonce=AwABEgEAAAADAOz_BQD0__1wpMWjufmyGkDH4GfzvQ4v-3Qrr5oR_7Roaasgh0cU3usNuIyMYV_sI4mfF88fPF8jL8ZPfH0qp7qgCr5M57UgAA&amp;client-request-id=118a4361-3ebe-4a41-ab17-0c7552b1c7dc&amp;mscrid=118a4361-3ebe-4a41-ab17-0c7552b1c7dc).
2. Go to **Teams apps** &gt; **Manage apps** to view the **Popular apps in your org** widget. It shows two of the most-used third-party apps in your organization based on random selection, the number of users using the app, and the **Install for others** option.

    [![Screenshot showing the widget on the Manage apps page for unified tenants.](media/top-apps-widget-manage-apps-unified.png)](media/top-apps-widget-manage-apps-unified.png#lightbox)
3. *Optional*: Select the **information** icon on the widget and choose the **Apps usage report** link.

    [![Screenshot showing the Apps usage report link.](media/apps-usage-reports-unified-widget.png)](media/apps-usage-reports-unified-widget.png#lightbox)

    The **Usage reports** page opens and automatically generates a report for all the third-party apps, including two of the most-used apps shown on the widget, as per usage in the last 90 days.

    [![Screenshot showing analytical report on apps usage for all the apps.](media/apps-usage-report-analytics.png)](media/apps-usage-report-analytics.png#lightbox)

    Important

    The **Usage reports** data is sourced from the `Ideas`API and covers app usage beyond Teams.
4. Select **Install for others** on the widget.

    [![Screenshot showing the install for others option for unified tenants.](media/unified-install-for-others-option.png)](media/unified-install-for-others-option.png#lightbox)

    The **Users and groups** tab opens, which shows the actual number of users for whom the selected app is installed. Select **Edit installs** to install the app for selected users or install it for everyone to increase adoption.

    [![Screenshot showing the users and groups for unified tenants.](media/unified-users-and-groups.png)](media/unified-users-and-groups.png#lightbox)

    Alternatively, go to the **Dashboard** in Teams admin center to view the widget that shows three of the most-used apps. These apps on the widget match those apps on the **Manage apps** page and appear in the same order, except for the third app. Select **Install** to open the **Users and groups** tab, where you can view and analyze the number of users for whom the app is installed and edit the installation accordingly.

[![Screenshot showing the widget on the dashboard for tenants with unified agents and.](media/dashboard-top-apps-unified.png)](media/dashboard-top-apps-unified.png#lightbox)