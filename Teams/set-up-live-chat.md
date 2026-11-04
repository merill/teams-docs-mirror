---
layout: Conceptual
title: Set up Live chat in Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/set-up-live-chat
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: jtremper
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-chat
audience: admin
ms.reviewer: anbalmos, bekeren
ms.date: 2026-08-06T00:00:00.0000000Z
description: Learn how to set up and manage Live chat on your website and connect with customers in real time.
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: teams-chat-and-channels
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
locale: en-us
document_id: a766c78a-be05-db6a-73e3-b3ff22e96713
document_version_independent_id: a766c78a-be05-db6a-73e3-b3ff22e96713
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/set-up-live-chat.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: set-up-live-chat
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/set-up-live-chat.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 05134e6a-6eff-5104-a538-70b0d892932d
---

# Set up Live chat in Teams - Microsoft Teams | Microsoft Learn

Important

Starting August 6, 2026, new customers can no longer set up Microsoft Teams Live chat. Starting October 5, 2026, Microsoft Teams Live chat is no longer supported, and incoming chats from the widget are no longer relayed to Teams. Remove the live chat widget from your website before October 5, 2026. For more information, see Live chat retirement FAQ.

Live chat allows your website's visitors to chat easily with your business through a chat widget on your customer-facing website. Visitors to your website can start a chat conversation through the widget.

This article teaches you how to set up and manage the live chat experience for Microsoft Teams.

**Requirements and limitations for live chat**

- Live chat is available only to Microsoft 365 Business Basic, Microsoft 365 Business Standard, and Microsoft 365 Business Premium users.
- The Teams admin can have any license type to set up live chat, as long as at least one member in your tenant has a supported license.
- There's a limit of up to 25 users who can be added to the handoff support team.

## Set up and manage live chat settings

You must be a Global admin to set up live chat in the Teams **Admin** app.

### Access live chat setup

1. Open the [**Admin**](https://teams.microsoft.com/l/app/b47c7387-2807-440c-9fc2-7c8f46147a20?source=agent-details-page) app in Teams. If you don't have the Admin app added to your Teams client, add it by searching the Teams App Store for "Admin" or go to this [**link**](https://teams.microsoft.com/l/app/b47c7387-2807-440c-9fc2-7c8f46147a20?source=agent-details-page).
2. Select **Live chat** in the left navigation of the **Admin** app.
3. Select **Get started** to start the setup process.

### Step 1: Customize your business logo, name, and support language

1. Customize the chat by adding your **business logo** and **name**. This is the name that live chat uses to represent itself with your customers.
2. Set the language the chat communicates in. The default is set to your Teams locale.
3. Customize the default message that shows in the chat to welcome your website visitors.
4. Continue to the next step.

### Step 2: Select your live chat support team members

When a customer asks a question from live chat on your website, Teams creates a request and automatically assigns it to the next available member of your support team.

1. Add the users that should be assigned to the live chat handoff team.
2. Continue to the next step.

### Step 3: Select your business hours

Live chat requests are only relayed to your support team during the business hours that you define. If customer requests come in outside of your business hours, live chat either collects their email or phone number so you can follow up or offers to schedule an appointment with a member of your support team.

1. Customize what message should be sent when no one is available to chat with a customer or if customers reach you outside business hours.
2. **Consent** to adding live chat to your organization.
3. Select **Save** to complete setup for the live chat. This process takes a few minutes to complete. Teams notifies you when the setup process is complete. The experience won't be available to your customers until you publish the live chat widget to your website.

## Add the live chat widget to your website

You must consent to adding the live chat bot to your organization.

1. Sign in to Teams by using your Global admin credentials.
2. Open the **Admin** app in Teams.
3. Select **Live chat**.
4. Select **Create** to start the live chat widget creation.

    The live chat widget is created in the background. Teams notifies you once the setup process is complete.
5. Test the chat widget by sending a message via the chat widget right within the **Admin** app and see how it connects website visitors to someone on your team by selecting **Test** under **Next steps**.
6. To add the chat widget to your website, select the **Add to website** button.
7. Add your website’s full URL as a trusted website.

    The chat widget can only be embedded on this website.
8. After you add the website, a code snippet is generated along with instructions to add to your website if it's powered by HTML, WordPress, Wix, or Squarespace.

After you complete these steps, the live chat widget is added to your website and ready for your customers to use.

## Add appointment booking to live chat (preview)

Let your customers schedule appointments directly from your live chat widget.

1. Go to the **Admin** app in Teams.
2. Select **Live chat** in the left navigation of the **Admin** app.
3. Select **Set up** on the suggestion **Automate** **appointments with customers** to begin setting up appointment booking in live chat.
4. Customize your appointment booking settings.

    1. Add or remove **Support staff**.
    2. Edit your team's **Availability**.
    3. Add, remove, or edit **Appointment types**.
5. Select **Enable appointment booking**. Your live chat widget now allows your website visitors to schedule appointments with your business. Once an appointment is made, it's automatically added to the assigned staff member’s calendar, and the post in the **Live chat requests** channel is updated with the relevant appointment details.

## Add an AI chatbot to your live chat experience

For tenants with a Microsoft Copilot Studio license, you can add an AI chatbot to your live chat widget to answer frequently asked customer questions before customers are connected to your support team. Learn more about Copilot Studio at [Microsoft Copilot Studio](https://www.microsoft.com/microsoft-copilot/microsoft-copilot-studio).

1. Go to the **Admin** app in Teams.
2. Select **Live chat** in the left navigation of the **Admin** app.
3. Select **Set up** on the suggestion **Save time with AI-generated responses** to set up the chatbot. This suggestion is only available to the admin if they have a Microsoft Copilot Studio license. In this step, add users to be assigned customer requests.
4. Add your company's public website and select **Add AI agent**.

The AI chatbot is now added to your live chat widget on your website. The AI chatbot answers your customer's questions based on information available on your website. If no answer is found or if the website visitor wants to talk to a human agent, a Teams customer request is sent to your support team (same experience as live chat).

When a customer on the website asks a question, Teams creates a request and automatically assigns it to the next available customer service member.

## What your customers and support people experience

When a customer opens the live chat widget on your website and starts a conversation, a request is made in the **Live chat requests** team. The admin and users in the Live chat team can view all tickets in the **General** channel under the **Requests** tab.

On your website, the Live chat bot gathers customer contact information and notifies the customer that they’re being connected to a member of your support team.

Live chat finds an available support person and connects the customer to the support person in your business based on their Teams status. Live chat automatically assigns the ticket to someone in your support team and connects them to the customer in Teams **Chat** where the support person can chat with the customer in real time.

## Fixing live chat errors

This section provides guidance for troubleshooting issues that you might encounter when you set up or use live chat.

### Your support tag was deleted

If your live chat support tag was deleted and requests are only being assigned as follow ups, admins can re-create the tag by selecting **Recreate tag** in the Admin app. After re-creating the tag, live chat requests will be assigned to your team again.

### Your team was deleted

If your live chat team was deleted, restart your live chat setup to re-create and add your support team again. To do this, select **Restart setup** on the error screen or select **Contact support** for help.

### Blocked by company policy

If you're blocked from creating your live chat setup because of your company's policy:

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com), and then in the left navigation, go to **Teams apps** &gt; **Manage apps**.
2. In the list of apps, locate and select **SharePoint**, and then check the following:
    1. Make sure that the SharePoint app isn't in a blocked state. If you see a banner indicating that the app is blocked, select **Unblock app**.

        [![Screenshot of the SharePoint page in Manage apps in the Teams admin center.](media/set-up-live-chat-sharepoint.png)](media/set-up-live-chat-sharepoint.png#lightbox)
    2. On the **Users and groups** tab, select **Edit availability**, and then make sure the app is available to everyone in your organization who manages live chat requests.
3. After you complete these steps to unblock SharePoint access, go back to the error screen in live chat and continue the setup process.

### Tag creation failed

If the setup failed and you get an error message saying that the tag couldn't be created:

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com), and then in the left navigation, go to **Teams** &gt; **Teams settings**.
2. Under **Tagging**, make sure that the **Custom tags** toggle is **On**.

    [![Screenshot of the Custom tags toggle on the Teams settings page of the Teams admin center.](media/set-up-live-chat-tagging.png)](media/set-up-live-chat-tagging.png#lightbox)

### Blocked by too many admin roles

If your setup is blocked because your account has too many [administrator roles](/en-us/microsoft-365/admin/add-users/about-admin-roles) assigned to it:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) to manage Microsoft Entra roles.
2. Reduce the number of roles to only the [Global Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference) role, which includes all other roles.
3. Wait about 10 minutes for the role changes to apply.
4. Go back to the live chat setup and try again or select **Contact support** for more help.

## Live chat retirement FAQ

### What is changing?

Starting October 5, 2026, Microsoft Teams Live chat is no longer supported. The service remains available until the end of support. After the retirement date, all live chat widgets that remain embedded on a website are hidden. New conversations, escalations, and customer interactions can't be initiated through the widget.

### What happens to my customer data?

After live chat support ends, previously created customer data won't be deleted. Existing Teams channels and associated List data remain available according to the applicable Microsoft 365 data retention and lifecycle policies in your tenant.

Review your data retention requirements and export any information that you want to preserve independently.

### What actions do I need to take?

To prepare for the end of live chat support, admins should:

- Remove the live chat widget from all websites before October 5, 2026.

    To do this, on the HTML pages where the widget is embedded, look for the `<script>` tag with `id="chatbot"` and remove it.
- Inform live chat support team members in your organization about the end of support.

### What alternative solutions can I transition to?

Microsoft currently supports these alternative live chat solutions:

- [Dynamics 365 Contact Center with Live Chat](/en-us/dynamics365/customer-service/implement/introduction-omnichannel)
- Microsoft Copilot Studio Contact Center AI solutions

Organizations with ongoing customer support, engagement, or contact center requirements should evaluate these solutions to determine which option best meets their business needs.

### How do I get additional help?

If you have questions regarding live chat retirement or need assistance during the transition period, contact Microsoft support at livechatsupport@microsoft.com.