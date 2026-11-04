---
layout: Conceptual
title: Teams Rooms Autopilot Registration for Partners - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/autopilot-registration4partners
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how integration and OEM partners can automatically complete the Autopilot registration for Teams Rooms devices
author: MattSlomka
manager: srpall
ms.author: mattslomka
ms.service: msteams
ms.topic: how-to
ms.date: 2025-12-02T00:00:00.0000000Z
ms.subservice: itpro-rooms
locale: en-us
document_id: c6942647-2441-c17b-bc66-3ff3135b7913
document_version_independent_id: c6942647-2441-c17b-bc66-3ff3135b7913
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/autopilot-registration4partners.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/autopilot-registration4partners
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/autopilot-registration4partners.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/4b132a0c-342a-42eb-91ff-8159e1ed413d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f2b71146-ce8e-46a8-9965-8aa8b3aa8235
platformId: 05a331b4-f4a5-0c16-9143-c4e8a041f9a7
---

# Teams Rooms Autopilot Registration for Partners - Microsoft Teams | Microsoft Learn

Teams Rooms on Windows devices support Intune Autopilot, which enables a zero-touch deployment, to learn more about the overall process see: [Windows Autopilot and Autologin for Teams Rooms on Windows](/en-us/microsoftteams/rooms/autopilot-autologin).

One of the key portions of Autopilot is adding the hardware identity information from the Teams Rooms compute to the customers Intune environment. Registration can be completed in three ways:

1. [OEMs can automatically load the hardware identity](/en-us/autopilot/oem-registration)
2. [Cloud Solution Providers (CSPs) can use Partner Center to load the hardware identity](/en-us/autopilot/partner-registration)
3. [Customers can load the hardware identity in Intune](/en-us/autopilot/manual-registration)

This document provides step by step instructions for a Teams Rooms partner (that is a [Cloud Solution Provider](/en-us/partner-center/enroll/csp-overview)) how to add the Teams Rooms Autopilot hardware identity into a customer’s environment.

Important

If you're a CSP but aren’t deploying Teams Rooms devices, reference the [Intune documentation](/en-us/autopilot/partner-registration). If you're a Teams Rooms partner who isn't a [Cloud Solution Provider](/en-us/partner-center/enroll/csp-overview): use the OEM automatic registration method or gather the hardware identities for your customer to load directly.

## Step 1: Establish a CSP relationship with the customer environment

A CSP relationship with a customer is essential to add devices into their environment. Follow these instructions to: [request a CSP relationship with your customer](/en-us/autopilot/registration-auth)

Note

Typically, CSP relationships are for requesting administrative access to a customer environment, Granular Delegated Administrative Permissions (GDAP) **isn't** required for registering Autopilot hardware identities. You can request GDAP to assist your customer with other administrative activities, but it isn't required for this process.

## Step 2: Gather hardware identities

Adding hardware identities to a customer’s environment through Partner Center can be accomplished using one of three combinations of values. Different devices can be registered with different methods, but you must have one of the three sets of information per device as it allows the Intune Autopilot service to identify the device.

1. Serial Number + Manufacturer Name + Model Number

    1. This information is typically included in the packing invoice when hardware is ordered/delivered from a distributor or OEM
2. Windows PKID (Product Key ID)

    1. This information is frequently found on the label on the box for a Teams Room or on a sticker on the Teams Room itself. Some OEMs also make this information available on their website by providing proof of device purchase.
3. Device Hardware Hash

    1. This information is most frequently collected manually by running a script on the device itself however occasionally it's also available by contacting the Teams Rooms OEM.

Since the best practice for gathering this information can vary by Teams Rooms OEM, the [learn to deploy Teams Rooms on Windows in minutes](https://aka.ms/MTRAutoPilot) blog has information authored by each OEM on what is recommended for their products.

## Step 3: Retrieve the CSV template for uploading Autopilot hardware identities

1. Open [Partner Center](https://partner.microsoft.com/pcv/dashboard/overview)
2. Select **Customers**
3. Select your desired customer from the customer list
4. Select **Devices** from the left navigation rail
5. Select **Devices** in the tabs at the top
6. Select **Add group**
7. Select **Download** next to *You can see a sample CSV here*

## Step 4: Add the device identity information to the CSV

Open the CSV template, delete all of the sample information and add in the relevant information for the customers Teams Rooms devices.

## Step 5: Upload the CSV into Partner Center for the customer

1. Open [Partner Center](https://partner.microsoft.com/pcv/dashboard/overview)
2. Select **Customers**
3. Select your desired customer from the customer list
4. Select **Devices** from the left navigation rail
5. Select **Devices** in the tabs at the top
6. Select **Add group**
7. Enter a group name for this upload. Ensure the group name starts with “MTR-“ so devices are automatically populated into the Pro Management Portal
8. Select **Upload File** and attach the file created in step 4

## Step 6: Continue the Teams Rooms Autopilot setup steps

The Autopilot hardware identity registration is now complete. Continue with the Intune and Pro Management Portal configuration guidance outlined in the deployment documentation: [Windows Autopilot and Autologin for Teams Rooms on Windows](/en-us/microsoftteams/rooms/autopilot-autologin).

Note

The remaining Teams Rooms Autopilot + Autologin steps are completed by the customer administrator or using GDAP.