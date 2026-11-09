---
layout: Conceptual
title: Plan SIP Gateway - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/sip-gateway-plan
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.date: 2026-09-17T00:00:00.0000000Z
ms.reviewer: chasing
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- M365-voice
- Tier1
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Learn more about SIP Gateway, such as requirements and benefits.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
locale: en-us
document_id: 5daedfbc-de69-1d72-c9b2-a1ad953c4737
document_version_independent_id: 5daedfbc-de69-1d72-c9b2-a1ad953c4737
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/sip-gateway-plan.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/sip-gateway-plan
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/sip-gateway-plan.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/58f888a4-3847-4473-ba35-882e789f0dbe
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/a3955c7b-f5ee-420d-aff5-d7119738f38b
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/314a9abc-91dd-4683-8691-43005e929bb8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/b31948f4-2f38-404b-ac93-c3c8c5b3ae33
platformId: fda60c4e-6850-72e5-202b-236f68622e35
---

# Plan SIP Gateway - Microsoft Teams | Microsoft Learn

SIP Gateway lets your organization use any compatible SIP device with Microsoft Teams to preserve your investments in SIP devices. Now you can sign-in to Teams with your corporate credentials and make and receive calls with a compatible SIP device. Compatible devices can be Skype for Business IP phones with standard SIP firmware, Cisco IP phones with multiplatform SIP firmware, or SIP devices from vendors such as Poly, Yealink, and AudioCodes. To find out how to configure your SIP devices for SIP Gateway, see [Configure SIP Gateway](sip-gateway-configure).

## Benefits of SIP Gateway

A SIP gateway lets compatible SIP devices connect seamlessly to Teams for calling features and lets them do the following:

- **Make calls:** SIP device users can make calls to the Public Switched Telephone Network (PSTN), to other SIP devices, and to Teams and Skype for Business users. SIP device users can only call users who have phone numbers.
- **Receive calls:** SIP device users can receive a call from the PSTN, from other Teams or Skype for Business users who have SIP devices, and from Teams and Skype for Business applications. The SIP device acts as a Teams endpoint. Inbound calls will be received on the user's SIP device.
- **Multiple simultaneous calls:** A SIP device user in a call can put the call on hold to make or receive other calls. A SIP device user can also conference two calls.
- **Hold/Resume and Mute/Unmute:** A SIP device user can hold and resume or mute and unmute a call by using the features for those actions on the device.
- **Voicemail:** SIP device users can listen to electronically stored voice messages that callers leave for them.
- **Message waiting indicator:** SIP device users can receive notifications that alert them when they have new voicemail messages.
- **Sign-in and sign-out:** SIP devices users can sign in and sign out of Teams on the device.
- **Dual-tone multi-frequency:** SIP device users can press number keys to provide input during interactive voice response calls.
- **Teams meetings:** A user's SIP device can join Teams meetings by dialing into the meeting using a phone number. A meeting participant can add an internal and external guest to a meeting by dialing out to user's phone number or can add them by using the 'Request to Join' button.
- **Call transfers:** SIP device users can transfer calls. SIP Gateway supports both blind and consultative transfers.
- **Local call forwarding:** A user can set forwarding rules (always, on timeout, and busy) for the device. If the device is connected to the SIP Gateway, then the call is sent to the calls endpoint based on the rule that the user sets. To make local call forwarding work, the admin must set the `AllowCallRedirect` attribute in `Set-CsTeamsCallingPolicy` to `Enabled`.
- **Off board stale devices:** A SIP gateway supports auto offboarding of stale devices provisioned for a tenant. Paired (signed-in) devices will be off boarded if not connected for 30 days, and unpaired (signed-out) devices after 14 days. A device that was offboarded can be onboarded again after a factory reset.
- **Set DND from SIP devices:** You can use your SIP device for setting and fetching your Teams Do Not Disturb (DND) status. To set the DND status for your Teams account from your SIP device, dial the feature code \*30\* on the SIP device. To reset your Teams DND status, dial \*31\* from the SIP device. Dialing \*31\* clears the user-configured presence status, in this case DND.
- **Call Queues and voice apps support:** Customers can use SIP devices as call queue agents with some restrictions, for instance, SIP Gateway doesn't publish presence for devices hence presence based routing isn't supported.

## Requirements to use SIP Gateway

Teams users must have a phone number with PSTN calling enabled to use SIP Gateway.

Note

SIP Gateway isn't yet available for DoD.

Note

SIP Gateway Feature Codes:

DND - \*30\* (Set DND From SIP Device)

\*31\* (Reset Teams DND Status from SIP Device)

Call Forwarding - (https://support.microsoft.com/office/call-forwarding-call-groups-and-simultaneous-ring-in-microsoft-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) \*32\* - Reset Call Forwarding Status

\*33\* (Set "Call Forwarded To" Number)

\*34\* (Set "Forward on Timeout")

\*35\* (Setup Simultaneous Ring)

Device Validation -

\*55\* - OTP validation from devices provisioned through Teams Admin Center Voicemail -

\*99\* - Check voicemail

### Hardware, software, and licenses

If you have a 3PIP or SIP device, you must have the following:

- [Microsoft Teams](https://www.microsoft.com/microsoft-teams/group-chat-software)
- Skype for Business Online (Plan 2)
    - *Skype for Business Online (Plan 2)* isn't a standalone license that can be purchased.
- [Microsoft Phone System](../what-is-phone-system-in-office-365)
- [PSTN Connectivity](../pstn-connectivity)

## Compatible devices

| Vendor | Model | Minimum firmware version | Approved firmware version | Remarks | Links |
| --- | --- | --- | --- | --- | --- |
| **Cisco** |  |  |  | Devices running Enterprise firmware must be converted to multiplatform (MPP) firmware. Read the guide at the right to learn how. | [Cisco firmware conversion guide](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html) |
|  | CP-8832^1^ | 11.3.5MPP | 12-0-7MPP | IP Phone |  |
|  | CP-6821^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-6841^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-6851^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-6861^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-6871^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-7811^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-7821^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-7832^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-7841^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-7861^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-8811^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-8841^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-8845^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-8851^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-8861^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-8865^1^ | 11.1.1MPP | 12-0-7MPP | IP Phone |  |
|  | CP-8875^1^ | PhoneOS 3.3.1 | PhoneOS 3.3.1 | IP Phone |  |
|  | DP-9811^1^ | PhoneOS 3.3.1 | PhoneOS 3.3.1 | IP Phone |  |
|  | DP-9841^1^ | PhoneOS 3.3.1 | PhoneOS 3.3.1 | IP Phone |  |
|  | DP-9851^1^ | PhoneOS 3.3.1 | PhoneOS 3.3.1 | IP Phone |  |
|  | DP-9861^1^ | PhoneOS 3.3.1 | PhoneOS 3.3.1 | IP Phone |  |
|  | DP-9871^1^ | PhoneOS 3.3.1 | PhoneOS 3.3.1 | IP Phone |  |
|  | ATA191-MPP^3^ | 11.2.2MPP | 11-3-1MPP | ATA |  |
|  | ATA192-MPP^3^ | 11.2.2MPP | 11-3-1MPP | ATA |  |
|  | VG400 2-port / 2FXO | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG400 4-port / 4FXO | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG400 6-port / 6FXO | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG400 8-port | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG410 24-port | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG410 24-port / 4FXO | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG410 48-port | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG420 84-port / 6FXO | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG420 132-port / 6FXO | N/A | Firmware updates are vendor-managed | ATA |  |
|  | VG420 144-port | N/A | Firmware updates are vendor-managed | ATA |  |
| **Poly** |  |  |  | The device will auto reboot and install the selected firmware. | [Poly Lens Provisioning Guide](https://info.lens.poly.com/docs/category/lens-assisted-provisioning) |
|  | Trio 8500^2^ | 5.9.5.3182 | 7.2.4.0185 | IP Phone |  |
|  | Trio 8800^2^ | 5.9.5.3182 | 7.2.4.0185 | IP Phone |  |
|  | Trio C60^2^ | 5.9.5.3182 | 7.2.4.0185 | IP Phone |  |
|  | VVX150^2^ | 5.9.5 | 6.4.3.5814 | IP Phone |  |
|  | VVX201^2^ | 5.9.5 | 6.4.6.2640 | IP Phone |  |
|  | Omegaline VVX250^2^ | 5.9.5 | 6.4.6.2681 | IP Phone |  |
|  | VVX250^2^ | 5.9.5 | 6.4.6.2656 | IP Phone |  |
|  | VVX300^3^ | 5.9.5 | 5.9.7.3480 | IP Phone |  |
|  | VVX301^2^ | 5.9.5 | 6.4.6.2640 | IP Phone |  |
|  | VVX310^3^ | 5.9.5 | 5.9.7.3480 | IP Phone |  |
|  | VVX311^2^ | 5.9.5 | 6.4.6.2640 | IP Phone |  |
|  | Omegaline VVX350^2^ | 5.9.5 | 6.4.6.2681 | IP Phone |  |
|  | VVX350^2^ | 5.9.5 | 6.4.6.2656 | IP Phone |  |
|  | VVX400^3^ | 5.9.5 | 5.9.7.3480 | IP Phone |  |
|  | VVX401^2^ | 5.9.5 | 6.4.6.2640 | IP Phone |  |
|  | VVX410^3^ | 5.9.5 | 5.9.7.3480 | IP Phone |  |
|  | VVX411^2^ | 5.9.5 | 6.4.6.2640 | IP Phone |  |
|  | Omegaline VVX450^2^ | 5.9.5 | 6.4.6.2681 | IP Phone |  |
|  | VVX450^2^ | 5.9.5 | 6.4.6.2656 | IP Phone |  |
|  | VVX500^3^ | 5.9.5 | 5.9.7.3480 | IP Phone |  |
|  | VVX501^2^ | 5.9.5 | 6.4.6.2640 | IP Phone |  |
|  | VVX600^3^ | 5.9.5 | 5.9.7.3480 | IP Phone |  |
|  | VVX601^2^ | 5.9.5 | 6.4.6.2640 | IP Phone |  |
|  | Rove B1^1^ | 8.0.11 | Firmware updates are vendor-managed.Adding the /autoupdate/ suffix to the initial provisioning URL will force a firmware update via the SIP Gateway | DECT-Base |  |
|  | Rove B2^1^ | 8.0.11 | Firmware updates are vendor-managed.Adding the /autoupdate/ suffix to the initial provisioning URL will force a firmware update via the SIP Gateway | DECT-Base |  |
|  | Rove B4^1^ | 8.0.11 | Firmware updates are vendor-managed.Adding the /autoupdate/ suffix to the initial provisioning URL will force a firmware update via the SIP Gateway | DECT-Base |  |
|  | Rove 20^1^ | 8.0.11 | Firmware updates are vendor-managed.Adding the /autoupdate/ suffix to the initial provisioning URL will force a firmware update via the SIP Gateway | DECT-HS |  |
|  | Rove 30^1^ | 8.0.11 | Firmware updates are vendor-managed.Adding the /autoupdate/ suffix to the initial provisioning URL will force a firmware update via the SIP Gateway | DECT-HS |  |
|  | Rove 40^1^ | 8.0.11 | Firmware updates are vendor-managed.Adding the /autoupdate/ suffix to the initial provisioning URL will force a firmware update via the SIP Gateway | DECT-HS |  |
|  | Edge E100^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E220^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E300^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E320^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E350^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E400^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E450^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E500^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge E550^2^ | 8.1.0.12774 | 8.5.1.0508 | IP Phone |  |
|  | Edge V 200^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | Edge V 250^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | Edge V 250+^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | Edge V 400^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | Edge V 450^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | Edge V 650^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | Edge V 800^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | Edge V 850^2^ | 8.5.1.0565 | 8.5.1.0565 | IP Phone |  |
|  | ATA 400^3^ | 4.0.1.6480 | Firmware updates are vendor-managed | ATA | [Poly ATA 400 Series Configuration Guide](https://kaas.hpcloud.hp.com/pdf-public/pdf_10029605_en-US-1.pdf) |
|  | ATA 402^3^ | 4.0.1.6480 | Firmware updates are vendor-managed | ATA |  |
|  | ATA 408^3^ | 4.0.1.6480 | Firmware updates are vendor-managed | ATA |  |
|  | OBi 300^3^ | 3.2.4.8441 | Firmware updates are vendor-managed | ATA |  |
|  | OBi 302^3^ | 3.2.4.8441 | Firmware updates are vendor-managed | ATA |  |
| **Yealink** |  |  |  |  | [Yealink support](https://www.yealink.com) |
|  | SIP-T21P^3^ | 83 | 34.72.0.75 | IP Phone |  |
|  | SIP-T21P\_E2^3^ | 83 | 52.84.0.125 | IP Phone |  |
|  | SIP-T23G^3^ | 83 | 44.84.0.140 | IP Phone |  |
|  | SIP-T27G^1^ | 83 | 69.86.0.15 | IP Phone |  |
|  | SIP-T29G^3^ | 83 | 46.83.0.130 | IP Phone |  |
|  | SIP-T30^1^ | 83 | 124.86.0.147 | IP Phone |  |
|  | SIP-T30P^1^ | 83 | 124.86.0.147 | IP Phone |  |
|  | SIP-T31G^1^ | 83 | 124.86.0.147 | IP Phone |  |
|  | SIP-T31P^1^ | 83 | 124.86.0.147 | IP Phone |  |
|  | SIP-T33G^1^ | 83 | 124.86.0.147 | IP Phone |  |
|  | SIP-T40G^3^ | 83 | 76.84.0.125 | IP Phone |  |
|  | SIP-T40P^3^ | 83 | 54.84.0.125 | IP Phone |  |
|  | SIP-T41P^3^ | 83 | 36.83.0.120 | IP Phone |  |
|  | SIP-T41S^2^ | 83 | 66.86.5.1 | IP Phone |  |
|  | SIP-T42G^3^ | 83 | 29.83.0.130 | IP Phone |  |
|  | SIP-T42S^2^ | 83 | 66.86.5.1 | IP Phone |  |
|  | SIP-T42U^2^ | 83 | 108.86.5.1 | IP Phone |  |
|  | SIP-T43U^2^ | 83 | 108.86.5.1 | IP Phone |  |
|  | SIP-T46G^3^ | 83 | 28.83.0.130 | IP Phone |  |
|  | SIP-T46S^2^ | 83 | 66.86.5.1 | IP Phone |  |
|  | SIP-T46U^2^ | 83 | 108.86.5.1 | IP Phone |  |
|  | SIP-T48G^3^ | 83 | 35.83.0.130 | IP Phone |  |
|  | SIP-T48S^2^ | 83 | 66.86.5.1 | IP Phone |  |
|  | SIP-T48U^2^ | 83 | 108.86.5.1 | IP Phone |  |
|  | SIP-T53^2^ | 83 | 96.86.5.1 | IP Phone |  |
|  | SIP-T53W^2^ | 83 | 96.86.5.1 | IP Phone |  |
|  | SIP-T54W^2^ | 83 | 96.86.5.1 | IP Phone |  |
|  | SIP-T57W^2^ | 83 | 96.86.5.1 | IP Phone |  |
|  | T64LTE | 185.87.0.35 | 185.87.0.35 | IP Phone |  |
|  | SIP-T73U^2^ | 185.87.0.35 | 185.87.0.35 | IP Phone |  |
|  | SIP-T73W^2^ | 185.87.0.35 | 185.87.0.35 | IP Phone |  |
|  | SIP-T74U^2^ | 185.87.0.35 | 185.87.0.35 | IP Phone |  |
|  | SIP-T74W^2^ | 185.87.0.35 | 185.87.0.35 | IP Phone |  |
|  | SIP-T85W^2^ | 185.87.0.35 | 185.87.0.35 | IP Phone |  |
|  | W56H^3^ | 61.85.0.56 | Firmware updates are vendor-managed | IP Phone |  |
|  | W73H^3^ | 116.85.0.38 | Firmware updates are vendor-managed | IP Phone |  |
|  | W78H^3^ |  | Firmware updates are vendor-managed | IP Phone |  |
|  | W57R^3^ | 118.85.0.27 | Firmware updates are vendor-managed | IP Phone |  |
|  | W59R^3^ | 115.85.0.56 | Firmware updates are vendor-managed | IP Phone |  |
|  | W59R Pro^3^ |  | Firmware updates are vendor-managed | IP Phone |  |
|  | W70B NOAM^3^ | 146.85.5.4 | Firmware updates are vendor-managed | IP Phone |  |
|  | W70B EMEA^3^ | 146.85.5.2 | Firmware updates are vendor-managed | IP Phone |  |
|  | W70B APAC^3^ | 146.85.5.3 | Firmware updates are vendor-managed | IP Phone |  |
|  | W80 NOAM^3^ | 130.85.5.5 | Firmware updates are vendor-managed | IP Phone |  |
|  | W80 EMEA^3^ | 130.85.5.6 | Firmware updates are vendor-managed | IP Phone |  |
|  | W80 APAC^3^ | 130.85.5.4 | Firmware updates are vendor-managed | IP Phone |  |
|  | W90 NOAM^3^ | 130.85.5.5 | Firmware updates are vendor-managed | IP Phone |  |
|  | W90 EMEA^3^ | 130.85.5.6 | Firmware updates are vendor-managed | IP Phone |  |
|  | W90 APAC^3^ | 130.85.5.4 | Firmware updates are vendor-managed | IP Phone |  |
|  | AX83H^3^ | 180.87.0.5 | 180.87.0.15 | WiFi IP Phone |  |
|  | AX86R^3^ | 180.87.0.5 | 180.87.0.15 | WiFi IP Phone |  |
| **AudioCodes** |  |  |  | AudioCodes IP phones are supported for provisioning and management through [OVOC.](https://www.audiocodes.com/products/management-products-solutions/one-voice-operations-center) | Some AudioCodes SIP devices need a provisioning URL setting. [Download and install upgrade files for the affected AudioCodes devices.](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5) |
|  | 405^1^ | 2.2.8 | 2.2.16.725 | IP Phone |  |
|  | 405HD^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 405HDG^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 420HD^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 420HDG^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 425HD^1^ | 3.5.1.75 | 3.5.4.44 | IP Phone |  |
|  | 430HD^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 430HDG^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 440HD^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 440HDG^1^ | 3.2.1 | 2.2.16.725 | IP Phone |  |
|  | 445HD^2^ | 3.2.1 | 3.5.4.44 | IP Phone |  |
|  | 445HDG^2^ | 3.2.1 | 3.5.4.44 | IP Phone |  |
|  | 450HD^2^ | 3.2.1 | 3.4.8.808.11 | IP Phone |  |
|  | 450HDG^2^ | 3.2.1 | 3.4.8.808.11 | IP Phone |  |
|  | C450HD^2^ | 3.2.1 | 3.5.4.44 | IP Phone |  |
|  | C450HDG^2^ | 3.2.1 | 3.5.4.44 | IP Phone |  |
|  | C448HD^2^ | 3.2.1 | 3.4.8.808.11 | IP Phone |  |
|  | RX50^2^ | 3.2.1 | 3.4.8.808.11 | IP Phone |  |
|  | MP112^3^ | 6.60A.367.001 | 6.60A.371.003 | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP114-FXS^3^ | 6.60A.367.001 | 6.60A.371.003 | ATA | 3 out of 4 ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP114-FXS-FXO^3^ | 6.60A.367.001 | 6.60A.371.003 | ATA | 3 out of 4 ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP118-FXS^3^ | 6.60A.367.001 | 6.60A.371.003 | ATA | 6 out of 8 ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP118-FXS-FXO^3^ | 6.60A.367.001 | 6.60A.371.003 | ATA | 6 out of 8 ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP124D/MP124E-FXS^3^ | 6.60A.367.001 | Firmware updates are vendor-managed | ATA | 18 out of 24 ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP1288-FXS^3^ | 7.40A.400.063 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP502^3^ | 7.26A.356.075 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP504^3^ | 7.26A.356.075 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP508^3^ | 7.26A.356.075 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP508-FXS-FXO^3^ | 7.26A.356.075 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP516^3^ | 7.26A.356.075 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP524^3^ | 7.26A.356.075 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP532^3^ | 7.26A.356.075 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | Mediant 800B - 4 FXS | 7.40A.604.077 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | Mediant 800B - 8 FXS | 7.40A.604.077 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | Mediant 800B - 12 FXS | 7.40A.604.077 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP1288-FXS 72 FXS | 7.40A.400.063 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP1288-FXS 144 FXS | 7.40A.400.063 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP1288-FXS 216 FXS | 7.40A.400.063 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
|  | MP1288-FXS 288 FXS | 7.40A.400.063 | Firmware updates are vendor-managed | ATA | All ports available [AudioCodes ATA Setup Guide](https://www.audiocodes.com/media/pafhki3d/onboarding-audiocodes-ata-to-microsoft-sip-gateway-for-teams.pdf) |
| **Spectralink** |  |  |  |  | [Spectralink Support](https://support.spectralink.com) |
|  | 7202^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7212^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7502^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7522^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7532^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7622^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7642^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7722^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | 7742^1,2^ | PCS22B | Firmware updates are vendor-managed | Handset |  |
|  | S33^1,2^ | PCS25J | Firmware updates are vendor-managed | Handset |  |
|  | S35^1,2^ | PCS25J | Firmware updates are vendor-managed | Handset |  |
|  | S37^1,2^ | PCS25J | Firmware updates are vendor-managed | Handset |  |
|  | S1000^1,2^ | PCS26Aa | Firmware updates are vendor-managed | IP-DECT Base Station |  |
|  | IP-DECT Server 400^1,2^ | PCS26Aa | Firmware updates are vendor-managed | IP-DECT Server |  |
|  | IP-DECT Server 6500^1,2^ | PCS26Aa | Firmware updates are vendor-managed | IP-DECT Server |  |
|  | Virtual IP-DECT Server One^1,2^ | PCS26Aa | Firmware updates are vendor-managed | IP-DECT Server |  |
|  | IP-DECT Base Station^1,2^ | PCS26Aa | Firmware updates are vendor-managed | IP-DECT Base Station |  |
|  | RFP6 TDM Digital Base Station^1,2^ | Firmware updates are vendor-managed | PCS16E | DECT Base Station |  |
|  | IP-DECT Gateway^3^ | PCS25B | Firmware updates are vendor-managed | IP-DECT Gateway |  |
| **Ascom** |  |  |  |  | [Ascom Support](https://www.ascom.com/products-and-services/services/support-and-maintenance/) |
|  | Ascom d43^3^ | 2.11.4 | Firmware updates are vendor-managed | Handset |  |
|  | Ascom d63^3^ | 2.11.4 | Firmware updates are vendor-managed | Handset |  |
|  | Ascom d81^3^ | 4.13.1 | Firmware updates are vendor-managed | Handset |  |
|  | Ascom d83^3^ | 1.3.2 | Firmware updates are vendor-managed | Handset |  |
|  | Ascom i63^3^ | 5.0.1 | Firmware updates are vendor-managed | VoWiFi Handset |  |
|  | Ascom Myco 3 DECT^3^ | 3.4.1 | Firmware updates are vendor-managed | Wireless Handset |  |
|  | IP-DECT Access Point IPBSx^3^ | 11.8.8 | Firmware updates are vendor-managed | IP-DECT Access Point |  |
|  | IP-DECT Gateway IPBL^3^ | 11.8.8 | Firmware updates are vendor-managed | IP-DECT Gateway |  |
|  | TDM Base Station^3^ | R3N | Firmware updates are vendor-managed | IP-DECT Base Station |  |
|  | IP-DECT Virtual Appliance IPVM^3^ | 11.8.8 | Firmware updates are vendor-managed | IP-DECT Server |  |
| **Gigaset** |  |  |  |  | [Gigaset Support](https://www.gigaset.com/en_en/cms/home/support/support.html) |
|  | N610 IP PRO^3^ | 2.52.0 | Firmware updates are vendor-managed | Base Station |  |
|  | N670 IP PRO^3^ | 2.52.0 | Firmware updates are vendor-managed | Base Station |  |
|  | N770 IP PRO^3^ | 2.52.0 | Firmware updates are vendor-managed | Base Station |  |
|  | N870 IP PRO^3^ | 2.52.0 | Firmware updates are vendor-managed | Base Station |  |
|  | N870E IP PRO^3^ | 2.52.0 | Firmware updates are vendor-managed | Base Station |  |
|  | N870 VI PRO^3^ | 2.52.0 | Firmware updates are vendor-managed | Base Station |  |
|  | P710 IP PRO^3^ | 10.1.226.16 | Firmware updates are vendor-managed | IP Phone |  |
|  | P810 IP PRO^3^ | 10.1.226.16 | Firmware updates are vendor-managed | IP Phone |  |
|  | P82X IP PRO^3^ | 10.1.226.16 | Firmware updates are vendor-managed | IP Phone |  |
|  | P85X IP PRO^3^ | 10.1.226.16 | Firmware updates are vendor-managed | IP Phone |  |
| **Algo** |  |  |  |  | [Algo Support](https://www.algosolutions.com/post-sale-technical-support/) |
|  | 8180g2^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8186^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8188^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8189^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8190^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8190s^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8196^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8197^3^ | 5.4 | Firmware updates are vendor-managed | Speaker |  |
|  | 8198^3^ | 5.3 | Firmware updates are vendor-managed | Speaker |  |
|  | 8199^3^ | 5.4 | Firmware updates are vendor-managed | Speaker |  |
|  | 8028g2^3^ | 5.3 | Firmware updates are vendor-managed | Intercom |  |
|  | 8063^3^ | 5.3 | Firmware updates are vendor-managed | Intercom |  |
|  | 8201^3^ | 5.3 | Firmware updates are vendor-managed | Intercom |  |
|  | 8203^3^ | 5.4 | Firmware updates are vendor-managed | Intercom |  |
|  | 8128g2^3^ | 5.3 | Firmware updates are vendor-managed | Visual Alerter |  |
|  | 8138^3^ | 5.3 | Firmware updates are vendor-managed | Visual Alerter |  |
|  | 8301^3^ | 5.3 | Firmware updates are vendor-managed | Paging Adapter |  |
|  | 8373^3^ | 5.3 | Firmware updates are vendor-managed | Paging Adapter |  |
|  | 8305^3^ | 5.4 | Firmware updates are vendor-managed | Paging Adapter |  |
|  | 8410^3^ | 5.3 | Firmware updates are vendor-managed | Display Speaker |  |
|  | 8420^3^ | 5.3 | Firmware updates are vendor-managed | Display Speaker |  |
|  | 8450^3^ | 5.4 | Firmware updates are vendor-managed | IP Console |  |
|  | 8507^3^ | 5.4 | Firmware updates are vendor-managed | Speaker |  |
| **Alcatel-Lucent Enterprise** |  |  |  |  | [Alcatel-Lucent Enterprise Support](https://www.al-enterprise.com) |
|  | M3^3^ | 2.14.03.000.2345 | 2.14.28.000.2656 |  |  |
|  | M5^3^ | 2.14.03.000.2345 | 2.14.28.000.2656 |  |  |
|  | M7^3^ | 2.14.03.000.2345 | 2.14.28.000.2656 |  |  |
|  | M3s^3^ | 2.16.07.000.3193 | 2.16.07.000.3193 |  |  |
|  | M5s^3^ | 2.16.07.000.3193 | 2.16.07.000.3193 |  |  |
|  | M7s^3^ | 2.16.07.000.3193 | 2.16.07.000.3193 |  |  |
|  | M7s Pro^3^ | 2.16.07.000.3193 | 2.16.07.000.3193 |  |  |
|  | M8^3^ | 2.14.05.000.2352 | 2.16.07.000.3193 |  |  |
| **Snom** |  |  |  |  |  |
|  | D717^3^ | 10.1.141.13 | 10.1.175.20 | IP Phone |  |
|  | D735^3^ | 10.1.141.13 | 10.1.175.20 | IP Phone |  |
|  | D810^3^ | 10.1.198.23 | 10.1.198.23 | IP Phone |  |
|  | D812^3^ | 10.1.198.23 | 10.1.198.23 | IP Phone |  |
|  | D815^3^ | 10.1.198.23 | 10.1.198.23 | IP Phone |  |
| **2N** |  |  |  |  | [2N EMEA Support](https://www.2n.com/en-GB/support/#verticaltabscontainer-do-you-need-support-or-help)[2N NOAM Support](https://www.2n.com/en-US/support/#verticaltabscontainer-do-you-need-support-or-help)[2N APAC Support](https://www.2n.com/en-AU/support/#verticaltabscontainer-do-you-need-support-or-help) |
|  | SIP Speaker Horn | 2.46.1 | Firmware updates are vendor-managed | SIP Paging Speaker |  |
|  | SIP Speaker | 2.46.1 | Firmware updates are vendor-managed | SIP Paging Speaker |  |
|  | Sentrio Cabin | 2.46.1 | Firmware updates are vendor-managed | Elevator Communication |  |
|  | Lift IP 2.0 | 2.46.1 | Firmware updates are vendor-managed | Elevator Communication |  |
|  | Indoor View - WiFi | 2.46.1 | Firmware updates are vendor-managed | Indoor Monitor |  |
|  | Indoor View | 2.46.1 | Firmware updates are vendor-managed | Indoor Monitor |  |
|  | Indoor Compact | 2.46.1 | Firmware updates are vendor-managed | Indoor Monitor |  |
|  | Indoor Talk | 2.46.1 | Firmware updates are vendor-managed | Indoor Audio Unit |  |
|  | Clip | 2.46.1 | Firmware updates are vendor-managed | Indoor Unit |  |
|  | IP Style | 2.46.1 | Firmware updates are vendor-managed | Video Intercom |  |
|  | IP Verso 2.0 | 2.46.1 | Firmware updates are vendor-managed | Video Intercom |  |
|  | IP Verso | 2.46.1 | Firmware updates are vendor-managed | Video Intercom |  |
|  | IP Vario | 2.46.1 | Firmware updates are vendor-managed | Video Intercom |  |
|  | IP Solo | 2.46.1 | Firmware updates are vendor-managed | Video Intercom |  |
|  | IP One | 2.46.1 | Firmware updates are vendor-managed | Video Intercom |  |
|  | IP Safety | 2.46.1 | Firmware updates are vendor-managed | Emergency Intercom |  |
|  | IP Force | 2.46.1 | Firmware updates are vendor-managed | Rugged Intercom |  |
|  | IP Base | 2.46.1 | Firmware updates are vendor-managed | Intercom Base |  |
|  | IP Video Kit | 2.46.1 | Firmware updates are vendor-managed | Video Intercom Kit |  |
|  | IP Audio Kit | 2.46.1 | Firmware updates are vendor-managed | Audio Intercom Kit |  |
|  | IP Clip2 (WIP) |  | Firmware updates are vendor-managed | Indoor Unit |  |
|  | IP Force2 |  | Firmware updates are vendor-managed | Rugged Intercom |  |
|  | IP SIP Speaker2 |  | Firmware updates are vendor-managed | SIP Paging Speaker |  |
|  | IP Uni |  | Firmware updates are vendor-managed | Audio Intercom |  |
|  | IP Sentrica |  | Firmware updates are vendor-managed | Emergency Communication |  |
|  | IP Sentrilo |  | Firmware updates are vendor-managed | Emergency Communication |  |
| **Avaya** |  |  |  |  | [Avaya Support](https://support.avaya.com/css/public/documents/101095133) |
|  | J129 | 4.1.11.0 | Firmware updates are vendor-managed | IP Phone |  |
|  | J139 | 4.1.11.0 | Firmware updates are vendor-managed | IP Phone |  |
|  | J159 | 4.1.11.0 | Firmware updates are vendor-managed | IP Phone |  |
|  | J169 | 4.1.11.0 | Firmware updates are vendor-managed | IP Phone |  |
|  | J179 | 4.1.11.0 | Firmware updates are vendor-managed | IP Phone |  |
|  | J189 | 4.1.11.0 | Firmware updates are vendor-managed | IP Phone |  |
| **Axis** |  |  |  |  | [Axis Support](https://www.axis.com/support) |
|  | AXIS A8207-VE Mk II Network Video Door Station | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1110-E Network Cabinet Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1111-E Network Cabinet Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1210-E Network Ceiling Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1211-E Network Ceiling Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1310-E Network Horn Speaker Mk II | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1410 Network Mini Speaker Mk II | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1510 Network Pendant Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1511 Network Pendant Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1610-VE Network Sound Projector | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C6110 Network Paging Console | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C8110 Network Audio Bridge | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C8210 Network Audio Amplifier | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1710 Network Display Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS C1720 Network Display Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS D4200-VE Network Strobe Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS D6310 Air Quality Sensor | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS I7010-VE Network Intercom | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS I7010-VE Network Intercom (Safety) | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS I7020 Network Intercom | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS I8016-LVE Network Video Intercom | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS I8116-E Network Video Intercom | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS I8307-VE Network Video Intercom | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M1075-L Mk II Box Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS XC1311 Explosion-Protected Network Horn Speaker | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3057-PLR Mk II Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3077-PLVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3085-V Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3086-V Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3086-V Mic Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3088-V Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3215-LVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M3216-LVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4215-LV Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4215-V Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4216-LV Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4216-V Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4218-LV Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4218-V Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4308-PLE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4317-PLR Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4317-PLVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4318-PLR Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4318-PLVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4327-P Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS M4328-P Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3265-LV Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3265-LVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3265-LVE-3 Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3265-V Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3267-LV Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3267-LVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3267-LVE Mic Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3268-LV Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3268-LVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P3268-SLVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS P9117-PV Panoramic Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS Q1715 Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS Q3536-LVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS Q3538-LVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS Q3538-SLVE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS Q3626-VE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS Q3628-VE Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS Q9307-LV Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS V5925 PTZ Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | AXIS V5938 PTZ Network Camera | 12.6.69 | Firmware updates are vendor-managed |  |  |
|  | D4100-E Network Strobe Siren |  | Firmware updates are vendor-managed |  |  |
|  | F9111 Main Unit |  | Firmware updates are vendor-managed |  |  |
|  | F9114 Main Unit |  | Firmware updates are vendor-managed |  |  |
|  | F9114-B Main Unit |  | Firmware updates are vendor-managed |  |  |
| **Ribbon** |  |  |  |  |  |
|  | EdgeMarc 2900A |  | Firmware updates are vendor-managed | ATA - up to 8FXS ports |  |
| **Tango Mobile** |  |  |  |  |  |
|  | ACL |  | N/A | eSIM |  |
|  | EFT |  | N/A | eSIM |  |
|  | EFU |  | N/A | eSIM |  |
|  | EFV |  | N/A | eSIM |  |
|  | EFW |  | N/A | eSIM |  |
|  | EFX |  | N/A | eSIM |  |
|  | EFY |  | N/A | eSIM |  |
|  | EFZ |  | N/A | eSIM |  |
|  | EXT |  | N/A | eSIM |  |
|  | GMM |  | N/A | eSIM |  |
|  | MOBILE\_UC |  | N/A | eSIM |  |
|  | NTT |  | N/A | eSIM |  |
|  | RDC |  | N/A | eSIM |  |
| **Dstny** |  |  |  |  |  |
|  | CAMOBILE |  | N/A | eSIM |  |
|  | DSTNY-CS |  | N/A | eSIM |  |
|  | IQ |  | N/A | eSIM |  |
|  | PXS |  | N/A | eSIM |  |
|  | TELUS |  | N/A | eSIM |  |

^1^ Device supports dynamic location discovery through LLDP with SIP Gateway.

^2^ Device supports dynamic location discovery with SIP Gateway / Device supports dynamic location discovery with SIP Gateway through BSSID.

^3^ Device supports only static location with SIP Gateway.

Note

For Poly devices, LLDP must be turned on at switch level for subnet length based dynamic location discovery.

Note

Compatible Cisco SIP IP phones support dynamic location discovery over LLDP only.

Note

Customers can use AudioCodes OVOC and Poly Lens to manage device side configuration of their AudioCodes 400 series and Poly VVX/Trio devices respectively.

Note

Spectralink Handsets receive firmware updates over the air from Spectralink IP-DECT servers.

Note

Ascom Handsets receive firmware updates over the air from Ascom IP-DECT servers.

Note

Gigaset Handsets receive firmware updates over the air from Gigaset IP-DECT servers. All Gigaset PRO DECT Handset models are compatible with Microsoft Teams SIP Gateway.

Note

For Yealink DECT Base Stations, use the appropriate region specific firmware version from the list to have the best calling experience.

Note

For support queries, customers using IP-DECT systems with Teams SIP Gateway should reach out to their DECT manufacturer or their implementation channel partners.

Note

For some devices, the minimum firmware version is greater than the approved firmware version. This is because the 3.X version is the Skype for Business version. We update the SIP version, which is 2.X.

Note

For support queries, customers using the Algo Solutions' SIP enabled endpoints listed with Teams SIP Gateway should reach out directly to Algo Solutions. [General Information on Algo integration with Teams](https://www.algosolutions.com/solutions/compatibility/msteams/)[Configuration Guide](https://www.algosolutions.com/wp-content/uploads/2023/04/Configuration-Guide-Teams-2023.pdf)[Troubleshooting Guide](https://www.algosolutions.com/wp-content/uploads/2023/07/Troubleshooting-Algo-Devices-in-MS-Teams.pdf).

Note

Customers should contact their Tango Extend Reseller for support queries related to Tango Extend eSIM endpoints. Help and Support information are provided in the Tango Extend Teams App.

**Emergency Calling** - Emergency calling is supported from the Tango Extend eSIM and uses the Teams number. Teams isn't notified of emergency calls made from the eSIM but will receive returned calls towards the Teams number.

**Tango Extend Supported Features** - Sign-in/out using Tango Extend Teams App with Teams policy sync, Make/receive calls with hold/resume and DTMF, dial-in to meeting, request to join, voicemail and MWI, Teams DND and Call Forwarding.

**Currently Unsupported Features** - Sign-out / sign-in currently creates redundant (signed out) entries for the eSIM endpoint in Teams Admin Center. Tango Extend doesn't support remote sign-in from TAC. If users have both Tango Extend eSIM and Teams mobile client on their phones, then inbound calls prioritize the Teams mobile client. Tango Extend doesn't support call transfer when presented by the mobile dialer menu option.