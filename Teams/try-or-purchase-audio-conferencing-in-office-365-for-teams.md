---
layout: Conceptual
title: Try or purchase Audio Conferencing in Microsoft 365 for Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/try-or-purchase-audio-conferencing-in-office-365-for-teams
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: oscarr
ms.date: 2026-11-02T00:00:00.0000000Z
ms.topic: how-to
ms.assetid: d080bb8c-3465-47bb-ad2b-9428f1a3fd24
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- Tier1
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.lync.lac.CpcGettingStarted
- seo-marvel-mar2020
description: Learn how to try or purchase Audio Conferencing (PSTN conferencing) licenses for Microsoft Teams with Microsoft 365 or Office 365 to set up conference calls that users can dial in to.
locale: en-us
document_id: 41c6c2e6-a1c7-dd0c-dbe3-0072497282d5
document_version_independent_id: 1b09ca3d-f45e-5540-40b4-8c3b7176fc81
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/try-or-purchase-audio-conferencing-in-office-365-for-teams.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: try-or-purchase-audio-conferencing-in-office-365-for-teams
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/try-or-purchase-audio-conferencing-in-office-365-for-teams.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/6ab06385-661e-4214-8870-bbe4071c960d
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/131ba09e-4280-4ae7-8622-1f9f1c0daad1
platformId: 6f8fe8f8-bdff-1b31-07d1-34fdb018e7ca
---

# Try or purchase Audio Conferencing in Microsoft 365 for Teams - Microsoft Teams | Microsoft Learn

Sometimes users in your organization need to use a phone to call in to a meeting. Microsoft Teams includes the Audio Conferencing feature for just this situation. Users can call in to Microsoft Teams meetings using a phone, instead of using the Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for users who plan to schedule or lead meetings. Meeting attendees who call in to the meeting don't need any licenses assigned to them and don't need other setup.

For pricing info, see [Pricing for Audio Conferencing](https://www.microsoft.com/microsoft-teams/audio-conferencing?rtc=3).

## Step 1: Buy and assign Audio Conferencing licenses

You must be a [billing administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.

### To buy and assign user Audio Conferencing licenses

1. Find out if **Audio Conferencing** is available in your country/region. [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
2. Get your **Audio Conferencing** licenses. If you want to:

    - **Try it** before you buy it: you can sign up for an Office 365 Enterprise E5 free trial that includes Audio Conferencing. See [Office 365 Enterprise E5 Trial](https://www.microsoft.com/microsoft-365/enterprise/office-365-e5?activetab=pivot:overviewtab).
    - **Buy it**: see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing).
3. [Assign licenses to users](/en-us/microsoft-365/admin/manage/assign-licenses-to-users) in your organization who will schedule or lead meetings.
4. If you purchased Audio Conferencing add-on licenses and Communications Credits licenses, assign these licenses to the appropriate users as well. For instructions, see [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing).

### To buy and assign pay-per-minute Audio Conferencing licenses

If you're a Volume and Licensing customer, you can get pay-per-minute Audio Conferencing licenses. For more information on pay-per-minute Audio Conferencing licenses, see [Audio Conferencing pay-per-minute](audio-conferencing-pay-per-minute).

1. Find out if **Audio Conferencing** is available in your country/region. [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
2. Get your **Audio Conferencing** licenses. To acquire pay-per-minute licenses, contact your account representative.
3. [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization) for your organization. To set up Communications Credits, see [What are Communications Credits?](what-are-communications-credits)

    Important

    If Communications Credits aren't set up, Audio Conferencing doesn't work for users with pay-per-minute licenses.
4. [Assign licenses to users](/en-us/microsoft-365/admin/manage/assign-licenses-to-users) in your organization who will schedule or lead meetings.

    Note

    If you have Audio Conferencing pay-per-minute licenses, you must also assign a Communications Credits license separately to each user.

## Step 2: Set the Audio Conferencing provider for users who lead or schedule meetings

When you assign an **Audio Conferencing** license to users in your organization who don't have Teams integrated with a third-party Audio Conferencing provider, they're automatically set up for Audio Conferencing. You don't need to set their Audio Conferencing provider.

If you have users set up with a third-party Audio Conferencing provider, you must change the provider of those users to Microsoft. To change the provider for a user, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses).

## Step 3: Other admin tasks

Consider the following **optional** configuration tasks:

1. [Customize meeting invitations](meeting-settings-in-teams#customize-meeting-invitations). The dial-in numbers assigned to a user are automatically included in the meeting invitations that are sent to attendees. You can also add custom help and legal links, a text message, and a small company graphic.
2. [Set the phone numbers included in meeting invitations](set-the-phone-numbers-included-on-invites-in-teams). Specify the phone numbers that appear in meetings scheduled by a user.
3. [Set the auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams). Configure the languages that the Audio Conferencing auto attendant uses to greet callers when they dial in. This setting applies only if you use Microsoft as your Audio Conferencing provider.
4. [Set the PIN length for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings-in-teams).

Note

This feature isn't yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).