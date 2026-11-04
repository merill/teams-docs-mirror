---
layout: Conceptual
title: Install Moodle integration with Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/install-moodle-integration
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: integration
ms.service: msteams
ms.subservice: teams-education
audience: admin
ms.reviewer: 
ms.date: 2026-07-08T00:00:00.0000000Z
search.appverid: MET150
description: Learn how to install and configure the Moodle open-source Learning Management System (LMS) app for Microsoft Teams.
keywords: Teams Moodle app integration plugin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- tier2
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
locale: en-us
document_id: 66c68e6d-936e-68f0-7405-d1e0fec62670
document_version_independent_id: f954014f-8c01-08fa-9afb-476feeb346b2
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/install-moodle-integration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: install-moodle-integration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/install-moodle-integration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/6ab06385-661e-4214-8870-bbe4071c960d
- https://authoring-docs-microsoft.poolparty.biz/devrel/1dd701e0-441f-4b0a-9806-aa47decc4e35
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/131ba09e-4280-4ae7-8622-1f9f1c0daad1
- https://authoring-docs-microsoft.poolparty.biz/devrel/0a2fc935-5977-4aa6-9f55-0be03bd2acb8
platformId: 2144fe8f-4bd8-d8f5-d088-a5fdc38ca693
---

# Install Moodle integration with Microsoft Teams - Microsoft Teams | Microsoft Learn

[Moodle](https://moodle.org/), the most popular and open-source Learning Management System (LMS) in the world, is now integrated with Microsoft Teams! This integration helps teachers and students collaborate around Moodle courses, ask questions about their grades and assignments and stay updated with notifications--right within Teams!

To help IT admins easily set this integration, we have updated our open-source Moodle Plugin with the following capabilities:

- Autoregistration of your Moodle server with Microsoft Entra ID.
- One-click deployment of your Moodle Assistant bot to Azure.
- Autoprovisioning of teams and autosynchronization of team enrollments for all or select Moodle courses.
- Autoinstallation of the Moodle tab and the Moodle Assistant bot into each synchronized team. (Coming soon)
- One-click publishing of the Moodle app into your private Teams App Store. (Coming soon)

To learn more about the functionality this integration provides, see [Installing the Moodle integration with Microsoft Teams](/en-us/microsoftteams/platform/resources/moodleinstructions).

## Prerequisites

In order to install and configure this application, you'll need:

1. Moodle administrator credentials
2. Microsoft Entra administrator credentials
3. An Azure subscription you can create new resources in

## Step 1: Install the Moodle Plugin

The Moodle integration in Microsoft Teams is powered by the open source [Moodle plugin set](https://github.com/Microsoft/o365-moodle). To install the plugin in your Moodle server:

1. First, download the [Moodle plugin set](https://moodle.org/plugins/pluginversions.php?plugin=local_o365)and save it to your local computer. You'll need to use version 3.5 or newer.
    - Installing the local\_o365 plugin will also install the [auth_oidc](https://moodle.org/plugins/auth_oidc) and [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) plugins.
2. Sign in to your Moodle server as an administrator, and select **Site administration** from the left navigation panel.
3. Select the **Plugins** tab, and then select **Install plugins**.
4. Under the Install plugin from ZIP file section, select the **Choose a file** button.
5. Select the **Upload a file** option from the left navigation, browse for the file you downloaded above and select **Upload this file**.
6. Select the **Site administration** option from the left navigation panel again to return to your admin dashboard. Scroll down to the **Local plugins** and select the **Microsoft Office 365 Integration** link. Keep this configuration page open in a separate browser tab as you'll be using it throughout the rest of this process.

You can find more information on how to install Moodle plugins in the [Moodle documentation](https://docs.moodle.org/34/en/Installing_plugins).

**Important Note:** Keep your Microsoft 365 or Office 365 Moodle Plugin configuration page open in a separate browser tab as you'll be returning to this set of pages throughout this process.

*Don't have a Moodle site already?* You might want to check out our Moodle on Azure [repo](https://github.com/azure/moodle) where you can quickly deploy a Moodle instance on Azure and customize it to your needs.

## Step 2: Configure the connection between the Microsoft 365 or Office 365 plugin and Microsoft Entra ID

Next you'll need to register Moodle as an application in your Microsoft Entra ID. We've provided a PowerShell script to help you complete this process. The PowerShell Script provisions a new Microsoft Entra application for your Microsoft 365 or Office 365 organization, which will be used by the Moodle Plugin. The script will provision the app for your Microsoft 365 or Office 365 tenant, set up all the required Reply URLs and Permissions for the provisioned app and return the AppID and Key. You can use the generated AppID and Key in your Moodle Plugin Setup Page to configure your Moodle server with Microsoft Entra ID. If you want to see the detailed manual steps that the PowerShell script is automating, you can find them in the full [documentation for the plugin](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### Moodle tab for Microsoft Teams information flow
![Illustration of Moodle tab for Microsoft Teams information flow](media/moodletabinformationflow.png)
1. From the Microsoft 365 or Office 365 Integration plugin page, select the **Setup** tab.
2. Select the **Download PowerShell Script** button and save it to your local computer.
3. You'll need to prepare the PowerShell script from the ZIP file. To do so:
    - Download and extract the `Moodle-AzureAD-Powershell.zip` file.
    - Open the extracted folder.
    - Right-click on the `Moodle-AzureAD-Script.ps1` file and select **Properties**.
    - Under the **General** tab of the Properties window, check the `Unblock` box next to the **Security** attribute at the bottom.
    - Select **OK**.
    - Copy the directory path of the extracted folder.
4. Next you'll run PowerShell as an administrator:
    - Select Start.
    - Type PowerShell.
    - Right-click Windows PowerShell.
    - Select "Run as Administrator".
5. Navigate to the unzipped directory by typing `cd ...\...\Moodle-AzureAD-Powershell` where `...\...` is the path to the directory.
6. Execute the PowerShell script by:
    - Enter `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    - Enter `.\Moodle-AzureAD-Script.ps1`.
    - Log in to your Microsoft 365 or Office 365 Administrator account in the pop-up window.
    - Enter the name of the Microsoft Entra Application (Ex. Moodle/Moodle plugin).
    - Enter the URL of your Moodle server.
    - Copy the **Application ID** and **Application Key** generated by the script and save them.
7. Next you'll need to add the ID and Key to the Moodle Plugin. Return to the plugin administration page (Site administration &gt; Plugins &gt; Microsoft 365 Integration).
8. On the Setup tab, add the **Application Id** and **Application Key** you copied previously, then select **Save changes**.
9. Once the page refreshes you should now see a new section **Choose connection method**. Select the checkbox labeled **Default** and then select **Save changes** again.
10. Once the page refreshes you'll see another new section **Admin consent & additional information**.
    - Select the **Provide Admin Consent** link, enter your Microsoft 365 or Office 365 Global Administrator credentials, then **Accept** to grant the permissions.
    - Next to the **Microsoft Entra tenant** field select the **Detect** button.
    - Next to the **OneDrive for Business URL** select the **Detect** button.
    - Once the fields populate, select the **Save changes** button again.
11. Select the **Update** button to verify the installation, then **Save changes**.
12. Next you'll need to synchronize users between your Moodle server and Microsoft Entra ID. Depending on your environment, you may select different options during this stage. The configuration you set here will run with each Moodle cron run (typically once a day) to keep everything in sync. To get started:
    - Switch to the **Sync Settings tab**
    - In the **Sync users with Microsoft Entra ID**section, select the checkboxes that apply to your environment. Typically you would select at least:
        - Create accounts in Moodle for users in Microsoft Entra ID
        - Update all accounts in Moodle for users in Microsoft Entra ID
    - In the **User Creation Restriction** section you can set up a filter to limit the Microsoft Entra users that will be synced to Moodle.
    - The **User Field Mapping** section will allow you to customize the Microsoft Entra ID to Moodle User Profile field mapping.
    - In the **Teams Sync** section you can choose to automatically create Groups (that is, Teams) for some, or all, of your existing Moodle courses.
13. To validate the cron jobs (and run them manually if you wish to for the first run) select the **Scheduled tasks management page** link in the **Sync users with Microsoft Entra ID** section. This will take you to the **Scheduled Tasks**page.
    - Scroll down and find the job **Sync users with Microsoft Entra ID** job and select **Run now**.
    - If you chose to create Groups based on existing courses, you can also run the **Create user groups in Office 365** job.
14. Return to the plugin administration page (Site administration &gt; Plugins &gt; Microsoft 365 Integration) and select the **Teams Settings**page. You'll need to configure some security settings to enable the Teams app integration.
    - To enable OpenID Connect, click the **Manage Authentication** link, and click the eye icon on the **OpenId Connect** line if it's greyed out.
    - Next you'll need to enable frame embedding. Select the **HTTP Security** link, then select the checkbox next to **Allow frame embedding**.
    - The next step is to enable web services, which will enable the Moodle API features. Click the **Advanced Features** link, then make sure the checkbox next to **Enable web services** is checked.
    - Finally you'll need to enable the external services for Microsoft 365 or Office 365. Click the **External services**link then:
        - Click **Edit** on the **Moodle Office 365 Webservices** row.
        - Mark the checkbox next to **Enabled**, then click **Save Changes**
    - Next you'll need to edit your authenticated user permissions to allow them to create web service tokens. Click the **Editing role 'Authenticated user'** link. Scroll down and find the **Create a web service token** capability and mark the **Allow** checkbox.

## Step 3: Deploy the Moodle Assistant Bot to Azure

The free Moodle Assistant Bot for Microsoft Teams helps teachers and students answer questions about their courses, assignments, grades, and other information in Moodle. The bot also sends Moodle notifications to students and teachers right within Teams. This bot is an open source project maintained by Microsoft, and is [available on GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

Note

In this section you will deploy resources to your Azure subscription, and all resources will be configured using the **free** tier. Depending on the usage of your bot, you may need to scale these resources. If you want to just use the Moodle tab without the bot, skip to step 4.

### Moodle bot information flow
![llustration of Moodle bot for Microsoft Teams information flow](media/moodlebotinformationflow.png)
To install the bot, you'll first need to register it on the [Microsoft identity platform](https://identity.microsoft.com/Landing). This allows your Bot to authenticate against your Microsoft endpoints. To register your bot:

1. Return to the plugin administration page (Site administration &gt; Plugins &gt; Microsoft 365 Integration) and select the **Teams Settings** tab.
2. Click the **Microsoft Application Registration Portal** link and login with your Microsoft ID.
3. Enter a name for your app (For example MoodleBot) and click the **Create** button.
4. Copy the **Application Id** and paste it into the **Bot Application ID** field on the **Team Settings** page.
5. Click the **Generate New Password** button. Copy the generated password and paste it into the **Bot Application Password** field on the **Team Settings** page.
6. Scroll to the bottom of the form and click **Save Changes**.

Now that you've generated your Application ID and Password, it's time to deploy your bot to Azure. Click on the **Deploy to Azure** button and fill out the form with the necessary information (the Bot Application ID, Bot Application Password and the Moodle Secret are on the **Team Settings** page, and the Azure information is on the **Setup** page). Once you've got the form filled out, click the check box to agree to the terms and conditions then click the **Purchase** button (all Azure resources are deployed to the free tier).

Once the resources are finished deploying to Azure, you'll need to configure the Moodle plugin with its messaging endpoint. First, you'll need to get the endpoint from your Bot in Azure. To do that:

1. If you aren't already, log into the [Azure portal](https://portal.azure.com).
2. In the left pane select **Resource groups**.
3. From the list select the resource group you just used (or created) while deploying your Bot.
4. Select the **WebApp Bot** resource from the list of resources in the group.
5. Copy the **Messaging Endpoint** from the **Overview** section.
6. In Moodle, open the **Team Settings** page of your Moodle Plugin.
7. In the **Bot Endpoint** field paste the URL you just copied and change the word *messages* to *webhook*. The URL should now look like `https://botname.azurewebsites.net/api/webhook`
8. Click **Save Changes**
9. Once your changes have saved, go back to the **Team Settings** tab, click the **Download manifest file** button and save the manifest package to your computer (you'll use it in the next section).

## Step 4: Deploy your Microsoft Teams app

Now that you have your Bot deployed to Azure and configured to talk to your Moodle server, it's time to deploy your Microsoft Teams app. To do this, you'll load the manifest file you downloaded from the Moodle Plugin Team Settings page in the previous step.

Before you can install the app, you'll need to make sure external apps and sideloading of apps is enabled. To do so, you can follow [these steps](admin-settings). Once you've ensured that external apps are enabled, you can follow the steps below to deploy your app.

1. Open Microsoft Teams.
2. Click the **Store** icon on the lower left of the navigation bar.
3. Click the **Upload a custom app** link from the list of options. *Note:* If you're logged in as a global administer you'll have the option of uploading the app to your organization's app store, otherwise you'll only be able to load the app for Teams you're a part of ("sideloading").
4. Select the `manifest.zip` package you downloaded previously and click **Save**. If you haven't yet downloaded the manifest package, you can do so from the **Team Settings** tab of the plugin configuration page in Moodle.

Now that you have the app installed you can add the tab to any channel that you have access to. To do so navigate to the channel, click the **+** symbol and select your app from the list. Follow the prompts to finish adding your Moodle course tab to a channel.

That's it! You and your team, can now start working with your Moodle courses directly from Microsoft Teams.

To share any feature requests or feedback with us, visit our [Feedback portal](https://feedbackportal.microsoft.com).

Note

Microsoft will be moving from UserVoice to our own customer feedback solution on a product-by-product basis during 2021. [Learn more](https://support.microsoft.com/topic/-pages-430e1a78-e016-472a-a10f-dc2a3df3450a).