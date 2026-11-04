---
layout: Conceptual
title: Teams device store - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/device-store
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: pauljuricic
ms.date: 2026-09-29T00:00:00.0000000Z
ms.topic: article
ms.service: msteams
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
description: Learn how to browse and purchase devices in the Microsoft Teams device store.
locale: en-us
document_id: 9667e76d-2017-0c53-c067-56e698fa8f2f
document_version_independent_id: 9667e76d-2017-0c53-c067-56e698fa8f2f
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/device-store.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/device-store
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/device-store.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 1902e26c-b1fa-0fa4-8306-17c3e5ee2a2d
---

# Teams device store - Microsoft Teams | Microsoft Learn

## What are the benefits of Teams device store?

Teams device store is a convenient and easy way to find and buy Teams certified devices that can enhance your Teams experience. By using Teams device store, you can:

- Discover the latest and best Teams certified devices for Teams calls and meetings in a single familiar place within the product.
- Browse devices by features, prices, and easily find the one you need based on rich filters.
- When you buy any Teams Room device from the store, you also get free expert support for 90-days after delivery, to help you set up and manage them.
- Hassle-free returns: Return almost any device within 30 days.

The device store lets you browse and purchase devices certified for Microsoft Teams. There are two places where you can find the device store:

- Device store in Teams admin center
- Device store in Teams App

## Device store in Teams admin center

The device store in the Teams admin center lets you browse, purchase, and provision devices certified for Microsoft Teams. The device store is available in Canada, France, Germany, Ireland, Italy, Portugal, Austria, Spain, Greece, Belgium, Netherlands, the United States, and the United Kingdom.

To use the devices store in the Teams admin center, go to **Devices &gt; Store**.

### Requirements

To use the device store, you need to be a Global admin, a Teams admin, or a Teams device admin.

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

### Browse the store

The device store includes all devices that are certified for Teams, including headsets, web cameras, and Teams devices such as Teams Rooms, desk phones, and Teams displays. You can sort, filter, or search to find the device that your organization needs.

### Purchase devices

When you purchase devices from the device store, the payment and fulfillment, including shipping and delivery, are handled by UnifiedCommunications.com (a Microsoft third-party fulfillment partner), under their [terms of service](https://unifiedcommunications.com/docs/teams-marketplace/en-US/terms-of-service) and [privacy policy](https://unifiedcommunications.com/docs/teams-marketplace/en-US/privacy-policy).

You can pay with a credit card or a purchase order. Purchase order payment requires one-time setup with the fulfillment provider. All orders can be returned up to 30 days after they're delivered to the buyer.

The checkout experience for the device store in Teams admin center can be enabled or disabled by configuring the **Allow the use of additional optional connected experiences in Office** policy setting. Learn more here: [Overview of optional connected experiences in Microsoft Teams](/en-us/microsoftteams/privacy/teams-privacy-oce-overview).

### Order tracking and history

You can view the order history by going to **Store &gt; Order history**, which includes all orders placed by you and other admins in the organization. Order history also includes the shipping status of your orders. For questions about order tracking, returns, or refunds, contact UnifiedCommunications.com. Their contact information is available on the invoice sent to the email address mentioned during order placement.

Orders placed in the Teams device store and any data associated with them are classified as tenant orders and tenant data.

### Provision devices

When you purchase devices that support remote provisioning, the MAC address of those devices is automatically added to the Teams admin center when the device is shipped. Depending on the order and when it ships, it can take approximately five days for the MAC address to appear in the Teams admin center.

Once your devices are delivered, see [Remotely provision devices](remote-provision-remote-login) to complete the provision and sign-in process.

Note

For devices purchased from the store, the automatic addition of the device MAC address to the Teams admin center is supported in United States and Canada only. For information about manually adding a device using its MAC address, see [Add a device MAC address](remote-provision-remote-login).

## Device store in Teams App

With Teams device store inside Microsoft Teams, users can easily discover and purchase certified Teams devices for personal or shared use cases - headsets, web cameras, desk phones, Teams Rooms, and more. Explore devices in categories, use search, or filters to find desired device.

The device store is available for tenants in Canada and the United States. To use the device store in the Teams App, go to **Apps &gt; Devices**.

![Screenshot of Device Store in Teams app.](media/device-store-app.png)

### Requirements

The device store is currently limited to commercial tenants only, that is, Education (EDU) tenants won't see this store. Also, it's limited to customers with user licenses less than or equal to 300.

### Browse the store

The device store includes all devices that are certified for Teams, including headsets, web cameras, and Teams devices such as Teams Rooms, desk phones, and Teams displays. Users can sort, filter, or search to find the device that they need.

### Purchase devices

When users purchase devices from the device store, the payment and fulfillment, including shipping and delivery, are handled by UnifiedCommunications.com (a Microsoft third-party fulfillment partner), under their [terms of service](https://unifiedcommunications.com/docs/teams-marketplace/en-US/terms-of-service) and [privacy policy.](https://unifiedcommunications.com/docs/teams-marketplace/en-US/privacy-policy)

Users can pay with a credit or debit card. All orders can be returned up to 30 days after they're delivered. For questions about order tracking, returns, or refunds, contact UnifiedCommunications.com. Their contact information is available on the invoice sent to the email address mentioned during order placement.

### Admin controls

Admins can manage the device store experience for their organization from Teams admin center. You can disable the purchase for all users in your tenant using this setting, available in **Teams admin center &gt; Devices &gt; Store &gt; Settings**. To update this setting in Teams admin center, you need to be a Global administrator.

Important

Microsoft recommends that you use roles with the fewest permissions. Using lower permissioned accounts helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

By default, purchase is enabled. When it's disabled, the device store will be visible for users to browse and learn about latest certified devices, but the users can't purchase.

Orders placed in the Teams device store and any data associated with them are classified as tenant orders and tenant data.